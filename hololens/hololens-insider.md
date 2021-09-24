---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始使用预览体验内部版本，并为我们的下一次主要操作系统更新提供有价值的HoloLens。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 68485fd0ad7f050748a412da3d57eb8f59e9a685
ms.sourcegitcommit: d09556a101663ef5dfff865d4753e64a41032b78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "128346738"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用最新的 Insider Preview 内部版本HoloLens！ 只需开始操作[，](hololens-insider.md#start-receiving-insider-builds)并为下一次主要操作系统更新提供有价值的反馈，HoloLens。

## <a name="windows-insider-release-notes"></a>Windows预览体验成员发行说明

我们很高兴地开始尝试新功能，再次Windows预览体验成员。 新内部版本将前往开发和 Beta 通道获取最新更新。 在向预览体验成员内部版本添加更多功能和更新时，Windows更新此页面。 准备好将这些更新混合到现实中，

本文介绍改进的故障排除和设备报告、展台模式下的一些修复 bug 和证书查看器、扩展的可管理性图面以及更新可靠性的提升。 即将发布此功能更新的一项新功能HoloLens移动平台模式。 查看所有适用于 HoloLens 2！

| 功能                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [移动平台模式](#moving-platform-mode) | 引入了移动平台模式 beta 版本，在配置后，HoloLens 2在遇到低动态运动的大型水陆上使用移动平台模式。 | 全部 | 20348.1411 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过自定义 UI 添加 PFX 设置证书 | 最终用户 | 20348.1405 |
| [在 HoloLens 中查看设置诊断HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上 MDM 诊断日志 | 故障排除 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的省/市/服务反馈 | 故障排除 | 20348.1405 |
| [低存储日志收集改进](#low-storage-log-collection-improvements) | 改进了低存储情况下的日志收集方案。 | 故障排除 | 20348.1412 |
| [CSP 更改报表HoloLens详细信息](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 CSP | IT 管理员    | 20348.1403                 |
| [CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [改进了更新重启检测和通知](#improved-update-restart-detection-and-notifications) | 新的已启用策略和用于更新的 UX。 | IT 管理员 | 20348.1405 |
| [应用更新的智能重试](#smart-retry-for-app-updates) | 允许 IT 管理员计划重试以更新应用。 | IT 管理员 | 20348.1405 |
| [仅将专用应用商店应用用于Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示来自组织的应用 | IT 管理员 | 20348.1408 |
| [使用 WDAC 和 LOB 应用](#use-wdac-and-lob-apps) | 允许 IT 管理员使用自己的应用，但仍使用 WDAC 阻止其他应用。 | IT 管理员 | 20348.1405 |
| [修复和改进](#fixes-and-improvements) | 修复和改进了 HoloLens。 | 全部 | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 管理员预览体验成员功能清单

✔️如果要将单个帐户设置为Azure AD登录，请 [配置此新 CSP。](#auto-login-policy-controlled-by-csp) <br>
✔️如果要将应用配置为在更新失败后自动尝试更新，请设置此 [新的 CSP 进行智能重试。](#smart-retry-for-app-updates) <br>
✔️若要对 OS 更新进行更多控制，请查看这些新 [启用的更新策略](#improved-update-restart-detection-and-notifications)。 <br>
✔️如果需要通过 Microsoft Store 使组织的应用在公司应用商店中可用，但只想允许访问组织的应用而不是整个应用商店，请设置[此策略](#use-only-private-store-apps-for-microsoft-store)。 <br>
✔️如果想了解设备可用存储空间、SSID 或 BSSID HoloLens请查看这些[报告 CSP。](#csp-changes-for-reporting-hololens-details) <br>
✔️如果要使用 WDAC 来阻止应用或进程启动，但还需要使用自己的模糊应用行，现在可以在 WDAC 策略 中允许[LOB。](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>移动平台模式

自 **Insider 内部版本 20348.1411** 起，我们添加了 beta 版本支持，用于跟踪 HoloLens 2 上的低动态运动移动平台。 安装生成并启用移动平台模式后，你将能够使用以前无法访问HoloLens 2环境（如大型飞船和大型水陆船）中的设备。 目前，该功能的目标是仅启用这些特定的移动平台。 虽然你可以随意地尝试在其他环境中使用该功能，但该功能首先侧重于增加对这些环境的支持。

若要详细了解支持的功能以及如何启用此新功能， [请访问移动平台页](hololens2-moving-platform.md)。

#### <a name="overview-to-try-out-moving-platform-mode"></a>试用移动平台模式概述

1. [启用开发人员模式和设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. [通过设备门户 启用移动平台模式](hololens2-moving-platform.md#enabling-moving-platform-mode)。
1. 将设备移动到大型移动平台，并观察全息影像有多稳定。

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

在预览体验Windows内部版本 20348.1405 中引入。 我们已向证书管理器添加了 [支持](certificate-manager.md) ，现在使用 .pfx 证书。 当用户导航到 **"设置**  >  **更新&安全** 证书  >  **"，** 然后选择"安装证书"时，UI 现在支持 .pfx 证书文件。
用户可以使用私钥将 .pfx 证书导入用户存储或计算机存储。

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>在证书管理器中试用 PFX 文件的概述

1. 准备 PFX 文件。
1. 通过 USB-C 电缆将文件复制到设备。
1. 打开设置应用，导航到证书[管理器](certificate-manager.md)并应用证书。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在 HoloLens 中查看设置诊断HoloLens

对于排查行为问题时的托管设备，确认应用了预期的策略配置是一个重要步骤。 以前对于此新功能，在导出通过 **设置** 帐户访问工作或学校收集的 MDM 诊断日志后，必须通过 MDM 在设备外或附近查看此信息，然后选择"导出管理日志"，并查看附近的  ->    >  电脑。

现在，可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到"访问工作或学校"页，然后选择"**查看高级诊断报告"。** 这会在新的 Edge 窗口中生成并打开报表。

![在应用内查看设置报告。](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>试用高级诊断报告的概述

1. 打开设置应用。
1. 导航到 "帐户" 页，然后单击 "新建" 链接以 **导出管理日志**。
1. 查看有关设备配置的高级信息。

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

此更新适用于称为 [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)的现有功能。 以前，用户已触发诊断收集或已完成，没有明确的指示器。
现已添加到 Windows 内部版本中，对于脱机诊断，有两种形式的视听反馈。 当收集开始和完成时，将显示第一个 toast 通知。 当用户登录并具有视觉对象时，将显示这些用户。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![记录收集完成时 Toast。](./images/logcollection2.jpg)

由于用户经常会使用脱机诊断作为回退日志收集机制来访问显示器、无法登录或仍处于 OOBE 状态，因此在收集日志时也会播放音频提示。 除了 toast 通知外，还会播放此声音。

这项新功能将在设备更新时启用，不需要启用或管理。 如果无法显示或听不到此新反馈，则仍将生成脱机诊断。

我们希望这种新的视听反馈增加，更易于收集诊断数据，并能更快地解决问题。

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>试用诊断通知概述

1. 解锁设备并磨损设备。
1. 按下 **电源** 和 **音量** 按钮组合，收集 [离线诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 查看 toast 通知，并在设备启动和完成收集日志时倾听音频提示。

### <a name="low-storage-log-collection-improvements"></a>低存储日志收集改进

如果收集诊断日志时，设备的磁盘空间似乎不足，则将创建一个名为 **StorageDiagnostics.zip** 的附加报表。 Windows[存储感知](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)会自动确定低存储的阈值。

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>试用低存储改进的概述

1. 填写设备的存储空间。
1. 按下 **电源** 和 **音量** 按钮组合，收集 [离线诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 观察在您的 HoloLens 的 Documents 文件夹中存储的日志集合中是否有一个新的文件。

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

#### <a name="overview-to-try-auto-logon-csp"></a>尝试自动登录 CSP 概述

1. [使用自定义策略](/mem/intune/configuration/custom-settings-windows-10)将新 CSP 配置到所需用户：`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. 通过 [预配包](hololens-provisioning.md) 或 [MDM](hololens-mdm-configure.md)将 CSP 应用到设备。
1. 登录到指定的帐户。
1. 重新启动设备，并观察用户是否已自动登录。

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

#### <a name="overview-to-try-new-update-notifications"></a>尝试新的更新通知概述

1. 通过 [预配包](hololens-provisioning.md) 或 [MDM](hololens-mdm-configure.md) 配置新的更新 csp 之一 (参阅上面的链接列表并选择一个) 。
1. 在计划时间内使用设备。
1. 观察用户是否收到更新通知，并需要重新启动设备 \* 。

\* 根据所使用的更新策略，结果可能会有所不同。

### <a name="smart-retry-for-app-updates"></a>应用更新的智能重试

现在为 HoloLens 启用了新策略，该策略允许 IT 管理员设置定期或一次性日期，以重新启动由于正在使用的应用程序允许应用更新而导致更新失败的应用。 可以基于几个不同的触发器（如计划时间或登录）来设置这些设置。 若要了解有关如何使用此策略视图的详细信息，请参阅 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>有关尝试应用更新的智能重试的概述

1. 配置新的智能重试功能。
1. 在尚未接收到你的应用并正确配置为的设备上，在联机环境中登录。
1. 使设备无法通过关闭或断开连接来下载应用。
1. 你的设备已打开并已在触发时连接到 internet，因此无法重试下载。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅对 Microsoft Store 使用专用应用商店应用

已为 HoloLens 启用 RequirePrivateStoreOnly 策略。 此策略使 Microsoft Store 应用程序可以配置为仅显示通过[适用于企业的 Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)为组织配置的专用存储。 仅将访问权限限制为可用的应用。

了解有关 [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)的详细信息。

#### <a name="overview-to-try-only-private-store-apps"></a>概述以仅尝试专用应用商店应用

1. 通过 [MDM](hololens-mdm-configure.md)为你的设备配置新策略。
1. 登录到具有策略的设备。
1. 打开 Microsoft Store 应用并观察你只能看到你的组织的应用。

### <a name="use-wdac-and-lob-apps"></a>使用 WDAC 和 LOB 应用

现在，可以使用 WDAC 阻止应用或进程启动，并继续使用自己的一系列粘性应用。 现在可以在 WDAC 策略中允许它们。 使用此策略涉及在创建 WDAC 策略时在 PowerShell 中运行额外的代码行。 [查看此处的步骤](/mem/intune/configuration/custom-profile-hololens)。

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>使用 WDAC 阻止其他应用时试用自己的应用的概述

1. 收集 LOB 应用的 AUMID 以及要阻止的应用。
1. [按照新步骤创建新的 WDAC](/mem/intune/configuration/custom-profile-hololens) 策略。
1. [使用 MDM 将策略](hololens-mdm-configure.md) 部署到设备。
1. 登录到设备并观察可以启动应用并阻止其他人。

### <a name="fixes-and-improvements"></a>修复和改进

#### <a name="for-developers"></a>面向开发人员

- 修复 [了在未提示设备门户锁定文件 时出现的文件的已知问题](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)。
- 修复了 [文件上传设备门户下载的一个已知问题](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)。
- 预览体验成员内部版本已禁用 2D 应用的游戏板处理。 删除它后，应用现在可以直接使用 Gamepad API，并可以访问整个控件集，并且可以考虑开发以执行更多操作。 开发人员应该使用 Gamepad API 来使用游戏板输入。 下面是[Gamepad 类示例 (Windows。Gaming.Input) - Windows UWP 应用程序](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)。
- 已启用[分配的访问 API，](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)以便应用现在可以确定HoloLens登录用户的展台模式是否正在运行HoloLens。

#### <a name="for-enterprise"></a>对于Enterprise

- 解决有关从设备报告符合性HoloLens的问题;可能需要重新启动才能在预览体验内部版本上触发正确的报告。  
- 更新了全新闪存Remote Assist安装的版本。
- 修复了使用基于 AAD 组的展台配置的情况下，首次用户登录后终止 OOBE 的问题。
- 更正了有关显示设备重启更新通知和对话框提示的问题。
- 修复了在设备重启后，需要再次配对 xbox 控制器蓝牙 LE 外围设备才能连接的问题。

## <a name="start-receiving-insider-builds"></a>开始接收预览体验内部版本

> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新生成。
>
> - "重新启动设备"语音命令运行良好。
> - 还可以选择"重启"按钮，设置/Windows 会员计划。
>
> 我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。

在 HoloLens 2设备上，**转到"设置**  >  **更新&安全**  >  **Windows 会员计划并选择"****开始使用"。** 链接用于注册为预览体验成员Windows帐户。

> [!NOTE]
> 若要在预览体验成员内部版本中注册设备，需要启用可选遥测。 如果尚未这样做，请打开 设置 应用，选择"隐私诊断&  ->  **反馈"，然后选择"** 可选 **诊断数据"。**

Windows预览体验成员现在迁移到频道。 快速 **通道** 将成为 **开发通道**，慢速通道将成为Beta 版频道通道，发布预览通道将成为 **发布预览通道**。 该映射如下所示：

![WindowsInsider Channels 说明。](images/WindowsInsiderChannels.png)

有关详细信息，请参阅博客[上的预览体验Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。
然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 
选择 **">立即重启** "以完成操作。 重启设备后，转到"设置 >更新&**安全性>检查更新**，获取最新生成。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题

如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。

#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版

1. 设置，更新&安全性，Windows 会员计划，选择"**发布预览通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。 更新后，继续进入阶段 2。

#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道

1. 设置，更新&安全性，Windows 会员计划，选择"**开发通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。

1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 从以下 (安装 ARC) 高级恢复 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。

1. 在HoloLens - 航班解锁 **：打开** 设置  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens提供反馈并报告问题。 使用 反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励尝试使用预览体验成员内部版本开发HoloLens。  若要开始[HoloLens请参阅开发人员](https://developer.microsoft.com/windows/mixed-reality/development)文档。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手恢复设备，[](hololens-recovery.md)将设备恢复到 Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 中取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产内部版本：

1. 转到 **"设置 >系统>关于**"，并找到生成号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

选择退出预览体验内部版本：

1. 在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**

1. 按照说明选择退出设备。
