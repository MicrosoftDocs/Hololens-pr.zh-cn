---
title: HoloLens 基础结构指南
description: 了解 HoloLens 设备的基础结构指南，包括无线网络支持、远程协助和移动设备管理。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189063"
---
# <a name="configure-your-network-for-hololens"></a>为 HoloLens 配置网络

文档的此部分将需要以下人员：

1. 具有对代理/防火墙进行更改的权限的网络管理员
2. Azure Active Directory 管理员
3. 移动设备管理器管理员

## <a name="infrastructure-requirements"></a>基础结构要求

HoloLens 从核心看来是与 Azure 集成的 Windows 移动设备。  它最适用于可使用无线网络 (wi-fi) 并可访问 Microsoft 服务的商业环境。

关键的云服务包括：

- Azure Active Directory (Azure AD)
- Windows 更新 (WU) 

商业客户需要通过企业移动性管理 (EMM) 或移动设备管理 (MDM) 基础结构来大规模管理 HoloLens 设备。  本指南使用 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) 作为示例，但任何完全支持 Microsoft 策略的提供商都可支持 HoloLens。  询问你的移动设备管理提供商是否支持 HoloLens 2。

HoloLens 支持一组有限的从云断开的连接体验。

### <a name="wireless-network-eap-support"></a>无线网络 EAP 支持

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens 特定网络要求

确保你的网络防火墙允许终结点的[此列表](hololens-offline.md)。 这将使 HoloLens 能够正常工作。

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist 特定网络要求

