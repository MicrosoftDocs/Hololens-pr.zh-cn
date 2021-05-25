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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397818"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用 HoloLens 的最新 Insider Preview 版本！ 它易于入门 [，](hololens-insider.md#start-receiving-insider-builds) 并为 HoloLens 的下一次主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows 预览体验成员发行说明

我们很高兴再次开始向 Windows 预览体验成员提供新功能。 新内部版本将前往开发和 Beta 通道获取最新更新。 我们将继续更新此页面，因为我们向新的内部版本添加更多功能Windows 预览体验成员更新。 准备好将这些更新混合到现实中， 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for Work or school Camera Roll upload

*在内部版本 20346.1402 中引入*

我们向 HoloLens 2 设置应用添加了一项新功能，使客户能够自动将混合现实照片和视频从设备的"图片">"相机滚动"文件夹上传到相应的 OneDrive for Work 或 school 文件夹。 此功能解决了 HoloLens 2 上的 [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) 应用中的功能差距，它仅支持自动将相机滚动上传到客户的个人Microsoft 帐户 (而不是工作或学校帐户) 。

**工作原理**

- 访问 **">系统> 混合现实相机** 设置"以启用"相机上传"。
- 将此功能设置为"打开"位置后，捕获到设备的任何混合现实照片或视频将自动排队，以上传到 OneDrive for Work 或 school 帐户的"图片"> 相机"Roll 文件夹。
    >[!NOTE]
    >启用此功能之前捕获的照片和视频不会排队等待上传，并且仍然需要手动上传。
- "设置"页上的状态消息将显示所有挂起的文件已上传到 (或读取"OneDrive 是最新的"（所有挂起的文件已上传到) ）。
- 如果担心带宽或出于任何原因想要"暂停"上传，可以将该功能切换到"关闭 **"** 位置。 临时禁用该功能可确保在将新文件添加到 "相机照片" 文件夹中时，上传队列将继续增加，但在重新启用该功能之前，将不会上载文件。
- 最新文件将首先上传 (最后一个) 。
- 例如，如果你的 OneDrive 帐户出现问题 (例如，) 更改密码后，"设置" 页上将显示 " **立即修复** " 按钮。
- 没有最大文件大小，但请注意，大文件上传会花费较长的时间，尤其是当上传带宽受到限制) 时 (。 如果在上载大型文件时 "暂停" 或关闭上载，则会立即取消上传。 重新启用此功能后，将重新启动上传;不会丢失任何文件，但会丢弃部分上传。

**已知问题和注意事项**

- 此设置没有基于当前带宽使用情况的内置限制。 如果需要将其他方案的带宽最大化，请手动关闭该设置。 上传将暂停，但该功能将继续监视新添加到相机的文件。 准备就绪后，请重新启用上传。
- 必须为设备上的每个用户帐户启用此功能，并且只能为当前已登录到设备的用户主动上载文件。
- 如果你正在拍摄照片或视频，同时在 "设置" 页上实时观看上传计数，请注意，在完成当前文件上传之前，挂起的文件数可能不会更改。
- 如果设备处于睡眠状态或关机，则上传将暂停。 若要确保挂起的上载完成，请主动使用设备，直到 "设置" 页显示 "OneDrive 是最新的" 或调整 **Power & 睡眠** 设置。

## <a name="start-receiving-insider-builds"></a>开始接收 Insider 内部版本
> [!NOTE]
> 如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。
> - "重新启动设备" 语音命令正常工作。 
> - 你还可以在 "设置/Windows 预览体验计划" 中选择 "重启" 按钮。
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
若要使用已签名 ffu 进行测试，必须先将设备解锁，然后再闪烁飞行签名 ffu。
1. 在 PC 上：
    1. 从下载 ffu [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft Store 安装 ARC (高级恢复随附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. 在 HoloLens 航班解锁：打开 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。
1. Flash FFU-现在可以使用 ARC 来刷新已签名的飞行 FFU。
### <a name="provide-feedback-and-report-issues"></a>提供反馈和报告问题
请使用 HoloLens 上 [的反馈中心应用](hololens-feedback.md) 提供反馈和报告问题。 使用反馈中心可确保包括所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  需要以相同的方式报告有关中国和日本版 HoloLens 的问题。
> [!NOTE]
> 请确保接受提示，询问你是否想要反馈中心访问文档文件夹 (在出现) 提示时选择 **"是"** 。
## <a name="note-for-developers"></a>开发人员注意事项
欢迎并鼓励你尝试使用 HoloLens 的内部版本开发应用程序。  若要开始，请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 。 这些相同的说明适用于 HoloLens 的内部版本。  你可以使用与你已用于 HoloLens 开发的 Unity 和 Visual Studio 相同的版本。
## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 内部版本
如果你不想再收到 Windows 全息的内部版本，你可以在你的 HoloLens 运行生产版本时选择退出，或者可以使用高级恢复助理 [恢复你](hololens-recovery.md) 的设备，以将设备恢复到非有问必答版 windows 全息版。
> [!CAUTION]
> 存在一个已知问题，即，手动重新安装全新预览版本后，从 Insider preview 版本注册的用户将会遇到蓝屏。 此后，它们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。
若要验证 HoloLens 是否正在运行生产内部版本，请运行：
1. 转到" **系统>设置>"关于"，** 并找到生成号。
1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。
选择退出预览体验内部版本：
1. 在运行生产内部运行的 HoloLens 上，转到"设置>更新&**安全> Windows 预览体验计划，** 然后选择"停止 **预览体验成员生成"。**
1. 按照说明选择退出设备。
