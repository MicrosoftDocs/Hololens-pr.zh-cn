---
title: 全局分配的访问权限
description: 开始使用我们的指南，通过 Intune 和 Windows 配置设计器将 OMA-URI 用于全局分配的访问权限展台。
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283173"
---
# <span data-ttu-id="0bc85-104">全局分配的访问权限 – 展台</span><span class="sxs-lookup"><span data-stu-id="0bc85-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="0bc85-105">此功能配置适用于多应用展台模式的 HoloLens 2 设备，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。</span><span class="sxs-lookup"><span data-stu-id="0bc85-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="0bc85-106">此功能目前仅适用于 Windows 预览体验成员版本。</span><span class="sxs-lookup"><span data-stu-id="0bc85-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="0bc85-107">如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [ Windows 预览体验成员](hololens-insider.md)版本的更多信息。</span><span class="sxs-lookup"><span data-stu-id="0bc85-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="0bc85-108">如何在 Intune 中使用全局分配的访问权限？</span><span class="sxs-lookup"><span data-stu-id="0bc85-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="0bc85-109">请注意标记有 "<!-" 的区域。</span><span class="sxs-lookup"><span data-stu-id="0bc85-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="0bc85-110">这些区域将要求你根据自己的偏好进行修改。</span><span class="sxs-lookup"><span data-stu-id="0bc85-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="0bc85-111">按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：</span><span class="sxs-lookup"><span data-stu-id="0bc85-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="0bc85-112">URI 值：./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="0bc85-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![Intune 中全局分配的访问权限 OMA URI](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="0bc85-114">对于数值，请更新并粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="0bc85-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="0bc85-115">如何在 Windows 配置设计器中使用全局分配的访问权限？</span><span class="sxs-lookup"><span data-stu-id="0bc85-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="0bc85-116">更新并保存上面提及的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0bc85-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="0bc85-117">请按照[使用预配包设置单应用或多应用展台](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作，特别是“预配</span><span class="sxs-lookup"><span data-stu-id="0bc85-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="0bc85-118">程序包，步骤 2 – 向预配包添加展台配置 XML 文件”一节并参考上一步中保存的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0bc85-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="0bc85-119">我可以创建一个配置，其中全局应用于所有人，单独的配置应用于 1 个 Azure AD 帐户或 Azure AD 组吗？</span><span class="sxs-lookup"><span data-stu-id="0bc85-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="0bc85-120">可以，请参阅下面的示例 XML blob。</span><span class="sxs-lookup"><span data-stu-id="0bc85-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="0bc85-121">如果未找到登录用户的特定用户，则全局分配的访问权限配置文件将应用于 HoloLens，因此它是登录用户的默认展台模式配置。</span><span class="sxs-lookup"><span data-stu-id="0bc85-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="0bc85-122">下面是要使用的 XML blob 示例：</span><span class="sxs-lookup"><span data-stu-id="0bc85-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="0bc85-123">请注意标记有 `<!-` 的突出显示的区域。</span><span class="sxs-lookup"><span data-stu-id="0bc85-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="0bc85-124">这些区域将要求你根据自己的偏好进行修改。</span><span class="sxs-lookup"><span data-stu-id="0bc85-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="0bc85-125">从全局分配的访问配置文件中排除设备所有者</span><span class="sxs-lookup"><span data-stu-id="0bc85-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="0bc85-126">此功能允许在 HoloLens 上被视为“ [设备所有者](security-adminless-os.md)”的用户被排除在全局分配的访问权限之外。</span><span class="sxs-lookup"><span data-stu-id="0bc85-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="0bc85-127">若要使用此功能，请在适用于多应用程序展台配置的 XML blob 中，确保添加突出显示的行：</span><span class="sxs-lookup"><span data-stu-id="0bc85-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="0bc85-128">其他的全局指定访问示例</span><span class="sxs-lookup"><span data-stu-id="0bc85-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="0bc85-129">这是示例全局分配访问网亭，当任何用户登录时，他们将拥有一个多应用网亭，其中包含设置应用程序、反馈中心和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0bc85-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="0bc85-130">此示例是全局分配的访问网亭，不包括设备所有者，当任何其他 Azure AD 用户登录时，他们将拥有带有设置应用程序、反馈中心和 Microsoft Edge 的多应用程序网亭。</span><span class="sxs-lookup"><span data-stu-id="0bc85-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="0bc85-131">此网亭还包括访客帐户的辅助信息网亭配置，任何人都可以在锁屏上登录。</span><span class="sxs-lookup"><span data-stu-id="0bc85-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="0bc85-132">用户登录到访问者帐户时，将拥有一个仅有反馈中心应用的多应用应用程序。</span><span class="sxs-lookup"><span data-stu-id="0bc85-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
