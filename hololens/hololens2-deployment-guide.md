---
title: 外部客户端部署指南
description: '适用于使用远程协助作为示例的适用于外部客户 (端的 HoloLens 2 部署指南) '
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308382"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>将 HoloLens 2 部署到具有远程协助的外部客户端

本指南可帮助 IT 专业人员在其组织中部署 Microsoft HoloLens 2 设备：

1. Cloud connect HoloLens 2 设备
1. 向外部客户端贷款 HoloLens 2 设备以供使用
1. 安全借出设备

本指南将提供 [一般的 hololens 2 部署建议](#general-deployment-recommendations-and-instructions) ，适用于大多数 hololens 2 部署方案，以及客户在部署外部使用的远程协助时的 [常见问题](#common-concerns) 。

## <a name="scenario-description"></a>方案描述

出于本文档的目的，Contoso 公司希望将一个 HoloLens 2 设备寄送到外部客户端的工厂，以便进行短期或长期使用。 如果客户端需要帮助服务设备，则客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用远程协助联系 Contoso 公司的专家。

[在此处](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)了解有关远程协助的详细信息。

### <a name="requirements-for-this-scenario"></a>此方案的要求

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile Device Manager-例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. 远程协助许可证
    1. [购买远程协助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [试用远程协助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>常见问题

- [如何确保外部客户端不能相互通信](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何确保客户端无法访问公司资源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制应用](#how-to-restrict-apps)
- [如何管理密码](#how-to-manage-passwords)
- [如何确保客户端无权访问聊天历史记录](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>如何确保外部客户端不能相互通信

由于不支持远程协助 HoloLens 到 HoloLens 的调用，因此客户端能够搜索，但无法进行相互通信。 为了进一步限制客户端可以搜索和调用的人员，  [信息障碍](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 可限制客户端可以与之通信。 要考虑的另一个选项是使用 [范围的目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 由于启用了单一登录，因此请务必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器。 如果外部客户端打开浏览器并使用 web 版本的团队，则客户端将有权访问呼叫/聊天历史记录。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>如何确保客户端无法访问公司资源

需要考虑两个选项。

第一个选项是多层方法：

1. 仅分配用户需要的许可证。 如果没有为用户分配 OneDrive、Outlook、SharePoint、Yammer 等，则他/她将无法访问这些资源。 用户需要的唯一许可证是远程协助、Intune 和 AAD 许可证开始。
1. 阻止应用程序 (例如不希望客户端访问的电子邮件)  (请参阅 [如何) 限制应用](#how-to-restrict-apps) 。
1. 不要将用户名和密码与客户端共享。 若要登录到 HoloLens 2，需要电子邮件和数字 PIN。

第二种方法是创建一个承载客户端的单独租户 (参阅图像 1.1) 。

**图像1。1**

![服务租户映像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>如何限制应用

[展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 应用程序控制) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是用于限制应用程序的选项。

### <a name="how-to-manage-passwords"></a>如何管理密码

1. 删除密码过期。 但是，这会增加帐户泄露的可能性。 NIST 密码建议每30-90 天更改一次密码。
1. 将 HoloLens 2 设备的密码过期时间延长到超过90天。
1. 设备应返回到 Contoso 以更改密码。 但是，如果设备预期在客户端的工厂中超过90天，这可能会导致问题。  
1. 对于发送到多个客户端的设备，在将设备发送到客户端之前重置密码。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>如何确保客户端无权访问聊天历史记录

远程协助在每个会话之后清除聊天历史记录。 但是，聊天历史记录将可供 Microsoft 团队用户使用。

> [!NOTE]
> 由于启用了单一登录，因此请务必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器。 如果外部客户端打开浏览器并使用 web 版本的团队，则客户端将有权访问呼叫/聊天历史记录。

## <a name="general-deployment-recommendations-and-instructions"></a>一般部署建议和说明

建议为 HoloLens 2 部署步骤执行以下操作：

1. 使用 [最新的 HOLOLENS OS 版本](https://aka.ms/hololens2download) 作为基准构建。
1. 分配基于用户或基于设备的许可证：
    1. 基于用户和基于设备的许可证都遵循以下步骤：
        1. [在 AAD 中创建一个组，并](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 为 HOLOLENS/RA 用户添加成员。
        1. [将基于设备或基于用户的许可证分配](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 给此组。
        1.  (可选) 你可以将 MDM 策略的组作为目标。

1. 设备应通过 AAD 加入你的租户、 [自动注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过 [自动试验](https://docs.microsoft.com/hololens/hololens2-autopilot)进行配置。
    1. 请注意，设备上的第一个用户将是设备所有者。
    1. 请注意，如果设备已加入 AAD，则执行联接的用户将成为设备所有者。
    1. 有关详细信息，请参阅 [设备所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。
1. [租户锁定](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。
    1. **附加链接：** [租户锁定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. 使用 [此处](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)的全局分配访问权限配置展台。
1. 建议禁用以下 (可选) 功能：
    1. 可以将设备置于开发[人员模式。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. 能够将 HoloLens 连接到 PC 以复制日期 [禁用 USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > 如果不想禁用 USB，但希望能够使用 USB 将设置包应用于设备，请按照 [**此处**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)列出的说明进行操作。

1. 使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 允许或阻止 HoloLens 2 设备上的应用。
1. 在安装过程中将远程协助更新到最新版本。 可以通过两种方法执行此操作：
    1. 这可以通过转到 Windows **Microsoft Store--> 远程协助--> 和更新应用** 来完成。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -默认情况下启用自动应用更新。 保持设备的连接以接收更新。
1. 禁用除网络设置以外的[所有设置页](https://docs.microsoft.com/hololens/settings-uri-list)，以允许用户在客户端站点连接到来宾网络。
1. [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)
    1. [控制 OS 更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允许自由流动的选项。
1. [常见设备限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
