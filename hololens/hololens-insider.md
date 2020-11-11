---
title: Microsoft HoloLens 内部预览版
description: 开始使用预览体验计划是很简单的，以便为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162952"
---
# Microsoft HoloLens 内部预览版

欢迎使用适用于 HoloLens 的最新预览体验计划预览版！ 这是一种非常简单的功能 [，可提供](hololens-insider.md#start-receiving-insider-builds) 针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。

## Windows 预览体验计划发行说明

### 通过应用安装程序在 HoloLens 2 上安装应用
我们将在 Windows 全息版20H2 更新后立即发布应用安装程序功能。 我们正在 ** (应用安装程序) 添加新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。 默认情况下，此功能将 **在非托管设备上处于打开**状态。 为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。  

如果以下 **任何** 条件成立，设备将被视为 "托管"：
- MDM 已 [注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) 为 AAD

现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。  只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。  或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。

**应用程序安装说明。**

1.  确保你的设备不被视为托管设备
1.  确保 HoloLens 2 设备已开机且已连接到你的电脑
1.  确保已登录到 HoloLens 2 设备
1.  在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。   完成文件复制后，您可以断开设备连接
1.  从 HoloLens 2 设备打开 "开始" 菜单，选择 "所有应用"，然后启动 "文件资源管理器" 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用的左侧面板上，选择 "此设备"，然后导航到 "下载"。
1.  选择 yourapp 文件。
1.  应用安装程序将启动。 选择 "安装" 按钮以安装你的应用。
已安装的应用将在安装完成后自动启动。

你可以在 [Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到示例应用来测试此流程。

有关 [在 HoloLens 2 上安装应用](app-deploy-app-installer.md)的完整过程，请参阅应用安装程序。  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

## 开始接收 Insider 内部版本

> [!NOTE]
> 如果您最近未进行更新，请重启设备以更新状态并获取最新版本。
> - "重新启动设备" 语音命令的效果很好。 
> - 您也可以选择 "设置/Windows 预览体验计划" 中的 "重新启动" 按钮。
>
> 我们在可能遇到的后端遇到错误，这将使你恢复进度。

在 HoloLens 2 设备上，转到 "**设置**"  >  **更新 & 安全**  >  **Windows 预览体验计划**"，然后选择"**开始**"。 将用于注册的帐户链接到 Windows 预览体验成员。

Windows 预览体验成员现在正在移至频道。 **快速**环将成为**开发频道**，**慢速**环将成为**Beta 通道**，并且 "**发布预览**" 环将成为 "**发布" 预览频道**。 映射如下所示：

![Windows 预览体验计划频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 Windows 博客上的 [Windows 预览体验成员频道简介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

然后，选择 " **Windows 的活动开发**"，选择是要接收 **开发渠道** 还是 **Beta 频道** 内部版本，并查看计划条款。

选择 " **确认" > "立即重启** " 完成。 重新启动设备后，转到 " **设置" > 更新 & 安全 > 检查更新** 以获取最新版本。

## FFU 下载和快闪路线
若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。
1. 在 PC 上：

    1. 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft Store 安装 ARC (高级恢复配套) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。

1. Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁。

## 提供反馈和报告问题

请使用 HoloLens 上 [的 "反馈中心" 应用](hololens-feedback.md) 提供反馈和报告问题。 使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。

> [!NOTE]
> 请务必接受询问是否希望 "反馈中心" 访问你的 "文档" 文件夹的提示 (在出现提示时选择 **"是"**) 。

## 适用于开发人员的备注

欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。 这些相同的说明适用于 HoloLens 的预览体验计划版本。  你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。

## 停止接收 Insider 内部版本

如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将 [设备恢复到](hololens-recovery.md) 非预览体验的 windows 全息版。

> [!CAUTION]
> 在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。 之后，他们必须手动恢复其设备。 有关如果你受到影响或不受影响的详细信息，请查看有关此 [已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。

若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：

1. 转到 " **设置" > "系统 >**"，然后找到内部版本号。

1. [请参阅生产内部版本号的发行说明](hololens-release-notes.md)。

若要退出预览体验计划内部版本，请执行以下操作：

1. 在运行生产版本的 HoloLens 上，转到 " **设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 " **停止预览体验成员版本**"。

1. 按照说明选择退出您的设备。
