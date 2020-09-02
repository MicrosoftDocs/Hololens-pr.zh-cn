---
title: 使用预配包 (HoloLens) 配置 HoloLens
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
ms.openlocfilehash: da783756c271c589f67efca0c229ad0f777857e2
ms.sourcegitcommit: ccdd628cdbb5b89741f5dbc971143cb2fd2e451b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10990913"
---
# 使用预配包配置 HoloLens

[Windows 预配](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 让 it 管理员可以轻松地配置最终用户设备而无需使用图像。 Windows 配置设计器是一个用于配置图像和运行时设置的工具，这些设置随后将被内置到预配程序包中。

可在预配包中应用的一些 HoloLens 配置包括以下内容：

- [在此处](hololens1-upgrade-enterprise.md)升级到 Windows 全息版企业版
- 设置本地帐户
- 设置 WLAN 连接
- 将证书应用到设备
- 启用开发人员模式
- 配置展台模式 (可在 [此处](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)找到配置展台模式的详细说明。

## 预配程序包 HoloLens 向导

HoloLens 向导可帮助你在预配包中配置以下设置：

- 升级到企业版

    > [!NOTE]
    > 这只应用于 HoloLens 第一代设备。 仅在预配包中包含 Windows 全息版的版本升级许可证或者 [设备已升级到 Windows 全息版企业](hololens1-upgrade-enterprise.md)版时，才会应用预配包中的设置。

- 在 OOBE (配置 HoloLens 首次体验) 
- 配置 Wlan 网络
- 在 Azure Active Directory 中注册设备，或创建本地帐户
- 添加证书
- 启用开发人员模式
- 配置展台模式。  (可在 [此处](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)) 找到配置展台模式的详细说明。

> [!WARNING]
> 你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。

预配程序包可以包括管理说明和策略、自定义网络连接和策略等。

> [!TIP]
> 使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。

## 创建预配程序包的步骤

1. **选项1：** [从 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。 这包括 HoloLens 2 功能。
2. **选项2：** [从 Windows 评估和部署工具包 (适用于 WINDOWS 10 的 ADK) ](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果从 Windows ADK 安装 Windows 配置设计器，请从 "**选择要安装的功能**" 对话框中选择 "**配置设计器**"。 此选项不包括 HoloLens 2 功能。

> [!NOTE]
> 如果你知道你将使用需要访问 Windows 配置设计器的脱机电脑，请按照 [此处](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 的脱机应用安装进行高级恢复助理，但让 Windows Confiugration Desinger 你的选择。 

### 2. 创建预配包

使用 Windows 配置设计器工具创建预配包。

1. 打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。

2. 选择 " **设置 HoloLens 设备**"。

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. 为项目命名，然后选择 " **完成**"。

4. 阅读 " **入门** " 页面上的说明，然后选择 " **下一步**"。 桌面预配的页面将引导你完成以下步骤。
  
> [!IMPORTANT]
> 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。

### 配置设置

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>通过浏览找到并选择要升级 HoloLens 版本的企业许可证文件。</br></br>您也可以切换 <strong> "是" </strong> 或 " <strong> 否" </strong> 以隐藏第一个体验的各个部分。</br></br>若要设置设备而无需连接到 Wi-fi 网络，请切换 <strong> "将 wi-fi 设置跳 </strong> 到 <strong> " </strong> 。</br></br>选择将使用设备的区域和时区。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在此部分中，你可以输入设备应自动连接到的 Wi-fi 无线网络的详细信息。 若要执行此操作，请依次选择 " <strong> </strong> 打开"、"网络类型" (" <strong> 打开" </strong> 或 <strong> "wpa2-个人 </strong>) "，以及 (如果 <strong> WPA2-个人 </strong>) 无线网络的密码。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>你可以在 Azure Active Directory 中注册设备，也可以在设备上创建本地帐户</br></br>使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。 Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 选择 " <strong> 获取批量令牌" </strong> 。 在 " <strong> 让&#39;s 登录" 窗口中 </strong> ，输入有权将设备加入 Azure AD 的帐户，然后输入密码。 选择 <strong> </strong> "接受" 以向 Windows 配置设计器提供必要的权限。 </br></br>若要创建本地帐户，请选择该选项，然后输入用户名和密码。 </br></br><strong>重要提示：</strong> <br /> (适用于 Windows 10 版本1607版本) 如果在预配包中创建本地帐户，则必须在 <strong> 每42天使用 "设置" 应用更改密码 </strong> 。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用证书预配设备，请单击<strong>添加证书</strong>。 输入证书的名称，然后浏览到要使用的证书并将其选中。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>切换 <strong> "是" </strong> 或 " <strong> 否" </strong> 以在 HoloLens 上启用开发人员模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">了解有关开发人员模式的详细信息。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>不要设置密码来保护预配包。 如果预配包受密码保护，则预配 HoloLens 设备将失败。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成后，选择 " **创建**"。 这只需几秒钟的时间。 生成该包之后，其存储位置将在页面底部显示为超链接。

### 3. 使用高级预配创建 HoloLens 的预配包

> [!NOTE]
> 在 **高级预配** 中创建的预配包无需包含版本升级许可证，Windows 全息版才能成功地应用于 HoloLens (第一代) 。 有关[HoloLens (第一代) 的详细信息，请参阅 Windows 全息版商业](hololens1-upgrade-enterprise.md)版。

1. 在 Windows 配置设计器起始页上，选择**高级预配**。
2. 在**输入项目详细信息**窗口中，指定项目的名称和项目的位置。 （可选）输入简要描述以描述你的项目。

3. 选择**下一步** 。

4. 在 " **选择要查看和配置的设置** " 窗口中，选择 " **Windows 10 全息**版"，然后选择 " **下一步**"。

5. 选择 " **完成**"。

6. 通过使用[本文后面所述](#what-you-can-configure)的任何设置，展开 "**运行时设置**" 并自定义程序包。

    > [!IMPORTANT]
    >  (适用于 Windows 10 版本1607版本) 如果在预配包中创建本地帐户，则必须在每42天使用 " **设置** " 应用更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。 如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 选择**File**"  >  **保存**文件"。

8. 阅读有关项目文件可能包含敏感信息的警告，然后选择 **"确定"**。

    > [!IMPORTANT]
    > 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。
    
9. 选择 "**导出**  >  **预配包**"。

10. 将 **所有者** 更改为 **IT 管理员**。这会将此预配包的优先级设置为高于从其他源应用到此设备的预配包的优先级。 选择**下一步** 。

11. 为**程序包版本**设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

12. 在 " **选择预配包的安全详细信息**" 中，选择 " **下一步**"。

    > [!WARNING]
    > 如果加密预配程序包，则 HoloLens 设备预配将失败。  

13. 选择 " **下一步** " 以指定在构建预配包后你希望其转到的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。

    或者，你可以选择 " **浏览** " 以更改默认输出位置。

14. 选择**下一步** 。

15. 选择 " **生成** " 开始构建程序包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。

16. 生成完成后，选择 " **完成**"。

<span id="apply" />

## 在安装期间将预配包应用于 HoloLens

在内部版本 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更高版本上使用 HoloLens 2 设备，可能会使用 USB 驱动器应用预配包。 只需将 ppkg 文件复制到 USB 驱动器的根目录。 仅当预配程序包位于 USB 驱动器的根中时，才会应用该程序包。 存在多个预配包，将按顺序应用。

1. 使用 USB 电缆将设备连接到电脑 (或用于 HoloLens 2 的 USB 驱动器（如上述) 所述），然后启动设备。 不要在 OOBE 的 **第一交互时刻的一** 页之前继续。   
    - 在 HoloLens (第一代) ，此页面包含一个蓝色框。 
    - 在 HoloLens 2 上，此页面包含 hummingbird。

2. 短暂地同时按下**调低音量**和**电源**按钮，然后释放。 

3. HoloLens 在电脑上的文件资源管理器中显示为设备。

4. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

5. 在 OOBE 的**第一个交互时刻**页面上，短暂地按下并释放**音量**和**电源**按钮。

6. 设备会询问你是否信任程序包并希望应用它。 确认你信任程序包。

7. 你将看到是否成功应用了程序包。 如果失败，你可以修复程序包，然后重试。 如果成功，请继续 OOBE。

> [!NOTE]
> 如果在2016年8月之前购买了该设备，你需要使用 Microsoft 帐户登录到该设备，获取最新的操作系统更新，然后重置操作系统，以便应用预配包。

## 安装后将预配包应用于 HoloLens

> [!NOTE]
> 这些步骤仅适用于 Windows 10 版本1809。

在你的电脑上，请按照以下步骤操作：
1. 按照 [使用 hololens 向导创建 HoloLens 的预配包](hololens-provisioning.md)中所述，创建预配包。
2. 使用 USB 电缆将 HoloLens 设备连接到电脑。 HoloLens 在电脑上的文件资源管理器中显示为设备。
3. 将预配包拖放到 HoloLens 上的 "文档" 文件夹。

在 HoloLens 中，请按照下列步骤操作：
1. 转到 "**设置**"  >  **帐户**  >  **访问工作或学校**。 
2. 在 " **相关设置**" 中，选择 " **添加或删除预配包**"。
3. 在下一页上，选择 " **添加程序包** " 以启动 "文件选取器"，然后选择预配包。 如果文件夹为空，请确保选择 " **此设备** "，然后选择 " **文档**"。

应用程序包后，它将显示在 **已安装程序包**的列表中。 若要查看程序包详细信息或从设备中删除程序包，请选择列出的程序包。

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

## 通过预配程序包安装应用

可以通过 HoloLens 2 设备上的预配包来安装应用。 这使你可以使用一种易于重新使用的程序包来帮助你分发你的应用。 阅读 [通过预配程序包部署应用](app-deploy-provisioning-package.md)的完整说明。  

> [!NOTE]
> HoloLens (第一代) 不支持通过使用预配包 (**UniversalAppInstall**) 安装应用。
