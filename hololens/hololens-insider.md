---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始使用预览体验内部版本，并为我们的下一次主要操作系统更新提供有价值的HoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859011"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用最新的 Insider Preview 内部版本HoloLens！ 可以很轻松开始[，](hololens-insider.md#start-receiving-insider-builds)并为下一次主要操作系统更新提供有价值的反馈，HoloLens。

## <a name="windows-insider-release-notes"></a>Windows预览体验成员发行说明

我们很高兴地开始尝试新功能，以再次Windows预览体验成员。 新内部版本将前往开发和 Beta 通道获取最新更新。 在向预览体验成员内部版本添加更多功能和更新时，Windows更新此页面。 准备好将这些更新混合到现实中，

本文介绍改进的故障排除和设备报告、展台模式下的一些修复 bug 和证书查看器、扩展的可管理性图面以及更新可靠性的提升。 即将发布此功能更新的一项新功能HoloLens移动平台模式。 查看所有适用于你的新HoloLens 2！

| 功能                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [移动平台模式](#moving-platform-mode) | 引入了移动平台模式 beta 版本，该版本在配置后HoloLens 2遇到低动态运动的大型水陆船上使用移动平台模式。 | 全部 | 20348.1411 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过自定义 UI 添加 PFX 设置证书 | 最终用户 | 20348.1405 |
| [在诊断中查看设置诊断HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上 MDM 诊断日志 | 疑难解答 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的省/市/服务反馈 | 疑难解答 | 20348.1405 |
| [低存储日志收集改进](#low-storage-log-collection-improvements) | 改进了低存储情况下的日志收集方案。 | 疑难解答 | 20348.1412 |
| [针对报表和详细信息的 CSP HoloLens更改](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 CSP | IT 管理员    | 20348.1403                 |
| [CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [改进了更新重启检测和通知](#improved-update-restart-detection-and-notifications) | 新的已启用策略和用于更新的 UX。 | IT 管理员 | 20348.1405 |
| [应用更新的智能重试](#smart-retry-for-app-updates) | 允许 IT 管理员计划重试以更新应用。 | IT 管理员 | 20348.1405 |
| [仅将专用应用商店应用用于Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示来自组织的应用 | IT 管理员 | 20348.1408 |
| [使用 WDAC 和 LOB 应用](#use-wdac-and-lob-apps) | 允许 IT 管理员使用自己的应用，但仍使用 WDAC 阻止其他应用。 | IT 管理员 | 20348.1405 |
| [修复和改进](#fixes-and-improvements) | 修复和改进了 HoloLens。 | 全部 | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 管理员预览体验成员功能清单

✔️如果要将单个帐户设置为Azure AD登录，请 [配置此新 CSP。](#auto-login-policy-controlled-by-csp) <br>
✔️如果要将应用配置为在更新失败后自动尝试更新，请设置此 [新的 CSP 进行智能重试。](#smart-retry-for-app-updates) <br>
✔️若要对 OS 更新进行更多控制，请查看这些新 [启用的更新策略。](#improved-update-restart-detection-and-notifications) <br>
✔️如果需要通过 Microsoft Store 使组织的应用在公司应用商店中可用，但只想允许访问组织的应用而不是整个应用商店，请设置[此策略。](#use-only-private-store-apps-for-microsoft-store) <br>
✔️若要了解设备可用存储空间、SSID 或 BSSID HoloLens请查看这些报表[IP。](#csp-changes-for-reporting-hololens-details) <br>
✔️如果要使用 WDAC 阻止应用或进程启动，但还需要使用自己的一系列模糊应用，现在可以在 WDAC 策略 中允许[LOB。](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>移动平台模式

自 **Insider 内部版本 20348.1411** 起，我们添加了 beta 版本支持，用于跟踪 HoloLens 2 上的低动态运动移动平台。 安装生成并启用移动平台模式后，你将能够使用以前无法访问HoloLens 2环境（如大型飞船和大型水陆船）中的设备。 目前，该功能的目标是仅启用这些特定的移动平台。 虽然你可以随意地尝试在其他环境中使用该功能，但该功能首先侧重于增加对这些环境的支持。

若要详细了解支持的功能以及如何启用此新功能， [请访问移动平台页。](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

预览体验Windows内部版本 20348.1405 中引入。 我们已向证书管理器添加了 [支持](certificate-manager.md) ，现在使用 .pfx 证书。 当用户导航到 **"设置**  >  **更新&证书**  >  **"，** 然后选择"安装证书"时，UI现在支持 .pfx 证书文件。
用户可以使用私钥将 .pfx 证书导入用户存储或计算机存储。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在诊断中查看设置诊断HoloLens

对于排查行为问题时的托管设备，确认应用了预期的策略配置是一个重要步骤。 以前，对于此新功能，在导出通过 **设置** 帐户访问工作或学校收集的 MDM 诊断日志后，必须通过 MDM 或附近的设备查看此信息，然后选择"导出管理日志"，并查看附近的  ->    >  电脑。

现在，可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到"访问工作或学校"页，然后选择"**查看高级诊断报告"。** 这会在新的 Edge 窗口中生成并打开报表。

![在应用内查看设置报告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

这是对名为"脱机诊断" [的现有功能的更新](hololens-diagnostic-logs.md#offline-diagnostics)。 以前，没有向用户明确指示他们已触发诊断收集或已完成。
现在，Windows预览体验内部版本中添加了两种形式的脱机诊断反馈。 第一种是，在收集开始和完成时为两者显示 toast 通知。 当用户登录且具有视觉对象时，将显示这些对象。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![日志收集完成后的 Toast。](./images/logcollection2.jpg)

由于用户通常使用脱机诊断作为回退日志收集机制，用于当用户无法访问显示器、无法登录或仍在 OOBE 中时，收集日志时也会播放音频提示。 除了 toast 通知之外，还将播放此声音。

这项新功能将在设备更新时启用，不需要启用或管理。 如果无法显示或听不到此新反馈，则仍将生成脱机诊断。

我们希望这种新的视听反馈增加，更易于收集诊断数据，并能更快地解决问题。

### <a name="low-storage-log-collection-improvements"></a>低存储日志收集改进

如果收集诊断日志时，设备的磁盘空间似乎不足，则将创建一个名为 **StorageDiagnostics.zip** 的附加报表。 Windows[存储感知](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)会自动确定低存储的阈值。

### <a name="csp-changes-for-reporting-hololens-details"></a>reporting HoloLens 详细信息的 CSP 更改

- 在 Windows 有问必答版本20348.1403 中引入

下面的 csp 已经用新方法进行了更新，以从 HoloLens 设备报告信息。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP-免费存储

DevDetail CSP 现在还报告 HoloLens 设备上的可用存储空间。 这应该与设置应用的存储页面中显示的值大致匹配。 下面是包含此信息的特定节点。

- /DevDetail/Ext/Microsoft/FreeStorage (仅获取操作) 

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP-SSID 和 BSSID

DeviceStatus CSP 现在还会报告与 HoloLens 主动连接 Wi-Fi 网络的 SSID 和 BSSID。 下面是包含此信息的特定节点。

- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

适用于 MDM 供应商的 syncml blob (的示例) 查询 NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>由 CSP 控制的自动登录策略

这个新的 AutoLogonUser 策略控制用户是否将自动登录。 某些客户需要设置绑定到标识的设备，但不需要任何登录体验。 Imagine 立即提取设备并使用远程协助。 或者有一个好处，即能够快速分发 HoloLens 设备，并使最终用户能够快速登录。

如果策略设置为非空值，则它指定自动登录用户的电子邮件地址。 指定的用户必须至少登录到设备一次，才能启用自动登录。

新策略 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 字符串值的 oma-uri

- 具有相同电子邮件地址的用户将启用自动登录。

在配置了此策略的设备上，策略中指定的用户至少需要登录一次。 第一次登录后，随后的设备重新启动将使指定的用户自动登录。 仅支持单个自动登录用户。 启用后，自动登录的用户将不能手动注销。 若要以其他用户身份登录，必须先禁用策略。

> [!NOTE]
>
> - 某些事件（例如，主要 OS 更新）可能需要指定的用户重新登录到设备，才能恢复自动登录行为。
> - 仅 MSA 和 AAD 用户支持自动登录。

### <a name="improved-update-restart-detection-and-notifications"></a>改进了更新重启检测和通知

在活动时间和安装时策略之间，在使用时可以避免重新启动 HoloLens 设备。 但是，如果不进行重新启动来完成所需更新的安装，它也会延迟更新的采用。 现在我们已添加策略，以允许它强制执行截止时间和必需的重新启动，并确保及时完成更新的安装。 用户可以在启动重新启动之前通知用户，并可根据 IT 策略延迟重新启动。

添加了以下更新策略：

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>应用更新的智能重试

现在为 HoloLens 启用了新策略，该策略允许 IT 管理员设置定期或一次性日期，以重新启动由于正在使用的应用程序允许应用更新而导致更新失败的应用。 可以基于几个不同的触发器（如计划时间或登录）来设置这些设置。 若要了解有关如何使用此策略视图的详细信息，请参阅 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅对 Microsoft Store 使用专用应用商店应用

已为 HoloLens 启用 RequirePrivateStoreOnly 策略。 此策略允许将 Microsoft Store 应用配置为仅显示为组织配置的专用存储。 仅将访问权限限制为可用的应用。

了解有关[ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)的详细信息

### <a name="use-wdac-and-lob-apps"></a>使用 WDAC 和 LOB 应用

你现在可以使用 WDAC 阻止应用或进程启动并继续使用你自己的 bushiness 应用程序。 你现在可以在 WDAC 策略中允许它们。 使用此策略时，需要在创建 WDAC 策略时在 PowerShell 中运行额外的代码行。 [查看此处的步骤。](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>修复和改进

- 修复了在 [未提示下载锁定文件的情况下设备门户的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 修复了 [包含文件上传和下载超时的设备门户的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- 解决与 HoloLens 设备报告符合性属性有关的问题;可能需要重新启动才能在内幕生成上触发正确的报告。  
- 已启用[分配的访问 API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) ，以便应用现在可以确定 HoloLens 是否在展台模式下为登录到 HoloLens 的用户运行。
- 更新了全新闪烁的远程协助的内置版本。

## <a name="start-receiving-insider-builds"></a>开始接收 Insider 内部版本

> [!NOTE]
> 如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。
>
> - "重新启动设备" 语音命令正常工作。
> - 你还可以在设置/Windows 预览体验计划 "中选择" 重新启动 "按钮。
>
> 我们在你可能遇到的后端上遇到了一个错误，这会使你返回到 "跟踪"。

在 HoloLens 2 设备上，转到 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，并选择 "**入门**"。 将用于注册的帐户链接到 Windows 有问必答。

Windows 有问必答现在正在移至频道。 **快速** 环将成为 **开发通道**，**慢速** 环将成为 **Beta 通道**，并且 **发布预览** 环将成为 **发布预览通道**。 如下图所示：

![Windows内幕频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 Windows 博客上的[Windows 有问必答通道简介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)。
然后，选择 " **Windows 的" 活动开发**"，选择是要接收 **开发渠道** 还是生成 **Beta 通道**，并查看程序条款。
选择 " **确认" > 立即重新启动** 以完成操作。 重新启动设备后，请转到 **设置 > 更新 & 安全 > 检查更新** 以获取最新版本。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490 解决方法

如果在开发或 Beta 通道上进行更新时遇到更新错误0x80070490，请尝试以下短期解决方法。 它涉及到移动预览体验，选择更新，然后再移到你的内部渠道。

#### <a name="stage-one---release-preview"></a>阶段单一发布预览版

1. 设置、更新 & 的安全 Windows 预览体验计划，请选择 "**发布预览通道**"。

2. 设置、更新 & 安全性、Windows 更新，**检查更新**。 更新后，继续执行第二阶段。

#### <a name="stage-two---dev-channel"></a>阶段两开发人员通道

1. 设置，请更新 & 安全 Windows 预览体验计划，然后选择 "**开发通道**"。

2. 设置、更新 & 安全性、Windows 更新，**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签名 ffu 进行测试，必须先将设备解锁，然后再闪烁飞行签名 ffu。

1. 在 PC 上：
    1. 从下载 ffu [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 从 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。

1. 在HoloLens - 航班解锁 **：打开** 设置  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。  若要开始[HoloLens请参阅开发人员](https://developer.microsoft.com/windows/mixed-reality/development)文档。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手恢复设备[](hololens-recovery.md)，将设备恢复到 Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 中取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产内部版本：

1. 转到 **"设置 >系统>关于"，** 并找到生成号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

选择退出预览体验内部版本：

1. 在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**

1. 按照说明选择退出设备。
