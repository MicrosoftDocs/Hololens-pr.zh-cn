---
title: 部署指南–企业连接的 HoloLens 2 （含 Dynamics 365 指南）-部署
description: 了解如何在使用 Dynamics 365 指南的公司连接网络上设置 HoloLens 2 设备的部署。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308383"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="6f12c-104">部署-企业连接指南</span><span class="sxs-lookup"><span data-stu-id="6f12c-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="6f12c-105">每个部署的一个重要部分是确保在测试部署之前正确设置部署，以确保对最终用户的流畅体验。</span><span class="sxs-lookup"><span data-stu-id="6f12c-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="6f12c-106">由于我们要通过 MDM 部署 Wi-Fi 证书，因此，我们需要在打开的 Wi-Fi 网络或不需要证书的网络上初始设置 HoloLens 并注册设备。</span><span class="sxs-lookup"><span data-stu-id="6f12c-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="6f12c-107">在 HoloLens 完成 OOBE 并注册后，设备将接收先前配置的网络证书和 LOB，同时我们能够验证设备是否已收到这两者。</span><span class="sxs-lookup"><span data-stu-id="6f12c-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="6f12c-108">之后，你将可以确认是否可以编写和运行测试指南。</span><span class="sxs-lookup"><span data-stu-id="6f12c-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="6f12c-109">注册验证</span><span class="sxs-lookup"><span data-stu-id="6f12c-109">Enrollment Validation</span></span>

