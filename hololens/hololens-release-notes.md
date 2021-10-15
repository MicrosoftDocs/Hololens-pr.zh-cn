---
title: HoloLens 2 发行说明
description: 随时了解每个新版本中HoloLens 2更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3f5e5f3e38c24805935fc69dfacd5eac93ddd017
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034274"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

为了确保你拥有高效体验，HoloLens设备，我们将继续发布功能、bug 和安全更新。 在此页上，可以看到每月HoloLens新增功能。 若要获取最新的HoloLens 2更新，可以检查更新并手动更新，[](hololens-update-hololens.md#check-for-updates-and-manually-update)或获取完整闪存更新 (FFU) 通过高级恢复助手 来刷用[设备](hololens-recovery.md#clean-reflash-the-device)。 [下载](https://aka.ms/hololens2download)会保持最新，并提供最新的已发布版本。

> [!NOTE]
> 最近的 Windows 11 公告侧重于 PC 版本的 Windows。 我们最近于[2021 年 10](#windows-holographic-version-21h2)月推出了HoloLens 2 OS 更新，我们正在根据客户反馈研究更多即将发布的版本。

## <a name="windows-holographic-version-21h2"></a>Windows全息版 21H2

- 内部版本 20348.1432

Windows全息版 21H2 现已发布，为用户和 IT 专业人员HoloLens 2一系列新功能。 本文介绍改进的故障排除和设备报告、展台模式下的一些修复 bug 和证书查看器、扩展的可管理性图面以及更新可靠性的提升。 即将发布此功能更新的一项新功能HoloLens移动平台模式。 查看所有新的出色的功能，HoloLens 2！

此最新版本是版本 21H1 的每月更新，但这次我们将包含新功能，因此主要内部版本号将保持不变，Windows 更新将指示每月发布版本 21H1 (内部版本 20348) 。 HoloLens 2设置仍将显示 21H1，即使我们将此版本引用为 21H2。 若要确保已收到 21H2，请验证版本号为 20348.1432 或更高版本。 可以在"关于"屏幕中查看设置 >号，以确认你使用最新的可用内部版本 20348.1432+。

若要更新到最新版本，请打开 设置 应用，转到"更新&安全性"，然后点击"检查更新"。 若要详细了解如何管理更新HoloLens，请访问[管理HoloLens更新。](hololens-updates.md)

| 功能                 | 说明                | 用户或方案 |
|-------------------------|----------------------------|--------------|
| [移动平台模式](#moving-platform-mode) | 引入了移动平台模式 beta 版本，在配置后，HoloLens 2遇到低动态运动的大型水陆船上使用移动平台模式。 | 全部 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过自定义 UI 添加 PFX 设置证书 | 最终用户 |
| [在诊断中查看设置诊断HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上 MDM 诊断日志 | 故障排除 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的省/市/服务反馈 | 故障排除 |
| [低存储日志收集改进](#low-storage-log-collection-improvements) | 改进了低存储情况下的日志收集方案。 | 故障排除 |
| [针对报表和详细信息的 CSP HoloLens更改](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 CSP | IT 管理员    |
| [CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 |
| [改进了更新重启检测和通知](#improved-update-restart-detection-and-notifications) | 新的已启用策略和用于更新的 UX。 | IT 管理员 |
| [应用更新的智能重试](#smart-retry-for-app-updates) | 允许 IT 管理员计划重试以更新应用。 | IT 管理员 |
| [仅将专用应用商店应用用于Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示来自组织的应用 | IT 管理员 |
| [使用 WDAC 和 LOB 应用](#use-wdac-and-lob-apps) | 允许 IT 管理员使用自己的应用，但仍使用 WDAC 阻止其他应用。 | IT 管理员 |
| [修复和改进](#fixes-and-improvements) | 修复和改进了 HoloLens。 | 全部 |

### <a name="it-admin-feature-checklist"></a>IT 管理员功能清单

✔️如果要将单个 Azure AD 帐户设置为自动登录，请[配置此新 CSP。](#auto-login-policy-controlled-by-csp) <br>
✔️如果要将应用配置为在更新失败后自动尝试更新，请设置此 [新的 CSP 进行智能重试。](#smart-retry-for-app-updates) <br>
✔️若要对 OS 更新进行更多控制，请查看这些新 [启用的更新策略。](#improved-update-restart-detection-and-notifications) <br>
✔️如果需要通过 Microsoft Store 在公司应用商店中提供组织的应用，但只想允许访问组织的应用，而不允许访问整个应用商店，请设置[此策略。](#use-only-private-store-apps-for-microsoft-store) <br>
✔️若要了解设备可用存储空间、SSID 或 BSSID HoloLens请查看这些报表[IP。](#csp-changes-for-reporting-hololens-details) <br>
✔️如果要使用 WDAC 来阻止应用或进程启动，但还需要使用自己的一系列粘性应用，现在可以在 WDAC 策略 中允许[LOB。](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>移动平台模式

自[Windows Holographic 版本 21H2](hololens-release-notes.md#windows-holographic-version-21h2)起，我们添加了 beta 版本支持，用于跟踪 HoloLens 2 上的低动态运动移动平台。 安装生成并启用移动平台模式后，你将能够使用以前无法访问HoloLens 2环境（如大型飞船和大型水陆船）中的设备。 目前，该功能的目标是仅启用这些特定的移动平台。 虽然你可以随意地尝试在其他环境中使用该功能，但该功能首先侧重于增加对这些环境的支持。

若要详细了解支持的功能以及如何启用此新功能， [请访问移动平台页](hololens2-moving-platform.md)。

#### <a name="overview-to-try-out-moving-platform-mode"></a>试用移动平台模式概述

1. [启用开发人员模式和设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. [通过设备门户 启用移动平台模式](hololens2-moving-platform.md#enabling-moving-platform-mode)。
1. 将设备移动到大型移动平台，并观察全息影像有多稳定。

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

预览体验Windows内部版本 20348.1405 中引入。 我们已向证书管理器添加了 [支持](certificate-manager.md) ，现在使用 .pfx 证书。 当用户导航到 **"设置**  >  **更新&证书**  >  **"，** 然后选择"安装证书"时，UI 现在支持 .pfx 证书文件。
用户可以使用私钥将 .pfx 证书导入用户存储或计算机存储。

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>在证书管理器中试用 PFX 文件的概述

1. 准备 PFX 文件。
1. 通过 USB-C 电缆将文件复制到设备。
1. 打开设置应用，导航到证书[管理器](certificate-manager.md)并应用证书。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在诊断中查看设置诊断HoloLens

对于排查行为问题时的托管设备，确认应用了预期的策略配置是一个重要步骤。 以前，若要使用这项新功能，在导出通过 **设置** 帐户访问工作或学校收集的 MDM 诊断日志后，必须将其通过 MDM 在设备外或附近完成，然后选择"导出管理日志"，并查看附近的  ->    >  电脑。

现在，可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到"访问工作或学校"页，然后选择"**查看高级诊断报告"。** 这会在新的 Edge 窗口中生成并打开报表。

![在应用内查看设置报告。](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>试用高级诊断报告的概述

1. 打开设置应用。
1. 导航到"帐户"页，然后单击新链接"**导出管理日志"。**
1. 查看有关设备配置的高级信息。

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

这是对名为"脱机诊断" [的现有功能的更新](hololens-diagnostic-logs.md#offline-diagnostics)。 以前，没有向用户明确指示他们已触发诊断收集或已完成。
现已添加到[Windows 全息版 21H2](hololens-release-notes.md#windows-holographic-version-21h2)中，这两种形式的视听反馈用于脱机诊断。 当收集开始和完成时，将显示第一个 toast 通知。 当用户登录并具有视觉对象时，将显示这些用户。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![记录收集完成时 Toast。](./images/logcollection2.jpg)

由于用户经常会使用脱机诊断作为回退日志收集机制来访问显示器、无法登录或仍处于 OOBE 状态，因此在收集日志时也会播放音频提示。 除了 toast 通知外，还会播放此声音。

这项新功能将在设备更新时启用，不需要启用或管理。 如果无法显示或听不到此新反馈，则仍将生成脱机诊断。

我们希望这种新的视听反馈增加，更易于收集诊断数据，并能更快地解决问题。

稍后可以在 " [诊断日志" 页](hololens-diagnostic-logs.md#offline-diagnostics)查看此信息。

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>试用诊断通知概述

1. 解锁设备并磨损设备。
1. 按下 **电源** 和 **音量** 按钮组合，收集 [离线诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 查看 toast 通知，并在设备启动和完成收集日志时倾听音频提示。

### <a name="low-storage-log-collection-improvements"></a>低存储日志收集改进

如果收集诊断日志时，设备的磁盘空间似乎不足，则将创建一个名为 **StorageDiagnostics.zip** 的附加报表。 Windows[存储感知](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)会自动确定低存储的阈值。

稍后可以在 " [诊断日志" 页](hololens-diagnostic-logs.md#offline-diagnostics)查看此信息。

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>试用低存储改进的概述

1. 填写设备的存储空间。
1. 按下 **电源** 和 **音量** 按钮组合，收集 [离线诊断](hololens-diagnostic-logs.md#offline-diagnostics)。
1. 观察在您的 HoloLens 的 Documents 文件夹中存储的日志集合中是否有一个新的文件。

### <a name="csp-changes-for-reporting-hololens-details"></a>reporting HoloLens 详细信息的 CSP 更改

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

如果策略设置为非空值，则它指定自动登录用户的电子邮件地址。 指定的用户必须至少登录到该设备，才能启用自动登录。

新策略 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 字符串值的 oma-uri

- 具有相同电子邮件地址的用户将启用自动登录。

在配置了此策略的设备上，策略中指定的用户至少需要登录一次。 第一次登录后，随后的设备重新启动将使指定的用户自动登录。 仅支持单个自动登录用户。 启用后，自动登录的用户将不能手动注销。 若要以其他用户身份登录，则必须先禁用策略。

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

现在为 HoloLens 启用了新策略，该策略允许 IT 管理员设置定期或一次性日期，以重新启动由于正在使用的应用程序允许应用更新而导致更新失败的应用。 可以基于几个不同的触发器（如计划时间或登录）来设置这些设置。 若要了解有关如何使用此策略的详细信息，请参阅 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

稍后可在适用于 [企业的应用部署应用商店页](app-deploy-store-business.md)中找到此信息。

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>有关尝试应用更新的智能重试的概述

1. 配置新的智能重试功能。
1. 在尚未接收你的应用并正确配置为的设备上，登录联机环境。
1. 使设备无法通过关闭或断开连接来下载应用。
1. 你的设备已打开并已在触发时连接到 internet，因此无法重试下载。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅对 Microsoft Store 使用专用应用商店应用

已为 HoloLens 启用 RequirePrivateStoreOnly 策略。 此策略使 Microsoft Store 应用程序可以配置为仅显示通过[适用于企业的 Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)为组织配置的专用存储。 仅将访问权限限制为可用的应用。

了解有关[ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)的详细信息

稍后可在适用于 [企业的应用部署应用商店页](app-deploy-store-business.md)中找到此信息。

#### <a name="overview-to-try-only-private-store-apps"></a>概述以仅尝试专用应用商店应用

1. 通过 [MDM](hololens-mdm-configure.md)为你的设备配置新策略。
1. 登录到具有策略的设备。
1. 打开 Microsoft Store 应用并观察你只能看到你的组织的应用。

### <a name="use-wdac-and-lob-apps"></a>使用 WDAC 和 LOB 应用

你现在可以使用 WDAC 阻止应用或进程启动并继续使用你自己的 bushiness 应用程序。 你现在可以在 WDAC 策略中允许它们。 使用此策略涉及在创建 WDAC 策略时在 PowerShell 中运行额外的代码行。 [请查看此处的步骤。](/mem/intune/configuration/custom-profile-hololens)

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
- 已启用[分配的访问 API，](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)以便应用现在可以确定登录 HoloLens的用户是否正在展台模式下HoloLens。

#### <a name="for-enterprise"></a>对于Enterprise

- 解决有关从设备报告符合性HoloLens的问题;可能需要重新启动才能在预览体验内部版本上触发正确的报告。  
- 更新了全新闪存Remote Assist安装的版本。
- 修复了在首次用户登录后，在使用了基于组AAD配置的情况下终止 OOBE 的问题。
- 更正了有关显示设备重启更新通知和对话框提示的问题。
- 修复了在设备重启后，需要再次配对 xbox 控制器蓝牙 LE 外围设备才能连接的问题。
- 修复了视频编码器问题，该问题可能导致在通话期间短时间冻结Remote Assist视频。 Wi-Fi驱动程序和固件更改来解决"片段和伪造"Wi-Fi漏洞。
- Wi-Fi驱动程序和固件更改来解决"片段和伪造"Wi-Fi漏洞。
- 将移动平台模式 (MPM) 时，"向下"通过在短时间内平均测量力来估算。 当在移动平台模式下时，此值将替换真正的力。
- 修复了在 3DoF 模式下或跟踪丢失期间全息影像中的周期性活动。
- 解决影响较旧版本 21H1/21H2 版本更新的问题。

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows全息版 20H2 - 2021 年 10 月更新

- 内部版本 19041.1168

更新中的改进和修复：

- 此每月质量更新不包含任何值得注意的更改，我们建议你试用我们的最新内部版本，Windows全息版 21H2。

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows全息版 21H1 - 2021 年 9 月更新

- 内部版本 20348.1018

更新中的改进和修复：

- 修复了问题，解决了系统时间可能会意外跳转的问题。

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows全息版 20H2 - 2021 年 9 月更新

- 内部版本 19041.1165

更新中的改进和修复：

- 修复了问题，解决了系统时间可能会意外跳转的问题。

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows全息版 21H1 - 2021 年 8 月更新

- 内部版本 20348.1014

更新中的改进和修复：

- 修复了阻止 Xbox 控制器在具有控制器支持的沉浸式应用程序中工作的问题。
- 改进了设备更新失败的诊断。

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows全息版 20H2 - 2021 年 8 月更新

- 内部版本 19041.1161

更新中的改进和修复：

- 此每月质量更新不包含任何值得注意的更改，我们建议你试用我们的最新内部版本，Windows全息版 21H1。

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows全息版 21H1 - 2021 年 7 月更新

- 内部版本 20348.1010

更新中的改进和修复：

- 设备门户在打开锁定文件时遇到问题时文件资源管理器通知客户的增强方法。
- 现在，在所有受支持的浏览器中使用 https 时，文件上传、下载、重命名和删除已修复。
- 修复了Wi-Fi从 设置 > **Network & Internet** 启动 Wi-Fi 属性 UI 时无法保存 > 代理>的问题。
- 解决了跨 OS 更新删除 eSIM 证书的问题。 此修补程序可确保在更新到 21H1 版本时删除 eSIM 证书和相关组件。
- 更正了影响跨 OS 重置的预安装应用的问题。
- 电池充电性能经过优化，在增加 CPU 负载的情况下增加运行时。 在HoloLens 2时，如果检测到设备运行热，内部电池的充电速度会变慢，以减少热度。 正面的权衡是设备不太可能因热问题而关闭，其影响是设备运行时间更长。 如果设备运行冷，则费用费率不受影响。

> [!IMPORTANT]
> 由于[21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)版本中现在解决了影响 Remote Assist 用户的已知问题，我们暂时暂停了 Windows Holographic 版本 21H1 更新的提供。 我们还将默认的 Advanced Recovery Companion (ARC) 内部版本更改为[Windows Holographic 版本 20H2 – 2021 年 6 月更新](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)。 ARC 生成现在将恢复以 21H1 版本为目标。

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows全息版 20H2 - 2021 年 7 月更新

- 内部版本 19041.1157

更新中的改进和修复：

- 设备门户在打开锁定文件时遇到问题时文件资源管理器通知客户的增强方法。
- 现在，在所有受支持的浏览器中使用 https 时，文件上传、下载、重命名和删除已修复。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows全息版 21H1 - 2021 年 6 月更新

- 内部版本 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive或学校相机照片上传

我们向 HoloLens 2 设置 应用添加了一项新功能，使客户能够自动将混合现实照片和视频从设备的"图片">"相机滚动"文件夹上传到相应的"OneDrive"工作或学校文件夹。 此功能解决了 HoloLens 2 上[OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)应用中的功能差距，它仅支持自动将相机滚动上传到客户的个人Microsoft 帐户 (，而不允许其工作或学校帐户) 。

**工作原理**

- 请访问 **设置 > System > 混合现实相机** 启用"相机上传"。
- 将此功能设置为"打开"位置后，捕获到设备的任何混合现实照片或视频将自动排队，以上传到工作或学校帐户的 OneDrive 的 Pictures > Camera Roll 文件夹。
    >[!NOTE]
    >启用此功能之前捕获的照片和视频不会排队等待上传，并且仍然需要手动上传。
- 设置 页上的状态消息将显示所有挂起的文件已上传到 (或读取"OneDrive 是最新的"（所有挂起的文件已上传) ）。
- 如果担心带宽或出于任何原因想要"暂停"上传，可以将该功能切换到"关闭 **"** 位置。 暂时禁用该功能可确保在将新文件添加到 Camera Roll 文件夹时上传队列将继续增加，但在重新启用该功能之前，文件不会上传。
- 最新文件将首先上传 (最后一个，第一个上传) 。
- 例如，OneDrive帐户 (密码更改后 **) "立即** 修复"按钮会显示在设置页上。
- 没有最大文件大小，但请注意，上传大型文件 (尤其是当上传带宽受限时) 。 如果在上传大型文件时"暂停"或关闭上传，将保留部分上传。 如果在"暂停"或关闭后几个小时内重新启用上传，上传将继续从中断位置开始。 但是，如果在几个小时后重新启用上传，则大型文件的上传会从头开始重启。

**已知问题和注意事项**

- 此设置没有基于当前带宽使用情况的内置限制。 如果需要为其他方案最大化带宽，请手动关闭设置。 Upload将暂停，但该功能将继续监视新添加到相机照片的文件。 准备好继续上传后，请重新启用上传。
- 必须为设备上每个用户帐户启用此功能，并且只能主动上传当前已登录到设备的用户的文件。
- 如果在实时观看 设置 页上的上传计数时拍摄照片或视频，请注意，在当前文件完成上传之前，挂起的文件计数可能不会更改。
- Upload设备睡眠或关机时，设备将暂停。 若要确保挂起的上传完成，请主动使用设备，直到 设置 页显示为"OneDrive"或调整 **Power & 睡眠设置**。

### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

现在支持以下遥测策略HoloLens 2：

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 都应该一起使用，以便对设置应用程序中的遥测和行为具有完全控制。

更新中的改进和修复：

- 修复了颜色校准导致的重大视频损坏。
- 解决了 "电源" 菜单中的文本可能被截断的问题。
- 支持 RequirePrivateStoreOnly 策略。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows版本20H2 –2021年6月更新

- 生成19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

HoloLens 2 上现在支持以下遥测策略：

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 都应该一起使用，以便对设置应用程序中的遥测和行为具有完全控制。

建议试用21H1 的最新版本，Windows 全息版。

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows全息版，版本 1903-2021 更新

- 生成18362.1116

更新中的改进和修复：

- 这一月度质量更新不包含任何显著的更改，我们建议你试用最新的版本，Windows 全息版21H1。

>[!IMPORTANT]
> 此生成将不再提供服务。

## <a name="windows-holographic-version-21h1"></a>Windows全息版21H1

- 生成20346.1002

此更新包含两个目标受众的功能;最终用户可以在设备上使用的所有功能，以及可由 IT 管理员配置的新设备管理选项。 下表指定了与每个受众相关的功能。 如果你是 IT 管理员，请查看我们的 [It 管理员更新清单](#it-admin---update-checklist)。
>[!IMPORTANT]
>若要更新到此生成，HoloLens 2 设备 (s) 必须当前正在运行2021年2月更新 (版本 19041.1136) 或更高版本。 如果未看到此功能更新可用，请先更新设备，然后重试。

>[!NOTE]
>目前，Microsoft HoloLens 2 支持以下版本的每月服务更新 (bug 和安全修补程序) ：
>
>- Windows全息版 20H2 (生成 19041.1128 +) 
>- Windows全息版 2004 (生成 19041.1103 +) 
>- Windows全息版 1903 (生成 18362 +) 
>
> 引入 Windows 全息版 21H1 **后，我们将为 Windows 全息版1903的每月服务更新停止**。 这使我们能够将重点放在最新版本上，并继续提供有价值的改进。

| 功能名称                                              | 简短说明                                                                      | 目标读者 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2。 | 最终用户 |
[WebXR 和 360 Viewer](#webxr-and-360-viewer) | 尝试沉浸式 web 体验和360视频播放。 | 最终用户 |
[新“设置”应用](#new-settings-app) | 旧的设置应用将被更新版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为 HoloLens 2 屏幕选择替代颜色配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应为每个文件或链接类型启动的应用。 | 最终用户 |
[每个应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 Web 应用](#install-web-apps) | 用新的 Microsoft Edge 浏览器在 HoloLens 2 上安装 web 应用，如 Microsoft Office。 | 最终用户 |
[轻扫以键入](#swipe-to-type) | 使用手指的笔尖在全息键盘上 "轻扫" 单词。 | 最终用户 |
[“开始”中的 Power 菜单](#power-menu-from-start) | 在 "开始" 菜单上，重新启动并关闭 HoloLens 设备 "。 | 最终用户 |
[登录屏幕上列出了多个用户](#multiple-users-listed-on-sign-in-screen) | 在登录屏幕上显示多个用户帐户。 | 最终用户 |
[USB-C 外置麦克风支持](#usb-c-external-microphone-support) | 为应用和/或远程协助使用 USB-C 麦克风。 | 最终用户 |
[网亭的访问者自动登录](#visitor-auto-logon-for-kiosks) | 启用对访问者帐户的自动登录以用于展台模式。 | IT 管理员 |
[展台模式下新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 用于新设置和边缘应用的 AUMIDs。 | IT 管理员 |
[改善了展台模式故障处理](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空 "开始" 菜单之前查找全局分配的访问权限。 | IT 管理员 |
[新的 SettingsURIs for Page 设置 Visibility](#new-settings-uris-for-page-settings-visibility) | 20多个新的 SettingsURIs 设置/PageVisibilityList 策略。 | IT 管理员 |
[配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在设置应用程序中设置回退诊断行为。 | IT 管理员 |
[与附近设备共享东西](#share-things-with-nearby-devices) | 将 HoloLens 中的文件或 url 共享到 PC。 | 全部 |
[新操作系统诊断跟踪](#new-os-diagnostic-traces) | 针对 OS 更新设置的新疑难解答。 | IT 管理员 |
[传递优化预览版](#delivery-optimization-preview) | 减少从多个 HoloLens 设备下载的带宽消耗。 | IT 管理员 |

查看相关发行说明：

- [访问 HoloLens Emulator 存档](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新版 Microsoft Edge 简介

![旧版 Microsoft Edge 徽标动画升级为新版 Microsoft Edge 徽标动画。](images/new-edge.gif)

新版 Microsoft Edge [采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)，为客户提供更好的兼容性，同时为 Web 开发人员减少 Web 碎片。

> [!IMPORTANT]
> 新版 Microsoft Edge 会自动替换旧版 Microsoft Edge，新版本中[不再支持](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)旧版 Microsoft Edge。

![新版 Microsoft Edge 屏幕截图。](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新版 Microsoft Edge

新的 Microsoft Edge ![新版 Microsoft Edge 图标。](images/new_edge_logo.png) （由蓝绿色漩涡图标表示）固定在“开始”菜单上，并将在你激活 Web 链接时自动启动。

> [!NOTE]
> 首次在 HoloLens 2 上启动新版 Microsoft Edge 时，系统将从旧版 Microsoft Edge 导入你的设置和数据。 如果在启动新 Microsoft Edge 后继续使用旧的 Microsoft Edge，则不会将新数据从旧 Microsoft Edge 同步到新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>为新版 Microsoft Edge 配置策略设置

相较于旧版 Microsoft Edge，新版 Microsoft Edge 在 HoloLens 2 上为 IT 管理员提供了一套更广泛的浏览器策略。

下面是一些有用的资源，可用于了解有关管理新版 Microsoft Edge 策略设置的详细信息：

- [使用 Microsoft Intune 配置 Microsoft Edge 策略设置](/deployedge/configure-edge-with-intune)
- [Microsoft Edge 旧版到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge 企业版文档](/deployedge/)

> [!IMPORTANT]
> 由于新版 Microsoft Edge 支持的浏览器策略较多，我们的团队无法保证每个新策略都适用于 HoloLens 2。 但是我们已测试并已确认的是，新版 Microsoft Edge 在 HoloLens 2 上支持等效于以前在其上支持的每个旧版 Microsoft Edge 策略。 请参阅 [Microsoft Edge 旧版到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)，查找与用于 HoloLens 2 的每个旧版 Microsoft Edge 浏览器策略等效的新版 Microsoft Edge 策略。
>
> 我们知道至少有两个新版 Microsoft Edge 策略无法用于 HoloLens 2：
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>在 HoloLens 2 上应用新版 Microsoft Edge 有哪些好处

由于新版 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用程序，因此它可以在仅使用 UWP 的设备（如 HoloLens 2）上运行，某些功能可能还不能立即使用。 我们将在未来几个月内提供对新方案和功能的支持，敬请关注此板块的最新信息。

支持的场景和功能：

- 首次运行体验、登录到配置文件和同步
- 网站应呈现并按预期运行
- 大多数浏览器功能（收藏夹、历史记录等）都应按预期运行
- 深色模式
- 将 Web 应用安装到设备
- 安装扩展（如果使用的扩展在 HoloLens 2 上无法正常运行，请告知我们）
- 查看并标记 PDF
- 来自单个浏览器窗口的空间音效
- 自动和手动更新浏览器
- 从“打印”菜单保存 PDF（使用“保存到 PDF”选项）
- WebXR 和 360 Viewer 扩展
- 跨环境中的多个窗口浏览时，内容还原到正确的窗口

不支持的场景和功能：

- 带有同步音频流，来自多个窗口的空间音效
- “看到它，说出来”
- 打印

**最常见的浏览器已知问题：**

- 全息键盘中的放大镜预览在新版 Microsoft Edge 中被禁用。 我们希望等放大功能恢复正常后，在未来的更新中重新启用此功能。
- 如果有其他浏览器窗口打开并处于活动状态，则音频可能会从错误的浏览器窗口播放。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在 ["关注我" 模式下](hololens2-basic-usage.md#follow-me-stop-following)从浏览器窗口播放音频时，如果禁用 "关注我" 模式，则音频将继续播放。 可以通过在禁用 "关注我" 模式之前停止音频播放，或通过使用 **X** 按钮关闭窗口，来解决此问题。
- 与处于活动状态的 Microsoft Edge 窗口交互可能会导致其他 2D 应用程序窗口意外变为非活动状态。 可以通过再次与这些窗口交互重新将其激活。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

Microsoft Edge 团队为 Edge Insider 社区提供了三个预览渠道：Beta、Dev 和 Canary。 在 HoloLens 2 上安装预览渠道不会卸载已发布的 Microsoft Edge 版本，而且你可以同时安装多个渠道。

请访问 [Microsoft Edge Insider 主页](https://www.microsoftedgeinsider.com)，了解有关 Edge Insider 社区的详细信息。 若要详细了解不同的 Edge Insider 渠道并开始体验，请访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。

在 HoloLens 2 上安装 Microsoft Edge Insider Channels 有多种方法：

直接在设备上安装（当前仅适用于非托管设备）

  1. 在 HoloLens 2 上，访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 为想要安装的 Edge Insider 渠道选择“适用于 HoloLens 2 的下载”按钮。
  1. 从 Edge 下载队列或设备的“下载”文件夹（使用文件资源管理器）启动下载的 .msix 文件。
  1. 将启动[应用安装程序](app-deploy-app-installer.md)。
  1. 选择“安装”按钮。
  1. 安装成功后，你将在“开始”菜单的“所有应用”列表中找到以单独条目显示的 Beta、Dev 或 Canary。

**使用 Windows 设备门户通过电脑安装（需要在 HoloLens 2 上启用 [开发人员模式](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)）**

  1. 在你的电脑上，访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 为想要安装的 Edge Insider 渠道选择“适用于 Windows 10 的下载”旁的下拉箭头按钮。
  1. 在下拉菜单中选择“HoloLens 2”。
  1. 将 .msix 文件保存到电脑的“下载”文件夹（或便于你查找的其他文件夹）。
  1. 在电脑上使用 [Windows 设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)将下载的 .msix 文件安装到 HoloLens 2 上。
  1. 安装成功后，你将在“开始”菜单的“所有应用”列表中找到以单独条目显示的 Beta、Dev 或 Canary。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 阻止新版 Microsoft Edge

对于希望更新其 [WDAC 策略](windows-defender-application-control-wdac.md)以阻止新版 Microsoft Edge 应用的 IT 管理员，需要向策略添加以下内容。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新版 Microsoft Edge 的终结点

某些环境可能需要考虑网络限制。 为了确保在使用新版 Edge 时获得流畅的体验，请[启用这些 Microsoft 终结点。](/deployedge/microsoft-edge-security-endpoints)

阅读有关当前可用的 [HoloLens 终结点](hololens-offline.md)的详细信息。

### <a name="install-web-apps"></a>安装 Web 应用

 > [!Note]
>从 [Windows 全息版（版本 21H1）](hololens-release-notes.md#windows-holographic-version-21h1)开始，将不再预安装 Office Web 应用。

你可以使用新版 Edge 将 Web 应用与 Microsoft Store 应用一起安装。 例如，可以安装 Microsoft Office Web 应用来查看和编辑托管在 SharePoint 或 OneDrive 上的文件。 若要安装 Office Web 应用，请访问 https://www.office.com 并在地址栏中选择“可用应用”或“安装 Office”。 选择“安装”确认该操作。

> [!IMPORTANT]
> 仅当 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。

### <a name="webxr-and-360-viewer"></a>WebXR 和 360 Viewer

新版 Microsoft Edge 包含对 WebXR 的支持，这是创建沉浸式 Web 体验的新标准（替代 WebVR）。 许多沉浸式 Web 体验在设计时都考虑了 VR 应用场景（它们用虚拟环境来替代你的视野），但 HoloLens 2 也支持这些体验。 WebXR 标准还支持使用物理环境的增强和混合现实沉浸式 Web 体验。 随着 WebXR 在开发人员中的应用逐渐普及，我们预计未来将有新的增强和混合现实沉浸式体验供 HoloLens 2 客户尝试！

360 Viewer 扩展是在 WebXR 的基础之上构建的，它随新版 Microsoft Edge 一起自动安装在 HoloLens 2 上。 该网络扩展使你能够沉浸在 360 度视频中。 YouTube 上提供的 360 度视频选择范围最多，我们建议你从该平台开始体验。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 导航到支持 WebXR 的网站。
1. 选择网站上的“进入 VR”。 此按钮的位置和视觉表现形式可能因网站而异，但其外观可能类似于：

    ![“进入 VR”按钮示例。](images/75px-enter-vr.png)

1. 首次尝试在特定域上启动 WebXR 体验时，浏览器将询问你是否同意进入沉浸式视图，选择“允许”。
1. 使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame)来操作体验。
1. 如果在体验时没有“退出”按钮，请使用[开始手势](hololens2-basic-usage.md#start-gesture)返回主菜单。

建议的 WebXR 示例

- 360 Viewer（参阅下一部分）
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用 360 Viewer

1. 在 YouTube 上导航到 360 度视频。
1. 在视频帧中，选择“混合现实头戴显示设备”按钮：

    ![激活 360 Viewer 的按钮。](images/enter-360-viewer.jpg)

1. 首次尝试在特定域上启动 360 Viewer 时，浏览器将询问你是否同意进入沉浸式视图。 选择“允许”。
1. [隔空敲击](hololens2-basic-usage.md#select-using-air-tap)以打开播放控件。 使用[手部射线和隔空敲击](hololens2-basic-usage.md#select-using-air-tap)来播放/暂停、快进/后退、打开/关闭字幕或停止体验（该操作会退出沉浸式视图）。 播放控件将在保持几秒的非活动状态后消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR 和 360 Viewer 常见已知问题

- 根据 WebXR 体验的复杂度，帧速率可能下降或卡顿。
- 默认情况下，WebXR 中不支持铰接式手关节。 开发人员可以 `edge://flags` 通过打开 "WebXR 手型输入" 启用支持。
- YouTube 网站之外的 360 度视频可能无法按预期运行。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>提供关于 WebXR 和 360 Viewer 的反馈

请通过新版 Microsoft Edge 中的“发送反馈”功能与我们的团队分享反馈和错误。

### <a name="new-settings-app"></a>新“设置”应用

在此版本中，我们引入了新版本的设置应用。 新的“设置”应用包括 HoloLens 2 在以下领域的新功能和扩展设置：声音、电源和休眠、网络和 Internet、应用、帐户、轻松访问等。

> [!NOTE]
> 由于新的“设置”应用不同于旧版“设置”应用，因此，此前围绕环境放置的任何“设置”窗口都将在更新时删除。

![新“设置”应用主页。](images/new-settings-app.png)

**新功能和设置**

- 设置搜索：使用关键字或设置名称搜索“设置”主页中的设置。
- 系统> 声音：
  - 输入和输出音频设备：独立选择输入和输出音频设备（例如，通过蓝牙耳机侦听音频，或使用 USB-C 麦克风进行音频输入）。
    > [!NOTE]
    > HoloLens 2 不支持蓝牙麦克风。
  - 应用音量：独立调整每个应用的音量。 请参阅[每个应用的音量控制](#per-app-volume-control)。
- 系统 > 电源和休眠：如果希望设备在一段时间不活动后进入休眠状态时选择此选项。
- 系统 > 电池：手动启用节电模式或设置节电模式模式自动打开的电池阈值。
- 设备 > USB：默认禁用 USB 连接。
- 网络和 Internet：
  - USB-C 以太网适配器将出现在“网络和 Internet”中。
  - USB-C 以太网适配器设置现已可用，包括其 IP 地址。
  - 现在可以在 HoloLens 2 上启用飞行模式。
- 应用：可以重置用于文件和链接类型的默认应用。 有关详细信息，请参见[默认应用选取器](#default-app-picker)。
- 帐户 > 其他用户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。
- 轻松访问：更改文本大小和一些视觉效果。

**已知问题**

- 将删除之前放置的“设置”窗口（请参见上面的注释）。
- 无法再使用“设置”应用重命名设备。 IT 管理员可以使用[适用于 HoloLens 2 的 Windows Autopilot](hololens2-autopilot.md) 设备名称模板或 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点来重命名设备。
- “以太网”页随时显示一个虚拟以太网设备（“UsbNcm”）。
- 新 Microsoft Edge 的电池使用情况可能不准确，因为它是一个由 UWP 适配器层支持的 Win32 桌面应用程序（预计近期不会有任何修复）。

#### <a name="display-color-calibration"></a>显示颜色校准

使用此新设置，可以为 HoloLens 2 显示选择备用颜色配置文件。 这可以帮助显示更准确的颜色，尤其是在较低的屏幕亮度级别。 可以在 "系统 > 校准" 页上的 "设置应用" 中找到显示颜色校准。

> [!NOTE]
> 由于此设置将新的颜色配置文件保存到屏幕固件，因此它是每个设备的设置（并且对每个用户帐户不是唯一的）。

##### <a name="how-to-use-display-color-calibration"></a>如何使用显示颜色校准

1. 启动“设置”应用，导航到“系统”>“校准”。
1. 在“显示颜色校准”下，选择“运行显示颜色校准”按钮。
1. 将启动显示颜色校准体验，并建议你确保面罩的位置正确。
1. 在继续执行指令对话框后，屏幕将自动调暗到 30% 的亮度。
    > [!TIP]
    > 如果你在环境中看不清昏暗的场景，可以使用设备左侧的亮度按钮手动调整 HoloLens 2 的亮度级别。
1. 选择按钮 1-6 可立即尝试每个颜色配置文件，并找到最适合你的眼睛的颜色配置文件（这通常意味着可帮助最中性地显示场景的配置文件，并且灰度模式和肤色符合预期。）

    ![显示颜色校准场景。](images/color-cal-ui.png)

1. 当你对所选配置文件感到满意，选择“保存和退出”按钮
1. 如果你不想进行更改，请选择“取消并退出”按钮，更改将恢复

> [!TIP]
> 下面是使用显示颜色校准设置时需要注意的一些有用的提示：
>
> - 你可以根据需要在“设置”中重新运行显示颜色校准
> - 如果设备上的任何人以前使用了设置来更改颜色配置文件，则最近更改的日期/时间将反映在“设置”页面上
> - 重新运行显示颜色校准时，将突出显示以前保存的颜色配置文件，并且不会显示配置文件 0（因为配置文件 0 表示屏幕的原始颜色配置文件）
> - 如果要恢复到屏幕的原始颜色配置文件，可从“设置”页面执行此查找（参阅[如何重置颜色配置文件](#how-to-reset-color-profile)）

##### <a name="how-to-reset-color-profile"></a>如何重置颜色配置文件

如果你对保存到 HoloLens 2 中的自定义颜色配置文件不满意，则可以还原设备的原始颜色配置文件：

1. 启动“设置”应用，导航到“系统”>“校准”。
1. 在“显示颜色校准”下，选择“重置为默认颜色配置文件”按钮。
1. 当对话框打开时，如果已准备好重新启动 HoloLens 2 并应用所做的更改，请选择“重新启动”。

#### <a name="top-display-color-calibration-known-issues"></a>顶部显示颜色校准已知问题

- 在 "设置" 页上，通知您上次更改颜色配置文件的状态字符串将过期，直到您重新加载设置的该页面为止。
    - 解决方法：选择另一个“设置”页面，然后重新选择“校准”页面。

#### <a name="default-app-picker"></a>默认应用选取器

当你激活超链接或打开具有多个已安装的应用程序的文件类型（该应用程序支持该类型）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用程序应处理文件或链接类型。 在该窗口中，还可以选择选定的应用“一次”或“始终”处理文件或链接类型。

如果选择“始终”，但以后想要更改处理特定文件或链接类型的应用，可以在“设置”>“应用”中重置设置默认值。 滚动到页面底部，然后选择“文件类型的默认应用”和/或“链接类型的默认应用”下的“清除”按钮。 与台式电脑类似设置不同的是，无法重置单个文件类型默认值。

#### <a name="per-app-volume-control"></a>每个应用音量控制

现在，在此 Windows 生成中，用户可以手动调整每个应用的音量级别。 这样，用户可以更好地关注他们所需要的应用，或者在使用多个应用时能更清晰地听到。 例如，在呼叫另一个人寻求远程帮助时降低其中一个应用的音量。

若要设置单个应用的音量，请导航到“设置” > “系统” > “声音”，然后在“高级”声音选项中选择“应用音量和设备首选项”。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>轻扫以键入

有些客户通过轻扫要键入的单词的形状，来更快地在虚拟键盘上 "键入"，并且我们正在为全息键盘预览此功能。 您可以通过在全息键盘的平面上传递手指的笔尖，刷一字的形状，然后从键盘飞机取出手指的笔尖，一次轻扫一个词。 通过在键盘上删除单词之间的手指，无需按删除键就可以轻扫后面的单词。 如果在键盘上看到轻扫轨迹按照手指移动，你将知道该功能正在运作。

请注意，由于全息键盘的性质，如果不能感觉到手指的阻力（不像手机显示一样），该功能使用和掌握起来可能比较麻烦。 

### <a name="power-menu-from-start"></a>“开始”中的 Power 菜单

通过新菜单，用户可以注销、关闭和重启设备。 HoloLens“开始”屏幕中的指示器显示系统更新何时可用。

#### <a name="how-to-use"></a>如何使用

1. 使用[“开始”手势](hololens2-basic-usage.md#start-gesture)或说出“转到开始”来打开 HoloLens“开始”屏幕。

2. 请注意用户个人资料图片旁边的省略号图标 (...)：<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用手或语音命令“Power”选择用户个人资料图片。

4. 将显示包含“注销”、“重启”或“关闭”设备选项的菜单：<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 选择菜单选项以注销、重启或关闭 HoloLens。 如果将设备设置为[单个 Microsoft 帐户 (MSA) 或本地帐户](hololens-identity.md)，“注销”选项可能不可用。

6. 通过触摸其他任意位置或关闭具有“开始”手势的“开始”菜单来关闭菜单。

#### <a name="update-indicator"></a>更新指示器

当更新可用时，省略号图标将亮起，指示重启将安装更新 菜单选项也会更改以反映更新的存在。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出的多个用户

以前，"登录"屏幕只显示最近登录的用户，以及"其他用户"入口点。 我们已收到客户反馈，如果多个用户已登录到设备，这是不够的。 他们仍然需要重新键入其用户名等。

本Windows中引入，在选择"PIN 输入"字段右侧"其他用户"时，"登录"屏幕将显示以前已登录到设备的多个用户。 这允许用户选择其用户配置文件，然后使用其凭据Windows Hello登录。 还可通过"添加帐户"按钮从此"其他用户"页将新 **用户添加到** 设备。

在"其他用户"菜单中，"其他用户"按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的"登录"屏幕。

![默认登录屏幕。](./images/multiusers1.jpg)

<br>

![其他用户的登录屏幕。](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外置麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens OS 将内部麦克风阵列的优先级设置为高于任何其他输入设备。 若要使用 USB-C 麦克风，请执行以下步骤。

用户可以使用“声音”设置面板选择 USB-C 连接的外置麦克风。 USB-C 麦克风可用于呼叫、录制等。

打开“设置”应用并选择“系统” > “声音”。

![声音设置。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外置麦克风用于 Remote Assist，用户需要单击“管理声音设备”超链接。
>
> 然后，使用下拉菜单将外置麦克风设置为“默认值”或“通信默认值”。 选择“默认值”表示将在任何位置使用外置麦克风。
>
> 选择“通信默认值”表示将在 Remote Assist 和其他通信应用中使用外置麦克风，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备。](images/usbc-mic-2.png)

<br>

![设置麦克风默认值。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>蓝牙麦克风支持怎么样？

遗憾的是，蓝牙目前仍不支持麦克风HoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风错误地将自身报告为 *麦克风和扬声器* 。 这是麦克风的问题，而不是麦克风HoloLens。 将其中一个麦克风插入 HoloLens时，可能会丢失声音。 幸运的是，有一个简单的修复方法。  

在 **设置** System Sound 中，将"模拟功能音频驱动程序" (将内置扬声器) 设置为  >    >  **"默认设备"。** HoloLens，即使稍后删除了麦克风并重新连接，也应记住此设置。

![USB-C 麦克风疑难解答。](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>展台的访问者自动登录

此新功能使访问者帐户能够自动登录，以用于展台模式。

对于非AAD配置，若要为访问者自动登录配置设备：

1. 创建一个预配包，该包：
    1. 配置 **运行时设置/AssignedAccess** 以允许访问者帐户。
    1. （可选）将设备注册到 MDM (**运行时设置/工作区/** 注册) 以便以后可以管理该设备。
    1. 不创建本地帐户
1. [应用预配包](hololens-provisioning.md)。

对于AAD配置，用户无需进行此更改即可实现与现在类似的功能。 AAD为展台模式配置的已加入设备可以通过登录屏幕中的单个按钮点击来登录访问者帐户。 登录到访问者帐户后，在从开始菜单显式注销访问者或重启设备之前，设备不会再次提示登录。

可以通过自定义 [OMA-URI](/mem/intune/configuration/custom-settings-windows-10) 策略管理访问者自动登录：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 策略  | 描述   | 配置  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允许访问者自动登录到展台   | 1 (是) ，0 (否，默认值.)   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在展台设置使用新的应用和 Edge 应用

在展台 [中](hololens-kiosk.md)包括应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。 由于 设置 应用和 Microsoft Edge 应用都被视为新应用，并且不同于使用这些应用的 AUMID 的较旧应用展台，因此需要更新这些应用，以使用新的 AUMID。

修改展台以包含新应用时，建议在新的 AUMID 中添加 ，并保留旧应用。 当用户更新 OS 且无需接收新策略以继续使用展台时，这将创建一个简单的转换。

| 应用                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 旧 设置 应用       | HolographicSystemSettings_cw5n1h2txyewy！应用程序            |
| 新建设置应用       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用程序 |
| 旧 Microsoft Edge 应用 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新Microsoft Edge应用 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>展台模式行为更改，用于处理故障

在较旧的生成中，如果设备具有展台配置（这是全局分配的访问权限和 AAD 组成员分配的访问权限的组合）时，如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中未显示任何内容[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)。

从此版本Windows开始，展台体验将回退到全局展台配置 (如果) 组展台模式期间发生故障，AAD展台配置。

### <a name="new-settings-uris-for-page-settings-visibility"></a>页面设置可见性的新 设置 URI

在 Windows Holographic 版本[20H2](hololens-release-notes.md#windows-holographic-version-20h2)中，我们添加了[设置/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)策略，以限制在 设置 应用中看到的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

如果访问["页面设置](settings-uri-list.md)可见性"，可以找到有关使用此 CSP 的说明，以及以前版本中提供的 URI 列表。

我们正在扩展 IT 管理员可以管理的 设置 URI 列表。 其中一些 URI 适用于新应用的新设置区域。 如果使用的是 设置/PageVisibilityList 策略，请查看以下列表，并根据需要调整允许或阻止的页面。

> [!NOTE]
> **已弃用：ms-settings：network-proxy**
>
> 在这些较新的生成中，一个设置页已弃用。 旧的 **"& Internet**  >  **代理"** 页不再作为全局设置提供。 可以在"网络""Internet Wi-Fi 属性"或"Internet 以太网&"下找到  >    >  **新的&**  >  **设置**  >  。

<br>

| “设置”页面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 应用>应用&功能                               | `ms-settings:appsfeatures`                         |
| 应用>应用&高级>功能          | `ms-settings:appsfeatures-app`                     |
| 脱机>应用                                  | `ms-settings:maps`                                 |
| 脱机>应用>下载地图                  | `ms-settings:maps-downloadmaps`                    |
| 设备 > 鼠标                                      | `ms-settings:mouse`                                |
| 设备 > USB                                        | `ms-settings:usb`                                  |
| 网络 & Internet > 飞行模式                   | `ms-settings:network-airplanemode`                 |
| 隐私 > 常规                                    | `ms-settings:privacy-general`                      |
| 隐私 > 墨迹 & 键入个性化             | `ms-settings:privacy-speechtyping`                 |
| 隐私 > 动作                                     | `ms-settings:privacy-motion`                       |
| 隐私 > 屏幕快照边框                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 隐私 > 屏幕截图和应用                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系统 > 电池                                     | `ms-settings:batterysaver`                         |
| 系统 > 电池                                     | `ms-settings:batterysaver-settings`                |
| 系统 > 声音                                       | `ms-settings:sound`                                |
| 系统 > 声音 > 应用卷和设备首选项 | `ms-settings:apps-volume`                          |
| 系统 > 声 > 管理声音设备              | `ms-settings:sound-devices`                        |
| 系统 > 存储 > 配置存储感知         | `ms-settings:storagepolicies`                      |
| 时间 & 语言 > 日期 & 时间                        | `ms-settings:dateandtime`                          |
| > 键盘的时间 & 语言                           | `ms-settings:keyboard`                             |
| > 语言 & 语言                           | `ms-settings:language`                             |
| > 语言 & 语言                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新 & 安全 > 重置 & 恢复               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>已更新 Uri

以前，以下两个 Uri 不会直接将用户带到所指示的页面，而只会阻止主更新页面。 以下项已更新为定向到其页面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>通过设置应用配置回退诊断

现在，在设置应用中，用户可以配置[回退诊断](hololens-diagnostic-logs.md)的行为。 在设置应用中，导航到 "**隐私**  >  **故障排除**" 页以配置此设置。

> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。  

### <a name="share-things-with-nearby-devices"></a>与附近设备共享东西

Windows 10 设备（包括电脑和其他 HoloLens 2 设备）与附近共享东西。 你可以在 **设置**  >  **系统**  >  **共享体验** 中试用它，以将文件或 url 从 HoloLens 共享到 PC。 有关更多详细信息，请参阅有关如何[在 Windows 10 中与附近设备共享内容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)的详细信息。

此功能可通过 [连接/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)进行管理。

### <a name="new-os-diagnostic-traces"></a>新操作系统诊断跟踪

除了设置应用中以前的疑难解答外，还添加了新的疑难解答，并添加了新的设置应用以进行操作系统更新。 导航到 **设置**  >  **更新 &amp; 安全**  >  **疑难解答**  >  **Windows 更新** 并选择 "**启动**"。 这样，你就可以收集跟踪，同时在操作系统更新中重现你的问题，以帮助更好地帮助你的 IT 或支持人员进行故障排除。

### <a name="delivery-optimization-preview"></a>传递优化预览版

使用此 HoloLens 更新时，Windows Holographic for Business 启用 "传递优化" 设置，以减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能的更完整说明以及建议的网络配置：[Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

以下设置作为管理图面的一部分启用，并且[可以从 Intune 进行配置](/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

有关此预览版产品/服务的一些注意事项：

- 此预览版中的 HoloLens 支持仅限于 OS 更新。
- Windows Holographic for Business 仅支持 HTTP 下载模式并从 [Microsoft 联网缓存终结点](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)进行下载；目前，HoloLens 设备不支持对等下载模式和组分配。
- HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。
- 故障排除将需要对联网缓存服务器进行诊断，或通过“设置” > “更新和安全” >  “故障排除” >  “Windows 更新”在 HoloLens 上收集跟踪。

### <a name="it-admin---update-checklist"></a>IT 管理员-更新清单

此清单可帮助你了解在此功能更新中添加的功能可能会影响当前设备管理配置的新项目，或者你可能希望开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式更新

[**为展台模式下的新应用✔️新 AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)：

如果你以前在展台使用设置应用或 Microsoft Edge 应用，我们已将这些应用替换为使用不同应用 ID 的新应用。 我们强烈建议你在下面的 [展台模式下阅读新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 这将确保在展台上继续拥有设置的应用程序，或包括新的 Microsoft Edge 应用程序。 现在可以完成这些更改，并将其部署到所有设备，并允许在更新时获得更平稳的过渡效果。

[**网亭的✔️访问者自动登录**](#visitor-auto-logon-for-kiosks)：

现在，访问者可以自动登录到展台。 默认情况下，此行为是启用的，但可以被管理和禁用。

✔️ [**改进了展台模式故障**](#kiosk-mode-behavior-changes-for-handling-of-failures)处理：

如果未成功确定登录 AAD 用户 AAD 组成员身份，则会在 "开始" 菜单中使用 "全局展台配置" (如果) 存在，则显示 "开始" 菜单，否则显示 "开始" 菜单。 尽管空 "开始" 菜单不是可以直接设置的配置，但如果您使用的是展台，则这种新的处理可能会告诉您的支持部门，因为这可能适用于您的配置，或者您可能想要对分配的访问配置进行新调整。

#### <a name="updates-to-page-settings-visibility"></a>页面设置可见性更新

[**为页设置可见性✔️新的设置 uri**](#new-settings-uris-for-page-settings-visibility)

如果你当前正在使用[页面设置可见性](settings-uri-list.md)，则你可能希望对已允许或阻止的现有 uri 进行调整。

#### <a name="updates-for-your-wdac-policy"></a>适用于 WDAC 策略的更新

✔️如果以前通过 WDAC 阻止 Microsoft Edge，则需要更新你的 wdac 策略。 请查看以下代码，并使用提供的示例代码。

#### <a name="enable-new-endpoints-for-edge"></a>启用边缘的新终结点

✔️如果你有涉及配置网络终结点（例如代理或防火墙）的基础结构，请为新的 Microsoft Edge 应用启用这些新的终结点。

#### <a name="newly-configurable-items"></a>新的可配置项

✔️ [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)：你可以配置是否和谁可以收集回退诊断。

✔️[与附近设备共享内容](#share-things-with-nearby-devices)：你可以禁用新的邻近共享功能。

[为新 Microsoft Edge ✔️配置策略设置](#configuring-policy-settings-for-the-new-microsoft-edge)：查看适用于 Microsoft Edge 的新配置。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

✔️[新 os 诊断跟踪](#new-os-diagnostic-traces)：收集与 OS 更新相关的日志。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。
- 解决了通过运行时预配包部署业务线应用程序的问题。
- 解决了业务线应用程序安装状态报告问题。
- 修复了跨设备重置的新应用程序包持久性的问题。
- 修复了一个问题，该问题可能导致日语客户在边缘内键入错误的符号。
- 提高了 OS 更新的复原能力，如边缘的预安装应用。
- 解决了影响 Microsoft Edge 安装的更新可靠性。

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows全息版20H2 –2021版更新

- 生成19041.1146

更新中的改进和修复：

- 这一月度质量更新不包含任何显著的更改，我们建议你试用最新的版本，Windows 全息版21H1。

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows全息版，版本 1903-5 2021 月更新

- 生成18362.1110

更新中的改进和修复：

- 此月度质量更新不包含任何显著的更改。 **此生成将不再接收每月服务更新**。 我们建议你试用最新的内部版本，Windows全息版 21H1。

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows全息版 20H2 - 2021 年 4 月更新

- 内部版本 19041.1144

更新中的改进和修复：

- 修复了有关业务线应用程序安装状态报告的问题。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows全息版 1903 - 2021 年 4 月更新

- 内部版本 18362.1108

更新中的改进和修复：

- 解决了尝试更改设置帐户的密码时，应用崩溃的问题。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows全息版 20H2 - 2021 年 3 月更新

- 内部版本 19041.1140

更新中的改进和修复：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 通过 HoloLens 2 捕获照片的客户现在可以在捕获照片后最多 3 秒检索相机姿势。
- 修复了服务中的设备门户泄漏，该问题导致服务的内存使用量增加，导致其他应用程序无法分配内存。
- 修复了在"分步推出"中注册的用户无法登录到设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows全息版 1903 - 2021 年 3 月更新

- 内部版本 18362.1102

更新中的改进和修复：

- 修复了服务中的设备门户泄漏，该问题导致服务的内存使用量增加，导致其他应用程序无法分配内存。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows全息版 20H2 - 2021 年 2 月更新

- 内部版本 19041.1136

更新中的改进和修复：

- 修复了有关初始设备设置和存储应用更新的问题。
- 解决有关升级和航班的问题，供HoloLens版本。
- 从设备中删除了 eSIM 根存储中未使用的HoloLens证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows全息版 1903 - 2021 年 2 月更新

- 内部版本 18362.1098

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows的最新内部版本。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows全息版 20H2 - 2021 年 1 月更新

- 内部版本 19041.1134

更新中的改进和修复：

- 改进了在设备上有许多用户时启动、恢复和用户切换期间的性能。
- 添加了对研究模式的 arm32 [支持](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows全息版 1903 - 2021 年 1 月更新

- 内部版本 18362.1091

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows的最新内部版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows全息版 20H2 - 2020 年 12 月更新

- 内部版本 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 HoloLens 2 在 应用安装程序

我们 **添加了一项新功能 (应用安装程序) ，** 让你能够更无缝地在 HoloLens 2 设备上安装应用程序。 对于非 **托管设备，此功能默认为打开状态**。 为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。  

如果以下任一情况 **成立，则** 设备被视为"托管"设备：

- MDM [已注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户[标识](hololens-identity.md)Azure AD

现在可以安装应用，而无需启用开发人员模式或设备门户。  只需 (USB 或 Edge) Appx 捆绑包下载到设备，然后导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。  或者， [从网页 启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。  与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，应用需要使用签名工具进行[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)数字签名，并且用于[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)签名的证书必须受 HoloLens 设备信任，然后才能部署应用。

**应用程序安装说明。**

1. 确保设备未被视为托管设备
1. 确保HoloLens 2设备已打开并连接到电脑
1. 确保已登录到 HoloLens 2 设备
1. 在电脑上导航到自定义应用，将 yourapp.appxbundle 复制到 yourdevicename\Internal 存储\Downloads。   复制完文件后，可以断开设备连接
1. 从HoloLens 2打开"开始"菜单，选择"所有应用"并启动文件资源管理器应用。
1. 导航到"下载"文件夹。 可能需要先在应用的左侧面板中选择"此设备"，然后导航到"下载"。
1. 选择 yourapp.appxbundle 文件。
1. 系统应用安装程序启动。 选择"安装"按钮以安装应用。
安装完成后，已安装的应用将自动启动。

可以在通用示例Windows[上](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)GitHub应用来测试此流。

阅读有关使用 HoloLens 2 在 应用安装程序[应用的完整应用安装程序。](app-deploy-app-installer.md)  

![通过 应用安装程序 安装 MRTK 示例。](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手部跟踪现在在许多以前丢失手部的新情况下保持跟踪。  在某些新情况下，只有手部位置会继续根据用户的实际手部进行更新，而其他连接则根据以前的姿势进行推断。  此更改有助于提高动作（如击球、引发、跳跃和击球）的跟踪一致性。  它还有助于手靠近表面或持有对象的情况。  在推断手部时 [，每个联合](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 准确度值将设置为"近似"，而不是"高"。
- 修复了帐户的 PIN 重置Azure AD显示错误"出现问题。
- 启动 ET、设置应用中的 Iris、新用户或通知 toast 时，用户应看到更少的启动后 OOBE 故障。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows全息版 1903 - 2020 年 12 月更新

- 内部版本 18362.1088

此每月质量更新不包含任何值得注意的更改，建议试用最新的 Windows Holographic 版本 20H2 – 2020 年 12 月更新，以及生成中添加的新 应用安装程序 功能。

## <a name="windows-holographic-version-20h2"></a>Windows全息版 20H2

- 内部版本 19041.1128

Windows全息版 20H2 现已发布，为用户和 IT 专业人员HoloLens 2一系列新功能。 从自动眼定位到 设置 中的证书管理器，改进了展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更精细地控制如何配置HoloLens设备，并为用户提供更无缝的全息体验。

此最新版本是版本 2004 的每月更新，但这次我们将包含新功能。 主内部版本号将保持不变，Windows更新将指示每月发布版本 2004 (内部版本 19041) 。 可以在"关于"屏幕中查看设置 >号，以确认你使用最新的可用内部版本 19041.1128+。 若要更新到最新版本，请打开 设置 应用，转到"更新&安全性"，然后点击"检查更新"。 若要详细了解如何管理更新HoloLens，请访问[管理HoloLens更新](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic 版本 20H2 Windows新增功能  

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，用户无需经过眼动跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许使用更简单的新方法来安装和删除应用设置证书。     |
| [从 USB 自动启动预配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 驱动器上的预配包会自动提示 OOBE 中的预配页。                                                         |
| [在 OOBE 中自动确认预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配包会在 OOBE 期间从预配页自动应用。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将设置自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，无需使用以太网适配器。 |
| [Tenantlockdown 云解决方案提供商和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，在设备重置或重新刷新时，设备只能在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个 app 展台模式的新配置方法，它在系统级别应用展台，使其适用于所有内容。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录到多应用展台模式时自动启动。                                                        |
| [用于处理故障的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制的回退。                                                                                                |
| [HoloLens政策](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新策略。     |
| [缓存 Azure AD 脱机展台的组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用 "组成员身份缓存" 在设置的天数内脱机使用展台模式。                                        |
| [HoloLens 2 的新设备限制策略](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 为 HoloLens 2 启用了新启用的设备管理策略。                                                                                |
| [HoloLens 2 的新电源策略](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 最新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允许控制更新的新启用的策略。           |
| [已启用 HoloLens 2 的设置页面可见性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选择在设置应用中出现哪些页的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [记录长度增加](hololens-release-notes.md#recording-length-increased) | MRC 记录不再超过5分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在 HoloLens 2 中，目视定位可实现准确的全息影像定位、舒适的观看体验，并改善了显示质量。 眼部位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。

自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。 自动目视位置在用户将设备置于设备上的时刻自动开始运行。 如果用户没有先前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视定位将开始向显示系统提供用户的眼睛位置。 用户数据不会保留在设备上，因此如果用户关闭并重新打开设备，或者设备重新启动或从睡眠状态唤醒，则此过程将重复。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在这种情况下，uncalibrated 用户指的是先前尚未经历设备上的目视跟踪校准过程的人。

| 活动应用程序 | 先前行为 | Windows 全息版 20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |“眼球跟踪校准提示”对话框随即显示。 | 不显示提示。 |
| 启用了凝视的应用 | “眼球跟踪校准提示”对话框随即显示。 | 仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将类似于。 例如，将不会启用一次传递的开始手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛眼睛数据或非常精确的全息图定位的体验，建议 uncalibrated 用户运行目视跟踪校准。 可以从目视跟踪校准提示进行访问，也可以从 "开始" 菜单启动设置应用程序，然后选择 "**系统 > 校准 > 目视校准 >" 运行目视校准**"。

稍后可以在 [其他校准信息](hololens-calibration.md#auto-eye-position-support)中找到此信息。

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能使你能够在商业环境中大规模部署、排查和验证你的证书。

在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 请参阅 **设置 > 更新 & 安全 > 证书**。 此功能提供了一种简单易用的方法来查看、安装和删除设备上的证书。 使用新的证书管理器，管理员和用户现在已经改进了审核、诊断和验证工具，以确保设备保持安全性和合规性。

- **审核：** 能够验证是否已正确部署证书，或者确认是否已正确删除证书。
- **诊断：** 出现问题时，验证设备上存在的适当证书是否节省时间并帮助进行故障排除。
- **验证：** 验证证书是否服务于预期目的并能正常工作，可以节省大量时间，特别是在商业环境中，在较大规模部署证书之前。

若要快速查找列表中的特定证书，可以按名称、存储或到期日期排序。 用户还可以直接搜索证书。 若要查看单独的证书属性，请选择该证书，然后单击 " **信息**"。

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从设置 UI 安装的证书。 如果通过其他方式安装了证书，则该证书还必须通过相同的机制删除。

#### <a name="steps-to-install-a-certificate"></a>安装证书的步骤

1. 将 HoloLens 2 连接到 PC。
1. 将要安装的证书文件放在 HoloLens 2 上的某个位置。
1. 导航到 **设置应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。
1. 单击 " **导入文件** "，并导航到保存证书的位置。
1. 选择 " **存储位置**"。
1. 选择 " **证书存储**"。
1. 单击“安装”  。

现在应在设备上安装证书。

#### <a name="steps-to-remove-a-certificate"></a>删除证书的步骤

1. 导航到 **设置应用 > 更新和安全 > 证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 出现确认提示时，选择“是”。

![设置应用中的证书查看器。](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片。](images/certificate-device-install.jpg)

稍后可 [在新的证书管理器页中](certificate-manager.md)找到此信息。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动设置

- 在 OOBE 期间使用带有预配包的 USB 驱动器时，可通过自动化过程来减少用户交互。

在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，才能使用按钮组合进行设置。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。

1. 在 OOBE 的第一次种不可交互时插入带有预配包的 USB 驱动器
1. 当设备准备好进行预配时，将自动在 "设置" 页中打开提示。

注意：如果在设备启动时，会将 USB 驱动器插入，则 OOBE 会枚举现有 USB 存储设备，并监视其他设备是否已插入。

有关在 OOBE 期间应用预配包的详细信息，请访问[HoloLens 预配](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)文档。

可以在 HoloLens 预配文档中找到有关[USB 中的自动启动设置](hololens-provisioning.md#auto-launch-provisioning-from-usb)的其他信息。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>自动确认在 OOBE 中预配包

- 自动化过程允许较少的用户交互，当显示"预配包"页时，它将自动应用列出的所有包。

当预配主屏幕出现时，OOBE 将倒计时 10 秒，然后自动开始应用所有预配包。 在验证 [预期的包](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 后，用户仍然可以在此 10 秒内确认或取消。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配

- 合并了自动过程，减少了预配的设备交互。

通过将从 USB 设备自动启动预配和自动确认预配包相结合，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至无需设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这可用于在同一区域中一次部署多个设备。

1. [使用配置设计器](hololens-provisioning.md)创建[Windows包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。
1. 将包复制到 USB 存储驱动器。
1. [将版本HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions)[到 19041.1361 或更高版本。](https://aka.ms/hololens2previewdownload)
1. 高级 [恢复助手](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成刷用设备后，拔下 USB-C 电缆。
1. 将 USB 驱动器插入设备。
1. 当HoloLens 2设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包并启动预配页。
1. 10 秒后，设备将自动应用预配包。

设备现已配置，将显示 ["预配成功"屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi连接一起使用

- 通过使 Autopilot 在连接的设备上运行，无需使用 USB-C 适配器Wi-Fi硬件需求。

现在，在 OOBE 期间，HoloLens 2 Wi-Fi 进行连接后，OOBE 将检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成AAD和注册流。 换句话说，不再要求使用以太网到 USB-C 或Wi-Fi连接到 USB-C 适配器，但如果在 OOBE 开始时提供，它们将继续工作。 详细了解适用于[设备 HoloLens 2 Autopilot。](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown 云解决方案提供商和 Autopilot

- 通过锁定组织租户上的设备，即使设备重置或重启，也可以将设备锁定到租户中。 通过禁止通过预配在 中创建帐户，进一步实现安全性。

HoloLens 2自 Holographic 版本[20H2](hololens-release-notes.md#windows-holographic-version-20h2)起，Windows支持 TenantLockdown CSP。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) 云解决方案提供商允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使执行了重刷、操作系统更新等操作，值仍将保留在设备上。

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中将不允许执行以下操作：

- 使用运行时预配创建本地用户
- 通过运行时预配执行 Azure AD 加入操作
- 选择 OOBE 体验中的设备所有者

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 对此进行设置？

1. 创建自定义 OMA URI 设备配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定。](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？

1. 将 HoloLens 2 从先前分配了上面创建的设备配置的设备组中删除。

1. 创建基于 OMA URI 的自定义设备配置文件，并针对 RequireNetworkInOOBE 指定 false，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![在 Intune 中通过 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图。](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于非活动状态。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>将 TenantLockdown 设置为 true 后，如果在 HoloLens 上取消分配 Autopilot 配置文件，在 OOBE 期间会发生什么情况？

OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了删除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown 云解决方案提供商引入的限制。

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

现在，可以在 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)下与 Autopilot 的其余部分一起找到此信息。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配访问权限 - 展台模式

- 通过启用在系统级别应用展台模式的新展台方法，减少了展台的标识管理。

此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识没有关联，并且适用于登录设备的每个人。 在展台模式下详细了解HoloLens[功能](hololens-kiosk.md)。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序

- 具有自动应用启动的集中体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能使用"分配的访问权限配置"中下面的突出显示属性将 1 个应用指定为自动启动。

用户登录时，应用程序会自动启动。

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>展台模式行为更改，用于处理故障

- 通过消除展台模式故障时可用的应用，实现更安全的展台模式。

之前在应用展台模式时遇到HoloLens，它用于显示开始菜单中的所有应用程序。 现在，Windows 20H2 版（如果发生故障）中，开始菜单中不会显示任何应用，如下所示：

![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens政策

- 专用于管理设备HoloLens的设备管理选项。

在全息版 20H2 上为 HoloLens 2 设备Windows混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、设置收集诊断的时间以及AAD成员身份缓存。  

| 新建HoloLens策略                                | 说明                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，以便按它不会更改亮度。       | 1 是，0 (默认)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便按它不会更改音量。               | 1 是，0 (默认)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此无法对麦克风进行音频HoloLens 2。                      | 1 是，0 (默认)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制何时可以收集诊断日志的行为。                               | 0 已禁用，1 为设备所有者启用，2 为默认 (启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制将组Azure AD缓存用于展台目标到组Azure AD天数。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>脱机Azure AD的缓存组成员身份

- 已启用脱机展台，AAD组一起使用最多 60 天。

此策略控制多少天，Azure AD组成员身份缓存用于针对已登录用户Azure AD组分配的访问配置。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最短 - 0 天  
最大值 - 60 天

正确使用此策略的步骤：

1. 为展台 Azure AD 组创建设备配置文件，并将其分配给 HoloLens 设备 () 。
1. 创建基于自定义 OMA URI 的设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。
    1. 应在 OMA-URI 文本框中输入 URI 值作为/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。
    1. 该值可以介于最小值/最大允许值之间。
1. 注册 HoloLens 设备，并验证两个配置是否应用于设备。
1. 当 internet 可用时，让 Azure AD 用户1登录，一旦用户登录并 Azure AD 组成员身份已成功确认，就会创建缓存。
1. 现在 Azure AD 用户1可以 HoloLens 脱机并将其用于展台模式，只要策略值允许 X 天。
1. 对于任何其他 Azure AD 用户 N，可以重复执行步骤4和步骤5。以下是任何 Azure AD 用户都必须使用 Internet 登录设备，因此至少可以确定它们是展台配置所针对的 Azure AD 组的成员。

> [!NOTE]
> 直到 Azure AD 执行步骤4后，才会在 "断开连接" 环境中遇到失败行为。

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新设备限制策略

- 允许用户管理特定的设备管理策略，如阻止添加或删除预配包。

允许 HoloLens 2 设备的更多管理选项的新启用的策略。

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [高](/windows/client-management/mdm/remotelock-csp)

这两个适用于 AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 就[高](/windows/client-management/mdm/remotelock-csp)而言，HoloLens 仅支持/Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理 PIN （如 reset 和 recover）的配置。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 的新电源策略

- 通过电源策略 HoloLens 睡眠或锁定时的更多选项。

这些新添加的策略使管理员能够控制电源状态，如空闲超时。 若要阅读有关每个策略的详细信息，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 配置设计器中使用的示例值，即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 配置设计器中使用的示例值，即100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

这两个适用于 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 若要在 HoloLens 2 上获得一致的体验，请确保将 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式备用的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### <a name="newly-enabled-update-policies-for-hololens"></a>针对 HoloLens 的新启用的更新策略

- 安装更新或禁用 "暂停更新" 按钮以确保更新的更多选项。

现在 HoloLens 2 设备上启用了这些更新策略：

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何使用这些策略的详细信息，请参阅[管理 HoloLens 更新](hololens-updates.md)中的 HoloLens 设备。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>已启用 HoloLens 2 的设置页面可见性

- 设置应用中增加的 UI 控件，这可能会使用户感到困惑，以显示有限的页面。

现在，我们已启用了一个策略，该策略允许 IT 管理员阻止系统设置应用中的特定页面可见或访问，或为除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 上自定义的页面设置，请访问我们的[设置 uri "页](settings-uri-list.md)。

![在“设置”应用中修改活动时段的屏幕截图。](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式

在研究模式下，HoloLens 2 成为计算机视觉研究的强大工具。 与以前的版本相比，HoloLens 2 的研究模式具有以下优点：

- 除了 HoloLens 中公开的传感器 (第一代) 研究模式，我们现在提供 IMU 传感器访问，包括加速感应器、陀螺仪和磁力仪。
- HoloLens 2 提供了可与研究模式一起使用的新功能。 具体来说，就是访问可提供更丰富的试验集的有表述的手动跟踪和目视跟踪 Api。

研究人员现在可以选择在其 HoloLens 设备上启用研究模式，以访问所有面向外部的原始图像传感器流。 HoloLens 2 的研究模式还提供对加速计、陀螺仪和磁力仪读数的访问。 为了保护用户的隐私性，无法通过 "调查" 模式获取原始眼睛跟踪相机图像，但可通过现有 Api 使用 "目视" 方向。

有关更多技术详细信息，请查看 [研究模式文档](/windows/mixed-reality/research-mode) 。

### <a name="recording-length-increased"></a>记录长度增加

由于客户反馈，我们已增加 [混合现实捕获](holographic-photos-and-videos.md)的记录长度。 默认情况下，混合现实捕获将不再限制为5分钟，但会根据可用磁盘空间来计算最大记录长度。 该设备将根据可用磁盘空间（最大为总磁盘空间的80%）估算最大视频录制持续时间。

> [!NOTE]
> 如果发生以下情况之一，HoloLens 将使用默认视频录制长度 (5 分钟) ：
>
> - 预计的最大记录持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

你可以在 " [全息照片和视频](holographic-photos-and-videos.md#maximum-recording-length) " 文档中找到完全要求。

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Windows 全息版20H2 更新中的改进和修补程序：

- OOBE 中的更多屏幕现在处于暗色模式。
- 了解更多内容应联机指向最新的隐私声明。
- 解决了用户无法通过设置包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 已更新策略以禁用通过 MDM for NCM for AllowUsbConnection 的 USB 函数的枚举。
- 解决了在将设备设置为[单应用展台](hololens-kiosk.md)后，阻止 HoloLens 设备在文件资源管理器中显示在 (MTP) 上的问题。 请注意，一般) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略进行禁用。
- 修复了在展台模式下正确缩放 "开始"菜单中的图标的问题。
- 修复了由于 HTTP 缓存干扰以展台模式为目标 Azure AD 组的问题。
- 修复了在使用预配包启用开发人员模式后，用户无法使用 "取消" 按钮的问题，除非他们禁用并重新启用了开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows全息版，版本 1903-2020 更新

- 生成18362.1085

这一月度质量更新不包含任何显著的更改，我们建议你试用最新的功能版本 Windows 全息版20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows全息版，版本 2004-2020 更新

- 生成19041.1124

更新中的改进和修复：

- 删除导致运行时系统错误的不必要的检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows全息版，版本 1903-2020 更新

- 生成18362.1081

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows全息版，版本 2004-2020 更新

- 生成19041.1117

更新中的改进和修复：

- 解决了在 appxmanifest.xml 中存在 SupportsMultipleInstances = "true" 时阻止 Visual Studio 调试应用程序的问题。
- 此版本包含 NCSI proxy 检测修复，可解决通过网络代理进行的 Internet 检测失败的问题。 NCSI 可以使用计算机代理和每个配置文件的代理来检测 Internet 连接。 将来的版本中，NCSI 将支持每个用户的代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，的较早版本 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜几度。 HoloLens 2 的较新版本已更正此情况，以确保各种形式因素的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。
- 此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows全息版，版本 1903-2020 更新

- 生成18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，的较早版本 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜几度。 HoloLens 2 的较新版本已更正此情况，以确保各种形式因素的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows全息版，版本 2004-8 2020 月版更新

- 生成19041.1113

更新中的改进和修复：

- 设置应用将不再跟随用户进入 Iris 注册或眼睛跟踪校准体验。
- 修复了一个 bug，该 bug 在用于重命名设备并执行其他操作 (例如连接到网络) 时在设备重启后执行其他操作（例如，连接到网络）的情况下应用设置包。
- 修改了初始设备设置流程的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows全息版，版本 1903-8 2020 月版更新

- 生成18362.1074

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows全息版，版本 2004-2020 更新

- 生成19041.1109

更新中的改进和修复：

- 现在，开发人员可以选择启用还是禁用设备门户要求安全连接。
- 操作系统更新后，针对应用程序启动的可靠性得到了提高。
- 更改了默认收件箱亮度到100%。
- 解决了 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows全息版，版本 1903-2020 更新

- 生成18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能导致在跟踪丢失或执行跟踪时，无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用 HoloLens Emulator 硬件加速时，使独占 HoloLens 应用程序故障回复到 shell 的问题。
- 解决了 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows全息版，版本 2004-2020 更新

- 生成19041.1106

更新中的改进和修复：

- 对于某些属性，如果未指定，则自定义 MRC 记录器现在具有新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上的当前 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 修复了一个 bug，以便在混合现实捕获方案中提高音频质量。 具体而言，当显示 " **开始** " 菜单时，此修复程序应消除录音 glitching。
- 改善了录制视频中的全息影像稳定性。
- 解决了在设备处于待机状态一段时间后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 通过 Wi-Fi 连接访问设备门户时，由于证书无效，web 浏览器可能会阻止访问。 即使之前信任设备证书，浏览器也可能会报告 "ERR_SSL_PROTOCOL_ERROR" 之类的错误。 在这种情况下，无法对设备门户进行进度，因为没有忽略安全警告的选项。 此更新解决了问题。 如果先前已在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并将其信任，以解决浏览器安全警告。
- 支持创建可通过使用 .MSIX 包安装应用的运行时预配包。
- 添加了 **设置**  >  **系统**  >  **全息影像** 中的设置，该设置允许用户在设备关闭时自动从混合现实总部删除所有全息影像。
- 修复了一个问题，该问题会导致在 HoloLens 模拟器中更改像素格式以呈现黑色 HoloLens 应用。
- 修复了 Iris 登录期间导致崩溃的 bug。
- 修复了有关现有应用的重复存储下载的问题。
- 修复了一个 bug，以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版更新后初始启动时启动照片应用的问题。
- 提高了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows全息版，版本 1903-2020 更新

- 生成18362.1064

更新中的改进和修复：

- 如果未指定自定义的 MRC 录像机，则为某些属性提供新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上的当前 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免当面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 修复了一个问题，该问题会导致 HoloLens 应用更改其像素格式，使其在 HoloLens Emulator 呈现为黑色。
- 修复了从1903版更新后初始启动时启动的照片应用程序的问题。

## <a name="windows-holographic-version-2004"></a>Windows全息版，版本2004

- 版本-19041.1103

*Windows 全息版* HoloLens 2 的主要软件更新2020，版本2004包含一种令人兴奋的新功能，例如支持 Windows Autopilot、应用程序暗模式、USB 以太网支持 5G/LTE 热点，等等。 若要更新到最新版本，请打开 **设置**   应用，请参阅  **更新 & 安全**"，然后选择" **检查更新**"   按钮。 

|             功能                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 预配置新设备并将其无缝设置为生产                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速和安全身份验证            |
|       改进的预配                      |          无缝地将预配包应用于 u 盘到 HoloLens                              |
|       应用程序安装状态                 |          在应用的设置应用中检查安装状态已通过 MDM 推送到 HoloLens 2               |
|       配置服务提供程序 (Csp)    |          添加了新的配置服务提供程序以增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          通过扩展 USB 以太网功能，支持 5G/LTE                                    |
|       深色应用模式                              |          深色应用模式适用于支持深色和浅色模式的应用，从而改善观看体验        |
|       语音命令                             |          支持使用其他系统语音命令来控制HoloLens操作                           |
|       手部跟踪改进                 |          手部跟踪改进使按钮和 2D 板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

WindowsAutopilot for HoloLens 2允许设备销售渠道预先注册HoloLens Intune 租户。 设备到达时，可以自行部署为租户下的共享设备。 若要利用自我部署，设备必须使用 USB-C 到以太网在安装的第一个屏幕期间连接到网络。

用户启动 Autopilot 自我部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 将设备注册到 Microsoft Intune (或其他 MDM 服务) 。
1. 下载设备目标策略、证书和网络配置文件。
1. 预配设备。
1. 向用户展示登录屏幕。

有关详细信息，请Windows [Autopilot for HoloLens 2指南](hololens2-autopilot.md)。

*立即联系帐户管理员以加入 AutoPilot 预览版。Autopilot 就绪设备即将开始交付。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户与HoloLens或学校环境中的用户共享设备。 因此，用户可以轻松地无需键入长用户名和密码，这一点很重要。 使用 Fast Identity Online (FIDO) ，组织 (Azure AD 租户中的) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是基于标准的"不可加密"无密码身份验证方法，可以采用任何外形要求。 FIDO 是无密码身份验证的开放标准。 它允许用户和组织在没有用户名或密码的情况下登录到其资源。 而是使用内置于设备的外部安全密钥或平台密钥。

若要开始，请参阅 [启用无密码安全密钥登录](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

通过预配包，HoloLens配置文件设置配置，而不是通过HoloLens体验进行配置。 以前，预配包必须复制到HoloLens内存。 现在，它们可以位于 USB 驱动器上，以便更轻松地在多个设备上重复使用HoloLens设备，并且你可以并行预配设备。 预配包现在还支持在设备管理中注册字段，因此预配后无需手动设置。

试试看：

1. 将最新版本的 Windows 配置设计器从 Windows 存储下载到电脑上。
1. 选择 **"HoloLens设备预配**  >  **HoloLens 2设备"。**
1. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
1. 将 USB-C 设备插入任何新刷入的HoloLens。 然后按 **音量关闭**  +  **电源** 按钮以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

业务线应用的 MDM 应用部署和管理对于HoloLens。 管理员和用户需要查看应用安装状态，以便进行审核和诊断。 在此版本中，我们在"帐户访问工作或设置"单击帐户信息"中添加  >    >    >  **了**  >  **更多详细信息**。

### <a name="additional-csps-and-policies"></a>其他 CSP 和策略

CSP [ (配置) ](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 是一个接口，用于读取、设置、修改或删除设备的配置设置。 在此版本中，我们添加了对更多策略的支持，以增加管理员对部署在设备上HoloLens控制。 有关云解决方案提供商支持的 CSP HoloLens，请参阅[NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在设备Windows策略。 在此版本中，我们为 HoloLens添加了新策略，此处列出了这些策略。 若要了解有关详细信息，请参阅由[HoloLens 2 支持的策略HOLOLENS 2。](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy 云解决方案提供商**

NetworkQoSPolicy 配置服务提供商使用 QoS 策略创建 (服务质量) 提供程序。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 有关详细信息，请参阅 [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>扩展了对 5G/LTS 网络设备的 USB 以太网支持

添加了支持，允许某些移动宽带设备（例如 5G/Wi-Fi）和 Wi-Fi 热点通过 USB 连接到 HoloLens 2设备。 这些设备现在在网络设置 **中显示为** 另一个以太网连接。  (不支持需要外部驱动程序的移动宽带设备。) 此功能在 Wi-Fi 不可用且网络Wi-Fi性能不足时启用高带宽连接。 若要详细了解支持的 USB 设备，请参阅 连接[蓝牙 和 USB-C 设备](hololens-connect-devices.md)。  

### <a name="hand-tracking-improvements"></a>手部跟踪改进

此版本包括多项手动跟踪改进：

- **指向姿势稳定性：** 现在，当手指被手指遮挡时，系统可以抵御手指的滑动。 此更改提高了按下按钮、键入、滚动内容等时的准确性！ 
- **减少了意外的敲击：** 改进了对敲击手势的检测。 现在，在多种常见情况下（例如，将手放在两侧时）中的意外激活更少。
- **用户交换机可靠性：** 现在，共享设备时，系统在更新手部大小时速度更快且更可靠。
- **减少手部窃取：** 改进了传感器视图超过两手的情况的处理。 如果多人在一起工作，现在跟踪手从用户"跳转"到场景中其他人手的可能性要低得多。
- **系统可靠性：** 修复了在设备负载较高时导致手部跟踪停止工作的问题。

### <a name="dark-mode"></a>深色模式

许多Windows应用现在都支持深色和浅色模式。 HoloLens 2用户可以为支持两者的应用选择默认模式。 更新后，默认应用模式为"深色"，**但** 可以轻松更改此设置：导航到"设置  >    >    >  **选择默认应用模式"。**

这些"盒中"应用支持深色模式：

- 设置
- Microsoft Store
- Mail
- 日历
- 文件资源管理器
- 反馈中心
- OneDrive
- 照片
- 3D 查看器
- 电影和电视

![深色模式窗口平铺。](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>系统语音命令

现在可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅[使用语音操作HoloLens。](hololens-cortana.md) 另请参阅[支持的语言HoloLens 2。](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana更新

更新后的应用与 Microsoft 365 集成，以帮助你完成当前仅 (设备US-English设备) 。 在HoloLens 2，Cortana不再支持某些特定于设备的命令，例如调整卷或重启。 新的系统语音命令现在支持这些选项。 在我们的博客 中Cortana新应用[。](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中的改进和修复：  

- 引入了主动显示校准系统。 此功能可提高全息影像的稳定性和对齐方式。 现在，当你将头部从一侧移到另一侧时，它们就位。
- 修复了一个 bug，Wi-Fi流式HoloLens定期中断。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)函数 来实现修复。
- 修复了在研究模式下流式传输期间发生的设备挂起。
- 修复了以下 bug：在某些情况下，恢复会话时不会在登录屏幕上显示正确的用户。
- 修复了用户无法通过 设置 导出 MDM **日志的问题**。
- 修复了以下问题：在开箱即用设置后立即进行眼动跟踪的准确性可能低于预期。
- 修复了在某些情况下眼动跟踪子系统无法初始化或执行校准的问题。
- 修复了提示已校准用户的眼部校准问题。
- 修复了驱动程序在眼部校准期间崩溃的问题。
- 修复了重复按下电源按钮可能导致 60 秒系统超时和 shell 崩溃的问题。
- 改进了深度缓冲区的稳定性。
- 在" **共享** "按钮中添加了反馈中心，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan 未正确安装的 bug。

### <a name="known-issues"></a>已知问题

- zh-CN 系统语言的问题阻止语音命令捕获混合现实或显示设备 IP 地址。
- 问题要求在启动设备Cortana"你好"语音激活后启动Cortana应用。 如果从 18362 版本更新，则还可能会看到在"启动"中不再Cortana以前版本的应用的第二个 **应用磁贴**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows全息版 1903 - 2020 年 5 月更新

- 内部版本 18362.1061

此每月质量更新不包含任何值得注意的更改，因为团队正在处理全息Windows 2004 年 5 月更新，如前文所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows全息版 1903 - 2020 年 4 月更新

- 内部版本 18362.1059

**受支持应用的深色模式**

许多Windows应用同时支持深色和浅色模式。 HoloLens 2客户现在可以为支持这两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为"深色"，但你随时可以轻松更改此设置：导航到 **设置 > System > Colors** 以查找"选择默认应用模式"。 

这些"盒中"应用支持深色模式：

- 设置
- Microsoft Store
- Mail
- 日历
- 文件资源管理器
- 反馈中心
- OneDrive
- 照片
- 3D 查看器
- 电影和电视

**更新中的改进和修复：**

- 确保混合现实捕获中包含 shell 覆盖。
- Unreal 开发人员现在可以使用 设备门户中的"3D 视图"页来测试和调试其应用程序。
- 改进了使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时混合现实捕获中的全息影像稳定性。
- 修复了 32 位 ARM 应用上的"WinRT IStreamSocketListener API 类未注册"错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows全息版 1903 - 2020 年 3 月更新

- 内部版本 18362.1056

更新中的改进和修复：

- 改进了使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时混合现实捕获中的全息影像稳定性。
- 确保附加到深度 MF 样本的坐标系与公共文档一致。
- 通过让客户通过设备门户粘贴大量文本，提高了开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows全息版 1903 - 2020 年 2 月更新

- 内部版本 18362.1053

更新中的改进和修复：

- 暂时禁用了 Unity 应用程序的 HolographicSpace.UserPresence API。 此更改可避免在视器翻转时导致某些应用暂停的问题，即使启用了"在后台运行"设置。
- 修复了手动跟踪导致的随机 HUP 崩溃，其中用户注意到 UI 冻结，然后在几秒钟后返回到 shell。
- 改进了手部跟踪，以便当你用手指触摸时，该手指的上半部分不太可能意外地卷曲。
- 改进了头部跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows全息版 1903 - 2020 年 1 月更新

- 内部版本 18362.1043

更新中的改进和修复：

- 改进了使用专用仿真器时HoloLens 2的稳定性。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows全息版 1903 - 2019 年 12 月更新

- 内部版本 18362.1042

更新中的改进和修复：

- 引入了 LSR (的最后) 重现。 改进了全息影像的视觉呈现，通过更准确地计算其深度来显示更稳定、更简洁。 如果应用没有正确设置全息影像的深度，则此症状在此更新后会更明显。
- 修复了独占应用的稳定性和独占应用之间的导航。
- 解决了混合现实捕获在设备处于待机状态数天后无法录制视频的问题。
- 提高了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows全息版 1903 - 2019 年 11 月更新

- 内部版本 18362.1039

更新中的改进和修复：

- 修复了在 en-CA **和** en-AU 的初始设置过程中选择语音命令的功能。
- 改进了在最新 Unity 和混合现实中放置的对象的视觉质量Toolkit (MRTK) 版本。
- 修复了全息应用程序在启动时停滞在暂停状态的问题，"开始"菜单打开然后关闭。
- OpenXR 运行时的一致性修复和改进HoloLens 2模拟器。
