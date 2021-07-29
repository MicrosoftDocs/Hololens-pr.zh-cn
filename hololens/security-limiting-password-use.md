---
title: 限制密码的使用
description: 限制 HoloLens 的密码使用
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，限制密码使用，密码，hololens 密码，登录，正在登录，windows hello，hello，windows 帐户管理器，FIDO2 登录，FIDO 2，WEBAUTHN，本地帐户，hololens 安全
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 074fffc8350dd6deb876a19320397674bcac3e46
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639295"
---
# <a name="limiting-password-use"></a>限制密码的使用

如今大多数计算机系统利用用户凭证作为安全的基础，使其依赖于可重用的、用户创建的密码。 这也导致密码成为账户和数据泄露的最常见原因。 例如，密码可以在传输过程中被截获或从服务器上被窃取（通过钓鱼或密码喷射攻击）并泄露以获得对用户帐户的访问权。

为提高安全性和帐户保护，HoloLens 2 能为设备登录启用强大的、硬件支持的“无密码”凭据（包括 Windows Hello），提供对 Microsoft 云的无缝访问。

## <a name="signing-in-from-another-device"></a>从另一台设备登录

HoloLens 2 在初始设备设置和用户登录期间为 Azure Active Directory 工作帐户提供远程设备登录选项，以减少键入复杂密码的需要，并将密码作为凭据的需要降至最低。 使用智能卡进行身份验证的用户和组织很难在 HoloLens 2 等设备上使用这些凭证，而且组织通常会开发复杂的系统和昂贵的流程来解决该问题。 为解决此问题，Azure AD 在 HoloLens 2 上提供了两个无密码登录选项。

第一种身份验证方法依赖于 Microsoft Authenticator 应用中的新功能，提供基于密钥的身份验证，可将用户凭据绑定到设备。 管理员在租户上启用后，在 HoloLens 设备安装期间将显示一条消息，告诉用户点击应用上的某个号码。 然后他们必须匹配验证器应用上的号码，选择“批准”，提供他们的个人识别码或完整的生物身份验证，才能继续安装 HoloLens。 [无密码登录](/azure/active-directory/authentication/howto-authentication-passwordless-phone)中对此有更详细的介绍。

第二种是设备代码流，它对用户来说很直观，不需要额外的基础设施。  此远程登录行为依赖于另一受信任的设备，该设备支持组织的首选身份验证机制，完成后，令牌被发送回 HoloLens 以完成登录或设备安装。 此流程中的步骤包括：

  1. 用户在 OOBE 上进行初始设备设置或登录流时，会看到“从其他设备登录”的链接并点击它。 这将启动远程登录会话。
  1. 然后显示一个带有 URI 的轮询页面 ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) ，它指向 Azure AD 安全令牌服务 (STS) 的设备身份验证终端。 用户还将看到一个在云中安全生成的一次性代码，最长生存期为 15 分钟。 生成代码的同时，Azure AD 还在上一步中启动远程登录请求时创建加密会话，并使用 URI 和代码批准远程登录请求。
  1. 然后用户从另一设备导航到 URI，系统会提示输入 HoloLens 2 设备上显示的代码。
  1. 用户输入代码后，Azure AD STS 将显示一个页面，指示用户触发远程登录请求的 HoloLens 2 设备，并请求生成代码。 然后系统会提示用户进行确认以防任何网络钓鱼攻击。
  1. 如果用户选择继续登录显示的应用，Azure AD STS 将提示用户输入凭据。 身份验证成功后，Azure AD STS 会将缓存的远程会话更新为“批准”，并给予授权代码。
  1. 最后，用户 HoloLens 2 设备上的轮询页面从 Azure AD 接收“授权”响应，并继续验证用户代码及其关联的存储授权代码，并根据请求生成 OAuth 令牌，以完成设备设置。 所创建的身份验证令牌的有效期为 1 小时，刷新令牌的生存期为 90 天。

此流中使用的代码生成和加密算法均符合美国联邦信息处理标准。 HoloLens 2 设备利用 TPM 保护设备密钥，并使用硬件保护密钥对用户身份验证后生成的令牌进行加密。 有关 HoloLens 2 上令牌安全性的详细信息，请参阅[什么是主刷新令牌 (PRT)](/azure/active-directory/devices/concept-primary-refresh-token)。

## <a name="device-sign-in-with-windows-hello"></a>使用 Windows Hello 登录设备

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 提供内置无密码选项，允许用户使用 Iris 或 PIN 登录设备。 PIN 作为凭证始终可用，是设备设安装所必需的，而 Iris 是可选的、可跳过的。 用户可以使用其个人 Microsoft 帐户或 [Azure Active Directory 工作帐户登录 HoloLens 设备，而无需输入密码](/azure/active-directory/authentication/concept-authentication-passwordless)。 这些选项为用户提供快速、安全丰富的 Windows 体验、应用、数据、网站和服务。 Microsoft 的无密码体验战略详情在此。

创建 Windows Hello 凭证后，它与标识提供者建立受信任的关系，并且创建用于身份验证的非对称密钥对。 Windows Hello 手势（如 iris 或 PIN）提供熵来解密由设备的受信任的平台模块 (TPM) 芯片支持的私钥。 然后，该私钥对对发送到身份验证服务器的请求进行签名，并在验证成功后，向用户授予对其邮件、图片和其他帐户设置的访问权限。

了解更多信息，请参阅以下信息图：

  ![Windows Hello 登录](images/security-hello-sign-in.png)
  
在上图中，注意 nonce 代表“number once”，是随机或半随机生成的数字。 设置 Windows Hello 生物或 PIN 凭据后，它永不会离开预配它的设备。 即使用户的 Windows Hello PIN 被盗（如通过网络钓鱼攻击），但[如果不使用用户的物理设备](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)，盗用 PIN 是无用的。

