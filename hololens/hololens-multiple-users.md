---
title: 与多人共享 HoloLens
description: 你可以将 HoloLens 配置为由多个 Azure Active Directory 帐户或使用单个帐户的多个用户共享。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827979"
---
# <span data-ttu-id="84e30-103">与多人共享 HoloLens</span><span class="sxs-lookup"><span data-stu-id="84e30-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="84e30-104">与很多人共享一个 HoloLens 或让多个用户共享一组 HoloLens 设备很常见。</span><span class="sxs-lookup"><span data-stu-id="84e30-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="84e30-105">本文介绍了可用于共享设备的不同方式。</span><span class="sxs-lookup"><span data-stu-id="84e30-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="84e30-106">与多人共享，每个人都使用自己的帐户</span><span class="sxs-lookup"><span data-stu-id="84e30-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="84e30-107">**先决条件**： HoloLens 设备必须运行 Windows 10 版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="84e30-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="84e30-108">HoloLens （第1代）也需要[升级到 Windows 全息版企业](hololens-upgrade-enterprise.md)版。</span><span class="sxs-lookup"><span data-stu-id="84e30-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="84e30-109">当他们使用自己的 Azure Active Directory （Azure AD）帐户时，多个用户可以在设备上保留自己的用户设置和用户数据。</span><span class="sxs-lookup"><span data-stu-id="84e30-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="84e30-110">若要确保多人可以在 HoloLens 上使用自己的帐户，请按照以下步骤进行配置：</span><span class="sxs-lookup"><span data-stu-id="84e30-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="84e30-111">请确保设备运行的是 Windows 10 版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="84e30-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="84e30-112">如果您使用的是 HoloLens （第1代）设备，请将[设备升级到 Windows 全息版 For Business](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="84e30-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="84e30-113">设置设备时，请选择 **"我的工作或学校拥有它**"，然后使用 Azure AD 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="84e30-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="84e30-114">完成设置后，请确保帐户设置（**设置**  >  **帐户**）包括**其他用户**。</span><span class="sxs-lookup"><span data-stu-id="84e30-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="84e30-115">若要使用 HoloLens，每个用户都可以按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="84e30-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="84e30-116">如果其他用户已使用该设备，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="84e30-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="84e30-117">按下 "电源" 按钮，转到 "待机"，然后再次按 "电源" 按钮以返回到锁屏界面</span><span class="sxs-lookup"><span data-stu-id="84e30-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="84e30-118">HoloLens 2 用户可以从 "开始" 菜单中选择 "用户" 磁贴来注销当前用户。</span><span class="sxs-lookup"><span data-stu-id="84e30-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="84e30-119">使用 Azure AD 帐户凭据登录到设备。</span><span class="sxs-lookup"><span data-stu-id="84e30-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="84e30-120">如果这是你首次使用该设备，则必须将 HoloLens[校准](hololens-calibration.md)到你自己的眼睛。</span><span class="sxs-lookup"><span data-stu-id="84e30-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="84e30-121">若要查看设备用户列表或从设备中删除用户，请转到 " **Settings**  >  **Accounts**  >  **其他用户**的设置帐户"。</span><span class="sxs-lookup"><span data-stu-id="84e30-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="84e30-122">与多人共享，所有使用同一个帐户</span><span class="sxs-lookup"><span data-stu-id="84e30-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="84e30-123">多个用户也可以在使用单个用户帐户时共享 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="84e30-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="84e30-124">**在 HoloLens 2 上**，当新用户首次将设备放在其头上时（在保持相同帐户登录的同时），设备会提示新用户快速校准和个性化查看体验。</span><span class="sxs-lookup"><span data-stu-id="84e30-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="84e30-125">设备可以存储校准信息，以便将来的设备可以自动优化质量并舒适了解每个用户的观看体验。</span><span class="sxs-lookup"><span data-stu-id="84e30-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="84e30-126">用户无需再次校准设备。</span><span class="sxs-lookup"><span data-stu-id="84e30-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="84e30-127">**在 HoloLens （第1代）上**共享帐户的用户需要在 "设置" 应用中要求重新校准。</span><span class="sxs-lookup"><span data-stu-id="84e30-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="84e30-128">阅读有关[校准](hololens-calibration.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="84e30-128">Read more about [calibration](hololens-calibration.md).</span></span>
