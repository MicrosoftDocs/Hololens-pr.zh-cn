---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始使用预览体验内部版本，并为 HoloLens 的下一次主要操作系统更新提供有价值的反馈。
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924360"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用 HoloLens 的最新 Insider Preview 版本！ 它易于入门 [，](hololens-insider.md#start-receiving-insider-builds) 并为 HoloLens 的下一次主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows 预览体验成员发行说明

我们很高兴再次开始向 Windows 预览体验成员提供新功能。 新内部版本将前往开发和 Beta 通道获取最新更新。 我们将继续更新此页面，因为我们向新的内部版本添加更多功能Windows 预览体验成员更新。 准备好将这些更新混合到现实中， 

### <a name="csp-changes-on-hololens"></a>HoloLens 上的 CSP 更改
 
- 在内部Windows 预览体验成员中引入，20348.1403

#### <a name="devdetail-csp"></a>DevDetail 云解决方案提供商

DevDetail CSP 现在还会报告 HoloLens 设备上的免费存储空间。 这应该与设置应用的"存储"页中显示的值大致匹配。 下面是包含此信息的特定节点。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET) 

#### <a name="devicestatus-csp"></a>DeviceStatus 云解决方案提供商

DeviceStatus CSP 现在还报告主动连接 HoloLens 的 Wifi 网络的 SSID 和 BSSID。 下面是包含此信息的特定节点。

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

### <a name="fixes-and-improvements"></a>修复和改进：

- 修复 [了在未提示设备门户锁定文件时出现此问题的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 修复了 [文件上传设备门户下载的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>开始接收预览体验内部版本
> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新生成。
> - "重新启动设备"语音命令运行良好。 
> - 还可以选择"设置/设置"中的"重启"Windows 预览体验计划。
>
> 我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。

在设备上HoloLens 2"设置 **""更新**  >  **&"安全**  >  **Windows 预览体验计划并选择"****开始使用"。** 链接用于注册为 Windows 预览体验成员。
Windows 预览体验成员现在正在迁移到频道。 快速 **通道** 将成为 **开发通道**，慢速通道 **将成为** Beta 版频道通道，发布预览通道将成为 **发布预览通道**。 下面是该映射的外观：Windows 预览体验成员频道说明。有关详细信息，请参阅 Windows 博客Windows 预览体验成员 ![ ](images/WindowsInsiderChannels.png) [频道](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介绍。
然后，**选择"Windows** 的活动开发"，选择要接收开发通道还是Beta 版频道 **版本，** 并查看计划条款。
选择 **">立即重启** "以完成操作。 重启设备后，转到"设置">更新 **&"安全性>检查更新** 以获取最新生成。
### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题
如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。
#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版
1.  设置，更新&安全性，Windows 预览体验计划，选择"**发布预览通道"。**
2.  设置、更新&安全性、Windows 更新、 **检查更新**。 更新后，继续进入阶段 2。
#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道
1. 设置，更新&安全性，Windows 预览体验计划，选择 **"开发通道"。**
2. 设置、更新&安全性、Windows 更新、 **检查更新**。
## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明
若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。
1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从以下 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。
    
1. 在"HoloLens - 航班解锁 **：打开设置** 更新  >  **&安全** Windows 预览体验计划  >  注册，重启设备。
1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。
### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题
请使用 [HoloLens](hololens-feedback.md) 反馈中心应用提供反馈并报告问题。 使用 反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同方式报告中文版和日语版 HoloLens 的问题。
> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 
## <a name="note-for-developers"></a>开发人员说明
欢迎并鼓励你尝试使用 HoloLens 预览体验内部版本开发应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。 这些相同的说明与 HoloLens 的预览体验内部版本一致。  可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。
## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本
如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产版本时选择退出，或者可以使用高级[](hololens-recovery.md)恢复助手恢复设备，将设备恢复到 Windows Holographic 的非 Insider 版本。
> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 版本取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。
若要验证 HoloLens 是否正在运行生产内部版本，请运行：
1. 转到" **系统>设置>"关于"，** 并找到生成号。
1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。
选择退出预览体验内部版本：
1. 在运行生产内部运行的 HoloLens 上，转到"设置>更新&**安全> Windows 预览体验计划，** 然后选择"停止 **预览体验成员生成"。**
1. 按照说明选择退出设备。
