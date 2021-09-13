---
title: 将云连接 HoloLens 2 部署到外部客户端
description: '外部客户端 HoloLens 2 的部署指南 (使用远程协助作为示例) '
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
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032102"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>将云连接 HoloLens 2 部署到外部客户端

本指南是 [云连接部署指南](hololens2-cloud-connected-overview.md)的补充。 当你的组织想要将 HoloLens 2 设备发送到外部客户端的设施进行短期或长期使用时，可使用此功能。 外部客户端将使用组织提供的凭据登录到 HoloLens 2 设备，并使用[远程协助](/dynamics365/mixed-reality/remote-assist/ra-overview)联系你的专家。 本指南提供适用于大多数外部 HoloLens 2 部署方案的[一般 HoloLens 2 部署建议](#general-deployment-recommendations)，以及客户在部署外部使用的远程协助时遇到的[常见问题](#common-external-client-deployment-concerns)。 

## <a name="prerequisites"></a>先决条件

以下基础结构应按照[云连接部署指南](hololens2-cloud-connected-overview.md)进行部署，以便在外部部署 HoloLens 2。

- 与 MDM 自动注册 Azure AD 联接-MDM 管理的 (Intune) 
- 用户用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备有一个或多个用户。

### <a name="remote-assist-licensing-and-requirements"></a>远程协助许可和要求

- Azure AD 帐户（购买订阅和分配许可证时需要）
- [Remote Assist 订阅](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)（或 [Remote Assist 试用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist)）

请参阅 [了解有关远程协助的详细信息](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 用户

- Remote Assist 许可证
- 网络连接

### <a name="microsoft-teams-user"></a>Microsoft Teams 用户

- Microsoft Teams 或 [Teams Freemium](https://products.office.com/microsoft-teams/free)
- 网络连接

## <a name="general-deployment-recommendations"></a>常规部署建议

对于外部 HoloLens 2 部署，建议执行以下步骤：

1. 使用[最新的 HoloLens OS 版本](https://aka.ms/hololens2download)作为基准构建。
1. 按照以下步骤分配基于用户或基于设备的许可证：
    1. [在 AAD 中创建一个组，并](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)为 HoloLens/RA 用户添加成员。
    1. [将基于设备或基于用户的许可证分配](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 给此组。
    1.  (用于移动设备管理的可选) 目标组 [ (MDM) ](hololens-enroll-mdm.md) 策略。

1. 将 AAD 设备加入你的租户， [自动注册](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过 [Autopilot](/hololens/hololens2-autopilot)进行配置。 有关详细信息，请参阅 [设备所有者](/hololens/security-adminless-os#device-owner)。
    1. 设备上的第一个用户将是设备所有者。
    1. 如果设备已加入 AAD，则执行加入的用户将成为设备所有者。
    
1. [租户锁定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能由你的租户加入。
    1. 另请参阅 [租户锁定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。

1. [使用全局分配的访问权限配置展台模式](/hololens/hololens-global-assigned-access-kiosk)。

1. 禁用以下 (可选) 功能：
    1. 可以将设备置于开发[人员模式。](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. 能够将 HoloLens 连接到 PC 以复制日期[禁用 USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > 如果不想禁用 USB，但希望能够使用 USB 将设置包应用于设备，请按照 [如何允许安装包的说明进行操作](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. 使用[Windows Defender 应用程序控件 (WDAC) ](/hololens/windows-defender-application-control-wdac)允许或阻止 HoloLens 2 设备上的应用。
1. 在安装过程中将远程协助更新到最新版本。 请考虑以下两个选项：
    1. 请参阅 Windows **Microsoft Store--> 远程协助--> 并更新应用程序**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -默认情况下启用自动应用更新。 保持设备的连接以接收更新。
1. 禁用除网络设置以外的[所有设置页](/hololens/settings-uri-list)，以允许用户在客户端站点连接到来宾网络。
1. [管理 HoloLens 更新](/hololens/hololens-updates)
    1. [控制 OS 更新](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允许自由流动的选项。
1. 设置 [常见设备限制](/hololens/hololens-common-device-restrictions)。

现在，外部客户端可以使用其 HoloLens 2。

## <a name="common-external-client-deployment-concerns"></a>常见的外部客户端部署问题

- [确保客户端无法彼此通信](#ensure-that-external-clients-cant-communicate-with-one-another)
- [确保客户端无法访问公司资源](#ensure-that-clients-wont-have-access-to-company-resources)
- [隐藏或限制应用](#hidden-or-restricted-apps)
- [为客户端管理密码](#password-management-for-your-clients) 
- [确保客户端无法访问聊天历史记录](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>确保外部客户端无法彼此通信

远程协助 HoloLens 不支持 HoloLens 调用。 客户端可以搜索，但无法相互通信。 [Microsoft 365 中的信息障碍](/microsoft-365/compliance/information-barriers)可以进一步限制客户端可以搜索和调用的客户端。 另一种方法是使用[Microsoft Teams 作用域的目录搜索](/MicrosoftTeams/teams-scoped-directory-search)。

 > [!NOTE]
> 由于启用了单一登录，因此必须使用[Windows Defender 应用程序控件 (WDAC) ](/hololens/windows-defender-application-control-wdac)禁用浏览器。 如果外部客户端打开浏览器并使用 Teams 的 web 版本，则客户端将有权访问聊天历史记录。

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>确保客户端无法访问公司资源

需要考虑两个选项。

第一个选项是多层方法：

1. 仅分配用户需要的许可证。 如果未分配 OneDrive、Outlook、SharePoint、Yammer 等，则用户将无法访问这些资源。 用户需要的唯一许可证是远程协助、Intune 和 AAD 许可证开始。
1. 阻止应用程序 (例如不希望客户端访问的电子邮件)  (请参阅 " [应用程序处于隐藏或受限](#apps are hidden or restricted)) "。
1. 不要与客户端共享用户名和密码。 若要登录到 HoloLens 2，需要电子邮件和数字 PIN。

第二种方法是创建一个承载客户端的单独租户 (参阅图像 1.1) 。

**图像1。1**

![服务租户映像。](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>隐藏或受限应用

[展台模式](/hololens/hololens-kiosk)和/或[Windows Defender 应用程序控件 (WDAC) ](/hololens/windows-efender-application-control-wdac)是用于隐藏和/或限制应用程序的选项。

### <a name="password-management-for-your-clients"></a>你的客户端的密码管理

1. 删除密码过期。 但是，此选项可能会增加帐户泄露的可能性。 NIST 密码建议每30-90 天更改一次密码。
1. 将 HoloLens 2 设备的密码过期时间延长到超过90天。
1. 设备应返回到你的组织以更改密码。 但是，如果设备预期在客户端的工厂中超过90天，则此选项可能会导致问题。  
1. 对于发送到多个客户端的设备，在将设备发送到客户端之前重置密码。

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>确保客户端无权访问聊天历史记录

远程协助在每个会话之后清除聊天历史记录。 不过，聊天历史记录将可供 Microsoft Teams 用户使用。

> [!NOTE]
> 由于启用了单一登录，因此必须使用[Windows Defender 应用程序控件 (WDAC) ](/hololens/windows-defender-application-control-wdac)禁用浏览器。  如果外部客户端打开浏览器并使用 Teams 的 web 版本，则客户端将有权访问呼叫/聊天历史记录。
