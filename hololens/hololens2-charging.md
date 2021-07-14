---
title: HoloLens 2 电池和充电
description: 如何对 HoloLens 进行充电并使用外部电池组。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923578"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="17d8f-103">HoloLens 2 电池和充电</span><span class="sxs-lookup"><span data-stu-id="17d8f-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="17d8f-104">本页提供有关 HoloLens 2 充电和使用外部电池组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="17d8f-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="17d8f-105">对设备充电</span><span class="sxs-lookup"><span data-stu-id="17d8f-105">Charging the device</span></span>

<span data-ttu-id="17d8f-106">使用 HoloLens 2 自带的[充电器和 USB Type-C 线缆](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因为这是设备充电的最快途径。</span><span class="sxs-lookup"><span data-stu-id="17d8f-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="17d8f-107">HoloLens 2 附带的充电器提供最多 9V @ 2A (18W)。</span><span class="sxs-lookup"><span data-stu-id="17d8f-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="17d8f-108">借助提供的壁式充电器，HoloLens 2 设备可在待机状态下在 65 分钟内将电池充满电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="17d8f-109">如果这些附件不可用，请确保可用的充电器支持至少 15W 的功率。</span><span class="sxs-lookup"><span data-stu-id="17d8f-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="17d8f-110">如果可能，请避免使用电脑通过 USB 给设备充电（速度很慢）。</span><span class="sxs-lookup"><span data-stu-id="17d8f-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="17d8f-111">检查电池电量</span><span class="sxs-lookup"><span data-stu-id="17d8f-111">Checking the battery charge level</span></span>
<span data-ttu-id="17d8f-112">如果设备已正确启动且运行，有三种方法可以检查电池电量：</span><span class="sxs-lookup"><span data-stu-id="17d8f-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="17d8f-113">从 HoloLens 设备 UI 的主菜单。</span><span class="sxs-lookup"><span data-stu-id="17d8f-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="17d8f-114">查看靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。</span><span class="sxs-lookup"><span data-stu-id="17d8f-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="17d8f-115">为设备充电时，电池指示灯将亮起，以指示当前的充电进度。</span><span class="sxs-lookup"><span data-stu-id="17d8f-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="17d8f-116">最后一盏灯将不停闪烁，表示正在充电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="17d8f-117">当 HoloLens 处于打开状态时，电池指示灯以五个增量方式显示电池剩余电量。</span><span class="sxs-lookup"><span data-stu-id="17d8f-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="17d8f-118">当五盏灯中只有一盏亮起时，表示电池剩余电量低于 20%。</span><span class="sxs-lookup"><span data-stu-id="17d8f-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="17d8f-119">如果在电池剩余电量严重不足时你尝试打开设备，则一盏灯将会短暂闪烁，然后熄灭。</span><span class="sxs-lookup"><span data-stu-id="17d8f-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="17d8f-120">在主机上，打开“文件资源管理器”，然后在左侧的“这台电脑”下查找 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="17d8f-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="17d8f-121">右键单击该设备，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="17d8f-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="17d8f-122">对话框将显示电池电量。</span><span class="sxs-lookup"><span data-stu-id="17d8f-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 属性屏幕显示电量变化情况](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="17d8f-124">备选充电规范</span><span class="sxs-lookup"><span data-stu-id="17d8f-124">Alternative charging specifications</span></span>

<span data-ttu-id="17d8f-125">[USB 电力输送](https://www.usb.org/usb-charger-pd)源最多可为 HoloLens 2 充入 27 瓦电量。</span><span class="sxs-lookup"><span data-stu-id="17d8f-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="17d8f-126">如果源至少能提供 10 瓦，HoloLens 的工作时间可以延长（某些工作负载可能无限期）。</span><span class="sxs-lookup"><span data-stu-id="17d8f-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="17d8f-127">使用 USB-A 到 USB-C 充电线缆会将充电限制为 7.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="17d8f-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="17d8f-128">工作时间仍会延长，但前提是使用 USB-C 到 C。</span><span class="sxs-lookup"><span data-stu-id="17d8f-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="17d8f-129">当 HoloLens 处于待机模式时，18 瓦足以达到内部电池的最大充电率。</span><span class="sxs-lookup"><span data-stu-id="17d8f-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="17d8f-130">如果 HoloLens 正在使用中，则可能会降低充电率，因为 HoloLens 会优先考虑操作而不是充电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17d8f-131">建议至少在 5V/1.5A 下对 HoloLens 2 进行充电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="17d8f-132">不能使用无法提供至少 5V/1.5A 的充电器。</span><span class="sxs-lookup"><span data-stu-id="17d8f-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="17d8f-133">外部电池组</span><span class="sxs-lookup"><span data-stu-id="17d8f-133">External Battery Packs</span></span>

<span data-ttu-id="17d8f-134">满足上述规范的电池组可用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="17d8f-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="17d8f-135">但请注意，某些 USB-C 电池组会再次充电，并通过相同的 USB-C 端口供电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="17d8f-136">这些电池组务必要要实现 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)，确保它们是对 HoloLens 充电，而不是从中充电。</span><span class="sxs-lookup"><span data-stu-id="17d8f-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="17d8f-137">热管理</span><span class="sxs-lookup"><span data-stu-id="17d8f-137">Managing Heat</span></span>

<span data-ttu-id="17d8f-138">与任何设备一样，HoloLens 充电会产生热量。</span><span class="sxs-lookup"><span data-stu-id="17d8f-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="17d8f-139">充电越快，生成的热量越多。</span><span class="sxs-lookup"><span data-stu-id="17d8f-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="17d8f-140">此外，在电池电量较低的情况下开始充电会比电池几乎全满时开始充电产生更多热量。</span><span class="sxs-lookup"><span data-stu-id="17d8f-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="17d8f-141">需要在热环境中长时间运行 HoloLens 的客户可以使用以下技术：</span><span class="sxs-lookup"><span data-stu-id="17d8f-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="17d8f-142">即使内部电池完全充电，也可以将 HoloLens 2 连接到外部电源。</span><span class="sxs-lookup"><span data-stu-id="17d8f-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="17d8f-143">当外部电池电量耗尽时，HoloLens 将继续运行其内部电池。</span><span class="sxs-lookup"><span data-stu-id="17d8f-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="17d8f-144">如果在执行上述步骤后仍存在发热问题，请考虑使用将充电限制为 1.5A 的充电器或电池组。</span><span class="sxs-lookup"><span data-stu-id="17d8f-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="17d8f-145">请注意，由于内部电池仍将缓慢耗尽，这个选项不会提供足够的运行时间。</span><span class="sxs-lookup"><span data-stu-id="17d8f-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="17d8f-146">疑难解答</span><span class="sxs-lookup"><span data-stu-id="17d8f-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="17d8f-147">HoloLens 对外部电池进行充电</span><span class="sxs-lookup"><span data-stu-id="17d8f-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="17d8f-148">如果 HoloLens 2 向外部电池充电而不是通过外部电池充电，则表明电池不能实现 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。</span><span class="sxs-lookup"><span data-stu-id="17d8f-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="17d8f-149">若要解决此问题，建议切换到较新的电池组，但也可以尝试切换到 USB-A 到 USB-C 线缆。</span><span class="sxs-lookup"><span data-stu-id="17d8f-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="17d8f-150">请记住，这会将充电率限制为 7.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="17d8f-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
