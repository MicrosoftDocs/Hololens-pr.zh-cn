---
title: MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境
description: 如何在 HoloLens 2 设备上获取网络的 MAC 地址
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253139"
---
# <span data-ttu-id="2a23e-103">MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境</span><span class="sxs-lookup"><span data-stu-id="2a23e-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="2a23e-104">本文将介绍在客户环境中标识的一种常见方案，其中WLAN 受 MAC 地址的限制，或者需要证书来加入无线网络。</span><span class="sxs-lookup"><span data-stu-id="2a23e-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="2a23e-105">示例方案</span><span class="sxs-lookup"><span data-stu-id="2a23e-105">Example Scenario</span></span>

<span data-ttu-id="2a23e-106">安全环境中的许多客户对其无线或有线网络有限制，这将只允许批准的设备（基于 MAC 地址）成功连接（在无线接入点或 DHCP 服务器上进行 MAC 地址筛选）。</span><span class="sxs-lookup"><span data-stu-id="2a23e-106">Many customers in secure environments have restrictions on their Wireless or wired networks, which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="2a23e-107">此外，一些无线网络可以用 PEAP 进行保护，这要求在能够成功地认证无线网络之前向设备应用证书。</span><span class="sxs-lookup"><span data-stu-id="2a23e-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate is applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="2a23e-108">HoloLens 设备可能会产生两个重要问题，这可能会导致延迟和在将 HoloLens 设备加入到网络时需要进行手动操作。</span><span class="sxs-lookup"><span data-stu-id="2a23e-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="2a23e-109">在设备成功加入无线网络之前必须将无线 PEAP 证书应用于设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="2a23e-110">必须注册 HoloLens WLAN 适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="2a23e-111">其关键挑战有：</span><span class="sxs-lookup"><span data-stu-id="2a23e-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="2a23e-112">目前，MAC 地址只能从设备上的设置应用中标识，或在成功进行 Intune 注册后从 Intune 标识。</span><span class="sxs-lookup"><span data-stu-id="2a23e-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="2a23e-113">没有 MAC 地址，设备就无法加入 WLAN 网络开始注册。</span><span class="sxs-lookup"><span data-stu-id="2a23e-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="2a23e-114">这些挑战的手动解决方案要求技术人员通过设备参与。</span><span class="sxs-lookup"><span data-stu-id="2a23e-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="2a23e-115">解决方案</span><span class="sxs-lookup"><span data-stu-id="2a23e-115">Solutions</span></span>

<span data-ttu-id="2a23e-116">有许多方法可以改善这种情况，具体取决于环境中可用的基础设施。</span><span class="sxs-lookup"><span data-stu-id="2a23e-116">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="2a23e-117">解决方案</span><span class="sxs-lookup"><span data-stu-id="2a23e-117">Solution</span></span> | <span data-ttu-id="2a23e-118">优势</span><span class="sxs-lookup"><span data-stu-id="2a23e-118">Benefits</span></span> | <span data-ttu-id="2a23e-119">要求</span><span class="sxs-lookup"><span data-stu-id="2a23e-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2a23e-120">使用以太网适配器预配程序包</span><span class="sxs-lookup"><span data-stu-id="2a23e-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="2a23e-121">改进 OOBE 体验，更快地提供技术人员体验。</span><span class="sxs-lookup"><span data-stu-id="2a23e-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="2a23e-122">HoloLens 兼容的 USB C HubTechnician 仍需与设备进行交互，以实现 MAC 捕获和 OOBE 完成</span><span class="sxs-lookup"><span data-stu-id="2a23e-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalization</span></span> |
| <span data-ttu-id="2a23e-123">Autopilot 在以太网上使用 Intune 注册</span><span class="sxs-lookup"><span data-stu-id="2a23e-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="2a23e-124">单步连接和将设备注册到客户 environmentMAC 捕获可以在不与设备交互的情况下完成</span><span class="sxs-lookup"><span data-stu-id="2a23e-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="2a23e-125">已为客户 Azure AD TenantHoloLens 启用 Intune 兼容的 USB-C 网络适配器</span><span class="sxs-lookup"><span data-stu-id="2a23e-125">Intune enabled for the customer Azure AD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="2a23e-126">自动报告 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="2a23e-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="2a23e-127">在 Intune 租户内注册设备后，将 MAC 地址的报告脚本给技术人员。</span><span class="sxs-lookup"><span data-stu-id="2a23e-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="2a23e-128">Intune PowerShell Commandlets</span><span class="sxs-lookup"><span data-stu-id="2a23e-128">Intune PowerShell Commandlets</span></span> |

