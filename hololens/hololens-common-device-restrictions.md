---
title: 常见设备限制
description: 通常在 HoloLens 上设置的设备 restrctions。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016761"
---
# <span data-ttu-id="faf66-103">常见设备限制</span><span class="sxs-lookup"><span data-stu-id="faf66-103">Common Device Restrictions</span></span> 

<span data-ttu-id="faf66-104">本指南可帮助 IT 专业人员了解适用于企业中的 Windows 10 全息操作系统的更常用的管理选项。</span><span class="sxs-lookup"><span data-stu-id="faf66-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="faf66-105">请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。</span><span class="sxs-lookup"><span data-stu-id="faf66-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="faf66-106">并非所有 MDM 系统都支持本指南中所述的每个设置。</span><span class="sxs-lookup"><span data-stu-id="faf66-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="faf66-107">一些系统通过 OMA-URI XML 文件支持自定义策略。</span><span class="sxs-lookup"><span data-stu-id="faf66-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="faf66-108">请参阅[对自定义策略的 Microsoft Intune 支持](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="faf66-108">See [Microsoft Intune support for Custom Policies](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="faf66-109">命名约定在各个 MDM 供应商之间可能也会不同。</span><span class="sxs-lookup"><span data-stu-id="faf66-109">Naming conventions may also vary among MDM vendors.</span></span>

## <span data-ttu-id="faf66-110">防止设置更改</span><span class="sxs-lookup"><span data-stu-id="faf66-110">Prevent changing of settings</span></span>
<span data-ttu-id="faf66-111">通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。</span><span class="sxs-lookup"><span data-stu-id="faf66-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="faf66-112">员工可以通过 "设置" UI 以交互方式调整 HoloLens 的某些设置。</span><span class="sxs-lookup"><span data-stu-id="faf66-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="faf66-113">使用 MDM，你可以限制允许用户更改的内容。</span><span class="sxs-lookup"><span data-stu-id="faf66-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="faf66-114">以下列出了 Windows 10 全息支持配置设置限制的常用 MDM 设置：</span><span class="sxs-lookup"><span data-stu-id="faf66-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="faf66-115">[允许 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置</span><span class="sxs-lookup"><span data-stu-id="faf66-115">[Allow VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="faf66-116">[允许手动 WiFi 配置：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM 预配网络外建立 Wlan 连接</span><span class="sxs-lookup"><span data-stu-id="faf66-116">[Allow Manual WiFi Configuration:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="faf66-117">[允许手动取消注册](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (也就是说，从 MDM 系统取消注册设备) </span><span class="sxs-lookup"><span data-stu-id="faf66-117">[Allow Manual MDM Unenrollment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="faf66-118">在 HoloLens 支持的[策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中查找有关策略选项的更多详细信息</span><span class="sxs-lookup"><span data-stu-id="faf66-118">Find more details on policy options in the HoloLens supported [Policy CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <span data-ttu-id="faf66-119">硬件限制</span><span class="sxs-lookup"><span data-stu-id="faf66-119">Hardware restrictions</span></span>
<span data-ttu-id="faf66-120">Windows 10 全息版设备使用包含常用硬件功能（如相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-fi）的一流技术。</span><span class="sxs-lookup"><span data-stu-id="faf66-120">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="faf66-121">可使用硬件限制控制这些功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="faf66-121">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="faf66-122">以下列出了 Windows 10 全息支持配置硬件限制的常用 MDM 设置：</span><span class="sxs-lookup"><span data-stu-id="faf66-122">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="faf66-123">其中一些硬件限制会影响连接并帮助保护数据。</span><span class="sxs-lookup"><span data-stu-id="faf66-123">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="faf66-124">[允许 wi-fi：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用和使用 WiFi 收音机。</span><span class="sxs-lookup"><span data-stu-id="faf66-124">[Allow Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="faf66-125">[允许 USB 连接：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (不会影响 USB 收费。 ) </span><span class="sxs-lookup"><span data-stu-id="faf66-125">[Allow USB Connection:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="faf66-126">[允许蓝牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在其设备上启用和使用蓝牙收音机。</span><span class="sxs-lookup"><span data-stu-id="faf66-126">[Allow Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="faf66-127">[限制相机：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 应用是否可以访问相机。</span><span class="sxs-lookup"><span data-stu-id="faf66-127">[Restrict Camera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="faf66-128">[限制麦克风：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 应用是否可以访问麦克风。</span><span class="sxs-lookup"><span data-stu-id="faf66-128">[Restrict Microphones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>
