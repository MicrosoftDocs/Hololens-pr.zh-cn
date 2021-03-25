---
title: 部署指南 - 企业连接的 HoloLens 2 与 Dynamics 365 指南 - 部署
description: 了解如何使用 Dynamics 365 指南通过企业连接网络设置 HoloLens 2 设备的部署。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448517"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="5bdc8-104">部署 - 企业连接指南</span><span class="sxs-lookup"><span data-stu-id="5bdc8-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="5bdc8-105">每个部署的一个重要部分是确保在自己测试部署之前正确设置部署，以确保最终用户获得流畅的体验。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="5bdc8-106">由于我们要通过 MDM 部署 Wi-Fi 证书，因此，我们首先需要设置 HoloLens，并注册开放 Wi-Fi 网络或不需要证书的网络上的设备。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="5bdc8-107">HoloLens 完成 OOBE 和注册后，设备将收到之前配置的网络证书和 LOB，并且我们能够验证设备是否收到这两者。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="5bdc8-108">之后，你将能够确认可以创作和操作测试指南。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="5bdc8-109">注册验证</span><span class="sxs-lookup"><span data-stu-id="5bdc8-109">Enrollment Validation</span></span>

<span data-ttu-id="5bdc8-110">现在，已针对 Azure AD 和 MDM 注册正确配置了一切，其余部分现在应该可以贴靠了。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="5bdc8-111">你将需要连接Wi-Fi HoloLens 设备，以及之前配置的 Azure AD 用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="5bdc8-112">如果你的设备当前未处于出厂设置状态，那么现在应该重新[调整设备。](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="5bdc8-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="5bdc8-113">设备进入 OOBE 后，你需要开始交互并遵循提示。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="5bdc8-114">连接到无需Wi-Fi加入 WLAN 的开放网络。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="5bdc8-115">这将允许设备下载证书，以在初始设置后Wi-Fi组织证书。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="5bdc8-116">当系统询问"谁拥有此 **HoloLens"时，将看到关键提示？**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="5bdc8-117">选择 **我的工作或学校拥有它** ，然后输入你的 Azure AD 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="5bdc8-118">注册成功后，系统将提示你设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="5bdc8-119">此 PIN 对于此用户是此设备所特有的。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="5bdc8-120">系统还会提示你输入虹膜扫描、语音数据和遥测设置，最后，你将能够了解如何打开开始菜单并完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="5bdc8-121">进入混合现实主页后，使用刚学习的"开始"手势 **打开** "开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="5bdc8-122">选择"**设置"** 应用，然后选择"**系统"。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="5bdc8-123">你将看到的第一条信息是设备名称，对于 HoloLens 2 设备，该名称将为 &quot; HOLOLENS-后跟 &quot; 六个字符字符串。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="5bdc8-124">记下此名称。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-124">Take note of this name.</span></span>

    ![HoloLens 2 设置屏幕](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="5bdc8-126">验证设备是否成功加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="5bdc8-127">有两种方法：</span><span class="sxs-lookup"><span data-stu-id="5bdc8-127">There are two ways;</span></span>

    1.  <span data-ttu-id="5bdc8-128">"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-128">The Settings app.</span></span> <span data-ttu-id="5bdc8-129">从 **"设置"\*\*\*\*中选择"**  ->  **帐户""访问工作或学校"。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="5bdc8-130">从此屏幕中，你可以查看连接到 azure AD 中的 &quot; nameofAAD&#39;注册成功。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="5bdc8-131">通过 *yourusername@nameofAAD.onmicrosoft.com*连接。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="5bdc8-132">这将验证你的设备已加入你的组织&#39;Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="5bdc8-133">[Azure 门户](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="5bdc8-134">转到 **"Azure Active Directory**  ->  **设备**  ->  **""所有设备**"，然后搜索设备名称。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="5bdc8-135">在"加入类型"下，它将显示为"已加入 Azure AD"。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        ![验证 Azure AD 中的加入类型](./images/hololens2-devices-all-devices.png)

9. <span data-ttu-id="5bdc8-137">验证你的设备是否注册了 MDM。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="5bdc8-138">有两种方法：</span><span class="sxs-lookup"><span data-stu-id="5bdc8-138">There are two ways;</span></span>

    1. <span data-ttu-id="5bdc8-139">从 **"设置"** 中 **，选择"**  ->  **帐户""访问工作或学校"。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="5bdc8-140">从此屏幕中，你可以查看连接到 azure AD 中的 &quot; nameofAAD&#39;注册成功。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="5bdc8-141">通过 *yourusername@nameofAAD.onmicrosoft.com*连接。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="5bdc8-142">通过选择 Azure AD 中的"连接到 &quot; nameofAAD"，从此&#39;或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="5bdc8-143">按 &quot; "yourusername@nameofAAD.onmicrosoft.com"，然后选择" **信息"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="5bdc8-144">[Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="5bdc8-145">登录并选择"**设备"，然后选择**"**所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="5bdc8-146">在这里，你可以按名称搜索 HoloLens&#39;。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="5bdc8-147">你应该能够看到在 Intune 上列出的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![在 Azure AD 中验证由 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="5bdc8-149">Wi-Fi证书验证</span><span class="sxs-lookup"><span data-stu-id="5bdc8-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="5bdc8-150">现在，设备应该已经收到Wi-Fi证书。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="5bdc8-151">最简单的验证是尝试连接到已Wi-Fi证书&#39;连接。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="5bdc8-152">打开"**设置"** 应用并导航到 **" &amp; 网络 Internet**  ->  **WLAN"，** 然后选择 WLAN 连接。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="5bdc8-153">连接后，打开 Microsoft Edge 应用并确认你可以导航到网站。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="5bdc8-154">若要确认你已接收设备上证书，可以使用证书 [管理器](https://docs.microsoft.com/hololens/certificate-manager)。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="5bdc8-155">验证 LOB 应用安装</span><span class="sxs-lookup"><span data-stu-id="5bdc8-155">Validate LOB app install</span></span>

<span data-ttu-id="5bdc8-156">若要查看托管应用的安装进度，你可以查看该应用是否已安装或检查"设置"。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="5bdc8-157">通过配置 LOB 应用作为组所需的安装，在向分配组的用户注册 HoloLens 后，该应用将自动下载到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="5bdc8-158">打开"开始"菜单并选择"**所有应用"。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="5bdc8-159">根据你拥有的应用数量，你可能需要使用"上页"**或"下**页"**按钮。**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="5bdc8-160">若要验证应用在设备上安装，可以通过"设置""帐户""\*\*\*\* 访问工作或学校"来进行验证;选择帐户，然后选择"信息"按钮，然后向下滚动以查看从  ->  \*\*\*\*  ->  \*\*\*\* MDM\*\*\*\* 应用到设备的不同配置和应用。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="5bdc8-161">若要验证 Intune 中的安装，请导航到[MEM 门户](https://endpoint.microsoft.com/#home)应用  ->  \*\*\*\*->**应用**  -> *NameOfYourApp*  ->  **设备安装状态**页。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="5bdc8-162">查看更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="5bdc8-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="5bdc8-163">验证 Dynamics 365 指南</span><span class="sxs-lookup"><span data-stu-id="5bdc8-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="5bdc8-164">HoloLens 上的 Guides 应用有一些创作和操作模式。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="5bdc8-165">在操作指南之前，你需要完成指南的创作。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="5bdc8-166">创作指南</span><span class="sxs-lookup"><span data-stu-id="5bdc8-166">Authoring the Guide</span></span>

<span data-ttu-id="5bdc8-167">我们无需为此快速验证做很多工作。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="5bdc8-168">只需选择你在电脑上准备的指南。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="5bdc8-169">你需要定位 [指南](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)，以便快速验证你可使用全息定位标记。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="5bdc8-170">之后，你应该 [放置你的步骤和模型](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="5bdc8-171">你将需要 **Authoring** 角色才能登录到电脑，并创作 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="5bdc8-172">接线员角色是只读的，并且无法访问电脑应用。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="5bdc8-173">操作指南</span><span class="sxs-lookup"><span data-stu-id="5bdc8-173">Operating the Guide</span></span>

<span data-ttu-id="5bdc8-174">全息影像就位后，你可以测试操作指南。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="5bdc8-175">选择 **运算符模式**</span><span class="sxs-lookup"><span data-stu-id="5bdc8-175">Select **Operator mode**</span></span>
- <span data-ttu-id="5bdc8-176">单击指南的步骤。</span><span class="sxs-lookup"><span data-stu-id="5bdc8-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="5bdc8-177">有关如何操作指南的更深入指导，请查看以下资源：</span><span class="sxs-lookup"><span data-stu-id="5bdc8-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="5bdc8-178">Dynamics 365 指南中的操作指南概述</span><span class="sxs-lookup"><span data-stu-id="5bdc8-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="5bdc8-179">使用"步骤"卡片作为 Dynamics 365 Guides 中的运算符进行定向</span><span class="sxs-lookup"><span data-stu-id="5bdc8-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="5bdc8-180">下一步</span><span class="sxs-lookup"><span data-stu-id="5bdc8-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="5bdc8-181">企业连接的部署 - 维护</span><span class="sxs-lookup"><span data-stu-id="5bdc8-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
