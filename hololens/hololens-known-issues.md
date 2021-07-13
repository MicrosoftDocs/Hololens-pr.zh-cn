---
title: " (第一代 HoloLens 的已知问题) "
description: 了解已知问题和解决方法的列表，该列表可能会影响使用 Unity 的客户和开发人员和 Windows 设备门户 HoloLens。
keywords: 故障排除、已知问题、帮助
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
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640298"
---
# <a name="known-issues-for-hololens-1st-gen"></a> (第一代 HoloLens 的已知问题) 

下面是 HoloLens 设备的已知问题的最新列表。 如果看到的是奇怪的行为，请先查看此处。 此列表将在发现或报告新问题时保持更新，或者在将来的 HoloLens 软件更新中解决了问题。

>[!NOTE]
> - 如果发现未阻止的问题，请通过[反馈中心](hololens-feedback.md)将其报告在 HoloLens 设备上。
> - 如果你面临的问题正在阻止你，则除了提供反馈外，请 [提交支持请求](https://aka.ms/hlsupport)。


- [所有 HoloLens 代的已知问题](#known-issues-for-all-hololens-generations)
- [ (第一代 HoloLens 的已知问题) ](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>所有 HoloLens 代的已知问题

### <a name="unity"></a>Unity

- 请参阅安装适用于 HoloLens 开发的最新 Unity 版本[工具](/windows/mixed-reality/install-the-tools)。
- [HoloLens unity 论坛](https://forum.unity3d.com/threads/known-issues.394627/)中介绍了 unity HoloLens Technical Preview 的已知问题。

### <a name="windows-device-portal"></a>Windows 设备门户

- 混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。

- 在 "虚拟输入" 页上，"虚拟手势" 部分下的手势和滚动控件不起作用。 使用它们将不起作用。 虚拟输入页上的虚拟键盘工作正常。

- 在设置中启用 "开发人员模式" 后，可能需要几秒钟才能打开设备门户。

### <a name="onedrive-camera-upload"></a>OneDrive 照相机上传

HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动照相机上传。

解决方法：

- 对于你的业务，在使用者 Microsoft 帐户上支持自动照相机上传。 除了使用工作或学校帐户外，还可以登录到 Microsoft 帐户 (OneDrive 应用支持双重登录) 。 在 OneDrive 内的 Microsoft 帐户配置文件中，你可以启用自动播放背景照相机滚动。

- 如果你不能安全地使用使用者 Microsoft 帐户来自动上载照片，你可以从 OneDrive 应用手动将照片上传到你的工作或学校帐户。 为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。 选择 "" **+** 按钮，然后选择 " **Upload**"。 通过导航到 " **照片" > 照相机滚动**"查找要上传的照片或视频。 选择要上传的照片或视频，然后选择 " **打开** " 按钮。

## <a name="known-issues-for-hololens-1st-gen"></a> (第一代 HoloLens 的已知问题) 

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>无法通过 Visual Studio 连接和部署到 HoloLens

> [!NOTE]
> 上次更新时间： 8/8 @ 5： Visual Studio 晚上11点已发布 VS 2019 版本16.2，其中包括对此问题的修复。 建议更新到此最新版本，以避免出现此错误。

Visual Studio 发布了 VS 2019 版本16.2，其中包括对此问题的修复。 建议更新到此最新版本，以避免出现此错误。

问题根本原因：使用 Visual Studio 2015 或早期版本的 Visual Studio 2017 的用户在其 HoloLens 上部署和调试应用程序，然后使用相同 Visual Studio 的最新版本 Visual Studio 2017 或 HoloLens 2019 将受到影响。 较新版本的 Visual Studio 会部署新版本的组件，但较旧版本中的文件将保留在设备上，导致较新版本失败。  这会导致出现以下错误消息： DEP0100：确保目标设备已启用开发人员模式。 由于错误80004005，无法获取开发人员许可证 \<ip\> 。

#### <a name="workaround"></a>解决方法

我们的团队当前正在努力解决问题。 同时，你可以使用以下步骤来解决此问题，并帮助取消阻止部署和调试：  

1. 打开 Visual Studio。

1. 选择“文件” > “新建” > “项目”  。

1. 选择 " **Visual c #**"  >  **Windows 桌面**  >  **控制台应用 (.NET Framework ")**"。

1. 为项目指定名称 (如 "HoloLensDeploymentFix" ) ，并确保框架至少设置为 4.5 .NET Framework，然后选择 **"确定"**。

1. 右键单击解决方案资源管理器中的 " **引用** " 节点，然后添加以下引用 (选择 " **浏览** " 部分并选择 " **浏览**) "：

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果尚未安装10.0.18362.0，请使用最新版本。

1. 在解决方案资源管理器中右键单击该项目，然后选择 "**添加**  >  **现有项**"。

1. 浏览到 C:\Program 文件 (x86) \ Windows Kits\10\bin\10.0.18362.0\x86，并将筛选器更改为 "**所有文件 (\* 。 \*)**"。

1. 选择 "SirepClient.dll" 和 "SshClient.dll"，然后选择 " **添加**"。

1. 找到并选择解决方案资源管理器中的两个文件 (它们应位于文件列表的底部) 并将 "**属性**" 窗口中的 "**复制到输出目录**" 改为 "**始终复制**"。

1. 在该文件的顶部，将以下内容添加到现有的语句列表中 `using` ：

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

1. 选择“生成” > “生成解决方案” 。

1. 打开一个命令提示符窗口，然后将 cd 放到包含已编译 .exe 文件的文件夹中 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。

1. 运行可执行文件，并提供设备的 IP 地址作为命令行参数。  (如果使用 USB 进行连接，则可以使用127.0.0.1，否则请使用设备的 Wi-Fi IP 地址。 ) 例如，"HoloLensDeploymentFix 127.0.0.1"。

1. 退出该工具而不使用任何消息 (仅需几秒钟时间) ，你现在便可以从 Visual Studio 2017 或更高版本进行部署和调试。  不需要继续使用该工具。

我们将在可用时提供更多更新。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>在 HoloLens 上启动 Microsoft Store 和应用程序时出现问题

> [!NOTE]
> 上次更新时间： 4/2 @ 10 点-已解决问题。

尝试在 HoloLens 上启动 Microsoft Store 和应用时可能会遇到问题。 我们确定，当后台应用程序更新在特定序列中部署较新版本的框架包，而其一个或多个从属应用仍在运行时，会出现此问题。 在这种情况下，自动应用更新将 .NET Native Framework (版本10.0.25531 的新版本传递到 10.0.27413) 导致正在运行的应用无法针对使用以前版本 Framework 的所有正在运行的应用进行正确更新。  用于框架更新的流程如下所示：

1. 新框架包将从应用商店下载并安装。

1. 使用较旧框架的所有应用程序都是 "更新"，以使用较新的版本。

如果步骤2在完成之前中断，则未注册新框架的任何应用都将无法从 "开始" 菜单启动。  我们相信 HoloLens 上的任何应用程序都可能受此问题影响。

某些用户已报告关闭挂起的应用程序并启动其他应用程序（如反馈中心、三维查看器或照片）解决了这些问题-但是，这不能在100% 的时间运行。

我们有根本原因导致此问题不是由更新本身引起的，而是操作系统中导致 .NET Native framework 更新处理不正确的 bug。 我们很高兴地宣布，我们已确定了一个修补程序，并且发布了一个更新 (操作系统版本 17763.380) 包含该修补程序。  

若要查看设备是否可以进行更新，请执行以下操作：

1. 请参阅设置应用并打开 **更新 & 安全**"。

1. 选择 " **检查更新**"。

1. 如果更新到17763.380，请更新到此版本以接收应用挂起 bug 的修补程序。

1. 更新到此版本的操作系统时，应用程序应按预期方式工作。

此外，与每个 HoloLens 操作系统版本一样，我们已将 FFU 图像发布到[Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果你不想进行更新，我们发布了 3/29 Microsoft Store UWP 应用的新版本。 更新版本的应用商店后：

1. 打开应用商店并确认它已加载。
1. 使用布隆笔势打开菜单。
1. 尝试打开以前中断的应用程序。
1. 如果仍无法启动，请点击并按住损坏的应用程序的图标，然后选择 "卸载"。
1. 从应用商店重新安装这些应用。

如果设备仍无法加载应用，则可以通过以下步骤，通过下载中心旁加载 .NET Native Framework 和运行时的版本：

1. 请从 Microsoft 下载中心下载 [此 zip 文件](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 。 解压缩会生成两个文件。  。 .Appx. .appx. .appx. .appx. .appx. .appx. .appx。

1. 请验证你的设备是否已进行开发解锁。  如果之前尚未执行此操作，请参阅[使用 Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)了解相关说明。

1. 然后，你需要进入 Windows 设备门户。 我们的建议是通过 USB 来完成此操作，可以通过在浏览器中键入来完成此操作 http://127.0.0.1:10080 。

1. 完成 Windows 设备门户后，我们需要你将下载的两个文件 "端加载"。 要执行此操作，需要向下滚动到 " **应用** " 部分，并选择 " **应用**"。

1. 随后会看到类似于下面的屏幕。  要转到 " **安装应用程序** " 部分，并浏览到解压这两个 APPX 文件的位置。 你一次只能执行一个操作，因此在选择第一个项后，在 "部署" 部分下单击 "开始"。 然后对第二个 APPX 文件执行此操作。

   ![Windows用于安装 Side-Loaded 应用的设备门户](images/20190322-DevicePortal.png)

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

