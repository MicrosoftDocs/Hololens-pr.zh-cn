---
title: '第一代HoloLens (的已知) '
description: 随时了解已知问题和解决方法的列表，这些问题和解决方法可能会影响HoloLens Unity 和 Windows 设备门户。
keywords: 疑难解答、已知问题、帮助
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189284"
---
# <a name="known-issues-for-hololens-1st-gen"></a>第一代HoloLens (的已知) 

下面是设备当前已知问题HoloLens列表。 如果看到异常行为，请首先查看此处。 发现或报告新问题时，或者随着将来在软件更新中解决问题，此列表HoloLens更新。

>[!NOTE]
> - 如果发现未阻止的问题，请通过 HoloLens 在设备上[反馈中心。](hololens-feedback.md)
> - 如果你所面临的问题阻止你，除了提交反馈外， [请提交支持请求](https://aka.ms/hlsupport)。


- [所有新代的HoloLens问题](#known-issues-for-all-hololens-generations)
- [第一代HoloLens (的已知) ](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>所有新代的HoloLens问题

### <a name="unity"></a>Unity

- 请参阅[安装工具](/windows/mixed-reality/install-the-tools)，了解建议用于开发HoloLens最新版本的 Unity。
- Unity HoloLens Technical Preview 的已知问题记录在[HoloLens Unity 论坛中](https://forum.unity3d.com/threads/known-issues.394627/)。

### <a name="windows-device-portal"></a>Windows 设备门户

- 混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。

- 在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。 使用它们将不起作用。 虚拟输入页上的虚拟键盘正常工作。

- 在 设置 中启用开发人员模式后，可能需要几秒钟时间，开关才能启用设备门户模式。

### <a name="onedrive-camera-upload"></a>OneDrive相机上传

OneDrive应用HoloLens工作或学校帐户的自动相机上传。

解决方法：

- 如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。 除了工作或学校帐户Microsoft 帐户，还可以登录到 (OneDrive 应用支持双重登录) 。 在Microsoft 帐户配置文件OneDrive启用自动后台相机滚动上传。

- 如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从应用将照片手动上传到工作或OneDrive帐户。 为此，请确保已登录到 OneDrive 应用的工作或学校帐户。 选择按钮 **+** 并选择 **"Upload"。** 通过导航到"照片"和"相机滚动> **上传的照片或视频**。 选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。

## <a name="known-issues-for-hololens-1st-gen"></a>第一代HoloLens (的已知) 

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>无法通过连接连接HoloLens部署到Visual Studio

> [!NOTE]
> 上次更新：8/8 @ 5：11PM - Visual Studio 已发布 VS 2019 版本 16.2，其中包括此问题的修补程序。 建议更新到此最新版本，以避免遇到此错误。

Visual Studio VS 2019 版本 16.2，其中包括此问题的修复。 建议更新到此最新版本，以避免遇到此错误。

问题根本原因：使用 Visual Studio 2015 或 Visual Studio 2017 早期版本在 HoloLens 上部署和调试应用程序，然后使用最新版本的 Visual Studio 2017 或 Visual Studio 2019 与同一 HoloLens 的用户将受到影响。 较新版本的 Visual Studio部署组件的新版本，但旧版本中的文件会留在设备上，从而导致较新版本失败。  这将导致以下错误消息：DEP0100：确保目标设备已启用开发人员模式。 由于出现错误，无法获取开发人员 \<ip\> 80004005。

#### <a name="workaround"></a>解决方法

我们的团队目前正在致力于修复。 在此期间，可以使用以下步骤来解决此问题，并帮助取消阻止部署和调试：  

1. 打开 Visual Studio。

1. 选择“文件” > “新建” > “项目”  。

1. 选择 **"Visual C#**  >  **Windows**  >  **桌面控制台应用 (.NET Framework) "。**

1. 为项目命名 (例如"HoloLensDeploymentFix") 并确保框架至少设置为 .NET Framework 4.5，然后选择"确定 **"。**

1. 右键单击"引用"节点，解决方案资源管理器"浏览"部分 (选择"浏览"部分并添加以下 **) ：**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果未安装 10.0.18362.0，请使用最新版本。

1. 右键单击项目中的项目解决方案资源管理器并选择"**添加**  >  **现有项"。**

1. 浏览到 C：\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86，将筛选器更改为"所有文件 **(\* \* .) "。**

1. 选择"SirepClient.dll和SshClient.dll"，然后选择"添加 **"。**

1. 找到并选择这两个文件解决方案资源管理器 (它们应位于文件列表的底部，) "属性"窗口中的"复制到输出目录"更改为"**始终复制"。** 

1. 在文件顶部，将以下内容添加到语句的现有 `using` 列表中：

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 在 `static void Main(...)` 内，添加以下代码：

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 选择“生成” > “生成解决方案” 。

1. 打开命令提示符窗口，将 cd 打开到包含已编译 .exe 文件的文件夹 (例如 C：\MyProjects\HoloLensDeploymentFix\bin\Debug) 。

1. 运行可执行文件，并提供设备的 IP 地址作为命令行参数。  (如果使用 USB 进行连接，可以使用 127.0.0.1，否则请使用设备的 Wi-Fi IP 地址。) 例如，"HoloLensDeploymentFix 127.0.0.1"。

1. 在该工具退出且没有任何消息 (此操作只需几秒钟) ，现在即可从 Visual Studio 2017 或更高版本进行部署和调试。  不需要继续使用该工具。

当更新可用时，我们将提供进一步更新。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>在 Microsoft Store 上启动应用HoloLens

> [!NOTE]
> 上次更新时间：4/2 @ 上午 10 点 - 问题已解决。

尝试在 HoloLens 上启动 Microsoft Store 应用时可能会遇到HoloLens。 我们已确定，当后台应用更新部署特定序列中较新版本的框架包时，当一个或多个依赖应用仍在运行时，会出现此问题。 在这种情况下，自动应用更新将新版本的 .NET Native Framework (版本 10.0.25531 传递到 10.0.27413) 导致正在运行的应用无法正确更新使用以前版本的框架的所有正在运行的应用。  框架更新流程如下所示：

1. 新框架包从存储区下载并安装。

1. 使用较旧框架的所有应用都"更新"为使用较新版本。

如果步骤 2 在完成之前中断，则任何未注册较新框架的应用将无法从开始菜单启动。  我们认为任何应用HoloLens可能会受此问题的影响。

一些用户报告，关闭挂起的应用并启动其他应用（例如 反馈中心、3D 查看器 或照片）可解决他们的问题 - 但是，这不能 100% 地正常工作。

我们的根本原因是，此问题不是由更新本身引起的，而是 OS 中的一个 bug，导致错误.NET Native框架更新。 我们很高兴地宣布，我们已确定一个修补程序，并发布了包含 (OS 版本 17763.380) 更新。  

查看设备能否进行更新：

1. 转到应用设置，打开"**更新&安全性"。**

1. 选择 **"检查更新"。**

1. 如果更新到 17763.380 可用，请更新到此内部版本，以接收应用挂起 bug 的修补程序。

1. 更新到此版本的 OS 后，应用应可正常工作。

此外，与每次发布 OS HoloLens一样，我们已将 FFU 映像发布给 Microsoft[下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果想进行更新，我们将于 3 月 29 日Microsoft Store UWP 应用的新版本。 拥有 Store 的更新版本后：

1. 打开 Store 并确认它已加载。
1. 使用布满手势打开菜单。
1. 尝试打开以前损坏的应用。
1. 如果仍然无法启动，请点击并按住损坏应用的图标，然后选择"卸载"。
1. 从应用商店重新安装这些应用。

如果设备仍无法加载应用，可以按照以下步骤.NET Native下载中心旁加载 .NET Native Framework 和 Runtime 的版本：

1. 请从 Microsoft [下载中心](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 下载此 zip 文件。 解压缩将生成两个文件。  Microsoft .NET.Native.Runtime.1.7.appx 和 Microsoft .NET.Native.Framework.1.7.appx。

1. 请验证设备是否解锁了开发。  如果之前尚未这样做，[请参阅使用Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)了解说明。

1. 然后，你需要进入Windows 设备门户。 我们的建议是使用 USB 实现此目标，为此，请键入 http://127.0.0.1:10080 浏览器。

1. 安装好Windows 设备门户，我们需要你"旁加载"下载的两个文件。 为此，需要向下转到左侧栏，直到转到"应用 **"部分并选择**"应用 **"。**

1. 随后会看到类似于下面的屏幕。  要转到 " **安装应用程序** " 部分，并浏览到解压这两个 APPX 文件的位置。 你一次只能执行一个操作，因此在选择第一个项后，在 "部署" 部分下单击 "开始"。 然后对第二个 APPX 文件执行此操作。

   ![Windows用于安装 Side-Loaded 应用的设备门户。](images/20190322-DevicePortal.png)

1. 此时，我们相信您的应用程序应再次开始工作，您也可以访问应用商店。

1. 在某些情况下，在启动受影响的应用程序之前，需要运行额外的步骤来启动3D 查看器应用程序。

我们非常感谢你的耐心，因为我们已经完成了解决此问题的过程，我们期待继续与我们的社区合作，以创建成功的混合现实体验。

### <a name="device-update"></a>设备更新

- 30秒后，shell 可能会消失一次。 请执行 **布隆** 手势以恢复会话。

### <a name="visual-studio"></a>Visual Studio

- 请参阅安装适用于 HoloLens 开发的 Visual Studio 的最新版本的[工具](/windows/mixed-reality/install-the-tools)。

- 将 Visual Studio 中的应用部署到 HoloLens 时，可能会看到以下错误：**无法在已打开用户映射的文件中对文件执行所请求的操作。 (异常从 HRESULT： 0x800704C8)**。 如果发生这种情况，请重试，部署通常会成功。

### <a name="api"></a>API

- 如果应用程序将 [焦点](/windows/mixed-reality/focus-point-in-unity) 置于用户后面或 "正常" 设置为 "摄像"，则全息体将不会在混合现实捕获照片或视频中出现。 在 Windows 中修复此 bug 之前，如果应用程序主动设置了[焦点](/windows/mixed-reality/focus-point-in-unity)，则应确保平面正常设置为相对相机前 (例如，normal =-摄像) 。

### <a name="xbox-wireless-controller"></a>Xbox 无线控制器

- 必须先更新 Xbox 无线控制器，然后才能将其与 HoloLens 一起使用。 尝试将控制器与 HoloLens 配对之前，请确保你是[最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)新的。

- 如果在连接 Xbox 无线控制器时重新启动 HoloLens，控制器将不会自动重新连接到 HoloLens。 在3分钟后控制器关闭之前，"指南" 按钮指示灯会慢慢闪烁。 若要立即重新连接控制器，请关闭控制器电源，方法是按住 "指南" 按钮，直到指示灯亮起。 再次打开控制器时，它会重新连接到 HoloLens。

- 如果在连接 Xbox 无线控制器时 HoloLens 进入待机状态，则控制器上的任何输入都将唤醒 HoloLens。 使用完控制器后，可以通过关闭控制器来阻止此操作。

