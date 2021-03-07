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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393836"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="14d9b-103">MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境</span><span class="sxs-lookup"><span data-stu-id="14d9b-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="14d9b-104">本文将介绍在客户环境中标识的一种常见方案，其中WLAN 受 MAC 地址的限制，或者需要证书来加入无线网络。</span><span class="sxs-lookup"><span data-stu-id="14d9b-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="14d9b-105">示例方案</span><span class="sxs-lookup"><span data-stu-id="14d9b-105">Example Scenario</span></span>

<span data-ttu-id="14d9b-106">安全环境中的许多客户对其无线或有线网络有限制，这将只允许批准的设备（基于 MAC 地址）成功连接。</span><span class="sxs-lookup"><span data-stu-id="14d9b-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="14d9b-107">这可以通过无线访问点上的 MAC 地址筛选或通过 DHCP 服务器强制执行。</span><span class="sxs-lookup"><span data-stu-id="14d9b-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="14d9b-108">此外，一些无线网络可通过 PEAP 进行保护，这要求在无线网络上进行身份验证之前，先将证书应用于设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="14d9b-109">在这种情况下，将 HoloLens 设备连接到网络时，两个关键要求可能会导致延迟或需要人工干预：</span><span class="sxs-lookup"><span data-stu-id="14d9b-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="14d9b-110">在设备成功加入无线网络之前必须将无线 PEAP 证书应用于设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="14d9b-111">必须注册 HoloLens WLAN 适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="14d9b-112">上述要求的核心挑战包括：</span><span class="sxs-lookup"><span data-stu-id="14d9b-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="14d9b-113">目前，MAC 地址只能从设备上的设置应用中标识，或在成功进行注册后从 Intune 标识。</span><span class="sxs-lookup"><span data-stu-id="14d9b-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="14d9b-114">没有 MAC 地址，设备就无法加入 WLAN 网络开始注册。</span><span class="sxs-lookup"><span data-stu-id="14d9b-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="14d9b-115">手动解决这些问题需要技术人员与设备交互。</span><span class="sxs-lookup"><span data-stu-id="14d9b-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="14d9b-116">解决方案</span><span class="sxs-lookup"><span data-stu-id="14d9b-116">Solutions</span></span>

<span data-ttu-id="14d9b-117">有许多方法可以改善这种情况，具体取决于环境中可用的基础设施。</span><span class="sxs-lookup"><span data-stu-id="14d9b-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="14d9b-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="14d9b-118">Solution</span></span> | <span data-ttu-id="14d9b-119">优势</span><span class="sxs-lookup"><span data-stu-id="14d9b-119">Benefits</span></span> | <span data-ttu-id="14d9b-120">要求</span><span class="sxs-lookup"><span data-stu-id="14d9b-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="14d9b-121">使用以太网适配器预配程序包</span><span class="sxs-lookup"><span data-stu-id="14d9b-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="14d9b-122">改进 OOBE 体验，更快地提供技术人员体验。</span><span class="sxs-lookup"><span data-stu-id="14d9b-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="14d9b-123">HoloLens 兼容的 USB C 集线器和以太网适配器，技术人员仍需与设备进行交互，以实现 MAC 捕获和 OOBE 最终定稿</span><span class="sxs-lookup"><span data-stu-id="14d9b-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="14d9b-124">Autopilot 在以太网上使用 Intune 注册</span><span class="sxs-lookup"><span data-stu-id="14d9b-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="14d9b-125">这是设备到客户环境的单步骤连接和注册。</span><span class="sxs-lookup"><span data-stu-id="14d9b-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="14d9b-126">MAC 捕获无需与设备交互即可完成</span><span class="sxs-lookup"><span data-stu-id="14d9b-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="14d9b-127">Intune 已为客户 AAD 租户和 HoloLens 兼容的 USB-C 以太网适配器启用</span><span class="sxs-lookup"><span data-stu-id="14d9b-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="14d9b-128">自动报告 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="14d9b-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="14d9b-129">在 Intune 租户中注册设备后，脚本可以将 MAC 地址报告给技术人员。</span><span class="sxs-lookup"><span data-stu-id="14d9b-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="14d9b-130">Intune Powershell Commandlets</span><span class="sxs-lookup"><span data-stu-id="14d9b-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="14d9b-131">使用以太网适配器预配程序包</span><span class="sxs-lookup"><span data-stu-id="14d9b-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="14d9b-132">如果有线网络还受 MAC 限制的约束，则需要预批准 USB-C 集线器和以太网适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="14d9b-133">请注意，这种适配器将允许从其他设备访问网络。</span><span class="sxs-lookup"><span data-stu-id="14d9b-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="14d9b-134">要求</span><span class="sxs-lookup"><span data-stu-id="14d9b-134">Requirements</span></span>

