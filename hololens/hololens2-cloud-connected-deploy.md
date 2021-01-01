---
title: 部署指南 – 通过远程协助大规模部署云连接的 HoloLens 2 - 部署
description: 如何通过云连接网络验证 HoloLens 设备的注册和远程协助
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253189"
---
# <span data-ttu-id="ce59d-104">部署 - 云连接指南</span><span class="sxs-lookup"><span data-stu-id="ce59d-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="ce59d-105">现在，你已配置所有内容，你应该已准备好分发设备。</span><span class="sxs-lookup"><span data-stu-id="ce59d-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="ce59d-106">不过，现在应该先验证设置。</span><span class="sxs-lookup"><span data-stu-id="ce59d-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="ce59d-107">首先应验证 Azure AD 加入和 MDM 注册过程，然后验证可以拨打远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce59d-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="ce59d-108">注册验证</span><span class="sxs-lookup"><span data-stu-id="ce59d-108">Enrollment Validation</span></span>

<span data-ttu-id="ce59d-109">现在，已针对 Azure AD 和 MDM 注册正确配置了一切，其余部分现在应该可以贴靠了。</span><span class="sxs-lookup"><span data-stu-id="ce59d-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="ce59d-110">你需要&#39;连接Wi-Fi HoloLens 设备，以及之前配置的 AAD 用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="ce59d-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="ce59d-111">如果你的设备当前&#39;处于出厂设置状态，那么现在应该重新调整[设备。](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="ce59d-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="ce59d-112">设备进入 OOBE 后，&#39;开始交互并遵循提示。</span><span class="sxs-lookup"><span data-stu-id="ce59d-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="ce59d-113">当系统询问谁拥有此**HoloLens**时，关键提示将是？</span><span class="sxs-lookup"><span data-stu-id="ce59d-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="ce59d-114">选择 **我的工作或学校拥有它** ，然后输入你的 Azure AD 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="ce59d-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="ce59d-115">注册成功后，&#39;提示你设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="ce59d-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="ce59d-116">此 PIN 对于此用户对于此设备是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ce59d-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="ce59d-117">系统还会提示你进行虹膜扫描、语音数据和遥测设置，最后，&#39;了解如何打开"开始"菜单并完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="ce59d-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="ce59d-118">进入混合现实主页后，使用刚学习的"开始"手势 **打开"** 开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="ce59d-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="ce59d-119">选择" **设置"** 应用，然后选择 **"系统"。**</span><span class="sxs-lookup"><span data-stu-id="ce59d-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="ce59d-120">你将看到的第&#39;一条信息是设备名称，对于 HoloLens 2 设备，它将是 &quot; HOLOLENS，后跟 &quot; 一个六个字符字符串。</span><span class="sxs-lookup"><span data-stu-id="ce59d-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="ce59d-121">记下此名称。</span><span class="sxs-lookup"><span data-stu-id="ce59d-121">Take note of this name.</span></span>

![HoloLens 2 设置 - 关于](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="ce59d-123">你可以验证设备在"设置"应用中是否成功注册了 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ce59d-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="ce59d-124">从 **"设置\*\*\*\*"中选择**  ->  **"帐户访问工作或学校"。**</span><span class="sxs-lookup"><span data-stu-id="ce59d-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="ce59d-125">从此屏幕中，可以通过查看 Azure AD 中"已连接到 &quot; _nameofAAD"&#39;_ 验证是否成功注册。</span><span class="sxs-lookup"><span data-stu-id="ce59d-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="ce59d-126">通过_yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; 连接。</span><span class="sxs-lookup"><span data-stu-id="ce59d-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="ce59d-127">若要验证设备已加入 Azure AD，我们可以从[Azure](https://portal.azure.com/#home)门户 Azure Active Directory 设备所有设备检查  ->  **Azure Active Directory，** 并搜索  ->  \*\*\*\*  ->  \*\*\*\* 设备名称。</span><span class="sxs-lookup"><span data-stu-id="ce59d-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="ce59d-128">你可以&#39;设备是 Azure Active Directory 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce59d-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory - 设备](./images/aad-enrollment.png)

<span data-ttu-id="ce59d-130">接下来，&#39;登录 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="ce59d-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="ce59d-131">登录并选择**设备**，然后选择 **"所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="ce59d-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="ce59d-132">你可以在此处搜索 HoloLens&#39;名称。</span><span class="sxs-lookup"><span data-stu-id="ce59d-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="ce59d-133">你应该能够看到你的 HoloLens 列在 Intune 上。</span><span class="sxs-lookup"><span data-stu-id="ce59d-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune - 设备](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="ce59d-135">远程协助呼叫验证</span><span class="sxs-lookup"><span data-stu-id="ce59d-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="ce59d-136">确认&#39;AAD 和 MDM 中注册设备后，&#39;测试远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce59d-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="ce59d-137">对于此验证&#39;你需要拥有 HoloLens 设备和 Windows 10 电脑，以及电脑的第二个 Azure AD 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ce59d-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="ce59d-138">此验证步骤将假定你之前已完成最后一个验证步骤，并且你的设备已注册，并且你的 Azure AD 用户位于设备上。</span><span class="sxs-lookup"><span data-stu-id="ce59d-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="ce59d-139">如果你的电脑上尚未安装 Microsoft Teams，可以在此处[下载 Teams。](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)</span><span class="sxs-lookup"><span data-stu-id="ce59d-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="ce59d-140">使用当前登录到 HoloLens 的第二个 Azure AD 用户帐户登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="ce59d-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="ce59d-141">登录电脑后，即可接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce59d-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="ce59d-142">解锁 HoloLens 并登录。</span><span class="sxs-lookup"><span data-stu-id="ce59d-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="ce59d-143">若要启动远程协助应用，请打开 **"开始"菜单并选择\*\*\*\*"远程协助"。**</span><span class="sxs-lookup"><span data-stu-id="ce59d-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="ce59d-144">远程协助不仅捆绑为收件箱应用，还固定到 HoloLens 2&#39;菜单。</span><span class="sxs-lookup"><span data-stu-id="ce59d-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="ce59d-145">如果看不到&#39;固定到"开始"菜单，请打开"所有 **应用** "列表来查找它。</span><span class="sxs-lookup"><span data-stu-id="ce59d-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="ce59d-146">远程协助启动后，它应通过 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 标识设备用户并登录到应用。</span><span class="sxs-lookup"><span data-stu-id="ce59d-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="ce59d-147">在应用中，选择 **"搜索** "，然后搜索电脑上的第二个用户。</span><span class="sxs-lookup"><span data-stu-id="ce59d-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="ce59d-148">选择用户以开始呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce59d-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="ce59d-149">从电脑应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce59d-149">From your PC, answer the call.</span></span>

<span data-ttu-id="ce59d-150">恭喜，&#39;已成功连接并正在拨打远程协助电话。</span><span class="sxs-lookup"><span data-stu-id="ce59d-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="ce59d-151">请确保试用特定的远程协助功能，例如：</span><span class="sxs-lookup"><span data-stu-id="ce59d-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="ce59d-152">墨迹书写批注</span><span class="sxs-lookup"><span data-stu-id="ce59d-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="ce59d-153">在混合现实中共享文件和视图</span><span class="sxs-lookup"><span data-stu-id="ce59d-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="ce59d-154">在另一个 HoloLens 应用中获取帮助</span><span class="sxs-lookup"><span data-stu-id="ce59d-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="ce59d-155">下一步</span><span class="sxs-lookup"><span data-stu-id="ce59d-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ce59d-156">云连接部署 - 维护</span><span class="sxs-lookup"><span data-stu-id="ce59d-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)