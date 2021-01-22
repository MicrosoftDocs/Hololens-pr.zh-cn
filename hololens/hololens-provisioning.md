---
title: '使用 HoloLens (预配包配置 HoloLens) '
description: Windows 预配可使 IT 管理员轻松配置最终用户设备，而无需映像处理。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284153"
---
# 使用预配包配置 HoloLens

[Windows 预配](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 使 IT 管理员无需映像即可轻松配置最终用户设备。 Windows 配置设计器是一个工具，用于配置随后内置到预配包中的映像和运行时设置。

可以在预配包中应用某些 HoloLens 配置包括：

- 升级到 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- 设置本地帐户
- 设置 WLAN 连接
- 将证书应用到设备
- 启用开发人员模式
- 按照详细说明配置展台 [模式](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

## 预配包 HoloLens 向导

HoloLens 向导可帮助你在预配包中配置以下设置：

- 升级到企业版

    > [!NOTE]
    > 这应仅用于 HoloLens 第一代设备。 仅在预配包包含 Windows Holographic for Business 版本升级许可证或设备已升级到 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)时，才应用预配包中的设置。

- 在 OOBE (配置 HoloLens) 
- 配置Wi-Fi网络
- 在 Azure Active Directory 中注册设备，或创建本地帐户
- 添加证书
- 启用开发人员模式
- 按照详细说明配置展台模式[) 。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> 你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。

预配包可以包括管理说明和策略、自定义网络连接和策略等。

> [!TIP]
> 使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。

## 创建预配包的步骤

1. **选项 1：**[从 Microsoft Store。](https://www.microsoft.com/store/apps/9nblggh4tx22) 这包括 HoloLens 2 功能。
2. **选项 2：**[从适用于 Windows 10 (ADK) Windows 评估和部署工具包](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果从 Windows ADK 安装 Windows 配置设计器，请 **从"选择要** 安装的功能"对话框中 **选择配置** 设计器。 此选项不包括 HoloLens 2 功能。

> [!NOTE]
> 如果你知道你将使用需要访问 Windows 配置设计器的脱机电脑，请按照[离线应用安装说明 (https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 高级恢复助手说明进行操作。 选择 Windows 配置设计器。 

### 2. 创建预配包

使用 Windows 配置设计器工具创建预配包。

1. 打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。

2. 选择 **"预配 HoloLens 设备"。**

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. 命名项目，然后选择"**完成"。**

4. 阅读"入门"**页上的说明**，然后选择"下一**步"。** 桌面预配页面将演练以下步骤。
  
> [!IMPORTANT]
> 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。

### 配置设置

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>浏览到并选择企业许可证文件以升级 HoloLens 版本。</br></br>还可以切换" <strong> 是 </strong> "或 <strong> </strong> "否"来隐藏第一个体验的某些部分。</br></br>若要设置设备，而无需连接到Wi-Fi网络，请将"跳过"Wi-Fi <strong> 设置为 </strong> <strong> "打开 </strong> "。</br></br>选择将在其中使用设备的时间和时区。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在此部分中，你可以输入设备Wi-Fi应连接到的无线网络的详细信息。 为此，请选择"开"，输入 <strong> </strong> SSID、网络类型 (Open <strong> </strong> 或 <strong> WPA2-Personal </strong>) ，如果 <strong> WPA2 个人 </strong>) 无线网络的密码，则选择 (。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>可以在 Azure Active Directory 中注册设备，或在设备上创建本地帐户</br></br>使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。 Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 选择 <strong> "获取批量令牌 </strong> "。 在"&#39;登录"窗口中，输入有权将设备加入 Azure AD 的帐户，然后 <strong> </strong> 输入密码。 选择 <strong> " </strong> 接受"以向 Windows 配置设计器授予必要的权限。 </br></br>若要创建本地帐户，请选择此选项并输入用户名和密码。 </br></br><strong>重要提示：</strong> <br /> (对于 Windows 10 版本 1607 仅) 如果在预配包中创建本地帐户，则必须每 <strong> 42 天使用"设置"应用更改密码。 </strong> 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用证书预配设备，请单击<strong>添加证书</strong>。 输入证书的名称，然后浏览到要使用的证书并将其选中。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>切换 <strong> " </strong> 是"或 <strong> </strong> "否"以在 HoloLens 上启用开发人员模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">了解有关开发人员模式的详细信息。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>不要设置密码来保护你的预配包。 如果预配包受密码保护，预配 HoloLens 设备将失败。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成后，选择"创建 **"。** 这只需几秒钟的时间。 生成该包之后，其存储位置将在页面底部显示为超链接。

### 3. 使用高级预配为 HoloLens 创建预配包

> [!NOTE]
> 在高级预配中创建的预配包无需**** 包含 Windows Holographic for Business 的版本升级许可证，即成功应用于 HoloLens (第一代) 。 [查看有关适用于 HoloLens 的 Windows Holographic for Business (第一代) 。 ](hololens1-upgrade-enterprise.md)

1. 在 Windows 配置设计器起始页上，选择**高级预配**。
2. 在**输入项目详细信息**窗口中，指定项目的名称和项目的位置。 （可选）输入简要描述以描述你的项目。

3. 选择**下一步** 。

4. 在"**选择要查看和**配置哪些设置"窗口中，选择**Windows 10**全息版，然后选择"下一**步"。**

5. 选择 **"完成"。**

6. 使用 **本文** 稍后介绍的任何设置展开运行时设置并 [自定义程序包](#what-you-can-configure)。

    > [!IMPORTANT]
    >  (对于 Windows 10 版本 1607) 如果你在预配包中创建了本地帐户，则必须每 42 天使用"设置"应用**** 更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。 如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 选择 **"文件**  >  **保存"。**

8. 读取项目文件可能包含敏感信息的警告，然后选择"**确定"。**

    > [!IMPORTANT]
    > 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。
    
9. 选择**导出**  >  **预配包**。

10. 将 **所有者** 更改为 **IT 管理员**。这会将此预配包的优先级设置得高于其他源中应用于此设备的预配包。 选择**下一步** 。

11. 为**程序包版本**设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

12. 在"**选择预配包的安全详细信息"上**，选择"下**一步"。**

    > [!WARNING]
    > 如果加密预配程序包，则 HoloLens 设备预配将失败。  

13. 选择 **"** 下一步"以指定您希望预配包在生成后转到的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。

    （可选） **您可以选择"浏览** "来更改默认输出位置。

14. 选择**下一步** 。

15. 选择 **"生成** "开始生成程序包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。

16. 生成完成后，选择"完成 **"。**

<span id="apply" />

## 在设置期间将预配包应用到 HoloLens

Windows 全息版版本 2004 或内部版本 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更高版本上的 HoloLens 2 设备可以使用 USB 驱动器应用预配包。 只需将 .ppkg 文件复制到 USB 驱动器的根目录。 预配包仅在 U 盘的根目录下时应用。 将按顺序应用多个预配包。

Windows 全息版 [20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更高版本上的 HoloLens 2 设备具有较新的功能，可帮助简化和简化此过程，使其自动运行。 请查看以下部分：

- [从 USB 自动启动预配](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [在 OOBE 中自动确认预配包](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [无需使用 UI 即可自动预配](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. 使用 USB 电缆将设备连接到适用于 HoloLens 2 (电脑或 U 盘，) 启动设备。 不要继续通过 OOBE **的第一个** 可交互时刻页面。   
    - 在 HoloLens (第一代) ，此页面包含一个蓝色框。 
    - 在 HoloLens 2 上，此页面包含 hummingbird。

2. 短暂地同时按下**调低音量**和**电源**按钮，然后释放。 

3. HoloLens 在电脑上的文件资源管理器中作为设备显示。

4. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

5. 在 OOBE 的第一个**** 可交互时刻页面上，再次短暂地同时**** 按下并释放音量降低和电源按钮。 ****

6. 设备会询问你是否信任程序包，并想应用它。 确认你信任程序包。

7. 你将看到是否成功应用了程序包。 如果失败，你可以修复程序包，然后重试。 如果成功，请继续 OOBE。

> [!NOTE]
> 如果设备是在 2016 年 8 月之前购买的，则需要使用 Microsoft 帐户登录到设备，获取最新的操作系统更新，然后重置操作系统以应用预配包。

### 从 USB 自动启动预配

- 当在 OOBE 期间使用带预配包的 USB 驱动器时，自动化进程允许更少的用户交互。

在此版本之前，用户在 OOBE 期间必须手动启动预配屏幕才能使用按钮组合进行预配。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个可交互时刻使用预配包插入 USB 驱动器
1. 设备准备好预配后，将自动打开包含预配页面的提示。 

注意：如果在设备启动时 USB 驱动器被留有插入，则 OOBE 将枚举现有的 USB 存储设备，并观察插入的其他设备。

阅读有关 [在 OOBE 期间应用预配包的信息](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### OOBE 中的自动确认预配包
- 自动进程，允许更少的用户交互，当显示预配包页面时，它将自动应用列出的所有程序包。

当设置主屏幕出现时，OOBE 将倒计时 10 秒，然后自动开始应用所有预配包。 在验证预期的程序包后，用户仍可在此 10 秒内确认或取消。

### 无需使用 UI 即可自动预配
- 用于减少预配的设备交互的组合自动过程。 

通过将 USB 设备的预配自动启动与预配包的自动确认相结合，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至不会佩戴该设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这可用于在同一区域中同时部署多个设备。 

1. [使用 Windows 配置设计器](hololens-provisioning.md) 创建 [预配包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. 将程序包复制到 USB 存储驱动器。
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build.](https://aka.ms/hololens2previewdownload) 
1. 当 [高级恢复助手](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成闪烁设备时，请拔下 USB-C 电缆。 
1. 将 U 盘插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它将自动检测 USB 驱动器上的预配包并启动预配页面。
1. 10 秒后，设备将自动应用预配包。 

你的设备现已配置，并显示"预配成功"屏幕。

## 设置后将预配包应用到 HoloLens

> [!NOTE]
> 这些步骤仅适用于 Windows 10 版本 1809。

在电脑上，按照以下步骤操作：
1. 创建预配包，如使用 [HoloLens 向导为 HoloLens 创建预配包中所述](hololens-provisioning.md)。
2. 使用 USB 电缆将 HoloLens 设备连接到电脑。 HoloLens 在电脑上的文件资源管理器中作为设备显示。
3. 将预配包拖放到 HoloLens 上的 Documents 文件夹。

在 HoloLens 上，按照以下步骤操作：
1. 转到"**设置**  >  **帐户**  >  **"访问工作或学校**。 
2. 在 **"相关设置**"中 **，选择"添加或删除预配包"。**
3. 下一页上，选择 **"添加程序包** "以启动文件选取器并选择你的预配包。 如果该文件夹为空，请确保选择 **"此设备"，** 然后选择"**文档"。**

应用程序包后，它会显示在已安装程序包 **的列表中**。 若要查看程序包详细信息或从设备中删除程序包，请选择列出的程序包。

## 可配置的内容

预配包使用配置服务提供程序 (CSP)。 如果你对 CSP 不甚了解，请参阅[针对 IT 专业人员的配置服务提供程序 (CSP) 简介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。

在 Windows 配置设计器中，当创建用于 Windows 全息版的预配包时，**可用自定义**中的设置是基于 [Windows 全息版中支持的 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。 下表介绍了你可能想要为 HoloLens 配置的设置。

![HoloLens 的通用运行时设置](images/icd-settings.png)

| 设置 | 说明 |
| --- | --- |
| **证书** | 将证书部署到 HoloLens。  |
| **ConnectivityProfiles** | 将 WLAN 配置文件部署到 HoloLens。   |
| **EditionUpgrade** | [升级为 Windows Holographic for Business。](hololens1-upgrade-enterprise.md)  |
| **策略** | 允许或阻止 HoloLens 中的开发人员模式。 [Windows Holographic for Business 支持的策略](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## 通过预配包安装应用

应用可以通过 HoloLens 2 设备的预配包进行安装。 这样，你可以轻松地使用包来帮助你分发应用。 阅读有关通过预配 [包部署应用的完整说明](app-deploy-provisioning-package.md)。  

> [!NOTE]
> HoloLens (第一代) 具有有限的支持，支持使用预配包 (**UniversalAppInstall**) 安装应用。 HoloLens (第一代) 设备仅在 OOBE 期间仅支持通过 PPKG 安装应用，并且仅支持用户上下文安装。
