---
title: 管理 HoloLens 的用户标识和登录
description: 了解如何管理用户标识、多用户支持、安全、企业身份验证和登录。
keywords: HoloLens，用户，帐户，AAD，Azure AD，adfs，microsoft 帐户，msa，凭据，引用
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308503"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是针对 IT 专业人员和技术爱好者的技术参考。 如果正在查找 HoloLens 设置说明，请参阅[设置 hololens (第一代) ](hololens1-start.md)"或"[设置 hololens 2](hololens2-start.md)"。

与其他 Windows 设备一样，HoloLens 始终在用户上下文中运行。 始终存在用户标识。 HoloLens 处理标识的方式与其他 Windows 10 设备的处理方式几乎相同。 本文是针对 HoloLens 的标识的深入了解，并且侧重于 HoloLens 与其他 Windows 10 设备的不同之处。

HoloLens 支持多种用户标识。 你可以使用一个或多个用户帐户登录。 以下概述了 HoloLens 上的标识类型和身份验证选项：

| 标识类型 | 每台设备的帐户 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (需要 Azure AD Premium)  | 64 | <ul><li>Azure web 凭据提供程序</li><li>Azure Authenticator 应用</li><li>生物识别 (Iris) &ndash; HoloLens 2 仅<sup>1</sup> </li><li>为 hololens &ndash; (第一代) 固定可选，为 hololens 2 所需</li><li>Password</li></ul> |
| [Microsoft 帐户 (MSA) ](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生物识别 (Iris) &ndash; 仅 HoloLens 2</li><li>为 hololens &ndash; (第一代) 固定可选，为 hololens 2 所需</li><li>Password</li></ul> |
| [本地帐户](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Password |

与云连接的帐户 (Azure AD 和 MSA) 提供更多功能，因为它们可以使用 Azure 服务。  

> [!NOTE]
> 1-虽然 HoloLens 2 设备最多可以支持 64 Azure AD 帐户，但只有10个帐户才能注册 Iris Authentication。 这与 [适用于 Windows Hello 企业版的其他生物识别身份验证选项](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)一致。

## <a name="setting-up-users"></a>设置用户

设置新用户的最常见方法是在 (OOBE) 的 HoloLens 全新体验。 在安装过程中，HoloLens 会提示用户使用他们要在设备上使用的帐户登录。 此帐户可以是使用者 Microsoft 帐户或已在 Azure 中配置的企业帐户。 请参阅设置 [hololens (第一代) ](hololens1-start.md) 或 [HoloLens 2](hololens2-start.md)。

与其他设备上的 Windows 一样，在安装过程中登录会在设备上创建用户配置文件。 用户配置文件存储应用程序和数据。 同一帐户还通过使用 Windows 帐户管理器 Api 为应用（如 Edge 或 Skype）提供单一登录。  

如果使用企业帐户或组织帐户登录到 HoloLens，则 HoloLens 会在组织的 IT 基础结构中注册。 此注册可让你的 IT 管理员配置移动设备管理 (MDM) 将组策略发送到 HoloLens。

默认情况下，对于其他 Windows 10 设备，你必须在 HoloLens 重新启动或从待机状态恢复时再次登录。 您可以使用 "设置" 应用程序来更改此行为，也可以通过组策略控制该行为。

### <a name="linked-accounts"></a>关联的帐户

与 Windows 的桌面版本一样，你可以将其他 web 帐户凭据链接到你的 HoloLens 帐户。 此类链接使你可以更轻松地跨应用程序或应用程序内访问资源 (例如存储) 或合并对个人资源和工作资源的访问。 将帐户连接到设备后，你可以向应用授予使用设备的权限，以便无需单独登录到每个应用。

链接帐户不会分离在设备上创建的用户数据，如图像或下载。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>仅 (Azure AD 设置多用户支持) 

HoloLens 支持同一 Azure AD 租户中的多个用户。 若要使用此功能，你必须使用属于你的组织的帐户来设置设备。 随后，同一租户中的其他用户可以通过登录屏幕或通过点击 "开始" 面板上的 "用户" 磁贴登录到该设备。 一次只能有一个用户登录。 当用户登录时，HoloLens 将注销上一个用户。 设备上的第一个用户被视为设备所有者，但在 Azure AD 联接的情况下，请 [详细了解设备所有者](security-adminless-os.md#device-owner)。

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用会为所有用户删除应用。  

使用 Azure AD 帐户设置的设备将不允许使用 Microsoft 帐户登录到设备。 使用的所有后续帐户都必须是与设备来自同一租户的 Azure AD 帐户。 你仍可以 [使用 Microsoft 帐户登录到](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 支持它的应用程序 (例如 Microsoft Store) 。 若要从使用 Azure AD 帐户更改为登录到设备的 Microsoft 帐户，必须 [刷新设备](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (第一代)** 开始支持 [Windows 10 2018 年4月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 的多个 Azure AD 用户作为 [windows 全息版企业](hololens-upgrade-enterprise.md)的一部分。

## <a name="removing-users"></a>删除用户

可以通过转到 "**设置**" "  >    >  **其他人**"，从设备中删除用户。 此操作还会通过从设备中删除该用户的所有应用数据来收回空间。  

## <a name="using-single-sign-on-within-an-app"></a>在应用中使用单一登录

作为应用开发人员，你可以通过使用 [Windows 帐户管理器 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)来利用 HoloLens 上的链接标识，就像在其他 Windows 设备上一样。 GitHub： [Web 帐户管理示例](https://go.microsoft.com/fwlink/p/?LinkId=620621)中提供了这些 api 的一些代码示例。

当应用请求身份验证令牌时，必须处理可能发生的任何帐户中断，如请求用户同意帐户信息、双因素身份验证等。

如果你的应用程序需要以前未链接的特定帐户类型，你的应用程序可以要求系统提示用户添加一个。 此请求触发 "帐户设置" 窗格以启动应用的模式子。 对于2D 应用程序，此窗口直接在应用的中心进行呈现。 对于 Unity 应用，此请求会短暂使用户退出全息应用以呈现子窗口。 有关自定义此窗格上的命令和操作的信息，请参阅 [WebAccountCommand 类](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>企业和其他身份验证

如果你的应用使用其他类型的身份验证，例如 NTLM、Basic 或 Kerberos，则可以使用 [Windows 凭据 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 来收集、处理和存储用户凭据。 收集这些凭据的用户体验非常类似于其他云驱动的帐户中断，并且在二维应用程序的基础上显示为子应用，或者只是暂时挂起 Unity 应用以显示 UI。

## <a name="deprecated-apis"></a>弃用的 API

针对 HoloLens 进行开发的一种方法不同于桌面开发，而不是完全支持 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 尽管在主帐户处于良好地位的情况下，API 返回令牌，但不会向用户显示任何用户界面，也无法正确验证帐户。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens (第一代) 是否支持 Windows Hello 企业版？

支持使用 PIN 登录) 的 Windows Hello 企业版 (支持 HoloLens (第一代) 。 在 HoloLens 上允许 Windows Hello 企业版 PIN 登录：

1. HoloLens 设备必须 [由 MDM 管理](hololens-enroll-mdm.md)。
1. 必须为设备启用 Windows Hello 企业版。  ([查看 Microsoft Intune 的说明。](https://docs.microsoft.com/intune/windows-hello)) 
1. 在 HoloLens 上，用户可以使用 "**设置**  >  **" "登录选项" "**  >  **添加 pin** " 来设置 pin。

> [!NOTE]
> 使用 Microsoft 帐户登录的用户还可以在 "**设置**" "  >  **登录选项**" "  >  **添加 pin**" 中设置 pin。 此 PIN 与 [Windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)关联，而不是 [Windows hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>在 HoloLens 2 上如何实现 Iris 生物识别身份验证？

HoloLens 2 支持 Iris authentication。 Iris 基于 Windows Hello 技术，并支持 Azure Active Directory 和 Microsoft 帐户一起使用。 Iris 的实现方式与其他 Windows Hello 技术相同，实现生物识别安全性远远为 1/10 万。

有关详细信息，请参阅 [Windows Hello 的生物识别要求和规范](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 。 了解有关 [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 和 [Windows hello 企业版的](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)详细信息。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>帐户类型如何影响登录行为？

如果应用登录策略，则会始终遵循该策略。 如果没有应用登录策略，则每个帐户类型的默认行为如下：

- **Azure AD**：默认情况下要求身份验证，并且由 **设置** 配置为不再要求身份验证。
- **Microsoft 帐户**：锁定行为与允许自动解锁有所不同，但重新启动时仍然需要登录身份验证。
- **本地帐户**：始终以密码形式请求身份验证，在 "**设置**" 中不可配置

> [!NOTE]
> 当前不支持非活动计时器，这意味着仅当设备进入待机状态时才考虑 **AllowIdleReturnWithoutPassword** 策略。

## <a name="additional-resources"></a>其他资源

有关详细信息，请参阅 [Windows 10 安全和标识文档中的](https://docs.microsoft.com/windows/security/identity-protection/)用户标识保护和身份验证。

详细了解如何设置混合标识基础结构全面了解 [Azure 混合标识文档](https://docs.microsoft.com/azure/active-directory/hybrid/)。
