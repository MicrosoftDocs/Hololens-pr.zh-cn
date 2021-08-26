---
title: HoloLens展台参考信息
description: 设备上展台的信息HoloLens示例。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863931"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens展台参考信息

此页面包含有关设置设备展台HoloLens的有用信息。 此参考包括收件箱应用和定位的 AUMID，以及展台模式的几个 XML 示例，这些示例只需进行一些编辑即可用于多个不同的方案。 有关设置展台的信息，请阅读 [设置展台页。](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens应用程序用户模型 ID (AUMID)   

有关如何选择展台应用的一般信息，请参阅有关在展台模式下选择分配 ([应用) 。 ](/windows/configuration/guidelines-for-assigned-access-app)

如果使用 Mobile 设备管理 (MDM) 系统或预配包来配置展台模式，请使用 [AssignedAccess 配置 ](/windows/client-management/mdm/assignedaccess-csp) 服务提供程序 (CSP) 来指定应用程序。 CSP 使用 [AUMID (应用程序用户) 标识 ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 应用程序。 下表列出了可在多应用展台中使用的一些已装箱应用程序的 AUMID。

<a id="aumids"></a>

|应用名称 |AUMID |
| --- | --- |
|3D 查看器 |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|日历 |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|相机<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! 应用 |
|第一代HoloLens (上的设备选取)  |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|设备上的设备选取HoloLens 2 |微软。Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows。DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|反馈 &nbsp; 中心 |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 应用 |
|文件资源浏览器 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！microsoft.windowslive.mail |
|旧Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新的 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|电影和电视 |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! 应用 |
|照片 |微软。Windows。照片 \_ 8wekyb3d8bbwe \! 应用 |
|旧设置 |HolographicSystemSettings_cw5n1h2txyewy！应用程序 |
|新建设置 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用程序 |
|提示 |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 若要启用照片或视频捕获，必须启用相机应用作为展台应用。  
> <sup>2</sup> 启用相机应用时，请注意以下条件：
> - "快速操作"菜单包括"照片和视频"按钮。
> - 还应启用应用 (，例如照片、邮件或OneDrive) 或检索图片的应用。  
>  
> <sup>3</sup>即使未启用Cortana应用，内置语音命令也已启用。 但是，与已禁用功能相关的命令不起作用。  
> <sup>4</sup>不能直接Miracast启用。 若要启用Miracast展台应用，请启用相机应用和设备选取器应用。

此外，混合现实主页无法设置为展台应用。

根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>展台 XML 代码示例

1. [多个应用全局分配的访问配置文件](#multiple-app-global-assigned-access-profile)
1. [多个应用全局分配的访问配置文件（设备所有者除外）](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [本地帐户或 AAD 用户帐户的多个应用分配的访问权限配置文件](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [为两个或多个 AAD 用户分配了多个应用访问配置文件](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [为一个 AAD 组分配多个应用访问配置文件](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [两个或多个 AAD 组的多个应用分配的访问权限配置文件](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [为一个 AAD 帐户和一个 AAD 组分配了多个应用访问配置文件](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [为访问者分配的多个应用访问配置文件](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> 根据要求替换 TODO 操作。

### <a name="multiple-app-global-assigned-access-profile"></a>多个应用全局分配的访问配置文件

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>多个应用全局分配的访问配置文件（设备所有者除外）

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>本地帐户或 AAD 用户帐户的多个应用分配的访问权限配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>为两个或多个 AAD 用户分配了多个应用访问配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>为一个 AAD 组分配多个应用访问配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>两个或多个 AAD 组的多个应用分配的访问权限配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>为一个 AAD 帐户和一个 AAD 组分配了多个应用访问配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>为访问者分配的多个应用访问配置文件

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[返回到列表](#kiosk-xml-code-samples) <br>
根据标识 [类型返回到展台模式支持的方案](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
