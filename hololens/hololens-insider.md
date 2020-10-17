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
ms.date: 10/15/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 408bf94b4cec49b91198917c16f83012fa9ab644
ms.sourcegitcommit: a81d48d362f8511960e74d38c7c8f0cff19b67c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119295"
---
# Microsoft HoloLens 内部预览版

欢迎使用适用于 HoloLens 的最新预览体验计划预览版！ 这是一种非常简单的功能 [，可提供](hololens-insider.md#start-receiving-insider-builds) 针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。

## Windows 预览体验计划发行说明

下面是您可以在 Windows 预览体验计划内部版本中试用的即将推出的功能列表。

| 功能                                                | 描述                                                                                    | 在预览体验成员内部版本中可用 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [自动目视位置支持](hololens-insider.md#auto-eye-position-support)                              | 主动计算眼睛位置并支持准确的全息图定位。                        | 19041.1339 +                 |
| [证书管理器](hololens-insider.md#certificate-manager)                                     | 用户可以在 "设置" 应用中查看、安装和删除当前用户和本地计算机证书的证书。                                         | 19041.1361 +                 |
| [来自 USB 的自动启动预配](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE 会自动检测 USB 驱动器上的预配程序包。                                | 19041.1361 +                 |
| [在 OOBE 中自动确认预配程序包](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | 在 OOBE 中自动应用预配程序包。                                             | 19041.1361 +                 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | 从设备 Wi-Fi 使用 autopilot，而无需使用以太网适配器。                             | 19041.1364 +                 |
|[Tenantlockdown CSP 和 Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | 应用租户注册和应用策略后，设备在重置或重新刷新设备时，即可随时在该租户中注册。 | 19041.1366 +|
| [全局分配的访问权限](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | 配置适用于系统级别的多个应用展台模式的 HoloLens 2 设备。 | 19041.1356 +                 |
| [在多应用展台中自动启动应用](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 将应用程序设置为在登录到多应用展台模式时自动启动。     | 19041.1346 +                 |
| [故障处理的展台模式行为更改](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 现在已处理展台模式故障的更改。                                              | 19041.1356 +                 |
| [HoloLens 政策](hololens-insider.md#hololens-policies)                                      | 混合现实设备的新策略。                                                        | 19041.1349 +                 |
| [缓存脱机展台的 AAD 组成员身份](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | 针对展台模式允许使用 AAD 组成员身份缓存的天数的策略。    | 19041.1356 +                 |
| [适用于 HoloLens 2 的新设备限制策略](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | 新启用了 HoloLens 2 的设备管理策略。                               | 19041.1349 +                 |
| [HoloLens 2 的新 power 策略](hololens-insider.md#new-power-policies-for-hololens-2)                      | 新支持的电源超时设置策略。                                           | 19041.1349 +                 |
| [更新策略](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 允许控制更新的新启用的策略。                                            | 19041.1352 +                 |
| [已启用 HoloLens 2 的设置页面可见性](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 用于选择在 "设置" 应用中显示哪些页面的策略。                                           | 19041.1349 +                 |
|  [研究模式](hololens-insider.md#research-mode) | 在 HoloLens 2 上使用研究模式 | 19041.1375 + |
| [录制长度增加](hololens-insider.md#recording-length-increased) | MRC 录制不再超过5分钟。 | 19041.1387 + |
| [更新中的改进和修复](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 更新中的其他修复程序。                                                                | 19041.1361 +                 |


### 自动目视位置支持

在 HoloLens 2 中，目视位置支持准确的全息图定位、舒适的查看体验和改进的显示质量。 眼位置将作为眼睛跟踪结果的一部分进行计算。 但是，这要求每个用户都可以通过目视跟踪校准，即使体验不需要目视的注视输入也是如此。

** (AEP 的 "自动目视" 位置) ** 支持这些方案，使用无交互方式为用户计算眼睛位置。  自动目视位置在用户将设备置于设备上时自动从后台开始工作。 如果用户没有以前的目视跟踪校准，则在较小的处理时间后，自动目视的位置将开始向显示系统提供用户的目视位置。 此处理时间通常介于 20-60 秒之间。 用户数据不会保留在设备上，因此，如果用户关闭并重新放置设备或者设备重新启动或从睡眠中唤醒，则会重复此过程。  

当 uncalibrated 用户放在设备上时，有一些系统行为发生了自动目视定位功能。 Uncalibrated 用户指的是尚未经历过设备上的目视跟踪校准过程的人。

|     活动应用程序                           |     当前行为                                   |     来自 Windows 预览体验成员内部版本19041.1339 的行为 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     不支持注视的应用程序或全息外壳    |     将显示目视跟踪校准提示。    |     不显示提示。                                                                                |
|     注视 "已启用" 应用                             |     将显示目视跟踪校准提示。    |     仅当应用程序访问眼睛注视流时，才会显示目视跟踪校准提示。     |

 如果用户从一个不支持注视的应用程序切换到一个访问注视数据的应用程序，则将显示校准提示。 将不会更改为 "现成的体验" 流程。 
 
对于需要眼睛眼数据或非常精确的全息图位置的体验，我们建议 uncalibrated 用户从目视跟踪校准提示中运行目视跟踪校准，或者从 "开始" 菜单启动 "设置" 应用，然后选择 " **系统 > 校准" > 目视校准 > "运行目视校准**"。

### 证书管理器

在 Windows 预览体验计划内部版本19041.1361 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 转到 " **设置" > 更新 & 安全 > 证书**。 此功能为查看、安装和删除设备上的证书提供了一种简单且易于用户理解的方法。 通过新的证书管理器，管理员和用户现已改进了审核、诊断和验证工具，以确保设备保持安全和合规。 

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

### 来自 USB 的自动启动预配
在此内部版本之前，用户必须在 OOBE 期间手动启动预配屏幕，以使用按钮组合。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个交互时刻插入带有预配包的 USB 驱动器
1. 准备好预配设备后，将自动通过预配页面打开提示。 

> [!NOTE]
> 如果在设备启动时插入了一个 USB 驱动器，则 OOBE 将枚举现有的 USB 存储设备，还会监视插入的其他设备。

有关在 OOBE 期间应用预配程序包的详细信息，请继续阅读 [此处](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### 在 OOBE 中自动确认预配程序包
当预配主屏幕出现时，OOBE 将在10秒后自动开始应用所有预配程序包。 用户在验证所需的程序包后，仍可在此10秒内确认或取消。

### 自动预配，不使用 UI
通过将预配的自动启动与 USB 设备中的自动启动和预配程序包的自动确认结合使用，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至戴设备。 你可以继续对多台设备使用相同的 USB 驱动器和预配程序包。 这对于在同一区域同时部署多个设备很有用。 

1. 使用[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)[创建预配包](hololens-provisioning.md)。 
1. 将程序包复制到 USB 存储驱动器。
1. 将[HoloLens 2 闪存](hololens-insider.md#ffu-download-and-flash-directions)到[19041.1361 或更高版本](https://aka.ms/hololens2previewdownload)。 
1. 当 " [高级恢复" 助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成闪烁时，您的设备将拔出 USB-C 电缆。 
1. 将您的 USB 驱动器插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它将自动检测 USB 驱动器上的预配包并启动预配页面。
1. 10秒后，设备将自动应用预配包。 

你的设备现已配置，并将显示预配成功屏幕。

### 将 Autopilot 与 Wi-Fi 连接结合使用
现在，在 OOBE 期间，一旦通过 Wifi 连接了 HoloLens 2，OOBE 将检查设备的 autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再需要使用以太网到 USB C 或 wifi 到 USB C 适配器，但如果在 OOBE 的开始，它们仍可继续正常工作。 了解有关 [HoloLens 2 设备的 Autopilot 的](hololens2-autopilot.md)详细信息。

### Tenantlockdown CSP 和 Autopilot
HoloLens 2 设备现在支持 TenantLockdown CSP，如 Windows 预览体验成员内部版本 19041.1366 +。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 HoloLens 2 能够仅使用 Autopilot 与 MDM 注册绑定。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false (最初在 HoloLens 2 上设置) 值时，即使重新闪烁、操作系统更新等，该值仍将保留在设备上。 

TenantLockdown 在 HoloLens 2 上将 Csp "RequireNetworkInOOBE" 节点设置为 true 时，OOBE 将无限期地等待 Autopilot 配置文件在网络连接后成功下载和应用。 

TenantLockdown 在 HoloLens 2 上将 Csp "RequireNetworkInOOBE" 节点设置为 true 时，OOBE 中不允许以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 AAD 联接操作 
- 在 OOBE 体验中选择拥有设备的人员 

#### 如何使用 Intune 设置此功能？ 
1. 创建自定义 OMA URI 设备配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA URI 值应为/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使在上一步中创建的组的 HoloLens 2 设备成员，并触发同步。  

在 Intune 门户中验证设备配置已成功应用。 一旦此设备配置成功应用于 Hololens 2 设备，TenantLockdown 的效果将处于活动状态。

#### 如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从上面创建的设备配置先前已分配的设备组中删除 HoloLens 2。 

1. 创建基于自定义 OMA URI 的设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA URI 值应为/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使在上一步中创建的组的 HoloLens 2 设备成员，并触发同步。

在 Intune 门户中验证设备配置已成功应用。 一旦此设备配置成功应用于 Hololens 2 设备，TenantLockdown 的效果将处于非活动状态。 

#### 如果 Autopilot 配置文件在 TenantLockdown 设置为 true 后未在 HoloLens 中取消分配，则在 OOBE 期间将会发生什么情况？ 
OOBE 将无限期地等待下载 Autopilot 配置文件，并将显示以下对话框。 为了删除 TenantLockdown 的效果，必须首先使用 Autopilot 向设备注册其原始租户，并且必须取消设置，如前面步骤中所述，RequireNetworkInOOBE TenantLockdown CSP 引入的限制。 

![设备中在设备上实施策略时的视图。](images/hololens-autopilot-lockdown.png)

### 全局分配的访问-展台模式
此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识都没有相关性，并且适用于登录设备的每个人。 请在此仔细阅读此新增[功能。](hololens-global-assigned-access-kiosk.md)

### 在多应用展台模式下自动启动应用程序 
仅适用于多应用展台模式，并且只能将1个应用指定为使用 "分配的访问配置" 下方的突出显示属性自动启动。 

应用程序将在用户登录时自动启动。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 故障处理的展台模式行为更改

早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 从 Windows 预览体验成员内部版本开始，如果出现故障，"开始" 菜单中将不显示任何应用，如下所示： 

!["展台" 模式的图像在失败时立即显示。](images/hololens-kiosk-failure-behavior.png )

#### 更新
也可以为此方法配置更新，因此即使用户未通过 Microsoft Store 安装，他们仍然可以接收更新。 可将更新配置为基于应用启动或计划。 若要阅读有关如何进行设置的详细信息， [请访问此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings)。 

### HoloLens 政策
在版本 19041.1349 + 上为 HoloLens 2 设备创建了新的混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、可收集诊断的设置以及 AAD 组成员身份缓存。  

| 新的 HoloLens 政策                                | 描述                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，因此按住它不会更改亮度。       | 1是，0否 (默认值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，因此按下不会更改音量。               | 1是，0否 (默认值)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此在 HoloLens 2 上不能录音。                      | 1是，0否 (默认值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集诊断日志的行为。                               | 0已禁用，1为设备所有者启用1，为所有 (默认值启用 2)  |
| MixedReality\HeadTrackingMode                      | 保留以供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制 AAD 组成员身份缓存用于面向 AAD 组的展台的天数。 | 请参阅下文。                                                           |

### 缓存脱机展台的 AAD 组成员身份

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
> 在针对 AAD 用户执行步骤4之前，将在 "断开连接的" 环境中遇到以下所述的失败行为。 

### 适用于 HoloLens 2 的新设备限制策略
允许 HoloLens 2 设备的更多管理选项的新启用的策略。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp) *

>[!NOTE]
> 对 [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)而言，HoloLens 将仅支持/Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理引脚（如 reset 和 recover）的配置。

### Hololens 2 的新 power 策略
这些新添加的策略允许管理员控制电源状态，如空闲超时。 若要阅读有关每个单独策略的详细信息，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 配置设计器中使用的示例值，即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 配置设计器中使用的示例值，即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

> [!NOTE]
> 为获得 HoloLens 2 上的一致体验，请确保 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值均设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式待机的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### 适用于 HoloLens 的新启用的更新策略
现已在 HoloLens 2 设备上启用这些更新策略：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### 已启用 HoloLens 2 的设置页面可见性
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


### 更新中的改进和修复：
- 已更新策略以禁用通过 MDM for AllowUsbConnection 对 USB 函数进行枚举的 NCM。
- OOBE 中的更多屏幕现在处于深色模式。
- 了解更多内容应联机了解最新的隐私声明。
- 解决了用户无法通过预配程序包预配 VPN 配置文件的问题。
- 解决了在将设备设置为 [单应用展台](hololens-kiosk.md)时，导致 HoloLens 设备无法在文件资源管理器中显示在媒体传输协议 (MTP) 的问题。 请注意，常规) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略禁用。

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
