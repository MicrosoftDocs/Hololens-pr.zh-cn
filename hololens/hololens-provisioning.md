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
# <span data-ttu-id="f9837-103">使用预配置包配置 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f9837-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="f9837-104">[通过 Windows 预定，IT](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 管理员可以轻松配置最终用户设备，而无需发送模拟。</span><span class="sxs-lookup"><span data-stu-id="f9837-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="f9837-105">Windows 配置设计器是一种用于配置图像和运行时设置的工具，这些设置之后将其内置于设置包中。</span><span class="sxs-lookup"><span data-stu-id="f9837-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="f9837-106">可以在设置包中应用的一些 HoloLens 配置包括：</span><span class="sxs-lookup"><span data-stu-id="f9837-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="f9837-107">在这里升级到适用于企业的 Windows Holographic [for](hololens1-upgrade-enterprise.md) Business</span><span class="sxs-lookup"><span data-stu-id="f9837-107">Upgrade to Windows Holographic for Business [here](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="f9837-108">设置本地帐户</span><span class="sxs-lookup"><span data-stu-id="f9837-108">Set up a local account</span></span>
- <span data-ttu-id="f9837-109">设置 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="f9837-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="f9837-110">将证书应用到设备</span><span class="sxs-lookup"><span data-stu-id="f9837-110">Apply certificates to the device</span></span>
- <span data-ttu-id="f9837-111">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="f9837-111">Enable Developer Mode</span></span>
- <span data-ttu-id="f9837-112">此处提供了 (组向内包模式配置适合配置的[说明。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="f9837-112">Configure Kiosk mode (Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <span data-ttu-id="f9837-113">设置包 HoloLens 向导</span><span class="sxs-lookup"><span data-stu-id="f9837-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="f9837-114">HoloLens 向导可帮助在设置包中配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f9837-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="f9837-115">升级到企业版</span><span class="sxs-lookup"><span data-stu-id="f9837-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9837-116">这应该仅用于 HoloLens 1st 生成的设备。</span><span class="sxs-lookup"><span data-stu-id="f9837-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="f9837-117">仅当预配置包包含 Windows Holographic for Business 的版本升级许可证时，或者该设备已升级到 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)时，才能应用正在设置的设置。</span><span class="sxs-lookup"><span data-stu-id="f9837-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="f9837-118">配置 OOBE 引发的 (HoloLens) 体验</span><span class="sxs-lookup"><span data-stu-id="f9837-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="f9837-119">配置 WLAN 网络</span><span class="sxs-lookup"><span data-stu-id="f9837-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="f9837-120">在 Azure Active Directory 中注册设备，或创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="f9837-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="f9837-121">添加证书</span><span class="sxs-lookup"><span data-stu-id="f9837-121">Add certificates</span></span>
- <span data-ttu-id="f9837-122">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="f9837-122">Enable Developer Mode</span></span>
- <span data-ttu-id="f9837-123">配置面板模式。</span><span class="sxs-lookup"><span data-stu-id="f9837-123">Configure kiosk mode.</span></span> <span data-ttu-id="f9837-124"> (在此处找到有关配置种类模式的详细说明[) 。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="f9837-124">(Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="f9837-125">你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。</span><span class="sxs-lookup"><span data-stu-id="f9837-125">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="f9837-126">设置包中可以包括管理说明和策略、自定义网络连接和策略等。</span><span class="sxs-lookup"><span data-stu-id="f9837-126">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="f9837-127">使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。</span><span class="sxs-lookup"><span data-stu-id="f9837-127">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <span data-ttu-id="f9837-128">创建设置包的步骤</span><span class="sxs-lookup"><span data-stu-id="f9837-128">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="f9837-129">**选项 1：**[来自 Microsoft Store。](https://www.microsoft.com/store/apps/9nblggh4tx22)</span><span class="sxs-lookup"><span data-stu-id="f9837-129">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="f9837-130">这包括 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="f9837-130">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="f9837-131">**选项** [2：从适用于 Windows 10 的 Windows 评估和 (部署) 工具包](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。</span><span class="sxs-lookup"><span data-stu-id="f9837-131">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="f9837-132">如果从 Windows ADK 安装 Windows 配置设计器，请从 **"选择** 要安装" **对话框的"配置设计器"中选择"配置** 设计器"。</span><span class="sxs-lookup"><span data-stu-id="f9837-132">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="f9837-133">此选项不包括 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="f9837-133">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="f9837-134">如果你知道自身需要 Windows Configuration Designer 访问的脱机电脑，请遵循此处的离线应用[here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store)安装进行高级恢复助手，但是改为让 Windows 确认认者已改为描述你的选择。</span><span class="sxs-lookup"><span data-stu-id="f9837-134">If you know you will be using an offline PC that needs access to Windows Configuration Designer please follow the offline app install [here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) for Advanced Recovery Companion but making Windows Confiugration Desinger your selection instead.</span></span> 

### <span data-ttu-id="f9837-135">2. 创建预订包</span><span class="sxs-lookup"><span data-stu-id="f9837-135">2. Create the provisioning package</span></span>

<span data-ttu-id="f9837-136">使用 Windows 配置设计器工具创建预配包。</span><span class="sxs-lookup"><span data-stu-id="f9837-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="f9837-137">打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。</span><span class="sxs-lookup"><span data-stu-id="f9837-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="f9837-138">选择 **"预安装 HoloLens 设备**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. <span data-ttu-id="f9837-140">为项目命名， **然后选择"完成**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="f9837-141">阅读"开始"页 **上的说明，然后选择"** 下一 **步**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="f9837-142">用于桌面设置的页面将为你完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f9837-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9837-143">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="f9837-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="f9837-144">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="f9837-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="f9837-145">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="f9837-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <span data-ttu-id="f9837-146">配置设置</span><span class="sxs-lookup"><span data-stu-id="f9837-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="f9837-147">浏览并选择企业许可证文件以升级 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="f9837-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="f9837-148">您也可以切换"是"或 <strong> " </strong> <strong> 否 </strong> "以隐藏第一个体验的各个部分。</span><span class="sxs-lookup"><span data-stu-id="f9837-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="f9837-149">要设置无需连接到 Wi-Fi 网络的设备，请将 <strong> Skip Wi-Fi 设置切换 </strong> 到 <strong> "开 </strong> "。</span><span class="sxs-lookup"><span data-stu-id="f9837-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="f9837-150">选择要使用设备的区域和时区。</span><span class="sxs-lookup"><span data-stu-id="f9837-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="f9837-151">在这一部分中，你可以输入设备应自动连接到的 Wi-Fi 无线网络的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9837-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="f9837-152">为此，选择 <strong> "打开 </strong> "，输入 SSID、网络类型 (<strong> 打开或 </strong> <strong> WPA2 个人 </strong>) 及 (如果 <strong> WPA2 个人 </strong> 版通过无线网络设置密码，) 则输入 SSID。）及 (</span><span class="sxs-lookup"><span data-stu-id="f9837-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="f9837-153">可在 Azure Active Directory 中注册设备，或在设备上创建一个本地帐户</span><span class="sxs-lookup"><span data-stu-id="f9837-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="f9837-154">使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。</span><span class="sxs-lookup"><span data-stu-id="f9837-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="f9837-155">Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。</span><span class="sxs-lookup"><span data-stu-id="f9837-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="f9837-156">若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。</span><span class="sxs-lookup"><span data-stu-id="f9837-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="f9837-157">设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。</span><span class="sxs-lookup"><span data-stu-id="f9837-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="f9837-158">选择 <strong> "获取批量令牌 </strong> "。</span><span class="sxs-lookup"><span data-stu-id="f9837-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="f9837-159">在" <strong> 允&#39;使你登录 </strong> 窗口中，输入有权将设备加入 Azure AD 的帐户，然后输入密码。</span><span class="sxs-lookup"><span data-stu-id="f9837-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="f9837-160">选择 <strong> "接受 </strong> "可向 Windows 配置设计器授予必要权限。</span><span class="sxs-lookup"><span data-stu-id="f9837-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="f9837-161">若要创建本地帐户，请选择该选项并输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f9837-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="f9837-162">重要提示：</span><span class="sxs-lookup"><span data-stu-id="f9837-162">Important:</span></span></strong> <br /><span data-ttu-id="f9837-163"> (对于 Windows 10，则只有版本 1607，) 如果在设置包中创建本地帐户，则每 42 天 <strong> 必须使用设置 </strong> 应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="f9837-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="f9837-164">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="f9837-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="f9837-165">若要使用证书预配设备，请单击<strong>添加证书</strong>。</span><span class="sxs-lookup"><span data-stu-id="f9837-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="f9837-166">输入证书的名称，然后浏览到要使用的证书并将其选中。</span><span class="sxs-lookup"><span data-stu-id="f9837-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="f9837-167">切换" <strong> 是"或" </strong> <strong> 否 </strong> "以在 HoloLens 上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="f9837-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)"><span data-ttu-id="f9837-168">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9837-168">Learn more about Developer Mode.</span></span></a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="f9837-169">请勿设置密码来保护你的设置包。</span><span class="sxs-lookup"><span data-stu-id="f9837-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="f9837-170">如果通过密码保护设置包，则设置 HoloLens 设备将失败。</span><span class="sxs-lookup"><span data-stu-id="f9837-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="f9837-171">完成后，选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-171">After you're done, select **Create**.</span></span> <span data-ttu-id="f9837-172">这只需几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="f9837-172">It only takes a few seconds.</span></span> <span data-ttu-id="f9837-173">生成该包之后，其存储位置将在页面底部显示为超链接。</span><span class="sxs-lookup"><span data-stu-id="f9837-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <span data-ttu-id="f9837-174">3. 使用高级设置，为 HoloLens 创建预订包</span><span class="sxs-lookup"><span data-stu-id="f9837-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="f9837-175">在高级设置中创建的设置包不需要**Advanced provisioning**包括 Windows Holographic for Business 的版本升级许可证，以便成功适用于 HoloLens (1st) 。</span><span class="sxs-lookup"><span data-stu-id="f9837-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="f9837-176">[查看 HoloLens for Business for Business 的 Windows Holographic for Business 的详细信息 (1st 生成) 。 ](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="f9837-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="f9837-177">在 Windows 配置设计器起始页上，选择**高级预配**。</span><span class="sxs-lookup"><span data-stu-id="f9837-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="f9837-178">在**输入项目详细信息**窗口中，指定项目的名称和项目的位置。</span><span class="sxs-lookup"><span data-stu-id="f9837-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="f9837-179">（可选）输入简要描述以描述你的项目。</span><span class="sxs-lookup"><span data-stu-id="f9837-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="f9837-180">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="f9837-180">Select **Next**.</span></span>

4. <span data-ttu-id="f9837-181">在" **选择要查看和配置的设置"** 中，选择 **Windows 10 全息版**，然后选择"下 **一步**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="f9837-182">**选择"完成**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-182">Select **Finish**.</span></span>

6. <span data-ttu-id="f9837-183">使用本文稍 **后所述** 的任何设置展开运行时设置并 [自定义该程序包](#what-you-can-configure)。</span><span class="sxs-lookup"><span data-stu-id="f9837-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9837-184"> (对于 Windows 10，版本 1607 仅) 如果在设置包中创建本地帐户，则每 42 天必须使用 **设置** 应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="f9837-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="f9837-185">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="f9837-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="f9837-186">如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。</span><span class="sxs-lookup"><span data-stu-id="f9837-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="f9837-187">选择 **"文件**  >  **保存**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="f9837-188">阅读项目文件可能包含敏感信息的警告，然后选择" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9837-189">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="f9837-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="f9837-190">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="f9837-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="f9837-191">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="f9837-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="f9837-192">选择**Export**  >  **"导出预订包**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="f9837-193">将 **所有者** 更改 **为 IT 管理员**。这会设置此设置包的优先级高于设置应用于此源的此设备的程序包。</span><span class="sxs-lookup"><span data-stu-id="f9837-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="f9837-194">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="f9837-194">Select **Next**.</span></span>

11. <span data-ttu-id="f9837-195">为**程序包版本**设置一个值。</span><span class="sxs-lookup"><span data-stu-id="f9837-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f9837-196">你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="f9837-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="f9837-197">在设置 **包的"选择安全详细信息"上，选择"** 下 **一步**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f9837-198">如果加密预配程序包，则 HoloLens 设备预配将失败。</span><span class="sxs-lookup"><span data-stu-id="f9837-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="f9837-199">选择 **"** 下一步"以指定在生成之后想要设置程序包的输出位置。</span><span class="sxs-lookup"><span data-stu-id="f9837-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="f9837-200">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="f9837-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="f9837-201">或者，也可以选择 **"浏览"来** 更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="f9837-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="f9837-202">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="f9837-202">Select **Next**.</span></span>

15. <span data-ttu-id="f9837-203">选择 **"生成** "以开始生成包。</span><span class="sxs-lookup"><span data-stu-id="f9837-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="f9837-204">项目信息会显示在构建页面中，并且进度栏会指示构建状态。</span><span class="sxs-lookup"><span data-stu-id="f9837-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="f9837-205">当内部版本完成时， **选择"完成**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <span data-ttu-id="f9837-206">在设置期间将配置包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f9837-206">Apply a provisioning package to HoloLens during setup</span></span>

<span data-ttu-id="f9837-207">内部版本 [19041.1103 或更](hololens-release-notes.md#windows-holographic-version-2004) 高版本上的 HoloLens 2 设备可能使用 U 盘来应用预配置包。</span><span class="sxs-lookup"><span data-stu-id="f9837-207">HoloLens 2 devices on build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) or later, may use a USB drive to apply a provisioning package.</span></span> <span data-ttu-id="f9837-208">只需将 .ppkg 文件复制到 U 盘的根中。</span><span class="sxs-lookup"><span data-stu-id="f9837-208">Simply copy the .ppkg file to the root of the USB drive.</span></span> <span data-ttu-id="f9837-209">仅当程序包位于 U 盘的根中时，它们将应用。</span><span class="sxs-lookup"><span data-stu-id="f9837-209">Provisioning packages will only be applied if they’re in the root of the USB drive.</span></span> <span data-ttu-id="f9837-210">多个设置包演示将按顺序应用。</span><span class="sxs-lookup"><span data-stu-id="f9837-210">Multiple provisioning package present will be applied sequentially.</span></span>

1. <span data-ttu-id="f9837-211">使用 USB 电缆将设备连接到上面 (的 UC 驱动器) 或 U 盘，然后启动该设备。</span><span class="sxs-lookup"><span data-stu-id="f9837-211">Use the USB cable to connect the device to a PC (or USB drive for HoloLens 2 as mentioned above), and then start the device.</span></span> <span data-ttu-id="f9837-212">不要在 OOBE 的第 **一个** 可互动的时段页面继续。</span><span class="sxs-lookup"><span data-stu-id="f9837-212">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="f9837-213">在 HoloLens 上， (第一) 代的，此页面包含一个蓝色的框。</span><span class="sxs-lookup"><span data-stu-id="f9837-213">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="f9837-214">在 HoloLens 2 上，此页面包含手拨号。</span><span class="sxs-lookup"><span data-stu-id="f9837-214">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="f9837-215">短暂地同时按下**调低音量**和**电源**按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="f9837-215">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="f9837-216">HoloLens 显示为电脑上文件资源管理器中的设备。</span><span class="sxs-lookup"><span data-stu-id="f9837-216">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="f9837-217">在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。</span><span class="sxs-lookup"><span data-stu-id="f9837-217">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="f9837-218">在 OOBE 的第一**Volume Down**个可互动性页面上，一次性按并释放音量向下和**电**源按钮。 **First interactable moment**</span><span class="sxs-lookup"><span data-stu-id="f9837-218">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **First interactable moment** page of OOBE.</span></span>

6. <span data-ttu-id="f9837-219">设备将询问您是否信任该程序包，并希望应用它。</span><span class="sxs-lookup"><span data-stu-id="f9837-219">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="f9837-220">确认你信任程序包。</span><span class="sxs-lookup"><span data-stu-id="f9837-220">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="f9837-221">你将看到是否成功应用了程序包。</span><span class="sxs-lookup"><span data-stu-id="f9837-221">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="f9837-222">如果失败，你可以修复程序包，然后重试。</span><span class="sxs-lookup"><span data-stu-id="f9837-222">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="f9837-223">如果成功，请继续 OOBE。</span><span class="sxs-lookup"><span data-stu-id="f9837-223">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="f9837-224">如果在 2016 年 8 月之前购买了该设备，你需要使用 Microsoft 帐户登录设备，获取最新操作系统更新，然后重置操作系统，以便应用设置包。</span><span class="sxs-lookup"><span data-stu-id="f9837-224">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

## <span data-ttu-id="f9837-225">在设置后将设置包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f9837-225">Apply a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="f9837-226">这些步骤仅适用于 Windows 10 版本 1809。</span><span class="sxs-lookup"><span data-stu-id="f9837-226">These steps apply only toWindows 10, version 1809.</span></span>

<span data-ttu-id="f9837-227">在电脑上，按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f9837-227">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="f9837-228">按照" [使用 HoloLens 向导创建为 HoloLens 创建 provisions 的包"创建预订包](hololens-provisioning.md)"。</span><span class="sxs-lookup"><span data-stu-id="f9837-228">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="f9837-229">使用 USB 电缆将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="f9837-229">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="f9837-230">HoloLens 显示为电脑上文件资源管理器中的设备。</span><span class="sxs-lookup"><span data-stu-id="f9837-230">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="f9837-231">将其首发放到 HoloLens 上的"文档"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9837-231">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="f9837-232">在 HoloLens 上，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f9837-232">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="f9837-233">转到"**设置**  >  **帐户**  >  **访问"工作或学校**帐户访问。</span><span class="sxs-lookup"><span data-stu-id="f9837-233">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="f9837-234">在 **"相关**设置" **中，选择"添加"或"移除设置包**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-234">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="f9837-235">在下一页上， **选择"添加包** "以启动文件选取器并选择你的设置包。</span><span class="sxs-lookup"><span data-stu-id="f9837-235">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="f9837-236">如果该文件夹为空，请确保选择"此 **设备"，** 然后选择" **文档**"。</span><span class="sxs-lookup"><span data-stu-id="f9837-236">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="f9837-237">在应用包后，它将显示在已安装程序 **包的列表中**。</span><span class="sxs-lookup"><span data-stu-id="f9837-237">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="f9837-238">若要查看程序包详细信息或要从设备中删除程序包，请选择列出的程序包。</span><span class="sxs-lookup"><span data-stu-id="f9837-238">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <span data-ttu-id="f9837-239">可配置的内容</span><span class="sxs-lookup"><span data-stu-id="f9837-239">What you can configure</span></span>

<span data-ttu-id="f9837-240">预配包使用配置服务提供程序 (CSP)。</span><span class="sxs-lookup"><span data-stu-id="f9837-240">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="f9837-241">如果你对 CSP 不甚了解，请参阅[针对 IT 专业人员的配置服务提供程序 (CSP) 简介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。</span><span class="sxs-lookup"><span data-stu-id="f9837-241">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="f9837-242">在 Windows 配置设计器中，当创建用于 Windows 全息版的预配包时，**可用自定义**中的设置是基于 [Windows 全息版中支持的 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="f9837-242">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="f9837-243">下表介绍了你可能想要为 HoloLens 配置的设置。</span><span class="sxs-lookup"><span data-stu-id="f9837-243">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens 的通用运行时设置](images/icd-settings.png)

| <span data-ttu-id="f9837-245">设置</span><span class="sxs-lookup"><span data-stu-id="f9837-245">Setting</span></span> | <span data-ttu-id="f9837-246">说明</span><span class="sxs-lookup"><span data-stu-id="f9837-246">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="f9837-247">证书</span><span class="sxs-lookup"><span data-stu-id="f9837-247">Certificates</span></span>** | <span data-ttu-id="f9837-248">将证书部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f9837-248">Deploy a certificate to HoloLens.</span></span>  |
| **<span data-ttu-id="f9837-249">ConnectivityProfiles</span><span class="sxs-lookup"><span data-stu-id="f9837-249">ConnectivityProfiles</span></span>** | <span data-ttu-id="f9837-250">将 WLAN 配置文件部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f9837-250">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| **<span data-ttu-id="f9837-251">EditionUpgrade</span><span class="sxs-lookup"><span data-stu-id="f9837-251">EditionUpgrade</span></span>** | [<span data-ttu-id="f9837-252">升级为 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="f9837-252">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| **<span data-ttu-id="f9837-253">策略</span><span class="sxs-lookup"><span data-stu-id="f9837-253">Policies</span></span>** | <span data-ttu-id="f9837-254">允许或阻止 HoloLens 中的开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="f9837-254">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="f9837-255">Windows Holographic for Business 支持的策略</span><span class="sxs-lookup"><span data-stu-id="f9837-255">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

> [!NOTE]
> <span data-ttu-id="f9837-256">HoloLens 当前不支持使用通过使用 (在 **UniversalAppInstall**) 来安装应用。</span><span class="sxs-lookup"><span data-stu-id="f9837-256">HoloLens does not currently support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span>
