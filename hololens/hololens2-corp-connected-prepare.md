---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 准备
description: 了解如何使用 HoloLens 2 准备通过企业连接网络注册Dynamics 365 Guides。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 88e7d0614cf95f32eaa0434724eddbcb5b8cf863
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636973"
---
# <a name="prepare---corporate-connected-guide"></a>准备 - 企业连接指南
## <a name="infrastructure-essentials"></a>基础结构基本信息
对于个人和公司部署方案，移动设备管理 (MDM) 系统是部署和管理 Windows 10 设备（尤其是 HoloLens 2） 所需的基本基础结构。 建议[Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium)订阅作为标识提供者，并且需要该订阅来支持某些功能。

> [!NOTE]
> 尽管HoloLens 2移动设备一样部署和管理设备，但它通常用作许多用户之间的共享设备。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD是一种基于云的目录服务，可提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已使用 Azure AD，它具有三个版本：免费版、高级版 P1 版和 高级版 P2 版 (请参阅 Azure Active Directory [) 。](https://azure.microsoft.com/documentation/articles/active-directory-editions) 所有版本都支持Azure AD注册，但高级版 P1 才能启用 MDM 自动注册，稍后将在本指南中使用它。
> [!Important]
> 必须创建一个Azure AD，HoloLens设备不支持本地 AD 联接。 如果尚未设置任何Azure AD，请按照说明开始操作，在 Azure Active Directory 中创建新[租户](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>标识管理
在本指南中， [使用的标识](/hololens/hololens-identity) 将Azure AD帐户。 创建帐户有几个Azure AD，例如：

- 员工使用Azure AD帐户在 Azure AD 中注册设备，并且可以将设备自动注册到组织的 MDM 解决方案 (Azure AD+MDM - 需要一Azure AD Premium[订阅](/azure/active-directory/fundamentals/active-directory-get-started-premium)) 。
- Azure AD帐户通过 Windows Hello [](/hololens/hololens-identity) [for Business 提供其他身份验证选项](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 除了 Iris 登录外，用户还可以从另一台设备登录或使用 FIDO 安全密钥。

> [!WARNING] 
> 员工只能使用一个帐户来初始化设备，因此组织必须控制首先 **启用的帐户**。 所选帐户将确定由谁来控制设备，并影响管理功能。

## <a name="mobile-device-management"></a>移动设备管理
Microsoft Intune是企业移动性 + 安全性的一部分，是一种基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，他们使用这些凭据登录到 Office 365。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 在本指南中，我们将重点介绍使用 Intune，以便使用 HoloLens 2。
> [!Important] 
> 必须拥有移动设备管理。 如果尚未设置它，请按照本指南和 Intune 入门操作。

> [!Important]
> 若要使用指南，Azure AD帐户。

> [!Note] 
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持这些服务的 MDM Windows 10 全息版包括：AirWatch、MobileIron 等。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可以在 中查找支持托管的 MDM 供应商[Azure AD Azure 市场。](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>网络访问 
Dynamics 365 Guides是基于云的应用程序。 如果网络管理员具有批准列表，他们可能需要添加连接到 Dynamics 365 服务器所需的 IP 地址和/或终结点。 [详细了解如何取消阻止 IP 地址和 URL。](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>证书
证书通过提供帐户身份验证、Wi-Fi身份验证、VPN 加密和 Web 内容的 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上证书，但最佳做法是使用 MDM 系统在整个生命周期（从注册到续订和吊销）管理这些证书。 

只要 MDM 系统支持 **简单证书注册协议 (SCEP**) 或公钥加密标准 (#12 (PKCS #12) ) ，MDM 系统就可以在注册这些证书后自动将它们部署到设备的 **证书存储。** [了解用于证书的证书类型和Microsoft Intune。](/mem/intune/protect/certificates-configure) MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。

如果 MDM 系统已针对证书进行配置，请[](/hololens/hololens-certificates-network)参考准备证书和网络配置文件HoloLens 2开始为 HoloLens 2 设备部署证书和配置文件。

## <a name="scep"></a>SCEP

SCEP 部署需要以下服务，Web 应用程序代理服务器除外。

- [证书颁发机构](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 服务器角色](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 连接器](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

还必须使用应用程序代理或客户端代理 将 NDES URL 发布到Azure AD [网络Web 访问外部](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)。 也可以使用所选的其他反向代理。

![SCEP 数据流](./images/hololens2-scep-info-flow.png)

如果网络尚未支持 SCEP，或者不确定网络是否使用 Intune 为 SCEP 正确设置，请引用配置基础结构以支持[使用 Intune 的 SCEP。](/mem/intune/protect/certificates-scep-configure)

如果基础结构已支持 SCEP，则需要为证书组[](/mem/intune/protect/certificates-profile-scep)将使用的每个[](/mem/configmgr/protect/deploy-use/create-certificate-profiles)SCEP 证书HoloLens 2配置文件。 如果遇到 SCEP 问题，请使用[SCEP](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)证书配置文件的故障排除来预配证书Microsoft Intune。

## <a name="pkcs"></a>PKCS
Intune 还支持对 PKCS 证书使用 (公钥) 对。 参考[有关详细信息，请参阅在](/mem/intune/protect/certificates-pfx-configure)Microsoft Intune 使用私钥和公钥证书。

## <a name="proxy"></a>代理
大多数企业 Intranet 网络都利用代理来管理外部流量。 借助HoloLens 2，你可以为以太网、Wi-Fi VPN 连接配置代理服务器。

有一些不同类型的代理和配置代理的方法。 在本指南中，我们选择选择 **Wi-Fi** 代理，通过 PAC URL 进行设置，然后通过 MDM 进行部署。 这具有以下优点：通过 MDM 自动部署，能够更新 PAC 文件而不是使用 server：port 配置，最后使用 Wi-Fi 代理将代理配置为仅应用于单个 Wi-Fi 连接，从而允许设备在连接另一个位置时仍然使用。

有关适用于 Windows 10 的代理设置的更多详细信息，请参阅为 Wi-Fi 中的设备创建 Microsoft Intune[配置文件 - Azure。](/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>业务线应用 
虽然可以通过 Microsoft Store 安装多个应用，但你可能有你自己的自定义应用，你已专门创建该应用以在混合现实中使用。 在整个组织中为业务分发的这些自定义应用称为业务线 (LOB) 应用。
  
有多种方法将应用程序部署到HoloLens 2设备。 可以直接通过 MDM 部署应用，适用于企业的 Microsoft Store (MSfB) 预配包进行旁加载。 为了本指南，我们将使用所需的应用安装通过 MDM 部署应用。 这样，LOB 应用可以在完成注册后自动下载到HoloLens设备。

对于没有自己的 LOB 的你，我们将提供一个示例应用来测试此部署流。 此应用将是 [MRTK 示例](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 应用，并且已预创建并打包，用于测试概念证明。

有关应用部署的更多详细信息，请参阅应用 [管理：概述](/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2仅支持运行 UWP ARM64 应用。

## <a name="guides-playbook"></a>指南 Playbook
指南使用 Microsoft Dataverse 环境作为 Guides 应用的数据存储。 必须更了解 Dataverse 环境如何与 Guides 应用和租户交互。 本指南中不会介绍如何管理 dataverse，但请查看有关部署 Dynamics 365 Guides - [Dynamics 365 混合现实 的基本概念](/dynamics365/mixed-reality/guides/admin-deployment-playbook)。

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接部署 - 配置](hololens2-corp-connected-configure.md)