- <span data-ttu-id="14d9b-135">可访问客户网络的有线网络端口</span><span class="sxs-lookup"><span data-stu-id="14d9b-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="14d9b-136">HoloLens 兼容的 USB-C 集线器，含有一个以太网适配器 - 不&#39;需要任何额外的驱动程序或应用程序安装的任何适配器均适用。</span><span class="sxs-lookup"><span data-stu-id="14d9b-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="14d9b-137">预配程序包包括：</span><span class="sxs-lookup"><span data-stu-id="14d9b-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="14d9b-138">包含无线网络信息和证书</span><span class="sxs-lookup"><span data-stu-id="14d9b-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="14d9b-139">（可选）包含组织 Azure AD 的注册信息</span><span class="sxs-lookup"><span data-stu-id="14d9b-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="14d9b-140">包含所有其他必需的预配设置</span><span class="sxs-lookup"><span data-stu-id="14d9b-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="14d9b-141">过程</span><span class="sxs-lookup"><span data-stu-id="14d9b-141">Process</span></span>

<span data-ttu-id="14d9b-142">该过程可能有所不同，具体取决于设备的软件级别。</span><span class="sxs-lookup"><span data-stu-id="14d9b-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="14d9b-143">如果该设备已于 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，请遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="14d9b-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="14d9b-144">将预配程序包放到 USB 棒的根位置，然后插入集线器。</span><span class="sxs-lookup"><span data-stu-id="14d9b-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="14d9b-145">将以太网缆线连接到集线器和以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="14d9b-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="14d9b-146">将 USB-C 集线器连接到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="14d9b-147">打开 HoloLens，然后戴上设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="14d9b-148">按**音量和电源按钮**应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="14d9b-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="14d9b-149">技术人员现在可以按照 OOBE 操作，完成后打开设置应用，然后检索设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="14d9b-150">如果该设备在 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前进行了操作系统构建，请遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="14d9b-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="14d9b-151">打开 HoloLens，然后将设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="14d9b-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="14d9b-152">设备应在电脑上显示为文件存储设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="14d9b-153">预配程序包复制到设备</span><span class="sxs-lookup"><span data-stu-id="14d9b-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="14d9b-154">将以太网缆线连接到集线器。</span><span class="sxs-lookup"><span data-stu-id="14d9b-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="14d9b-155">将 USB-C 集线器连接到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="14d9b-156">戴上 HoloLens</span><span class="sxs-lookup"><span data-stu-id="14d9b-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="14d9b-157">按**音量和电源**按钮应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="14d9b-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="14d9b-158">技术人员现在可以按照 OOBE 操作，完成后打开设置应用，然后检索设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="14d9b-159">优势</span><span class="sxs-lookup"><span data-stu-id="14d9b-159">Benefits</span></span>

<span data-ttu-id="14d9b-160">这将允许设备&quot;单一触控&quot;应用正确的预配程序包并收集设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="14d9b-161">可按此指南创建预配程序包。</span><span class="sxs-lookup"><span data-stu-id="14d9b-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="14d9b-162">具有 Intune 注册的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="14d9b-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="14d9b-163">要求</span><span class="sxs-lookup"><span data-stu-id="14d9b-163">Requirements</span></span>

