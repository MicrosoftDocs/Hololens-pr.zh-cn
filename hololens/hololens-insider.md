---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始体验内部版本，并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
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
ms.openlocfilehash: 22d635fd3fc32b8aedc36bcb19d900128cdcb718
ms.sourcegitcommit: ab86b31357004726d8a28ebae76123728adc8e59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "128306159"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用 HoloLens 的最新 Insider preview 版本！ 这是一种非常简单的[入门](hololens-insider.md#start-receiving-insider-builds)方法，为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows内幕发行说明

我们非常高兴地开始试验新功能，以便 Windows 的预览体验。 新版本将会试验到适用于最新更新的开发和测试渠道。 我们将继续更新此页面，因为我们将更多的功能和更新添加到 Windows 有问必答版本。 令人兴奋并准备好将这些更新混合到您的现实中。

这一问题与改进了疑难解答和设备报表、展台模式和证书查看器中的一些固定 bug、扩展的可管理性面以及增加的更新可靠性相关。 此功能更新的新旗舰功能 HoloLens 是我们的移动平台模式。 查看 HoloLens 2 的所有全新功能！

| 功能                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [移动平台模式](#moving-platform-mode) | 引入了移动平台模式 beta，在配置后，可以在遇到低动态运动的大型海军船舶上使用 HoloLens 2。 | 全部 | 20348.1411 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过设置 UI 添加 PFX 证书 | 最终用户 | 20348.1405 |
| [查看 HoloLens 上设置的高级诊断报告](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上的 MDM 诊断日志 | 疑难解答 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的视听反馈 | 疑难解答 | 20348.1405 |
| [低存储日志收集改进](#low-storage-log-collection-improvements) | 在低存储环境中对日志收集方案的改进。 | 疑难解答 | 20348.1412 |
| [reporting HoloLens 详细信息的 CSP 更改](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 Csp | IT 管理员    | 20348.1403                 |
| [由 CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [改进了更新重启检测和通知](#improved-update-restart-detection-and-notifications) | 新启用的策略和更新的 UX。 | IT 管理员 | 20348.1405 |
| [应用更新的智能重试](#smart-retry-for-app-updates) | 允许 IT 管理员计划重试更新应用程序。 | IT 管理员 | 20348.1405 |
| [仅将专用应用商店应用用于 Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示组织中的应用 | IT 管理员 | 20348.1408 |
| [使用 WDAC 和 LOB 应用](#use-wdac-and-lob-apps) | 允许 IT 管理员使用其自己的应用程序，仍使用 WDAC 来阻止其他应用。 | IT 管理员 | 20348.1405 |
| [修复和改进](#fixes-and-improvements) | HoloLens 的修复和改进。 | 全部 | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 管理员有问必答功能清单

✔️如果要将单个 Azure AD 帐户设置为自动登录，请 [配置此新 CSP。](#auto-login-policy-controlled-by-csp) <br>
✔️如果你想要将应用配置为在更新失败后自动尝试更新，请 [将此新 CSP 设置为 "智能重试"。](#smart-retry-for-app-updates) <br>
✔️如果你想要更好地控制 OS 更新，请查看这些 [新启用的更新策略](#improved-update-restart-detection-and-notifications)。 <br>
✔️如果您需要通过 Microsoft Store 使您的组织的应用程序在公司商店中可用，但希望只允许访问您的组织的应用程序而不允许使用完全存储，请[设置此策略](#use-only-private-store-apps-for-microsoft-store)。 <br>
✔️如果要了解 HoloLens 设备的可用存储空间、SSID 或 BSSID，请查看这些[报告 csp](#csp-changes-for-reporting-hololens-details)。 <br>
✔️如果你想要使用 WDAC 阻止应用或进程启动，但还需要使用你自己的 bushiness 应用程序，你现在可以 [在你的 WDAC 策略中允许 LOB](#use-wdac-and-lob-apps)。

### <a name="moving-platform-mode"></a>移动平台模式

在 **内部版本 20348.1411** 中，我们添加了针对 HoloLens 2 上的低动态移动平台跟踪的测试支持。 安装生成并启用移动平台模式后，你将能够在以前无法访问的环境（如大型发货和大型海军船舶）中使用你的 HoloLens 2。 目前，该功能的目标是仅启用这些特定的移动平台。 虽然你可以随意地尝试在其他环境中使用该功能，但该功能首先侧重于增加对这些环境的支持。

若要详细了解受支持的功能以及如何启用此新功能，请 [访问移动平台页](hololens2-moving-platform.md)。

#### <a name="overview-to-try-out-moving-platform-mode"></a>尝试移动平台模式的概述

1. [启用开发人员模式和设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. [通过设备门户启用移动平台模式](hololens2-moving-platform.md#enabling-moving-platform-mode)。
1. 将你的设备带到你的大型移动平台，并观察稳定全息影像的方式。

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

在 Windows 有问必答版本20348.1405 中引入。 我们已向 [证书管理器添加了对证书管理器](certificate-manager.md) 的支持，以便现在使用 .pfx 证书。 当用户导航到 **设置**  >  **更新 & 安全**  >  **证书**，并选择 "**安装证书**" 时，UI 现在支持 .pfx 证书文件。
用户可以将包含私钥的 .pfx 证书导入到用户存储或计算机存储。

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>在证书管理器中试用 PFX 文件的概述

1. 准备 PFX 文件。
1. 通过 USB 电缆将文件复制到设备。
1. 打开设置应用，并导航到[证书管理器](certificate-manager.md)并应用证书。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>查看 HoloLens 上设置的高级诊断报告

对于托管设备，在对行为进行故障排除时，确认应用了预期的策略配置是一个重要的步骤。 以前，若要查看此信息，必须先通过 MDM 在设备上完成此信息，或在导出通过 **设置**  ->  **帐户**  >  **访问工作或学校** 收集的 MDM 诊断日志后，选择 "**导出管理日志** 并在附近的 PC 上查看"。

现在可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到 "访问" 工作或学校页面，然后选择 " **查看高级诊断报告**"。 这会在新的边缘窗口中生成并打开报表。

![在设置应用中查看高级诊断报告。](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>试用高级诊断报告的概述

1. 打开设置应用。
1. 导航到"帐户"页，然后单击新链接"**导出管理日志"。**
1. 查看有关设备配置的高级信息。

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

这是对名为"脱机诊断" [的现有功能的更新](hololens-diagnostic-logs.md#offline-diagnostics)。 以前，没有向用户明确指示他们已触发诊断收集或已完成。
现在，Windows预览体验内部版本中添加了两种形式的脱机诊断反馈。 第一种是，在收集开始和完成时为两者显示 toast 通知。 当用户登录且具有视觉对象时，将显示这些对象。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![日志收集完成后的 Toast。](./images/logcollection2.jpg)

由于用户通常使用脱机诊断作为回退日志收集机制，用于当用户无法访问显示器、无法登录或仍在 OOBE 中时，收集日志时也会播放音频提示。 除了 toast 通知之外，还将播放此声音。

此新功能将在设备更新时启用，无需启用或管理。 如果无法显示或听到此新反馈，仍将生成脱机诊断。

我们希望通过这种新添加的 feedback 反馈，可以更轻松地收集诊断数据，并更快排查问题。

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>试用诊断通知的概述

1. 解锁设备并安装设备。
1. 按"**电源"****和"音量** 降低"按钮组合以收集 [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 查看 toast 通知，并听到设备何时启动和完成日志收集的音频提示。

### <a name="low-storage-log-collection-improvements"></a>低存储日志收集改进

在收集诊断日志时，设备似乎磁盘空间不足的情况下，将创建名为 **StorageDiagnostics.zip报表。** 低存储阈值由存储感知自动Windows[确定](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>试用低存储改进的概述

1. 填充设备的存储空间。
1. 按"**电源"****和"音量** 降低"按钮组合以收集 [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 请注意，存储在数据库的 Documents 文件夹中的日志集合中HoloLens。

### <a name="csp-changes-for-reporting-hololens-details"></a>用于报告详细信息的 CSP HoloLens更改

- 预览体验Windows内部版本 20348.1403 中引入

以下 CSP 已更新为以新方式从设备HoloLens信息。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 免费存储

DevDetail CSP 现在还报告设备上HoloLens存储空间。 这大约应该与应用设置页中显示的存储匹配。 下面是包含此信息的特定节点。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作) 

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID 和 BSSID

DeviceStatus CSP 现在还报告主动Wi-Fi连接的 HoloLens SSID 和 BSSID。 下面是包含此信息的特定节点。

- 适配器 /SSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* 地址Wi-Fi /SSID
- 适配器 /BSSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac Wi-Fi *地址*

用于 MDM 供应商 (NetworkIdentifiers) 的 syncml blob 示例

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

### <a name="auto-login-policy-controlled-by-csp"></a>CSP 控制的自动登录策略

此新的 AutoLogonUser 策略控制用户是否将自动登录。 某些客户想要设置与标识绑定的设备，但不希望任何登录体验。 Imagine设备并立即使用远程协助。 或者，能够快速分发设备HoloLens最终用户加快登录。

当策略设置为非空值时，它指定自动登录用户的电子邮件地址。 指定的用户必须至少登录到设备一次才能启用自动登录。

新策略字符串值的 OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同一电子邮件地址的用户将启用自动登录。

在配置了此策略的设备上，策略中指定的用户至少需要登录一次。 第一次登录后设备的后续重启会自动登录指定的用户。 仅支持单个自动登录用户。 启用后，自动登录的用户将无法手动注销。 若要以其他用户登录，必须先禁用策略。

> [!NOTE]
>
> - 某些事件（例如主要 OS 更新）可能需要指定用户再次登录到设备，以恢复自动登录行为。
> - 仅 MSA 和 AAD 用户支持自动登录。

#### <a name="overview-to-try-auto-logon-csp"></a>尝试自动登录 CSP 的概述

1. 使用自定义策略将新的 CSP [配置为所需的用户](/mem/intune/configuration/custom-settings-windows-10) ： `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. 通过预配包或 MDM [将](hololens-provisioning.md) CSP 应用到 [设备](hololens-mdm-configure.md)。
1. 登录到指定的帐户。
1. 重启设备并观察用户是否自动登录。

### <a name="improved-update-restart-detection-and-notifications"></a>改进了更新重启检测和通知

在活动小时数和安装时间策略之间，可以避免在设备HoloLens重启设备。 但是，如果没有重启来完成所需更新的安装，则也会延迟更新的采用。 我们现在添加了策略，使 IT 能够强制实施截止时间并需要重启，并确保及时完成更新的安装。 可以在启动重新启动之前通知用户，他们可能会根据 IT 策略延迟重新启动。

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

#### <a name="overview-to-try-new-update-notifications"></a>尝试新更新通知的概述

1. 通过预配包或 MDM 服务配置其中[](hololens-provisioning.md)一个新的更新[ (](hololens-mdm-configure.md)请参阅上面的链接列表，并选取一) 。
1. 在计划的时间使用设备。
1. 观察用户收到有关更新的通知，以及需要重启设备 \* 。

\* 结果可能会因所使用的更新策略而异。

### <a name="smart-retry-for-app-updates"></a>应用更新的智能重试

现在为 HoloLens 是一个新策略，它允许 IT 管理员设置定期或一次性日期来重启由于应用使用而更新失败的应用，从而允许应用更新。 可以基于一些不同的触发器（例如计划时间或登录）来设置这些触发器。 若要详细了解如何使用此策略视图[ApplicationManagement/ScheduleForceRestartForUpdateFailures。](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>有关尝试应用更新的智能重试的概述

1. 配置新的智能重试功能。
1. 在尚未收到应用且配置正确的设备上，在联机环境中登录。
1. 使设备无法通过将其关闭或断开连接来下载应用。
1. 在触发的时间让设备打开并连接到 Internet，以重试下载。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅将专用应用商店应用用于Microsoft Store

已启用 RequirePrivateStoreOnly 策略HoloLens。 此策略Microsoft Store应用配置为仅显示通过 适用于企业的 Microsoft Store 为组织[配置的专用适用于企业的 Microsoft Store。](/microsoft-store/microsoft-store-for-business-overview) 仅限制对可用应用的访问。

详细了解 [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)。

#### <a name="overview-to-try-only-private-store-apps"></a>概述：仅尝试专用应用商店应用

1. 通过 MDM 为设备配置新 [策略](hololens-mdm-configure.md)。
1. 登录到具有策略的设备。
1. 打开Microsoft Store应用，观察你只能看到组织的应用。

### <a name="use-wdac-and-lob-apps"></a>使用 WDAC 和 LOB 应用

现在，可以使用 WDAC 阻止应用或进程启动，并继续使用自己的一系列粘性应用。 现在可以在 WDAC 策略中允许它们。 使用此策略涉及在创建 WDAC 策略时在 PowerShell 中运行额外的代码行。 [查看此处的步骤](/mem/intune/configuration/custom-profile-hololens)。

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>使用 WDAC 阻止其他应用时试用自己的应用的概述

1. 收集 LOB 应用的 AUMID 以及要阻止的应用。
1. [按照新步骤创建新的 WDAC](/mem/intune/configuration/custom-profile-hololens) 策略。
1. [使用 MDM 将策略](hololens-mdm-configure.md) 部署到设备。
1. 登录到设备并观察可以启动应用并阻止其他人。

### <a name="fixes-and-improvements"></a>修复和改进

- 修复 [了在未提示设备门户锁定文件 时出现的文件的已知问题](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)。
- 修复了 [文件上传设备门户下载的已知问题](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)。
- 解决有关从设备报告符合性HoloLens的问题;可能需要重新启动才能在预览体验内部版本上触发正确的报告。  
- 已启用[分配的访问 API，](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)以便应用现在可以确定HoloLens登录用户的展台模式是否正在运行HoloLens。
- 更新了全新闪存Remote Assist的现用版本。
- 预览体验成员内部版本已禁用 2D 应用的游戏板处理。 删除它后，应用现在可以直接使用 Gamepad API，并可以访问整个控件集，并按其需要执行任何操作。 开发人员应该使用 Gamepad API 来使用游戏板输入。 下面是[Gamepad 类示例 (Windows。Gaming.Input) - Windows UWP 应用程序](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)。
- 修复了使用基于 AAD 组的展台配置的情况下，首次用户登录后终止 OOBE 的问题。
- 更正了有关显示设备重启更新通知和对话框提示的问题。

## <a name="start-receiving-insider-builds"></a>开始接收预览体验内部版本

> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新生成。
>
> - "重新启动设备"语音命令运行良好。
> - 还可以选择"重启"按钮设置/Windows 会员计划。
>
> 我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。

在 HoloLens 2设备上，**转到"设置**  >  **更新&"Windows 会员计划"**  >  **开始"。** 链接用于注册为预览体验成员Windows帐户。

> [!NOTE]
> 若要在预览体验成员内部版本中注册设备，需要启用可选遥测。 如果尚未这样做，请打开 设置 应用，选择"隐私诊断&  ->  **反馈"，然后选择"** 可选 **诊断数据"。**

Windows预览体验成员现在迁移到频道。 快速 **通道** 将成为 **开发通道**，慢速通道将成为Beta 版频道通道，而发布预览通道将成为 **发布预览通道**。  该映射如下所示：

![WindowsInsider Channels 说明。](images/WindowsInsiderChannels.png)

有关详细信息，请参阅博客[上的预览Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。
然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 
选择 **">立即重启** "以完成操作。 重启设备后，转到"更新设置 >"&**安全性>检查更新** 以获取最新生成。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题

如果在 Dev 或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期方法。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。

#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版

1. 设置"更新&安全性"，Windows 会员计划，选择"发布 **预览通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。 更新后，继续进入阶段 2。

#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道

1. 设置"更新&安全性"，Windows 会员计划，选择"**开发通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。

1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 从 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。

1. 在HoloLens - 航班解锁 **：打开** 设置  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens提供反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。  请查看开发人员[HoloLens文档](https://developer.microsoft.com/windows/mixed-reality/development)开始。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手恢复设备[](hololens-recovery.md)，将设备恢复到 Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 中取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产生成：

1. 转到 **"设置 >系统>关于**"，并找到生成号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

选择退出预览体验内部版本：

1. 在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**

1. 按照说明选择退出设备。
