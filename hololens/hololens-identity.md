---
title: 管理 HoloLens 的用户标识和登录
description: 管理 HoloLens 的用户标识、安全和登录。
keywords: HoloLens， user， account， aad， adfs， microsoft account， msa， 凭据， 参考
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
ms.openlocfilehash: 17d55d8cd5540c9beaf4b7348688c362b079f5da
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955444"
---
# 管理 HoloLens 的用户标识和登录

> [!NOTE]
> 本文是 IT 专业人员和技术人本的技术参考。 如果要查找 HoloLens 设置说明，请阅读"[设置 HoloLens (1st 生成) "](hololens1-start.md)或"设置[HoloLens 2"。](hololens2-start.md)

与其他 Windows 设备类似，HoloLens 始终在用户上下文下运行。 始终有一个用户标识。 HoloLens 在几乎与其他 Windows 10 设备相同的方式对身份进行处理。 本文是 HoloLens 上的标识的深入参考，并重点介绍 HoloLens 与其他 Windows 10 设备有什么不同。

HoloLens 支持多种类型的用户身份。 可以使用一个或多个用户帐户登录。 下面是 HoloLens 上的标识类型和身份验证选项概述：

| 标识类型 | 每个设备的帐户数量 | 身份验证选项 |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure Web 凭据提供程序</li><li>Azure 验证器应用</li><li>生物识 () 仅 &ndash; 适用于 HoloLens 2</li><li>&ndash;HoloLens 的可选 (可选 1) ，HoloLens 2 要求</li><li>密码</li></ul> |
| [Microsoft 帐户 (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生物识 () 仅 &ndash; 适用于 HoloLens 2</li><li>&ndash;HoloLens 的可选 (可选 1) ，HoloLens 2 要求</li><li>密码</li></ul> |
| [本地帐户](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 密码 |

连接了 AAD 和 MSA 应用 (提供更多) 功能，因为它们可以使用 Azure 服务。  

## 设置用户

设置新用户的最常见方法是在 HoloLens 外出体验期间 (OOBE) 。 在设置过程中，HoloLens 将提示用户使用他们想要在设备上使用的帐户登录。 此帐户可以是消费者的 Microsoft 帐户，也可以是已在 Azure 中配置的企业帐户。 请参阅设置[HoloLens (第一代、) ](hololens1-start.md) [HoloLens 2。](hololens2-start.md)

与其他设备上的 Windows 类似，在设置过程中登录将在设备上创建用户配置文件。 用户配置文件存储应用和数据。 相同帐户还使用 Windows 帐户管理器 API 为应用（如 Edge 或 Skype）提供单一登录。  

如果你使用企业或组织帐户登录 HoloLens，HoloLens 将会注册组织的 IT 基础结构。 通过此注册，你的 IT 管理员可以为你的 HoloLens (时管理移动设备管理功能) ，以向你的 HoloLens 发送组策略。

默认情况下，与其他 Windows 10 设备一样，当 HoloLens 重启或从机机状态恢复时必须重新登录。 你可以使用"设置"应用更改此行为，也可通过组策略控制该行为。

### 链接的帐户

在 Windows 桌面版中，你可以将其他 Web 帐户凭据链接到你的 HoloLens 帐户。 此类链接使你能够更轻松地在 (事件之间或在应用 (资源（如应用商店）内) 访问个人和工作资源。 将某个帐户连接到该设备后，您可以授予使用设备的权限，从而无需单独登录到每个应用。

链接帐户不会分隔设备上创建的用户数据，如图像或下载。  

### 仅设置多用户支持将 (AAD) 

HoloLens 支持同一 AAD 租户中的多个用户。 若要使用此功能，你必须使用属于组织的帐户来设置设备。 随后，来自同一租户的其他用户可以从登录屏幕或通过单击"开始"面板上的用户磁贴登录到设备。 一次只能登录一个用户。 用户登录时，HoloLens 注销上一个用户。  

所有用户都可以使用设备上安装的应用。 但是，每个用户都有自己的应用数据和首选项。 从设备中删除应用会为所有用户删除该应用。  

使用 AAD 帐户设置的设备将不允许使用 Microsoft 帐户登录设备。 使用的所有后续帐户必须是来自与设备相同的租户的 AAD 帐户。 你可能仍 [可使用 Microsoft 帐户登录到在](hololens-identity.md#setting-up-multi-user-support-aad-only) Microsoft Store 开发 (Microsoft Store 开发人员) 。 若要从使用 AAD 帐户更改为登录设备，你 [必须刷新设备](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (1st 游戏) ** Windows 10 大会在 [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 年 4 月更新中作为 [Windows Holographic for Business 的一般用户开始](hololens-upgrade-enterprise.md)更新。

## 删除用户

您可以通过转到"设置帐户"或"其他人"**从**  >  **设备**  >  **中删除用户**。 此操作还通过从设备中删除该用户的所有应用数据来回收空间。  

## 在应用中使用单一登录

作为应用开发人员，你可以利用 Windows 帐户管理器 API 利用在 HoloLens 上链接的 [身](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)份，就像在其他 Windows 设备上一样。 GitHub 上提供这些 API 的某些代码示例 [：Web 帐户管理示例](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

任何可能发生的帐户中断（例如请求用户同意帐户信息、双因素身份验证等）必须在应用请求身份验证令牌时进行处理。

如果你的应用需要以前未链接的特定帐户类型，你的应用可以请求系统提示用户添加一个。 此请求会触发帐户设置窗格，以作为应用的模式子元素启动。 对于 2D 应用，该窗口将在应用中心直接呈现。 对于 Unity 应用，这请求将使用户从你的全息应用中一次后面呈现子窗口。 有关自定义此窗格上的命令和操作的信息，请参阅 [WebAccountCommand 类](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## 企业和其他身份验证

如果你的应用使用其他类型的身份验证（例如 NTLM、Basic 或 Kerberos），你可以使用 [Windows 凭据 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 来收集、处理和存储用户凭据。 收集这些凭据的用户体验与其他云驱动的帐户中断非常相似，且在你的 2D 应用的顶部显示为子应用或暂停某个 Unity 应用来显示 UI。

## 弃用的 API

为 HoloLens 进行开发的一种方法是 [：不完全支持 OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 尽管此 API 在主要帐户处于良好状态时返回令牌，但中断（如本文所述的那些 UI）不会显示任何用户的 UI 且未能正确对帐户进行身份验证。

## 常见问题

### HoloLens 上是否支持使用 Windows Hello for Business (一代) ？

HoloLens (支持使用 PIN 登录) Windows Hello for Business 用户 (1st) 。 允许在 HoloLens 上登录 Windows Hello for Business PIN 登录：

1. 必须由 [MDM 管理](hololens-enroll-mdm.md)HoloLens 设备。
1. 你必须为设备启用 Windows Hello for Business。  ([请参阅 Microsoft Intune 的](https://docs.microsoft.com/intune/windows-hello) 说明) 
1. 在 HoloLens 上，用户可以使用 **"**  >  **设置登录**选项  >  **添加 PIN"** 设置 PIN 来设置 PIN。

> [!NOTE]
> 使用 Microsoft 帐户登录的用户也可以在"设置登录选项添加**Settings**  >  **PIN"中设置**  >  **PIN。** 此 PIN 与[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)关联，而不是[Windows Hello for Business。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### 如何在 HoloLens 2 上实现 Iris 生物识别身份验证？

HoloLens 2 支持 Iris 身份验证。 Iris 基于 Windows Hello 技术，支持同时使用 Azure Active Directory 和 Microsoft 帐户。 Iris 的实现方式与其他 Windows Hello 技术的实现方式相同，并可实现生物识别安全性，1/100K。

可以在此处了解有关 Windows Hello 的生物识别要求和 [规范的详细信息](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)。 了解有关 [Windows Hello 和](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) [Windows Hello for Business 的详细信息](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### 帐户类型如何影响登录行为？

如果应用登录策略，则会始终遵循该策略。 如果不应用登录策略，则以下是每个帐户类型的默认行为：

- **Azure AD：** 默认请求身份验证，设置完成，无法再请求身份验证。 **Settings**
- **Microsoft 帐户**：有关锁定操作不同，可以自动解锁，但重新启动时仍需要登录身份验证。
- **本地帐户**：始终以密码形式要求身份验证，而不是在"设置"中 **进行配置**

> [!NOTE]
> 当前不支持非活动计时器，这意味着 **AllowIdleReturnWithoutPassword** 策略仅在设备进入 StandBy 时应被检查。

## 其他资源

阅读有关 Windows 10 安全和标识文档上的用户身份保护 [和身份验证的详细信息](https://docs.microsoft.com/windows/security/identity-protection/)。

了解有关设置混合身份基础结构的详细信息，尽管 [Azure 混合身份文档](https://docs.microsoft.com/azure/active-directory/hybrid/)。
