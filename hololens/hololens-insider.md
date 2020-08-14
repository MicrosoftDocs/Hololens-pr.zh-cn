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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb7c60ed8a381c0ce8c7f6a28bc8274d5ea20f30
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929869"
---
# Microsoft HoloLens 内部预览版

欢迎使用适用于 HoloLens 的最新预览体验计划预览版！ 这是一种非常简单的功能 [，可提供](hololens-insider.md#start-receiving-insider-builds) 针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。

## Windows 预览体验计划发行说明

如果你要查找的功能不再在此处列出，则它现在通常可用。 请查看 [发行说明](hololens-release-notes.md) ，了解哪些版本具有你非常兴奋的功能 (s) 。 请确保 [更新 HoloLens](hololens-update-hololens.md) 以获取所有最新功能。

我们将再次通过新功能更新此页面，因为我们将其发布给 Windows 预览体验成员版本。

| 功能                                              | 描述                                                                                   | 在预览体验成员内部版本中可用 |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| 自动目视位置支持                            | 主动发现眼睛位置并支持准确的全息图定位。                       | 19041.1339 +                 |
| 证书查看器                                   | 在 "设置" 应用中查看用户和设备证书。                                        | 19041.1346 +                 |
| 安装和删除证书                      | 用户可以使用证书查看器安装和删除证书。                       | 19041.1361 +                 |
| 从 USB 自动启动预配                    | OOBE Automaticly 检测 USB 驱动器上的预配程序包。                                 | 19041.1361 +                 |
| 在 OOBE 中自动确认预配程序包           | 在 OOBE 中自动应用预配程序包。                                            | 19041.1361 +                 |
| Wi-fi 连接和使用 Autopilot                 | 从设备 Wi-fi 中使用 autopilot，而无需使用以太网适配器。                            | 19041.1364 +                 |
| HoloLens 政策                                    | 混合现实设备的新策略。                                                       | 19041.1349 +                 |
| 缓存脱机展台的 AAD 组成员身份         | 针对展台模式允许使用 AAD 组成员身份缓存的天数的策略。     | 19041.1356 +                 |
| 适用于 HoloLens 2 的新设备限制策略       | 新启用了 HoloLens 2 的设备管理策略。                              | 19041.1349 +                 |
| HoloLens 2 的新 power 策略                    | 新支持的电源超时设置策略。                                          | 19041.1349 +                 |
| 更新策略                                      | 允许控制更新的新启用的策略。                                           | 19041.1352 +                 |
| 已启用 HoloLens 2 的设置页面可见性      | 用于选择在 "设置" 应用中显示哪些页面的策略。                                          | 19041.1349 +                 |
| 全局分配的访问权限                               | 配置适用于系统级别的多个应用展台模式的 HoloLens 2 设备。  | 19041.1356 +                 |
| 在多应用展台中自动启动应用                | 将应用程序设置为在登录到多应用展台模式时自动启动。 | 19041.1346 +                 |
| 网亭的访问者自动登录                        | 允许在展台模式下使用自动登录访问者帐户。                        | 19041.1361 +                 |
| 故障处理的展台模式行为更改 | 现在已处理展台模式故障的更改。                                             | 19041.1356 +                 |
| 更新中的改进和修复                 | 更新中的其他修复程序。                                                               | 19041.1361 +                 |

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

**已知问题**
 - 我们正在调查 "目视跟踪器驱动程序" 在较高内存负载下运行时可能会崩溃的问题。 目视跟踪驱动程序主机进程应自动恢复。

### 证书查看器

在 Windows 预览体验计划内部版本19041.1346 中，我们将在 HoloLens 2 设置应用中添加证书查看器。 证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户都只能安装到当前用户。 用户只能从 "设置" UI 中删除直接安装的证书。 如果证书已通过其他方法安装，则它还必须由相同的机制删除。

-   **审核：** 验证是否已正确部署证书或确认是否已正确删除证书的功能。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间并帮助进行故障排除。 
-   **验证：** 验证证书是否服务于预期用途且正常运行，可以节省大量时间，尤其是在商业环境中，在以较大比例部署证书之前。

若要查看证书，请转到 " **设置" > 更新 & 安全 > 证书**。

!["设置" 应用中的证书查看器](images/hololens-certificate-viewer.png)

### 安装和删除证书
从 Windows 预览体验成员版本19041.1361 开始，您可以通过 "设置" 应用直接在 HoloLens 2 上安装和删除证书。 证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户都只能安装到当前用户。 用户只能从 "设置" UI 中删除直接安装的证书。 如果证书已通过其他方法安装，则它还必须由相同的机制删除。

#### 要使用证书查看器安装证书，请执行以下操作： 
1. 导航到 "**设置" 应用**  ->  **更新和安全**  ->  **证书**，然后选择 "**安装证书**"。 
1. 从文件选取器体验中选择 .cer 文件。
1. 选择 "本地计算机" (或您的证书所在的位置。 ) 
1. 选择 " **Root** " 作为证书存储 (或想要放置证书的存储。 )  
1. 单击**安装**。

证书现在应安装在设备上。

#### 要使用证书查看器删除证书，请执行以下操作： 
1. 导航到 "**设置" 应用**  ->  **更新和安全**  ->  **证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 出现提示时，选择 "是"，然后在要求确认时选择 "是"。

![显示如何使用证书 UI 安装证书的图片](images/hololens-install-certificate.jpg)

#### 已知问题 
我们正在调查安装流程期间的问题，在从文件选取器中选择证书后，安装对话框 UI 不会显示所选的证书文件（虽然已选中）。 选择文件后，您可以继续安装，即使在对话框中看不到显示的文件也是如此。 

### 来自 USB 的自动启动预配
在此内部版本之前，用户必须在 OOBE 期间手动启动预配屏幕，以使用按钮组合。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个交互时刻插入带有预配包的 USB 驱动器
1. 准备好预配设备后，将自动通过预配页面打开提示。 

注意：如果在设备启动时插入了一个 USB 驱动器，则 OOBE 将枚举现有的 USB 存储设备，还会监视插入的其他设备。

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

### Wi-fi 连接和使用 Autopilot
现在，在 OOBE 期间，一旦通过 Wifi 连接了 HoloLens 2，OOBE 将检查设备的 autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再需要使用以太网到 USB C 或 wifi 到 USB C 适配器，但如果在 OOBE 的开始，它们仍可继续正常工作。 了解有关 [HoloLens 2 设备的 Autopilot 的](hololens2-autopilot.md)详细信息。

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
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

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

### 适用于 HoloLens 的新启用的更新策略
现已在 HoloLens 2 设备上启用这些更新策略：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### 已启用 HoloLens 2 的设置页面可见性
现已启用策略，允许 IT 管理员防止系统设置应用中的特定页面可见或易于访问，或者针对除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![在 "设置" 应用中修改的活动小时的屏幕截图](images/hololens-page-visibility-list.jpg)

### 全局分配的访问-展台模式
此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识都没有相关性，并且适用于登录设备的每个人。 请在此仔细阅读此新增[功能。](hololens-global-assigned-access-kiosk.md)

### 在多应用展台模式下自动启动应用程序 
仅适用于多应用展台模式，并且只能将1个应用指定为使用 "分配的访问配置" 下方的突出显示属性自动启动。 

应用程序将在用户登录时自动启动。 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 网亭的访问者自动登录
此新功能使访问者帐户的自动登录能够用于展台模式。 

对于非 AAD 配置，要为访问者自动登录配置设备，请执行以下操作：
1.  创建一个预配包：
    1.  将 **运行时设置/AssignedAccess** 配置为允许访问者帐户。
    1.  （可选）在 MDM 中注册设备 ** (运行时设置/工作区/注册) ** 以便以后可以对其进行管理。
    1.  不创建本地帐户
1.  [应用预配包](hololens-provisioning.md)。

对于 AAD 配置，用户可以实现与今天类似的操作，而无需进行此更改。 为展台模式配置的 AAD 联接设备可以通过单击 "登录" 屏幕上的一个按钮点击来登录访问者帐户。 一旦登录到访问者帐户，设备将不会再次提示登录，直到从 "开始" 菜单明确注销访问者，否则设备将重新启动。

### 故障处理的展台模式行为更改

早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 从 Windows 预览体验成员内部版本开始，如果出现故障，"开始" 菜单中将不显示任何应用，如下所示： 

!["展台" 模式的图像在失败时立即显示。](images/hololens-kiosk-failure-behavior.png )

### 更新中的改进和修复：
- 已更新策略以禁用通过 MDM for AllowUsbConnection 对 USB 函数进行枚举的 NCM。
- OOBE 中的更多屏幕现在处于深色模式。
- 了解更多内容应联机了解最新的隐私声明。
- 解决了用户无法通过预配程序包预配 VPN 配置文件的问题。

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
