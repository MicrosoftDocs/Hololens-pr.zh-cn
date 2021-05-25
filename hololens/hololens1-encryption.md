---
title: HoloLens BitLocker 加密
description: 了解如何启用 BitLocker 设备加密来保护 HoloLens 混合现实设备上存储的文件。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397278"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="73dae-103">HoloLens (第一代) BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="73dae-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="73dae-104">HoloLens (第一代) 和 HoloLens 2 都支持使用 BitLocker 进行设备加密，但 BitLocker 始终在 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="73dae-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="73dae-105">本文将帮助你在 HoloLens 上启用和管理 BitLocker (第一代) 。</span><span class="sxs-lookup"><span data-stu-id="73dae-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="73dae-106">在 HoloLens (第一代) 可以手动启用 BitLocker 设备加密，或者使用 MDM (移动设备) 。</span><span class="sxs-lookup"><span data-stu-id="73dae-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="73dae-107">按照这些说明启用 [BitLocker 设备加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) ，以保护存储在 HoloLens 上的文件和信息。</span><span class="sxs-lookup"><span data-stu-id="73dae-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="73dae-108">设备加密有助于使用 AES-CBC 128 加密方法保护数据，该方法等效于 BitLocker 配置服务提供程序 (CSP) 中的[EncryptionMethodByDriveType 方法 3。](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype)</span><span class="sxs-lookup"><span data-stu-id="73dae-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="73dae-109">具有正确的加密密钥（例如 (密码）的人员) 解密或执行数据恢复。</span><span class="sxs-lookup"><span data-stu-id="73dae-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="73dae-110">使用 MDM 启用设备加密</span><span class="sxs-lookup"><span data-stu-id="73dae-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="73dae-111">可以使用 Mobile 设备管理 (MDM) 应用需要设备加密的策略。</span><span class="sxs-lookup"><span data-stu-id="73dae-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="73dae-112">使用的策略是策略 CSP [中的 Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 设置。</span><span class="sxs-lookup"><span data-stu-id="73dae-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="73dae-113">请参阅有关使用证书启用设备加密Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="73dae-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="73dae-114">有关其他 MDM 工具，请参阅 MDM 提供程序文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="73dae-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="73dae-115">如果 MDM 提供程序需要自定义 URI 进行设备加密，请使用以下配置：</span><span class="sxs-lookup"><span data-stu-id="73dae-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="73dae-116">**名称**：你选择的名称</span><span class="sxs-lookup"><span data-stu-id="73dae-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="73dae-117">**说明**：可选</span><span class="sxs-lookup"><span data-stu-id="73dae-117">**Description**: optional</span></span>
- <span data-ttu-id="73dae-118">**OMA-URI：**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="73dae-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="73dae-119">**数据类型：integer**</span><span class="sxs-lookup"><span data-stu-id="73dae-119">**Data type**: integer</span></span>
- <span data-ttu-id="73dae-120">**值**：`1`</span><span class="sxs-lookup"><span data-stu-id="73dae-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="73dae-121">使用预配程序包启用设备加密</span><span class="sxs-lookup"><span data-stu-id="73dae-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="73dae-122">预配程序包是由 Windows 配置设计器工具创建的文件，可将指定的配置应用于设备。</span><span class="sxs-lookup"><span data-stu-id="73dae-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="73dae-123">创建一个预配包，用于升级 Windows Holographic 版本并启用加密</span><span class="sxs-lookup"><span data-stu-id="73dae-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="73dae-124">为 HoloLens 创建预配包。</span><span class="sxs-lookup"><span data-stu-id="73dae-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="73dae-125">转到"**运行时设置**  >  **策略**  >  **安全性"，** 然后选择 **"RequireDeviceEncryption"。**</span><span class="sxs-lookup"><span data-stu-id="73dae-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![“要求设备加密”设置配置为“是”](images/device-encryption.png)

1. <span data-ttu-id="73dae-127">查找购买商业套件时提供的 XML 许可证文件。</span><span class="sxs-lookup"><span data-stu-id="73dae-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="73dae-128">浏览并选择购买 Commercial 套件时提供的 XML 许可证文件。</span><span class="sxs-lookup"><span data-stu-id="73dae-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="73dae-129">你可以配置[预配包中的其他设置](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="73dae-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="73dae-130">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="73dae-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="73dae-131">阅读说明项目文件可能包含敏感信息的警告，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="73dae-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="73dae-132">生成预配包时，可以在项目文件中包含敏感信息，并 ( ppkg) 文件中设置包。</span><span class="sxs-lookup"><span data-stu-id="73dae-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="73dae-133">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="73dae-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="73dae-134">你应将项目文件存储在安全的位置，并在不再需要时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="73dae-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="73dae-135">在 " **导出** " 菜单上，单击 " **预配包**"。</span><span class="sxs-lookup"><span data-stu-id="73dae-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="73dae-136">将 **所有者** 更改为 **IT 管理员**，这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="73dae-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="73dae-137">为“程序包版本”设置一个值。</span><span class="sxs-lookup"><span data-stu-id="73dae-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="73dae-138">你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="73dae-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="73dae-139">在 **选择预配包的安全性详细信息** 上，单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="73dae-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="73dae-140">单击 " **下一步** " 以指定在生成预配包后要将其移到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="73dae-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="73dae-141">默认情况下，Windows ICD 会使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="73dae-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="73dae-142">或者，你还可以单击“浏览”更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="73dae-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="73dae-143">单击“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="73dae-143">Click **Next**.</span></span>
1. <span data-ttu-id="73dae-144">单击“构建”开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="73dae-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="73dae-145">项目信息会显示在构建页面中，并且进度栏会指示构建状态。</span><span class="sxs-lookup"><span data-stu-id="73dae-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="73dae-146">构建完成后，单击 **完成**。</span><span class="sxs-lookup"><span data-stu-id="73dae-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="73dae-147">将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="73dae-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="73dae-148">通过 USB 将设备连接到电脑并启动设备，但请勿继续通过初始设置体验的 **调整** 页（带有蓝色框的第一页）。</span><span class="sxs-lookup"><span data-stu-id="73dae-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="73dae-149">短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="73dae-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="73dae-150">HoloLens 将在电脑的文件资源管理器中显示为设备。</span><span class="sxs-lookup"><span data-stu-id="73dae-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="73dae-151">在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。</span><span class="sxs-lookup"><span data-stu-id="73dae-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="73dae-152">在 **调整** 页中，再次短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。</span><span class="sxs-lookup"><span data-stu-id="73dae-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="73dae-153">设备将询问你是否信任该程序包并想要应用它。</span><span class="sxs-lookup"><span data-stu-id="73dae-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="73dae-154">确认你信任程序包。</span><span class="sxs-lookup"><span data-stu-id="73dae-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="73dae-155">你将看到是否成功应用了程序包。</span><span class="sxs-lookup"><span data-stu-id="73dae-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="73dae-156">如果失败，你可以修复程序包，然后重试。</span><span class="sxs-lookup"><span data-stu-id="73dae-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="73dae-157">如果成功，请继续进行设备设置。</span><span class="sxs-lookup"><span data-stu-id="73dae-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="73dae-158">如果设备的购买日期在 2016 年 8 月之前，则将需要使用 Microsoft 帐户登录设备，获取最新的操作系统更新并重置操作系统，以便应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="73dae-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="73dae-159">验证设备加密</span><span class="sxs-lookup"><span data-stu-id="73dae-159">Verify device encryption</span></span>

<span data-ttu-id="73dae-160">加密在 HoloLens 上无提示。</span><span class="sxs-lookup"><span data-stu-id="73dae-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="73dae-161">若要验证设备加密状态：</span><span class="sxs-lookup"><span data-stu-id="73dae-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="73dae-162">在 HoloLens 上，中转到 "**设置**" "  >  **系统**"  >  。</span><span class="sxs-lookup"><span data-stu-id="73dae-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="73dae-163">如果设备已加密，则 **启用** **BitLocker** 。</span><span class="sxs-lookup"><span data-stu-id="73dae-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![显示启用了 BitLocker 的屏幕](images/about-encryption.png)
