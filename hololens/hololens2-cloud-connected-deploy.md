---
title: 部署指南-云通过远程辅助功能在扩展时连接到 HoloLens 2 部署
description: 如何通过连接到云的网络上的 HoloLens 设备验证注册和远程协助
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196273"
---
# <span data-ttu-id="cd091-104">部署-云连接指南</span><span class="sxs-lookup"><span data-stu-id="cd091-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="cd091-105">既然已配置所有内容，您就可以分发设备了。</span><span class="sxs-lookup"><span data-stu-id="cd091-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="cd091-106">但是，这是你应该首先验证你的设置。</span><span class="sxs-lookup"><span data-stu-id="cd091-106">However, this is when you should first validate your set up.</span></span> <span data-ttu-id="cd091-107">首先应验证 AAD 联接和 MDM 注册过程，然后验证是否可以放置远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd091-107">First the AAD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="cd091-108">注册验证</span><span class="sxs-lookup"><span data-stu-id="cd091-108">Enrollment Validation</span></span>

<span data-ttu-id="cd091-109">现在，所有为 AAD 和 MDM 注册配置的内容都应该是快照。</span><span class="sxs-lookup"><span data-stu-id="cd091-109">With everything properly configured for AAD and MDM Enrollment should now be a snap.</span></span> <span data-ttu-id="cd091-110">你&#39;需要 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 AAD 用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="cd091-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="cd091-111">如果你的设备目前&#39;t 处于工厂设置状态，现在可以将 [设备 reflash](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="cd091-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="cd091-112">一旦设备在 OOBE 中，你&#39;需要开始交互并遵循提示。</span><span class="sxs-lookup"><span data-stu-id="cd091-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="cd091-113">当系统询问**谁拥有此 HoloLens**时，关键提示将是什么？</span><span class="sxs-lookup"><span data-stu-id="cd091-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="cd091-114">选择 **"我的工作或学校拥有它"** ，然后输入 AAD 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="cd091-114">Select **My work or school owns it** and enter your AAD account credentials.</span></span>
1. <span data-ttu-id="cd091-115">注册成功后，系统将提示你&#39;设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="cd091-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="cd091-116">此用户的此设备独有。</span><span class="sxs-lookup"><span data-stu-id="cd091-116">This is unique to this device for this user.</span></span> <span data-ttu-id="cd091-117">你还会收到虹膜扫描、语音数据和遥测设置的提示，最后，你&#39;能够了解如何打开 "开始" 菜单和完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="cd091-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="cd091-118">在混合现实开始时，请使用刚刚学习的 " **开始** " 菜单打开 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="cd091-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span> 
1. <span data-ttu-id="cd091-119">选择 " **设置** " 应用，然后选择 " **系统"。**</span><span class="sxs-lookup"><span data-stu-id="cd091-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="cd091-120">你&#39;看到的第一条信息是你的设备名称，而你的 HoloLens 2 设备的第一条信息将是 &quot; hololens， &quot; 后跟6个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="cd091-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a 6 character string.</span></span> 
1. <span data-ttu-id="cd091-121">记下此名称。</span><span class="sxs-lookup"><span data-stu-id="cd091-121">Take note of this name.</span></span>

