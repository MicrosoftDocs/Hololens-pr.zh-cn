---
title: 部署指南–云连接的 HoloLens 2 大规模部署，具有远程协助-部署
description: 了解如何通过云连接网络验证 HoloLens 设备的注册和远程协助。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308485"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="a61d5-104">部署-云连接指南</span><span class="sxs-lookup"><span data-stu-id="a61d5-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="a61d5-105">完成所有配置后，应准备好分发设备。</span><span class="sxs-lookup"><span data-stu-id="a61d5-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="a61d5-106">不过，现在您应该首先验证您的设置。</span><span class="sxs-lookup"><span data-stu-id="a61d5-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="a61d5-107">首先，应验证 Azure AD 联接和 MDM 注册过程，然后验证是否可以发出远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="a61d5-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="a61d5-108">注册验证</span><span class="sxs-lookup"><span data-stu-id="a61d5-108">Enrollment Validation</span></span>

<span data-ttu-id="a61d5-109">现在，所有内容都已正确配置 Azure AD 和 MDM 注册，接下来应该是一个快照。</span><span class="sxs-lookup"><span data-stu-id="a61d5-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="a61d5-110">&#39;要求 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 AAD 用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="a61d5-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="a61d5-111">如果设备目前处于出厂设置状态&#39;t，现在是 [刷新设备](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)的好时机。</span><span class="sxs-lookup"><span data-stu-id="a61d5-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="a61d5-112">设备进入 OOBE 后，您&#39;需要开始交互，并按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="a61d5-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="a61d5-113">当系统询问您 **此 HoloLens 的所有者** 时，将会出现严重提示？</span><span class="sxs-lookup"><span data-stu-id="a61d5-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="a61d5-114">选择 **"我的工作" 或 "学校拥有"** ，然后输入 Azure AD 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="a61d5-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="a61d5-115">注册成功后，将提示您&#39;设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="a61d5-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="a61d5-116">此 PIN 对于此用户是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a61d5-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="a61d5-117">系统还会提示你进行 Iris 扫描、语音数据和遥测设置，最后&#39;可以了解如何打开 "开始" 菜单并完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="a61d5-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="a61d5-118">进入混合现实后，开始使用刚刚学习的 **开始手势** 。</span><span class="sxs-lookup"><span data-stu-id="a61d5-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="a61d5-119">选择 " **设置** " 应用，并选择 " **系统"。**</span><span class="sxs-lookup"><span data-stu-id="a61d5-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="a61d5-120">你&#39;的第一条信息是你的设备名称，你的 HoloLens 2 设备的名称将为 &quot; hololens， &quot; 后跟六个字符串。</span><span class="sxs-lookup"><span data-stu-id="a61d5-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="a61d5-121">记下此名称。</span><span class="sxs-lookup"><span data-stu-id="a61d5-121">Take note of this name.</span></span>

