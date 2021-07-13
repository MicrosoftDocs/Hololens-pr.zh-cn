---
title: 常见设备限制
description: 与 HoloLens 混合现实设备的常见设备限制和设置保持最新。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639210"
---
# <a name="common-device-restrictions"></a><span data-ttu-id="19c2c-103">常见设备限制</span><span class="sxs-lookup"><span data-stu-id="19c2c-103">Common Device Restrictions</span></span> 

<span data-ttu-id="19c2c-104">本指南可帮助 IT 专业人员了解适用于企业中的 Windows 10 全息版 OS 的更常用管理选项。</span><span class="sxs-lookup"><span data-stu-id="19c2c-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="19c2c-105">请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。</span><span class="sxs-lookup"><span data-stu-id="19c2c-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="19c2c-106">并非所有 MDM 系统都支持本指南中所述的每个设置。</span><span class="sxs-lookup"><span data-stu-id="19c2c-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="19c2c-107">一些系统通过 OMA-URI XML 文件支持自定义策略。</span><span class="sxs-lookup"><span data-stu-id="19c2c-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="19c2c-108">请参阅[对自定义策略的 Microsoft Intune 支持](/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="19c2c-108">See [Microsoft Intune support for Custom Policies](/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="19c2c-109">命名约定在各个 MDM 供应商之间可能也会不同。</span><span class="sxs-lookup"><span data-stu-id="19c2c-109">Naming conventions may also vary among MDM vendors.</span></span>

## <a name="prevent-changing-of-settings"></a><span data-ttu-id="19c2c-110">防止设置更改</span><span class="sxs-lookup"><span data-stu-id="19c2c-110">Prevent changing of settings</span></span>
<span data-ttu-id="19c2c-111">通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。</span><span class="sxs-lookup"><span data-stu-id="19c2c-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="19c2c-112">员工可以通过 "设置" UI 以交互方式调整 HoloLens 的某些设置。</span><span class="sxs-lookup"><span data-stu-id="19c2c-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="19c2c-113">使用 MDM，你可以限制允许用户更改的内容。</span><span class="sxs-lookup"><span data-stu-id="19c2c-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="19c2c-114">下面列出了 Windows 10 全息版支持配置设置限制的常用 MDM 设置：</span><span class="sxs-lookup"><span data-stu-id="19c2c-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="19c2c-115">[允许 VPN：](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置</span><span class="sxs-lookup"><span data-stu-id="19c2c-115">[Allow VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="19c2c-116">[允许手动配置 WiFi：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM 预配的网络以外建立 Wi-Fi 连接</span><span class="sxs-lookup"><span data-stu-id="19c2c-116">[Allow Manual WiFi Configuration:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="19c2c-117">[允许手动取消注册 mdm](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (例如，从 MDM 系统取消注册设备) </span><span class="sxs-lookup"><span data-stu-id="19c2c-117">[Allow Manual MDM Unenrollment](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="19c2c-118">添加到 HoloLens 2 设备[Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中：</span><span class="sxs-lookup"><span data-stu-id="19c2c-118">Added in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices:</span></span>
- <span data-ttu-id="19c2c-119">[允许添加预配包：](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 如果用户可以添加新的预配包，则切换，并将其替换为新值。</span><span class="sxs-lookup"><span data-stu-id="19c2c-119">[Allow Add Provisioning Package:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Toggle if users can add new provisioning packages, overwriting with new values.</span></span>
- <span data-ttu-id="19c2c-120">[允许删除预配包：](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 如果用户可以删除预配包，则切换，使其可以切换以前锁定的设置。</span><span class="sxs-lookup"><span data-stu-id="19c2c-120">[Allow Remove Provisioning Package:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Toggle if users can remove provisioning packages, allowing them to toggle previously locked settings.</span></span>

<span data-ttu-id="19c2c-121">在 HoloLens 支持的[策略 csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2)中查找有关策略选项的更多详细信息</span><span class="sxs-lookup"><span data-stu-id="19c2c-121">Find more details on policy options in the HoloLens supported [Policy CSPs](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <a name="hardware-restrictions"></a><span data-ttu-id="19c2c-122">硬件限制</span><span class="sxs-lookup"><span data-stu-id="19c2c-122">Hardware restrictions</span></span>
<span data-ttu-id="19c2c-123">Windows 10 全息版设备使用最先进的技术，其中包括相机、麦克风、扬声器、USB 接口、蓝牙接口和 wi-fi 等热门硬件功能。</span><span class="sxs-lookup"><span data-stu-id="19c2c-123">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="19c2c-124">可使用硬件限制控制这些功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="19c2c-124">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="19c2c-125">下面列出了 Windows 10 全息版支持配置硬件限制的常用 MDM 设置：</span><span class="sxs-lookup"><span data-stu-id="19c2c-125">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="19c2c-126">其中一些硬件限制会影响连接性，并帮助保护数据。</span><span class="sxs-lookup"><span data-stu-id="19c2c-126">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="19c2c-127">[允许 wi-fi：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用并使用 WiFi 收音机。</span><span class="sxs-lookup"><span data-stu-id="19c2c-127">[Allow Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="19c2c-128">[允许 USB 连接：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (不会影响 USB 充电 ) </span><span class="sxs-lookup"><span data-stu-id="19c2c-128">[Allow USB Connection:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="19c2c-129">[允许蓝牙：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)用户是否可以在其设备上启用并使用蓝牙收音机。</span><span class="sxs-lookup"><span data-stu-id="19c2c-129">[Allow Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="19c2c-130">[限制照相机：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera)指定 Windows 应用是否可以访问相机。</span><span class="sxs-lookup"><span data-stu-id="19c2c-130">[Restrict Camera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="19c2c-131">[限制麦克风：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone)指定 Windows 应用是否可以访问麦克风。</span><span class="sxs-lookup"><span data-stu-id="19c2c-131">[Restrict Microphones:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>

<span data-ttu-id="19c2c-132">添加到 HoloLens 2 设备的[Windows 全息版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中。</span><span class="sxs-lookup"><span data-stu-id="19c2c-132">Added in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> 
- <span data-ttu-id="19c2c-133">[DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 设置显示关闭后的时间长度，并关闭显示，锁定设备。</span><span class="sxs-lookup"><span data-stu-id="19c2c-133">[DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Set amount of time until display turns off, and by turning off the display, locks the device.</span></span> 
- <span data-ttu-id="19c2c-134">[DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 设置显示关闭后的时间长度，并关闭显示，锁定设备。</span><span class="sxs-lookup"><span data-stu-id="19c2c-134">[DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Set amount of time until display turns off, and by turning off the display, locks the device.</span></span> 