![HoloLens 2 设置-关于](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="cd091-123">你可以在 "设置" 应用中验证你的设备是否已成功注册到 AAD 中。</span><span class="sxs-lookup"><span data-stu-id="cd091-123">You can verify that your device is successfully enrolled in the AAD within the Settings app.</span></span> <span data-ttu-id="cd091-124">从 "**设置**" 中选择 "**帐户**  ->  **访问工作或学校**"。</span><span class="sxs-lookup"><span data-stu-id="cd091-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="cd091-125">在此屏幕上，你可以通过查看已 &quot; 连接到 _nameofAAD_&#39;s Azure AD 来验证是否已成功注册。</span><span class="sxs-lookup"><span data-stu-id="cd091-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="cd091-126">通过_用户名_ @ _nameofAAD_ &quot; 连接。</span><span class="sxs-lookup"><span data-stu-id="cd091-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>

<span data-ttu-id="cd091-127">若要验证设备是否已加入 AAD，我们可以从[azure Portal](https://portal.azure.com/#home)  ->  **azure active directory**设备中检查所有设备的 azure active directory  ->  **Devices**  ->  **All devices** ，并搜索设备名称。</span><span class="sxs-lookup"><span data-stu-id="cd091-127">To validate the device has AAD Joined we can check the Azure Active Directory from the [Azure Portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices** , and search the device name.</span></span> <span data-ttu-id="cd091-128">你&#39;能够看到该设备是 Azure Active Directory 的一部分。</span><span class="sxs-lookup"><span data-stu-id="cd091-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>

![Azure Active Directory-设备](./images/aad-enrollment.png)

<span data-ttu-id="cd091-130">接下来，你&#39;需要登录到 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="cd091-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="cd091-131">登录并选择 " **设备** "，然后选择 " **所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="cd091-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="cd091-132">在此处，您可以搜索您的 HoloLens 设备&#39;s 名称。</span><span class="sxs-lookup"><span data-stu-id="cd091-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="cd091-133">你应该能够查看 Intune 上列出的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd091-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-设备](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="cd091-135">远程协助呼叫验证</span><span class="sxs-lookup"><span data-stu-id="cd091-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="cd091-136">一旦你&#39;验证你的设备已在 AAD 和 MDM 中注册，它将&#39;s 次进行测试远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd091-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="cd091-137">对于此验证，你&#39;需要安装 HoloLens 设备和 Windows 10 电脑，以及电脑的第二个 AAD 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cd091-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second AAD user account for the PC.</span></span>

<span data-ttu-id="cd091-138">此验证步骤将假定你之前已完成最后一个验证步骤，并且你的设备已注册，并且你的 AAD 用户位于设备上。</span><span class="sxs-lookup"><span data-stu-id="cd091-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your AAD user is on the device.</span></span>

1. <span data-ttu-id="cd091-139">如果你未在电脑上安装 Microsoft 团队&#39;则可以在 [此处下载团队](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。</span><span class="sxs-lookup"><span data-stu-id="cd091-139">If you don&#39;t already have Microsoft Teams installed on your PC you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="cd091-140">使用当前登录到 HoloLens 的第二个 AAD 用户帐户登录团队。</span><span class="sxs-lookup"><span data-stu-id="cd091-140">Sign into Teams using the second AAD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="cd091-141">登录电脑后，您就可以接收呼叫了。</span><span class="sxs-lookup"><span data-stu-id="cd091-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="cd091-142">解锁 HoloLens 并登录。</span><span class="sxs-lookup"><span data-stu-id="cd091-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="cd091-143">若要启动远程协助应用，请打开 " **开始" 菜单** ，然后选择 " **远程协助**"。</span><span class="sxs-lookup"><span data-stu-id="cd091-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="cd091-144">远程协助不仅捆绑为收件箱应用，还固定到 HoloLens 2&#39;s "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="cd091-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="cd091-145">在事件中，你不&#39;t 看到它固定到 "开始" 菜单，然后打开 " **所有应用** " 列表以查找它。</span><span class="sxs-lookup"><span data-stu-id="cd091-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="cd091-146">远程协助启动后，它应通过 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 确定设备的用户并登录到该应用。</span><span class="sxs-lookup"><span data-stu-id="cd091-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="cd091-147">在应用内，选择 " **搜索** "，然后搜索电脑上的第二个用户。</span><span class="sxs-lookup"><span data-stu-id="cd091-147">From within the app select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="cd091-148">选择要开始呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="cd091-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="cd091-149">您的电脑接听通话。</span><span class="sxs-lookup"><span data-stu-id="cd091-149">From your PC answer the call.</span></span>

<span data-ttu-id="cd091-150">恭喜，您&#39;已成功连接，并且在您的远程协助呼叫中。</span><span class="sxs-lookup"><span data-stu-id="cd091-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="cd091-151">请确保尝试使用特定的远程协助功能，例如使用：</span><span class="sxs-lookup"><span data-stu-id="cd091-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="cd091-152">墨迹书写批注</span><span class="sxs-lookup"><span data-stu-id="cd091-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="cd091-153">在混合现实中共享文件和视图</span><span class="sxs-lookup"><span data-stu-id="cd091-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="cd091-154">在其他 HoloLens 应用中获取帮助</span><span class="sxs-lookup"><span data-stu-id="cd091-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="cd091-155">下一步</span><span class="sxs-lookup"><span data-stu-id="cd091-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cd091-156">云连接部署-维护</span><span class="sxs-lookup"><span data-stu-id="cd091-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)