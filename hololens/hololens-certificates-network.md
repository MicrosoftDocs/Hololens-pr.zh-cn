---
title: 为 HoloLens 2 准备证书和网络配置文件
description: 了解如何在 HoloLens 2 混合现实设备上对网络的证书进行配置、使用、部署和疑难解答。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639261"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a><span data-ttu-id="e7c95-103">为 HoloLens 2 准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="e7c95-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="e7c95-104">基于证书的身份验证是使用 HoloLens 2 的客户的常见要求。</span><span class="sxs-lookup"><span data-stu-id="e7c95-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="e7c95-105">你可能需要证书才能访问 Wi-Fi、连接到 VPN 解决方案或访问组织中的内部资源。</span><span class="sxs-lookup"><span data-stu-id="e7c95-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="e7c95-106">由于 HoloLens 2 设备通常已加入 Azure Active Directory (Azure AD) 并且由 Intune 或其他 MDM 提供程序进行管理，因此你将需要使用简单证书注册协议 (SCEP) 或与你的 MDM 解决方案集成的公钥加密标准 (PKCS) 证书来部署此类证书。</span><span class="sxs-lookup"><span data-stu-id="e7c95-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> 

>[!NOTE]
> <span data-ttu-id="e7c95-107">如果没有 MDM 提供程序，仍可以通过在 [Windows 配置设计器](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)中[预配包](hololens-provisioning.md#steps-for-creating-provisioning-packages)或在[证书管理器](certificate-manager.md)中转到“设置”>“更新和安全”>“证书管理器”来部署证书。</span><span class="sxs-lookup"><span data-stu-id="e7c95-107">If you do not have an MDM provider, you can still deploy certificates via a [provisioning package](hololens-provisioning.md#steps-for-creating-provisioning-packages) in [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) or through [Certificate Manager](certificate-manager.md) by going to **Settings > Update & Security > Certificate Manager**.</span></span>

## <a name="certificate-requirements"></a><span data-ttu-id="e7c95-108">证书要求</span><span class="sxs-lookup"><span data-stu-id="e7c95-108">Certificate requirements</span></span>
<span data-ttu-id="e7c95-109">需要根证书才能通过 SCEP 或 PKCS 基础结构部署证书。</span><span class="sxs-lookup"><span data-stu-id="e7c95-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="e7c95-110">你的组织中的其他应用程序和服务可能还需要将根证书部署到 HoloLens 2 设备上。</span><span class="sxs-lookup"><span data-stu-id="e7c95-110">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="e7c95-111">Wi-Fi 连接要求</span><span class="sxs-lookup"><span data-stu-id="e7c95-111">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="e7c95-112">为了自动为设备提供企业网络所需的 Wi-Fi 配置，你需要一个 Wi-Fi 配置配置文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-112">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="e7c95-113">你可以配置 Intune 或其他 MDM 提供程序以将这些配置文件部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="e7c95-113">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="e7c95-114">如果你的网络安全要求设备是本地域的一部分，则你可能还需要评估 Wi-Fi 网络基础结构，以确保它与 HoloLens 2 设备兼容（HoloLens 2 设备仅加入 Azure AD）。</span><span class="sxs-lookup"><span data-stu-id="e7c95-114">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="e7c95-115">部署证书基础结构</span><span class="sxs-lookup"><span data-stu-id="e7c95-115">Deploy certificate infrastructure</span></span>
<span data-ttu-id="e7c95-116">如果未存在 SCEP 或 PKCS 基础结构，则需要准备一个。</span><span class="sxs-lookup"><span data-stu-id="e7c95-116">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="e7c95-117">若要支持使用 SCEP 或 PKCS 证书进行身份验证，则 Intune 需要使用[证书连接器](/mem/intune/protect/certificate-connectors)。</span><span class="sxs-lookup"><span data-stu-id="e7c95-117">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="e7c95-118">结合使用 SCEP 和 Microsoft CA 时，你还必须配置[网络设备注册服务 (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span><span class="sxs-lookup"><span data-stu-id="e7c95-118">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="e7c95-119">有关详细信息，请参阅[在 Microsoft Intune 中为设备配置证书配置文件。](/intune/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="e7c95-119">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](/intune/certificates-configure)</span></span>

## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="e7c95-120">部署证书和 Wi-Fi/VPN 配置文件</span><span class="sxs-lookup"><span data-stu-id="e7c95-120">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="e7c95-121">若要部署证书和配置文件，请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="e7c95-121">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="e7c95-122">为每个根证书和中间证书创建一个配置文件（请参阅[创建受信任的证书配置文件](/intune/protect/certificates-configure#create-trusted-certificate-profiles)。）这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。</span><span class="sxs-lookup"><span data-stu-id="e7c95-122">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="e7c95-123">将不会部署无到期日期的证书配置文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-123">**Certificate profiles without an expiration date will not be deployed.**</span></span>
1.  <span data-ttu-id="e7c95-124">为每个 SCEP 或 PKCS 证书创建一个配置文件（请参阅[创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。</span><span class="sxs-lookup"><span data-stu-id="e7c95-124">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="e7c95-125">将不会部署无到期日期的证书配置文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-125">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7c95-126">由于 HoloLens 2 将多个设备视为一个共享设备，并且每个设备上有多个用户，因此建议尽可能部署设备证书（而不是用户证书）进行 Wi-Fi 身份验证</span><span class="sxs-lookup"><span data-stu-id="e7c95-126">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="e7c95-127">为每个公司 Wi-Fi 网络创建配置文件（请参阅 [Windows 10 和更高版本设备的 Wi-Fi 设置](/intune/wi-fi-settings-windows)）。</span><span class="sxs-lookup"><span data-stu-id="e7c95-127">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="e7c95-128">建议尽可能将 Wi-Fi 配置文件[分配](/mem/intune/configuration/device-profile-assign)到设备组，而不是用户组。</span><span class="sxs-lookup"><span data-stu-id="e7c95-128">It is recommended that the Wi-Fi profile be [assigned](/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

    > [!TIP]
    > <span data-ttu-id="e7c95-129">此外，还可从公司网络上的 Windows 10 电脑导出有效的 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-129">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="e7c95-130">此导出将创建包含所有当前设置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-130">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="e7c95-131">然后，将此文件导入到 Intune 中，并将其用作 HoloLens 2 设备的 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="e7c95-131">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="e7c95-132">请参阅[导出和导入 Windows 设备的 Wi-Fi 设置。](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span><span class="sxs-lookup"><span data-stu-id="e7c95-132">See [Export and import Wi-Fi settings for Windows devices.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="e7c95-133">为每个公司 VPN 创建配置文件（请参阅 [Windows 10 和 Windows 全息版设备设以使用 Intune 添加 VPN 连接](/intune/vpn-settings-windows-10)）。</span><span class="sxs-lookup"><span data-stu-id="e7c95-133">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/intune/vpn-settings-windows-10)).</span></span>

## <a name="troubleshooting-certificates"></a><span data-ttu-id="e7c95-134">证书疑难解答</span><span class="sxs-lookup"><span data-stu-id="e7c95-134">Troubleshooting certificates</span></span>

<span data-ttu-id="e7c95-135">如果你需要验证是否正确部署了证书，请使用设备上的[证书管理器](certificate-manager.md)验证你的证书是否存在。</span><span class="sxs-lookup"><span data-stu-id="e7c95-135">In the event that you need to validate that a certificate is deployed correctly please use the [Certificate Manager](certificate-manager.md) on the device to verify your certificate is present.</span></span>  

>[!WARNING]
> <span data-ttu-id="e7c95-136">虽然可以在证书管理器中查看 MDM 部署的证书，但是无法在证书管理器中将其卸载。</span><span class="sxs-lookup"><span data-stu-id="e7c95-136">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="e7c95-137">必须通过 MDM 将其卸载。</span><span class="sxs-lookup"><span data-stu-id="e7c95-137">You must uninstall them through MDM.</span></span>


