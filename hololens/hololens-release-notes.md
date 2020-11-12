---
title: HoloLens 2 发行说明
description: 了解每个新的 HoloLens 2 版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: df8d6e2c00bd8ff8507be4a2fd58c773d8833c11
ms.sourcegitcommit: 20ff249e3570c74f62cdf6339c8be76c401d9f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "11165972"
---
# HoloLens 2 发行说明

为确保您的 HoloLens 设备具有高效的体验，我们将继续发布功能、缺陷和安全更新。 在此页面上，您可以查看每月 HoloLens 的新增功能。 若要获取最新的 HoloLens 2 更新，你可以 [检查更新并手动更新](hololens-update-hololens.md#check-for-updates-and-manually-update) 或获取完整的 Flash 更新 (FFU) [通过 "高级恢复助理" 将你的设备闪存](hololens-recovery.md#clean-reflash-the-device)，请 [在此处下载](https://aka.ms/hololens2download)。 下载将保持最新状态，并提供最新的通用内部版本。

>[!NOTE]
> 若要阅读 HoloLens 模拟器发行说明，请 [访问存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)。

## Windows 全息版20H2
- 内部版本19041.1128

Windows 全息版20H2 现已推出，并向 HoloLens 2 用户和 IT 专业人员提供了一组强大的新功能。 从自动目视定位，到 "设置" 中的 "证书管理器"，到改进的展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更细致地控制配置和管理 HoloLens 设备，并为用户提供更流畅的全息体验。 

此最新版本是对版本2004的每月更新，但这次我们包括新功能。 主内部版本号将保持不变，Windows 更新将指示每月发布到版本 2004 (内部版本 19041) 。 你可以在 "设置" > "关于屏幕" 中查看内部版本号，以确认你使用的是最新的版本 19041.1128 +。 若要更新到最新版本，请打开 "设置" 应用，转到 "更新 & 安全性"，然后点击 "检查更新"。 有关如何管理 HoloLens 更新的详细信息，请访问 [此页面](https://docs.microsoft.com/hololens/hololens-updates)。

### Windows 全息版20H2 中的新增功能  

| 功能                                              | 描述                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算目视的位置，而无需用户通过目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许从 "设置" 应用中安装和删除证书的更简单方法。     |
| [来自 USB 的自动启动预配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 预配 USB 驱动器上的程序包会自动提示 OOBE 中的预配页面。                                                         |
| [在 OOBE 中自动确认预配程序包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配包将在 OOBE 期间从设置页面自动应用。                                                         |
| [自动预配，不使用 UI](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将预配自动启动和自动确认结合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，而无需使用以太网适配器。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册和应用策略后，设备在重置或重新刷新设备时，即可随时在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个应用展台模式的新配置方法，可在系统级别应用展台，使其适用于所有。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录到多应用展台模式时自动启动。                                                        |
| [故障处理的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制性的回退。                                                                                                |
| [HoloLens 政策](hololens-release-notes.md#hololens-policies)                                    | 适用于 HoloLens 的新策略。     |
| [缓存脱机展台的 AAD 组成员身份](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | 新策略允许用户使用组成员身份缓存在设置的天数内脱机使用展台模式。                                        |
| [适用于 HoloLens 2 的新设备限制策略](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 新启用了 HoloLens 2 的设备管理策略。                                                                                |
| [HoloLens 2 的新 power 策略](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允许控制更新的新启用的策略。           |
| [已启用 HoloLens 2 的设置页面可见性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选择在 "设置" 应用中显示哪些页面的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [录制长度增加](hololens-release-notes.md#recording-length-increased) | MRC 录制不再超过5分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修复程序。   |

### 自动眼部位置支持

在 HoloLens 2 中，眼部位置可实现准确的全息影像定位、舒适的观看体验和改进的显示质量。 目视位置作为目视跟踪计算的一部分在内部进行计算。 但是，这要求每个用户都可以通过目视跟踪校准，即使体验可能不需要目视的注视输入也是如此。

**自动眼部位置 (AEP)** 使这些场景能够以无交互方式为用户眼部位置。 从用户戴上设备开始，“自动眼部位置”将自动在后台开始工作。 如果用户没有以前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视将开始向显示系统提供用户的目视位置。 用户数据不会保留在设备上，因此，如果用户取下并重新戴上设备，或者设备重新启动或从睡眠状态唤醒，则会重复此过程。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在此上下文中，uncalibrated 用户是指尚未经历过设备上的目视跟踪校准过程的人员。

| 活动应用程序 | 以前的行为 | 来自 Windows 全息版、版本20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |"目视跟踪校准提示" 对话框随即显示。 | 不显示提示。 |
| 已启用凝视的应用 | "目视跟踪校准提示" 对话框随即显示。 | 仅当应用程序访问眼睛注视流时，才会显示目视跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。 

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将与此类似。 例如，将不会启用一次性开始手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛数据或非常精确的全息图位置的体验，我们建议 uncalibrated 用户运行目视跟踪校准。 可通过目视跟踪校准提示或从 "开始" 菜单启动 "设置" 应用，然后选择 " **系统 > 校准" > 目视校准 > "运行目视校准**"。

此信息可以在以后与 [其他校准信息](hololens-calibration.md#auto-eye-position-support)一起找到。 

### 证书管理器

- 通过新的证书管理器改进了针对设备安全性和合规性的审核、诊断和验证工具。 利用此功能，你可以在商业环境中按比例部署、排除和验证你的证书。

在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 转到 " **设置" > 更新 & 安全 > 证书**。 此功能为查看、安装和删除设备上的证书提供了一种简单且易于用户理解的方法。 通过新的证书管理器，管理员和用户现已改进了审核、诊断和验证工具，以确保设备保持安全和合规。 

-   **审核：** 验证是否已正确部署证书或确认是否已正确删除证书的功能。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间并帮助进行故障排除。 
-   **验证：** 验证证书是否服务于预期用途且正常运行，可以节省大量时间，尤其是在商业环境中，在以较大比例部署证书之前。

若要快速查找列表中的特定证书，有一些选项可按名称、存储或过期日期进行排序。 用户也可以直接搜索证书。 若要查看单个证书属性，请选择证书，然后单击 " **信息**"。 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户都只能安装到当前用户。 用户只能从 "设置" UI 中删除直接安装的证书。 如果证书已通过其他方法安装，则它还必须由相同的机制删除。

#### 要安装证书，请执行以下操作： 

1.  将 HoloLens 2 连接到电脑。
1.  将要安装的证书文件放在 HoloLens 2 上的某个位置。
1.  导航到 " **设置" 应用 > 更新 & 安全 > 证书**，然后选择 "安装证书"。
1.  单击 " **导入文件** "，然后导航到保存证书的位置。
1.  选择 " **存储位置**"。
1.  选择 " **证书存储**"。
1.  单击**安装**。

证书现在应安装在设备上。

#### 要删除证书，请执行以下操作： 
1. 导航到 " **设置" 应用 > 更新和安全 > 证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 提示确认时，请选择 **"是"** 。

!["设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

此信息稍后可 [在新的证书管理器页面中](certificate-manager.md)找到。

### 来自 USB 的自动启动预配

- 在 OOBE 期间使用具有预配程序包的 USB 驱动器时，自动化的流程允许较少的用户交互。

在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，以使用按钮组合。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个交互时刻插入带有预配包的 USB 驱动器
1. 准备好预配设备后，将自动通过预配页面打开提示。 

注意：如果在设备启动时插入了一个 USB 驱动器，则 OOBE 将枚举现有的 USB 存储设备，还会监视插入的其他设备。

有关在 OOBE 期间应用预配程序包的详细信息，请继续阅读 [此处](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

此信息可在此处找到 [。](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### 在 OOBE 中自动确认预配程序包
- 自动化流程允许较少的用户交互，当 "预配程序包" 页面显示时，它将自动应用列出的所有程序包。

当预配主屏幕出现时，OOBE 将在10秒后自动开始应用所有预配程序包。 用户在验证所需的程序包后，仍可在此10秒内确认或取消。

此信息可在此处找到 [。](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### 自动预配，不使用 UI
- 合并了自动流程以减少设置的设备交互。 

通过将预配的自动启动与 USB 设备中的自动启动和预配程序包的自动确认结合使用，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至戴设备。 你可以继续对多台设备使用相同的 USB 驱动器和预配程序包。 这对于在同一区域同时部署多个设备很有用。 

1. 使用[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)[创建预配包](hololens-provisioning.md)。 
1. 将程序包复制到 USB 存储驱动器。
1. 将[HoloLens 2 闪存](hololens-insider.md#ffu-download-and-flash-directions)到[19041.1361 或更高版本](https://aka.ms/hololens2previewdownload)。 
1. 当 " [高级恢复" 助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成闪烁时，您的设备将拔出 USB-C 电缆。 
1. 将您的 USB 驱动器插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它将自动检测 USB 驱动器上的预配包并启动预配页面。
1. 10秒后，设备将自动应用预配包。 

你的设备现已配置，并将显示预配成功屏幕。

此信息可在此处找到 [。](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### 将 Autopilot 与 Wi-Fi 连接结合使用
- 已删除对以太网减少硬件需求的 USB-C 适配器的需要，方法是启用 Autopilot 以在 Wi-Fi 连接的设备上运行。

现在，在 OOBE 期间，一旦通过 Wifi 连接了 HoloLens 2，OOBE 将检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，对 usb-C 或 Wi-Fi 到 USB-C 适配器的使用以太网不再是必需的，但是如果在 OOBE 开始时提供，它们仍可继续正常工作。 了解有关 [HoloLens 2 设备的 Autopilot 的](hololens2-autopilot.md)详细信息。

### Tenantlockdown CSP 和 Autopilot
- 将设备锁定到租户后，即使进行设备重置或重新刷新也可将设备保留在组织的租户上。 通过预配禁用帐户创建，进一步增强安全性。 

HoloLens 2 设备现在支持 TenantLockdown for [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中的 CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使进行重新刷新、操作系统更新，该值仍将保留在设备上。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后， OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许执行以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 AAD 加入操作 
- 在 OOBE 体验中选择设备所有者 

#### 如何使用 Intune 设置此选项？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 一旦此设备配置成功应用于 HoloLens 2 设备，TenantLockdown 的效果将处于活动状态。

#### 如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从先前分配了上面创建的设备配置的设备组中删除 HoloLens 2。 

1. 创建基于 OMA URI 的自定义设备配置配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 一旦此设备配置成功应用于 HoloLens 2 设备，TenantLockdown 的效果将处于非活动状态。 

#### 如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，则 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了消除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown CSP 引入的限制。 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

此信息现在还可以在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的其余 Autopilot 中找到。

### 全局分配的访问-展台模式
- 通过启用在系统级别应用展台模式的新展台方法，减少了展台的身份管理。

此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识都没有相关性，并且适用于登录设备的每个人。 请在此仔细阅读此新增[功能。](hololens-global-assigned-access-kiosk.md)

### 在多应用展台模式下自动启动应用程序 
- 通过自动应用启动的重点体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能将1个应用指定为使用 "分配的访问配置" 下方的突出显示属性自动启动。 

应用程序将在用户登录时自动启动。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 故障处理的展台模式行为更改
- 通过在展台模式失败上消除可用应用，更安全地保护展台模式。 

早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 现在在 Windows 全息版20H2 中，在出现故障的情况下，"开始" 菜单中不会显示任何应用，如下所示： 

!["展台" 模式的图像在失败时立即显示。](images/hololens-kiosk-failure-behavior.png )

### HoloLens 政策
- 专用于为管理设备而创建的 HoloLens 的设备管理选项。 

在 Windows 全息版20H2 上为 HoloLens 2 设备创建了新的混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、可收集诊断的设置以及 AAD 组成员身份缓存。  

| 新的 HoloLens 政策                                | 描述                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，因此按住它不会更改亮度。       | 1是，0否 (默认值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，因此按下不会更改音量。               | 1是，0否 (默认值)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此在 HoloLens 2 上不能录音。                      | 1是，0否 (默认值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集诊断日志的行为。                               | 0已禁用，1为设备所有者启用1，为所有 (默认值启用 2)  |
| MixedReality\HeadTrackingMode                      | 保留以供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制 AAD 组成员身份缓存用于面向 AAD 组的展台的天数。 | 请参阅下文。                                                           |

### 缓存脱机展台的 AAD 组成员身份
- 已启用与 AAD 组一起使用的离线用户，最多可达60天。

此策略控制允许将 AAD 组成员身份缓存用于分配用于登录用户的 AAD 组的分配访问配置的天数。 一旦将此策略值设置为大于0的值，否则将使用缓存。  

名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值-0 天  
最大-60 天 

正确使用此策略的步骤： 
1. 为面向 AAD 组的展台创建设备配置文件，并将其分配到 HoloLens 设备 (s) 。 
1. 创建基于自定义 OMA URI 的设备配置，将此策略值设置为所需的天数 ( # 0) ，并将其分配到 HoloLens 设备 (s) 。 
    1. 应在/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays 中将 URI 值输入到 "OMA URI" 文本框中。
    1. 值可以介于 min/max 允许之间。
1. 注册 HoloLens 设备并验证这两种配置均已应用到设备。 
1. 允许 AAD 用户1登录当 internet 可用时，一旦用户登录和 AAD 组成员身份已成功确认，将创建缓存。 
1. 现在，AAD 用户1可以将 HoloLens 脱机，并将其用于展台模式，前提是策略值允许 X 天。 
1. 可以为任何其他 AAD 用户 N 重复执行步骤4和步骤5。此处的关键点是任何 AAD 用户必须使用 Internet 登录到设备，因此至少可以确定它们是对其进行目标展台配置的 AAD 组的成员。 
 
> [!NOTE]
> 直到针对 AAD 用户执行步骤4时，才会在 "断开连接的" 环境中遇到故障行为。 

### 适用于 HoloLens 2 的新设备限制策略
- 允许用户管理特定的设备管理策略，例如阻止添加或删除预配程序包。

允许 HoloLens 2 设备的更多管理选项的新启用的策略。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的这两个新策略将添加到我们的 [常见设备限制](hololens-common-device-restrictions.md)中。

### HoloLens 2 的新 power 策略
- 当 HoloLens 休眠或通过电源策略锁定时的更多选项。 

这些新添加的策略允许管理员控制电源状态，如空闲超时。 若要阅读有关每个单独策略的详细信息，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 配置设计器中使用的示例值，即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 配置设计器中使用的示例值，即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的这两个新策略将添加到我们的 [常见设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 为获得 HoloLens 2 上的一致体验，请确保 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值均设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式待机的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### 适用于 HoloLens 的新启用的更新策略
- 有关安装更新或禁用 "暂停更新" 按钮以确保更新的更多选项。

现已在 HoloLens 2 设备上启用这些更新策略：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关 thise 更新策略以及如何使用 HoloLens 设备的完整详细信息，请参阅 [管理 hololens 更新](hololens-updates.md)。

### 已启用 HoloLens 2 的设置页面可见性
- "设置" 应用中增加的 UI 控件，这可能会与显示有限的页面范围相混淆。

现已启用策略，允许 IT 管理员防止系统设置应用中的特定页面可见或易于访问，或者针对除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解在 HoloLens 2 上可以自定义的页面设置，请访问我们的 " [设置 uri" 页面](settings-uri-list.md)。 
 
![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

### 研究模式
在研究模式下，HoloLens 2 成为计算机远景研究的 potent 工具。 与以前的版本相比，HoloLens 2 的研究模式具有以下优点：
-   除了 HoloLens 中显示的传感器 (第一代) 研究模式中，我们现在提供 IMU 传感器访问，包括加速计、gyroscope 和磁力计。
-   HoloLens 2 提供了可与研究模式结合使用的新功能。 尤其是，可以访问可提供更丰富的实验集的可表述的手动跟踪和目视跟踪 Api。

研究人员现在可以选择在其 HoloLens 设备上启用研究模式，以访问所有外部面向的裸图像传感器流。 HoloLens 2 的研究模式还提供对加速计、gyroscope 和磁力计读数的访问。 为了保护用户的隐私，无法通过 "信息检索" 模式获取原始目视跟踪相机图像，但目视方向可通过现有 Api 使用。

有关技术详细信息，请查看 [信息检索模式文档](https://docs.microsoft.com/windows/mixed-reality/research-mode) 。

### 录制长度增加
由于客户反馈，我们增加了 [混合现实捕获](holographic-photos-and-videos.md)的录制长度。 默认情况下，混合现实捕获将不再限制为5分钟，而是将根据可用磁盘空间计算最大录制长度。 设备将根据可用磁盘空间达到总磁盘空间的80%，估计最大视频录制持续时间。

> [!NOTE]
> 如果出现以下情况之一，则 HoloLens 将使用默认视频录制长度 (5 分钟) ：
> - 估计的最大录制持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

可 [在此处](holographic-photos-and-videos.md#maximum-recording-length)再次找到此信息。 

### 更新中的改进和修复：
- OOBE 中的更多屏幕现在处于深色模式。
- 了解更多内容应联机了解最新的隐私声明。
- 解决了用户无法通过预配程序包预配 VPN 配置文件的问题。
- 已修复 VPN 连接的代理配置问题。
- 已更新策略以禁用通过 MDM for AllowUsbConnection 对 USB 函数进行枚举的 NCM。
- 解决了在将设备设置为 [单应用展台](hololens-kiosk.md)时，导致 HoloLens 设备无法在文件资源管理器中显示在媒体传输协议 (MTP) 的问题。 请注意，常规) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略禁用。
- 修复了 "开始" 菜单中的图标在展台模式下正确缩放的问题。
- 修复了由于 HTTP 缓存干扰针对 AAD 组的展台模式而导致的问题。
- 修复了在启用具有预配程序包的开发人员模式时用户无法使用配对按钮的问题，除非它们禁用且重新启用了开发人员模式。

## Windows 全息版、版本 1903-2020 更新
- 内部版本18362.1085

此每月质量更新不包含任何显著更改，我们鼓励你试用最新功能版本 Windows 全息版20H2。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1124
 
更新中的改进和修复：

- 已删除导致运行时系统错误的不必要检查。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1081

此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1117

更新中的改进和修复：

- 解决了阻止 Visual Studio 在 package.appxmanifest 中存在 SupportsMultipleInstances = "true" 时调试应用程序的问题。
- 此版本包括 NCSI 代理检测修复，以解决通过网络代理进行的 Internet 检测失败。 NCSI 可以使用计算机代理和每个配置文件的代理进行 Internet 连接检测。 未来版本中的 NCSI 将支持每用户代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。 但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。
- 改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。
- 此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。 但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。
- 改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1113

更新中的改进和修复：

- "设置" 应用将不再关注用户进入虹膜注册或目视跟踪校准体验。
- 修复了在 OOBE 期间应用预配包的 bug，用于重命名设备并执行其他操作 (例如，连接到网络) 将无法在设备重启（由于重命名）后执行其他操作。
- 已修改初始设备设置流的配色方案，以提高视觉质量。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1074

此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。

## Windows 全息版 2004-2020 年7月更新
- 内部版本19041.1109

更新中的改进和修复：

- 现在，开发人员可以在启用或禁用设备门户时选择是否需要安全连接。
- 操作系统更新后，应用程序启动时的可靠性有所改进。
- 已将默认收件箱亮度更改为100%。
- 解决了有关 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发的问题。

## Windows 全息版 1903-2020 年7月更新
- 内部版本18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能会导致全息图在丢失或执行跟踪时无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用 HoloLens 模拟器和硬件加速时，导致独占 HoloLens 应用崩溃的问题。
- 解决了与 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发有关的问题。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1106

更新中的改进和修复：

- 如果未指定某些属性，自定义 MRC 记录器现在具有新的默认值。
  - 在 " *MRC 视频" 效果*中：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5
  - 在 " *MRC 音频" 效果*中：
    - LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) 
    - MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) 
- 修复了在混合现实捕获方案中提高音频质量的 bug。 尤其是，此修补程序应在显示 " **开始** " 菜单时消除录制中的音频 glitching。
- 改进了录制视频中的全息图稳定性。
- 解决了在设备离开待机状态几天后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。 此行为可避免在面板翻转时导致某些应用暂停的问题，即使已启用 "在后台运行" 设置。 现已针对 Unity 版本2018.4.18 及更高版本和2019.3.4 及更高版本启用 API。
- 通过 Wi-Fi 连接访问 Device Portal 时，web 浏览器可能会阻止访问，因为证书无效。 浏览器可能会报告诸如 "ERR_SSL_PROTOCOL_ERROR" 之类的错误，即使设备证书以前已受信任。 在这种情况下，你无法对 Device Portal 进行进度，因为没有用于忽略安全警告的选项。 此更新解决了此问题。 如果以前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并信任该证书才能解决浏览器安全警告。
- 已启用创建可使用 MSIX 程序包安装应用的运行时预配包的功能。
- 在**设置**系统全息图中添加了一项设置  >  **System**  >  **Holograms** ，使用户可以在设备关闭时自动删除混合现实主页中的所有全息影像。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了在虹膜登录期间导致崩溃的 bug。
- 修复了有关为现有应用重复下载的应用的问题。
- 修复了一个 bug 以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版本更新后初始引导中的 "照片" 应用启动时出现的问题。
- 提高了性能和可靠性。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1064

更新中的改进和修复：

- 如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。
  - 在 " *MRC 视频" 效果*中：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5
  - 在 " *MRC 音频" 效果*中：
    - LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) 
    - MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) 
- 对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。 此行为可避免在面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。 现已针对 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用 API。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了从1903版本更新后初始启动时启动照片应用的问题。

## Windows 全息版2004  
- 内部版本-19041.1103

适用于 HoloLens 2、 *Windows 全息版、版本 2004* 的2020主要软件更新包括一种令人兴奋的新功能，例如对 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LTE 热点的支持等。 若要更新到最新版本，请打开 "**设置**"   应用，转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 为生产预配置和无缝设置新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥以对共享设备启用快速和安全身份验证            |
|       改进的预配                      |          将预配包从 u 盘无缝应用到 HoloLens                              |
|       应用程序安装状态                 |          在应用的 "设置" 应用中检查安装状态已通过 MDM 推送到 HoloLens 2               |
|        (Csp) 的配置服务提供商   |          添加了新的配置服务提供程序以增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          扩展的 USB 以太网功能支持 5G/LTE 支持                                    |
|       深色应用模式                              |          适用于支持深色模式和浅色模式的应用的深色应用模式，改善了查看体验        |
|       语音命令                             |          支持用于控制 HoloLens 免提的其他系统语音命令                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 平板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### Windows Autopilot 支持

用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道预注册 HoloLens 到你的 Intune 租户。 当设备到达时，它们准备就绪，可以作为你的租户下的共享设备进行自我部署。 若要充分利用自部署，设备必须在安装程序的第一个屏幕中使用 USB-以太网连接到网络。

用户启动 Autopilot 自部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。
1. 下载面向设备的策略、证书和网络配置文件。
1. 预配设备。
1. 向用户呈现登录屏幕。

请通过适用于 [HoloLens 2 评估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)了解详细信息。

*请与您的帐户管理员联系，立即加入 AutoPilot 预览版。 Autopilot 已准备好的设备即将开始发货。*

### FIDO2 安全密钥支持

某些用户在工作或学校环境中与其他用户共享一个 HoloLens 设备。 因此，用户不必输入长的用户名和密码，就很重要。 快速身份联机 (FIDO) 允许你组织中的任何人 (Azure AD 租户) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是一种基于标准的 "unphishable" passwordless 身份验证方法，可采用任何形式的外观。 FIDO 是一种用于 passwordless 身份验证的开放式标准。 它允许用户和组织无需用户名或密码即可登录到其资源。 而是使用内置的安全密钥或内置于设备的平台密钥。

若要开始使用，请参阅 [启用 passwordless 安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### 通过预配包改进了 MDM 注册

预配程序包允许你通过配置文件（而不是 HoloLens 全新体验）设置 HoloLens 配置。 以前，必须将预配包复制到 HoloLens 内部内存。 现在，他们可以在 USB 驱动器上使用，以便更轻松地在多个 HoloLens 设备上重用，并且可以并行预配设备。 预配程序包现在还支持用于注册设备管理的字段，因此预配后无手动设置。

若要试用：

1. 将 windows 配置设计器的最新版本从 Windows 应用商店下载到你的电脑。
1. 选择 "**预配 hololens 设备**"  >  **预配 hololens 2 设备**。
2. 构建配置文件。 然后将创建的所有文件复制到一个 USB-C 存储设备。
3. 将 USB-C 设备插入任何全新刷新的 HoloLens。 然后按**音量按下**  +  **电源**按钮以应用预配包。

### 业务线应用程序安装状态

适用于 HoloLens 的 MDM 应用部署和业务线应用的管理是 HoloLens 的关键。 管理员和用户需要查看用于审核和诊断的应用安装状态。 在此版本中，我们在**设置**帐户中添加了更多详细信息  >  **Accounts**  >  **访问工作或学校**  >  **单击您的帐户**  >  **信息**。

### 其他 Csp 和策略

[配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们添加了对更多策略的支持，以增加管理员对已部署的 HoloLens 设备的控制。 有关 HoloLens 支持的 Csp 列表，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

此版本中的新增内容：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们为 HoloLens 添加了新策略，这些策略将在此处列出。 若要了解详细信息，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 配置服务提供程序创建网络服务质量 (QoS) 策略。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 若要了解详细信息，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### 已展开的 USB 以太网支持 5G/LTE tethered 设备

已添加支持以启用某些移动宽带设备，如 5G/LTE 电话和 Wi-Fi hotpots，它们通过 USB tethered 到 HoloLens 2。 这些设备现在在 " **网络设置** " 中显示为另一个以太网连接。 不支持需要外部驱动程序的 (移动宽带设备。 ) 此功能可在 Wi-Fi 不可用时启用高带宽连接，并且 Wi-Fi 的 tethering 没有足够的性能。 若要了解有关受支持的 USB 设备的详细信息，请参阅 [连接到蓝牙和 USB-C 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 手动跟踪改进

此版本包括多项跟踪改进：

- **指针具有稳定性：** 现在，系统通过 palm 获取 occluded 时，resists 将对食指进行弯曲。 当你推送按钮、键入、滚动内容等时，此更改可提高精确度。 
- **减少了意外的空中点击：** 我们改进了对空中点击手势的检测。 现在，在几种常见方案中（例如，当您将手放到您的一侧时），会减少意外激活的次数。
- **用户切换可靠性：** 当您共享设备时，系统现在可以更快、更可靠地更新手形大小。
- **减少右手偷窃：** 我们改进了对传感器的两次手的处理情形。 如果多人一起密切协作，现在，所跟踪的手势将从用户 "跳转" 到场景中其他人的手边。
- **系统可靠性：** 修复了当设备处于高负载时导致手动跟踪停止工作的问题。

### 深色模式

许多 Windows 应用现在支持深色模式和浅色模式。 HoloLens 2 用户可以为支持两者的应用选择默认模式。 更新后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 "**设置**"  >  **系统**  >  **颜色**  >  **选择默认应用模式**。 

这些 "机箱中" 应用支持深色模式： 

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

### 系统语音命令

现在，你可以将语音命令与设备上的任何应用配合使用。 有关详细信息，请参阅 [使用语音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另请参阅 [HoloLens 2 支持的语言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana 更新

已更新的应用与 Microsoft 365 集成以帮助你在设备上进行更多的操作 (当前仅 US-English) 。 在 HoloLens 2 上，Cortana 不再支持特定于设备的命令，如调整音量或重启。 新的系统语音命令现在支持这些选项。 在我们的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新的 Cortana 应用的详细信息。

### 质量改进和修复

更新中也有改进和修复：  
- 引入了活动的显示校准系统。 此功能可改善全息影像的稳定性和对齐方式。 当您的打印头并排移动时，它们将保留在原地。
- 修复了 Wi-Fi 到 HoloLens 的数据流定期中断的 bug。 如果应用程序指示它需要低延迟流，请通过调用 [SetSocketMediaStreamingMode 函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。
- 修复了在研究模式下流式处理期间发生的设备挂起。
- 修复了一个 bug，在某些情况下，在恢复会话时，在登录屏幕上无法显示正确的用户。
- 修复了用户无法通过 **设置**导出 MDM 日志的问题。
- 修复了立即关注全新设置的目视跟踪的问题，这可能比预期的要低。
- 修复了目视跟踪子系统无法在特定条件下初始化或执行校准的问题。
- 修复了提示校准已校准用户的问题。
- 修复了在目视校准期间驱动程序崩溃的问题。
- 修复了重复的电源按钮按下可能导致60秒系统超时和外壳崩溃的问题。
- 改善了深度缓冲区的稳定性。
- 在 "反馈中心" 添加了 " **共享** " 按钮，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan't 正确安装的 bug。

### 已知问题

- Zh-cn&platform 系统语言的问题阻止语音命令接受混合现实捕获或显示设备 IP 地址。
- 问题要求你在启动设备后启动 Cortana 应用以使用 "你好 Cortana" 语音激活。 如果从18362版本更新，你可能还会看到以前版本的 Cortana 应用的第二个应用磁贴，在 **开始**时不再有效。

## Windows 全息版 1903-五月2020更新 
- 内部版本18362.1061

此每月质量更新不包含任何显著的更改，因为团队正在处理 Windows 全息版本2004可能会更新，如前文所述。

## Windows 全息版 1903-2020 年4月更新
- 内部版本18362.1059

**支持的应用的深色模式** 

许多 Windows 应用均支持深色模式和浅色模式。 HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为 "深色"，但你可以随时轻松地更改此设置：导航到 " **设置" > "系统 > 颜色** " 以找到 **"选择默认应用模式"。**

这些 "机箱中" 应用支持深色模式：
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

**更新中也有改进和修复：** 
- 确保在混合现实捕获中包含外壳覆盖。
- Unreal 开发人员现在可以使用 Device Portal 中的3D 视图页面来测试和调试其应用程序。
- 在使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，在混合现实捕获中改进了全息图稳定性。
- 修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。

## Windows 全息版、版本 1903-2020 更新 
- 内部版本18362.1056

更新中的改进和修复：

- 在使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，在混合现实捕获中改进了全息图稳定性。
- 已确保连接到 depth MF 示例的坐标系与公共文档一致。
- 通过让客户通过 device portal 粘贴大量文本，提高了开发人员的工作效率。

## Windows 全息版 1903-2 月2020更新 
- 内部版本18362.1053

更新中的改进和修复：

- 已暂时禁用 Unity 应用程序的 UserPresence API HolographicSpace。 此更改避免了在面板翻转时导致某些应用暂停的问题，即使 "在后台运行" 设置也是如此。
- 修复了手动跟踪导致的随机 HUP 崩溃，在此情况下，用户注意到 UI 冻结，然后在几秒钟后返回到外壳。
- 改善了手动跟踪，以便在您用食指向您外出时，该手指的上半部分不太可能意外卷曲。
- 改进了 head 跟踪、空间映射和其他运行时的可靠性。

## Windows 全息版 1903-2020 更新 
- 内部版本18362.1043
 
更新中的改进和修复：

- 使用 HoloLens 2 模拟器时，改进了独占应用的稳定性。

## Windows 全息版 1903-2019 更新 
- 内部版本18362.1042

更新中的改进和修复：

- 引入了上一阶段复制 (LSR) 修复。 改进了全息图的视觉呈现，使其更准确地获得更稳定的深度。 如果应用未正确设置全息影像的深度，此更新后的症状将更明显。
- 固定应用和独占应用之间导航的固定稳定性。
- 解决了在设备处于待机状态几天后混合现实捕获无法录制视频的问题。
- 改进了全息图稳定性。

## Windows 全息版、版本 1903-2019 更新 
- 内部版本18362.1039

更新中的改进和修复：

- 固定的功能：在初始设置中为 en-us 和 en-us **选择** 语音命令。
- 改进了在最新的 Unity 和混合现实工具包中最远地放置的对象的视觉质量 (MRTK) 版本。
- 修复了在启动时，全息应用程序在处于暂停状态时处于暂停状态的问题，直到打开 "开始" 菜单，然后关闭。
- 适用于 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。