- <span data-ttu-id="14d9b-164">可访问客户网络的有线网络端口</span><span class="sxs-lookup"><span data-stu-id="14d9b-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="14d9b-165">运行 Windows Holographic 2004 的 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="14d9b-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="14d9b-166">HoloLens 兼容的 USB-C 以太网适配器</span><span class="sxs-lookup"><span data-stu-id="14d9b-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="14d9b-167">已为客户租户设置并启用 Intune</span><span class="sxs-lookup"><span data-stu-id="14d9b-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="14d9b-168">为 Autopilot 注册并导入客户租户的设备</span><span class="sxs-lookup"><span data-stu-id="14d9b-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="14d9b-169">已为设备定义 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="14d9b-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="14d9b-170">包含无线网络信息和证书</span><span class="sxs-lookup"><span data-stu-id="14d9b-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="14d9b-171">包含所有其他必需的预配设置</span><span class="sxs-lookup"><span data-stu-id="14d9b-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="14d9b-172">这将允许有高级网络需求的客户以一种不干涉的、可伸缩的方式注册设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="14d9b-173">需要更多先决条件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="14d9b-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="14d9b-174">为 Autopilot 预览版启用租户</span><span class="sxs-lookup"><span data-stu-id="14d9b-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="14d9b-175">创建 HoloLens 策略以替换 Intune 内的预配程序包。</span><span class="sxs-lookup"><span data-stu-id="14d9b-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="14d9b-176">创建 HoloLens Intune 策略。</span><span class="sxs-lookup"><span data-stu-id="14d9b-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="14d9b-177">向正确的组分配设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="14d9b-178">过程</span><span class="sxs-lookup"><span data-stu-id="14d9b-178">Process</span></span>

1. <span data-ttu-id="14d9b-179">将以太网电缆连接到适配器，然后将适配器插入 HoloLens 2 设备上的 USB-C 端口。</span><span class="sxs-lookup"><span data-stu-id="14d9b-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="14d9b-180">打开 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="14d9b-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="14d9b-181">设备应在 OOBE 期间通过以太网适配器自动连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="14d9b-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="14d9b-182">它应检测 Autopilot 配置，并自动向 Azure AD 和 Intune 注册</span><span class="sxs-lookup"><span data-stu-id="14d9b-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="14d9b-183">设备将根据需要通过 Intune 应用所需的 Wlan 证书和其他配置</span><span class="sxs-lookup"><span data-stu-id="14d9b-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="14d9b-184">完成后，技术人员可加载 Intune （终结点管理器）门户，并钻取到**主页 > 设备 -> 设备名称- > 硬件**的设备属性页面。</span><span class="sxs-lookup"><span data-stu-id="14d9b-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="14d9b-185">Wifi MAC 地址将显示在 Intune 门户中</span><span class="sxs-lookup"><span data-stu-id="14d9b-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![通过 Intune 检索 MAC 地址](images/mac-address-intune.jpg)

7. <span data-ttu-id="14d9b-187">技术人员将此 MAC 地址添加为允许的设备。</span><span class="sxs-lookup"><span data-stu-id="14d9b-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="14d9b-188">优势</span><span class="sxs-lookup"><span data-stu-id="14d9b-188">Benefits</span></span>

<span data-ttu-id="14d9b-189">这将允许技术人员获得&quot;直接的&quot; 部署体验，并且设备可以从盒中到 Azure AD 和 Intune 中注册，而技术人员无需佩戴设备或手动与 HoloLens 环境进行交互。</span><span class="sxs-lookup"><span data-stu-id="14d9b-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="14d9b-190">向技术人员报告 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="14d9b-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="14d9b-191">要求</span><span class="sxs-lookup"><span data-stu-id="14d9b-191">Requirements</span></span>

- <span data-ttu-id="14d9b-192">针对客户租户 &quot;Intune Graph PowerShell&quot; 进行授权</span><span class="sxs-lookup"><span data-stu-id="14d9b-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="14d9b-193">安装技术人员机器上的 Intune Graph PowerShell。</span><span class="sxs-lookup"><span data-stu-id="14d9b-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="14d9b-194">Intune 元素&quot;托管设备&quot;的读取权限。</span><span class="sxs-lookup"><span data-stu-id="14d9b-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="14d9b-195">（支持人员过程调用或更高版本或自定义角色）</span><span class="sxs-lookup"><span data-stu-id="14d9b-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="14d9b-196">目前，还没有一种&quot;简单&quot;的方法来触发基于在Intune中注册新设备的自动命令。</span><span class="sxs-lookup"><span data-stu-id="14d9b-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="14d9b-197">因此，此命令将为技术人员提供一种检索 MAC 地址的简单方法，无需登录到门户并手动检索。</span><span class="sxs-lookup"><span data-stu-id="14d9b-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="14d9b-198">这将返回最近 30 天内已注册的任何 HoloLens 设备的名称和 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![通过 Powershell 检索 MAC 地址](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="14d9b-200">过程</span><span class="sxs-lookup"><span data-stu-id="14d9b-200">Process</span></span>

<span data-ttu-id="14d9b-201">Intune 注册完成后，技术人员将运行以上脚本检索 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="14d9b-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
