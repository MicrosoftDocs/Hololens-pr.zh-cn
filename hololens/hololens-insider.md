---
title: Microsoft HoloLens 内部预览版
description: 开始使用预览体验成员版本并为 HoloLens 的下一个主要操作系统更新提供有用的反馈。
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
ms.openlocfilehash: 1e6b8fcfad1dab49823f38c722de33654b361f58
ms.sourcegitcommit: 16d61083a1da8007278aed7e11eb6d44f7a90952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941699"
---
# Microsoft HoloLens 内部预览版

欢迎来到 HoloLens 的最新 Insider Preview 版本！ 开始使用 HoloLens[get started](hololens-insider.md#start-receiving-insider-builds)的下一个主要操作系统更新并提供有用反馈。

## Windows 预览体验成员发行说明

以下是你立即在 Windows 预览体验成员版本中试用的功能列表。

| 功能                                                | 描述                                                                                    | 预览体验成员版本中提供 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [自动等于位置支持](hololens-insider.md#auto-eye-position-support)                              | 积通发现位置并启用准确的全息影位位置。                        | 19041.1339+                 |
| [证书查看器](hololens-insider.md#certificate-viewer)                                     | 在"设置"应用中查看用户和设备证书。                                         | 19041.1346+                 |
| [安装和删除证书](hololens-insider.md#install-and-remove-certificates)                        | 用户可以使用证书查看器安装和删除证书。                        | 19041.1361+                 |
| [从 USB 自动启动设置](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE 会自动检测 U 盘上设置包。                                | 19041.1361+                 |
| [在 OOBE 中自动确认包装](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | 自动应用 OOBE 中的程序包。                                             | 19041.1361+                 |
| [将"自动试试"与 Wi-Fi 连接结合使用](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | 使用设备 Wi-Fi 中的自动图书，无需进行以太网适配器。                             | 19041.1364+                 |
|[租户关闭 CSP 和自动化](hololens-insider.md#tenantlockdown-csp-and-autopilot) | 在租户注册且应用策略后，只有在重置或重新安装设备时，只能在该租户中注册设备。 | 19041.1366+|
| [全局分配的访问权限](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | 针对多个应用种类模式配置 HoloLens 2 设备，该设备适合在系统级别。 | 19041.1356+                 |
| [在多应用启动启动中自动启动应用](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 将应用程序设置为在登录多应用启动模式时自动启动。     | 19041.1346+                 |
| [Kiosks 的访问者自动登录](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | 启用访问者帐户上的自动登录，用于 Kiosk 模式。                         | 19041.1361+                 |
| [用于处理故障的 Kiosk 模式行为更改](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 处理了展行模式故障的变化。                                              | 19041.1356+                 |
| [HoloLens 策略](hololens-insider.md#hololens-policies)                                      | 新的混合现实设备策略。                                                        | 19041.1349+                 |
| [离线 Lineiosk 缓存 AAD 组成员身份](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | 允许在展会模式中使用 AAD 组成员身份缓存的策略。    | 19041.1356+                 |
| [HoloLens 2 的新设备限制策略](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | 为 HoloLens 2 启用新启用的设备管理策略。                               | 19041.1349+                 |
| [HoloLens 2 的新电源策略](hololens-insider.md#new-power-policies-for-hololens-2)                      | 新支持的超时设置策略。                                           | 19041.1349+                 |
| [更新策略](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 新启用的策略允许控制更新。                                            | 19041.1352+                 |
| [HoloLens 2 启用的"设置"页面可见性](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 用于选取"设置"应用中所显示页面的策略。                                           | 19041.1349+                 |
| [更新中的改进和修复](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 更新中的其他修补程序。                                                                | 19041.1361+                 |

### 自动等于位置支持

在 HoloLens 2 中，人节位置支持准确的全息影通位、适合查看体验和改进的显示质量。 目的在于作为人类跟踪结果的一部分计算。 但是，每位用户都需要进行跟踪转书，即使体验不需要注视用户的注意也可以。

**使用空快速 (AEP) 方案， ** 通过无动方式为用户计算访问位置的交互方法实现。  自动等于用户将设备放在后台自动开始工作。 如果用户之前没有显示跟踪剪辑，则"自动清空"位置会在进行较小的处理时间后开始向显示系统提供用户的视觉位置。 此处理时间通常在 20 到 60 秒之间。 用户数据不会保留在设备上，因此在用户关闭设备后重新打开或从处于状态状态恢复设备时，会重复此过程。  

当用户将内容放在设备上时，使用自动 Eye Position 功能会发生一些系统行为更改。 不适合的用户指的是之前未通过设备上的 Eye 跟踪转移流程的人。

|     活动应用程序                           |     当前行为                                   |     Windows 预览体验计划版本 19041.1339 端到+                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     不支持 Gaze 的应用或全息 Shell    |     显示了人跟踪修订提示。    |     不显示任何提示。                                                                                |
|     Gaze 支持的应用                             |     显示了人跟踪修订提示。    |     仅当应用程序访问 Eye Gaze 流时才会显示人跟踪剪辑提示。     |

 如果用户从启用了不需要的应用程序切换到访问监视数据的应用程序，将显示剪辑提示。 不会更改为"提供外框体验"流程。 
 
对于需要一定优动的体验（或非常精确的全息影集位置） 我们建议不缩略的用户从简略的跟踪转录提示符或通过从"开始"菜单中启动"设置"应用，然后选择**系统 > Calibration > >运行 Eye Calibration >运行 Eye calibration 运行 Eye calibration。**

**已知问题**
 - 我们正在调查一个问题，即 eye Tracker 驱动程序主机进程在重负载下运行时崩溃。 应该自动恢复显示驱动程序主机进程。

### 证书查看器

在 Windows 预览体验计划版本 19041.1346 中，我们在 HoloLens 2"设置"应用中添加证书查看器。 证书安装当前支持 .cer 和 .crt 文件。 设备所有者可在本地机器和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从"设置"UI 安装的证书。 如果已通过其他方式安装证书，则还必须由相同机制删除证书。

-   **Acuditing：** 验证是否已正确部署证书或确认是否已被正确删除的功能。 
-   **诊断：** 问题出现时，验证设备上是否存在适当的证书节省时间并帮助进行故障排除。 
-   **验证：** 验证证书可提供预期用途以及功能是否能节省大量时间，尤其是在部署较大规模证书之前在商业环境中。

若要查看证书，请转到 **">安全&证 >安全"。**

![设置应用中的证书查看器](images/certificate-viewer-device.jpg)

### 安装和删除证书
从 Windows 预览体验成员版本开始，19041.1361+ 后，可通过"设置"应用直接在 HoloLens 2 上安装和删除证书。 证书安装当前支持 .cer 和 .crt 文件。 设备所有者可在本地机器和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从"设置"UI 安装的证书。 如果已通过其他方式安装证书，则还必须由相同机制删除证书。

#### 若要使用证书查看器安装证书： 
1. 导航**到**  ->  **设置应用**  ->  **更新和安全证书，** 然后选择 **"安装证书**"。 
1. 从文件选取器体验中选择 .cer 文件。
1. 选择本地 (计算机或你具有证书的位置) 
1. 选择 **根** 证书存储 (或要将证书放置到的商店)  
1. 单击**安装**。

证书现应安装在该设备上。

#### 若要使用证书查看器删除证书，请执行以下操作： 
1. 导航**到**  ->  **设置应用**  ->  **更新和安全证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击" **删除"**
1. 出现提示时，选择"是"，以及确认提示时。

![演示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

#### 已知问题 
我们正在调查安装流中出现的问题，从文件选取器中选择证书后，安装对话框 UI 不会显示所选的证书文件，但它已被选中。 一进入文件后，即使对话框中未显示该文件，也可继续安装。 

### 从 USB 自动启动设置
在此构建用户必须在 OOBE 期间手动启动设置屏幕，才能使用按钮组合进行设置。 现在用户可使用 U 盘上的配置包来跳过按钮组合。 

1. 在 OOBE 的第一个可互动期间使用设置包插入 U 盘
1. 设备准备好设置时，它将自动打开带有预定页面的提示。 

注意：如果在设备正在展示期限内将左交了 U 盘，则 OOBE 将枚举现有 USB 存储设备，并观看其他插入的设备。

有关在 OOBE 期间应用设置包的详细信息，请继续在此处 [阅读](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### 在 OOBE 中自动确认包装
当设置主屏幕上有时，OOBE 将在自动开始应用所有设置包之前，OOBE 将降到最多 10 秒。 在验证包的确认，否则在此 10 秒内仍可以在验证或取消。

### 在不使用 UI 的情况下自动设置
通过将来自 USB 设备的自动启动功能与设置程序包的自动确认结合起来，用户可以自动预配置 HoloLens 2 设备，而无需使用设备的 UI 甚至使设备设备受到影响。 你可以继续使用同一个 U 盘，并为多台设备设置程序包。 这对于在同一区域部署多个设备同一次时必须这样做。 

1. [使用 Windows 配置设计器创建](hololens-provisioning.md) 配置 [包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. 将程序包复制到 U 盘。
1. [将 HoloLens 2 转换到](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 或更高版本。](https://aka.ms/hololens2previewdownload) 
1. [在"高级恢复助手"完成](https://www.microsoft.com/store/productId/9P74Z35SFRS8)刷新设备后，将你的设备清除电缆。 
1. 为设备插入 U 盘。
1. HoloLens 2 设备启动到 OOBE 时，将自动检测 U 盘上的预配置包并启动"设置"页面。
1. 10 秒后，设备将自动应用预安装程序包。 

你的设备现已配置，并显示"设置成功"屏幕。

### 将"自动试试"与 Wi-Fi 连接结合使用
现在在 OOBE 期间，在通过 Wifi 连接 HoloLens 2 后，OOBE 将检查设备的自动试用配置文件。 如果找到一个单元格，则用于完成 AAD 加入和注册流程的其一部分。 换言之，并非对 USB C 或 Wifi 使用以太网不再需要，但是，如果在 OOBE 开始时提供，这些功能仍可继续进行。 了解有关 [HoloLens 2 设备的 Autopilot 的详细信息](hololens2-autopilot.md)。

### 租户关闭 CSP 和自动化
HoloLens 2 设备现在支持从 Windows 预览体验计划版本 19041.1366+ 等 Windows 预览体验计划时支持 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 HoloLens 2 仅使用自动试行帐户与 MDM 注册关联。 一经 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 (在 HoloLens 2 上最初设置) 值，该值将保留在设备（但操作系统更新等）上仍然保留。 

一经 TenantLockdown CSPs' RequireNetworkInOOBE 节点在 HoloLens 2 上设置为 true，OOBE 将无意在网络连接后成功下载和应用自动试试配置文件。 

一经 TenantLockdown CSPs' RequireNetworkInOOBE 节点设置为 True，在 HoloLens 2 上禁止执行以下操作： 
- 使用运行时预配置创建本地用户 
- 通过运行时设置执行 AAD 联接操作 
- 选择在 OOBE 体验中拥有设备的人员 

#### 如何使用 Intune 设置此内容？ 
1. 创建自定义 OMA URI 设备配置文件并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOBE Setting 租户锁定应通过 ![ OMA-URI](images/hololens-tenant-lockdown.png)
1. 创建一个组并将设备配置文件分配到该设备组。 
1. 使上一步中创建的组的 HoloLens 2 设备成员成为或触发同步。  

验证已成功应用设备配置的 Intune 门户。 成功将此设备配置应用于 Hololens 2 设备上后，TenantLockdown 的效果将处于活动状态。

#### 如何在 HoloLens 2 上使用 Intune 取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从之前向其分配的设备配置中删除 HoloLens 2。 
1. 创建基于其自定义 OMA URI 的设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE ![ 屏幕截图，该屏幕地址针对 Intune 中的 OMA URI 设置 RequireNetworkInOOBE 设置为 false](images/hololens-tenant-lockdown-false.png)
1. 创建一个组并将设备配置文件分配到该设备组。 
1. 使上一步中创建的组的 HoloLens 2 设备成员成为或触发同步。

验证已成功应用设备配置的 Intune 门户。 成功地将此设备配置应用于 Hololens 2 设备上后，TenantLockdown 的效果将处于非活动状态。 

#### 如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，会发生什么情况？ 
OOBE 将不定期等待 Autopilot 配置文件下载和遵循对话框。 为了删除 TenantLockdown 的效果，必须首先仅使用 Autopilot 和 RequireNetworkInOOBE 的原始租户来注册设备，且删除了 TenantLockdown CSP 所在的限制前面的步骤必须首先取消设置 DeviceInOOBE。 

![设备中强制执行策略的情况时，针对设备内视图。](images/hololens-autopilot-lockdown.png)

### 全局分配的访问 - Kiosk 模式
此新功能使 IT 管理员可以为多个应用启动模式配置 HoloLens 2 设备，该设备适合于系统级别，不影响系统级别上的任何标识并且适用于登录设备的所有人。 在此处详细了解此新 [功能](hololens-global-assigned-access-kiosk.md)。

### 在多应用启动模式下自动启动应用程序 
仅适用于多应用展台模式，而只能使用"分配的访问"配置中下方的突出显示属性将只有 1 个应用指定为自动启动。 

用户登录时将自动启动应用程序。 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Kiosks 的访问者自动登录
这项新功能使访问者帐户的自动登录功能用于 Kiosk 模式。 

对于非 AAD 配置，要针对访问者的自动登录配置设备：
1.  创建用于以下项的预编程序包：
    1.  将 **运行时设置/AssignedAccess** 配置为允许访问者帐户。
    1.  （可选）在运行时设置 ** /Workplace/注册 () ** 以便稍后管理。
    1.  不创建本地帐户
1.  [应用设置包](hololens-provisioning.md)。

对于 AAD 配置，用户现在可以获取如今此类似于此项的版本。无需此更改。 为启动模式配置的 AAD 加入的设备可以使用从登录屏幕中点击一个按钮，登录访问者帐户。 登录访问者帐户后，设备不会再次提示登录，直到从开始菜单中明确注销该设备或重新启动该设备。

### 用于处理故障的 Kiosk 模式行为更改

在应用启动模式时遇到故障的早期版本，HoloLens 用于显示开始菜单中的所有应用程序。 从此 Windows 预览体验成员版本中开始，对于失败，开始菜单中不会显示任何应用，如下所示： 

![显示在出现故障时现在模式下的外观的图像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens 策略
已在内部版本 19041.1349+ 上为 HoloLens 2 设备上创建了新的混合现实策略。 新的可控制设置包括：设置亮度、设置音量、在混合现实捕获中禁用音频录制、设置可收集诊断的时间以及 AAD 组成员身份缓存的设置。  

| 新建 HoloLens 策略                                | 描述                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，因此，按住它不会更改亮度。       | 1 是，0 默认 (默认)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便在按住它不更改音量的同时按它。               | 1 是，0 默认 (默认)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，以便 HoloLens 2 上不支持录音。                      | 1 是，0 默认 (默认)                                                 |
| MixedReality\FallbackDiagnostics                   | 可收集诊断日志的控件行为。                               | 为设备所有者启用 0 个已启用 1，2 对所有器启用 (默认)  |
| MixedReality\HeadTrackingMode                      | 保留以供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制用于面向 AAD 组的 AAD 组成员身份缓存的天数。 | 请参阅下文。                                                           |

### 离线 Lineiosk 缓存 AAD 组成员身份

此策略控制天数、AAD 组成员身份缓存用于针对登录用户的 AAD 组的"已分配访问"配置。 在此策略值设置为仅大于 0 的值之后，则将使用缓存，否则不使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 天  
最多 - 60 天 

正确使用此策略的步骤： 
1. 为面向 AAD 组的 kiosk 创建设备配置文件，并将其分配给 HoloLens 设备 (s) 。 
1. 创建基于 OMA URI 的自定义 OMA URI，并将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 (s) 。 
    1. 应在 OMA-URI 文本框中输入 URI 值为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/ 最大值之间。
1. 注册 HoloLens 设备并验证两个配置都已应用到设备。 
1. 让 AAD 用户 1 在可使用 Internet 后，系统将创建一次用户登录，并且 AAD 组成员身份成功确认后，将创建缓存。 
1. 现在 AAD 用户 1 可以使 HoloLens 脱机，并将其用于展行模式，只要策略值允许 X 天数。 
1. 对于任何其他 AAD 用户 N，可以重复执行步骤 4 和步骤 5。此处的任何 AAD 用户都必须使用 Internet 登录到设备，以便我们可以确定他们是针对哪种 Kiosk 配置的 AAD 组的成员。 
 
> [!NOTE]
> 在为 AAD 用户执行步骤 4 之前，将体验"断开连接"环境中提到的行为不可及的行为。 

### HoloLens 2 的新设备限制策略
新启用的策略允许对 HoloLens 2 设备进行更多的管理选项。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

### Hololens 2 的新电源策略
这些新添加的策略允许管理员控制电源状态，例如空习超时。 若要阅读有关每个单独政策的详细信息，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows Configuration Designer（如，e.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows Configuration Designer（如，e.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows Configuration Designer（如 100）中使用的示例值                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows Configuration Designer（如 100）中使用的示例值                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows Configuration Designer（如，e.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows Configuration Designer（如，e.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### 为 HoloLens 启用新更新策略
现在在 HoloLens 2 设备上启用了这些更新策略：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [更新/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### HoloLens 2 启用的"设置"页面可见性
现在，我们启用了一个策略，允许 IT 管理员阻止系统设置应用中的特定页面显示或可供访问，或者为除指定这些指定页面除外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![正在"设置"应用中修改的活动时段的屏幕截图](images/hololens-page-visibility-list.jpg)

### 更新中的改进和修补程序：
- 更新了策略，以禁用通过 NCM for NCM 的 UCM 进行枚举。
- OOBE 中的更多屏幕现在处于深色模式。
- 了解更多内容应指向在线的最新隐私声明。
- 解决了用户无法通过设置包预配置 VPN 配置文件的问题。

## 开始会员版本

> [!NOTE]
> 如果你最近未更新，请重新启动设备以更新状态并获取最新版本。
> - "重试设备"语音命令的工作方式非常好。 
> - 也可以在"设置/Windows 预览体验成员计划"中选择重启按钮。
>
> 我们在你可能遇到的后端有 bug，这会让你回到轨事。

在 HoloLens 2 设备上，转到 **"安全**Windows  >  **预览&程序**"中的  >  **Windows Insider Program**"设置"更新，**然后选择"开始**"。 链接你用于注册为 Windows 预览体验成员的帐户。

Windows 预览体验成员现已移动到频道。 "**快"** 环将成为**Dev 渠道****，"慢"** 环将变为**beta 渠道**，**发布预览**版环将成为**Release Preview 频道**。 映射如下所示：

![Windows Insider Channel 说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 [Windows 上的"Windows 预览体验成员频道](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) "简要介绍。

然后，选择 **Windows 的主动开发**，选择是否想要接收 **Dev 渠** 道或 **Beta 渠道内** 部版本，并查看计划条款。

选择 **"确认>立即重新** 启动"以完成。 重新启动设备后，请转到" **设置>"和"&安全>检查更新** 以获取最新版本。

## FFU 下载和快速路线
要使用外部测试版签出的 Ffu 进行测试，你必须先外部测试计算机，然后才能完成外部测试测试（签档后的 Ffu）。
1. 在电脑上：

    1. 从以下位置下载你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 的 fff。
    
    1. 从 Microsoft Store (") 安装 ARC 链接 (恢复助手： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens 上 - 外部测试版解锁：打开**和**  >  &安全 Windows 预览**体验**  >  **计划程序的**打开设置更新，然后重新启动设备。

1. Flash FFU - 现可使用 ARC 来找出已签名的 FFU。

## 提供反馈和报告问题

请使用[the Feedback Hub app](hololens-feedback.md) HoloLens 上的"反馈中心"应用提供反馈和报告问题。 使用反馈中心可确保包含所有必要的诊断信息，帮助工程师快速调试并解决问题。  应使用相同的方式报告中国和日语版存在中语和日语版的问题。

> [!NOTE]
> 请务必接受询问你是否希望反馈中心访问"文档"文件夹的提示 ** (在出现** 提示时选择) 。

## 面向开发人员的注意事项目

欢迎你，鼓励你使用 HoloLens 的预览体验计划内部版本开发你的应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。 这些相同的说明适用于 HoloLens 的预览体验计划内部版本。  你可以使用与 HoloLens 开发Visual Studio统一内部版本相同的 Unity 和版本。

## 停止接受会员版本

如果不想再接收 Windows Holographic 的预览体验计划版本，则可选择在 HoloLens 运行时内部版本时出现;还 [可使用](hololens-recovery.md) 高级恢复助手将设备恢复到非预览体验成员版本的 Windows Holographic。

> [!CAUTION]
> 存在一个已知问题，即在手动重新安装全新预览版之后从 Insider Preview 版本取消注册，将出现蓝屏。 之后，他们必须手动恢复其设备。 有关你是否会受到影响的完整详细信息，请查看此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

要验证 HoloLens 正在运行生动版本，请执行以下操作：

1. 转到" **设置>系统>相关**"并查找内部版本号。

1. [请参阅生作版本号的发行说明](hololens-release-notes.md)。

选择选择不使用预览体验成员版本：

1. 在运行生动版的 HoloLens 上，转到 **"设置"> 和"安全 &> Windows 预览体验计划和>更新安全功能**，然后选择 **"停止预览体验计划**"。

1. 按照说明操作，可选择出设备。
