---
title: HoloLens 2 发行说明
description: 了解每个新 HoloLens 2 版本中的所有更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9ad1fd599605a82280fc3ce45a2b78fcd0be6f14
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400712"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

为了确保你拥有使用 HoloLens 设备的高效体验，我们将继续发布功能、Bug 和安全更新。 在此页面上，你可以看到 HoloLens 每月的新增功能。 若要获取最新的 HoloLens 2 更新，你可以检查更新并[手动](hololens-update-hololens.md#check-for-updates-and-manually-update)更新，或获取完整闪存更新 (FFU) 通过高级恢复助手快速刷新[设备。](hololens-recovery.md#clean-reflash-the-device) [下载](https://aka.ms/hololens2download)保持最新，并提供最新发布版本。

>[!NOTE]
> 我们很高兴再次开始向 Windows 预览体验成员提供新功能。 我们将测试到开发人员频道获取最新更新。 我们将继续使用 [**HoloLens 预览**](hololens-insider.md) 体验成员说明，因为我们向 Windows 预览体验成员版本添加更多功能和更新。 获得快感，并准备好将这些更新融合到你的现实中。

查看相关的发行说明：

- [访问 HoloLens 仿真器存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows 全息版版本 20H2 - 2021 年 3 月更新
- 内部版本 19041.1140

更新中的改进和修复：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 捕获 HoloLens 2 照片的客户现在可以在捕获照片后最多 3 秒检索相机。
- 修复了 Device Portal Service 中的内存泄漏，该问题导致服务的内存使用率增加，导致其他应用程序无法分配内存。
- 修复了在分步推出中注册的用户无法登录到设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows 全息版版本 1903 - 2021 年 3 月更新
- 内部版本 18362.1102

更新中的改进和修复：

- 修复了 Device Portal Service 中的内存泄漏，该问题导致服务的内存使用率增加，导致其他应用程序无法分配内存。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic 版本 20H2 - 2021 年 2 月更新
- 内部版本 19041.1136

更新中的改进和修复：

- 修复了有关初始设备设置和存储应用更新的问题。
- 解决了有关更高版本 HoloLens 的升级和测试版的问题。
- 从 HoloLens 设备的 eSIM 根存储中删除了未使用的预安装证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows 全息版版本 1903 - 2021 年 2 月更新
- 内部版本 18362.1098

此每月质量更新不包含任何值得注意的更改，我们鼓励你试用 Windows Holographic 版本 2004 的最新内部版本。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic 版本 20H2 - 2021 年 1 月更新
- 内部版本 19041.1134

更新中的改进和修复：

- 在设备上有许多用户时，在启动、恢复和用户切换期间提高性能。
- 添加了对研究模式的 arm32 [支持](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows 全息版版本 1903 - 2021 年 1 月更新
- 内部版本 18362.1091

此每月质量更新不包含任何值得注意的更改，我们鼓励你试用 Windows Holographic 版本 2004 的最新内部版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic 版本 20H2 – 2020 年 12 月更新
- 内部版本 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过应用安装程序在 HoloLens 2 上安装应用

我们正在 **向应用安装程序 (** 新功能) 允许你在 HoloLens 2 设备上更加无缝地安装应用程序。 默认情况下，非 **托管设备将启用此功能**。 为了防止企业中断，应用安装程序目前对 **托管设备** 不可用。  

如果以下任一情况为 true，则设备被视为"托管"设备： ****
- MDM [已注册](hololens-enroll-mdm.md)
- 使用预配 [包配置](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) 为 Azure AD

现在无需启用开发人员模式或使用 Device Portal 即可安装应用。  只需通过 USB (通过 Edge) Appx 捆绑包下载到设备，然后导航到文件资源管理器中的 Appx 捆绑包，以提示启动安装。  或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，需要使用签名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)工具对应用进行[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)数字签名，并且用于签名的证书必须受 HoloLens 设备信任，然后才能部署应用。

**应用程序安装说明。**

1.  确保设备未被视为托管设备
1.  确保 HoloLens 2 设备已打开并连接到电脑
1.  确保你已登录到 HoloLens 2 设备
1.  在电脑上导航到自定义应用，将 yourapp.appxbundle 复制到 yourdevicename\Internal Storage\Downloads。   复制完文件后，你可以断开设备连接
1.  从 HoloLens 2 设备打开"开始"菜单，选择"所有应用"并启动"文件资源管理器"应用。
1.  导航到"下载"文件夹。 你可能需要在应用的左侧面板上选择"此设备"，然后导航到"下载"。
1.  选择 yourapp.appxbundle 文件。
1.  应用安装程序将启动。 选择"安装"按钮以安装应用。
安装完成后，已安装的应用将自动启动。

可以在 Windows 通用示例 [GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到示例应用来测试此流。

阅读有关使用应用安装程序在 [HoloLens 2 上安装应用的完整过程](app-deploy-app-installer.md)。  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手部跟踪现在在许多新情况下保持跟踪，这些新情况下手以前会丢失。  在一些新情况下，仅根据用户的实际手继续更新手部位置，而其他连接根据上一个位置进行推断。  此更改有助于提高移动（如跳跃、抛出、跳跃和包打）的跟踪一致性。  它还有助于在手靠近表面或按住对象的情况下。  在推断手部连接时 [，每个联合](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度值将设置为"近似"，而不是"高"。
- 修复了 Azure AD 帐户的 PIN 重置将显示错误"出错"的问题。
- 在启动 ET、设置应用中的 Iris、新用户或通知 Toast 时，用户应看到更少的启动后 OOBE 崩溃。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic 版本 1903 – 2020 年 12 月更新
- 内部版本 18362.1088

此每月质量更新不包含任何值得注意的更改，我们鼓励你试用我们最新的 Windows 全息版版本 20H2 – 2020 年 12 月更新和内部版本中添加的新应用安装程序功能。


## <a name="windows-holographic-version-20h2"></a>Windows 全息版版本 20H2
- 内部版本 19041.1128

Windows Holographic 版本 20H2 现已发布，为 HoloLens 2 用户和 IT 专业人员带来了一组出色的新功能。 从自动目视定位到"设置"中的证书管理器，到改进的展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更精细地控制 HoloLens 设备的配置和管理，并为用户提供更加无缝的全息体验。 

此最新版本是版本 2004 的每月更新，但这次我们将包含新功能。 主要内部版本号将保持不变，Windows 更新将指示版本 2004 的每月版本 (版本 19041 版本) 。 可以在"设置">"关于"屏幕中查看内部版本号，以确认你已使用最新的可用内部版本 19041.1128+。 若要更新到最新版本，请打开"设置"应用，转到"&安全性"，然后点击"检查更新"。 若要详细了解如何管理 HoloLens 更新，请访问 [此页面](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows 全息版版本 20H2 中的新增功能  

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，无需用户进行目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许使用更简单的新方法来安装和删除"设置"应用中的证书。     |
| [从 USB 自动启动预配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 驱动器上的预配包会自动在 OOBE 中提示预配页面。                                                         |
| [在 OOBE 中自动确认预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配包会在 OOBE 期间从预配页面自动应用。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将预配自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi连接一起使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备设备使用 autopilot Wi-Fi无需以太网适配器。 |
| [Tenantlockdown 云解决方案提供商和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 在租户注册和应用策略后，设备每次重置或重新闪烁时只能在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个应用展台模式的新配置方法，该方法在系统级别应用展台，使其适用于所有应用展台。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置在登录多应用展台模式时自动启动。                                                        |
| [用于处理故障的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有严格的回退。                                                                                                |
| [HoloLens 策略](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新策略。     |
| [为脱机展台缓存 Azure AD 组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用组成员身份缓存在设置的天数内脱机使用展台模式。                                        |
| [HoloLens 2 的新设备限制策略](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 新启用 HoloLens 2 的设备管理策略。                                                                                |
| [HoloLens 2 的新电源策略](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允许控制更新的新启用策略。           |
| [HoloLens 2 的"已启用设置"页面可见性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选取在"设置"应用中显示的页面的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用"研究"模式。 |
| [录音长度增加](hololens-release-notes.md#recording-length-increased) | MRC 录制不再限定为 5 分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在 HoloLens 2 中，目视位置可实现准确的全息影像定位、舒适的观看体验和改进的显示质量。 目视位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过目视跟踪校准，即使体验可能不需要目视的注视输入也是如此。

**自动眼部位置 (AEP)** 使这些场景能够以无交互方式为用户眼部位置。 从用户戴上设备开始，“自动眼部位置”将自动在后台开始工作。 如果用户没有之前的眼球跟踪校准，自动目视位置将在 20-30 秒的处理时间后开始向显示系统提供用户的眼部位置。 用户数据不会保留在设备上，因此，如果用户取下并重新戴上设备，或者设备重新启动或从睡眠状态唤醒，则会重复此过程。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在这种情况下，未校准的用户指的是之前未在设备上完成眼球跟踪校准过程的人员。

| 活动应用程序 | 先前行为 | Windows 全息版 20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |“眼球跟踪校准提示”对话框随即显示。 | 不显示提示。 |
| 已启用凝视的应用 | “眼球跟踪校准提示”对话框随即显示。 | 仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。 

所有其他系统行为将类似于当前用户没有活动的眼球跟踪校准的情况。 例如，将不会启用单只手的开始手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛凝视数据或非常精确的全息影像位置的体验，我们建议未校准的用户运行眼球跟踪校准。 您可以通过眼球跟踪校准提示或从开始菜单启动设置应用程序，然后选择 **“系统” > “校准” > “眼球校准” > “运行眼睛球校准”**。

稍后可以使用其他校准信息 [找到此信息](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和合规性的审核、诊断和验证工具。 此功能使您能够在商业环境中大规模部署、排查和验证证书。

在 Windows 全息版 20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 转到" **设置>更新&安全>证书**。 此功能提供在设备上查看、安装和删除证书的简单且用户友好的方式。 借助新的证书管理器，管理员和用户现在改进了审核、诊断和验证工具，以确保设备保持安全与合规。 

-   **审核：** 验证证书是否正确部署或确认证书已正确删除的能力。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间，并有助于进行故障排除。 
-   **验证：** 在大规模部署证书之前，验证证书是否达到预期目的并正常运行，可以节省大量时间，尤其是在商业环境中。

若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。 用户还可以直接搜索证书。 若要查看单个证书属性，请选择证书并单击 **"信息"。** 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户中。 用户只能删除直接从"设置"UI 安装的证书。 如果证书是通过其他方式安装的，则还必须通过同一机制将其删除。

#### <a name="to-install-a-certificate"></a>若要安装证书，请运行： 

1.  将 HoloLens 2 连接到电脑。
1.  将你想要安装的证书文件放在 HoloLens 2 上的位置。
1.  导航到 **"设置>更新&安全>证书**，然后选择"安装证书"。
1.  单击 **"导入** 文件"并导航到保存证书的位置。
1.  选择 **"存储位置"。**
1.  选择 **证书存储**。
1.  单击**安装**。

现在应在设备上安装证书。

#### <a name="to-remove-a-certificate"></a>若要删除证书，请： 
1. 导航到 **设置应用>更新和安全>证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 **"删除"**
1. 当 **系统** 提示确认时，选择"是"。

!["设置"应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

稍后可在新的证书管理器页面上 [找到此信息](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动预配

- 在 OOBE 期间使用带预配包的 USB 驱动器时，自动化进程允许更少的用户交互。

在此版本之前，用户必须手动在 OOBE 期间启动预配屏幕，才能使用按钮组合进行预配。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个可交互时刻将 USB 驱动器与预配包一起插入
1. 当设备准备好预配时，它将使用预配页面自动打开提示。 

注意：如果在设备启动时 USB 驱动器被左插入，则 OOBE 将枚举现有的 USB 存储设备，并观察正在插入的其他 USB 存储设备。

有关在 OOBE 期间应用预配包的信息，请访问 [HoloLens 预配](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 文档。

有关从 [USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) 自动启动预配的其他信息，请参阅 HoloLens 预配文档。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>在 OOBE 中自动确认预配包
- 自动过程，允许更少的用户交互，当显示预配包页面时，它将自动应用列出的所有程序包。

当设置主屏幕显示时，OOBE 将倒计时 10 秒，然后自动开始应用所有预配包。 在验证 [预期的](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 程序包后，用户仍可在此 10 秒内确认或取消。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配
- 用于减少预配的设备交互的组合自动进程。 

通过将 USB 设备的预配自动启动和预配包的自动确认相结合，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至不会佩戴该设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这可用于在同一区域中同时部署多个设备。 

1. [使用 Windows 配置设计器](hololens-provisioning.md) 创建 [预配包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. 将程序包复制到 USB 存储驱动器。
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. 当 [高级恢复](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 助手完成设备闪烁时，请拔下 USB-C 电缆。 
1. 将 U 盘插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它将自动检测 USB 驱动器上的预配包并启动预配页面。
1. 10 秒后，设备将自动应用预配包。 

你的设备现已配置， [并显示"预配成功"屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi连接一起使用
- 通过使 Autopilot 在连接的设备上运行，无需 USB-C 适配器来减少Wi-Fi硬件需求。

现在，在 OOBE 期间，将 HoloLens 2 与 WLAN 连接后，OOBE 将检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 加入和注册流的其余部分。 换句话说，不再要求使用以太网到 USB-C 或 Wi-Fi USB-C 适配器，但如果在 OOBE 开始时提供，它们仍可以继续工作。 了解有关适用于 [HoloLens 2 设备的 Autopilot 的信息](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot
- 将设备锁定到租户后，即使进行设备重置或重新刷新也可将设备保留在组织的租户上。 通过预配禁用帐户创建，进一步增强安全性。 

从 Windows 全息版 [20H2](hololens-release-notes.md#windows-holographic-version-20h2)开始，HoloLens 2 设备现在支持 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。  在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使进行重新刷新、操作系统更新，该值仍将保留在设备上。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后， OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许执行以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 Azure AD 加入操作 
- 在 OOBE 体验中选择设备所有者 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 设置此选项？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从先前分配了上面创建的设备配置的设备组中删除 HoloLens 2。 

1. 创建基于 OMA URI 的自定义设备配置配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，则 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了消除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown CSP 引入的限制。 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

现在，可以在 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的 Autopilot 旁边找到此信息。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配的访问权限 – 展台模式
- 通过启用在系统级别应用展台模式的新 Kiosk 方法，减少了展台的标识管理。

此新功能允许 IT 管理员为适用于系统级别的多个应用展台模式配置 HoloLens 2 设备，与系统上的任何标识没有任何关联，并且适用于登录设备的每个人。 在 [HoloLens](hololens-global-assigned-access-kiosk.md)全局分配的访问权限展台中详细阅读此新功能。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序 
- 自动应用启动的集中体验，进一步增加为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能使用"分配的访问权限"配置中的以下突出显示属性将 1 个应用指定为自动启动。 

当用户登录时，应用程序将自动启动。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>用于处理故障的展台模式行为更改
- 通过消除展台模式故障上的可用应用，更安全的展台模式。 

在应用展台模式失败之前，HoloLens 用于在"开始"菜单中显示所有应用程序。 现在，在 Windows 全息版 20H2 中，如果失败，则"开始"菜单中不会显示任何应用，如下所示： 

![展台模式在出现故障时的外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 策略
- 专为 HoloLens 创建的用于管理设备的设备管理选项。 

为 Windows 全息版 20H2 上的 HoloLens 2 设备创建了新的混合现实策略。 新的可控制设置包括：设置亮度、设置音量、在混合现实捕获中禁用音频录制、设置何时可以收集诊断以及 AAD 组成员身份缓存。  

| 新 HoloLens 策略                                | 说明                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，以便按它不会改变亮度。       | 1 是，0 (默认)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便按它不会改变音量。               | 1 是，0 (默认)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，以便 HoloLens 2 上无法录制音频。                      | 1 是，0 (默认)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制何时可以收集诊断日志的行为。                               | 0 已禁用，1 为设备所有者启用，2 为默认 (启用)  |
| MixedReality\HeadTrackingMode                      | 保留以供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制 Azure AD 组成员身份缓存用于面向 Azure AD 组的展台的天数。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>为脱机展台缓存 Azure AD 组成员身份
- 启用的脱机展台可与 AAD 组一起使用，最多 60 天。

此策略控制允许 Azure AD 组成员身份缓存用于面向已登录用户的 Azure AD 组的分配的访问权限配置天数。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值 - 0 天  
最大值 - 60 天 

正确使用此策略的步骤： 
1. 创建面向 Azure AD 组的展台的设备配置文件，并将其分配给 HoloLens () 。 
1. 创建一个基于 OMA URI 的自定义设备配置，该配置将此策略值设置为 (> 0) 所需的天数，并将其分配给 HoloLens () 。 
    1. URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/最大值之间。
1. 注册 HoloLens 设备并验证这两种配置是否适用于该设备。 
1. 在 Internet 可用时允许 Azure AD 用户 1 登录，一旦成功确认用户登录和 Azure AD 组成员身份，将创建缓存。 
1. 现在，Azure AD 用户 1 可以将 HoloLens 脱机并用于展台模式，只要策略值允许 X 天数。 
1. 对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的关键点是，任何 Azure AD 用户都必须使用 Internet 登录设备，以便我们至少一次可以确定他们是展台配置面向的 Azure AD 组的成员。 
 
> [!NOTE]
> 为 Azure AD 用户执行步骤 4 之前，将遇到"断开连接"环境中提及的失败行为。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新设备限制策略
- 允许用户管理特定设备管理策略，例如阻止添加或删除预配包。

新启用的策略，允许更多 HoloLens 2 设备的管理选项。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的这两个新设置将添加到我们的 [常见设备限制中](hololens-common-device-restrictions.md)。

> [!NOTE]
> 对于 [RemoteLock，HoloLens](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)将仅支持 ./Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理 PIN 的配置，例如重置和恢复。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 的新电源策略
- 有关 HoloLens 何时通过电源策略睡眠或锁定的更多选项。 

这些新添加的策略允许管理员控制电源状态，例如空闲超时。 若要了解有关每个单独策略的更多信息，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     用于 Windows 配置设计器的示例值，例如，  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     用于 Windows 配置设计器的示例值，例如，  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  在 Windows 配置设计器（即 100）中使用的示例值                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     在 Windows 配置设计器（即 100）中使用的示例值                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     用于 Windows 配置设计器的示例值，例如，   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     用于 Windows 配置设计器的示例值，例如，  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

这两个 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新设置将添加到我们的 [常见设备限制中](hololens-common-device-restrictions.md)。

> [!NOTE]
> 若要在 HoloLens 2 上获得一致体验，请确保 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都设置为相同值。 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn 也适用。 有关新式 [待机的详细信息](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) ，请参阅显示、睡眠和休眠空闲计时器。

### <a name="newly-enabled-update-policies-for-hololens"></a>新启用的 HoloLens 更新策略
- 有关何时安装更新或禁用"暂停更新"按钮以确保更新的更多选项。

这些更新策略现在在 HoloLens 2 设备上启用：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何将它们用于 HoloLens 设备的完整详细信息，请参阅"管理[HoloLens 更新"。](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 的"已启用设置"页面可见性
- "设置"应用中的 UI 控件增加，这可能与显示有限的页面选择混淆。

现在，我们已启用一个策略，允许 IT 管理员阻止"系统设置"应用中的特定页面可见或可访问，或者对除指定页面以外的所有页面启用此策略。 若要了解如何完全自定义此功能，请单击以下链接。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 上自定义的页面设置，请访问我们的设置 [URI 页面](settings-uri-list.md)。 
 
![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式下，HoloLens 2 成为计算机视觉研究的重要工具。 与以前版本相比，HoloLens 2 研究模式具有以下优点：
-   除了在 HoloLens (第一代) 研究模式中公开的传感器，我们现在还提供 IMU 传感器访问，包括加速计、陀螺仪和磁力计。
-   HoloLens 2 提供可与研究模式一同使用的新功能。 具体而言，访问可交付更丰富的实验集的清晰手部跟踪和目视跟踪 API。

现在，研究人员可以选择在 HoloLens 设备上启用研究模式，以访问所有这些面向外部的原始图像传感器流。 HoloLens 2 研究模式还提供对加速计、陀螺仪和磁力计读数的访问。 为了保护用户的隐私，原始目视跟踪相机图像无法通过研究模式提供，但可以通过现有 API 提供凝视方向。

请查看研究 [模式文档，](https://docs.microsoft.com/windows/mixed-reality/research-mode) 了解进一步的技术详细信息。

### <a name="recording-length-increased"></a>录音长度增加
由于客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。 默认情况下，混合现实捕获将不再限制为 5 分钟，而是将基于可用磁盘空间计算最大录制长度。 设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。

> [!NOTE]
> 如果发生以下情况之一 (HoloLens) 5 分钟以下时间的默认视频录制长度：
> - 估计的最大录制持续时间小于默认的 5 分钟。
> - 可用磁盘空间少于总磁盘空间的 20%。

你可以在我们的全息照片和视频文档中找到 [完整](holographic-photos-and-videos.md#maximum-recording-length) 要求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：
- OOBE 中的更多屏幕现在都为深色模式。
- 了解更多内容应指向最新的联机隐私声明。
- 解决了用户无法通过预配包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 更新了策略，以禁用通过适用于 AllowUsbConnection 的 NCM 的 MDM 枚举 USB 函数。
- 解决了当将 HoloLens 设备设置为单应用展台时，阻止 HoloLens 设备在文件资源管理器中显示媒体传输协议 (MTP) [的问题。](hololens-kiosk.md) 请注意，通常 (UTP 连接和 USB) 仍可以使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略禁用。
- 修复了在展台模式下正确缩放"开始"菜单中的图标的问题。
- 修复了由于 HTTP 缓存干扰面向 Azure AD 组的展台模式的问题。
- 修复了用户在通过预配包启用开发人员模式后无法使用配对按钮的问题，除非他们禁用并重新启用开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows 全息版版本 1903 - 2020 年 11 月更新
- 内部版本 18362.1085

此每月质量更新不包含任何明显的更改，我们鼓励你试用我们的最新功能版本版本 Windows 全息版版本 20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 10 月更新
- 内部版本 19041.1124
 
更新中的改进和修复：

- 删除了导致运行时系统错误的不必要的检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 10 月更新
- 内部版本 18362.1081

此每月质量更新不包含任何值得注意的更改，我们鼓励你试用 Windows Holographic 版本 2004 的最新内部版本。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 9 月更新
- 内部版本 19041.1117

更新中的改进和修复：

- 解决了当 appxmanifest Visual Studio SupportsMultipleInstances="true"时阻止用户调试应用程序的问题。
- 此版本包括 NCSI 代理检测修复，用于解决网络代理 Internet 检测失败的问题。 NCSI 可以使用计算机代理和每个配置文件代理进行 Internet 连接检测。 在未来版本中，NCSI 将支持每用户代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的头处于向前的中性位置时，向前方向矢量与地面平行。 但是，早期版本的 HoloLens 2 将矢量与显示面板垂直对齐，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已对此进行更正，以确保不同外形要素的语义一致性。
- 改进了手部跟踪稳定性，将减少特定方案中的跟踪损失。
- 此版本包含一个改进音频时间戳质量的修补程序，该修补程序可能导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows 全息版版本 1903 - 2020 年 9 月更新
- 内部版本 18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的头处于向前的中性位置时，向前方向矢量与地面平行。 但是，早期版本的 HoloLens 2 将矢量与显示面板垂直对齐，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已对此进行更正，以确保不同外形要素的语义一致性。
- 改进了手部跟踪稳定性，将减少特定方案中的跟踪损失。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 8 月更新
- 内部版本 19041.1113

更新中的改进和修复：

- 设置应用将不再关注用户进入 Iris 注册或目视跟踪校准体验。
- 修复了在 OOBE 期间应用预配包以重命名设备并执行其他操作 (（例如连接到网络) ）在设备重启后因重命名而无法执行其他操作的问题。
- 修改了初始设备设置流的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 8 月更新
- 内部版本 18362.1074

此每月质量更新不包含任何值得注意的更改，我们鼓励你试用 Windows Holographic 版本 2004 的最新内部版本。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 7 月更新
- 内部版本 19041.1109

更新中的改进和修复：

- 开发人员现在可以在启用或禁用 Device Portal 时选择需要安全连接。
- 改进了操作系统更新后应用程序启动的可靠性。
- 将默认收件箱亮度更改为 100%。
- 解决了 HoloLens 2 上 Windows Device Portal 的 HTTPS 转发问题。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows 全息版版本 1903 - 2020 年 7 月更新
- 内部版本 18362.1071

更新中的改进和修复：

- 修复了在丢失或重新获得跟踪时可能导致全息影像在 Unity 应用程序中消失的问题。
- 修复了导致独占 HoloLens 应用在将 HoloLens 仿真器在某些设备上使用硬件加速时崩溃回 shell 的问题。
- 解决了 HoloLens 2 上 Windows Device Portal 的 HTTPS 转发问题。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 6 月更新
- 内部版本 19041.1106

更新中的改进和修复：

- 自定义 MRC 录制器现在具有某些属性的新默认值（如果未指定）。
  - 在 *MRC 视频效果上*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 *MRC 音频效果上*：
    - LoopbackGain (Windows Device Portal) 的"混合现实捕获"页面上的当前"应用音频获取") 
    - MicrophoneGain (Windows Device Portal) 的"混合现实捕获"页面上的当前"麦克风音频获得") 
- 修复了在混合现实捕获方案中提高音频质量的 Bug。 具体而言，此修补程序应该消除在显示"开始"菜单时录制 **中的** 音频故障。
- 改进了录制的视频中的全息影像稳定性。
- 解决了混合现实捕获在设备处于待机状态多天后无法录制视频的问题。
- HolographicSpace.UserPresence API 通常对 Unity 应用程序禁用。 此行为可以避免导致某些应用在翻转面罩时暂停的问题，即使启用了"在后台运行"设置。 API 现在为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用。
- 通过连接访问 Device Portal Wi-Fi，Web 浏览器可能会由于证书无效而阻止访问。 即使之前信任设备证书，浏览器也可能报告"ERR_SSL_PROTOCOL_ERROR"等错误。 在这种情况下，你无法前进到 Device Portal，因为无法忽略安全警告。 此更新解决了问题。 如果之前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，必须下载并信任新证书，以解决浏览器安全警告。
- 启用创建运行时预配包的能力，该预配包可以使用 MSIX 包安装应用。
- 在"设置系统**** 全息影像"中添加了一个设置，允许用户在设备关闭时自动从 Mixed Reality 主页中删除  >  ****  >  **** 所有全息影像。
- 修复了导致 HoloLens 应用更改其像素格式以在 HoloLens 仿真器中呈现黑色的问题。
- 修复了在 Iris 登录期间导致崩溃的 Bug。
- 修复了当前应用的重复存储下载问题。
- 修复了防止沉浸式应用重复打开 Microsoft Edge 的 Bug。
- 修复了从 1903 版本更新后在初始启动中启动"照片"应用的问题。
- 改进了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows 全息版版本 1903 - 2020 年 6 月更新
- 内部版本 18362.1064

更新中的改进和修复：

- 自定义 MRC 录制器具有某些属性的新默认值（如果未指定）。
  - 在 *MRC 视频效果上*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 *MRC 音频效果上*：
    - LoopbackGain (Windows Device Portal) 的"混合现实捕获"页面上的当前"应用音频获取") 
    - MicrophoneGain (Windows Device Portal) 的"混合现实捕获"页面上的当前"麦克风音频获得") 
- HolographicSpace.UserPresence API 通常对 Unity 应用程序禁用。 此行为可以避免导致某些应用在翻转面罩时暂停的问题，即使已启用在后台运行的设置。 API 现在为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用。
- 修复了导致 HoloLens 应用更改其像素格式以在 HoloLens 仿真器中呈现黑色的问题。
- 修复了从 1903 版本更新后在初始启动中启动"照片"应用的问题。

## <a name="windows-holographic-version-2004"></a>Windows 全息版版本 2004  
- 内部版本 - 19041.1103

2020 年 5 月 HoloLens 2、Windows 全息版版本 *2004* 的主要软件更新包括一系列令人兴奋的新功能，例如支持 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LTE 热点等。 若要更新到最新版本，请打开"设置****"应用，转到"&安全性"，然后选择   "检查 **** **更新"**   按钮。 

|             功能                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 预配置并无缝设置用于生产的新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，以实现共享设备的快速而安全的身份验证            |
|       改进的预配                      |          将预配包从 U 盘无缝应用到 HoloLens                              |
|       应用程序安装状态                 |          在"设置"应用中检查应用的安装状态，该应用已通过 MDM 推送到 HoloLens 2               |
|       配置服务提供程序 (的 CSP)    |          添加了新的配置服务提供程序来增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          扩展的 USB 以太网功能支持 5G/LTE                                    |
|       深色应用模式                              |          深色应用模式适用于支持深色和浅色模式的应用，从而改善观看体验        |
|       语音命令                             |          支持其他系统语音命令以控制 HoloLens 无手操作                           |
|       手跟踪改进                 |          手部跟踪改进使按钮和 2D 平板电脑交互更加准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>对 Windows Autopilot 的支持

适用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道将 HoloLens 预注册到 Intune 租户。 当设备到达时，他们已准备好在租户下自行部署为共享设备。 若要利用自部署，设备必须使用 USB-C 到以太网在设置的第一个屏幕期间连接到网络。

在用户启动 Autopilot 自部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory （Azure AD）。
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。
1. 下载面向设备的策略、证书和网络配置文件。
1. 预配设备。
1. 向用户呈现登录屏幕。

从 [适用于 HoloLens 2 的 Windows Autopilot 评估指南中了解更多信息](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*立即联系你的客户经理以加入 AutoPilot 预览版。 Autopilot 就绪设备将很快开始发货。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户与工作或学校环境中其他人共享 HoloLens 设备。 因此，用户无需键入长用户名和密码即可轻松操作，这一点非常重要。 借助快速标识 (FIDO) ，组织 (Azure AD 租户中的) 无需输入用户名或密码即可无缝登录 HoloLens。

FIDO2 安全密钥是基于标准的"不可访问"的无密码身份验证方法，可采用任何外形要求。 FIDO 是无密码身份验证的开放标准。 它允许用户和组织在没有用户名或密码的情况下登录其资源。 相反，它们使用内置于设备的外部安全密钥或平台密钥。

若要开始，请参阅启用 [无密码安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

预配包使你可以通过 配置文件 而不是 HoloLens 开箱即用体验来设置 HoloLens 配置。 以前，预配包必须复制到 HoloLens 内部内存中。 现在，它们可以位于 USB 驱动器上，以便更轻松地在多个 HoloLens 设备上重复使用，并且你可以并行预配设备。 预配包现在还支持在设备管理中注册的字段，以便预配后无需手动设置。

若要试用：

1. 将最新版本的 Windows 配置设计器从 Windows 应用商店下载到电脑。
1. 选择 **"预配 HoloLens 设备**  >  **预配 HoloLens 2 设备"。**
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何刚闪烁的 HoloLens。 然后按**音量降低**  +  **电源**按钮以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

业务线应用的 MDM 应用部署和管理对 HoloLens 至关重要。 管理员和用户需要查看应用安装状态进行审核和诊断。 在此版本中，我们在"设置帐户访问"**** 工作或学校"单击  >  ****  >  ****  >  **你的帐户信息"中添加了**  >  **更多详细信息**。

### <a name="additional-csps-and-policies"></a>其他 CSP 和策略

配置 [服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 是一个接口，用于读取、设置、修改或删除设备的配置设置。 在此版本中，我们增加了对更多策略的支持，以增加管理员对已部署的 HoloLens 设备的控制。 有关 HoloLens 支持的 CSP 的列表，请参阅[NetworkQoSPolicy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

此版本中的新增功能：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们添加了 HoloLens 的新策略，这些策略在此处列出。 若要了解更多信息，请参阅[HoloLens 2 支持的策略 CSP。](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

NetworkQoSPolicy 配置服务提供商创建 QoS (网络服务质量) 策略。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 若要了解更多信息，请参阅[NetworkQoSPolicy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>扩展了对 5G/LTE 连接设备的 USB 以太网支持

添加了支持，以启用某些移动宽带设备，例如 5G/LTE 电话和 Wi-Fi 热点，当它们通过 USB 连接到 HoloLens 2 时。 这些设备现在在网络设置 **中显示为** 另一个以太网连接。  (不支持需要外部驱动程序的移动宽带设备。) 如果 Wi-Fi 不可用并且 Wi-Fi连接性能不足，此功能将启用高带宽连接。 若要了解有关受支持的 USB 设备的信息，请参阅Bluetooth [和 USB-C 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手跟踪改进

此版本包括几个手部跟踪改进：

- **指向位置稳定性：** 现在，当食指被手心遮挡时，系统将抵御手指弯曲。 此更改提高了你按下按钮、键入、滚动内容等时的准确性！ 
- **减少意外的点击：** 我们改进了对空点击手势的检测。 现在，在一些常见方案中（例如，将手放在一边时）的意外激活更少。
- **用户交换机可靠性：** 现在，当你共享设备时，系统更新手型的速度更快、更可靠。
- **减少手盗：** 我们改进了对传感器视图多于两个手的情况的处理。 如果多个人紧密协作，则跟踪手从用户"跳"到场景中其他人手的可能性要低得多。
- **系统可靠性：** 修复了导致手部跟踪在设备负载较高时停止工作的问题。

### <a name="dark-mode"></a>深色模式

许多 Windows 应用现在都支持深色和浅色模式。 HoloLens 2 用户可以为支持两者的应用选择默认模式。 更新后，默认应用模式为"深色"，但你可以轻松更改此设置：**导航到设置**  >  **系统**  >  **颜色**  >  **选择默认应用模式**。 

这些"In-box"应用支持深色模式： 

- “设置” 
- Microsoft Store 
- Mail 
- 日历 
- 文件资源管理器 
- 反馈中心 
- OneDrive 
- 照片 
- 3D 查看器 
- 电影和电视 

![深色模式窗口平铺](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>系统语音命令

现在，你可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅"[使用语音操作 HoloLens"。](https://docs.microsoft.com/hololens/hololens-cortana) 另请参阅 [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support)支持的语言。  

### <a name="cortana-updates"></a>Cortana 更新

更新后的应用与 Microsoft 365 集成，可帮助你完成当前仅 (设备US-English完成) 。 在 HoloLens 2 上，Cortana 不再支持某些特定于设备的命令，如调整音量或重启。 现在，新的系统语音命令支持这些选项。 在我们的博客中了解有关新 Cortana 应用[的内容。](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中的改进和修复：  
- 引入了活动显示校准系统。 此功能提高了全息影像的稳定性和对齐方式。 当你将头从一侧移动到另一侧时，它们现在就位。
- 修复了流式Wi-Fi HoloLens 定期中断的 Bug。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode 函数实现修复](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)。
- 修复了在研究模式下流式传输期间发生的设备挂起。
- 修复了在某些情况下，在恢复会话时不会在登录屏幕上显示正确用户的问题。
- 修复了用户无法通过"设置"导出 MDM **日志的问题**。
- 修复了以下问题：立即执行开箱即用设置的目视跟踪的准确性可能低于预期。
- 修复了在某些情况下，目视跟踪子系统无法初始化或校准的问题。
- 修复了为已校准的用户提示进行目视校准的问题。
- 修复了驱动程序在目视校准期间崩溃的问题。
- 修复了重复电源按钮按下可能导致 60 秒系统超时和 shell 崩溃的问题。
- 改进了深度缓冲区的稳定性。
- 在 **反馈中心** 添加了"共享"按钮，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan 未正确安装的问题。

### <a name="known-issues"></a>已知问题

- zh-CN 系统语言的问题阻止语音命令获取混合现实捕获或显示设备 IP 地址。
- 问题需要你在启动设备后启动 Cortana 应用以使用"你好小娜"语音激活。 如果你从 18362 版本更新，你也可能看到以前版本的 Cortana 应用的第二个应用磁贴不再在"开始"版本中 **工作**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows 全息版版本 1903 - 2020 年 5 月更新 
- 内部版本 18362.1061

此每月质量更新不包含任何显著更改，因为团队正在处理 Windows 全息版 2004 年 5 月更新，如前面所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows 全息版版本 1903 - 2020 年 4 月更新
- 内部版本 18362.1059

**受支持的应用的深色模式** 

许多 Windows 应用都支持深色和浅色模式。 HoloLens 2 客户现在可以为支持这两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为"深色"，但你可以随时轻松更改此设置：导航到"设置 **">系统 > 颜色**以查找"**选择默认应用**模式"。

这些"In-box"应用支持深色模式：
- “设置”
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
- 确保外壳覆盖包含在混合现实捕获中。
- 现在，不真实的开发人员可以使用 Device Portal 中的"3D 视图"页测试和调试其应用程序。
- 使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，改进了混合现实捕获中的全息影像稳定性。
- 修复了 32 位应用上的"未注册 WinRT IStreamSocketListener API 类ARM错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 3 月更新 
- 内部版本 18362.1056

更新中的改进和修复：

- 使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，改进了混合现实捕获中的全息影像稳定性。
- 确保附加到深度 MF 示例的坐标系与公共文档一致。
- 通过允许客户通过设备门户粘贴大量文本，提高了开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows 全息版版本 1903 - 2020 年 2 月更新 
- 内部版本 18362.1053

更新中的改进和修复：

- 临时禁用 Unity 应用程序的 HolographicSpace.UserPresence API。 此更改可以避免导致某些应用在翻转面罩时暂停的问题，即使启用了"在后台运行"设置。
- 修复了由手部跟踪导致的随机 HUP 崩溃，其中用户注意到 UI 冻结，然后在几秒钟后返回到 shell。
- 改进了手部跟踪功能，以便当您用食指弯曲时，该手指的上半部分不太可能意外出现弯曲。
- 改进了头跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows 全息版版本 1903 - 2020 年 1 月更新 
- 内部版本 18362.1043
 
更新中的改进和修复：

- 改进了使用 HoloLens 2 仿真器时独占应用的稳定性。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic 版本 1903 - 2019 年 12 月更新 
- 内部版本 18362.1042

更新中的改进和修复：

- 引入了 LSR (最后阶段) 重现。 改进了全息影像的视觉呈现，通过更精确地计算其深度，使其更加稳定且清晰。 如果应用没有正确设置全息影像的深度，此症状在此更新后将更为明显。
- 修复了独占应用和独占应用之间的导航稳定性。
- 解决了混合现实捕获在设备处于待机状态数天后无法录制视频的问题。
- 改进了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic 版本 1903 - 2019 年 11 月更新 
- 内部版本 18362.1039

更新中的改进和修复：

- 修复了在初始**** 设置 en-CA 和 en-AU 期间选择语音命令的功能。
- 改进了放置在最新 Unity 和混合现实版 MRTK 版本Toolkit (对象) 质量。
- 修复了全息应用程序在启动时卡在暂停状态的问题，直到打开然后关闭"开始"菜单。
- HoloLens 2 和模拟器的 OpenXR 运行时一致性修补程序和改进。
