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
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636075"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用 HoloLens 的最新 Insider preview 版本！ 这是一种非常简单的[入门](hololens-insider.md#start-receiving-insider-builds)方法，为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows内幕发行说明

我们非常高兴地开始试验新功能，以便 Windows 的预览体验。 新版本将会试验到适用于最新更新的开发和测试渠道。 我们将继续更新此页面，因为我们将更多的功能和更新添加到 Windows 有问必答版本。 令人兴奋并准备好将这些更新混合到您的现实中。

| 功能                 | 说明                | 用户或方案 | 引入的生成 |
|-------------------------|----------------------------|--------------|------------------|
| [reporting HoloLens 详细信息的 CSP 更改](#csp-changes-for-reporting-hololens-details) | 用于查询数据的新 Csp | IT 管理员    | 20348.1403                 |
| [由 CSP 控制的自动登录策略](#auto-login-policy-controlled-by-csp) | 用于自动登录帐户 | IT 管理员 | 20348.1405 |
| [证书管理器的 PFX 文件支持](#pfx-file-support-for-certificate-manager) | 通过设置 UI 添加 PFX 证书 | 最终用户 | 20348.1405 |
| [查看 HoloLens 上设置的高级诊断报告](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看设备上的 MDM 诊断日志 | 疑难解答 | 20348.1405 |
| [脱机诊断通知](#offline-diagnostics-notifications) | 日志收集的视听反馈 | 疑难解答 | 20348.1405 |


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
> - 某些事件（例如，主要 OS 更新）可能需要指定的用户重新登录到设备，才能恢复自动登录行为。 
> - 仅 MSA 和 AAD 用户支持自动登录。

### <a name="pfx-file-support-for-certificate-manager"></a>证书管理器的 PFX 文件支持

在 Windows 有问必答版本20348.1405 中引入。 我们已向 [证书管理器添加了对证书管理器](certificate-manager.md) 的支持，以便现在使用 .pfx 证书。 当用户导航到 **设置**  >  **更新 & 安全**  >  **证书**，并选择 "**安装证书**" 时，UI 现在支持 .pfx 证书文件。
用户可以将包含私钥的 .pfx 证书导入到用户存储或计算机存储。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>查看 HoloLens 上设置的高级诊断报告

对于托管设备，在对行为进行故障排除时，确认应用了预期的策略配置是一个重要的步骤。 之前，此新功能必须通过 mdm 或附近的设备完成，然后再导出通过 **设置**  ->  **帐户**  >  **访问工作或学校** 收集的 mdm 诊断日志，并选择 "**导出管理日志** 并在附近的 PC 上查看"。

现在可以使用 Edge 浏览器在设备上查看 MDM 诊断。 若要更轻松地查看 MDM 诊断报告，请导航到 "访问" 工作或学校页面，然后选择 " **查看高级诊断报告**"。 这会在新的边缘窗口中生成并打开报表。

![在设置应用中查看高级诊断报告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>脱机诊断通知

此更新适用于称为 [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)的现有功能。 以前，用户已触发诊断收集或已完成，没有明确的指示器。
现已添加到 Windows 内部版本中，对于脱机诊断，有两种形式的视听反馈。 当收集开始和完成时，将显示第一个 toast 通知。 当用户登录并具有视觉对象时，将显示这些用户。

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![记录收集完成时 Toast。](./images/logcollection2.jpg)
 
由于用户经常会使用脱机诊断作为回退日志收集机制来访问显示器、无法登录或仍处于 OOBE 状态，因此在收集日志时也会播放音频提示。 除了 toast 通知外，还会播放此声音。

这项新功能将在设备更新时启用，不需要启用或管理。 如果无法显示或听不到此新反馈，则仍将生成脱机诊断。

我们希望这种新的视听反馈增加，更易于收集诊断数据，并能更快地解决问题。



### <a name="fixes-and-improvements"></a>修复和改进：

- 修复了在 [未提示下载锁定文件的情况下设备门户的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 修复了 [包含文件上传和下载超时的设备门户的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)


## <a name="start-receiving-insider-builds"></a>开始接收 Insider 内部版本

> [!NOTE]
> 如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。
> - "重新启动设备" 语音命令正常工作。 
> - 你还可以在设置/Windows 预览体验计划 "中选择" 重新启动 "按钮。
>
> 我们在你可能遇到的后端上遇到了一个错误，这会使你返回到 "跟踪"。

在 HoloLens 2 设备上，转到 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，并选择 "**入门**"。 将用于注册的帐户链接到 Windows 有问必答。

Windows 有问必答现在正在移至频道。 快速 **通道** 将成为 **开发通道**，慢速通道 **将成为** Beta 版频道通道，发布预览通道将成为 **发布预览通道**。 该映射如下所示：

![Windows预览体验成员频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅博客[上的预览Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。
然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 
选择 **">立即重启** "以完成操作。 重启设备后，转到"更新设置 >"&**安全性>检查更新** 以获取最新生成。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题

如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。

#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版

1.  设置"更新&安全性"，Windows 会员计划，选择"**发布预览通道"。**

2.  设置、更新&安全性、Windows更新、**检查更新**。 更新后，继续进入阶段 2。

#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道

1. 设置"更新&安全性"，选择Windows 会员计划"**开发通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。

1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。
    
1. 在HoloLens - 航班解锁：打开 **设置**  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens提供反馈并报告问题。 使用 反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。  请查看开发人员[HoloLens文档](https://developer.microsoft.com/windows/mixed-reality/development)开始。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手将设备恢复到[](hololens-recovery.md)Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 版本取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产内部版本：

1. 转到 **"设置 >系统>关于**"，并找到生成号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

选择退出预览体验内部版本：

1. 在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**

1. 按照说明选择退出设备。