1. 为保证 Remote Assist 的最佳性能，推荐的带宽为 1.5Mbps。 若要了解其他信息，请参阅[详细的网络要求](/MicrosoftTeams/prepare-network)。
**（请注意，即使你的网络速度无法至少达到 1.5Mbps，Remote Assist 也仍可以正常工作。但工作质量可能会受到影响。）**
1. 请确保网络防火墙上允许使用这些端口和 URL，以使 Microsoft Teams 能够正常运行。 随时了解[最新的端口列表](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。

- 详细了解特定的 [Remote Assist 的网络要求](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。 
- 详细了解如何[为 Microsoft Teams 准备组织网络](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Guides 特定网络要求

Guides 仅需要通过网络访问权限下载并使用该应用。

## <a name="azure-active-directory-guidance"></a>Azure Active Directory 指南

> [!NOTE]
> 仅当贵公司计划管理 HoloLens 时，才需要执行此步骤。

1. 确保你拥有 Azure AD 许可证。
若要了解更多信息，请参阅 [HoloLens 许可要求](hololens-licenses-requirements.md)。

1. 如果计划使用自动注册，必须[配置 Azure AD 注册。](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. 确保贵公司的用户在 Azure Active Directory (Azure AD) 中。
请参阅以下有关添加用户的[说明](/azure/active-directory/fundamentals/add-users-azure-active-directory)。

1. 建议将需要类似许可证的用户添加到相同组中。
    1. [创建一个组](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [将用户添加到组](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 确保为贵公司的用户（或用户组）分配了所需的许可证。
如果你需要分配许可证，请按照以下[操作说明](/azure/active-directory/fundamentals/license-users-groups)执行。

1. 仅当希望用户向你注册自己的 HoloLens/移动设备时，才执行此步骤。（有三个选项。）这些步骤可确保公司的用户（或用户组）可以添加设备。
    1. **选项 1：** 向所有用户授予将设备加入 Azure AD 的权限。
“以管理员身份登录 Azure 门户” > “Azure Active Directory” > “设备” > “设备设置” >
将可将设备加入 Azure AD 的用户设置为“所有人”    

    1. 选项 2：向选定用户/组授予将设备加入 Azure AD 的权限。“以管理员身份登录 Azure 门户” > “Azure Active Directory” > “设备” > “设备设置” >
“将可将设备加入 Azure AD 的用户设置为‘选定用户’”
![图片显示了已加入 Azure AD 的设备的配置。](images/azure-ad-image.png)     ****

    1. **选项 3：** 可阻止所有用户将其设备加入到域中。 这意味着需要手动注册所有设备。

## <a name="mobile-device-manager-guidance"></a>移动设备管理器指南

### <a name="ongoing-device-management"></a>持续设备管理

> [!NOTE]
> 只有公司计划管理 HoloLens 时才需要此步骤。

持续设备管理依赖于移动设备管理基础结构。  大多数具有相同的常规功能，但用户界面可能会有很大差异。

1. [CSP（配置服务提供商）](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)可用于创建和部署网络上设备的管理设置。 有关参考，请参阅 [HoloLens CSP 列表](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。

1. [合规性策略](/intune/device-compliance-get-started)是一些规则和设置，设备必须满足这些规则和设置才能在企业基础结构中合规。 将这些策略与条件访问结合使用，可阻止不合规的设备访问公司资源。 例如，可以创建一个要求启用 Bitlocker 的策略。

1. [创建合规性策略](/intune/protect/compliance-policy-create-windows)。

1. 条件访问可以允许/拒绝移动设备和移动应用程序访问公司资源。 [计划 CA 部署](/azure/active-directory/conditional-access/plan-conditional-access)文档和[最佳做法](/azure/active-directory/conditional-access/best-practices)文档可能会对你有所帮助。

1. [本文](/intune/fundamentals/windows-holographic-for-business)介绍 Intune 的 HoloLens 管理工具。

1. [创建设备配置文件](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>管理更新

Intune 包含名为“更新通道”的功能，适用于 Windows 10 设备，包括 HoloLens 2 和 HoloLens v1（具有 Holographic for Business）。 更新通道包括一组设置，用于确定安装更新的时间和方式。

例如，你可以创建一个维护时段来安装更新，也可以选择在安装更新后重新启动。  还可以选择无限期暂停更新，直至到你准备好进行更新。

详细了解如何[使用 Intune 配置更新通道](/intune/windows-update-for-business-configure)。

### <a name="application-management"></a>应用程序管理

可通过以下工具管理 HoloLens 应用程序：

1. Microsoft Store  
  Microsoft Store 是在 HoloLens 上分发和使用应用程序的最佳方式。  商店中已有大量的核心 HoloLens 应用程序，你还可以[发布自己的应用程序](/windows/uwp/publish/)。  
  商店中的所有应用程序都向所有人公开，但如果这不可接受，请使用适用于企业的 Microsoft Store。  

1. [适用于企业的 Microsoft Store](/microsoft-store/)  
  适用于企业和教育的 Microsoft Store 是用于企业环境的自定义商店。  通过该产品，可以使用内置于 Windows 10 和 HoloLens 的 Microsoft Store 为组织查找、获取、分发和管理应用。  它还可用于部署特定于你的商业环境而不适合公开的应用程序。

1. 通过 Intune 或其他移动设备管理解决方案进行应用程序部署和管理  
  大多数移动设备管理解决方案（包括 Intune）提供将业务线应用程序直接部署到一组注册设备的方法。  请参阅本篇关于 [Intune 应用安装](/intune/apps-deploy)的文章。

1. 不推荐设备门户  
  还可使用 Windows 设备门户直接在 HoloLens 上安装应用程序。  不建议这样做，因为必须启用开发人员模式才可使用设备门户。

详细了解[在 HoloLens 上安装应用](hololens-install-apps.md)。

### <a name="certificates"></a>证书

可通过 MDM 提供商分发证书。 如果贵公司需要证书，Intune 支持 PKCS、PFX 和 SCEP。 了解哪种证书适合公司很重要。 请参阅[证书配置](/intune/protect/certificates-configure)文档，确定最合适的证书。 如果计划将证书用于 HoloLens 身份验证，则 PFX 或 SCEP 可能适合你。

关于使用 [SCEP](/intune/protect/certificates-profile-scep)，请参阅以下步骤。

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>如何升级到 Holographics for Business 商业套件

> [!NOTE]
> Windows Holographics for Business（商业套件）仅适用于 HoloLens 第 1 代设备。 配置文件不会应用于 HoloLens 2 设备。

可以在[全息升级](/intune/configuration/holographic-upgrade)文档中找到升级到商业套件的说明。

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>如何使用 Microsoft Intune 配置展台模式

1. 将 Microsoft Store 同步到 Intune（请参阅以下[说明](/intune/apps/windows-store-for-business)）。

1. 检查应用设置
    1. 登录到你的 Microsoft Store 企业帐户
    1. **“管理”>“产品和服务”>“应用和软件”>“选择要同步的应用”>“专用应用商店的可用性”>“选择‘每个人’或‘特定组’”**
        >[!NOTE]
        >如果看不到所需的应用，必须通过在应用商店中搜索应用来“获取”该应用。 **单击右上角的“搜索”栏 > 输入应用名称 > 单击应用 > 选择“获取”** 。
    1. 如果“Intune”>“客户端应用”>“应用”中未显示你的应用，你可能需要再次[同步应用](/intune/apps/windows-store-for-business#synchronize-apps)。

1. [创建用于展台模式的设备配置文件](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> 通过使用“Azure AD”作为“用户登录类型”，可将不同用户配置为使用不同的展台模式体验。 但是，此选项仅在多应用展台模式下可用。 多应用展台模式适用于单个应用和多个应用。

![图片显示了 Intune 中展台模式的配置。](images/aad-kioskmode.png)

对于其他 MDM 服务，请参阅提供商文档中的说明。 如果需要使用自定义设置和完整 XML 配置在 MDM 服务中设置展台，请参阅 [HoloLens 展台](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)说明。

## <a name="certificates-and-authentication"></a>证书和身份验证

可通过 MDM 部署证书（请参阅 [MDM 部分](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)的“证书”）。 还可以通过包预配将证书部署到 HoloLens。 有关其他信息，请参阅 [HoloLens 预配](hololens-provisioning.md)。

### <a name="additional-intune-quick-links"></a>其他 Intune 快速链接

1. [创建配置文件：](/intune/configuration/device-profile-create)通过配置文件可以添加和配置将推送到组织内部设备的设置。

