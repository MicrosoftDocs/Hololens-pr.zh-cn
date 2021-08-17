---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始体验内部版本，并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 86a763adb233b45242182d069a56692aeddc2e59
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858570"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用 HoloLens 的最新 Insider preview 版本！ 这是一种非常简单的[入门](hololens-insider.md#start-receiving-insider-builds)方法，为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows内幕发行说明

我们非常高兴地开始试验新功能，以便 Windows 的预览体验。 新版本将会试验到适用于最新更新的开发和测试渠道。 我们将继续更新此页面，因为我们将更多的功能和更新添加到 Windows 有问必答版本。 令人兴奋并准备好将这些更新混合到您的现实中。

| Feature                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [reporting HoloLens 详细信息的 CSP 更改](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 Csp | IT 管理员    | 20348.1403                 |
| [由 CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [改进了更新重启检测和通知](#improved-update-restart-detection-and-notifications) | 新启用的策略和更新的 UX。 | IT 管理员 | 20348.1405 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过设置 UI 添加 PFX 证书 | 最终用户 | 20348.1405 |
| [应用更新的智能重试](#smart-retry-for-app-updates) | 允许 IT 管理员计划重试更新应用程序。 | IT 管理员 | 20348.1405 |
| [查看 HoloLens 上设置的高级诊断报告](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上的 MDM 诊断日志 | 疑难解答 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的视听反馈 | 疑难解答 | 20348.1405 |
| [仅将专用应用商店应用用于 Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示组织中的应用 | IT 管理员 | 20348.1408 |
| [低存储日志收集改进](#low-storage-log-collection-improvements) | 在低存储环境中对日志收集方案的改进。 | IT 管理员 | 20348.1412 |
| [移动平台模式](#moving-platform-mode) | 引入了移动平台模式 beta，在配置后，可以在遇到低动态运动的大型海军船舶上使用 HoloLens 2。 | 全部 | 20348.1411 |
| [修复和改进](#fixes-and-improvements) | HoloLens 的修复和改进。 | 全部 | 20348.1411 |

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

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

预览体验Windows内部版本 20348.1405 中引入。 我们已向证书管理器添加了 [支持](certificate-manager.md) ，现在使用 .pfx 证书。 当用户导航到 **"设置**  >  **更新&证书**  >  **"，** 然后选择"安装证书"时，UI 现在支持 .pfx 证书文件。 
用户可以使用私钥将 .pfx 证书导入用户存储或计算机存储。

### <a name="smart-retry-for-app-updates"></a>应用更新的智能重试

现在，HoloLens是一个新策略，允许 IT 管理员设置重复或一次性日期来重启由于应用使用而更新失败的应用，从而允许应用更新。 可以基于一些不同的触发器（例如计划时间或登录）来设置这些触发器。 若要详细了解如何使用此策略，请查看 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在诊断中查看设置诊断HoloLens

对于排查行为问题时的托管设备，确认应用了预期的策略配置是一个重要步骤。 以前，若要使用这项新功能，在导出通过 **设置** 帐户访问工作或学校收集的 MDM 诊断日志后，必须通过 MDM 或设备附近完成此操作，然后选择"导出管理日志"，并查看附近的  ->    >  电脑。

现在，可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到"访问工作或学校"页，然后选择"**查看高级诊断报告"。** 这会在新的 Edge 窗口中生成并打开报表。

![在应用内查看设置报告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

这是对名为"脱机诊断" [的现有功能的更新](hololens-diagnostic-logs.md#offline-diagnostics)。 以前，没有向用户明确指示他们已触发诊断收集或已完成。
现在，Windows预览体验内部版本中添加了两种形式的脱机诊断反馈。 第一种是，在收集开始和完成时为两者显示 toast 通知。 当用户登录且具有视觉对象时，将显示这些对象。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![日志收集完成后的 Toast。](./images/logcollection2.jpg)

由于用户通常使用脱机诊断作为回退日志收集机制，用于当用户无法访问显示器、无法登录或仍在 OOBE 中时，收集日志时也会播放音频提示。 除了 toast 通知之外，还将播放此声音。

此新功能将在设备更新时启用，无需启用或管理。 如果无法显示或听到此新反馈，仍将生成脱机诊断。

我们希望通过这种新添加的 feedback 反馈，可以更轻松地收集诊断数据，并更快排查问题。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅将专用应用商店应用用于Microsoft Store

已启用 RequirePrivateStoreOnly 策略HoloLens。 此策略Microsoft Store应用配置为只显示为组织配置的专用存储。 仅限制对可用应用的访问。

详细了解 [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>低存储日志收集改进

在收集诊断日志时设备似乎磁盘空间不足的情况下，将创建名为 **StorageDiagnostics.zip报表。** 低存储阈值由存储感知自动Windows[确定](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

### <a name="moving-platform-mode"></a>移动平台模式

自 **Insider 内部版本 20348.1411** 起，我们添加了 beta 版本支持，用于跟踪 HoloLens 2 上的低动态运动移动平台。 安装生成并启用移动平台模式后，你将能够使用以前无法访问HoloLens 2环境（如大型飞船和大型水陆船）中的设备。 目前，该功能仅针对启用这些特定的移动平台。 虽然没有任何功能会阻止你尝试在其他环境中使用该功能，但该功能侧重于首先添加对这些环境的支持。

若要详细了解支持的功能以及如何启用此新功能， [请访问移动平台页。](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>修复和改进

- 修复 [了在未提示设备门户锁定文件时出现此问题的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 修复了 [文件上传设备门户下载的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- 解决有关从设备报告符合性HoloLens的问题;可能需要重新启动才能在预览体验内部版本上触发正确的报告。  
- 已启用[分配的访问 API，](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348)以便应用现在可以确定HoloLens登录用户的展台模式是否正在运行HoloLens。
- 更新了全新闪存Remote Assist的现用版本。

## <a name="start-receiving-insider-builds"></a>开始接收预览体验内部版本

> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新生成。
>
> - "重新启动设备"语音命令运行良好。
> - 还可以选择"重启"按钮设置/Windows 会员计划。
>
> 我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。

在 HoloLens 2设备上，**转到"设置**  >  **更新&安全**  >  **Windows 会员计划并选择"****开始使用"。** 链接用于注册为预览体验成员Windows帐户。

Windows预览体验成员现在迁移到频道。 快速 **通道** 将成为 **开发通道**，慢速通道将成为Beta 版频道通道，发布预览通道将成为 **发布预览通道**。 该映射如下所示：

![Windows预览体验成员频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅博客[上的预览体验Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。
然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 
选择 **">立即重启** "以完成操作。 重启设备后，转到"设置 >更新&**安全性>检查更新** 以获取最新生成。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题

如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。

#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版

1. 设置，更新&安全性，Windows 会员计划，选择"**发布预览通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。 更新后，继续进入阶段 2。

#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道

1. 设置"更新&安全性"，Windows 会员计划，选择"**开发通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。

1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 从以下 (安装 ARC) 高级恢复 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。

1. 在HoloLens - 航班解锁：打开设置  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。  请查看开发人员[HoloLens文档](https://developer.microsoft.com/windows/mixed-reality/development)开始。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手将设备恢复到[](hololens-recovery.md)Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 中取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产生成：

1. 请参阅 **设置 > 系统 >**，并找到内部版本号。

1. [请参阅生产内部版本号的发行说明](hololens-release-notes.md)。

选择退出内幕生成：

1. 在运行生产生成的 HoloLens，请参阅 **设置 > 更新 & Security > Windows 预览体验计划**，并选择 "**停止内幕生成**"。

1. 按照说明选择设备。
