---
title: '使用 HoloLens 包 (HoloLens) 配置 HoloLens) '
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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 917e9fd0e8bf69eb0b7c53165029cb8e42904582
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955454"
---
# 使用预配置包配置 HoloLens

[通过 Windows 预定，IT](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 管理员可以轻松配置最终用户设备，而无需发送模拟。 Windows 配置设计器是一种用于配置图像和运行时设置的工具，这些设置之后将其内置于设置包中。

可以在设置包中应用的一些 HoloLens 配置包括：

- 在这里升级到适用于企业的 Windows Holographic [for](hololens1-upgrade-enterprise.md) Business
- 设置本地帐户
- 设置 WLAN 连接
- 将证书应用到设备
- 启用开发人员模式
- 此处提供了 (组向内包模式配置适合配置的[说明。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## 设置包 HoloLens 向导

HoloLens 向导可帮助在设置包中配置以下设置：

- 升级到企业版

    > [!NOTE]
    > 这应该仅用于 HoloLens 1st 生成的设备。 仅当预配置包包含 Windows Holographic for Business 的版本升级许可证时，或者该设备已升级到 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)时，才能应用正在设置的设置。

- 配置 OOBE 引发的 (HoloLens) 体验
- 配置 WLAN 网络
- 在 Azure Active Directory 中注册设备，或创建本地帐户
- 添加证书
- 启用开发人员模式
- 配置面板模式。  (在此处找到有关配置种类模式的详细说明[) 。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> 你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。

设置包中可以包括管理说明和策略、自定义网络连接和策略等。

> [!TIP]
> 使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。

## 创建设置包的步骤

1. **选项 1：**[来自 Microsoft Store。](https://www.microsoft.com/store/apps/9nblggh4tx22) 这包括 HoloLens 2 功能。
2. **选项** [2：从适用于 Windows 10 的 Windows 评估和 (部署) 工具包](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果从 Windows ADK 安装 Windows 配置设计器，请从 **"选择** 要安装" **对话框的"配置设计器"中选择"配置** 设计器"。 此选项不包括 HoloLens 2 功能。

> [!NOTE]
> 如果你知道自身需要 Windows Configuration Designer 访问的脱机电脑，请遵循此处的离线应用[here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store)安装进行高级恢复助手，但是改为让 Windows 确认认者已改为描述你的选择。 

### 2. 创建预订包

使用 Windows 配置设计器工具创建预配包。

1. 打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。

2. 选择 **"预安装 HoloLens 设备**"。

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. 为项目命名， **然后选择"完成**"。

4. 阅读"开始"页 **上的说明，然后选择"** 下一 **步**"。 用于桌面设置的页面将为你完成以下步骤。
  
> [!IMPORTANT]
> 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。

### 配置设置

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>浏览并选择企业许可证文件以升级 HoloLens 版本。</br></br>您也可以切换"是"或 <strong> " </strong> <strong> 否 </strong> "以隐藏第一个体验的各个部分。</br></br>要设置无需连接到 Wi-Fi 网络的设备，请将 <strong> Skip Wi-Fi 设置切换 </strong> 到 <strong> "开 </strong> "。</br></br>选择要使用设备的区域和时区。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在这一部分中，你可以输入设备应自动连接到的 Wi-Fi 无线网络的详细信息。 为此，选择 <strong> "打开 </strong> "，输入 SSID、网络类型 (<strong> 打开或 </strong> <strong> WPA2 个人 </strong>) 及 (如果 <strong> WPA2 个人 </strong> 版通过无线网络设置密码，) 则输入 SSID。）及 (</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>可在 Azure Active Directory 中注册设备，或在设备上创建一个本地帐户</br></br>使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。 Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 选择 <strong> "获取批量令牌 </strong> "。 在" <strong> 允&#39;使你登录 </strong> 窗口中，输入有权将设备加入 Azure AD 的帐户，然后输入密码。 选择 <strong> "接受 </strong> "可向 Windows 配置设计器授予必要权限。 </br></br>若要创建本地帐户，请选择该选项并输入用户名和密码。 </br></br><strong>重要提示：</strong> <br /> (对于 Windows 10，则只有版本 1607，) 如果在设置包中创建本地帐户，则每 42 天 <strong> 必须使用设置 </strong> 应用更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用证书预配设备，请单击<strong>添加证书</strong>。 输入证书的名称，然后浏览到要使用的证书并将其选中。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>切换" <strong> 是"或" </strong> <strong> 否 </strong> "以在 HoloLens 上启用开发人员模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">了解有关开发人员模式的详细信息。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>请勿设置密码来保护你的设置包。 如果通过密码保护设置包，则设置 HoloLens 设备将失败。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成后，选择" **创建**"。 这只需几秒钟的时间。 生成该包之后，其存储位置将在页面底部显示为超链接。

### 3. 使用高级设置，为 HoloLens 创建预订包

> [!NOTE]
> 在高级设置中创建的设置包不需要**Advanced provisioning**包括 Windows Holographic for Business 的版本升级许可证，以便成功适用于 HoloLens (1st) 。 [查看 HoloLens for Business for Business 的 Windows Holographic for Business 的详细信息 (1st 生成) 。 ](hololens1-upgrade-enterprise.md)

1. 在 Windows 配置设计器起始页上，选择**高级预配**。
2. 在**输入项目详细信息**窗口中，指定项目的名称和项目的位置。 （可选）输入简要描述以描述你的项目。

3. 选择**下一步** 。

4. 在" **选择要查看和配置的设置"** 中，选择 **Windows 10 全息版**，然后选择"下 **一步**"。

5. **选择"完成**"。

6. 使用本文稍 **后所述** 的任何设置展开运行时设置并 [自定义该程序包](#what-you-can-configure)。

    > [!IMPORTANT]
    >  (对于 Windows 10，版本 1607 仅) 如果在设置包中创建本地帐户，则每 42 天必须使用 **设置** 应用更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。 如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 选择 **"文件**  >  **保存**"。

8. 阅读项目文件可能包含敏感信息的警告，然后选择" **确定**"。

    > [!IMPORTANT]
    > 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。
    
9. 选择**Export**  >  **"导出预订包**"。

10. 将 **所有者** 更改 **为 IT 管理员**。这会设置此设置包的优先级高于设置应用于此源的此设备的程序包。 选择**下一步** 。

11. 为**程序包版本**设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

12. 在设置 **包的"选择安全详细信息"上，选择"** 下 **一步**"。

    > [!WARNING]
    > 如果加密预配程序包，则 HoloLens 设备预配将失败。  

13. 选择 **"** 下一步"以指定在生成之后想要设置程序包的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。

    或者，也可以选择 **"浏览"来** 更改默认输出位置。

14. 选择**下一步** 。

15. 选择 **"生成** "以开始生成包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。

16. 当内部版本完成时， **选择"完成**"。

<span id="apply" />

## 在设置期间将配置包应用于 HoloLens

内部版本 [19041.1103 或更](hololens-release-notes.md#windows-holographic-version-2004) 高版本上的 HoloLens 2 设备可能使用 U 盘来应用预配置包。 只需将 .ppkg 文件复制到 U 盘的根中。 仅当程序包位于 U 盘的根中时，它们将应用。 多个设置包演示将按顺序应用。

1. 使用 USB 电缆将设备连接到上面 (的 UC 驱动器) 或 U 盘，然后启动该设备。 不要在 OOBE 的第 **一个** 可互动的时段页面继续。   
    - 在 HoloLens 上， (第一) 代的，此页面包含一个蓝色的框。 
    - 在 HoloLens 2 上，此页面包含手拨号。

2. 短暂地同时按下**调低音量**和**电源**按钮，然后释放。 

3. HoloLens 显示为电脑上文件资源管理器中的设备。

4. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

5. 在 OOBE 的第一**Volume Down**个可互动性页面上，一次性按并释放音量向下和**电**源按钮。 **First interactable moment**

6. 设备将询问您是否信任该程序包，并希望应用它。 确认你信任程序包。

7. 你将看到是否成功应用了程序包。 如果失败，你可以修复程序包，然后重试。 如果成功，请继续 OOBE。

> [!NOTE]
> 如果在 2016 年 8 月之前购买了该设备，你需要使用 Microsoft 帐户登录设备，获取最新操作系统更新，然后重置操作系统，以便应用设置包。

## 在设置后将设置包应用于 HoloLens

> [!NOTE]
> 这些步骤仅适用于 Windows 10 版本 1809。

在电脑上，按照下列步骤操作：
1. 按照" [使用 HoloLens 向导创建为 HoloLens 创建 provisions 的包"创建预订包](hololens-provisioning.md)"。
2. 使用 USB 电缆将 HoloLens 设备连接到电脑。 HoloLens 显示为电脑上文件资源管理器中的设备。
3. 将其首发放到 HoloLens 上的"文档"文件夹中。

在 HoloLens 上，请按照下列步骤操作：
1. 转到"**设置**  >  **帐户**  >  **访问"工作或学校**帐户访问。 
2. 在 **"相关**设置" **中，选择"添加"或"移除设置包**"。
3. 在下一页上， **选择"添加包** "以启动文件选取器并选择你的设置包。 如果该文件夹为空，请确保选择"此 **设备"，** 然后选择" **文档**"。

在应用包后，它将显示在已安装程序 **包的列表中**。 若要查看程序包详细信息或要从设备中删除程序包，请选择列出的程序包。

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

> [!NOTE]
> HoloLens 当前不支持使用通过使用 (在 **UniversalAppInstall**) 来安装应用。
