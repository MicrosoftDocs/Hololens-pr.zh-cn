---
title: HoloLens 已知问题
description: 及时了解使用 Unity 和 Windows Device Portal 的可能影响 HoloLens 客户和开发人员的已知问题和解决方法列表。
keywords: 疑难解答， 已知问题， 帮助
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284073"
---
# HoloLens 已知问题

这是 HoloLens 设备的已知问题的当前列表。 如果看到奇数行为，请首先查看此处。 随着发现或报告新问题，或在将来的 HoloLens 软件更新中解决问题，此列表将保持更新。

>[!NOTE]
> - 如果你发现未阻止的问题，请通过反馈中心在 HoloLens 设备上 [报告它](hololens-feedback.md)。
> - 如果你所面临的问题是阻止你，除了归档反馈外， [请提交支持请求](https://aka.ms/hlsupport)。

- [所有 HoloLens 代的已知问题](#known-issues-for-all-hololens-generations)
- [HoloLens 2 设备的已知问题](#known-issues-for-hololens-2-devices)
- [HoloLens 第一代 (已知) ](#known-issues-for-hololens-1st-gen)
- [HoloLens 仿真器已知问题](#known-issues-for-hololens-emulator)

## 所有 HoloLens 代的已知问题

### Unity

- 请参阅 [安装适用于](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens 开发建议最新版本的 Unity 的工具。
- Unity HoloLens Technical Preview 的已知问题记录在 [HoloLens Unity 论坛中](https://forum.unity3d.com/threads/known-issues.394627/)。

### Windows Device Portal

- 混合现实捕获中的实时预览功能可能会显示几秒钟的延迟。

- 在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。 使用它们将不起作用。 同一页面上的虚拟键盘可以正常工作。

- 在"设置"中启用开发人员模式后，可能需要几秒钟的时间才能启用打开 Device Portal 的开关。

### OneDrive 相机上传

适用于 HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动相机上载。

解决方法：

- 如果适用于你的企业，则 Microsoft 消费者帐户支持自动相机上载。 除了工作或学校帐户外，还可以登录 Microsoft 帐户 (OneDrive 应用支持双重登录) 。 在 OneDrive 内的 Microsoft 帐户配置文件中，你可以启用自动后台相机照片上传。

- 如果无法安全地使用消费者 Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。 为此，请确保你已登录到 OneDrive 应用中的工作或学校帐户。 选择该 **+** 按钮，然后选择"**上载"。** 通过导航到"图片"或"相机照片"> **要上载的照片或视频**。 选择要上载的照片或视频，然后选择"打开 **"** 按钮。

## HoloLens 2 设备的已知问题

### Microsoft Edge 无法启动

一些客户报告了 Microsoft Edge 无法启动的问题。 对于这些客户，此问题通过重新启动而仍然存在，并且无法通过 Windows 或应用程序更新解决。 如果你遇到此问题，并且已确认[Windows](hololens-updates.md#manually-check-for-updates)是最新的，请从反馈中心应用提交具有以下类别和子类别的 Bug：[](hololens-feedback.md)安装和更新 > 下载、安装和配置 Windows 更新。

没有已知的解决方法，因为到目前为止，我们一直无法找出问题的根本原因。 通过反馈中心归档 Bug 将有助于我们的调查！

### 键盘不切换到特殊字符

OOBE 期间存在一个问题，在用户选择工作或学校帐户并输入其密码后，尝试通过点击 &123 按钮切换到键盘上的特殊字符不会更改为特殊字符。 

工作：：
-   关闭键盘，然后通过点击文本字段重新打开它。
-   输入的密码不正确。 下次重新启动键盘时，键盘将正常工作。
- Web 身份验证，关闭键盘，然后选择 **"从另一台设备登录"。** 
-   如果仅输入数字，用户可以长按某些键以打开展开的菜单。
-   使用 USB 键盘。

这不会影响：
- 选择使用个人帐户的用户。

### 从预览体验成员预览版注销后，在使用预览体验成员内部版本重新更新的设备上显示蓝屏

This is an issue affecting that affects users who are on an Insider preview build， reflashed their HoloLens 2 with a new insider preview build， and then unenrolled from the Insider program. 

这不会影响：
- 未在 Windows 预览体验成员中注册的用户 
- 预览体验成员：
    - 如果设备自预览体验成员版本版本 18362.x 起已注册
    - 如果他们刷新了预览体验成员签名的 19041.x 版本，并一直注册预览体验计划 

工作： 
- 避免此问题 
    - 刷新非内部版本。 每月定期更新之一。 
    - 保持预览体验成员
- 重新放大设备

    1. 在未连接时完全关闭电源，将 [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 手动置于闪烁模式。 然后，在保持音量的同时，点击电源按钮。
    
    1. 连接到电脑并打开"高级恢复助手"。 
    
    1. 将 HoloLens 2 闪烁为默认版本。   

## HoloLens 第一代 (已知) 

### 无法通过客户端连接到 HoloLens Visual Studio

> [!NOTE]
> Last Update： 8/8 @ 5：11PM - Visual Studio 已发布 VS 2019 版本 16.2，其中包括解决此问题的修补程序。 我们建议更新到此最新版本以避免遇到此错误。

Visual Studio VS 2019 版本 16.2，其中包含解决此问题的修补程序。 我们建议更新到此最新版本以避免遇到此错误。

问题的根本原因：使用 Visual Studio 2015 或早期版本的 Visual Studio 2017 在 HoloLens 上部署和调试应用程序，然后使用具有相同 HoloLens 的 Visual Studio 2017 或 Visual Studio 2019 的最新版本的用户将受到影响。 较新版本的 Visual Studio部署新版本的组件，但较旧版本的文件将留在设备上，从而导致较新版本失败。  这将导致以下错误消息：DEP0100：请确保目标设备已启用开发人员模式。 由于错误 \<ip\> 80004005，无法获取开发人员许可证。

#### 解决方法

Our team is currently working on a fix. 在此期间，可以使用以下步骤解决该问题，并帮助取消阻止部署和调试：  

1. 打开 Visual Studio。

1. 选择 **"**  >  **文件新建**  >  **项目"。**

1. 选择**Visual C#**  >  **Windows 桌面**  >  **控制台应用 (.NET Framework) 。 **

1. 为项目命名 (例如"HoloLensDeploymentFix") 并确保框架至少设置为 .NET Framework 4.5，然后选择"确定 **"。**

1. 右键单击解决方案**** 资源管理器中的"引用"节点，将以下引用 ("浏览"部分，然后选择****"浏览) ： ****

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果未安装 10.0.18362.0，请使用最新版本。 

1. 右键单击解决方案资源管理器中的项目，然后选择 **"添加**  >  **现有项目"。**

1. 浏览到 C：\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86，将筛选器更改为所有**文件 (\*.\*) 。 **

1. 选择"SirepClient.dll和SshClient.dll，然后选择"添加 **"。**

1. 在解决方案资源管理器中查找并选择这两个文件 (它们应位于文件列表的底部) 将"属性"窗口中的"复制到输出目录"**** 更改为"始终**复制"。** ****

1. 在文件顶部，将以下内容添加到现有语句 `using` 列表中：

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 在 `static void Main(...)` 内部，添加以下代码：

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 选择**生成**  >  **解决方案**。

1. 打开命令提示符窗口，将 cd 打开到包含已编译的 .exe 文件 (例如 C：\MyProjects\HoloLensDeploymentFix\bin\Debug) 。

1. 运行可执行文件，并提供设备的 IP 地址作为命令行参数。  (如果使用 USB 进行连接，可以使用 127.0.0.1，否则使用设备的 Wi-Fi IP 地址。) 例如，"HoloLensDeploymentFix 127.0.0.1"。

1. 在该工具退出后，没有任何消息 (此操作仅需要几秒钟) ，现在您将能够从 Visual Studio 2017 或更高版本进行部署和调试。  不需要继续使用该工具。

我们将在更新可用时提供进一步更新。

### 在 HoloLens 上启动 Microsoft Store 和应用时的问题

> [!NOTE]
> 上次更新：4/2 @ 10 AM - 问题已解决。 

尝试在 HoloLens 上启动 Microsoft Store 和应用时可能会遇到问题。 我们已确定当后台应用更新在一个或多个从属应用仍在运行时以特定顺序部署较新版本的框架包时，会出现此问题。 在这种情况下，自动应用更新将新版本的 .NET Native Framework (版本 10.0.25531 传递到 10.0.27413) 导致正在运行的应用无法正确更新使用以前版本的框架的所有正在运行的应用。  框架更新流程如下所示： 

1. 新框架包从应用商店下载并安装。

1. 使用旧框架的所有应用都"更新"为使用较新版本。

如果步骤 2 在完成之前中断，则任何未注册较新框架的应用将无法从"开始"菜单启动。  我们认为 HoloLens 上的任何应用都可能会受此问题的影响。

一些用户已报告关闭挂起的应用并启动其他应用（如反馈中心、3D 查看器或照片）可解决他们的问题，但是，这 &mdash; 100% 不起作用。

我们已找到根本原因，导致此问题不是由更新本身引起的，而是操作系统中的一个缺陷，导致未正确处理 .NET Native framework 更新。 我们很高兴地宣布我们已确定修补程序，并发布了包含 (操作系统版本 17763.380) 更新。  

若要了解你的设备能否接受更新，请：

1. 转到"设置"应用并打开"&**安全"。**

1. 选择 **"检查更新"。**

1. 如果更新到 17763.380 可用，请更新到此内部版本，以接收应用挂起 Bug 的修复。

1. 更新到此版本的操作系统后，应用应能正常工作。

此外，与处理每个 HoloLens 操作系统版本一样，我们已将 FFU 映像张贴到 [Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果你不希望进行更新，我们自 2019 年 3 月 29 日发布新版本的 Microsoft Store UWP 应用。 拥有应用商店的更新版本后：

1. 打开应用商店并确认它已加载。
1. 使用花红手势打开菜单。
1. 尝试打开以前损坏的应用。
1. 如果仍然无法启动，请点击并按住损坏应用的图标，然后选择卸载。
1. 从应用商店重新安装这些应用。

如果你的设备仍然无法加载应用，你可以按照以下步骤通过下载中心旁加载 .NET Native Framework 和运行时的版本：

1. 请从 Microsoft [下载中心](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 下载此 zip 文件。 解压缩将生成两个文件。  Microsoft.NET.Native.Runtime.1.7.appx 和 Microsoft.NET.Native.Framework.1.7.appx。

1. 请验证你的设备是否解锁了开发。  如果你之前没有这样做，请参阅使用 Windows [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 了解说明。

1. 然后，你想要进入 Windows Device Portal。 我们的建议是使用 USB 进行此操作，你将通过键入浏览器 http://127.0.0.1:10080 来完成此操作。

1. 安装 Windows Device Portal 后，我们需要你"旁加载"你下载的两个文件。 为此，你需要转到左侧栏，直到到达"应用"部分并选择"**应用"。** ****

1. 然后，你将看到类似于下面的屏幕。  你想要转到"安装应用"部分，并**** 浏览到解压缩这两个 APPX 文件的位置。 一次只能执行一个操作，因此选择第一个后，单击"部署"部分下的"转到"。 然后为第二个 APPX 文件执行此操作。

   ![Windows Device Portal 以安装Side-Loaded应用](images/20190322-DevicePortal.png)
   
1. 此时，我们认为你的应用程序应该重新开始工作，并且你还可访问应用商店。

1. 在某些情况下，在受影响的应用启动之前，必须运行启动 3D 查看器应用的额外步骤。 

感谢你耐心等待，在我们完成解决此问题的过程中，并期待继续与社区合作，以创造成功的混合现实体验。

### 设备更新

- 新更新后 30 秒，命令行管理程序可能会消失一次。 Please perform the **bloom** gesture to resume your session.

### Visual Studio

- 请参阅 [安装适用于](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens 开发Visual Studio最新版本的工具。

- 将应用从 Visual Studio 部署到 HoloLens 时，你可能会看到错误：无法在用户映射分区打开的文件上执行请求的操作 **。 (HRESULT 的异常：0x800704C8) 。 ** 如果发生这种情况，请重试，部署通常会成功。

### API

- 如果应用程序 [将焦点设置](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 在用户后面或普通到 camera.forward，全息影像将不会显示在混合现实捕获照片或视频中。 在 Windows 中修复此 bug 之前，如果应用程序[](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)主动设置对焦点，它们应确保将平面法线设置为与相机前进方向相反 (例如 normal = -camera.forward) 。

### Xbox 无线控制器

- Xbox 无线控制器 S 必须先更新，然后才能与 HoloLens 一起使用。 在尝试 [将控制器](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 与 HoloLens 配对之前，请确保你为最新版本。

- 如果在连接 Xbox 无线控制器时重新启动 HoloLens，控制器不会自动重新连接到 HoloLens。 "指南"按钮指示灯将缓慢闪烁，直到控制器在 3 分钟后关闭电源。 若要立即重新连接控制器，请按住"指南"按钮关闭控制器，直到灯关闭。 当你再次打开控制器时，它将重新连接到 HoloLens。

- 如果你的 HoloLens 在 Xbox 无线控制器连接时进入待机状态，控制器上的任何输入都将唤醒 HoloLens。 使用完控制器后，可以通过关闭控制器来阻止这种情况。

## HoloLens 仿真器已知问题

- 并非所有 Microsoft Store 中的应用都与仿真器兼容。 例如，Young Conker 和 Fragments 在仿真器上不可播放。
- 无法在仿真器中使用电脑摄像头。
- Windows Device Portal 的"实时预览"功能对仿真器不起作用。 你仍然可以捕获混合现实视频和图像。
