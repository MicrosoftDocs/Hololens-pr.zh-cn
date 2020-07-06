---
title: 使用预配包（HoloLens）配置 HoloLens
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
ms.openlocfilehash: 2b34cc642aa08adf5bb875588c9e4458df0034e1
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830156"
---
# <span data-ttu-id="7c25f-103">使用预配包配置 HoloLens</span><span class="sxs-lookup"><span data-stu-id="7c25f-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="7c25f-104">[Windows 预配](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)让 it 管理员可以轻松地配置最终用户设备而无需使用图像。</span><span class="sxs-lookup"><span data-stu-id="7c25f-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="7c25f-105">Windows 配置设计器是一个用于配置图像和运行时设置的工具，这些设置随后将被内置到预配程序包中。</span><span class="sxs-lookup"><span data-stu-id="7c25f-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="7c25f-106">可在预配包中应用的一些 HoloLens 配置包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="7c25f-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="7c25f-107">[在此处](hololens1-upgrade-enterprise.md)升级到 Windows 全息版企业版</span><span class="sxs-lookup"><span data-stu-id="7c25f-107">Upgrade to Windows Holographic for Business [here](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="7c25f-108">设置本地帐户</span><span class="sxs-lookup"><span data-stu-id="7c25f-108">Set up a local account</span></span>
- <span data-ttu-id="7c25f-109">设置 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="7c25f-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="7c25f-110">将证书应用到设备</span><span class="sxs-lookup"><span data-stu-id="7c25f-110">Apply certificates to the device</span></span>
- <span data-ttu-id="7c25f-111">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="7c25f-111">Enable Developer Mode</span></span>
- <span data-ttu-id="7c25f-112">配置展台模式（可[在此处](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)找到配置展台模式的详细说明。</span><span class="sxs-lookup"><span data-stu-id="7c25f-112">Configure Kiosk mode (Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <span data-ttu-id="7c25f-113">预配程序包 HoloLens 向导</span><span class="sxs-lookup"><span data-stu-id="7c25f-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="7c25f-114">HoloLens 向导可帮助你在预配包中配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7c25f-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="7c25f-115">升级到企业版</span><span class="sxs-lookup"><span data-stu-id="7c25f-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c25f-116">这只应用于 HoloLens 第一代设备。</span><span class="sxs-lookup"><span data-stu-id="7c25f-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="7c25f-117">仅在预配包中包含 Windows 全息版的版本升级许可证或者[设备已升级到 Windows 全息版企业](hololens1-upgrade-enterprise.md)版时，才会应用预配包中的设置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="7c25f-118">配置 HoloLens 首次体验（OOBE）</span><span class="sxs-lookup"><span data-stu-id="7c25f-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="7c25f-119">配置 Wlan 网络</span><span class="sxs-lookup"><span data-stu-id="7c25f-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="7c25f-120">在 Azure Active Directory 中注册设备，或创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="7c25f-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="7c25f-121">添加证书</span><span class="sxs-lookup"><span data-stu-id="7c25f-121">Add certificates</span></span>
- <span data-ttu-id="7c25f-122">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="7c25f-122">Enable Developer Mode</span></span>
- <span data-ttu-id="7c25f-123">配置展台模式。</span><span class="sxs-lookup"><span data-stu-id="7c25f-123">Configure kiosk mode.</span></span> <span data-ttu-id="7c25f-124">（可[在此处](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)找到配置展台模式的详细说明）。</span><span class="sxs-lookup"><span data-stu-id="7c25f-124">(Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="7c25f-125">你必须在 Windows 10 上运行 Windows 配置设计器，才能使用任何向导配置 Azure Active Directory 注册。</span><span class="sxs-lookup"><span data-stu-id="7c25f-125">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="7c25f-126">预配程序包可以包括管理说明和策略、自定义网络连接和策略等。</span><span class="sxs-lookup"><span data-stu-id="7c25f-126">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="7c25f-127">使用桌面向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置、应用、策略等。</span><span class="sxs-lookup"><span data-stu-id="7c25f-127">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <span data-ttu-id="7c25f-128">创建预配程序包的步骤</span><span class="sxs-lookup"><span data-stu-id="7c25f-128">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="7c25f-129">**选项1：** [从 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-129">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="7c25f-130">这包括 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="7c25f-130">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="7c25f-131">**选项2：** [从适用于 Windows 10 的 Windows 评估和部署工具包（ADK）](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-131">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="7c25f-132">如果从 Windows ADK 安装 Windows 配置设计器，请从 "**选择要安装的功能**" 对话框中选择 "**配置设计器**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-132">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="7c25f-133">此选项不包括 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="7c25f-133">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="7c25f-134">如果你知道你将使用需要访问 Windows 配置设计器的脱机电脑，请按照[此处](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store)的脱机应用安装进行高级恢复助理，但让 Windows Confiugration Desinger 你的选择。</span><span class="sxs-lookup"><span data-stu-id="7c25f-134">If you know you will be using an offline PC that needs access to Windows Configuration Designer please follow the offline app install [here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) for Advanced Recovery Companion but making Windows Confiugration Desinger your selection instead.</span></span> 

### <span data-ttu-id="7c25f-135">2. 创建预配包</span><span class="sxs-lookup"><span data-stu-id="7c25f-135">2. Create the provisioning package</span></span>

<span data-ttu-id="7c25f-136">使用 Windows 配置设计器工具创建预配包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="7c25f-137">打开 Windows 配置设计器（默认情况下为 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe）。</span><span class="sxs-lookup"><span data-stu-id="7c25f-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="7c25f-138">选择 "**设置 HoloLens 设备**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 启动选项](images/icd-create-options-1703.png)

3. <span data-ttu-id="7c25f-140">为项目命名，然后选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="7c25f-141">阅读 "**入门**" 页面上的说明，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="7c25f-142">桌面预配的页面将引导你完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7c25f-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7c25f-143">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7c25f-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="7c25f-144">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="7c25f-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="7c25f-145">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="7c25f-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <span data-ttu-id="7c25f-146">配置设置</span><span class="sxs-lookup"><span data-stu-id="7c25f-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="7c25f-147">通过浏览找到并选择要升级 HoloLens 版本的企业许可证文件。</span><span class="sxs-lookup"><span data-stu-id="7c25f-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="7c25f-148">您也可以切换 <strong> "是" </strong> 或 " <strong> 否" </strong> 以隐藏第一个体验的各个部分。</span><span class="sxs-lookup"><span data-stu-id="7c25f-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="7c25f-149">若要设置设备而无需连接到 Wi-fi 网络，请切换 <strong> "将 wi-fi 设置跳 </strong> 到 <strong> " </strong> 。</span><span class="sxs-lookup"><span data-stu-id="7c25f-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="7c25f-150">选择将使用设备的区域和时区。</span><span class="sxs-lookup"><span data-stu-id="7c25f-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="7c25f-151">在此部分中，你可以输入设备应自动连接到的 Wi-fi 无线网络的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c25f-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="7c25f-152">若要执行此操作，请选择 " <strong> 打开 </strong> "，输入 SSID、网络类型（" <strong> 打开" 或 " </strong> <strong> WPA2-个人" </strong> ）以及（如果 <strong> WPA2-个人 </strong> ）无线网络的密码。</span><span class="sxs-lookup"><span data-stu-id="7c25f-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="7c25f-153">你可以在 Azure Active Directory 中注册设备，也可以在设备上创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="7c25f-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="7c25f-154">使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。</span><span class="sxs-lookup"><span data-stu-id="7c25f-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="7c25f-155">Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。</span><span class="sxs-lookup"><span data-stu-id="7c25f-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="7c25f-156">若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。</span><span class="sxs-lookup"><span data-stu-id="7c25f-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="7c25f-157">设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。</span><span class="sxs-lookup"><span data-stu-id="7c25f-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="7c25f-158">选择 " <strong> 获取批量令牌" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="7c25f-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="7c25f-159">在 " <strong> 让&#39;s 登录" 窗口中 </strong> ，输入有权将设备加入 Azure AD 的帐户，然后输入密码。</span><span class="sxs-lookup"><span data-stu-id="7c25f-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="7c25f-160">选择 <strong> </strong> "接受" 以向 Windows 配置设计器提供必要的权限。</span><span class="sxs-lookup"><span data-stu-id="7c25f-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="7c25f-161">若要创建本地帐户，请选择该选项，然后输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="7c25f-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="7c25f-162">重要提示：</span><span class="sxs-lookup"><span data-stu-id="7c25f-162">Important:</span></span></strong> <br /><span data-ttu-id="7c25f-163">（仅适用于 Windows 10，版本1607）如果在预配包中创建本地帐户，则必须 <strong> </strong> 每隔42天使用 "设置" 应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="7c25f-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="7c25f-164">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="7c25f-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="7c25f-165">若要使用证书预配设备，请单击<strong>添加证书</strong>。</span><span class="sxs-lookup"><span data-stu-id="7c25f-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="7c25f-166">输入证书的名称，然后浏览到要使用的证书并将其选中。</span><span class="sxs-lookup"><span data-stu-id="7c25f-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="7c25f-167">切换 <strong> "是" </strong> 或 " <strong> 否" </strong> 以在 HoloLens 上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="7c25f-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)"><span data-ttu-id="7c25f-168">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c25f-168">Learn more about Developer Mode.</span></span></a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="7c25f-169">不要设置密码来保护预配包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="7c25f-170">如果预配包受密码保护，则预配 HoloLens 设备将失败。</span><span class="sxs-lookup"><span data-stu-id="7c25f-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="7c25f-171">完成后，选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-171">After you're done, select **Create**.</span></span> <span data-ttu-id="7c25f-172">这只需几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="7c25f-172">It only takes a few seconds.</span></span> <span data-ttu-id="7c25f-173">生成该包之后，其存储位置将在页面底部显示为超链接。</span><span class="sxs-lookup"><span data-stu-id="7c25f-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <span data-ttu-id="7c25f-174">3. 使用高级预配创建 HoloLens 的预配包</span><span class="sxs-lookup"><span data-stu-id="7c25f-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="7c25f-175">在**高级预配**中创建的预配包无需包含版本升级许可证，Windows 全息版才能成功应用于 HoloLens （第1代）。</span><span class="sxs-lookup"><span data-stu-id="7c25f-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="7c25f-176">[查看有关 HoloLens 的 Windows 全息版（第1代）的更多信息](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="7c25f-177">在 Windows 配置设计器起始页上，选择**高级预配**。</span><span class="sxs-lookup"><span data-stu-id="7c25f-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="7c25f-178">在**输入项目详细信息**窗口中，指定项目的名称和项目的位置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="7c25f-179">（可选）输入简要描述以描述你的项目。</span><span class="sxs-lookup"><span data-stu-id="7c25f-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="7c25f-180">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="7c25f-180">Select **Next**.</span></span>

4. <span data-ttu-id="7c25f-181">在 "**选择要查看和配置的设置**" 窗口中，选择 " **Windows 10 全息**版"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="7c25f-182">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-182">Select **Finish**.</span></span>

6. <span data-ttu-id="7c25f-183">通过使用[本文后面所述](#what-you-can-configure)的任何设置，展开 "**运行时设置**" 并自定义程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c25f-184">（仅适用于 Windows 10，版本1607）如果在预配包中创建本地帐户，则必须每隔42天使用 "**设置**" 应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="7c25f-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="7c25f-185">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="7c25f-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="7c25f-186">如果用户帐户被锁定，则必须[执行完整设备恢复](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="7c25f-187">选择**File**"  >  **保存**文件"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="7c25f-188">阅读有关项目文件可能包含敏感信息的警告，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7c25f-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c25f-189">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7c25f-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="7c25f-190">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="7c25f-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="7c25f-191">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="7c25f-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="7c25f-192">选择 "**导出**  >  **预配包**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="7c25f-193">将**所有者**更改为**IT 管理员**。这会将此预配包的优先级设置为高于从其他源应用到此设备的预配包的优先级。</span><span class="sxs-lookup"><span data-stu-id="7c25f-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="7c25f-194">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="7c25f-194">Select **Next**.</span></span>

11. <span data-ttu-id="7c25f-195">为**程序包版本**设置一个值。</span><span class="sxs-lookup"><span data-stu-id="7c25f-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7c25f-196">你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="7c25f-197">在 "**选择预配包的安全详细信息**" 中，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7c25f-198">如果加密预配程序包，则 HoloLens 设备预配将失败。</span><span class="sxs-lookup"><span data-stu-id="7c25f-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="7c25f-199">选择 "**下一步**" 以指定在构建预配包后你希望其转到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="7c25f-200">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="7c25f-201">或者，你可以选择 "**浏览**" 以更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="7c25f-202">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="7c25f-202">Select **Next**.</span></span>

15. <span data-ttu-id="7c25f-203">选择 "**生成**" 开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="7c25f-204">项目信息会显示在构建页面中，并且进度栏会指示构建状态。</span><span class="sxs-lookup"><span data-stu-id="7c25f-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="7c25f-205">生成完成后，选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <span data-ttu-id="7c25f-206">在安装期间将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="7c25f-206">Apply a provisioning package to HoloLens during setup</span></span>

1. <span data-ttu-id="7c25f-207">使用 USB 电缆将设备连接到电脑，然后启动设备。</span><span class="sxs-lookup"><span data-stu-id="7c25f-207">Use the USB cable to connect the device to a PC, and then start the device.</span></span> <span data-ttu-id="7c25f-208">不要在 OOBE 的**第一交互时刻的一**页之前继续。</span><span class="sxs-lookup"><span data-stu-id="7c25f-208">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="7c25f-209">在 HoloLens （第1代）上，此页面包含一个蓝色框。</span><span class="sxs-lookup"><span data-stu-id="7c25f-209">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="7c25f-210">在 HoloLens 2 上，此页面包含 hummingbird。</span><span class="sxs-lookup"><span data-stu-id="7c25f-210">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="7c25f-211">短暂地同时按下**调低音量**和**电源**按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="7c25f-211">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="7c25f-212">HoloLens 在电脑上的文件资源管理器中显示为设备。</span><span class="sxs-lookup"><span data-stu-id="7c25f-212">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="7c25f-213">在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。</span><span class="sxs-lookup"><span data-stu-id="7c25f-213">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="7c25f-214">在**调整**页中，再次短暂地同时按下**调低音量**和**电源**按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="7c25f-214">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>

6. <span data-ttu-id="7c25f-215">设备会询问你是否信任程序包并希望应用它。</span><span class="sxs-lookup"><span data-stu-id="7c25f-215">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="7c25f-216">确认你信任程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-216">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="7c25f-217">你将看到是否成功应用了程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-217">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="7c25f-218">如果失败，你可以修复程序包，然后重试。</span><span class="sxs-lookup"><span data-stu-id="7c25f-218">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="7c25f-219">如果成功，请继续 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7c25f-219">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="7c25f-220">如果在2016年8月之前购买了该设备，你需要使用 Microsoft 帐户登录到该设备，获取最新的操作系统更新，然后重置操作系统，以便应用预配包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-220">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

### <span data-ttu-id="7c25f-221">4. 安装后将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="7c25f-221">4. Apply a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="7c25f-222">这些步骤仅适用于 toWindows 10 版本1809。</span><span class="sxs-lookup"><span data-stu-id="7c25f-222">These steps apply only toWindows 10, version 1809.</span></span>

<span data-ttu-id="7c25f-223">在你的电脑上，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7c25f-223">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="7c25f-224">按照[使用 hololens 向导创建 HoloLens 的预配包](hololens-provisioning.md)中所述，创建预配包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-224">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="7c25f-225">使用 USB 电缆将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="7c25f-225">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="7c25f-226">HoloLens 在电脑上的文件资源管理器中显示为设备。</span><span class="sxs-lookup"><span data-stu-id="7c25f-226">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="7c25f-227">将预配包拖放到 HoloLens 上的 "文档" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7c25f-227">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="7c25f-228">在 HoloLens 中，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7c25f-228">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="7c25f-229">转到 "**设置**"  >  **帐户**  >  **访问工作或学校**。</span><span class="sxs-lookup"><span data-stu-id="7c25f-229">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="7c25f-230">在 "**相关设置**" 中，选择 "**添加或删除预配包**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-230">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="7c25f-231">在下一页上，选择 "**添加程序包**" 以启动 "文件选取器"，然后选择预配包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-231">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="7c25f-232">如果文件夹为空，请确保选择 "**此设备**"，然后选择 "**文档**"。</span><span class="sxs-lookup"><span data-stu-id="7c25f-232">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="7c25f-233">应用程序包后，它将显示在**已安装程序包**的列表中。</span><span class="sxs-lookup"><span data-stu-id="7c25f-233">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="7c25f-234">若要查看程序包详细信息或从设备中删除程序包，请选择列出的程序包。</span><span class="sxs-lookup"><span data-stu-id="7c25f-234">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <span data-ttu-id="7c25f-235">可配置的内容</span><span class="sxs-lookup"><span data-stu-id="7c25f-235">What you can configure</span></span>

<span data-ttu-id="7c25f-236">预配包使用配置服务提供程序 (CSP)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-236">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="7c25f-237">如果你对 CSP 不甚了解，请参阅[针对 IT 专业人员的配置服务提供程序 (CSP) 简介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-237">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="7c25f-238">在 Windows 配置设计器中，当创建用于 Windows 全息版的预配包时，**可用自定义**中的设置是基于 [Windows 全息版中支持的 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="7c25f-238">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="7c25f-239">下表介绍了你可能想要为 HoloLens 配置的设置。</span><span class="sxs-lookup"><span data-stu-id="7c25f-239">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens 的通用运行时设置](images/icd-settings.png)

| <span data-ttu-id="7c25f-241">设置</span><span class="sxs-lookup"><span data-stu-id="7c25f-241">Setting</span></span> | <span data-ttu-id="7c25f-242">说明</span><span class="sxs-lookup"><span data-stu-id="7c25f-242">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="7c25f-243">证书</span><span class="sxs-lookup"><span data-stu-id="7c25f-243">Certificates</span></span>** | <span data-ttu-id="7c25f-244">将证书部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7c25f-244">Deploy a certificate to HoloLens.</span></span>  |
| **<span data-ttu-id="7c25f-245">ConnectivityProfiles</span><span class="sxs-lookup"><span data-stu-id="7c25f-245">ConnectivityProfiles</span></span>** | <span data-ttu-id="7c25f-246">将 WLAN 配置文件部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7c25f-246">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| **<span data-ttu-id="7c25f-247">EditionUpgrade</span><span class="sxs-lookup"><span data-stu-id="7c25f-247">EditionUpgrade</span></span>** | [<span data-ttu-id="7c25f-248">升级为 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="7c25f-248">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| **<span data-ttu-id="7c25f-249">策略</span><span class="sxs-lookup"><span data-stu-id="7c25f-249">Policies</span></span>** | <span data-ttu-id="7c25f-250">允许或阻止 HoloLens 中的开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="7c25f-250">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="7c25f-251">Windows Holographic for Business 支持的策略</span><span class="sxs-lookup"><span data-stu-id="7c25f-251">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

> [!NOTE]
> <span data-ttu-id="7c25f-252">HoloLens 当前不支持通过使用预配包来安装应用（**UniversalAppInstall**）。</span><span class="sxs-lookup"><span data-stu-id="7c25f-252">HoloLens does not currently support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span>