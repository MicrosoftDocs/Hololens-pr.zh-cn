---
title: 将云连接HoloLens 2外部客户端
description: '使用远程HoloLens 2为外部客户端 (部署指南作为示例) '
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 476ea17dfad114741191595fa0ce3bd1c7bca28d
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401127"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>将云连接HoloLens 2外部客户端

本指南是对云连接部署指南 [的补充](hololens2-cloud-connected-overview.md)。 它用于组织希望将设备HoloLens 2外部客户端设施供短期或长期使用的情况。 外部客户端将使用组织HoloLens 2凭据登录到 Remote Assist 设备，并联系专家。 [](/dynamics365/mixed-reality/remote-assist/ra-overview) 本指南提供了[一HoloLens 2](#general-deployment-recommendations)部署建议，这些建议适用于大多数HoloLens 2部署方案，以及客户在部署外部Remote Assist时常见的问题。 [](#common-external-client-deployment-concerns) 

## <a name="prerequisites"></a>先决条件

应按照云连接部署指南部署以下基础结构[，](hololens2-cloud-connected-overview.md)以在HoloLens 2部署。

- Azure AD MDM 自动注册 - MDM 托管 (Intune) 
- 用户使用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备的一个或多个用户。

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist许可和要求

- Azure AD 帐户（购买订阅和分配许可证时需要）
- [Remote Assist 订阅](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)（或 [Remote Assist 试用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist)）

请参阅[详细了解 Remote Assist。](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 用户

- Remote Assist 许可证
- 网络连接

### <a name="microsoft-teams-user"></a>Microsoft Teams 用户

- Microsoft Teams 或 [Teams Freemium](https://products.office.com/microsoft-teams/free)
- 网络连接

## <a name="general-deployment-recommendations"></a>常规部署建议

对于外部部署，建议HoloLens 2步骤：

1. 使用[最新的 HoloLens OS 版本](https://aka.ms/hololens2download)作为基线版本。
1. 按照以下步骤分配基于用户或基于设备的许可证：
    1. [在 AAD 中创建组，并添加HoloLens/RA](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)用户的成员。
    1. [将基于设备或基于用户的许可证分配到](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 此组。
    1.  (MDM) 策略的移动设备管理 [ (可选) ](hololens-enroll-mdm.md) 组。

1. 将 AAD 设备加入租户， [自动注册](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过 [Autopilot 进行配置](/hololens/hololens2-autopilot)。 有关详细信息，请参阅 [设备所有者](/hololens/security-adminless-os#device-owner)。
    1. 设备上的第一个用户将是设备所有者。
    1. 如果设备已加入 AAD，则执行联接的用户将成为设备所有者。
    
1. [租户](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 锁定设备，以便只有租户才能加入该设备。
    1. 另请参阅 [租户锁定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。

1. [使用全局分配的访问权限 配置展台模式](/hololens/hololens-global-assigned-access-kiosk)。

1. 禁用以下 (可选) 功能：
    1. 能够在此处将设备置于开发人员 [模式](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 能够将 HoloLens连接到电脑以复制日期禁用[USB。](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > 如果不想禁用 USB，但希望能够使用 USB 将预配包应用到设备，请按照有关如何允许预配包安装 [的说明进行操作](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. 使用[Windows Defender 应用程序控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)允许或阻止设备上HoloLens 2应用。
1. 在Remote Assist更新到最新版本。 请考虑以下两个选项：
    1. 转到"Windows Microsoft Store **--> Remote Assist --> 更新应用"。**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate（](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 允许自动应用更新）默认启用。 让设备保持插入状态以接收更新。
1. [禁用除网络设置](/hololens/settings-uri-list) 之外的所有设置页，以允许用户连接到客户端站点中的来宾网络。
1. [管理 HoloLens 更新](/hololens/hololens-updates)
    1. 控制 [OS 更新或](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允许自由流动的选项。
1. 设置 [常见设备限制](/hololens/hololens-common-device-restrictions)。

现在，外部客户端可以使用其HoloLens 2。

## <a name="common-external-client-deployment-concerns"></a>常见的外部客户端部署问题

- [确保客户端无法相互通信](#ensure-that-external-clients-cant-communicate-with-one-another)
- [确保客户端无法访问公司资源](#ensure-that-clients-wont-have-access-to-company-resources)
- [隐藏或限制应用](#hidden-or-restricted-apps)
- [管理客户端的密码](#password-management-for-your-clients) 
- [确保客户端无法访问聊天历史记录](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>确保外部客户端无法相互通信

Remote Assist HoloLens HoloLens调用。 客户端可以搜索，但不能相互通信。 [客户端中的信息Microsoft 365](/microsoft-365/compliance/information-barriers)可以进一步限制客户端可以搜索和调用谁。 另一个选项是使用[Microsoft Teams范围的目录搜索](/MicrosoftTeams/teams-scoped-directory-search)。

 > [!NOTE]
> 由于已启用单一登录，因此使用 WDAC Windows Defender 应用程序控制 (禁用[) 。 ](/hololens/windows-defender-application-control-wdac) 如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问聊天历史记录。

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>确保客户端无法访问公司资源

有两个选项需要考虑。

第一个选项是多层方法：

1. 仅分配用户所需的许可证。 如果未分配资源、OneDrive Outlook、SharePoint、Yammer等，则用户将无法访问这些资源。 用户所需的唯一许可证是Remote Assist Intune 和 AAD 许可证才能开始。
1. 阻止 (应用，例如) 不希望客户端访问的电子邮件 (请参阅应用[隐藏或) 。](#apps are hidden or restricted)
1. 不要与客户端共享用户名或密码。 若要登录到HoloLens 2，需要电子邮件和数字 PIN。

第二个选项是创建托管客户端的单独租户， (映像 1.1) 。

**图像 1.1**

![服务租户映像](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>隐藏或受限应用

[展台模式](/hololens/hololens-kiosk)和/或[Windows Defender应用程序 (WDAC) ](/hololens/windows-efender-application-control-wdac)是隐藏和/或限制应用程序的选项。

### <a name="password-management-for-your-clients"></a>客户端的密码管理

1. 删除密码过期。 但是，此选项可能会增加帐户遭到入侵的可能性。 NIST 密码建议是每 30-90 天更改一次密码。
1. 将设备的密码过期HoloLens 2超过 90 天。
1. 设备应返回到组织以更改密码。 但是，如果设备预期在客户端的工厂中工作 90 天以上，则此选项可能会导致问题。  
1. 对于发送到多个客户端的设备，在将设备寄送到客户端之前重置密码。

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>确保客户端无法访问聊天历史记录

Remote Assist会话后清除聊天历史记录。 但是，聊天历史记录将可供Microsoft Teams用户使用。

> [!NOTE]
> 由于已启用单一登录，因此使用 WDAC Windows Defender 应用程序控制 (禁用[) 。 ](/hololens/windows-defender-application-control-wdac)  如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。
