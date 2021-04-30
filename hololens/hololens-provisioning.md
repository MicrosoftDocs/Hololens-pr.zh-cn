---
title: '使用预配包配置 HoloLens (HoloLens) '
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308498"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>使用预配包配置 HoloLens

[Windows 预配](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 使 it 管理员可以轻松地配置最终用户设备，而无需进行图像处理。 Windows 配置设计器是一种用于配置映像和运行时设置的工具，这些设置随后会内置到预配包中。

可在预配包中应用的某些 HoloLens 配置包括：

- 升级到[Windows 全息企业](hololens1-upgrade-enterprise.md)版
- 设置本地帐户
- 设置 WLAN 连接
- 将证书应用到设备
- 启用“开发人员模式”
- 按照我们的 [详细说明](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)配置展台模式。

## <a name="provisioning-package-hololens-wizard"></a>设置包 HoloLens 向导

HoloLens 向导帮助你在预配包中配置以下设置：

- 升级到 enterprise edition

    > [!NOTE]
    > 这仅适用于 HoloLens 第一代设备。 仅当预配包包含适用于 Windows 全息版的 Windows 全息版或 [设备已升级到 Windows 全息版企业](hololens1-upgrade-enterprise.md)版时，才应用设置包中的设置。

- 配置 HoloLens first experience (OOBE) 
- 配置 Wi-Fi 网络
- 在 Azure Active Directory 中注册设备，或创建本地帐户
- 添加证书
- 启用“开发人员模式”
- 按照) [详细说明](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置展台模式。

> [!WARNING]
> 你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。

预配包可以包括管理说明和策略、自定义网络连接和策略等。

> [!TIP]
> 使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。

## <a name="steps-for-creating-provisioning-packages"></a>创建预配包的步骤

1. **选项1：** [从 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。 这包括 HoloLens 2 功能。
2. **选项2：** [从 Windows 评估和部署工具包 (ADK) 适用于 windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果从 Windows ADK 安装 Windows 配置设计器，请从 "**选择要安装的功能**" 对话框中选择 "**配置设计器**"。 此选项不包括 HoloLens 2 功能。

> [!NOTE]
> 如果你知道将使用需要访问 Windows 配置设计器的脱机计算机，请按照 [脱机应用安装 (https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 说明进行高级恢复。 使 Windows 配置设计器可选择。 

### <a name="2-create-the-provisioning-package"></a>2. 创建预配包

使用 Windows 配置设计器工具创建预配包。

1. 打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。

2. 选择 " **预配 HoloLens 设备**"。

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. 为项目命名，然后选择 " **完成**"。

4. 阅读 " **入门** " 页上的说明，然后选择 " **下一步**"。 桌面预配页面将引导你完成以下步骤。
  
> [!IMPORTANT]
> 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。

### <a name="configure-settings"></a>配置设置

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>浏览到并选择企业许可证文件以升级 HoloLens 版本。</br></br>还可以切换 <strong>"是" 或 "</strong> <strong>否</strong> "，隐藏第一次体验的各个部分。</br></br>若要设置设备而无需连接到 Wi-Fi 网络，请将 " <strong>跳过 Wi-Fi 安装程序</strong> " 设置为 <strong>"开</strong>"。</br></br>选择要在其中使用设备的区域和时区。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在此部分中，可以输入设备应自动连接到 Wi-Fi 无线网络的详细信息。 为此， <strong>请选择 "打开"</strong>，输入 SSID、"网络类型" (<strong>打开</strong> "或" <strong>wpa2-个人</strong> ") ，并 (" <strong>Wpa2-个人</strong> ") 无线网络的密码。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>你可以在 Azure Active Directory 中注册设备，或在设备上创建本地帐户</br></br>使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。 Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 选择 " <strong>获取批量令牌</strong>"。 在 " <strong>让&#39;登录</strong> " 窗口中，输入有权将设备加入 Azure AD 的帐户，然后输入密码。 选择 " <strong>接受</strong> "，为 Windows 配置设计器指定必需的权限。 </br></br>若要创建本地帐户，请选择该选项，并输入用户名和密码。 </br></br><strong>无关紧要</strong> <br /> (适用于 Windows 10，版本1607仅) 如果在预配包中创建本地帐户，则必须每42天使用 " <strong>设置</strong> " 应用程序更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用证书预配设备，请单击<strong>添加证书</strong>。 输入证书的名称，然后浏览到要使用的证书并将其选中。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>切换 <strong>"是" 或 "</strong> <strong>否</strong> " 以在 HoloLens 上启用开发人员模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">了解有关开发人员模式的详细信息。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>不要设置密码来保护预配包。 如果预配包受密码保护，预配 HoloLens 设备将失败。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成后，选择“创建”  。 这只需几秒钟的时间。 生成该包之后，其存储位置将在页面底部显示为超链接。

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. 使用高级设置为 HoloLens 创建预配包

> [!NOTE]
> 在 **高级设置** 中创建的预配包无需包含版本升级许可证，Windows 全息 for Business 即可成功应用于 HoloLens (第一代) 。 有关[HoloLens (第一代) ，请参阅 Windows 全息 For Business 上的详细信息](hololens1-upgrade-enterprise.md)。

1. 在 Windows 配置设计器起始页上，选择 **高级预配**。
2. 在 **输入项目详细信息** 窗口中，指定项目的名称和项目的位置。 （可选）输入简要描述以描述你的项目。

3. 选择“**下一页**”。

4. 在 " **选择要查看和配置的设置** " 窗口中，选择 " **Windows 10 全息** 版"，然后选择 " **下一步**"。

5. 选择“完成”。

6. 展开 " **运行时设置** "，然后使用 [本文后面所述](#what-you-can-configure)的任何设置自定义包。

    > [!IMPORTANT]
    >  (适用于 Windows 10，版本1607仅) 如果在预配包中创建本地帐户，则必须每42天使用 " **设置** " 应用程序更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。 如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 选择“文件” > “保存”。

8. 阅读警告：项目文件可能包含敏感信息，然后选择 **"确定"**。

    > [!IMPORTANT]
    > 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。
    
9. 选择 "**导出**  >  **设置包**"。

10. 将 **所有者** 更改为 **IT 管理员**。这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包。 选择“**下一页**”。

11. 为“程序包版本”设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

12. 在 " **选择预配包的安全详细信息**" 中，选择 " **下一步**"。

    > [!WARNING]
    > 如果加密预配程序包，则 HoloLens 设备预配将失败。  

13. 选择 " **下一步** " 以指定在生成预配包后要将其移到的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。

    还可以选择 " **浏览** " 以更改默认输出位置。

14. 选择“**下一页**”。

15. 选择 " **生成** " 开始生成包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。

16. 生成完成后，选择 " **完成**"。

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>在安装过程中将预配包应用于 HoloLens

HoloLens 2 设备在 Windows 全息版、版本2004或版本 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更高版本上，可以使用 USB 驱动器应用预配包。 只需将 ppkg 文件复制到 USB 驱动器的根目录。 仅当设置包位于 USB 驱动器的根目录中时，才会应用它。 存在多个设置包将按顺序应用。

[Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本上的 HoloLens 2 设备具有较新的功能，可帮助简化和简化此过程，使其自动执行。 请查看以下各节：

- [从 USB 自动启动设置](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [自动确认在 OOBE 中预配包](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [无需使用 UI 即可自动预配](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. 使用 USB 电缆将设备连接到电脑 (或用于 HoloLens 2 的 USB 驱动器，如上文所述) ，然后启动设备。 请不要在 OOBE 的 **第一个种不可交互时间** 页面之前继续。   
    - 在 HoloLens (第一代) 上，此页包含一个蓝色框。 
    - 在 HoloLens 2 上，此页包含 hummingbird。

2. 短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。 

3. HoloLens 在计算机上的文件资源管理器中显示为设备。

4. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

5. 在 OOBE 的 **第一个种不可交互时刻** 页面上，短暂地按下并释放 "**音量降低**" 和 "**电源**" 按钮。

6. 设备会询问你是否信任包，并想要应用它。 确认你信任程序包。

7. 你将看到是否成功应用了程序包。 如果失败，你可以修复程序包，然后重试。 如果成功，请继续 OOBE。

> [!NOTE]
> 如果设备是在2016年8月之前购买的，则需要使用 Microsoft 帐户登录到设备，获取最新的操作系统更新，然后重置操作系统，以便应用预配包。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动设置

- 在 OOBE 期间使用带有预配包的 USB 驱动器时，可通过自动化过程来减少用户交互。

在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，才能使用按钮组合进行设置。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一次种不可交互时插入带有预配包的 USB 驱动器
1. 当设备准备好进行预配时，将自动在 "设置" 页中打开提示。 

注意：如果在设备启动时，会将 USB 驱动器插入，则 OOBE 会枚举现有 USB 存储设备，并监视其他设备是否已插入。

了解如何在 [OOBE 期间应用预配包](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>自动确认在 OOBE 中预配包
- 自动进程允许进行更少的用户交互，当 "预配包" 页面显示时，它将自动应用列出的所有包。

当设置主屏幕出现时，OOBE 将在10秒内计数，然后自动开始应用所有预配包。 验证所需的包后，用户仍可以在此10秒内确认或取消。

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

你的设备现在已配置，并将显示设置成功屏幕。

## <a name="apply-a-provisioning-package-to-hololens-after-setup"></a>安装后将预配包应用于 HoloLens

> [!NOTE]
> 这些步骤仅适用于 Windows 10 1809 版。

在电脑上，执行以下步骤：
1. 创建预配包，如 [使用 Hololens 创建 hololens 的预配包](hololens-provisioning.md)中所述。
2. 使用 USB 电缆将 HoloLens 设备连接到 PC。 HoloLens 在计算机上的文件资源管理器中显示为设备。
3. 将预配包拖放到 HoloLens 上的 Documents 文件夹中。

在 HoloLens 上，执行以下步骤：
1. 转至“设置”   > “帐户”   > “访问工作或学校”  。 
2. 在 " **相关设置**" 中，选择 " **添加或删除预配包**"。
3. 在下一页上，选择 " **添加包** " 以启动文件选取器并选择预配包。 如果文件夹为空，请确保选择 **该设备** 并选择 " **文档**"。

应用了你的包后，它将显示在 **已安装的包** 列表中。 若要查看包详细信息或从设备中删除包，请选择列出的包。

## <a name="what-you-can-configure"></a>可配置项

预配包使用配置服务提供程序 (CSP)。 如果你对 CSP 不甚了解，请参阅[针对 IT 专业人员的配置服务提供程序 (CSP) 简介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。

在 Windows 配置设计器中，当创建用于 Windows 全息版的预配包时，**可用自定义** 中的设置是基于 [Windows 全息版中支持的 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。 下表介绍了你可能想要为 HoloLens 配置的设置。

![HoloLens 的通用运行时设置](images/icd-settings.png)

| 设置 | 描述 |
| --- | --- |
| **Certificates** | 将证书部署到 HoloLens。  |
| **ConnectivityProfiles** | 将 WLAN 配置文件部署到 HoloLens。   |
| **EditionUpgrade** | [升级到 Windows 全息版企业版。](hololens1-upgrade-enterprise.md)  |
| **策略** | 允许或阻止 HoloLens 中的开发人员模式。 [Windows Holographic for Business 支持的策略](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>通过预配包安装应用

可以通过在 HoloLens 2 设备上通过预配包安装应用。 这样就可以轻松地重复使用包，你可以使用它来帮助你分发应用程序。 阅读有关 [通过预配包部署应用](app-deploy-provisioning-package.md)的完整说明。  

> [!NOTE]
> HoloLens (第一代) 支持通过使用预配包在 **UniversalAppInstall**)  (安装应用程序。 HoloLens (第一代) 设备仅支持在 OOBE 期间仅通过 PPKG 安装应用，并且仅支持使用用户上下文安装进行安装。
