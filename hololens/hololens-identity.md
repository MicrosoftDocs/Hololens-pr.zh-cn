---
title: 管理 HoloLens 的用户标识和登录
description: 了解如何管理 HoloLens 设备的用户标识、多用户支持、安全性、企业身份验证和登录。
keywords: HoloLens， 用户， 帐户， AAD， Azure AD， adfs， microsoft 帐户， msa， 凭据， 参考
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400682"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是 IT 专业人员和技术人士的技术参考。 如果你正在寻找 HoloLens 设置说明，请阅读"设置[HoloLens (第一代) "](hololens1-start.md)或"[设置 HoloLens 2"。](hololens2-start.md)

与其他 Windows 设备一样，HoloLens 始终在用户上下文中运行。 始终存在用户标识。 HoloLens 处理标识的方式与其他 Windows 10 设备几乎相同。 本文深入探究了 HoloLens 上的标识，重点介绍 HoloLens 与其他 Windows 10 设备的区别。

HoloLens 支持多种类型的用户标识。 可以使用一个或多个用户帐户登录。 下面概述了 HoloLens 上的标识类型和身份验证选项：

| 标识类型 | 每个设备的帐户 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (需要 Azure AD Premium)  | 64 | <ul><li>Azure Web 凭据提供程序</li><li>Azure Authenticator 应用</li><li>HoloLens (2) &ndash; 1 生物识别 <sup></sup> </li><li>适用于 HoloLens (第一代) 的 PIN 可选 &ndash; ，HoloLens 2 需要 PIN</li><li>密码</li></ul> |
| [Microsoft 帐户 (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>仅 (&ndash; HoloLens) Iris 生物识别</li><li>适用于 HoloLens (第一代) 的 PIN 可选 &ndash; ，HoloLens 2 需要 PIN</li><li>密码</li></ul> |
| [本地帐户](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 密码 |

Azure AD 和 MSA (云连接) 提供了更多功能，因为它们可以使用 Azure 服务。  

> [!NOTE]
> 1 - HoloLens 2 设备可支持最多 64 个 Azure AD 帐户，但其中只有 10 个帐户可以注册 Iris 身份验证。 这与 Windows Hello 企业应用的其他生物 [识别身份验证选项一致](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)。

## <a name="setting-up-users"></a>设置用户

设置新用户的最常见方式是在 HoloLens 全新体验期间 (OOBE) 。 在设置过程中，HoloLens 会提示用户使用他们希望在设备上使用的帐户登录。 此帐户可以是使用者 Microsoft 帐户或在 Azure 中配置的企业帐户。 请参阅设置[HoloLens (第一代) ](hololens1-start.md) [或 HoloLens 2。](hololens2-start.md)

与其他设备上 Windows 一样，在安装期间登录会创建设备的用户配置文件。 用户配置文件存储应用和数据。 同一帐户还使用 Windows 帐户管理器 API 为边缘或 Skype 等应用提供单一登录。  

如果使用企业或组织帐户登录 HoloLens，HoloLens 将注册组织的 IT 基础结构。 此注册允许 IT 管理员配置移动设备管理 (MDM) 将组策略发送到 HoloLens。

默认情况下，与其他 Windows 10 设备一样，当 HoloLens 重新启动或从待机状态恢复时，你必须重新登录。 可以使用"设置"应用更改此行为，也可以由组策略控制该行为。

### <a name="linked-accounts"></a>链接帐户

与桌面版 Windows 一样，你可以将其他 Web 帐户凭据链接到 HoloLens 帐户。 通过此类链接，可以更轻松地跨应用或访问应用 (如应用商店) 或合并对个人和工作资源的访问权限。 将帐户连接到设备后，你可以授予将设备用于应用的权限，以便你不必单独登录每个应用。

链接帐户不会分离在设备上创建的用户数据，如图像或下载。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>仅设置 Azure AD (多用户) 

HoloLens 支持来自同一 Azure AD 租户的多个用户。 若要使用此功能，必须使用属于组织的帐户来设置设备。 随后，来自同一租户的其他用户可以从登录屏幕或点击"开始"面板上的用户磁贴登录到设备。 一次只能登录一个用户。 当用户登录时，HoloLens 将退出上一个用户。 除 Azure AD 加入的情况外，设备上的第一个用户被视为设备 [所有者，了解有关设备所有者的信息](security-adminless-os.md#device-owner)。

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用会删除所有用户的应用。  

使用 Azure AD 帐户设置的设备将不允许使用 Microsoft 帐户登录设备。 使用的所有后续帐户必须是来自设备同一租户的 Azure AD 帐户。 你仍 [可以使用 Microsoft 帐户](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 登录支持它 (Microsoft Store) 。 若要从使用 Azure AD 帐户更改为 Microsoft 帐户以登录设备，必须[重新控制设备。](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (** 第一代) 开始在 [Windows 10 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 年 4 月更新中支持多个 Azure AD 用户，作为 Windows [Holographic for Business](hololens-upgrade-enterprise.md)的一部分。

## <a name="removing-users"></a>删除用户

可以通过访问"设置帐户"其他用户来从**设备**  >  ****  >  **中删除用户**。 此操作还通过从设备中删除该用户的所有应用数据来回收空间。  

## <a name="using-single-sign-on-within-an-app"></a>在应用中使用单一登录

作为应用开发人员，可以使用 Windows 帐户管理器 [API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)利用 HoloLens 上的链接标识，就像在其他 Windows 设备上一样。 GitHub 上提供了这些 API 的一些代码示例 [：Web 帐户管理示例](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

当应用请求身份验证令牌时，必须处理任何可能会发生的帐户中断，例如请求用户同意帐户信息、双重身份验证等。

如果你的应用需要之前未链接的特定帐户类型，你的应用可以要求系统提示用户添加一个帐户类型。 此请求将触发帐户设置窗格以作为应用的模式子级启动。 对于 2D 应用，此窗口直接在应用中心呈现。 对于 Unity 应用，此请求会暂时将用户从全息应用退出，以呈现子窗口。 有关自定义此窗格中的命令和操作的信息，请参阅 [WebAccountCommand 类](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>企业身份验证和其他身份验证

如果你的应用使用其他类型的身份验证（如 NTLM、Basic 或 Kerberos），可以使用 Windows [凭据 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 收集、处理和存储用户的凭据。 收集这些凭据的用户体验与其他云驱动的帐户中断非常相似，显示为 2D 应用顶部的子应用，或短暂暂停 Unity 应用以显示 UI。

## <a name="deprecated-apis"></a>弃用的 API

HoloLens 开发不同于针对桌面进行开发的一种方式是 [，OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API 不受完全支持。 尽管 API 在主帐户正常运行时返回令牌，但是中断（如本文中所述的中断）不会为用户显示任何 UI，并且无法正确验证帐户。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens 第一代 (上是否支持 Windows Hello 企业) ？

HoloLens 第一代 (支持使用 PIN 登录) 的 Windows Hello 企业 (版本) 。 若要在 HoloLens 上允许 Windows Hello 企业 PIN 登录：

1. HoloLens 设备必须由 [MDM 管理](hololens-enroll-mdm.md)。
1. 你必须为设备启用 Windows Hello 企业应用。  (Microsoft [Intune 的说明。) ](https://docs.microsoft.com/intune/windows-hello)
1. 在 HoloLens 上，用户随后**可以使用"设置**  >  **登录选项**  >  **添加 PIN"** 来设置 PIN。

> [!NOTE]
> 使用 Microsoft 帐户登录的用户还可以在"设置登录选项添加****  >  **PIN"中设置**  >  **PIN。** 此 PIN 与[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相关联，而不是[Windows Hello 企业应用。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>如何在 HoloLens 2 上实现 Iris 生物识别身份验证？

HoloLens 2 支持 Iris 身份验证。 Iris 基于 Windows Hello 技术，并且受 Azure Active Directory 和 Microsoft 帐户支持使用。 Iris 的实现方式与其他 Windows Hello 技术相同，并实现 1/100K 生物识别安全。

有关详细信息， [请参阅 Windows Hello 的生物](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 识别要求和规范。 了解有关 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 和 Windows [Hello 企业应用计划更多信息](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>帐户类型如何影响登录行为？

如果应用登录策略，则会始终遵循该策略。 如果未应用登录策略，则每个帐户类型的默认行为为：

- **Azure AD：** 默认情况下要求进行身份验证，并且"设置"可**** 配置以不再要求进行身份验证。
- **Microsoft 帐户**：锁定行为不同，允许自动解锁，但重启时仍然需要登录身份验证。
- **本地帐户**：始终要求以密码形式进行身份验证，在"设置"中不可 **配置**

> [!NOTE]
> 当前不支持非活动计时器，这意味着仅在设备进入 StandBy 时才遵守 **AllowIdleReturnWithoutPassword** 策略。

## <a name="additional-resources"></a>其他资源

阅读 Windows 10 安全和标识文档中有关用户标识 [保护和身份验证的更多内容](https://docs.microsoft.com/windows/security/identity-protection/)。

了解有关在 Azure 混合标识文档中全面设置 [混合标识基础结构的信息](https://docs.microsoft.com/azure/active-directory/hybrid/)。
