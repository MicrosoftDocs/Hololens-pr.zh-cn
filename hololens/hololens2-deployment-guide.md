---
title: 外部客户端部署指南
description: '远程辅助HoloLens 2外部客户端 (部署指南作为示例) '
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636939"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>使用 HoloLens 2 部署到外部Remote Assist

本指南可帮助 IT 专业人员实现以下目标，Microsoft HoloLens 2 台设备部署：

1. 云HoloLens 2连接
1. 将HoloLens 2设备贷款给外部客户端以使用
1. 保护已贷款设备

本指南将提供[一般HoloLens 2](#general-deployment-recommendations-and-instructions)部署建议，这些建议适用于大多数 HoloLens 2部署方案，以及客户在部署外部Remote Assist时常见的问题[](#common-concerns)。

## <a name="scenario-description"></a>方案描述

就本文档而言，Contoso 公司希望将HoloLens 2设备运送到外部客户端的工厂，以便短期或长期使用。 当客户端需要维护机器的帮助时，客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用 Remote Assist 联系 Contoso 公司专家。

在此处详细了解[Remote Assist。](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>此方案的要求

1. Azure AD
1. 移动设备管理器 - 例如 [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist许可证
    1. [购买Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [试用Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>常见问题

- [如何确保外部客户端无法相互通信](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何确保客户端无法访问公司资源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制应用](#how-to-restrict-apps)
- [如何管理密码](#how-to-manage-passwords)
- [如何确保客户端无法访问聊天历史记录](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>如何确保外部客户端无法相互通信

由于Remote Assist HoloLens HoloLens调用，因此客户端能够搜索但无法相互通信。 为了进一步限制客户端可以搜索和调用谁[](/microsoft-365/compliance/information-barriers)，信息屏障可以限制客户端可以与谁通信。 要考虑的另一个选项是使用 [作用域目录搜索](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 由于已启用单一登录，因此使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。 如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>如何确保客户端无法访问公司资源

有两个选项需要考虑。

第一个选项是多层方法：

1. 仅分配用户所需的许可证。 如果未向用户分配OneDrive、Outlook、SharePoint、Yammer等，则他/她将无法访问这些资源。 用户所需的唯一许可证是Remote Assist Intune 和 AAD 许可证。
1. 阻止 (，例如) 不希望客户端访问的电子邮件 [ (请参阅如何](#how-to-restrict-apps) 限制) 。
1. 请勿与客户端共享用户名或密码。 若要登录到HoloLens 2，需要电子邮件和数字 PIN。

第二个选项是创建托管客户端的单独租户， (映像 1.1) 。

**图像 1.1**

![服务租户映像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>如何限制应用

[展台模式](/hololens/hololens-kiosk)和/或[WDAC (Windows Defender应用程序控制) ](/hololens/windows-defender-application-control-wdac)是限制应用程序的选项。

### <a name="how-to-manage-passwords"></a>如何管理密码

1. 删除密码过期。 但是，这会增加帐户遭到入侵的可能性。 NIST 密码建议是每 30-90 天更改一次密码。
1. 将设备的密码HoloLens 2超过 90 天。
1. 设备应返回到 Contoso 以更改密码。 但是，如果设备预期在客户端的工厂中工作 90 天以上，则这可能会导致问题。  
1. 对于发送到多个客户端的设备，在将设备寄送到客户端之前重置密码。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>如何确保客户端无法访问聊天历史记录

Remote Assist会话后清除聊天历史记录。 但是，聊天历史记录将可供Microsoft Teams用户使用。

> [!NOTE]
> 由于已启用单一登录，因此使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。 如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。

## <a name="general-deployment-recommendations-and-instructions"></a>常规部署推荐和说明

对于部署步骤，HoloLens 2以下内容：

1. 使用[最新的 HoloLens OS 版本](https://aka.ms/hololens2download)作为基线版本。
1. 分配基于用户或基于设备的许可证：
    1. 基于用户的许可证和基于设备的许可证都遵循以下步骤：
        1. [在 AAD 中创建组，并添加HoloLens/RA](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)用户的成员。
        1. [将基于设备或基于用户的许可证分配到](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 此组。
        1.  (可选) 可以针对 MDM 策略的组。

1. 设备应已加入租户的 AAD，自动 [注册](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过自动试点 [进行配置](/hololens/hololens2-autopilot)。
    1. 请注意，设备上的第一个用户将是设备所有者。
    1. 请注意，如果设备已加入 AAD，则执行联接的用户将成为设备所有者。
    1. 有关详细信息，请参阅 [设备所有者](/hololens/security-adminless-os#device-owner)。
1. [租户锁定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。
    1. **其他链接：租户**[锁定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。
1. 使用此处 的全局分配访问权限配置 [展台](/hololens/hololens-global-assigned-access-kiosk)。
1. 建议禁用以下可选 () 功能：
    1. 能够在此处将设备置于开发人员 [模式](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 能够将 HoloLens连接到电脑以复制日期禁用[USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > 如果不想禁用 USB，但希望能够使用 USB 将预配包应用到设备，请按照此处列出的 [**说明进行操作**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. 使用[WDAC](/hololens/windows-defender-application-control-wdac)允许或阻止设备上HoloLens 2应用。
1. 在Remote Assist更新到最新版本。 有两个选项可以这样做：
    1. 为此，可以Windows Microsoft Store **--> Remote Assist --> 更新应用**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate（](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 允许自动应用更新）默认启用。 让设备保持插入状态以接收更新。
1. [禁用除网络设置](/hololens/settings-uri-list) 之外的所有设置页，以允许用户连接到客户端站点中的来宾网络。
1. [管理HoloLens更新](/hololens/hololens-updates)
    1. 控制 [OS 更新或](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允许自由流动的选项。
1. [常见设备限制](/hololens/hololens-common-device-restrictions)。
