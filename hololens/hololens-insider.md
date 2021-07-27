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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b7e5a7cbaa746f58fe0344dd8bf5b027e2e8cea7
ms.sourcegitcommit: dc5d6f3802c997749775be04de522af8cb6d0850
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "114693711"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用最新的 Insider Preview 内部版本HoloLens！ 只需开始操作[，](hololens-insider.md#start-receiving-insider-builds)并为下一次主要操作系统更新提供有价值的反馈，HoloLens。

## <a name="windows-insider-release-notes"></a>Windows预览体验成员发行说明

我们很高兴地开始尝试新功能，以再次Windows预览体验成员。 新内部版本将前往开发和 Beta 通道获取最新更新。 在向预览体验成员内部版本添加更多功能和更新时，Windows更新此页面。 准备好将这些更新混合到现实中，

| 功能                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [CSP 更改报表HoloLens详细信息](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 CSP | IT 管理员    | 20348.1403                 |
| [CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过自定义 UI 添加 PFX 设置证书 | 最终用户 | 20348.1405 |
| [在诊断中查看设置诊断HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上 MDM 诊断日志 | 疑难解答 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的省/市/服务反馈 | 疑难解答 | 20348.1405 |
| [仅将专用应用商店应用用于Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 将应用商店应用配置为仅显示来自组织的应用 | IT 管理员 | 20348.1408 |
| [修复和改进](hololens-insider.md#fixes-and-improvements) | 修复和改进了 HoloLens。 | All | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP 更改报表HoloLens详细信息

- 预览体验Windows内部版本 20348.1403 中引入

以下 CSP 已更新为以新方式从设备HoloLens信息。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 免费存储

DevDetail CSP 现在还报告设备上HoloLens存储空间。 这大约应该与应用设置页中显示的存储匹配。 下面是包含此信息的特定节点。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET) 

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID 和 BSSID

DeviceStatus CSP 现在还报告主动Wi-Fi连接的 HoloLens SSID 和 BSSID。 下面是包含此信息的特定节点。

- 适配器 /SSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* Wi-Fi /SSID
- 适配器 /BSSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* 地址Wi-Fi /BSSID

用于 MDM 供应商的 syncml blob (示例) 用于查询 NetworkIdentifiers

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

此新的 AutoLogonUser 策略控制用户是否将自动登录。 某些客户想要设置与标识绑定的设备，但不希望任何登录体验。 Imagine设备并立即使用远程协助。 或者，能够快速分发HoloLens，并使它们的最终用户能够加快登录。

当策略设置为非空值时，它指定自动登录用户的电子邮件地址。 指定的用户必须至少登录到设备一次才能启用自动登录。

新策略字符串值的 OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同一电子邮件地址的用户将启用自动登录。

在配置了此策略的设备上，策略中指定的用户至少需要登录一次。 第一次登录后设备的后续重启会自动登录指定的用户。 仅支持单个自动登录用户。 启用后，自动登录的用户将无法手动注销。 若要以其他用户登录，必须先禁用策略。

> [!NOTE]
> - 某些事件（例如主要 OS 更新）可能需要指定用户再次登录到设备，以恢复自动登录行为。 
> - 仅 MSA 和 AAD 用户支持自动登录。

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

预览体验Windows内部版本 20348.1405 中引入。 我们已向证书管理器添加了 [支持](certificate-manager.md) ，现在使用 .pfx 证书。 当用户导航到 **"设置**  >  **更新&安全** 证书"，然后选择"安装证书"  >  时，UI 现在支持 .pfx 证书文件。 
用户可以使用私钥将 .pfx 证书导入用户存储或计算机存储。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在诊断中查看设置诊断HoloLens

对于排查行为问题时的托管设备，确认应用了预期的策略配置是一个重要步骤。 以前，若要使用这项新功能，在导出通过 **设置** 帐户访问工作或学校收集的 MDM 诊断日志后，必须将其通过 MDM 或设备附近完成，然后选择"导出管理日志"，并查看附近的  ->    >  电脑。

现在，可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到"访问工作或学校"页，然后选择"**查看高级诊断报告"。** 这会在新的 Edge 窗口中生成并打开报表。

![在应用内查看设置报告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

这是对名为"脱机诊断" [的现有功能的更新](hololens-diagnostic-logs.md#offline-diagnostics)。 以前，没有向用户明确指示他们已触发诊断收集或已完成。
现在，Windows预览体验内部版本中添加，有两种形式的脱机诊断反馈。 第一种是，在收集开始和完成时为两者显示 toast 通知。 当用户登录且具有视觉对象时，将显示这些对象。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![日志收集完成后的 Toast。](./images/logcollection2.jpg)
 
由于用户通常使用脱机诊断作为回退日志收集机制，用于当用户无法访问显示器、无法登录或仍在 OOBE 中时，收集日志时也会播放音频提示。 除了 toast 通知之外，还将播放此声音。

此新功能将在设备更新时启用，无需启用或管理。 如果无法显示或听到此新反馈，仍将生成脱机诊断。

我们希望通过这种新添加的 feedback 反馈，可以更轻松地收集诊断数据，并更快排查问题。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>仅将专用应用商店应用用于Microsoft Store

已启用 RequirePrivateStoreOnly 策略HoloLens。 此策略Microsoft Store应用配置为只显示为组织配置的专用存储。 仅将访问权限限制为可用的应用。

了解有关[ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)的详细信息

### <a name="fixes-and-improvements"></a>修复和改进：

- 修复了在 [未提示下载锁定文件的情况下设备门户的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 修复了 [包含文件上传和下载超时的设备门户的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- 解决与 HoloLens 设备报告符合性属性有关的问题;可能需要重新启动才能在内幕生成上触发正确的报告。  
- 更新了全新闪烁的远程协助的内置版本。


## <a name="start-receiving-insider-builds"></a>开始接收 Insider 内部版本

> [!NOTE]
> 如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。
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

1.  设置、更新 & 的安全 Windows 预览体验计划，请选择 "**发布预览通道**"。

2.  设置、更新 & 安全性、Windows 更新，**检查更新**。 更新后，继续执行第二阶段。

#### <a name="stage-two---dev-channel"></a>阶段两开发人员通道

1. 设置，请更新 & 安全 Windows 预览体验计划，然后选择 "**开发通道**"。

2. 设置、更新 & 安全性、Windows 更新，**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签名 ffu 进行测试，必须先将设备解锁，然后再闪烁飞行签名 ffu。

1. 在 PC 上：
    1. 从下载 ffu [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft Store 安装 ARC (高级恢复随附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. 在 HoloLens 航班解锁：打开 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。

1. Flash FFU-现在可以使用 ARC 来刷新已签名的飞行 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈和报告问题

请使用 HoloLens 上[的反馈中心应用](hololens-feedback.md)提供反馈和报告问题。 使用反馈中心可确保包括所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  HoloLens 中文版和日语版的问题应以相同的方式进行报告。

> [!NOTE]
> 请确保接受提示，询问你是否想要反馈中心访问文档文件夹 (在出现) 提示时选择 **"是"** 。

## <a name="note-for-developers"></a>开发人员注意事项

欢迎并鼓励你尝试使用 HoloLens 的内部版本来开发应用程序。  若要开始，请查看[HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development)。 这些相同的说明适用于 HoloLens 的内部版本。  您可以使用您已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。

## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 内部版本

如果你不想再收到 Windows 全息的内部版本，你可以在 HoloLens 运行生产版本时选择退出，或者可以使用高级恢复助理[恢复设备](hololens-recovery.md)，以将设备恢复到 Windows 全息版的非有问必答版。

> [!CAUTION]
> 存在一个已知问题，即，手动重新安装全新预览版本后，从 Insider preview 版本注册的用户将会遇到蓝屏。 此后，它们必须手动恢复其设备。 有关是否受影响的详细信息，请查看此 [已知问题](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)的详细信息。

验证 HoloLens 是否正在运行生产版本：

1. 请参阅 **设置 > 系统 >**，并找到内部版本号。

1. [请参阅生产内部版本号的发行说明](hololens-release-notes.md)。

选择退出内幕生成：

1. 在运行生产生成的 HoloLens，请参阅 **设置 > 更新 & Security > Windows 预览体验计划**，并选择 "**停止内幕生成**"。

1. 按照说明选择设备。
