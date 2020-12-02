---
title: HoloLens 已知问题
description: 这是可能影响 HoloLens 客户和开发人员的已知问题的列表。
keywords: 疑难解答、已知问题、帮助
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
ms.openlocfilehash: e5450cc41406416ec1b6e7c0bd7c8205056cb7d4
ms.sourcegitcommit: bf9a784d1b5f221d0766c5ae90efa4e9a5979b84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194620"
---
# HoloLens 已知问题

这是用于 HoloLens 设备的已知问题的当前列表。 如果看到奇怪的行为，请先查看此处。 此列表将在发现或报告新问题时保持更新，或者在将来的 HoloLens 软件更新中解决问题。

>[!NOTE]
> - 如果发现未阻止的问题，请通过 [反馈中心](hololens-feedback.md)将其报告在 HoloLens 设备上。
> - 如果您所面临的问题是阻止您，除了归档反馈外，请 [提交支持请求](https://aka.ms/hlsupport)。

- [所有 HoloLens 生成的已知问题](#known-issues-for-all-hololens-generations)
- [HoloLens 2 设备的已知问题](#known-issues-for-hololens-2-devices)
- [HoloLens 的已知问题 (第一代) ](#known-issues-for-hololens-1st-gen)
- [HoloLens 模拟器的已知问题](#known-issues-for-hololens-emulator)

## 所有 HoloLens 生成的已知问题

### Unity

- 有关为 HoloLens 开发推荐的最新版本的 Unity，请参阅 [安装工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。
- 在 [Hololens unity 论坛](https://forum.unity3d.com/threads/known-issues.394627/)中记录了 Unity HoloLens 技术预览版的已知问题。

### Windows Device Portal

- 混合现实捕获中的实时预览功能可能会显示几秒钟的延迟。

- 在 "虚拟输入" 页面上，"虚拟手势" 部分下的 "手势" 和 "滚动" 控件不起作用。 使用它们将不起作用。 同一页面上的虚拟键盘工作正常。

- 在 "设置" 中启用开发人员模式后，可能需要几秒钟才能启用设备门户。

### OneDrive 相机上传

适用于 HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动照相机上载。

办法

- 如果你的企业可行，自动照相机上载在消费者 Microsoft 帐户上受支持。 除了你的工作或学校帐户外，你还可以登录到你的 Microsoft 帐户 (OneDrive 应用支持双重登录) 。 从 OneDrive 中的 Microsoft 帐户配置文件，你可以启用自动的后台相机滚动上载。

- 如果您无法安全地使用消费者 Microsoft 帐户自动上载您的照片，则可以手动将照片从 OneDrive 应用上载到您的工作或学校帐户。 若要执行此操作，请确保在 OneDrive 应用中登录到你的工作或学校帐户。 选择该 **+** 按钮，然后选择 " **上传**"。 导航到 " **照片" > "照相机卷筒**"，查找要上载的照片或视频。 选择要上传的照片或视频，然后选择 " **打开** " 按钮。

## HoloLens 2 设备的已知问题

### Microsoft Edge 启动失败

几名客户报告了 Microsoft Edge 启动失败的问题。 对于这些客户，通过重启时问题仍然存在，并且不会通过 Windows 或应用程序更新进行解决。 如果你遇到此问题，并且你已确认 [Windows 是最](hololens-updates.md#manually-check-for-updates)新的，请使用以下类别和子类别从 " [反馈中心" 应用](hololens-feedback.md) 中归档 Bug：安装和更新 > 下载、安装和配置 Windows 更新。

目前没有任何已知的解决方法，因为我们目前无法为此带来问题。 通过反馈中心归档 bug 将有助于我们进行调查！

### 键盘不切换到特殊字符

在 OOBE 期间存在一个问题，即用户选择了工作或学校帐户并输入其密码后，通过点击 &123 按钮不会更改为特殊字符，尝试切换到键盘上的特殊字符。 

解决方法：
-   关闭键盘，然后点击文本字段将其重新打开。
-   输入密码不正确。 下一次更高一筹键盘时，它将按预期工作。
- Web 身份验证，关闭键盘，然后 **从其他设备中选择 "登录**"。 
-   如果仅输入数字，则用户可以按住某些键以打开展开的菜单。
-   使用 USB 键盘。

这不会影响：
- 选择使用个人帐户的用户。

### 通过在具有预览体验计划的设备 reflashed 上的预览体验计划内部版本后显示的蓝色屏幕

这是影响到预览体验成员预览版中的用户的问题，reflashed 其 HoloLens 2 与新的预览体验计划版本，然后从预览体验计划 unenrolled。 

这不会影响：
- 未在 Windows 预览体验成员中注册的用户 
- 预览
    - 由于预览体验成员版本18362的设备已注册
    - 如果他们刷新了预览体验成员签名的19041版本，并保持已注册预览体验计划 

解决办法： 
- 避免此问题 
    - 快速刷新非预览体验成员内部版本。 常规的每月更新之一。 
    - 继续预览预览体验计划
- Reflash 设备

    1. 通过在不连接时完全关闭，将 [HoloLens 2 手动置于闪烁模式](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 。 然后，在按住音量时，点击 "电源" 按钮。
    
    1. 连接到电脑并打开高级恢复助理。 
    
    1. 将 HoloLens 2 闪存到默认内部版本。   

## HoloLens 的已知问题 (第一代) 

### 无法通过 Visual Studio 连接和部署到 HoloLens

> [!NOTE]
> 上次更新时间： 8/8 @ 5： 11PM-Visual Studio 已发布 VS 2019 版本16.2，其中包括对此问题的修复。 我们建议更新到此最新版本，以避免遇到此错误。

Visual Studio 已发布 VS 2019 版本16.2，其中包括对此问题的修复。 我们建议更新到此最新版本，以避免遇到此错误。

问题根本原因：使用 Visual studio 2015 或早期版本的 Visual Studio 2017 的用户在其 HoloLens 上部署和调试应用程序，随后使用同一 HoloLens 的最新版本的 Visual Studio 2017 或 Visual Studio 2019 将受到影响。 较新版本的 Visual Studio 部署了组件的新版本，但是较旧版本中的文件会保留在设备上，从而导致更新版本失败。  这将导致以下错误消息： DEP0100：请确保目标设备已启用开发人员模式。 由于错误80004005，无法获取开发人员许可证 \<ip\> 。

#### 解决方法

我们的团队目前正在努力解决问题。 在此期间，你可以使用以下步骤来解决此问题并帮助取消阻止部署和调试：  

1. 打开 Visual Studio。

1. 选择 "**文件**  >  **新建**  >  **项目**"。

1. 选择 " **Visual c #**  >  **Windows 桌面版**  >  **控制台应用 ( .net Framework) **。

1. 为项目提供一个名称 (如 "HoloLensDeploymentFix" ) ，确保框架至少设置为 .NET Framework 4.5，然后选择 **"确定"**。

1. 在 "解决方案资源管理器" 中右键单击 " **引用** " 节点，然后添加以下引用 (选择到 " **浏览** " 部分，然后选择 " **浏览** ") ：

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果尚未安装10.0.18362.0，请使用您拥有的最新版本。 

1. 在 "解决方案资源管理器" 中右键单击该项目，然后选择 "**添加**  >  **现有项**"。

1. 通过浏览找到 C:\Program 文件 (x86) \Windows Kits\10\bin\10.0.18362.0\x86，并将筛选器更改为 ** ( \ * \ * \ * ) 的所有文件 **。

1. 同时选择 "SirepClient.dll" 和 "SshClient.dll"，然后选择 " **添加**"。

1. 在 "解决方案资源管理器" 中找到并选择两个文件 (它们应位于文件列表的底部) 并将 "**属性**" 窗口中的 "**复制到输出目录**" 更改为 "**始终复制**"。

1. 在文件的顶部，将以下内容添加到现有语句列表中 `using` ：

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 在中 `static void Main(...)` ，添加以下代码：

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 选择 "**生成**  >  **生成解决方案**"。

1. 将命令提示符窗口和 cd 打开到包含已编译 .exe 文件的文件夹中 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。

1. 运行可执行文件，并以命令行参数的形式提供设备的 IP 地址。  (如果使用 USB 进行连接，则可以使用127.0.0.1，否则使用设备的 Wi-Fi IP 地址。 ) 例如，"HoloLensDeploymentFix 127.0.0.1"。

1. 在该工具退出后没有任何消息 (此操作只需几秒钟) ，您现在就可以从 Visual Studio 2017 或更高版本部署和调试。  无需继续使用该工具。

我们将提供进一步的更新，因为它们变得可用。

### 在 HoloLens 上启动 Microsoft Store 和应用时出现问题

> [!NOTE]
> 上次更新时间： 4/2 @ 10 点-问题已解决。 

尝试在 HoloLens 上启动 Microsoft Store 和应用时，可能会遇到问题。 我们已确定，当后台应用更新在特定序列中部署较新版本的 framework 程序包，而其一个或多个依赖应用仍在运行时，则会出现此问题。 在此情况下，自动应用更新向10.0.27413 提供了一个新版本的 .NET Native Framework (10.0.25531 到) ，从而导致使用以前版本的 Framework 的所有运行应用无法正确更新运行的应用。  框架更新流程如下所示： 

1. 将从应用商店下载并安装新的框架程序包。

1. 所有使用较旧框架的应用均 "更新" 为使用较新的版本。

如果步骤2在完成之前中断，则未注册较新框架的任何应用都将无法从 "开始" 菜单启动。  我们认为 HoloLens 上的任何应用都可能受此问题的影响。

某些用户已报告关闭挂起的应用并启动其他应用（如反馈中心、3D 查看器或照片）解决了这些应用的问题 &mdash; ，但这不会在100% 的时间起作用。

我们的根本原因导致此问题不会导致更新，但操作系统中导致 .NET Native framework 更新未正确处理的 bug。 我们很高兴地宣布我们已确定修补程序，并已发布 (OS 版本 17763.380) 包含该修补程序的更新。  

若要查看设备是否可以进行更新，请执行以下操作：

1. 转到 "设置" 应用，打开 " **更新 & 安全性**"。

1. 选择 " **检查更新**"。

1. 如果有17763.380 更新可用，请更新到此内部版本以接收应用挂起 bug 的修补程序。

1. 更新到此版本的操作系统后，应用应按预期工作。

此外，在每次 HoloLens 操作系统发布时，我们已将 FFU 映像发布到 [Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果您不想进行更新，我们发布了一个新版本的 Microsoft Store UWP 应用，3/29。 在拥有更新版本的应用商店后：

1. 打开应用商店并确认它已加载。
1. 使用绽放手势打开菜单。
1. 尝试打开以前损坏的应用。
1. 如果仍然无法启动，请点击并按住损坏的应用的图标，然后选择 "卸载"。
1. 从应用商店重新安装这些应用。

如果你的设备仍无法加载应用，你可以通过以下步骤通过下载中心旁加载 .NET Native Framework 和运行时的版本：

1. 请从 Microsoft 下载中心下载 [此 zip 文件](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 。 解压缩将产生两个文件。  Microsoft. .appx. .appx 和 .appx.-.appx.-.net.。

1. 请验证您的设备是否已进行开发解锁。  如果你之前未执行此操作，请参阅 [使用 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 获取说明。

1. 然后，你需要进入 Windows Device Portal。 我们建议通过 USB 执行此操作，并通过在浏览器中键入来执行此操作 http://127.0.0.1:10080 。

1. 在安装好 Windows Device Portal 之后，我们需要你已下载的两个文件 "端加载"。 若要执行此操作，您需要沿左侧栏，直到找到 " **应用** " 部分，然后选择 " **应用**"。

1. 然后，你将看到类似于下面的屏幕。  你希望转到表示 " **安装应用** " 的部分，并浏览到解压缩这两个 APPX 文件的位置。 一次只能执行一个操作，因此在选择第一个，然后单击 "部署" 部分下的 "开始"。 然后为第二个 APPX 文件执行此操作。

   ![用于安装 Side-Loaded 应用程序的 Windows Device Portal](images/20190322-DevicePortal.png)
   
1. 此时，我们认为你的应用程序应再次开始工作，并且你也可以访问应用商店。

1. 在某些情况下，在启动受影响的应用之前，需要运行其他启动3D 查看器应用的步骤。 

我们已完成解决此问题的过程，我们非常感谢你的耐心等待，我们期待继续与社区协作以创建成功的混合现实体验。

### 设备更新

- 新更新后30秒后，shell 可能会消失一次。 请执行 **绽放** 手势以恢复你的会话。

### Visual Studio

- 请参阅安装适用于 HoloLens 开发的最新版本 Visual Studio 的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。

- 从 Visual Studio 向 HoloLens 部署应用时，你可能会看到错误：无法对已 **打开用户映射区域的文件执行所请求的操作。 (异常来自 HRESULT： 0x800704C8) **。 如果发生这种情况，请重试，部署通常会成功。

### API

- 如果应用程序设置了用户 [关注的焦点](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 或将其设置为 "垂直于照相机"。转发，则全息图将不会在混合现实中捕获照片或视频。 在 Windows 中修复此 bug 之前，如果应用程序主动设置了 [焦点](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ，则应确保平面法线的设置不是相对的相机前向 (例如，正常 =-摄像机前) 。

### Xbox 无线控制器

- Xbox 无线控制器必须先更新，然后才能与 HoloLens 配合使用。 在尝试将控制器与 HoloLens 配对之前，请确保你处于 [最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 新状态。

- 如果您在 Xbox 无线控制器连接的情况下重新启动 HoloLens，控制器将不会自动重新连接到 HoloLens。 "辅助线" 按钮指示灯将慢慢地闪烁，直到控制器在3分钟后关机。 要立即重新连接控制器，请通过按住 "指南" 按钮来关闭控制器，直到指示灯熄灭。 再次打开控制器电源时，它将重新连接到 HoloLens。

- 如果你的 HoloLens 在 Xbox 无线控制器连接时进入待机状态，则控制器上的任何输入都将唤醒 HoloLens。 您可以通过在使用控制器后关闭控制器来阻止此操作。

## HoloLens 模拟器的已知问题

- 并非 Microsoft Store 中的所有应用都与模拟器兼容。 例如，不能在仿真器上播放年轻人 Conker 和片段。
- 您不能在仿真器中使用 PC 网络摄像头。
- Windows Device Portal 的实时预览功能不能与模拟器配合使用。 您仍然可以捕获混合现实视频和图像。