## <span data-ttu-id="2a23e-129">使用以太网适配器预配程序包</span><span class="sxs-lookup"><span data-stu-id="2a23e-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="2a23e-130">如果有线网络还受 MAC 限制的约束，则需要预批准 USB-C 以太网适配器/集线器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="2a23e-131">请注意，这种集线器将允许从其他设备访问网络。</span><span class="sxs-lookup"><span data-stu-id="2a23e-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="2a23e-132">要求</span><span class="sxs-lookup"><span data-stu-id="2a23e-132">Requirements</span></span>

- <span data-ttu-id="2a23e-133">可访问客户网络的有线网络端口</span><span class="sxs-lookup"><span data-stu-id="2a23e-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="2a23e-134">HoloLens 兼容的 USB-C 集线器，包括一个以太网适配器 - 不&#39;需要任何额外的驱动程序或应用程序安装的任何集线器均适用。</span><span class="sxs-lookup"><span data-stu-id="2a23e-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="2a23e-135">预配程序包包括：</span><span class="sxs-lookup"><span data-stu-id="2a23e-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="2a23e-136">包含无线网络信息和证书</span><span class="sxs-lookup"><span data-stu-id="2a23e-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="2a23e-137">（可选）包含组织 Azure AD 的注册信息</span><span class="sxs-lookup"><span data-stu-id="2a23e-137">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="2a23e-138">包含所有其他必需的预配设置</span><span class="sxs-lookup"><span data-stu-id="2a23e-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="2a23e-139">过程</span><span class="sxs-lookup"><span data-stu-id="2a23e-139">Process</span></span>

<span data-ttu-id="2a23e-140">该过程可能有所不同，具体取决于设备的软件级别。</span><span class="sxs-lookup"><span data-stu-id="2a23e-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="2a23e-141">如果该设备已于 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，请遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2a23e-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="2a23e-142">将预配程序包放到 USB 棒的根位置，然后插入集线器。</span><span class="sxs-lookup"><span data-stu-id="2a23e-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="2a23e-143">将以太网缆线连接到集线器。</span><span class="sxs-lookup"><span data-stu-id="2a23e-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="2a23e-144">将 USB-C 集线器连接到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="2a23e-145">打开 HoloLens 设备并佩戴设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="2a23e-146">按**音量和电源按钮**应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="2a23e-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="2a23e-147">技术人员现在可以按照 OOBE 操作，完成后，打开设置应用，然后检索设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="2a23e-148">如果该设备在 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前进行了操作系统构建，请遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2a23e-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="2a23e-149">打开 HoloLens 设备，然后将设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="2a23e-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="2a23e-150">设备应在电脑上显示为文件存储设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="2a23e-151">预配程序包复制到设备</span><span class="sxs-lookup"><span data-stu-id="2a23e-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="2a23e-152">将以太网缆线连接到集线器。</span><span class="sxs-lookup"><span data-stu-id="2a23e-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="2a23e-153">将 USB-C 集线器连接到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="2a23e-154">佩戴设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-154">Wear the device.</span></span>
7. <span data-ttu-id="2a23e-155">按**音量和电源**按钮应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="2a23e-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="2a23e-156">技术人员现在可以按照 OOBE 操作，完成后，打开设置应用，然后检索设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="2a23e-157">优势</span><span class="sxs-lookup"><span data-stu-id="2a23e-157">Benefits</span></span>

<span data-ttu-id="2a23e-158">这将允许设备&quot;单一触控&quot;应用正确的预配程序包并收集设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="2a23e-159">可按此指南创建预配程序包。</span><span class="sxs-lookup"><span data-stu-id="2a23e-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="2a23e-160">具有 Intune 注册的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="2a23e-160">Autopilot with Intune Enrollment</span></span>

### <span data-ttu-id="2a23e-161">要求</span><span class="sxs-lookup"><span data-stu-id="2a23e-161">Requirements</span></span>

