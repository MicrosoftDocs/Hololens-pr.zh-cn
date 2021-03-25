---
title: 部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 准备
description: 了解如何准备使用 Dynamics 365 指南通过企业连接网络注册 HoloLens 2 设备。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448513"
---
# <a name="prepare---corporate-connected-guide"></a>Prepare - 企业连接指南
## <a name="infrastructure-essentials"></a>基础结构要素
对于个人和公司部署方案，移动设备管理 (MDM) 系统是部署和管理 Windows 10 设备（尤其是 HoloLens 2）所需的基本基础结构。 建议使用 [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) 订阅作为标识提供程序， **并且需要该订阅** 才能支持某些功能。

> [!NOTE]
> 尽管 HoloLens 2 的部署和管理方式与移动设备类似，但它通常用作许多用户之间的共享设备。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是一项基于云的目录服务，可提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已在使用 Azure AD，该 AD 具有三个版本：免费版、高级版 P1 和高级 P2 (请参阅 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)) 。 所有版本都支持 Azure AD 设备注册，但需要高级 P1 才能启用 MDM 自动注册，我们将稍后在本指南中使用它。
> [!Important]
> 必须拥有 Azure AD，因为 HoloLens 设备不支持本地 AD 加入。 如果尚未设置 Azure AD，请按照说明开始操作，在 [Azure Active Directory 中创建新租户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>身份管理
在本指南中， [使用的标识](https://docs.microsoft.com/hololens/hololens-identity) 将是 Azure AD 帐户。 Azure AD 帐户有几个好处，例如：
- 员工使用其 Azure AD 帐户在 Azure AD 中注册设备，并可以在组织的 MDM 解决方案 (Azure AD+MDM 中自动注册它，这需要 [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) 订阅) 。
- Azure AD 帐户可通过 Windows Hello [企业](https://docs.microsoft.com/hololens/hololens-identity) 应用提供 [其他身份验证选项](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 除了 Iris 登录之外，用户还可以从另一台设备登录或使用 FIDO 安全密钥。

> [!WARNING] 
> 员工只能使用一个帐户来初始化设备，因此组织必须控制 **首先启用的帐户**。 所选帐户将确定由谁来控制设备，并影响管理功能。

## <a name="mobile-device-management"></a>移动设备管理
Microsoft Intune 是企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同的凭据在 Intune 中注册用于登录 Office 365 的设备。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 在本指南中，我们将重点介绍使用 Intune，以便使用 HoloLens 2 部署到内部网络。
> [!Important] 
> 必须拥有移动设备管理。 如果你尚未设置它，请遵循本指南和 Intune 入门。

> [!Important]
> 若要使用指南，需要 Azure AD 帐户。

> [!Note] 
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持 Windows 10 全息版 MDM 提供程序包括：AirWatch、MobileIron 和其他。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 你可以找到在 Azure Marketplace 中支持 Azure AD 的 MDM 供应商 [最新列表](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)。

## <a name="network-access"></a>网络访问 
Dynamics 365 Guides 是一款基于云的应用程序。 如果网络管理员具有批准列表，他们可能需要添加连接到 Dynamics 365 服务器所需的 IP 地址和/或终结点。 [详细了解如何取消阻止 IP 地址和 URL。](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>证书
证书通过提供帐户身份验证、Wi-Fi、VPN 加密和 Web 内容的 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上证书，但最佳做法是使用 MDM 系统管理这些证书的整个生命周期，从注册到续订和吊销。 

只要 MDM 系统支持简单证书注册协议 ** (SCEP) ** 或公钥加密标准 **#12 (PKCS#12 **) ) ，在注册证书 (后，MDM 系统就可以自动将它们部署到设备的证书存储。 [了解与 Microsoft Intune 一同使用的证书类型和配置文件](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。 MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。
 
如果你的 MDM 系统已配置为证书，请参考为 [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) 准备证书和网络配置文件，开始为 HoloLens 2 设备部署证书和配置文件。

## <a name="scep"></a>SCEP

SCEP 部署需要以下服务，Web 应用程序代理服务器除外。
- [证书颁发机构](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 服务器角色](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 连接器](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

还必须使用 [Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)应用程序代理或 Web Access 代理将 NDES URL 发布到企业网络外部。 您还可以使用你选择的另一个反向代理。

![SCEP 数据流](./images/hololens2-scep-info-flow.png)

如果网络尚未支持 SCEP，或者不确定网络是否使用 Intune 为 SCEP 正确设置，请引用配置基础结构以支持[使用 Intune 的 SCEP。](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

如果基础结构已支持 SCEP，则需要为 HoloLens 2 将使用的每个 SCEP 证书创建配置文件。 [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) 如果 SCEP 遇到问题，请使用 SCEP 证书配置文件疑难解答使用 [Microsoft Intune 预配证书](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)。

## <a name="pkcs"></a>PKCS
Intune 还支持将私钥和公钥对 (PKCS) 证书。 参考 [有关详细信息，请使用 Microsoft Intune 中的](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) 私钥和公钥证书。

## <a name="proxy"></a>代理
大多数公司 Intranet 网络都利用代理来管理外部流量。 使用 HoloLens 2，你可以为以太网、Wi-Fi VPN 连接配置代理服务器。

有一些不同类型的代理和配置代理的方法。 在本指南中，我们选择选择 WLAN 代理，通过 PAC URL 设置，然后通过 **MDM 进行部署**。 这有一个优势：通过 MDM 自动部署，能够更新 PAC 文件，而不是使用 server：port 配置，最后使用 Wi-Fi 代理将代理配置为仅应用于单个 Wi-Fi 连接，允许设备在连接到其他位置时仍使用。 


有关 Windows 10 的代理设置的更多详细信息，请参阅 [在 Microsoft Intune - Azure Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)创建设备配置文件。

## <a name="line-of-business-apps"></a>业务线应用 
虽然可以通过 Microsoft Store 安装多个应用，但你可能有自己专门创建的自定义应用，以在混合现实中使用。 这些在整个组织中为业务分布的自定义应用称为业务线 (LOB) 应用。
  
有多种方法将应用程序部署到 HoloLens 2 设备。 应用可以通过 MDM、适用于企业 Microsoft Store (MSfB) 直接部署，或者通过预配包进行旁加载。 出于本指南考虑，我们将使用所需的应用安装，通过 MDM 部署应用。 这将允许 LOB 应用在注册完成后自动下载到 HoloLens 设备。

对于没有自己的 LOB 的这些用户，我们将提供一个示例应用来测试此部署流。 此应用将是 [MRTK 示例](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 应用，并且已经预创建并打包，用于测试概念证明。
 
有关应用部署的更多详细信息，请参阅应用 [管理：概述](https://docs.microsoft.com/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 仅支持运行 UWP ARM64 应用。

## <a name="guides-playbook"></a>Guides Playbook
Guides 使用 Microsoft Dataverse 环境作为 Guides 应用的数据存储。 了解 Dataverse 环境如何与 Guides 应用和租户交互的更大全局信息非常重要。 我们不会在本指南中介绍如何管理 dataverse，但请查看部署 [Dynamics 365 Guides - Dynamics 365 Mixed Reality 的基本概念](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)。

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接的部署 - 配置](hololens2-corp-connected-configure.md)