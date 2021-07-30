---
title: 管理 HoloLens 的用户标识和登录
description: 了解如何管理设备的用户标识、多用户支持、安全性、企业身份验证HoloLens登录。
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
ms.openlocfilehash: e2c5c98eb62f9e8ec19306b2cb460004eb8ae8dd
ms.sourcegitcommit: 44d5fbee8aa0e2404137484edbeb4653437e79dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2021
ms.locfileid: "114991417"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是 IT 专业人员和技术专家的技术参考。 如果要查找设置HoloLens，请阅读"设置 HoloLens (第[1 代) "](hololens1-start.md)或"设置[HoloLens 2"。](hololens2-start.md)

与其他Windows一样，HoloLens始终在用户上下文中运行。 始终存在用户标识。 HoloLens以与其他设备几乎相同的方式Windows标识。 本文深入探讨有关设备标识HoloLens，并重点介绍HoloLens设备与其他Windows的区别。

HoloLens支持多种用户标识。 可以使用一个或多个用户帐户登录。 下面概述了以下项上的标识类型和身份验证HoloLens：

| 标识类型 | 每个设备的帐户数 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure Web 凭据提供程序</li><li>Azure Authenticator 应用</li><li>生物 (Iris) HoloLens 2 &ndash; <sup>2</sup> </li><li>FIDO2 安全密钥</li><li>PIN &ndash; 可选HoloLens (第一代) ，是第一代HoloLens 2</li><li>Password</li></ul> |
| [Microsoft 帐户 (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>仅 () HoloLens 2 &ndash; 生物识别</li><li>PIN &ndash; 可选HoloLens (第一代) ，是第一代HoloLens 2</li><li>Password</li></ul> |
| [本地帐户](/windows/security/identity-protection/access-control/local-accounts) | 1 | Password |

云连接帐户 (Azure AD MSA) 提供了更多功能，因为它们可以使用 Azure 服务。  
> [!IMPORTANT]
> 1 - Azure AD Premium登录设备时不需要密码。 但是，对于基于云的低接触部署的其他功能（如自动注册和 Autopilot）需要它。

> [!NOTE]
> 2 - 尽管HoloLens 2设备最多支持 64 Azure AD帐户，但其中只有 31 个帐户可以注册 Iris 身份验证。 这与其他适用于企业应用[的安全Windows Hello身份验证选项保持一致](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)。

## <a name="setting-up-users"></a>设置用户

有两种方法可以设置新用户HoloLens。 最常见的方法是在 OOBE HoloLens中提供 (体验) 。 如果使用 Azure Active Directory，[则其他用户可以在](#setting-up-multi-user-support-azure-ad-only)OOBE 之后使用其凭据Azure AD登录。 HoloLens OOBE 期间最初使用 MSA 或本地帐户设置的设备不支持多个用户。 请参阅设置第[](hololens2-start.md)[一代HoloLens (或) HoloLens 2。](hololens1-start.md)

如果使用企业或组织帐户登录到 HoloLens，HoloLens组织的 IT 基础结构中注册。 此注册允许 IT 管理员配置 Mobile 设备管理 (MDM) 将组策略发送到HoloLens。

与其他Windows一样，在安装过程中登录会创建一个用户配置文件。 用户配置文件存储应用和数据。 同一帐户还通过使用 Windows 帐户管理器 API 为应用（例如 Edge 或 Microsoft Store）提供单一登录。 

默认情况下，与其他Windows 10一样，当设备重启或从备用HoloLens时，必须再次登录。 可以使用 设置 应用来更改此行为，也可以由组策略控制该行为。

### <a name="linked-accounts"></a>关联的帐户

与桌面版 Windows一样，可以将其他 Web 帐户凭据链接到HoloLens帐户。 通过此类链接，可以更轻松地跨应用或内部访问 (例如 Store) 或合并对个人和工作资源的访问。 将帐户连接到设备后，可以授予将设备用于应用的权限，以便不必单独登录到每个应用。

链接帐户不会将设备上创建的用户数据（例如映像或下载）分开。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>仅设置多用户 (Azure AD支持) 

HoloLens支持来自同一租户的多个Azure AD用户。 若要使用此功能，必须使用属于组织的帐户来设置设备。 随后，来自同一租户的其他用户可以从登录屏幕或点击"开始"面板上的用户磁贴登录到设备。 一次只能有一个用户登录。 当用户登录时，HoloLens上一个用户。 

>[!IMPORTANT]
> 设备上的第一个用户被视为设备所有者，但对于"加入Azure AD， [请详细了解设备所有者](security-adminless-os.md#device-owner)。

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用会删除所有用户的应用。  

使用 microsoft 帐户Azure AD设备不允许使用 Microsoft 帐户登录设备。 使用的所有后续帐户都必须Azure AD设备同一租户中的帐户。 你仍[可以使用 Microsoft 帐户](hololens-identity.md#setting-up-multi-user-support-azure-ad-only)登录到支持该帐户的应用 (例如Microsoft Store) 。 若要从使用Azure AD帐户更改为使用 Microsoft 帐户登录设备，必须 [重新将设备更改为](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (** [2018) 2018](/windows/mixed-reality/release-notes-april-2018)年 4 月更新Azure AD Windows 10中开始支持多个 Windows Holographic for Business [用户。](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出的多个用户

以前，"登录"屏幕只显示最近登录的用户，以及"其他用户"入口点。 我们已收到客户反馈，如果多个用户已登录到设备，这是不够的。 他们仍然需要重新键入其用户名等。

在[Windows Holographic 版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)中引入，在选择"PIN 输入"字段右侧"其他用户"时，"登录"屏幕将显示以前已登录到设备的多个用户。 这允许用户选择其用户配置文件，然后使用其凭据Windows Hello登录。 还可通过"添加帐户"按钮从此"其他用户"页将新 **用户添加到** 设备。

在"其他用户"菜单中，"其他用户"按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的"登录"屏幕。

![默认登录屏幕](./images/multiusers1.jpg)

<br>

![其他用户的登录屏幕](./images/multiusers2.jpg)

## <a name="removing-users"></a>删除用户

可以通过访问"帐户""其他人"设置  >    >  **从设备中删除用户**。 此操作还会通过从设备中删除该用户的所有应用数据来回收空间。  

## <a name="using-single-sign-on-within-an-app"></a>在应用中使用单一登录

应用开发人员可以使用[Windows HoloLens 帐户](/uwp/api/Windows.Security.Authentication.Web.Core)管理器 API 利用 HoloLens 上的链接标识，就像在其他 Windows 设备上一样。 有关这些 API 的一些代码示例，GitHub [Web 帐户管理示例 。](https://go.microsoft.com/fwlink/p/?LinkId=620621)

当应用请求身份验证令牌时，必须处理可能会发生的任何帐户中断，例如请求用户同意帐户信息、双重身份验证等。

如果应用需要之前未链接的特定帐户类型，则应用可以要求系统提示用户添加一个帐户类型。 此请求触发帐户设置窗格，以作为应用的模式子级启动。 对于 2D 应用，此窗口直接在应用中心呈现。 对于 Unity 应用，此请求会暂时将用户从全息应用退出，以呈现子窗口。 有关自定义此窗格上的命令和操作的信息，请参阅 [WebAccountCommand 类](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>Enterprise身份验证和其他身份验证

如果应用使用其他类型的身份验证（例如 NTLM、Basic 或 Kerberos），可以使用 Windows[凭据 UI](/uwp/api/Windows.Security.Credentials.UI)收集、处理和存储用户的凭据。 收集这些凭据的用户体验与其他云驱动帐户中断非常相似，并显示为 2D 应用顶部的子应用，或短暂挂起 Unity 应用以显示 UI。

## <a name="deprecated-apis"></a>弃用的 API

针对桌面进行开发HoloLens的一个区别是[，OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API 未完全受支持。 尽管 API 在主帐户正常运行时返回令牌，但本文中所述的中断不会为用户显示任何 UI，并且无法正确验证帐户。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>是否 Windows Hello HoloLens (第一代) 支持的业务？

HoloLens (第一代) 支持使用 PIN 登录) Windows Hello 适用于业务 (。 若要允许 Windows Hello 在 HoloLens 上进行业务 PIN 登录：

1. HoloLens 设备必须[由 MDM 管理](hololens-enroll-mdm.md)。
1. 必须为设备启用 Windows Hello for Business。  ([查看 Microsoft Intune 的说明。](/intune/windows-hello)) 
1. 在 HoloLens 上，用户可以使用 **设置**  >  **登录选项**"  >  **添加 pin** " 来设置 pin。

> [!NOTE]
> 使用 Microsoft 帐户登录的用户还可以在 **设置**  >  **登录选项**"  >  **添加 pin**" 中设置 pin。 此 PIN 与[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相关联，而不是[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview)。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>如何在 HoloLens 2 上实施 Iris 生物识别身份验证？

HoloLens 2 支持 Iris authentication。 Iris 基于 Windows Hello 技术，并支持 Azure Active Directory 和 Microsoft 帐户一起使用。 Iris 的实现方式与其他 Windows Hello 技术相同，并实现[生物识别安全性远远为 1/10 万](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)。

有关详细信息，请参阅[生物识别要求和 Windows Hello 规范](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)。 详细了解[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)和[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### <a name="where-is-iris-biometric-information-stored"></a>Iris 生物识别信息存储在何处？

Iris 生物识别信息按[Windows Hello 规范](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored)HoloLens 本地存储在每个上。 它不是共享的，受两个加密层保护。 其他用户（甚至是管理员）无法访问它，因为 HoloLens 上没有管理员帐户。

### <a name="do-i-have-to-use-iris-authentication"></a>我是否必须使用 Iris authentication？
不可以，你可以在安装过程中跳过此步骤。 

![设置 Iris](./images/setup-iris.png)

HoloLens 2 提供了许多不同的身份验证选项，包括 FIDO2 安全密钥。

### <a name="can-iris-information-be-removed-from-the-hololens"></a>是否可以从 HoloLens 中删除 Iris 信息？
是的，你可以在设置中手动删除它。


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>帐户类型如何影响登录行为？

如果应用登录策略，则会始终遵循该策略。 如果没有应用登录策略，则每个帐户类型的默认行为如下：

- **Azure AD**：默认情况下请求身份验证，**设置** 可配置为不再要求身份验证。
- **Microsoft 帐户**：锁定行为与允许自动解锁有所不同，但重新启动时仍然需要登录身份验证。
- **本地帐户**：始终以密码形式请求身份验证，在 **设置** 中不可配置

> [!NOTE]
> 当前不支持非活动计时器，这意味着仅当设备进入待机状态时才考虑 **AllowIdleReturnWithoutPassword** 策略。

## <a name="additional-resources"></a>其他资源

有关用户标识保护和身份验证的详细信息，请阅读[Windows 10 安全和身份验证文档](/windows/security/identity-protection/)。

详细了解如何设置混合标识基础结构全面了解 [Azure 混合标识文档](/azure/active-directory/hybrid/)。
