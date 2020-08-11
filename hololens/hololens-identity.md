---
title: 管理 HoloLens 的用户标识和登录
description: 管理 HoloLens 的用户身份、安全和登录。
keywords: HoloLens、用户、帐户、aad、adfs、microsoft 帐户、msa、凭据、参考
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: 9829b90445be7f73cfdc0e330d9d57af1ef0a44b
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919113"
---
# 管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是面向 IT 专业人员和技术爱好者的技术参考。 如果您要查找 HoloLens 设置说明，请参阅 "[设置 hololens (第一代) ](hololens1-start.md)" 或 "[设置 hololens 2](hololens2-start.md)"。

与其他 Windows 设备一样，HoloLens 始终在用户上下文下运行。 始终存在用户标识。 HoloLens 处理身份的方式与其他 Windows 10 设备几乎完全相同。 本文是针对 HoloLens 的标识的深入参考，重点介绍 HoloLens 与其他 Windows 10 设备的不同之处。

HoloLens 支持几种类型的用户标识。 你可以使用一个或多个用户帐户登录。 下面概述了 HoloLens 上的身份类型和身份验证选项：

| 标识类型 | 每个设备的帐户 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure web 凭据提供程序</li><li>Azure 身份验证器应用</li><li>仅) HoloLens 2 的生物识别 (虹膜 &ndash;</li><li>Hololens &ndash; (第一代) （hololens）所需的可选针2</li><li>密码</li></ul> |
| [Microsoft 帐户 (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | raid-1 | <ul><li>仅) HoloLens 2 的生物识别 (虹膜 &ndash;</li><li>Hololens &ndash; (第一代) （hololens）所需的可选针2</li><li>密码</li></ul> |
| [本地帐户](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | raid-1 | 密码 |

与云连接的帐户 (AAD 和 MSA) 提供更多功能，因为它们可以使用 Azure 服务。  

## 设置用户

设置新用户的最常见方法是在 OOBE 全新体验 (OOBE) 。 在安装期间，HoloLens 将提示用户使用要在设备上使用的帐户登录。 此帐户可以是已在 Azure 中配置的消费者 Microsoft 帐户或企业帐户。 请参阅设置[hololens (第一代) ](hololens1-start.md)或[HoloLens 2](hololens2-start.md)。

与其他设备上的 Windows 一样，在安装过程中登录会在设备上创建用户配置文件。 用户配置文件存储应用和数据。 同一个帐户还通过使用 Windows 帐户管理器 Api 为应用（如 Edge 或 Skype）提供单一登录。  

如果您使用企业或组织帐户登录 HoloLens，则 HoloLens 将在组织的 IT 基础结构中注册。 此注册允许 IT 管理员配置移动设备管理 (MDM) 以向 HoloLens 发送组策略。

默认情况下，对于其他 Windows 10 设备，你将在 HoloLens 重新启动或从待机状态恢复时再次登录。 你可以使用 "设置" 应用更改此行为，或该行为可由组策略控制。

### 链接的帐户

在 Windows 桌面版本中，你可以将其他 web 帐户凭据链接到 HoloLens 帐户。 此类链接使你可以更轻松地跨应用或在应用内访问资源 (例如应用商店) 或将访问权限与个人资源和工时资源进行合并。 将帐户连接到设备后，你可以向应用授予使用设备的权限，以便你无需单独登录每个应用。

链接帐户不会将在设备上创建的用户数据（如图像或下载）分开。  

###  (仅限 AAD) 设置多用户支持

> [!NOTE]
> **HoloLens (第一代) **开始支持[windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)中的多个 AAD 用户，作为[windows 全息版企业](hololens-upgrade-enterprise.md)的一部分。

HoloLens 支持来自同一 AAD 租户的多个用户。 若要使用此功能，你必须使用属于你的组织的帐户来设置设备。 随后，来自同一租户的其他用户可以从登录屏幕登录到该设备，或者通过在 "开始" 面板上点击用户磁贴登录。 一次只能登录一个用户。 当用户登录时，HoloLens 将注销以前的用户。  

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用将为所有用户删除该应用。  

## 删除用户

你可以通过转到 " **Settings**  >  **Accounts**  >  **其他人**" 的 "设置" 帐户从设备中删除用户。 此操作还会通过从设备中删除所有用户的应用数据来回收空间。  

## 在应用内使用单一登录

作为应用开发人员，你可以使用[Windows 帐户管理器 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)利用 HoloLens 上链接的身份，就像在其他 Windows 设备上一样。 [此处](https://go.microsoft.com/fwlink/p/?LinkId=620621)提供了这些 api 的一些代码示例。

在应用请求身份验证令牌时，必须处理可能发生的任何帐户中断，例如请求用户同意帐户信息、双因素身份验证等。

如果你的应用需要以前尚未链接的特定帐户类型，你的应用可以要求系统提示用户添加一个帐户。 此请求触发 "帐户设置" 窗格，以应用的模式子元素的形式启动。 对于2D 应用，此窗口直接呈现在应用中心。 对于 Unity 应用，此请求会暂时使用户退出全息应用以呈现子窗口。 有关自定义此窗格中的命令和操作的信息，请参阅[WebAccountCommand 类](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## 企业和其他身份验证

如果你的应用使用其他类型的身份验证（如 NTLM、基本或 Kerberos），则可以使用[Windows 凭据 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI)收集、处理和存储用户的凭据。 收集这些凭据的用户体验非常类似于其他云驱动的帐户中断，并作为子应用显示在2D 应用上，或暂时挂起 Unity 应用以显示 UI。

## 弃用的 API

对 HoloLens 进行开发不同于桌面开发的一种方法是不完全支持[OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 尽管当主帐户处于良好的主帐户时，API 才会返回标记，但本文中所述的中断不会显示用户的任何 UI，也无法正确验证帐户。

## 常见问题

### 在 HoloLens (第一代) 上是否支持 Windows Hello 企业版？

对于 HoloLens (第一代) ，支持使用 PIN 登录) 的 Windows Hello 企业版 (。 若要在 HoloLens 上允许 Windows Hello 企业版 PIN 登录，请执行以下操作：

1. HoloLens 设备必须[由 MDM 托管](hololens-enroll-mdm.md)。
1. 必须为设备启用 Windows Hello 企业版。  ([查看 Microsoft Intune 的说明。](https://docs.microsoft.com/intune/windows-hello)) 
1. 在 HoloLens 中，用户可以使用 "**设置**  >  **" 登录选项 "**  >  **添加 pin** " 设置 pin。

> [!NOTE]
> 使用 Microsoft 帐户登录的用户也可以在 "**设置**"  >  **登录选项**"  >  **添加 pin**" 中设置 pin。 此 PIN 与[Windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相关联，而不是[Windows hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### 在 HoloLens 2 上如何实现虹膜生物识别身份验证？

HoloLens 2 支持虹膜身份验证。 虹膜基于 Windows Hello 技术，并且支持由 Azure Active Directory 和 Microsoft 帐户使用。 虹膜的实现方式与其他 Windows Hello 技术相同，并达到远达 1/10 万美元的生物识别安全。

你可以在[此处](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)了解有关适用于 Windows Hello 的生物识别要求和规范的详细信息。 了解有关[Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)和[Windows hello 企业版的](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)详细信息。 

### 帐户类型如何影响登录行为？

如果应用登录策略，则会始终遵循该策略。 如果没有应用用于登录的策略，则以下是每种帐户类型的默认行为：

- **AZURE AD**：默认情况下要求身份验证，并通过**设置**进行配置，以使其不再请求身份验证。
- **Microsoft 帐户**：锁定行为因允许自动解锁而有所不同，但重启时仍需要登录身份验证。
- **本地帐户**：始终以密码形式请求身份验证，在 "**设置**" 中不可配置

> [!NOTE]
> 当前不支持非活动计时器，这意味着仅当设备进入待机状态时，才会考虑**AllowIdleReturnWithoutPassword**策略。

## 其他资源

有关详细信息，请参阅[Windows 10 安全和标识文档中的](https://docs.microsoft.com/windows/security/identity-protection/)用户身份保护和身份验证。

深入了解有关设置混合身份基础结构的更多信息，请[参阅 Azure 混合标识文档](https://docs.microsoft.com/azure/active-directory/hybrid/)。
