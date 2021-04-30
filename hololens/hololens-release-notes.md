---
title: HoloLens 2 发行说明
description: 随时了解每个新的 HoloLens 2 版本中的所有更新。
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
ms.openlocfilehash: 18b0d6b304e8de8c85caeec9f3e8ba190647aaec
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308487"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

为了确保您的 HoloLens 设备具有工作效率，我们继续发布功能、bug 和安全更新。 在此页上，你可以查看每个月的最新功能。 若要获取最新的 HoloLens 2 更新，可以 [检查更新并手动更新](hololens-update-hololens.md#check-for-updates-and-manually-update) 或获取完整的闪存更新 (FFU) [通过高级恢复助理来闪存你的设备](hololens-recovery.md#clean-reflash-the-device)。 [下载](https://aka.ms/hololens2download)内容保持最新，并提供最新的公开发布版本。

>[!NOTE]
> 我们非常高兴地开始向 Windows 预览体验人员试验新功能。 我们将为最新的更新试验开发渠道。 我们将继续在我们的我们的 Windows 预览体验内部版本中添加更多的功能和更新，以继续进行 [**HoloLens 有问必答笔记**](hololens-insider.md) 。 令人兴奋并准备好将这些更新混合到您的现实中。

查看相关发行说明：

- [访问 HoloLens 模拟器存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows 全息，版本 20H2-2021 年4月更新
- 生成19041.1144

更新中的改进和修复：

- 解决了业务线应用程序安装状态报告问题。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1108

更新中的改进和修复：

- 解决了尝试更改本地帐户的密码时设置应用崩溃的问题。

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows 全息，版本 20H2-2021 年3月更新
- 生成19041.1140

更新中的改进和修复：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 捕获照片和 HoloLens 2 的客户现在可以在捕获照片后，最多运行3秒钟。
- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。
- 解决了在分阶段推出中注册的用户无法登录到该设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1102

更新中的改进和修复：

- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows 全息，版本 20H2-2021 年2月更新
- 生成19041.1136

更新中的改进和修复：

- 修复了初始设备安装和应用程序更新的相关问题。
- 解决了以后的 HoloLens 版本的升级和航班问题。
- 从 HoloLens 设备上删除了来自 eSIM 根存储的未使用的预安装证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1098

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows 全息，版本 20H2-2021 年1月更新
- 生成19041.1134

更新中的改进和修复：

- 当设备上有多个用户时，在启动、恢复和用户切换期间提高了性能。
- 为 [研究模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)添加了 arm32 支持。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1091

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows 全息版20H2 –2020年12月更新
- 生成19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过应用安装程序在 HoloLens 2 上安装应用

我们正在 **添加新功能 (应用安装程序) ，使你能够在 HoloLens 2 设备上更无缝地安装应用程序** 。 **默认情况下，对于非托管设备**，此功能将处于启用状态。 若要防止企业中断，此时将不能 **为托管设备提供** 应用安装程序。  

如果满足以下 **任一** 条件，则将设备视为 "托管"：
- 已[注册](hololens-enroll-mdm.md)MDM
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

你现在可以安装应用，而无需启用开发人员模式或使用设备门户。  只需通过 USB 或边缘) Appx 包下载到设备的 (，然后在文件资源管理器中导航到 Appx 捆绑，系统将提示开始安装。  或者， [通过网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 对应用进行数字签名，并且在部署应用之前，必须由 HoloLens 设备 [信任用于签署的证书](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。

**应用程序安装说明。**

1.  确保你的设备不被视为托管设备
1.  确保你的 HoloLens 2 设备已开机并连接到你的电脑
1.  确保已登录到 HoloLens 2 设备
1.  在电脑上导航到自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。   完成文件复制后，可以断开与设备的连接
1.  在 HoloLens 2 设备上，打开 "开始" 菜单，选择 "所有应用"，然后启动 "文件资源管理器" 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用程序的左侧面板上选择 "此设备"，然后导航到 "下载"。
1.  选择 yourapp 文件。
1.  应用程序安装程序将启动。 选择 "安装" 按钮以安装您的应用程序。
安装完成后，安装的应用将自动启动。

可以在 [Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到示例应用来测试此流程。

阅读有关在 [HoloLens 2 上通过应用安装程序安装应用](app-deploy-app-installer.md)的完整过程。  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手动跟踪现在可以在很多新情况下维护跟踪，这种情况先前会丢失。  在其中一些新情况下，只会根据用户的真实情况继续更新手掌位置，而其他联系则基于上一个姿势进行推断。  此更改有助于改进跟踪的一致性，例如 slapping、抛出、scooping 和拍手。  它还有助于在手接近某个表面或持有对象的情况下使用。  当推理出手动联接时，" [每个联合准确性](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) " 值将设置为 "近似" 而不是 "高"。
- 修复了 Azure AD 帐户的 PIN 重置会显示错误 "出现错误的问题。
- 从 "设置" 应用、"新建用户" 或 "通知 toast" 启动 ET、Iris 时，用户应会看到更少的引导后 OOBE 崩溃。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows 全息，版本1903–2020更新
- 生成18362.1088

这一月度质量更新不包含任何显著的更改，我们建议你试用最新的 Windows 全息版20H2 –2020年12月更新和在生成中添加的新应用安装程序功能。


## <a name="windows-holographic-version-20h2"></a>Windows 全息，版本20H2
- 生成19041.1128

Windows 全息版20H2 现已推出，并向 HoloLens 2 用户和 IT 专业人员提供了一套丰富的新功能。 从自动目视定位到 "设置" 中的 "证书管理器"，到改进展台模式功能和新的 Autopilot 设置功能。 这一新的更新使 IT 团队能够更精细地控制如何配置和管理 HoloLens 设备，并为用户提供更无缝的无缝体验。 

此最新版本是对版本2004的每月更新，但这次我们将包括新功能。 主要内部版本号将保持不变，Windows 更新将指示每月版本 2004 (版本 19041) 。 你可以在 "设置" > 的 "屏幕" 中查看生成号，以确认你使用的是最新的版本 19041.1128 +。 若要更新到最新版本，请打开 "设置" 应用，中转到 "更新 & 安全性"，然后点击 "检查更新"。 有关如何管理 HoloLens 更新的详细信息，请访问 [此页](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows 全息版20H2 中的新增功能  

| 功能                                              | 描述                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动目视定位支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，无需用户通过目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许从 "设置" 应用程序中安装和删除证书的更简单方法。     |
| [从 USB 自动启动设置](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在 USB 驱动器上预配包会自动提示 OOBE 中的设置页面。                                                         |
| [自动确认在 OOBE 中预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配页面会在 OOBE 期间自动应用预配包。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将设置自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，无需使用以太网适配器。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，在设备重置或重新刷新时，设备只能在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个 app 展台模式的新配置方法，它在系统级别应用展台，使其适用于所有内容。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录到多应用展台模式时自动启动。                                                        |
| [用于处理故障的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制的回退。                                                                                                |
| [HoloLens 策略](hololens-release-notes.md#hololens-policies)                                    | 针对 HoloLens 的新策略。     |
| [缓存 Azure AD 脱机展台的组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用 "组成员身份缓存" 在设置的天数内脱机使用展台模式。                                        |
| [HoloLens 2 的新设备限制策略](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 为 HoloLens 2 启用了新启用的设备管理策略。                                                                                |
| [HoloLens 2 的新电源策略](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 最新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允许控制更新的新启用的策略。           |
| [已启用 HoloLens 2 的设置页面可见性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选择在 "设置" 应用中显示哪些页的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [记录长度增加](hololens-release-notes.md#recording-length-increased) | MRC 记录不再超过5分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动目视定位支持

在 HoloLens 2 中，目视定位可实现准确的全息影像定位、舒适的观看体验，并改善了显示质量。 目视位置作为眼睛跟踪计算的一部分在内部进行计算。 但是，这要求每个用户都要经历眼睛跟踪校准，即使在体验可能不需要目视输入时也是如此。

**自动排列位置 (AEP)** 通过无交互的方式来计算用户的眼睛位置。 自动目视位置在用户将设备置于设备上的时刻自动开始运行。 如果用户没有先前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视定位将开始向显示系统提供用户的眼睛位置。 用户数据不会保留在设备上，因此如果用户关闭并重新打开设备，或者设备重新启动或从睡眠状态唤醒，则此过程将重复。

当 uncalibrated 用户进入设备时，会有一些系统行为随 "自动目视定位" 功能发生变化。 在这种情况下，uncalibrated 用户指的是先前尚未经历设备上的目视跟踪校准过程的人。

| 活动应用程序 | 之前的行为 | Windows 全息版20H2 更新中的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用注视的应用或全息 Shell |显示 "目视跟踪校准提示" 对话框。 | 不显示提示。 |
| 已启用注视的应用 | 显示 "目视跟踪校准提示" 对话框。 | 仅当应用程序访问眼睛注视流时才显示眼睛跟踪校准提示。 |

如果用户从未启动的已启用的应用程序转换到访问看不到的数据的应用程序，则将显示校准提示。 

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将类似于。 例如，将不会启用一次传递的开始手势。 初始设置的全新体验将不会更改。

对于需要眼睛眼睛数据或非常精确的全息图定位的体验，建议 uncalibrated 用户运行目视跟踪校准。 可以从目视跟踪校准提示进行访问，也可以通过从 "开始" 菜单启动 "设置" 应用程序，然后选择 " **系统 > 校准 > 目视校准 > 运行目视校准**。

稍后可以在 [其他校准信息](hololens-calibration.md#auto-eye-position-support)中找到此信息。 

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能使你能够在商业环境中大规模部署、排查和验证你的证书。

在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 请参阅 " **设置" > 更新 & Security > 证书**。 此功能提供了一种简单易用的方法来查看、安装和删除设备上的证书。 使用新的证书管理器，管理员和用户现在已经改进了审核、诊断和验证工具，以确保设备保持安全性和合规性。 

-   **审核：** 能够验证是否已正确部署证书，或者确认是否已正确删除证书。 
-   **诊断：** 出现问题时，验证设备上存在的适当证书是否节省时间并帮助进行故障排除。 
-   **验证：** 验证证书是否服务于预期目的并能正常工作，可以节省大量时间，特别是在商业环境中，在较大规模部署证书之前。

若要快速查找列表中的特定证书，可以按名称、存储或到期日期排序。 用户还可以直接搜索证书。 若要查看单独的证书属性，请选择该证书，然后单击 " **信息**"。 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从 "设置" UI 安装的证书。 如果通过其他方式安装了证书，则该证书还必须通过相同的机制删除。

#### <a name="to-install-a-certificate"></a>若要安装证书： 

1.  将 HoloLens 2 连接到 PC。
1.  将要安装的证书文件放在 HoloLens 2 上的某个位置。
1.  导航到 " **设置" 应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。
1.  单击 " **导入文件** "，并导航到保存证书的位置。
1.  选择 " **存储位置**"。
1.  选择 " **证书存储**"。
1.  单击“安装” 。

现在应在设备上安装证书。

#### <a name="to-remove-a-certificate"></a>删除证书的步骤： 
1. 导航到 " **设置" 应用 > 更新和安全 > 证书**"。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 出现确认提示时，选择“是”。

!["设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

稍后可 [在新的证书管理器页中](certificate-manager.md)找到此信息。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动设置

- 在 OOBE 期间使用带有预配包的 USB 驱动器时，可通过自动化过程来减少用户交互。

在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，才能使用按钮组合进行设置。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一次种不可交互时插入带有预配包的 USB 驱动器
1. 当设备准备好进行预配时，将自动在 "设置" 页中打开提示。 

注意：如果在设备启动时，会将 USB 驱动器插入，则 OOBE 会枚举现有 USB 存储设备，并监视其他设备是否已插入。

有关在 OOBE 期间应用预配包的详细信息，请访问 [HoloLens 预配](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 文档。

可以在 HoloLens 预配文档中找到有关 USB 中的 [自动启动设置](hololens-provisioning.md#auto-launch-provisioning-from-usb) 的其他信息。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>自动确认在 OOBE 中预配包
- 自动进程允许进行更少的用户交互，当 "预配包" 页面显示时，它将自动应用列出的所有包。

当设置主屏幕出现时，OOBE 将在10秒内计数，然后自动开始应用所有预配包。 验证所需的包后，用户仍可以在此10秒内 [确认或取消](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配
- 合并了自动过程，减少了设置的设备交互。 

通过将预配的自动启动和预配包的自动启动结合起来，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至还可以戴上设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这适用于同一区域中同时部署多个设备。 

1. 使用[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)[创建预配包](hololens-provisioning.md)。 
1. 将包复制到 USB 存储驱动器。
1. 将[HoloLens 2 刷新](hololens-insider.md#ffu-download-and-flash-directions)到[19041.1361 或更高版本](https://aka.ms/hololens2previewdownload)。 
1. 当 [高级恢复助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成时，设备将拔出 USB-C 电缆。 
1. 将 u 盘插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包，并启动设置页面。
1. 10秒后，设备会自动应用预配包。 

你的设备现在已配置，并将 [显示设置成功屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi 连接结合使用
- 通过使 Autopilot 能够在 Wi-Fi 连接的设备上正常工作，已消除了将 USB C 适配器连接到以太网以降低硬件需求的需要。

现在，在 OOBE 期间，一旦使用 Wi-fi 连接了 HoloLens 2，OOBE 就会检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再需要使用以太网到 USB-C 或 Wi-Fi 到 USB-C 适配器，因为在 OOBE 开始时提供了它们。 详细了解 [适用于 HoloLens 2 设备的 Autopilot](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot
- 通过设备重置或刷新将设备锁定到租户，从而使其在组织的租户上保持不变。 通过设置，禁止在中创建帐户，从而增强安全性。 

HoloLens 2 设备现在支持 TenantLockdown CSP，如 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 HoloLens 2 仅限使用 Autopilot 绑定到 MDM 注册。 将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false 后 (初始在 HoloLens 2 上设置) 值，即使重新闪烁、OS 更新等，该值仍保留在设备上。 

在 HoloLens 2 上将 TenantLockdown Csp "RequireNetworkInOOBE" 节点设置为 true 后，OOBE 会无限期等待 Autopilot 配置文件在网络连接后成功下载和应用。 

在 HoloLens 2 上将 TenantLockdown Csp "RequireNetworkInOOBE" 节点设置为 true 后，OOBE 不允许以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时设置执行 Azure AD 联接操作 
- 在 OOBE 体验中选择设备的所有者 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 进行设置？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 使在上一步中创建的组的 HoloLens 2 设备成员成为触发器同步。  

在 Intune 门户中验证是否已成功应用设备配置。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown？ 
1. 从前面创建的设备配置之前分配的设备组中删除 HoloLens 2。 

1. 创建基于自定义 OMA URI 的设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 使在上一步中创建的组的 HoloLens 2 设备成员成为触发器同步。

在 Intune 门户中验证是否已成功应用设备配置。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>如果 TenantLockdown 设置为 true 后在 HoloLens 上未分配 Autopilot 配置文件，则在 OOBE 期间将发生什么情况？ 
OOBE 会无限期等待 Autopilot 配置文件下载并显示以下对话框。 若要删除 TenantLockdown 的效果，必须首先使用 Autopilot 向设备注册其原始租户，并且必须按照上一步骤中所述取消设置 TenantLockdown CSP 引入的限制。 

![设备上强制实施策略的设备内视图。](images/hololens-autopilot-lockdown.png)

此信息现在可在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的 Autopilot 的其余部分找到。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配的访问–展台模式
- 通过启用在系统级别应用展台模式的新展台方法，降低了展台的标识管理。

这项新功能可让 IT 管理员为多个 app 展台模式（在系统级上适用）配置一个 HoloLens 2 设备，该模式与系统上的任何标识都无关联，并且适用于登录到该设备的所有用户。 有关此新功能的详细信息，请参阅 [HoloLens 全局分配的访问展台](hololens-global-assigned-access-kiosk.md)。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序 
- 自动应用启动的聚焦体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只有1个应用可以使用下面的突出显示属性指定为自动启动。 

当用户登录时，应用程序将自动启动。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>用于处理故障的展台模式行为更改
- 通过消除展台模式故障中的可用应用，更安全的展台模式。 

早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 现在，在 Windows 全息版20H2 中，如果出现故障，则在 "开始" 菜单中将不会显示任何应用，如下所示： 

![显示故障时的展台模式的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 策略
- 专用于用于管理设备的 HoloLens 的设备管理选项。 

已在 Windows 全息版20H2 上为 HoloLens 2 设备创建新的混合现实策略。 新的可控制设置包括：设置亮度、设置卷、禁用混合现实捕获中的录音、诊断可以收集时设置以及 AAD 组成员身份缓存。  

| 新建 HoloLens 策略                                | 说明                                                                               | 说明                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，因此按下不会更改亮度。       | 1是，0无 (默认值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，因此按下不会更改音量。               | 1是，0无 (默认值)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此不能在 HoloLens 2 上录音。                      | 1是，0无 (默认值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制诊断日志可以收集的行为。                               | 0已禁用，1为设备所有者启用1，2为所有 (默认值启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制将组成员身份缓存 Azure AD 多少天用于面向 Azure AD 组的展台。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存 Azure AD 脱机展台的组成员身份
- 已启用将脱机展台用于 AAD 组，最多60天。

此策略控制允许使用 Azure AD 组成员身份缓存来指定已登录用户 Azure AD 组的指定访问配置的天数。 一旦将此策略值设置为大于0的值，则不使用缓存。  

名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值为0天  
最大-60 天 

正确使用此策略的步骤： 
1. 为展台 Azure AD 组创建设备配置文件，并将其分配给 HoloLens 设备 (s) 。 
1. 创建基于自定义 OMA URI 的设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. 应在 OMA-URI 文本框中输入 URI 值作为/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。
    1. 该值可以介于最小值/最大允许值之间。
1. 注册 HoloLens 设备，并验证这两项配置是否适用于设备。 
1. 当 internet 可用时，让 Azure AD 用户1登录，一旦用户登录并 Azure AD 组成员身份已成功确认，就会创建缓存。 
1. 现在 Azure AD 用户1可以使 HoloLens 脱机并将其用于展台模式，只要策略值允许 X 天。 
1. 对于任何其他 Azure AD 用户 N，可以重复执行步骤4和步骤5。以下是任何 Azure AD 用户都必须使用 Internet 登录设备，因此至少可以确定它们是展台配置所针对的 Azure AD 组的成员。 
 
> [!NOTE]
> 直到 Azure AD 执行步骤4后，才会在 "断开连接" 环境中遇到失败行为。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新设备限制策略
- 允许用户管理特定的设备管理策略，如阻止添加或删除预配包。

新启用的策略，允许提供更多的 HoloLens 2 设备管理选项。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [高](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

这两个适用于 AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 就 [高](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)而言，HoloLens 仅支持/Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理 PIN （如 reset 和 recover）的配置。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 的新电源策略
- 通过电源策略休眠或锁定时的更多选项。 

这些新添加的策略使管理员能够控制电源状态，如空闲超时。 若要阅读有关每个策略的详细信息，请单击该策略的链接。

|     策略文档链接                |     备注                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 配置设计器中使用的示例值，即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 配置设计器中使用的示例值，即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

这两个适用于 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 若要在 HoloLens 2 上保持一致的体验，请确保 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式备用的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### <a name="newly-enabled-update-policies-for-hololens"></a>针对 HoloLens 的新启用的更新策略
- 安装更新或禁用 "暂停更新" 按钮以确保更新的更多选项。

以下更新策略现已在 HoloLens 2 设备上启用：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何使用这些策略的详细信息，请参阅 [管理 hololens 更新](hololens-updates.md)。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>已启用 HoloLens 2 的设置页面可见性
- "设置" 应用中的 UI 控件增加，这可能会使用户感到困惑，以显示有限的页面。

现在，我们已启用了一个策略，该策略允许 IT 管理员阻止显示或访问 "系统设置" 应用中的特定页面，或为除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 上自定义的页面设置，请访问我们的 [设置 uri 页](settings-uri-list.md)。 
 
![在 "设置" 应用中修改的活动小时的屏幕截图](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式下，HoloLens 2 变成了用于计算机视觉研究的强大工具。 与以前的版本相比，HoloLens 2 的研究模式具有以下优点：
-   除了在 HoloLens 中公开的传感器 (第一代) 研究模式，我们现在提供 IMU 传感器访问，包括加速感应器、陀螺仪和磁力仪。
-   HoloLens 2 提供可与研究模式一起使用的新功能。 具体来说，就是访问可提供更丰富的试验集的有表述的手动跟踪和目视跟踪 Api。

研究人员现在可以选择在其 HoloLens 设备上启用研究模式，以访问所有面向外部的原始图像传感器流。 HoloLens 2 的研究模式还提供对加速计、陀螺仪和磁力仪读数的访问。 为了保护用户的隐私性，无法通过 "调查" 模式获取原始眼睛跟踪相机图像，但可通过现有 Api 使用 "目视" 方向。

有关更多技术详细信息，请查看 [研究模式文档](https://docs.microsoft.com/windows/mixed-reality/research-mode) 。

### <a name="recording-length-increased"></a>记录长度增加
由于客户反馈，我们已增加 [混合现实捕获](holographic-photos-and-videos.md)的记录长度。 默认情况下，混合现实捕获将不再限制为5分钟，但会根据可用磁盘空间来计算最大记录长度。 该设备将根据可用磁盘空间（最大为总磁盘空间的80%）估算最大视频录制持续时间。

> [!NOTE]
> 如果发生以下情况之一，则 HoloLens 将使用默认视频录制长度 (5 分钟) ：
> - 预计的最大记录持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

你可以在 " [全息照片和视频](holographic-photos-and-videos.md#maximum-recording-length) " 文档中找到完全要求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：
- OOBE 中的更多屏幕现在处于暗色模式。
- 了解更多内容应联机指向最新的隐私声明。
- 解决了用户无法通过设置包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 已更新策略以禁用通过 MDM for NCM for AllowUsbConnection 的 USB 函数的枚举。
- 解决了在将设备设置为 [单应用展台](hololens-kiosk.md)时，会阻止 HoloLens 设备在文件资源管理器中显示在文件资源管理器中的问题， (MTP) 。 请注意，一般) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略进行禁用。
- 修复了 "开始" 菜单中的图标在展台模式下正确缩放的问题。
- 修复了由于 HTTP 缓存干扰以展台模式为目标 Azure AD 组的问题。
- 修复了在使用预配包启用开发人员模式后，用户无法使用 "取消" 按钮的问题，除非他们禁用并重新启用了开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1085

这一月度质量更新不包含任何显著的更改，我们建议你试用最新的功能版本 Windows 全息版20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1124
 
更新中的改进和修复：

- 删除导致运行时系统错误的不必要的检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1081

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1117

更新中的改进和修复：

- 解决了在 appxmanifest.xml 中存在 SupportsMultipleInstances = "true" 时阻止 Visual Studio 调试应用程序的问题。
- 此版本包含 NCSI proxy 检测修复，可解决通过网络代理进行的 Internet 检测失败的问题。 NCSI 可以使用计算机代理和每个配置文件的代理来检测 Internet 连接。 将来的版本中，NCSI 将支持每个用户的代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，更早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜了几度。 更新版本的 HoloLens 2 已更正此情况，以确保各种外形规格的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。
- 此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，更早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜了几度。 更新版本的 HoloLens 2 已更正此情况，以确保各种外形规格的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows 全息，版本 2004-8 2020 月版更新
- 生成19041.1113

更新中的改进和修复：

- "设置" 应用将不再跟随用户进入 Iris 注册或眼睛跟踪校准体验。
- 修复了一个 bug，该 bug 在用于重命名设备并执行其他操作 (例如连接到网络) 时在设备重启后执行其他操作（例如，连接到网络）的情况下应用设置包。
- 修改了初始设备设置流程的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows 全息，版本 1903-8 2020 月版更新
- 生成18362.1074

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1109

更新中的改进和修复：

- 现在，开发人员可以选择启用还是禁用设备门户要求安全连接。
- 操作系统更新后，针对应用程序启动的可靠性得到了提高。
- 更改了默认收件箱亮度到100%。
- 解决了在 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能导致在跟踪丢失或执行跟踪时，无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用具有硬件加速功能的 HoloLens 模拟器时，专用的 HoloLens 应用程序故障回复到 shell 的问题。
- 解决了在 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1106

更新中的改进和修复：

- 对于某些属性，如果未指定，则自定义 MRC 记录器现在具有新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上当前的 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 修复了一个 bug，以便在混合现实捕获方案中提高音频质量。 具体而言，当显示 " **开始** " 菜单时，此修复程序应消除录音 glitching。
- 改善了录制视频中的全息影像稳定性。
- 解决了在设备处于待机状态一段时间后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 通过 Wi-Fi 连接访问设备门户时，由于证书无效，web 浏览器可能会阻止访问。 即使之前信任设备证书，浏览器也可能会报告 "ERR_SSL_PROTOCOL_ERROR" 之类的错误。 在这种情况下，无法对设备门户进行进度，因为没有忽略安全警告的选项。 此更新解决了问题。 如果先前已在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并将其信任，以解决浏览器安全警告。
- 支持创建可通过使用 .MSIX 包安装应用的运行时预配包。
- 添加了 **设置**  >  **系统**  >  **全息影像** 中的设置，该设置允许用户在设备关闭时自动删除混合现实主页中的所有全息影像。
- 修复了一个问题，该问题导致在 HoloLens 模拟器中将更改像素格式的 HoloLens 应用程序呈现为黑色。
- 修复了 Iris 登录期间导致崩溃的 bug。
- 修复了有关现有应用的重复存储下载的问题。
- 修复了一个 bug，以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版更新后初始启动时启动照片应用的问题。
- 提高了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1064

更新中的改进和修复：

- 如果未指定自定义的 MRC 录像机，则为某些属性提供新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上当前的 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免当面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 修复了一个问题，该问题导致在 HoloLens 模拟器中将更改像素格式的 HoloLens 应用程序呈现为黑色。
- 修复了从1903版更新后初始启动时启动的照片应用程序的问题。

## <a name="windows-holographic-version-2004"></a>Windows 全息，版本2004  
- 版本-19041.1103

适用于 HoloLens 2 的 Windows 全息版主要软件更新、 *Windows 全息版、版本 2004* 包含一种令人兴奋的新功能，例如支持 Windows Autopilot、应用程序暗模式、USB 以太网支持 5G/LTE 热点，等等。2020 若要更新到最新版本，请打开 "**设置**"   应用，中转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 为生产预配置并无缝设置新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速和安全身份验证            |
|       改进的预配                      |          将预配包从 USB 驱动器无缝应用于 HoloLens                              |
|       应用程序安装状态                 |          在应用的设置应用中检查安装状态已通过 MDM 推送到 HoloLens 2               |
|       配置服务提供程序 (Csp)    |          添加了新的配置服务提供程序以增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          通过扩展 USB 以太网功能，支持 5G/LTE                                    |
|       深色应用模式                              |          适用于支持深色和浅色模式的应用的深色应用模式，从而改善了查看体验        |
|       语音命令                             |          支持其他系统语音命令，以控制 HoloLens 免提                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 石板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

Windows Autopilot for HoloLens 2 允许设备销售渠道预先注册到 Intune 租户中。 设备到达后，它们就可以自行部署为租户下的共享设备。 若要利用自部署，设备必须在安装过程中的第一个屏幕上通过使用 USB 到以太网连接到网络。

用户启动 Autopilot 自行部署过程后，此过程将完成以下步骤：

1. 将设备加入到 Azure Active Directory (Azure AD) 。
1. 使用 Azure AD 在 Microsoft Intune (或其他 MDM 服务) 中注册设备。
1. 下载设备目标策略、证书和网络配置文件。
1. 设置设备。
1. 向用户显示登录屏幕。

有关详细信息，请参阅 [Windows Autopilot For HoloLens 2 评估指南](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*请联系你的帐户管理员立即加入 AutoPilot preview。即将开始交付 Autopilot 的设备。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户在工作或学校环境中与其他用户共享一台 HoloLens 设备。 因此，用户无需键入较长的用户名和密码，就很重要。 快速标识在线 (FIDO) 允许组织中的任何人 (Azure AD 租户) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是一种基于标准的无密码身份验证方法，可采用任何外形规格。 FIDO 是无密码 authentication 的开放标准。 它允许用户和组织无需用户名或密码即可登录到其资源。 相反，它们使用内置于设备中的外部安全密钥或平台密钥。

若要开始，请参阅 [Enable 无密码 security key sign in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

预配包使你可以通过配置文件而不是通过 HoloLens 全新体验来设置 HoloLens 配置。 以前，必须将预配包复制到 HoloLens 内部内存。 现在，它们可以位于 USB 驱动器上，因此可以更轻松地在多个 HoloLens 设备上重复使用，并且可以并行设置设备。 预配包现在还支持用于在设备管理中注册的字段，因此，在预配后无手动设置。

试试看：

1. 从 Windows 应用商店将最新版本的 Windows 配置设计器下载到你的电脑上。
1. 选择 "**预配 hololens 设备**" "  >  **预配 hololens 2 设备**"。
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何刚刷新的 HoloLens。 然后按 **下音量**  +  **键**，以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

适用于业务线应用的 MDM 应用部署和管理对于 HoloLens 至关重要。 管理员和用户需要查看应用安装状态以进行审核和诊断。 在此版本中，我们在 **设置**  >  **帐户**  >  **访问工作或学校**  >  **单击你的帐户信息时添加了**  >  更多详细信息。

### <a name="additional-csps-and-policies"></a>其他 Csp 和策略

[ (CSP) 的配置服务提供程序](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一个用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们添加了对更多策略的支持，以提高管理员对已部署的 HoloLens 设备的控制。 有关 HoloLens 支持的 Csp 列表，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们为 HoloLens 添加了新策略，这里列出了这些策略。 若要了解详细信息，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 配置服务提供程序创建 (QoS) 策略的网络服务质量。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 若要了解详细信息，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>为 5G/LTE 受限设备扩展 USB 以太网支持

添加了支持，以使某些移动宽带设备（例如 5G/LTE 手机和 Wi-Fi 热点）通过 USB 受限到 HoloLens 2 时使用。 这些设备现在作为另一个以太网连接显示在 " **网络设置** " 中。  (不支持需要外部驱动程序的移动宽带设备。 ) 此功能在 Wi-Fi 不可用时启用了高带宽连接，并且 Wi-Fi tethering 的性能不够高。 若要了解有关受支持的 USB 设备的详细信息，请参阅 [连接到蓝牙和 USB 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手动跟踪改进

此版本包含多项跟踪改进：

- 指示 **稳定性：** 系统现在在拒绝封闭像素时，会对索引手指进行弯曲。 当你推送按钮、类型、滚动内容和其他内容时，此更改会提高准确性！ 
- **减少了意外的空中点击：** 我们改进了对 $ 攻分流手势的检测。 现在几个常见情况下的意外激活次数较少，例如，当您将指针放在您的侧面时。
- **用户交换机可靠性：** 当你共享设备时，系统现在更快、更可靠。
- **精简的手偷窃：** 我们改进了对传感器进行两次干预的情况的处理。 如果有多个人密切合作，则现在会有很少的机会将用户从用户 "跳转" 到场景中的其他人。
- **系统可靠性：** 修复了一个问题，该问题导致手动跟踪在设备负载较高时停止工作。

### <a name="dark-mode"></a>深色模式

许多 Windows 应用现在支持深色和浅色模式。 HoloLens 2 用户可以为同时支持这两种应用的应用选择默认模式。 更新之后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 "**设置**" "  >  **系统**  >  **颜色**" "  >  **选择默认的应用模式**。 

这些 "内置" 应用支持暗色模式： 

- 设置 
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

你现在可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅 [使用语音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另请参阅 [HoloLens 2 支持的语言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### <a name="cortana-updates"></a>Cortana 更新

更新后的应用程序可与 Microsoft 365 集成，以帮助你在设备上进行更多的操作， (当前仅 US-English) 。 在 HoloLens 2 上，Cortana 不再支持某些特定于设备的命令，例如调整音量或重新启动。 新的系统语音命令现在支持这些选项。 在 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新 Cortana 应用的详细信息。

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中也有改进和修复：  
- 引入了活动的显示校准系统。 此功能可改善全息影像的稳定性和对齐方式。 当你从一侧到另一侧时，它们现在就会保持不变。
- 修复了一个 bug，在这种情况下，Wi-Fi 流式传输到 HoloLens 会定期中断。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode 函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。
- 修复了在研究模式下流式处理期间发生的设备挂起。
- 修复了一个 bug，在某些情况下，当恢复会话时，正确的用户将不会显示在登录屏幕上。
- 修复了用户无法通过 **设置** 导出 MDM 日志的问题。
- 修复了在全新安装后立即进行目视跟踪的准确性可能低于预期的问题。
- 修复了在某些情况下，眼睛跟踪子系统未能初始化或执行校准的问题。
- 解决了向已校准的用户提示目视校准的问题。
- 修复了驱动程序在目视校准过程中崩溃的问题。
- 解决了重复电源按钮按下的问题可能导致60秒系统超时和 shell 崩溃。
- 提高了深度缓冲区的稳定性。
- 在反馈中心添加了 " **共享** " 按钮，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan't 安装正确的 bug。

### <a name="known-issues"></a>已知问题

- Zh-chs 系统语言的问题会阻止语音命令采用混合现实捕获或显示设备 IP 地址。
- 问题要求在启动设备后启动 Cortana 应用以使用 "你好 Cortana" 语音激活。 如果从18362版本进行了更新，则在 **启动** 时，你可能还会看到以前版本的 Cortana 应用的第二个应用磁贴。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows 全息，版本 1903-5 2020 月更新 
- 生成18362.1061

这一月度质量更新不包含任何显著的更改，因为团队正在处理 Windows 全息版本2004可能会更新，如前文所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1059

**支持的应用的深色模式** 

许多 Windows 应用都支持深色和浅色模式。 HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认的应用模式设置为 "深色"，但你随时可以轻松地更改此设置：导航到 " **设置" > 系统 > 颜色** "以找到 **" 选择你的默认应用模式 "。**

这些 "内置" 应用支持暗色模式：
- 设置
- Microsoft Store
- Mail
- 日历
- 文件资源管理器
- 反馈中心
- OneDrive
- 照片
- 3D 查看器
- 电影和电视

**更新中也有改进和修复：** 
- 确保在混合现实捕获中包含 shell 重叠。
- Unreal 开发人员现在可以在设备门户中使用3D 视图页面来测试和调试应用程序。
- 当使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，混合现实捕获中改进了全息图稳定性。
- 修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows 全息，版本 1903-2020 更新 
- 生成18362.1056

更新中的改进和修复：

- 当使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，混合现实捕获中改进了全息图稳定性。
- 确保连接到深度 MF 示例的坐标系与公共文档一致。
- 通过使客户能够通过设备门户粘贴大量文本，提高开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows 全息，版本 1903-2020 更新 
- 生成18362.1053

更新中的改进和修复：

- 暂时禁用了 Unity 应用程序的 HolographicSpace. UserPresence API。 此更改避免了在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。
- 修复了手动跟踪引起的随机 HUP 崩溃，在这种情况下，用户会注意到，在几秒钟后，UI 冻结后会返回到 shell。
- 改善了手动跟踪，这样当你通过食指时，该手指的上半部分就不会意外地弯曲。
- 提高了头跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows 全息，版本 1903-2020 更新 
- 生成18362.1043
 
更新中的改进和修复：

- 使用 HoloLens 2 模拟器时，对独占应用的稳定性得到提高。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows 全息，版本 1903-2019 更新 
- 生成18362.1042

更新中的改进和修复：

- 引入了 (LSR) 修补程序的最后阶段复制。 改善了全息影像渲染，使其深度更准确地显示更稳定，更清晰。 如果应用未正确设置全息影像的深度，则此更新后，此症状将更为明显。
- 固定应用和独占应用之间的导航的固定稳定性。
- 解决了在设备处于待机状态几天后混合现实捕获无法录制视频的问题。
- 改善了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows 全息，版本 1903-2019 更新 
- 生成18362.1039

更新中的改进和修复：

- 修复了在初始安装过程中用于 en CA 和 en-us 的 **选择** 语音命令的功能。
- 提高了在最新 Unity 和混合现实工具包中放置的对象的视觉质量 (MRTK) 版本。
- 修复了在打开 "开始" 菜单并关闭之前，内置应用程序在启动时停滞处于暂停状态的问题。
- 针对 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。