- <span data-ttu-id="2a23e-162">可访问客户网络的有线网络端口</span><span class="sxs-lookup"><span data-stu-id="2a23e-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="2a23e-163">运行 Windows Holographic 2004 的 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="2a23e-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="2a23e-164">HoloLens 兼容的 USB-C 集线器</span><span class="sxs-lookup"><span data-stu-id="2a23e-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="2a23e-165">已为客户租户设置并启用 Intune</span><span class="sxs-lookup"><span data-stu-id="2a23e-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="2a23e-166">为 Autopilot 注册并导入客户租户的设备</span><span class="sxs-lookup"><span data-stu-id="2a23e-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="2a23e-167">已为设备定义 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="2a23e-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="2a23e-168">包含无线网络信息和证书</span><span class="sxs-lookup"><span data-stu-id="2a23e-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="2a23e-169">包含所有其他必需的预配设置</span><span class="sxs-lookup"><span data-stu-id="2a23e-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="2a23e-170">这将允许有高级网络需求的客户以一种不干涉的、可伸缩的方式注册设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="2a23e-171">需要更多先决条件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a23e-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="2a23e-172">为 Autopilot 预览版启用租户</span><span class="sxs-lookup"><span data-stu-id="2a23e-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="2a23e-173">创建 HoloLens 策略以替换 Intune 内的预配程序包。</span><span class="sxs-lookup"><span data-stu-id="2a23e-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="2a23e-174">创建 HoloLens Intune 策略。</span><span class="sxs-lookup"><span data-stu-id="2a23e-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="2a23e-175">向正确的组分配设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="2a23e-176">过程</span><span class="sxs-lookup"><span data-stu-id="2a23e-176">Process</span></span>

1. <span data-ttu-id="2a23e-177">将 USB-C 集线器和以太网缆线插入 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="2a23e-178">打开 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="2a23e-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="2a23e-179">设备应通过以太网适配器在 OOBE 处自动连接到网络，检测 Autopilot 配置，并使用 Azure AD 和 Intune 自动注册</span><span class="sxs-lookup"><span data-stu-id="2a23e-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="2a23e-180">设备将根据需要通过 Intune 应用所需的 Wlan 证书和其他配置</span><span class="sxs-lookup"><span data-stu-id="2a23e-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="2a23e-181">完成后，技术人员将能够加载 Intune （终结点管理器）门户，并钻取到**主页 > 设备 -> 设备名称- > 硬件**的设备属性页面。</span><span class="sxs-lookup"><span data-stu-id="2a23e-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="2a23e-182">Wi-Fi MAC 地址将在 Intune 门户中可见</span><span class="sxs-lookup"><span data-stu-id="2a23e-182">The Wi-Fi MAC address will be visible within the Intune Portal</span></span>

![通过 Intune 检索 MAC 地址](images/mac-address-intune.jpg)

7. <span data-ttu-id="2a23e-184">技术人员将此 MAC 地址添加为允许的设备。</span><span class="sxs-lookup"><span data-stu-id="2a23e-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="2a23e-185">优势</span><span class="sxs-lookup"><span data-stu-id="2a23e-185">Benefits</span></span>

<span data-ttu-id="2a23e-186">这将允许技术人员获得&quot;直接的&quot; 部署体验，并且设备可以从盒中到 Azure AD 和 Intune 中注册，而技术人员无需佩戴设备或手动与 HoloLens 环境进行交互。</span><span class="sxs-lookup"><span data-stu-id="2a23e-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="2a23e-187">向技术人员报告 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="2a23e-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="2a23e-188">要求</span><span class="sxs-lookup"><span data-stu-id="2a23e-188">Requirements</span></span>

- <span data-ttu-id="2a23e-189">针对客户租户 &quot;Intune Graph PowerShell&quot; 进行授权</span><span class="sxs-lookup"><span data-stu-id="2a23e-189">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="2a23e-190">安装技术人员机器上的 Intune Graph PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2a23e-190">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="2a23e-191">Intune 元素&quot;托管设备&quot;的读取权限。</span><span class="sxs-lookup"><span data-stu-id="2a23e-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="2a23e-192">（支持人员过程调用或更高版本或自定义角色）</span><span class="sxs-lookup"><span data-stu-id="2a23e-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="2a23e-193">目前，还没有一种&quot;简单&quot;的方法来触发基于在Intune中注册新设备的自动命令。</span><span class="sxs-lookup"><span data-stu-id="2a23e-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="2a23e-194">因此，此命令将为技术人员提供一种检索 MAC 地址的简单方法，无需登录到门户并手动检索。</span><span class="sxs-lookup"><span data-stu-id="2a23e-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="2a23e-195">这将返回最近 30 天内已注册的任何 HoloLens 设备的名称和 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![通过 Powershell 检索 MAC 地址](images/mac-address-powershell.jpg)

### <span data-ttu-id="2a23e-197">过程</span><span class="sxs-lookup"><span data-stu-id="2a23e-197">Process</span></span>

<span data-ttu-id="2a23e-198">Intune 注册完成后，技术人员将运行以上脚本检索 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2a23e-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
