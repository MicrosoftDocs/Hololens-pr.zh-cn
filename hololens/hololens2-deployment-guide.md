---
title: 部署指南
description: 'HoloLens 2 (远程辅助的部署指南作为示例) '
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/7/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 0cd75fdbe5f6a4e6da87770768ce9f22bce491c0
ms.sourcegitcommit: 58bffba63ed581351d80d13b1437aca74d7ed64a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "11266359"
---
# 使用远程协助将 HoloLens 2 部署到外部客户端

本文档可帮助 IT 专业人员规划并部署 HoloLens 2 设备，侧重于远程协助。 [了解有关远程协助的更多信息](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

## 方案说明

出于本文档的目的，Contoso 公司希望将 HoloLens 2 设备发运给外部客户端的工厂，以便短期或长期使用。 当客户端需要协助服务时，客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用远程协助联系 Contoso 公司专家。

### 此方案的要求

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. 移动设备管理器 - 例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist 许可证
    1. [购买远程协助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [试用远程协助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## 常见问题

- [如何确保外部客户端无法相互通信](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何确保客户端无法访问公司资源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制应用](#how-to-restrict-apps)
- [如何管理密码](#how-to-manage-passwords)
- [如何确保客户端无法访问聊天历史记录](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### 如何确保外部客户端无法相互通信

由于不支持远程协助 HoloLens 到 HoloLens 的呼叫，因此客户端可以搜索但无法相互通信。 为了进一步限制可以搜索和呼叫的客户端[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)，信息屏障可以限制客户端可以与谁通信。 要考虑的另一个选项是使用 [作用域目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 由于启用了单一登录，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。 如果外部客户端打开浏览器并使用 Web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。

### 如何确保客户端无法访问公司资源

有两个选项需要考虑。

第一个选项是多层方法：

1. 仅分配用户所需的许可证。 如果未将 OneDrive、Outlook、SharePoint、Yammer 等分配给用户，则他/她将无法访问这些资源。 用户需要的唯一许可证是远程协助、Intune 和 AAD 许可证才能开始。
1. 阻止 (应用程序，) 您不希望客户端访问的电子邮件 (请参阅如何限制 [应用程序](#how-to-restrict-apps)) 。
1. 不要与客户端共享用户名或密码。 若要登录到 HoloLens 2，需要电子邮件和数字 PIN。

第二个选项是创建托管客户端的单独租户 (图像 1.1) 。

**图像 1.1**

![服务租户映像](./images/hololens-service-tenant-image.png)

### 如何限制应用

[展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender应用程序 ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)) 限制应用程序的选项。

### 如何管理密码

1. 删除密码过期。 但是，这会增加帐户遭到入侵的可能性。 NIST 密码建议是每 30-90 天更改一次密码。
1. 将 HoloLens 2 设备的密码过期时间延长 90 天。
1. 设备应返回到 Contoso 以更改密码。 但是，如果设备预期在客户端中工作 90 天以上，这可能会导致问题。  
1. 对于发送到多个客户端的设备，在将设备寄送到客户端之前重置密码。

### 如何确保客户端无法访问聊天历史记录

远程协助在每个会话后清除聊天历史记录。 但是，聊天历史记录将提供给 Microsoft Teams 用户。

> [!NOTE]
> 由于启用了单一登录，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。 如果外部客户端打开浏览器并使用 Web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。

## 一般部署建议和说明

我们建议对 HoloLens 2 部署步骤执行以下操作：

1. 使用 [最新的 HoloLens 操作系统版本](https://aka.ms/hololens2download) 作为基准版本。
1. 分配基于用户或基于设备的许可证：
    1. 基于用户的许可证和基于设备的许可证都遵循以下步骤：
        1. [在 AAD 中创建组，并添加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 用户的成员。
        1. [向此组分配基于设备或基于](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 用户的许可证。
        1.  (可选) 你可以面向 MDM 策略的组。

1. 设备应已加入租户的 AAD，自动 [注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过自动引导 [进行配置](https://docs.microsoft.com/hololens/hololens2-autopilot)。
    1. 请注意，设备上第一个用户将是设备所有者。
    1. 请注意，如果设备已加入 AAD，则执行加入的用户将成为设备所有者。
    1. 有关详细信息，请参阅 [设备所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。
1. [租户锁定](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。
    1. **其他链接：**[租户锁定 CSP。](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. 使用全局分配的访问权限在此处配置 [展台](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。
1. 我们建议禁用以下可选 () 功能：
    1. 在此处将设备置于开发人员模式 [的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 将 HoloLens 连接到电脑以复制日期的能力禁用[USB。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > 如果你不想禁用 USB，但希望能够使用 USB 将预配包应用到设备，请按照此处列出的 [**说明操作**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. 使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 允许或黑色 HoloLens 2 设备上应用。
1. 将远程协助更新到最新版本，作为设置的一部分。 有两个选项可进行此操作：
    1. 这可以通过访问 Windows Microsoft **Store --> Remote Assist --> 应用完成**。
    1. 另一个方法是让 HoloLens 2 在一夜之间保持插入状态以自动更新。
1. [禁用除网络](https://docs.microsoft.com/hololens/settings-uri-list) 设置以外的所有设置页面，以允许用户连接到客户端站点中的来宾网络。
1. [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)
    1. 控制 [操作系统更新或](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允许自由流动的选项。
1. [常见设备限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
