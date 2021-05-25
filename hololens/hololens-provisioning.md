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
ms.openlocfilehash: cf2abe249e40e522b4d8993449b9f19033a64744
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397398"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a><span data-ttu-id="9f930-103">使用预配包配置 HoloLens</span><span class="sxs-lookup"><span data-stu-id="9f930-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="9f930-104">[Windows 预配](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 使 it 管理员可以轻松地配置最终用户设备，而无需进行图像处理。</span><span class="sxs-lookup"><span data-stu-id="9f930-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="9f930-105">Windows 配置设计器是一种用于配置映像和运行时设置的工具，这些设置随后会内置到预配包中。</span><span class="sxs-lookup"><span data-stu-id="9f930-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="9f930-106">可在预配包中应用的某些 HoloLens 配置包括：</span><span class="sxs-lookup"><span data-stu-id="9f930-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="9f930-107">升级到[Windows 全息企业](hololens1-upgrade-enterprise.md)版</span><span class="sxs-lookup"><span data-stu-id="9f930-107">Upgrade to [Windows Holographic for Business](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="9f930-108">设置本地帐户</span><span class="sxs-lookup"><span data-stu-id="9f930-108">Set up a local account</span></span>
- <span data-ttu-id="9f930-109">设置 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="9f930-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="9f930-110">将证书应用到设备</span><span class="sxs-lookup"><span data-stu-id="9f930-110">Apply certificates to the device</span></span>
- <span data-ttu-id="9f930-111">启用“开发人员模式”</span><span class="sxs-lookup"><span data-stu-id="9f930-111">Enable Developer Mode</span></span>
- <span data-ttu-id="9f930-112">按照我们的 [详细说明](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)配置展台模式。</span><span class="sxs-lookup"><span data-stu-id="9f930-112">Configure Kiosk mode by following our [detailed instructions](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <a name="provisioning-package-hololens-wizard"></a><span data-ttu-id="9f930-113">设置包 HoloLens 向导</span><span class="sxs-lookup"><span data-stu-id="9f930-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="9f930-114">HoloLens 向导帮助你在预配包中配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="9f930-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="9f930-115">升级到 enterprise edition</span><span class="sxs-lookup"><span data-stu-id="9f930-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f930-116">这仅适用于 HoloLens 第一代设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="9f930-117">仅当预配包包含适用于 Windows 全息版的 Windows 全息版或 [设备已升级到 Windows 全息版企业](hololens1-upgrade-enterprise.md)版时，才应用设置包中的设置。</span><span class="sxs-lookup"><span data-stu-id="9f930-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="9f930-118">配置 HoloLens first experience (OOBE) </span><span class="sxs-lookup"><span data-stu-id="9f930-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="9f930-119">配置 Wi-Fi 网络</span><span class="sxs-lookup"><span data-stu-id="9f930-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="9f930-120">在 Azure Active Directory 中注册设备，或创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="9f930-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="9f930-121">添加证书</span><span class="sxs-lookup"><span data-stu-id="9f930-121">Add certificates</span></span>
- <span data-ttu-id="9f930-122">启用“开发人员模式”</span><span class="sxs-lookup"><span data-stu-id="9f930-122">Enable Developer Mode</span></span>
- <span data-ttu-id="9f930-123">按照) [详细说明](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置展台模式。</span><span class="sxs-lookup"><span data-stu-id="9f930-123">Configure kiosk mode by following out [detailed instructions](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="9f930-124">你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。</span><span class="sxs-lookup"><span data-stu-id="9f930-124">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="9f930-125">预配包可以包括管理说明和策略、自定义网络连接和策略等。</span><span class="sxs-lookup"><span data-stu-id="9f930-125">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="9f930-126">使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。</span><span class="sxs-lookup"><span data-stu-id="9f930-126">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <a name="steps-for-creating-provisioning-packages"></a><span data-ttu-id="9f930-127">创建预配包的步骤</span><span class="sxs-lookup"><span data-stu-id="9f930-127">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="9f930-128">**选项1：** [从 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="9f930-128">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="9f930-129">这包括HoloLens 2功能。</span><span class="sxs-lookup"><span data-stu-id="9f930-129">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="9f930-130">**选项 2：** 从 Windows 评估和部署工具包 (适用于) [的 ADK Windows 10。](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)</span><span class="sxs-lookup"><span data-stu-id="9f930-130">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="9f930-131">如果从 Windows ADK 安装 Windows 配置设计器，请从"选择要安装的功能"对话框中选择 **"配置** 设计器"。</span><span class="sxs-lookup"><span data-stu-id="9f930-131">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="9f930-132">此选项不包括HoloLens 2功能。</span><span class="sxs-lookup"><span data-stu-id="9f930-132">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="9f930-133">如果知道你将使用需要访问 Windows 配置设计器的脱机电脑，请按照高级恢复助手的 [脱机应用安装 (https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="9f930-133">If you know you'll be using an offline PC that needs access to Windows Configuration Designer, follow the [offline app install(https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) instructions for Advanced Recovery Companion.</span></span> <span data-ttu-id="9f930-134">选择"Windows 配置设计器"。</span><span class="sxs-lookup"><span data-stu-id="9f930-134">Make Windows Configuration Designer your selection.</span></span> 

### <a name="2-create-the-provisioning-package"></a><span data-ttu-id="9f930-135">2.创建预配包</span><span class="sxs-lookup"><span data-stu-id="9f930-135">2. Create the provisioning package</span></span>

<span data-ttu-id="9f930-136">使用 Windows 配置设计器工具创建预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="9f930-137">打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。</span><span class="sxs-lookup"><span data-stu-id="9f930-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="9f930-138">选择 **"预配 HoloLens 设备"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. <span data-ttu-id="9f930-140">将项目命名，然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="9f930-141">阅读"入门"**页上的说明，然后选择**"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="9f930-142">桌面预配页面将演练以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9f930-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9f930-143">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="9f930-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="9f930-144">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="9f930-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="9f930-145">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="9f930-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <a name="configure-settings"></a><span data-ttu-id="9f930-146">配置设置</span><span class="sxs-lookup"><span data-stu-id="9f930-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="9f930-147">浏览到并选择企业许可证文件以升级 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="9f930-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="9f930-148">还可以 <strong>切换"是</strong> "或" <strong>否</strong> "来隐藏第一个体验的某些部分。</span><span class="sxs-lookup"><span data-stu-id="9f930-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="9f930-149">若要设置设备而无需连接到 Wi-Fi，请将"跳过Wi-Fi<strong>设置为</strong><strong>"打开"。</strong></span><span class="sxs-lookup"><span data-stu-id="9f930-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="9f930-150">选择将在其中使用设备的区域与时区。</span><span class="sxs-lookup"><span data-stu-id="9f930-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="9f930-151">在本部分，可以输入设备Wi-Fi应连接到的无线网络的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9f930-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="9f930-152">为此，请选择"开<strong></strong>"，输入 SSID、网络类型 (<strong>Open</strong>或<strong>WPA2-Personal</strong>) ，如果<strong>WPA2-Personal</strong>) 无线网络的密码，则输入 (。</span><span class="sxs-lookup"><span data-stu-id="9f930-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="9f930-153">可以在设备上注册Azure Active Directory，或在设备上创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="9f930-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="9f930-154">使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。</span><span class="sxs-lookup"><span data-stu-id="9f930-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="9f930-155">Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。</span><span class="sxs-lookup"><span data-stu-id="9f930-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="9f930-156">若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。</span><span class="sxs-lookup"><span data-stu-id="9f930-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="9f930-157">设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。</span><span class="sxs-lookup"><span data-stu-id="9f930-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="9f930-158">选择<strong>"获取批量令牌"。</strong></span><span class="sxs-lookup"><span data-stu-id="9f930-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="9f930-159">在 <strong>"&#39;</strong> 登录"窗口中，输入有权将设备加入 Azure AD的帐户，然后输入密码。</span><span class="sxs-lookup"><span data-stu-id="9f930-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="9f930-160">选择 " <strong>接受</strong> "，为 Windows 配置设计器指定必需的权限。</span><span class="sxs-lookup"><span data-stu-id="9f930-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="9f930-161">若要创建本地帐户，请选择该选项，并输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="9f930-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><span data-ttu-id="9f930-162"><strong>无关紧要</strong> </span><span class="sxs-lookup"><span data-stu-id="9f930-162"><strong>Important:</strong> </span></span><br /><span data-ttu-id="9f930-163"> (适用于 Windows 10，版本1607仅) 如果在预配包中创建本地帐户，则必须每42天使用 " <strong>设置</strong> " 应用程序更改密码。</span><span class="sxs-lookup"><span data-stu-id="9f930-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="9f930-164">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="9f930-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="9f930-165">若要使用证书预配设备，请单击<strong>添加证书</strong>。</span><span class="sxs-lookup"><span data-stu-id="9f930-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="9f930-166">输入证书的名称，然后浏览到要使用的证书并将其选中。</span><span class="sxs-lookup"><span data-stu-id="9f930-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="9f930-167">切换 <strong>"是" 或 "</strong> <strong>否</strong> " 以在 HoloLens 上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="9f930-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <span data-ttu-id="9f930-168"><a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">了解有关开发人员模式的详细信息。</a></span><span class="sxs-lookup"><span data-stu-id="9f930-168"><a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Learn more about Developer Mode.</a></span></span></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br><span data-ttu-id="9f930-169">不要设置密码来保护预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="9f930-170">如果预配包受密码保护，预配 HoloLens 设备将失败。</span><span class="sxs-lookup"><span data-stu-id="9f930-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="9f930-171">完成后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="9f930-171">After you're done, select **Create**.</span></span> <span data-ttu-id="9f930-172">这只需几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="9f930-172">It only takes a few seconds.</span></span> <span data-ttu-id="9f930-173">生成该包之后，其存储位置将在页面底部显示为超链接。</span><span class="sxs-lookup"><span data-stu-id="9f930-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a><span data-ttu-id="9f930-174">3. 使用高级设置为 HoloLens 创建预配包</span><span class="sxs-lookup"><span data-stu-id="9f930-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="9f930-175">在 **高级设置** 中创建的预配包无需包含版本升级许可证，Windows 全息 for Business 即可成功应用于 HoloLens (第一代) 。</span><span class="sxs-lookup"><span data-stu-id="9f930-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="9f930-176">有关[HoloLens (第一代) ，请参阅 Windows 全息 For Business 上的详细信息](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="9f930-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="9f930-177">在 Windows 配置设计器起始页上，选择 **高级预配**。</span><span class="sxs-lookup"><span data-stu-id="9f930-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="9f930-178">在 **输入项目详细信息** 窗口中，指定项目的名称和项目的位置。</span><span class="sxs-lookup"><span data-stu-id="9f930-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="9f930-179">（可选）输入简要描述以描述你的项目。</span><span class="sxs-lookup"><span data-stu-id="9f930-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="9f930-180">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="9f930-180">Select **Next**.</span></span>

4. <span data-ttu-id="9f930-181">在 " **选择要查看和配置的设置** " 窗口中，选择 " **Windows 10 全息** 版"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9f930-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="9f930-182">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="9f930-182">Select **Finish**.</span></span>

6. <span data-ttu-id="9f930-183">展开 " **运行时设置** "，然后使用 [本文后面所述](#what-you-can-configure)的任何设置自定义包。</span><span class="sxs-lookup"><span data-stu-id="9f930-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9f930-184"> (适用于 Windows 10，版本1607仅) 如果在预配包中创建本地帐户，则必须每42天使用 " **设置** " 应用程序更改密码。</span><span class="sxs-lookup"><span data-stu-id="9f930-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="9f930-185">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="9f930-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="9f930-186">如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。</span><span class="sxs-lookup"><span data-stu-id="9f930-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="9f930-187">选择“文件” > “保存”。</span><span class="sxs-lookup"><span data-stu-id="9f930-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="9f930-188">阅读警告：项目文件可能包含敏感信息，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9f930-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9f930-189">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="9f930-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="9f930-190">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="9f930-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="9f930-191">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="9f930-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="9f930-192">选择 "**导出**  >  **设置包**"。</span><span class="sxs-lookup"><span data-stu-id="9f930-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="9f930-193">将 **所有者** 更改为 **IT 管理员**。这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="9f930-194">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="9f930-194">Select **Next**.</span></span>

11. <span data-ttu-id="9f930-195">为“程序包版本”设置一个值。</span><span class="sxs-lookup"><span data-stu-id="9f930-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9f930-196">你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="9f930-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="9f930-197">在 " **选择预配包的安全详细信息**" 中，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9f930-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="9f930-198">如果加密预配程序包，则 HoloLens 设备预配将失败。</span><span class="sxs-lookup"><span data-stu-id="9f930-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="9f930-199">选择 " **下一步** " 以指定在生成预配包后要将其移到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="9f930-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="9f930-200">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="9f930-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="9f930-201">（可选）可以选择" **浏览"** 以更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="9f930-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="9f930-202">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="9f930-202">Select **Next**.</span></span>

15. <span data-ttu-id="9f930-203">选择 **"生成** "以开始生成包。</span><span class="sxs-lookup"><span data-stu-id="9f930-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="9f930-204">项目信息会显示在构建页面中，并且进度栏会指示构建状态。</span><span class="sxs-lookup"><span data-stu-id="9f930-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="9f930-205">生成完成后，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a><span data-ttu-id="9f930-206">在安装过程中将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="9f930-206">Apply a provisioning package to HoloLens during setup</span></span>

<span data-ttu-id="9f930-207">HoloLens 2 Windows Holographic 版本 2004 或内部 [版本 19041.1103 或](hololens-release-notes.md#windows-holographic-version-2004) 更高版本上的设备，可以使用 USB 驱动器应用预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-207">HoloLens 2 devices on Windows Holographic, version 2004 or build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) or later, may use a USB drive to apply a provisioning package.</span></span> <span data-ttu-id="9f930-208">只需将 .ppkg 文件复制到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="9f930-208">Simply copy the .ppkg file to the root of the USB drive.</span></span> <span data-ttu-id="9f930-209">只有在 USB 驱动器的根目录下，才应用预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-209">Provisioning packages will only be applied if they’re in the root of the USB drive.</span></span> <span data-ttu-id="9f930-210">将按顺序应用多个预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-210">Multiple provisioning package present will be applied sequentially.</span></span>

<span data-ttu-id="9f930-211">HoloLens 2 [Windows Holographic 版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更高版本上的设备具有较新的功能，可帮助简化和简化此过程，使其自动执行。</span><span class="sxs-lookup"><span data-stu-id="9f930-211">HoloLens 2 devices on [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or later have newer features to help streamline and simplify this process making it automatic.</span></span> <span data-ttu-id="9f930-212">请查看以下部分：</span><span class="sxs-lookup"><span data-stu-id="9f930-212">Please review the following sections:</span></span>

- [<span data-ttu-id="9f930-213">从 USB 自动启动预配</span><span class="sxs-lookup"><span data-stu-id="9f930-213">Auto-launch provisioning from USB</span></span>](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [<span data-ttu-id="9f930-214">在 OOBE 中自动确认预配包</span><span class="sxs-lookup"><span data-stu-id="9f930-214">Auto-confirm provisioning packages in OOBE</span></span>](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [<span data-ttu-id="9f930-215">无需使用 UI 即可自动预配</span><span class="sxs-lookup"><span data-stu-id="9f930-215">Automatic provisioning without using UI</span></span>](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. <span data-ttu-id="9f930-216">使用 USB 电缆将设备连接到 PC (或 USB 驱动器，HoloLens 2上述) ，然后启动设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-216">Use the USB cable to connect the device to a PC (or USB drive for HoloLens 2 as mentioned above), and then start the device.</span></span> <span data-ttu-id="9f930-217">不要继续超过 OOBE 的第一个 **可** 交互时刻页。</span><span class="sxs-lookup"><span data-stu-id="9f930-217">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="9f930-218">在 HoloLens (第一代) 上，此页面包含一个蓝色框。</span><span class="sxs-lookup"><span data-stu-id="9f930-218">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="9f930-219">在HoloLens 2，此页包含"花鸟"。</span><span class="sxs-lookup"><span data-stu-id="9f930-219">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="9f930-220">短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="9f930-220">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="9f930-221">HoloLens 在电脑上文件资源管理器设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-221">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="9f930-222">在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。</span><span class="sxs-lookup"><span data-stu-id="9f930-222">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="9f930-223">在 OOBE 的"第一个可交互时刻"页上，再次短暂按下并松开"音量降低"和"电源"按钮。 </span><span class="sxs-lookup"><span data-stu-id="9f930-223">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **First interactable moment** page of OOBE.</span></span>

6. <span data-ttu-id="9f930-224">设备会询问你是否信任该包，并想应用它。</span><span class="sxs-lookup"><span data-stu-id="9f930-224">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="9f930-225">确认你信任程序包。</span><span class="sxs-lookup"><span data-stu-id="9f930-225">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="9f930-226">你将看到是否成功应用了程序包。</span><span class="sxs-lookup"><span data-stu-id="9f930-226">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="9f930-227">如果失败，你可以修复程序包，然后重试。</span><span class="sxs-lookup"><span data-stu-id="9f930-227">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="9f930-228">如果成功，请继续 OOBE。</span><span class="sxs-lookup"><span data-stu-id="9f930-228">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="9f930-229">如果设备是在2016年8月之前购买的，则需要使用 Microsoft 帐户登录到设备，获取最新的操作系统更新，然后重置操作系统，以便应用预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-229">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

### <a name="auto-launch-provisioning-from-usb"></a><span data-ttu-id="9f930-230">从 USB 自动启动设置</span><span class="sxs-lookup"><span data-stu-id="9f930-230">Auto-launch provisioning from USB</span></span>

- <span data-ttu-id="9f930-231">在 OOBE 期间使用带有预配包的 USB 驱动器时，可通过自动化过程来减少用户交互。</span><span class="sxs-lookup"><span data-stu-id="9f930-231">Automated processes allowing for less user interaction, when USB Drives with Provisioning Packages are used during OOBE.</span></span>

<span data-ttu-id="9f930-232">在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，才能使用按钮组合进行设置。</span><span class="sxs-lookup"><span data-stu-id="9f930-232">Before this release users had to launch the provisioning screen manually during OOBE to provision using a button combination.</span></span> <span data-ttu-id="9f930-233">现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。</span><span class="sxs-lookup"><span data-stu-id="9f930-233">Now users can skip the button combination, by using a Provisioning Package on a USB storage drive.</span></span> 

1. <span data-ttu-id="9f930-234">在 OOBE 的第一次种不可交互时插入带有预配包的 USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="9f930-234">Plug in the USB drive with the provisioning package during OOBE’s first interactable moment</span></span>
1. <span data-ttu-id="9f930-235">当设备准备好进行预配时，将自动在 "设置" 页中打开提示。</span><span class="sxs-lookup"><span data-stu-id="9f930-235">When the device is ready to be provisioned it will automatically open the prompt with the provisioning page.</span></span> 

<span data-ttu-id="9f930-236">注意：如果在设备启动时，会将 USB 驱动器插入，则 OOBE 会枚举现有 USB 存储设备，并监视其他设备是否已插入。</span><span class="sxs-lookup"><span data-stu-id="9f930-236">Note: If a USB drive is left plugged in while the device is booting then OOBE will enumerate existing USB storage device, as well as watch for additional ones being plugged in.</span></span>

<span data-ttu-id="9f930-237">了解如何在 [OOBE 期间应用预配包](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="9f930-237">Read up on [applying provisioning packages during OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

### <a name="auto-confirm-provisioning-packages-in-oobe"></a><span data-ttu-id="9f930-238">自动确认在 OOBE 中预配包</span><span class="sxs-lookup"><span data-stu-id="9f930-238">Auto-confirm provisioning packages in OOBE</span></span>
- <span data-ttu-id="9f930-239">自动进程允许进行更少的用户交互，当 "预配包" 页面显示时，它将自动应用列出的所有包。</span><span class="sxs-lookup"><span data-stu-id="9f930-239">Automated process allowing for less user interaction, when the Provisioning Package page is displayed it will automatically apply all packages listed.</span></span>

<span data-ttu-id="9f930-240">当设置主屏幕出现时，OOBE 将在10秒内计数，然后自动开始应用所有预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-240">When the provisioning main screen comes up, OOBE will count down 10 seconds before automatically starting applying all provisioning packages.</span></span> <span data-ttu-id="9f930-241">验证所需的包后，用户仍可以在此10秒内确认或取消。</span><span class="sxs-lookup"><span data-stu-id="9f930-241">Users can still confirm or cancel within this 10 seconds after verifying the packages they expected.</span></span>

### <a name="automatic-provisioning-without-using-ui"></a><span data-ttu-id="9f930-242">无需使用 UI 即可自动预配</span><span class="sxs-lookup"><span data-stu-id="9f930-242">Automatic provisioning without using UI</span></span>
- <span data-ttu-id="9f930-243">合并了自动过程，减少了设置的设备交互。</span><span class="sxs-lookup"><span data-stu-id="9f930-243">Combined automatic processes for reduced device interactions for provisioning.</span></span> 

<span data-ttu-id="9f930-244">通过将预配的自动启动和预配包的自动启动结合起来，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至还可以戴上设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-244">By combining the auto-launch of provisioning from USB devices and the auto-confirmation of provisioning packages, a user can provision HoloLens 2 devices automatically without using the device's UI or even wearing the device.</span></span> <span data-ttu-id="9f930-245">你可以继续为多个设备使用相同的 USB 驱动器和预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-245">You may continue to use the same USB drive and provisioning package for multiple devices.</span></span> <span data-ttu-id="9f930-246">这适用于同一区域中同时部署多个设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-246">This is useful for deploying multiple devices at once in the same area.</span></span> 

1. <span data-ttu-id="9f930-247">[使用 Windows 配置设计器 创建](hololens-provisioning.md)[预配包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。</span><span class="sxs-lookup"><span data-stu-id="9f930-247">[Create a Provisioning Package](hololens-provisioning.md) using [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22).</span></span> 
1. <span data-ttu-id="9f930-248">将包复制到 USB 存储驱动器。</span><span class="sxs-lookup"><span data-stu-id="9f930-248">Copy the package to a USB storage drive.</span></span>
1. <span data-ttu-id="9f930-249">[将HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions)刷新到[19041.1361 或更高版本。](https://aka.ms/hololens2previewdownload)</span><span class="sxs-lookup"><span data-stu-id="9f930-249">[Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload).</span></span> 
1. <span data-ttu-id="9f930-250">高级 [恢复助手](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成刷用设备后，拔下 USB-C 电缆。</span><span class="sxs-lookup"><span data-stu-id="9f930-250">When [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) has completed flashing your device unplug your USB-C cable.</span></span> 
1. <span data-ttu-id="9f930-251">将 USB 驱动器插入设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-251">Plug in your USB drive to the device.</span></span>
1. <span data-ttu-id="9f930-252">当HoloLens 2设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包并启动预配页。</span><span class="sxs-lookup"><span data-stu-id="9f930-252">When the HoloLens 2 device boots into OOBE it will automatically detect the provisioning package on the USB drive and launch the provisioning page.</span></span>
1. <span data-ttu-id="9f930-253">10 秒后，设备将自动应用预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-253">After 10 seconds the device will automatically apply the provisioning package.</span></span> 

<span data-ttu-id="9f930-254">设备现已配置，将显示"预配成功"屏幕。</span><span class="sxs-lookup"><span data-stu-id="9f930-254">Your device is now configured and will display the Provisioning Successful screen.</span></span>

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a><span data-ttu-id="9f930-255">设置后将预配包应用/删除到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="9f930-255">Apply/Remove a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="9f930-256">这些步骤适用于 Windows Holographic HoloLens 2版本 1809 (上的所有) 设备以及 HoloLens) 第一代设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-256">These steps apply to all HoloLens 2 devices and HoloLens (1st gen) devices on Windows Holographic, version 1809 and above.</span></span>

<span data-ttu-id="9f930-257">在电脑上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9f930-257">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="9f930-258">根据使用 HoloLens 向导 为 [HoloLens](hololens-provisioning.md)创建预配包中所述创建预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-258">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="9f930-259">使用 USB 电缆将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="9f930-259">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="9f930-260">HoloLens 在电脑上文件资源管理器设备。</span><span class="sxs-lookup"><span data-stu-id="9f930-260">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="9f930-261">将预配包拖放到 HoloLens 上的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9f930-261">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="9f930-262">在 HoloLens 上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9f930-262">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="9f930-263">转至“设置”   > “帐户”   > “访问工作或学校”  。</span><span class="sxs-lookup"><span data-stu-id="9f930-263">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="9f930-264">在 **"相关设置"** 中 **，选择"添加或删除预配包"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-264">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="9f930-265">下一页上，选择 **"添加包** "以启动文件选取器并选择预配包。</span><span class="sxs-lookup"><span data-stu-id="9f930-265">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="9f930-266">如果文件夹为空，请确保选择"此 **设备"，** 然后选择"文档 **"。**</span><span class="sxs-lookup"><span data-stu-id="9f930-266">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="9f930-267">应用包后，它会显示在"已安装的包 **"列表中**。</span><span class="sxs-lookup"><span data-stu-id="9f930-267">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="9f930-268">若要查看包详细信息或从设备中删除包，请选择列出的包。</span><span class="sxs-lookup"><span data-stu-id="9f930-268">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <a name="what-you-can-configure"></a><span data-ttu-id="9f930-269">可配置项</span><span class="sxs-lookup"><span data-stu-id="9f930-269">What you can configure</span></span>

<span data-ttu-id="9f930-270">预配包使用配置服务提供程序 (CSP)。</span><span class="sxs-lookup"><span data-stu-id="9f930-270">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="9f930-271">如果你对 CSP 不甚了解，请参阅[针对 IT 专业人员的配置服务提供程序 (CSP) 简介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。</span><span class="sxs-lookup"><span data-stu-id="9f930-271">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="9f930-272">在 Windows 配置设计器中，当创建用于 Windows 全息版的预配包时，**可用自定义** 中的设置是基于 [Windows 全息版中支持的 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="9f930-272">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="9f930-273">下表介绍了你可能想要为 HoloLens 配置的设置。</span><span class="sxs-lookup"><span data-stu-id="9f930-273">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens 的通用运行时设置](images/icd-settings.png)

| <span data-ttu-id="9f930-275">设置</span><span class="sxs-lookup"><span data-stu-id="9f930-275">Setting</span></span> | <span data-ttu-id="9f930-276">说明</span><span class="sxs-lookup"><span data-stu-id="9f930-276">Description</span></span> |
| --- | --- |
| <span data-ttu-id="9f930-277">**Certificates**</span><span class="sxs-lookup"><span data-stu-id="9f930-277">**Certificates**</span></span> | <span data-ttu-id="9f930-278">将证书部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="9f930-278">Deploy a certificate to HoloLens.</span></span>  |
| <span data-ttu-id="9f930-279">**ConnectivityProfiles**</span><span class="sxs-lookup"><span data-stu-id="9f930-279">**ConnectivityProfiles**</span></span> | <span data-ttu-id="9f930-280">将 WLAN 配置文件部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="9f930-280">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| <span data-ttu-id="9f930-281">**EditionUpgrade**</span><span class="sxs-lookup"><span data-stu-id="9f930-281">**EditionUpgrade**</span></span> | [<span data-ttu-id="9f930-282">升级到 Windows 全息版企业版。</span><span class="sxs-lookup"><span data-stu-id="9f930-282">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| <span data-ttu-id="9f930-283">**策略**</span><span class="sxs-lookup"><span data-stu-id="9f930-283">**Policies**</span></span> | <span data-ttu-id="9f930-284">允许或阻止 HoloLens 中的开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="9f930-284">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="9f930-285">Windows Holographic for Business 支持的策略</span><span class="sxs-lookup"><span data-stu-id="9f930-285">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a><span data-ttu-id="9f930-286">通过预配包安装应用</span><span class="sxs-lookup"><span data-stu-id="9f930-286">App install via Provisioning Package</span></span>

<span data-ttu-id="9f930-287">可以通过在 HoloLens 2 设备上通过预配包安装应用。</span><span class="sxs-lookup"><span data-stu-id="9f930-287">Apps can be installed via provisioning packages on HoloLens 2 devices.</span></span> <span data-ttu-id="9f930-288">这样就可以轻松地重复使用包，你可以使用它来帮助你分发应用程序。</span><span class="sxs-lookup"><span data-stu-id="9f930-288">This allows for an easily re-useable package you can use to help you distribute your apps.</span></span> <span data-ttu-id="9f930-289">阅读有关 [通过预配包部署应用](app-deploy-provisioning-package.md)的完整说明。</span><span class="sxs-lookup"><span data-stu-id="9f930-289">Read the full instructions for [deploying apps via Provisioning Packages](app-deploy-provisioning-package.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="9f930-290">HoloLens (第一代) 支持通过使用预配包在 **UniversalAppInstall**)  (安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="9f930-290">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="9f930-291">HoloLens (第一代) 设备仅支持在 OOBE 期间仅通过 PPKG 安装应用，并且仅支持使用用户上下文安装进行安装。</span><span class="sxs-lookup"><span data-stu-id="9f930-291">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>