为提高安全性，Windows Hello 凭据由受信任的平台模块 (TPM) 保护，以防凭据被篡改，并辅以针对多次错误输入的防攻击保护，并提供防恶意软件保护以避免凭据泄露。 有关单一登录 (SSO) 的详细信息，请阅读此 [SSO 方法概述](/azure/active-directory/manage-apps/what-is-single-sign-on)。

Iris 身份验证回退到 PIN。 为了在设备上设置新 PIN（强身份验证），用户须最近已通过[多重身份验证 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) 才能完成此进程。

## <a name="single-sign-on-with-web-account-manager"></a>使用 Web 帐户管理器进行单一登录

单一登录 (SSO) 允许无密码用户使用用户的个人、工作或学校帐户登录设备。 用户将通过 [Web 帐户管理器 API](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true) 自动获得所有集成应用和服务的 SSO 授权。

通过一个应用程序添加了身份标识后，在用户同意的情况下，该标识可通过系统级集成用于所有应用程序和服务。 这显著降低应用程序的登录负担，并为用户提供无缝的标识体验。

有关实现 Web 帐户管理器 API 的详细信息，请参阅[实现 Web 帐户管理器 API](/windows/uwp/security/web-account-manager)。

  ![安全性 API](images/security-api-img.png)
  
对有特殊身份验证要求的应用程序套件，Web 帐户管理器 (WAM) 框架可扩展到自定义标识提供程序。 用户可从 Microsoft Store 下载打包为通用 Windows 平台 (UWP) 应用的自定义标识提供程序，以便在与该身份提供程序集成的其他应用上启用 SSO。

有关实现自定义 WAM 标识提供程序的详细信息，请参阅[自定义 WAM 标识提供程序 API 引用](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)。

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>使用 WebAuthn 登录 Windows Hello 和 FIDO2

HoloLens 2 可用无密码用户凭据（如 Windows Hello 或 FIDO2 安全参数），通过 Microsoft Edge 登录上网，以及登录到支持 WebAuthn 的网站。 FIDO2 允许用户凭证利用基于标准的设备进行联机服务身份验证。

> [!Note]
> 服务中实施了 [WebAuthn](https://www.w3.org/TR/webauthn/) 和 FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) 规范。 由 WebAuthn 和 FIDO2 指定的已签名元数据提供信息（如用户是否存在）并通过本地手势进行身份验证。

至于 Windows Hello，当用户创建并注册 FIDO2 凭据时，设备（HoloLens 2 或 FIDO2 安全参数）将在设备上生成私钥和公钥。 私钥安全地存储在设备上，并仅在使用生物特征或 PIN 等本地手势解锁后才能使用。 存储私钥后，公钥将被发送到云中的 Microsoft 帐户系统，并用相关的用户账户进行注册。

使用 MSA 和 Azure AD 帐户登录后，系统会向 HoloLens 2 或 FIDO2 设备发送生成的号码或数据变量。 HoloLens 2 或设备使用私钥为标识签名。 已签名的标识和元数据被发送回 Microsoft 帐户系统，并使用公钥进行验证。

Windows Hello 和 FIDO2 设备根据 HoloLens 设备，尤其是内置受信任的平台模块的安全区域，来实现凭据。 TPM 区域存储私钥，并需要生物特征或 PIN 才能解除锁定。 类似地，FIDO2 安全参数是一个具有内置安全区域的小型外部设备，用于存储私钥，并且需要生物特征或 PIN 来解锁。

这两个选项通过一个步骤提供双因素身份验证，需要注册设备和生物识别或 PIN 才能成功登录。 有关详细信息，请参阅使用 FIDO2 安全密钥进行强身份验证的图形和流程，如下所示。

### <a name="strong-authentication-with-fido2-security-key"></a>使用 FIDO2 安全密钥进行强身份验证

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. 用户将 FIDO2 安全密钥插入 HoloLens 2
1. Windows 检测 FIDO2 安全密钥
1. HoloLens 发送身份验证请求
1. Azure AD 发送回 nonce
1. 用户作出手势，以解锁安全密钥安全协处理器中的私钥存储库
1. FIDO2 安全密钥使用私钥对 nonce 进行签名
1. 含有签名 nonce 的 PRT 令牌请求被发送至 Azure AD
1. Azure AD 验证 FIDO 密钥
1. Azure AD 返回 PRT 和 TGT 以启用对资源的访问权限

MSA 和 Azure AD 是第一批通过实施 WebAuthn 支持无密码身份验证的信赖方。

有关将 WebAuthn 与应用程序和/或 SDK 一起使用的详细信息，请参阅[用于在 Windows 10 上进行无密码身份验证的 WebAuthn API](/windows/security/identity-protection/hello-for-business/webauthnapis)。

HoloLens 2 支持按照规范实现的且满足 [Azure Active Directory 无密码登录 - FIDO2 安全密钥](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)中列出的要求的 FIDO2 安全设备。

## <a name="local-accounts"></a>本地帐户

可为脱机模式部署配置一个本地帐户。 本地帐户在默认情况下为未启用状态，必须在设备预配时进行配置。 它们需要使用密码登录，且不支持备用身份验证方法（例如 [Windows Hello 企业版](/windows/security/identity-protection/hello-for-business/hello-overview) 或 [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)）。

有关 HoloLens 用户帐户的更多详细信息，请参阅 [HoloLens 标识](hololens-identity.md)。

IT 管理员通过 [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) 调整是否允许用户使用 MSA 帐户进行与电子邮件无关的连接身份验证和获取服务。 有关密码设置策略、空闲策略和锁屏策略，请参阅[设备锁定](/windows/client-management/mdm/policy-csp-devicelock)。
