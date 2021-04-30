---
title: 部署指南–企业连接的 HoloLens 2 （含 Dynamics 365 指南）-准备
description: 了解如何准备使用 Dynamics 365 指南通过企业连接的网络注册 HoloLens 2 设备。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308421"
---
# <a name="prepare---corporate-connected-guide"></a>准备-企业连接指南
## <a name="infrastructure-essentials"></a>基础结构概要
对于个人和公司部署方案， (MDM) system 这一移动设备管理是部署和管理 Windows 10 设备（特别是 HoloLens 2）所需的基本基础结构。 建议将 [Azure AD Premium 订阅](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) 作为标识提供者，并 **要求** 支持某些功能。

> [!NOTE]
> 尽管 HoloLens 2 的部署和管理与移动设备类似，但它通常用作许多用户之间的共享设备。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是一种基于云的目录服务，提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已使用 Azure AD，其中有三个版本：免费版、高级版 P1 和高级 P2 (，请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)) 。 所有版本都支持 Azure AD 设备注册，但要启用 MDM 自动注册，需要使用高级 P1，稍后将在本指南中使用。
> [!Important]
> 使用 Azure AD，因为 HoloLens 设备不支持本地 AD 加入。 如果尚未设置 Azure AD，请按照说明开始操作，并 [在 Azure Active Directory 中创建新租户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>标识管理
在本指南中，使用的 [标识](https://docs.microsoft.com/hololens/hololens-identity) 将是 Azure AD 帐户。 Azure AD 帐户有多个优点，例如：
- 员工使用其 Azure AD 帐户在 Azure AD 中注册设备，并可使用组织的 MDM 解决方案自动注册该设备 (Azure AD + MDM –要求 [Azure AD Premium 订阅](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)) 。
- 通过[Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)，Azure AD 帐户有其他[身份验证选项](https://docs.microsoft.com/hololens/hololens-identity)。 除了 Iris 登录外，用户还可以从其他设备登录或使用 FIDO 安全密钥。

> [!WARNING] 
> 员工只能使用一个帐户来初始化设备，因此 **，组织必须先控制首先启用哪个帐户**。 所选帐户将确定由谁来控制设备，并影响管理功能。

## <a name="mobile-device-management"></a>移动设备管理
Microsoft Intune 是企业移动性 + 安全性的一部分，它是一种基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，以用于登录到 Office 365。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 出于本指南的目的，我们将重点介绍如何使用 Intune 来实现使用 HoloLens 2 的内部网络部署。
> [!Important] 
> 有必要进行移动设备管理。 如果尚未设置，请遵循本指南并开始使用 Intune。

> [!Important]
> 为了使用指南，需要 Azure AD 帐户。

> [!Note] 
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持 Windows 10 全息版的 MDM 提供程序包括： AirWatch、MobileIron 和其他。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可以在 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)中找到支持 Azure AD 的最新 MDM 供应商列表。

## <a name="network-access"></a>网络访问 
Dynamics 365 指南是一个基于云的应用程序。 如果网络管理员具有审批列表，则他们可能需要添加连接到 Dynamics 365 服务器所需的 IP 地址和/或终结点。 [了解有关取消阻止 IP 地址和 url 的详细信息](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)。

## <a name="certificates"></a>证书
证书通过提供 web 内容的帐户身份验证、Wi-Fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上的证书，但最佳做法是使用 MDM 系统管理整个生命周期中的那些证书–从注册到续订和吊销。 

你的 MDM 系统在注册这些证书后，可以将其自动部署到设备的证书存储 (，只要你的 MDM 系统支持 **简单证书注册协议 (SCEP)** 或 **公钥加密标准 #12 (PKCS # 12)**) 。 [了解用于 Microsoft Intune 的证书类型和配置文件](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。 MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。
 
如果已为证书配置了 MDM 系统，请参阅 [为 hololens 2 准备证书和网络配置文件](https://docs.microsoft.com/hololens/hololens-certificates-network) ，以便为你的 hololens 2 设备开始部署证书和配置文件。

## <a name="scep"></a>SCEP

以下服务是 SCEP 部署所必需的，但 Web 应用程序代理服务器除外。
- [证书颁发机构](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 服务器角色](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 连接器](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

还必须使用 [Azure AD 应用程序代理或 Web 访问 proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)将 NDES URL 发布到公司网络。 也可以使用所选的其他反向代理。

![SCEP 数据流](./images/hololens2-scep-info-flow.png)

如果你的网络尚不支持 SCEP，或者你不确定是否已为 SCEP 和 Intune 正确设置了网络，则参考  [配置基础结构以支持通过 intune 的 scep](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)。

如果你的基础结构已支持 SCEP，则需要为 HoloLens 2 将使用的每个 SCEP 证书 [创建](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) 一个 [配置文件](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) 。 如果在 SCEP 中遇到问题，请使用 [使用 SCEP 证书配置文件进行故障排除，通过 Microsoft Intune 设置证书](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)。

## <a name="pkcs"></a>PKCS
Intune 还支持对 (PKCS) 证书使用私钥和公钥对。 有关详细信息， [请参阅在 Microsoft Intune 中使用私钥和公钥证书](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) 。

## <a name="proxy"></a>代理
大多数公司 intranet 网络都利用代理来管理外部流量。 使用 HoloLens 2，你可以为以太网、Wi-Fi 和 VPN 连接配置代理服务器。

有几种不同类型的代理和配置代理的方式。 出于本指南的目的，我们将选择 **"wi-fi 代理"、"通过 PAC URL 设置"，并通过 MDM 部署**。 这就是通过 MDM 自动部署的优点，能够更新 PAC 文件而不是使用服务器：端口配置，最后使用 Wi-Fi proxy 将代理配置为仅应用于单个 Wi-Fi 连接，这样，即使在其他位置连接，仍可使用设备。 


有关适用于 Windows 10 的代理设置的更多详细信息，请参阅 [在 Microsoft Intune 中为设备创建 Wi-Fi 配置文件](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)。

## <a name="line-of-business-apps"></a>业务线应用 
尽管可以通过 Microsoft Store 安装多个应用程序，但您可能已创建自己的自定义应用程序，该应用程序专门用于混合现实。 在整个组织中为你的企业分发的这些自定义应用称为业务线 (LOB) 应用。
  
可以通过多种方式将应用程序部署到 HoloLens 2 设备。 可以通过 MDM、Business (MSfB) 的 Microsoft Store，或通过预配包旁加载部署应用。 出于本指南的目的，我们将通过使用所需的应用安装来通过 MDM 部署应用。 这样一来，在完成注册后，LOB 应用就会自动下载到 HoloLens 设备。

对于没有自己 LOB 的用户，我们将提供一个示例应用来测试此部署流程。 此应用将是 [MRTK 示例](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 应用，已经预先构建并打包以测试概念证明。
 
有关应用部署的更多详细信息，请参阅 [应用管理：概述](https://docs.microsoft.com/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 仅支持运行 UWP ARM64 应用。

## <a name="guides-playbook"></a>向导手册手册
指南使用 Microsoft Dataverse 环境作为指导应用的数据存储。 务必了解 Dataverse 环境如何与指南应用和租户进行交互的更大的图片。 在本指南中，我们不会介绍如何管理 dataverse，但请查看 [有关部署 dynamics 365 指南的基本概念-dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)。

## <a name="next-step"></a>后续步骤 
> [!div class="nextstepaction"]
> [企业连接部署-配置](hololens2-corp-connected-configure.md)