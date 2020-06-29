---
title: 解锁 Windows Holographic for Business 功能
description: 升级到 Windows 全息版 for Business 时，HoloLens 提供了专为企业设计的额外功能。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827991"
---
# <span data-ttu-id="73d64-103">解锁 Windows Holographic for Business 功能</span><span class="sxs-lookup"><span data-stu-id="73d64-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73d64-104">此页面仅适用于 HoloLens 第一代。</span><span class="sxs-lookup"><span data-stu-id="73d64-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="73d64-105">Microsoft HoloLens 在*开发版*中可用，它运行 windows 全息版（专为 HoloLens 设计的 windows 10 版本），并且在[商业版套件](hololens-commercial-features.md)中提供了专为企业设计的额外功能。</span><span class="sxs-lookup"><span data-stu-id="73d64-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="73d64-106">购买商业套件时，你会收到可将 Windows 全息版升级为 Windows Holographic for Business 的许可。</span><span class="sxs-lookup"><span data-stu-id="73d64-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="73d64-107">你可以使用组织的[移动设备管理（MDM）提供程序](#edition-upgrade-by-using-mdm)或[预配包](#edition-upgrade-by-using-a-provisioning-package)将此许可证应用到设备。</span><span class="sxs-lookup"><span data-stu-id="73d64-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="73d64-108">在 Windows 10 版本1803中，可以通过选择 "**设置**系统" 检查 HoloLens 是否已升级到商业版  >  **System**。</span><span class="sxs-lookup"><span data-stu-id="73d64-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="73d64-109">使用 MDM 升级版本</span><span class="sxs-lookup"><span data-stu-id="73d64-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="73d64-110">可通过支持 [WindowsLicensing 配置服务提供程序 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任意 MDM 提供程序应用企业许可。</span><span class="sxs-lookup"><span data-stu-id="73d64-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="73d64-111">最新版的 Microsoft MDM API 将支持 WindowsLicensing CSP。</span><span class="sxs-lookup"><span data-stu-id="73d64-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="73d64-112">有关使用 Microsoft Intune 升级 HoloLens 的分步说明，请参阅[将运行 Windows 全息的设备升级到 Windows 全息版 For Business](https://docs.microsoft.com/intune/holographic-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="73d64-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="73d64-113">在其他 MDM 提供程序中，策略的具体设置和部署步骤可能不同。</span><span class="sxs-lookup"><span data-stu-id="73d64-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="73d64-114">使用预配包进行版本升级</span><span class="sxs-lookup"><span data-stu-id="73d64-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="73d64-115">预配程序包是由 Windows 配置设计器工具创建的文件，可将指定的配置应用于设备。</span><span class="sxs-lookup"><span data-stu-id="73d64-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="73d64-116">创建可升级 Windows 全息版的预配程序包</span><span class="sxs-lookup"><span data-stu-id="73d64-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="73d64-117">为 HoloLens 创建预配包。</span><span class="sxs-lookup"><span data-stu-id="73d64-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="73d64-118">转到**运行时设置** > **EditionUpgrade**，然后选择**EditionUpgradeWithLicense**。</span><span class="sxs-lookup"><span data-stu-id="73d64-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![使用已选择的许可证设置升级版本](images/icd1.png)

1. <span data-ttu-id="73d64-120">查找购买商业版套件时提供的 XML 许可证文件。</span><span class="sxs-lookup"><span data-stu-id="73d64-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73d64-121">你可以配置[预配包中的其他设置](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="73d64-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="73d64-122">在 "**文件**" 菜单上，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="73d64-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="73d64-123">阅读警告，指出项目文件可能包含敏感信息，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="73d64-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="73d64-124">生成预配包时，你可能会在项目文件和预配包（ppkg）文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="73d64-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="73d64-125">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="73d64-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="73d64-126">应将项目文件存储在安全的位置，并在不再需要项目文件时将其删除。</span><span class="sxs-lookup"><span data-stu-id="73d64-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="73d64-127">在“导出”\*\*\*\* 菜单上，选择“设置包”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73d64-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="73d64-128">将**所有者**更改为**IT 管理员**，这会将此预配包的优先级设置为高于从其他源应用到此设备的其他应用程序，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="73d64-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="73d64-129">为**程序包版本**设置一个值。</span><span class="sxs-lookup"><span data-stu-id="73d64-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="73d64-130">你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="73d64-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="73d64-131">在 **"选择预配包的安全详细信息**" 中，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="73d64-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="73d64-132">选择 "**下一步**" 以指定在构建预配包后你希望其转到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="73d64-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="73d64-133">默认情况下，Windows ICD 会使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="73d64-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="73d64-134">或者，你可以选择 "**浏览**" 以更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="73d64-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="73d64-135">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="73d64-135">Select **Next**.</span></span>

1. <span data-ttu-id="73d64-136">选择 "**生成**" 开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="73d64-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="73d64-137">"生成" 页面显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="73d64-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="73d64-138">生成完成后，选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="73d64-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="73d64-139">将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="73d64-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="73d64-140">使用 USB 电缆将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="73d64-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="73d64-141">启动设备，但不要在初始设置体验的 "**适合**" 页（第一个带有蓝色框的第一页）上继续。</span><span class="sxs-lookup"><span data-stu-id="73d64-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="73d64-142">在电脑上，HoloLens 在文件资源管理器中显示为设备。</span><span class="sxs-lookup"><span data-stu-id="73d64-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73d64-143">如果 HoloLens 设备运行的是 Windows 10 版本1607或更早版本，请打开文件资源管理器，方法是在设备上同时短暂地按下并释放 "**音量**" 和 "**电源**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="73d64-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="73d64-144">在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。</span><span class="sxs-lookup"><span data-stu-id="73d64-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="73d64-145">虽然 HoloLens 仍在 "**适合**" 页面，请暂时按下并再次释放**音量**和**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="73d64-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="73d64-146">HoloLens 会询问你是否信任程序包并希望应用它。</span><span class="sxs-lookup"><span data-stu-id="73d64-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="73d64-147">确认你信任程序包。</span><span class="sxs-lookup"><span data-stu-id="73d64-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="73d64-148">你将看到是否成功应用了程序包。</span><span class="sxs-lookup"><span data-stu-id="73d64-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="73d64-149">如果未成功应用，您可以修复程序包并重试。</span><span class="sxs-lookup"><span data-stu-id="73d64-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="73d64-150">如果成功，请继续执行设备设置。</span><span class="sxs-lookup"><span data-stu-id="73d64-150">If successful, proceed with device setup.</span></span>
