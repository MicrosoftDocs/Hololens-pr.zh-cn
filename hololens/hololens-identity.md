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
ms.openlocfilehash: f8dcc8619715871db0aaba306dd19d252d73ac47
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397828"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是 IT 专业人员和技术专家的技术参考。 如果要查找 HoloLens 设置说明，请阅读"设置[HoloLens ](hololens1-start.md) (第一代) "或"设置[HoloLens 2"。](hololens2-start.md)

与其他 Windows 设备一样，HoloLens 始终在用户上下文中运行。 始终存在用户标识。 HoloLens 以与其他设备几乎相同的方式Windows 10标识。 本文深入介绍了 HoloLens 上的标识，重点介绍 HoloLens 与其他设备Windows 10差异。

HoloLens 支持多种用户标识。 可以使用一个或多个用户帐户登录。 下面概述了 HoloLens 上的标识类型和身份验证选项：

| 标识类型 | 每个设备的帐户数 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory (](https://docs.microsoft.com/azure/active-directory/) 需要Azure AD Premium)  | 64 | <ul><li>Azure Web 凭据提供程序</li><li>Azure Authenticator 应用</li><li>生物 (Iris) HoloLens 2 &ndash; <sup>1</sup> </li><li>适用于 &ndash; HoloLens (第一代) 的 PIN 可选，HoloLens 2</li><li>密码</li></ul> |
| [Microsoft 帐户 (MSA) ](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生物识别 (Iris) &ndash; 仅 HoloLens 2</li><li>为 hololens &ndash; (第一代) 固定可选，为 hololens 2 所需</li><li>密码</li></ul> |
| [本地帐户](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 密码 |

与云连接的帐户 (Azure AD 和 MSA) 提供更多功能，因为它们可以使用 Azure 服务。  

> [!NOTE]
> 1-虽然 HoloLens 2 设备最多可以支持 64 Azure AD 帐户，但只有10个帐户才能注册 Iris Authentication。 这与 [适用于 Windows Hello 企业版的其他生物识别身份验证选项](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)一致。

## <a name="setting-up-users"></a>设置用户

设置新用户的最常见方法是在 (OOBE) 的 HoloLens 全新体验。 在安装过程中，HoloLens 会提示用户使用他们要在设备上使用的帐户登录。 此帐户可以是使用者 Microsoft 帐户或已在 Azure 中配置的企业帐户。 请参阅设置 [hololens (第一代) ](hololens1-start.md) 或 [HoloLens 2](hololens2-start.md)。

与其他设备上的 Windows 一样，在安装过程中登录会在设备上创建用户配置文件。 用户配置文件存储应用程序和数据。 同一帐户还通过使用 Windows 帐户管理器 Api 为应用（如 Edge 或 Skype）提供单一登录。  

如果使用企业帐户或组织帐户登录到 HoloLens，则 HoloLens 会在组织的 IT 基础结构中注册。 此注册可让你的 IT 管理员配置移动设备管理 (MDM) 将组策略发送到 HoloLens。

默认情况下，对于其他 Windows 10 设备，你必须在 HoloLens 重新启动或从待机状态恢复时再次登录。 您可以使用 "设置" 应用程序来更改此行为，也可以通过组策略控制该行为。

### <a name="linked-accounts"></a>关联的帐户

与 Windows 的桌面版本一样，你可以将其他 web 帐户凭据链接到你的 HoloLens 帐户。 此类链接使你可以更轻松地跨应用程序或应用程序内访问资源 (例如存储) 或合并对个人资源和工作资源的访问。 将帐户连接到设备后，可以授予将设备用于应用的权限，以便不必单独登录到每个应用。

链接帐户不会将设备上创建的用户数据（例如映像或下载）分开。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>仅设置多用户 (Azure AD支持) 

HoloLens 支持来自同一租户的多个Azure AD用户。 若要使用此功能，必须使用属于组织的帐户来设置设备。 随后，来自同一租户的其他用户可以从登录屏幕或点击"开始"面板上的用户磁贴登录到设备。 一次只能有一个用户登录。 用户登录时，HoloLens 会向上一个用户进行登录。 设备上的第一个用户被视为设备所有者，但对于"加入Azure AD， [请详细了解设备所有者](security-adminless-os.md#device-owner)。

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用会删除所有用户的应用。  

使用 microsoft 帐户Azure AD设备不允许使用 Microsoft 帐户登录设备。 使用的所有后续帐户都必须Azure AD设备同一租户中的帐户。 你仍 [可以使用 Microsoft 帐户登录到](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 支持该帐户的应用 (例如 Microsoft Store) 。 若要从使用Azure AD帐户更改为使用 Microsoft 帐户登录设备，必须 [重新将设备更改为](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (** 第一代) 开始支持 Azure AD Windows 10 2018 年 4 月更新 中的多个 Windows Holographic for Business [用户。](hololens-upgrade-enterprise.md) [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出的多个用户

以前，"登录"屏幕只显示最近登录的用户，以及"其他用户"入口点。 我们已收到客户反馈，如果多个用户已登录到设备，这是不够的。 它们仍需要重新键入其用户名等。

[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1)中引入的其他用户，选择位于 "PIN 输入" 字段右侧的 **其他用户** 时，"登录" 屏幕将显示多个以前登录到设备的用户。 这允许用户选择其用户配置文件，然后使用他们的 Windows Hello 凭据进行登录。 还可以通过 " **添加帐户** " 按钮将新用户添加到该设备。

在 "其他用户" 菜单中，"其他用户" 按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的登录屏幕。

![登录屏幕默认值](./images/multiusers1.jpg)

<br>

![其他用户登录屏幕](./images/multiusers2.jpg)

## <a name="removing-users"></a>删除用户

可以通过转到 "**设置**" "  >    >  **其他人**"，从设备中删除用户。 此操作还会通过从设备中删除该用户的所有应用数据来收回空间。  

## <a name="using-single-sign-on-within-an-app"></a>在应用中使用单一登录

作为应用开发人员，你可以通过使用 [Windows 帐户管理器 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)来利用 HoloLens 上的链接标识，就像在其他 Windows 设备上一样。 GitHub： [Web 帐户管理示例](https://go.microsoft.com/fwlink/p/?LinkId=620621)中提供了这些 api 的一些代码示例。

当应用请求身份验证令牌时，必须处理可能发生的任何帐户中断，如请求用户同意帐户信息、双因素身份验证等。

如果你的应用程序需要以前未链接的特定帐户类型，你的应用程序可以要求系统提示用户添加一个。 此请求触发 "帐户设置" 窗格以启动应用的模式子。 对于2D 应用程序，此窗口直接在应用的中心进行呈现。 对于 Unity 应用，此请求会短暂使用户退出全息应用以呈现子窗口。 有关自定义此窗格上的命令和操作的信息，请参阅 [WebAccountCommand 类](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>企业和其他身份验证

如果应用使用其他类型的身份验证（如 NTLM、Basic 或 Kerberos），可以使用 Windows [凭据 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 收集、处理和存储用户的凭据。 收集这些凭据的用户体验与其他云驱动帐户中断非常相似，并显示为 2D 应用顶部的子应用，或短暂挂起 Unity 应用以显示 UI。

## <a name="deprecated-apis"></a>弃用的 API

针对 HoloLens 进行开发不同于针对桌面进行开发的方法之一是 [，OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API 不受完全支持。 尽管 API 在主帐户正常运行时返回令牌，但本文中所述的中断不会为用户显示任何 UI，并且无法正确验证帐户。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens Windows Hello 企业版第一代 (是否支持) ？

Windows Hello 企业版 (支持使用 PIN 登录) HoloLens (第一代) 。 若要Windows Hello 企业版 HoloLens 上登录 PIN：：

1. HoloLens 设备必须由 [MDM 管理](hololens-enroll-mdm.md)。
1. 必须为设备Windows Hello 企业版设备。  ([请参阅有关 Microsoft Intune) 的说明。](https://docs.microsoft.com/intune/windows-hello)
1. 然后，用户可以在 HoloLens 上使用"设置  >  **登录选项""**  >  **添加 PIN"** 来设置 PIN。

> [!NOTE]
> 使用登录帐户登录Microsoft 帐户还可以在"设置登录选项""添加  >  PIN"**中** 设置  >  **PIN。** 此 PIN 与[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相关联，而不是[Windows Hello 企业版。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Iris 生物识别身份验证如何HoloLens 2？

HoloLens 2 Iris 身份验证。 Iris 基于Windows Hello技术，并且支持由 Azure Active Directory 和 Microsoft 帐户使用。 Iris 的实现方式与其他技术Windows Hello相同，并实现 1/100K 生物识别安全。

有关详细信息 [，请参阅](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Windows Hello生物识别要求和规范。 了解有关 [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 和 [Windows hello 企业版的](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)详细信息。 

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