<span data-ttu-id="6f12c-110">现在，所有内容都已正确配置 Azure AD 和 MDM 注册，接下来应该是一个快照。</span><span class="sxs-lookup"><span data-stu-id="6f12c-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="6f12c-111">需要 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 Azure AD 用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="6f12c-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="6f12c-112">如果设备当前处于出厂设置状态，现在就可以 [刷新设备](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)了。</span><span class="sxs-lookup"><span data-stu-id="6f12c-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="6f12c-113">设备进入 OOBE 后，将需要开始交互并按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="6f12c-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="6f12c-114">连接到无需证书即可加入 Wi-fi 的开放 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="6f12c-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="6f12c-115">这将允许设备下载初始设置后在组织的 Wi-Fi 上使用的证书。</span><span class="sxs-lookup"><span data-stu-id="6f12c-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="6f12c-116">当系统询问您 **此 HoloLens 的所有者** 时，将会出现严重提示？</span><span class="sxs-lookup"><span data-stu-id="6f12c-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="6f12c-117">选择 **"我的工作" 或 "学校拥有"** ，然后输入 Azure AD 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="6f12c-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="6f12c-118">注册成功后，系统将提示你设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="6f12c-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="6f12c-119">此 PIN 对于此用户是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6f12c-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="6f12c-120">系统还会提示你输入 Iris 扫描、语音数据和遥测设置，最后，你将能够了解如何打开 "开始" 菜单并完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="6f12c-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="6f12c-121">在混合现实中，使用刚刚学习的 **开始手势** 打开 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="6f12c-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="6f12c-122">选择 " **设置** " 应用，并选择 " **系统**"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="6f12c-123">你将看到的第一条信息是你的设备名称，而你的 HoloLens 2 设备的第一条信息将为 &quot; hololens， &quot; 后跟六个字符串。</span><span class="sxs-lookup"><span data-stu-id="6f12c-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="6f12c-124">记下此名称。</span><span class="sxs-lookup"><span data-stu-id="6f12c-124">Take note of this name.</span></span>

    ![HoloLens 2 设置屏幕](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="6f12c-126">验证设备是否已成功加入到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6f12c-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="6f12c-127">有两种方法：</span><span class="sxs-lookup"><span data-stu-id="6f12c-127">There are two ways;</span></span>

    1.  <span data-ttu-id="6f12c-128">"设置" 应用。</span><span class="sxs-lookup"><span data-stu-id="6f12c-128">The Settings app.</span></span> <span data-ttu-id="6f12c-129">从 "**设置**" 中选择 "**帐户**" "  ->  **访问工作单位或学校**"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="6f12c-130">在此屏幕中，可以通过查看 &quot; 连接到 nameofAAD&#39;s Azure AD 来验证是否已成功注册。</span><span class="sxs-lookup"><span data-stu-id="6f12c-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6f12c-131">通过连接 *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="6f12c-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="6f12c-132">这将验证是否已将你的设备加入到你的组织&#39;Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6f12c-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="6f12c-133">[Azure 门户](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="6f12c-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="6f12c-134">中转到 **Azure Active Directory**  ->  **设备**""  ->  **所有设备**"，然后搜索设备名称。</span><span class="sxs-lookup"><span data-stu-id="6f12c-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="6f12c-135">在 "联接类型" 下，它将显示为 "Azure AD 联接"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="6f12c-136">![验证 Azure AD 中的联接类型](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="6f12c-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="6f12c-137">验证你的设备是否已注册 MDM。</span><span class="sxs-lookup"><span data-stu-id="6f12c-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="6f12c-138">有两种方法：</span><span class="sxs-lookup"><span data-stu-id="6f12c-138">There are two ways;</span></span>

    1. <span data-ttu-id="6f12c-139">从 "**设置**" 中，选择 "**帐户**" "  ->  **访问工作或学校**"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="6f12c-140">在此屏幕中，可以通过查看 &quot; 连接到 nameofAAD&#39;s Azure AD 来验证是否已成功注册。</span><span class="sxs-lookup"><span data-stu-id="6f12c-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6f12c-141">通过连接 *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="6f12c-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="6f12c-142">通过选择 " &quot; 连接到 nameofAAD&#39;s Azure AD，从该访问工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="6f12c-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6f12c-143">连接方式 yourusername@nameofAAD.onmicrosoft.com &quot; 并选择 "**信息**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="6f12c-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="6f12c-144">[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="6f12c-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="6f12c-145">登录并选择 "  **设备**  "，然后选择 "  **所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="6f12c-146">在此处，你可以搜索你的 HoloLens 设备&#39;的名称。</span><span class="sxs-lookup"><span data-stu-id="6f12c-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="6f12c-147">你应该能够看到你的 HoloLens 已在 Intune 上列出。</span><span class="sxs-lookup"><span data-stu-id="6f12c-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![验证 Azure AD 中的 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="6f12c-149">Wi-Fi 证书验证</span><span class="sxs-lookup"><span data-stu-id="6f12c-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="6f12c-150">现在，设备应收到 Wi-Fi 证书。</span><span class="sxs-lookup"><span data-stu-id="6f12c-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="6f12c-151">可以执行的最简单验证是尝试连接到&#39;为其收到证书的 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="6f12c-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="6f12c-152">打开 "**设置**" 应用并导航到 "**网络 &amp; Internet**  ->  **wi-fi** "，然后选择 "wi-fi 连接"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="6f12c-153">连接后，请打开 Microsoft Edge 应用并确认你可以导航到网站。</span><span class="sxs-lookup"><span data-stu-id="6f12c-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="6f12c-154">若要确认是否已在设备上收到证书，可以使用 [证书管理器](https://docs.microsoft.com/hololens/certificate-manager)。</span><span class="sxs-lookup"><span data-stu-id="6f12c-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="6f12c-155">验证 LOB 应用安装</span><span class="sxs-lookup"><span data-stu-id="6f12c-155">Validate LOB app install</span></span>

<span data-ttu-id="6f12c-156">若要查看托管应用的安装进度，你可以查看应用是否已安装或检查设置。</span><span class="sxs-lookup"><span data-stu-id="6f12c-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="6f12c-157">通过将 LOB 应用配置为组所需的安装，在向已分配组中的用户注册 HoloLens 后，应用将自动下载到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6f12c-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="6f12c-158">打开 "开始" 菜单，并选择 " **所有应用**"。</span><span class="sxs-lookup"><span data-stu-id="6f12c-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="6f12c-159">你可能需要使用 **page up** 或 **page down** 按钮，具体取决于你所拥有的应用数。</span><span class="sxs-lookup"><span data-stu-id="6f12c-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="6f12c-160">若要在设备上验证应用的安装，你可以通过 "**设置**" "帐户" "  ->    ->  **访问工作或学校**" 执行此操作; 选择帐户，然后单击 "**信息**" 按钮，然后向下滚动查看从 MDM 应用到设备的不同配置和应用。</span><span class="sxs-lookup"><span data-stu-id="6f12c-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="6f12c-161">若要从 Intune 验证安装，请导航到 "[内存门户](https://endpoint.microsoft.com/#home)  ->  **应用**-> 所有 **应用**"  -> *TheNameOfYourApp*"  ->  **设备安装状态**" 页。</span><span class="sxs-lookup"><span data-stu-id="6f12c-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="6f12c-162">了解更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="6f12c-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="6f12c-163">验证 Dynamics 365 指南</span><span class="sxs-lookup"><span data-stu-id="6f12c-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="6f12c-164">在 HoloLens、创作和操作方面，辅助应用程序有多种模式。</span><span class="sxs-lookup"><span data-stu-id="6f12c-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="6f12c-165">在操作之前，需要完成编写指南。</span><span class="sxs-lookup"><span data-stu-id="6f12c-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="6f12c-166">创作指南</span><span class="sxs-lookup"><span data-stu-id="6f12c-166">Authoring the Guide</span></span>

<span data-ttu-id="6f12c-167">对于此快速验证，我们不需要这么做。</span><span class="sxs-lookup"><span data-stu-id="6f12c-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="6f12c-168">只需选择你在电脑上准备的指南即可。</span><span class="sxs-lookup"><span data-stu-id="6f12c-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="6f12c-169">你需要 [定位指南](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)，以便快速验证你可以使用全息锚。</span><span class="sxs-lookup"><span data-stu-id="6f12c-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="6f12c-170">之后，应 [放置步骤和模型](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="6f12c-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="6f12c-171">你将需要 **创作** 角色登录到电脑，并在 HoloLens 上创作。</span><span class="sxs-lookup"><span data-stu-id="6f12c-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="6f12c-172">操作员角色为只读，不能访问电脑应用。</span><span class="sxs-lookup"><span data-stu-id="6f12c-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="6f12c-173">操作指南</span><span class="sxs-lookup"><span data-stu-id="6f12c-173">Operating the Guide</span></span>

<span data-ttu-id="6f12c-174">全息影像准备就绪后，即可测试操作指南。</span><span class="sxs-lookup"><span data-stu-id="6f12c-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="6f12c-175">选择 **操作员模式**</span><span class="sxs-lookup"><span data-stu-id="6f12c-175">Select **Operator mode**</span></span>
- <span data-ttu-id="6f12c-176">单击指导的步骤。</span><span class="sxs-lookup"><span data-stu-id="6f12c-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="6f12c-177">若要深入了解如何操作指南，请查看以下资源：</span><span class="sxs-lookup"><span data-stu-id="6f12c-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="6f12c-178">Dynamics 365 指南中的操作指南概述</span><span class="sxs-lookup"><span data-stu-id="6f12c-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="6f12c-179">在 Dynamics 365 指南中，使用步骤卡作为操作员</span><span class="sxs-lookup"><span data-stu-id="6f12c-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="6f12c-180">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6f12c-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="6f12c-181">企业连接部署-维护</span><span class="sxs-lookup"><span data-stu-id="6f12c-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