![HoloLens 2 设置-关于](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="a61d5-123">你可以在 "设置" 应用中验证你的设备是否已成功注册 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a61d5-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="a61d5-124">从 "**设置**" 中选择 "**帐户**" "  ->  **访问工作单位或学校**"。</span><span class="sxs-lookup"><span data-stu-id="a61d5-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="a61d5-125">在此屏幕上，可以通过查看 &quot; 连接到 _nameofAAD_&#39;s Azure AD 来验证是否已成功注册。</span><span class="sxs-lookup"><span data-stu-id="a61d5-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="a61d5-126">通过 _yourusername_ @ _nameofAAD_. onmicrosoft.com 连接 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="a61d5-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="a61d5-127">若要验证设备是否已 Azure AD 联接，我们可以从[Azure 门户](https://portal.azure.com/#home)Azure Active Directory 设备 "" 所有设备 "中检查 Azure Active Directory  ->    ->    ->  ，并搜索设备名称。</span><span class="sxs-lookup"><span data-stu-id="a61d5-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="a61d5-128">&#39;可以看到该设备是 Azure Active Directory 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a61d5-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-设备](./images/aad-enrollment.png)

<span data-ttu-id="a61d5-130">接下来，需要登录到 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com/#home)&#39;。</span><span class="sxs-lookup"><span data-stu-id="a61d5-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="a61d5-131">登录并选择 " **设备** "，然后选择 " **所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="a61d5-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="a61d5-132">可从此处搜索你的 HoloLens 设备&#39;的名称。</span><span class="sxs-lookup"><span data-stu-id="a61d5-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="a61d5-133">你应该能够看到你的 HoloLens 已在 Intune 上列出。</span><span class="sxs-lookup"><span data-stu-id="a61d5-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-设备](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="a61d5-135">远程协助呼叫验证</span><span class="sxs-lookup"><span data-stu-id="a61d5-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="a61d5-136">&#39;ve 验证你的设备是否已注册到 AAD 和 MDM 后，就&#39;了下一次测试远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="a61d5-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="a61d5-137">对于此验证，&#39;需要安装 HoloLens 设备和 Windows 10 PC，还需要安装 PC 的第二 Azure AD 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a61d5-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="a61d5-138">此验证步骤将假定你之前已完成了上一次验证步骤，并且你的设备已注册，并且你的 Azure AD 用户在设备上。</span><span class="sxs-lookup"><span data-stu-id="a61d5-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="a61d5-139">如果你的电脑上尚未安装 Microsoft 团队，则可以在 [此处下载团队](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。</span><span class="sxs-lookup"><span data-stu-id="a61d5-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="a61d5-140">使用第二个 Azure AD 用户帐户登录团队，而不是当前登录到 HoloLens 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a61d5-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="a61d5-141">登录到你的电脑后，你将可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="a61d5-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="a61d5-142">解锁 HoloLens 并登录。</span><span class="sxs-lookup"><span data-stu-id="a61d5-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="a61d5-143">若要启动远程协助应用，请打开 " **开始" 菜单** ，然后选择 " **远程协助**"。</span><span class="sxs-lookup"><span data-stu-id="a61d5-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="a61d5-144">远程协助不仅捆绑为收件箱应用，还会固定到 HoloLens 2&#39;s 开始菜单。</span><span class="sxs-lookup"><span data-stu-id="a61d5-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="a61d5-145">在不&#39;的事件中，会看到它固定到 "开始" 菜单，并打开 " **所有应用程序** " 列表来查找它。</span><span class="sxs-lookup"><span data-stu-id="a61d5-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="a61d5-146">远程协助启动后，它应通过 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 确定设备的用户，并登录到该应用。</span><span class="sxs-lookup"><span data-stu-id="a61d5-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="a61d5-147">在应用中，选择 " **搜索** "，然后搜索计算机上的第二个用户。</span><span class="sxs-lookup"><span data-stu-id="a61d5-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="a61d5-148">选择要开始呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="a61d5-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="a61d5-149">在电脑上，回答呼叫。</span><span class="sxs-lookup"><span data-stu-id="a61d5-149">From your PC, answer the call.</span></span>

<span data-ttu-id="a61d5-150">恭喜，你&#39;ve 已成功连接，并且在远程协助呼叫上。</span><span class="sxs-lookup"><span data-stu-id="a61d5-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="a61d5-151">请确保尝试特定的远程协助功能，如使用：</span><span class="sxs-lookup"><span data-stu-id="a61d5-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="a61d5-152">墨迹批注</span><span class="sxs-lookup"><span data-stu-id="a61d5-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="a61d5-153">在混合现实中共享文件和视图</span><span class="sxs-lookup"><span data-stu-id="a61d5-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="a61d5-154">在另一个 HoloLens 应用中获取帮助</span><span class="sxs-lookup"><span data-stu-id="a61d5-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="a61d5-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a61d5-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a61d5-156">云连接部署-维护</span><span class="sxs-lookup"><span data-stu-id="a61d5-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)