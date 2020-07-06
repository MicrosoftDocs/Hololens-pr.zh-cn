---
title: HoloLens 的环境注意事项
description: 为眼睛和环境优化设备时使用 HoloLens 获取可能的最佳体验。 为了支持跟踪，许多不同的环境因素融合在了一起，但是作为一位混合现实开发人员，你可以记住一些因素来优化空间以获取更好的全息影像。
keywords: 全息框, 视野, fov, 校准, 空间, 环境, 操作方法
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d2bec32e118ee1c9307b56fad99b7e8859e2a94d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827681"
---
# <span data-ttu-id="c4cce-105">HoloLens 的环境注意事项</span><span class="sxs-lookup"><span data-stu-id="c4cce-105">Environment considerations for HoloLens</span></span>

<span data-ttu-id="c4cce-106">HoloLens 可将全息影像与“真实”世界融合在一起，并将全息影像放在周围环境中。</span><span class="sxs-lookup"><span data-stu-id="c4cce-106">HoloLens blends the holographic with the "real" world, placing holograms in your surroundings.</span></span> <span data-ttu-id="c4cce-107">全息应用窗口“挂”在墙上，全息芭蕾舞演员在桌面上旋转，兔子的耳朵安放在不知情的好友头顶上。</span><span class="sxs-lookup"><span data-stu-id="c4cce-107">A holographic app window "hangs" on the wall, a holographic ballerina spins on the tabletop, bunny ears sit on top of your unwitting friend’s head.</span></span> <span data-ttu-id="c4cce-108">使用沉浸式游戏或应用时，全息世界将扩展到周围的环境中，但你仍可以在空间中四处查看和移动。</span><span class="sxs-lookup"><span data-stu-id="c4cce-108">When you’re using an immersive game or app, the holographic world will spread to fill your surroundings but you’ll still be able to see and move around the space.</span></span>

<span data-ttu-id="c4cce-109">你放置的全息影像将保留在所放置的位置，即使你关闭了设备也是如此。</span><span class="sxs-lookup"><span data-stu-id="c4cce-109">The holograms you place will stay where you’ve put them, even if you turn off your device.</span></span>

## <span data-ttu-id="c4cce-110">设置环境</span><span class="sxs-lookup"><span data-stu-id="c4cce-110">Setting up an environment</span></span>

<span data-ttu-id="c4cce-111">HoloLens 设备知道如何在空间中*跟踪*用户以放置稳定且准确的全息影像。</span><span class="sxs-lookup"><span data-stu-id="c4cce-111">HoloLens devices know how to place stable and accurate holograms by *tracking* users in a space.</span></span> <span data-ttu-id="c4cce-112">如果未正确跟踪，则设备无法了解环境或其中的用户，因此，全息影像可能会出现在错误的位置，不会每次都出现在同一地点，或者根本不会出现。</span><span class="sxs-lookup"><span data-stu-id="c4cce-112">Without proper tracking, the device does not understand the environment or the user within it so holograms can appear in the wrong places, not appear in the same spot every time, or not appear at all.</span></span> <span data-ttu-id="c4cce-113">*空间地图*中呈现了用于跟踪用户的数据。</span><span class="sxs-lookup"><span data-stu-id="c4cce-113">The data used to track users is represented in the *spatial map*.</span></span>  

<span data-ttu-id="c4cce-114">用户所在的环境会严重影响跟踪性能，调优环境以产生稳定且一致的跟踪效果是一门艺术，而不是一种科学。</span><span class="sxs-lookup"><span data-stu-id="c4cce-114">Tracking performance is heavily influenced by the environment the user is in, and tuning an environment to induce stable and consistent tracking is an art rather than a science.</span></span> <span data-ttu-id="c4cce-115">为了支持跟踪，许多不同的环境因素融合在了一起，但是作为一位混合现实开发人员，你可以记住一些因素来优化空间以获得更好的跟踪效果。</span><span class="sxs-lookup"><span data-stu-id="c4cce-115">Many different environmental factors are fused together to enable tracking, but as a Mixed Reality developer, there are several factors you can keep in mind to tune a space for better tracking.</span></span>

### <span data-ttu-id="c4cce-116">照明</span><span class="sxs-lookup"><span data-stu-id="c4cce-116">Lighting</span></span>

<span data-ttu-id="c4cce-117">Windows Mixed Reality 使用可见光跟踪用户的位置。</span><span class="sxs-lookup"><span data-stu-id="c4cce-117">Windows Mixed Reality uses visual light to track the user's location.</span></span> <span data-ttu-id="c4cce-118">当环境太亮时，相机可能会光线饱和，因此看不到任何内容。</span><span class="sxs-lookup"><span data-stu-id="c4cce-118">When an environment is too bright, the cameras can get saturated, and nothing is seen.</span></span> <span data-ttu-id="c4cce-119">如果环境太暗，相机将无法获得足够的信息，那么将看不到任何内容。</span><span class="sxs-lookup"><span data-stu-id="c4cce-119">If the environment is too dark, the cameras cannot pick up enough information, and nothing is seen.</span></span> <span data-ttu-id="c4cce-120">照明应均匀且足够亮，使人们无需费力就能看到东西；但又不能亮得让人难以看清光线。</span><span class="sxs-lookup"><span data-stu-id="c4cce-120">Lighting should be even and sufficiently bright that a human can see without effort, but not so bright that the light is painful to look at.</span></span>  

<span data-ttu-id="c4cce-121">在整个暗淡区域中存在亮光点的区域也存在问题，因为在移入或移出明亮空间时相机必须进行调整。</span><span class="sxs-lookup"><span data-stu-id="c4cce-121">Areas where there are points of bright light in an overall dim area are also problematic, as the camera has to adjust when moving in and out of bright spaces.</span></span> <span data-ttu-id="c4cce-122">这可能导致设备“迷路”，并认为光线变化等同于位置变化。</span><span class="sxs-lookup"><span data-stu-id="c4cce-122">This can cause the device to "get lost" and think that the change in light equates to a change in location.</span></span> <span data-ttu-id="c4cce-123">区域中稳定的光线水平将导致更好的跟踪效果。</span><span class="sxs-lookup"><span data-stu-id="c4cce-123">Stable light levels in an area will lead to better tracking.</span></span>  

<span data-ttu-id="c4cce-124">任何户外照明也会导致跟踪器不稳定，因为太阳会随时间发生很大变化。</span><span class="sxs-lookup"><span data-stu-id="c4cce-124">Any outdoor lighting can also cause instability in the tracker, as the sun may vary considerably over time.</span></span> <span data-ttu-id="c4cce-125">例如，夏季与冬季在同一空间中进行跟踪可能会产生截然不同的结果，因为外面的间接光在一年中的不同时间可能会更强。</span><span class="sxs-lookup"><span data-stu-id="c4cce-125">For example, tracking in the same space in the summer vs. winter can produce drastically different results, as the secondhand light outside may be higher at different times of year.</span></span>  

<span data-ttu-id="c4cce-126">如果你有一个照度计，那么稳定的 500-1000 勒克斯是一个好起点。</span><span class="sxs-lookup"><span data-stu-id="c4cce-126">If you have a luxmeter, a steady 500-1000 lux is a good place to start.</span></span>  

#### <span data-ttu-id="c4cce-127">照明类型</span><span class="sxs-lookup"><span data-stu-id="c4cce-127">Types of lighting</span></span>

<span data-ttu-id="c4cce-128">空间中不同类型的光也会影响跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4cce-128">Different types of light in a space can also influence tracking.</span></span> <span data-ttu-id="c4cce-129">灯泡通过流经灯泡的交流电产生脉冲 - 如果交流电频率为 50Hz，则光脉冲频率为 50Hz。</span><span class="sxs-lookup"><span data-stu-id="c4cce-129">Light bulbs pulse with the AC electricity running through it - if the AC frequency is 50Hz, then the light pulses at 50Hz.</span></span> <span data-ttu-id="c4cce-130">对于人类，观察不到这种脉冲。</span><span class="sxs-lookup"><span data-stu-id="c4cce-130">For a human, this pulsing is not noticed.</span></span> <span data-ttu-id="c4cce-131">但是，HoloLens 的 30fps 相机会察觉这些变化 - 某些帧将很亮，某些帧将不太亮，而某些帧会因相机尝试补偿光脉冲而过度曝光。</span><span class="sxs-lookup"><span data-stu-id="c4cce-131">However, HoloLens' 30fps camera sees these changes - some frames will be well-lit, some will be poorly lit, and some will be over-exposed as the camera tries to compensate for light pulses.</span></span>  

<span data-ttu-id="c4cce-132">在美国，电力频率标准是 60Hz，因此灯泡脉冲与 HoloLens 的帧速率协调一致 - 60Hz 脉冲与 HoloLens 的 30 FPS 帧速率一致。</span><span class="sxs-lookup"><span data-stu-id="c4cce-132">In the USA, electricity frequency standard is 60Hz, so light bulb pulses are harmonized with HoloLens' framerate - 60Hz pulses align with HoloLens' 30 FPS framerate.</span></span> <span data-ttu-id="c4cce-133">但是，许多国家/地区的交流电频率标准是 50Hz，这意味着在脉冲过程中将拍摄一些 HoloLens 帧，而其他帧则不会被拍摄到。</span><span class="sxs-lookup"><span data-stu-id="c4cce-133">However, many countries have an AC frequency standard of 50Hz, which means some HoloLens frames will be taken during pulses, and others will not.</span></span> <span data-ttu-id="c4cce-134">特别是，我们已知欧洲的荧光照明会导致问题。</span><span class="sxs-lookup"><span data-stu-id="c4cce-134">In particular, fluorescent lighting in Europe has been known to cause issues.</span></span>  

<span data-ttu-id="c4cce-135">可以试用一些方法来解决闪烁问题。</span><span class="sxs-lookup"><span data-stu-id="c4cce-135">There are a few things you can try to resolve flickering issues.</span></span> <span data-ttu-id="c4cce-136">温度、灯泡寿命和预热周期是导致荧光闪烁的常见原因，更换灯泡可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="c4cce-136">Temperature, bulb age, and warm-up cycles are common causes of fluorescent flickering and replacing bulbs may help.</span></span> <span data-ttu-id="c4cce-137">拧紧灯泡并确保电流消耗恒定也可能会有帮助。</span><span class="sxs-lookup"><span data-stu-id="c4cce-137">Tightening bulbs and making sure current draws are constant can also help.</span></span>  

### <span data-ttu-id="c4cce-138">空间中的物品</span><span class="sxs-lookup"><span data-stu-id="c4cce-138">Items in a space</span></span>

<span data-ttu-id="c4cce-139">HoloLens 使用独特的环境陆标（也称为*特征*）在空间中定位自身。</span><span class="sxs-lookup"><span data-stu-id="c4cce-139">HoloLens uses unique environmental landmarks, also known as *features*, to locate itself in a space.</span></span>  

<span data-ttu-id="c4cce-140">设备几乎无法在特征不明显的区域中进行跟踪，因为设备无法知道它所在的具体空间。</span><span class="sxs-lookup"><span data-stu-id="c4cce-140">A device can almost never track in a feature-poor area, as the device has no way of knowing where in space it is.</span></span> <span data-ttu-id="c4cce-141">将特征添加到空间的墙壁中通常是改进跟踪的好方法。</span><span class="sxs-lookup"><span data-stu-id="c4cce-141">Adding features to the walls of a space is usually a good way to improve tracking.</span></span> <span data-ttu-id="c4cce-142">海报、贴在墙上的标志、植物、独特的物体或其他类似物品全都有用。</span><span class="sxs-lookup"><span data-stu-id="c4cce-142">Posters, symbols taped to a wall, plants, unique objects, or other similar items all help.</span></span> <span data-ttu-id="c4cce-143">凌乱的办公桌是便于进行跟踪的一个环境示例 - 一个区域中有很多不同的特征。</span><span class="sxs-lookup"><span data-stu-id="c4cce-143">A messy desk is a good example of an environment that leads to good tracking - there are a lot of different features in a single area.</span></span>  

<span data-ttu-id="c4cce-144">此外，请在相同的空间中使用独特的特征。</span><span class="sxs-lookup"><span data-stu-id="c4cce-144">Additionally, use unique features in the same space.</span></span> <span data-ttu-id="c4cce-145">例如，同一张海报在墙上重复多次会引起设备混淆，因为 HoloLens 不知道要看哪个重复的海报。</span><span class="sxs-lookup"><span data-stu-id="c4cce-145">The same poster repeated multiple times over a wall, for example, will cause device confusion as the HoloLens won't know which of the repetitive posters it is looking at.</span></span> <span data-ttu-id="c4cce-146">添加独特的特征的一种常见方法是使用遮蔽胶带线沿着空间的墙壁和地板创建独特的非重复图案。</span><span class="sxs-lookup"><span data-stu-id="c4cce-146">One common way of adding unique features is to use lines of masking tape to create unique, non-repetitive patterns along the walls and floor of a space.</span></span>  

<span data-ttu-id="c4cce-147">问自己一个适当的问题：如果只看到了很少的场景，那么能否在空间中唯一定位自己？</span><span class="sxs-lookup"><span data-stu-id="c4cce-147">A good question to ask yourself is: if you saw just a small amount of the scene, could you uniquely locate yourself in the space?</span></span> <span data-ttu-id="c4cce-148">如果不能，设备可能也会有跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="c4cce-148">If not, it's likely the device will have problems tracking as well.</span></span>

#### <span data-ttu-id="c4cce-149">虫洞</span><span class="sxs-lookup"><span data-stu-id="c4cce-149">Wormholes</span></span>

<span data-ttu-id="c4cce-150">如果你有两个看起来相同的区域，则跟踪器可能会认为它们相同。</span><span class="sxs-lookup"><span data-stu-id="c4cce-150">If you have two areas or regions that look the same, the tracker may think they are the same.</span></span> <span data-ttu-id="c4cce-151">这会导致设备骗自己以为它在其他地方。</span><span class="sxs-lookup"><span data-stu-id="c4cce-151">This results in the device tricking itself into thinking it is somewhere else.</span></span> <span data-ttu-id="c4cce-152">我们将这些类型的重复区域称为*虫洞*。</span><span class="sxs-lookup"><span data-stu-id="c4cce-152">We call these types of repetitive areas *wormholes*.</span></span>  

<span data-ttu-id="c4cce-153">若要防止出现虫洞，请尝试阻止相同空间中出现相同区域。</span><span class="sxs-lookup"><span data-stu-id="c4cce-153">To prevent wormholes, try to prevent identical areas in the same space.</span></span> <span data-ttu-id="c4cce-154">相同区域有时可能包括工厂工作站、建筑物上的窗户、服务器机架或工作站。</span><span class="sxs-lookup"><span data-stu-id="c4cce-154">Identical areas can sometimes include factory stations, windows on a building, server racks, or work stations.</span></span> <span data-ttu-id="c4cce-155">给区域贴上标签或为每个外观相似的区域添加独特的特征可以帮助减少虫洞。</span><span class="sxs-lookup"><span data-stu-id="c4cce-155">Labelling areas or adding unique features to each similar-looking areas can help mitigate wormholes.</span></span>

### <span data-ttu-id="c4cce-156">空间中的运动</span><span class="sxs-lookup"><span data-stu-id="c4cce-156">Movement in a space</span></span>

<span data-ttu-id="c4cce-157">如果环境在不断移动和变化，则设备没有可供定位参照的稳定特征。</span><span class="sxs-lookup"><span data-stu-id="c4cce-157">If your environment is constantly shifting and changing, the device has no stable features to locate against.</span></span>  

<span data-ttu-id="c4cce-158">空间中移动的对象（包括人员）越多，就越容易跟丢。</span><span class="sxs-lookup"><span data-stu-id="c4cce-158">The more moving objects that are in a space, including people, the easier it is to lose tracking.</span></span> <span data-ttu-id="c4cce-159">众所周知，空间中的移动传送带、处于不同施工状态的东西以及许多人都会引起跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="c4cce-159">Moving conveyor belts, items in different states of construction, and lots of people in a space have all been known to cause tracking issues.</span></span>

<span data-ttu-id="c4cce-160">HoloLens 可以快速适应这些变化，但只有在该区域对设备清晰可见时才能适应。</span><span class="sxs-lookup"><span data-stu-id="c4cce-160">The HoloLens can quickly adapt to these changes, but only when that area is clearly visible to the device.</span></span> <span data-ttu-id="c4cce-161">不经常看到的区域可能会滞后于现实，这可能会导致空间地图中出现错误。</span><span class="sxs-lookup"><span data-stu-id="c4cce-161">Areas that are not seen as frequently may lag behind reality, which can cause errors in the spatial map.</span></span> <span data-ttu-id="c4cce-162">例如，用户扫视朋友，然后在朋友离开房间时转身。</span><span class="sxs-lookup"><span data-stu-id="c4cce-162">For example, a user scans a friend and then turns around while the friend leaves the room.</span></span> <span data-ttu-id="c4cce-163">朋友的“重影”表现形式将一直保留在空间映射数据中，直到用户重新扫视现在的空白空间为止。</span><span class="sxs-lookup"><span data-stu-id="c4cce-163">A 'ghost' representation of the friend will persist in the spatial mapping data until the user re-scans the now empty space.</span></span>

### <span data-ttu-id="c4cce-164">用户对空间中物品的邻近感应</span><span class="sxs-lookup"><span data-stu-id="c4cce-164">Proximity of the user to items in the space</span></span>

<span data-ttu-id="c4cce-165">与人类无法很好地聚焦在眼睛附近的物体上一样，当物体靠近 HoloLens 的相机时，HoloLens 也无法聚焦。</span><span class="sxs-lookup"><span data-stu-id="c4cce-165">Similarly to how humans cannot focus well on objects close to the eyes, HoloLens struggles when objects are close to it's cameras.</span></span> <span data-ttu-id="c4cce-166">如果物体太近，导致两个相机都无法看到此物体，或者物体挡住了一个相机，则设备跟踪该物体的问题将更多。</span><span class="sxs-lookup"><span data-stu-id="c4cce-166">If an object is too close to be seen with both cameras, or if an object is blocking one camera, the device will have far more issues with tracking against the object.</span></span>  

<span data-ttu-id="c4cce-167">相机看不到距离物体 15cm 之内的东西。</span><span class="sxs-lookup"><span data-stu-id="c4cce-167">The cameras can see no closer than 15cm from an object.</span></span>

### <span data-ttu-id="c4cce-168">空间中的表面</span><span class="sxs-lookup"><span data-stu-id="c4cce-168">Surfaces in a space</span></span>

<span data-ttu-id="c4cce-169">强反射表面看起来可能因角度而异，这会影响跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4cce-169">Strongly reflective surfaces will likely look different depending on the angle, which affects tracking.</span></span> <span data-ttu-id="c4cce-170">想想一辆崭新的汽车 - 当你在它四周移动时，光线会反射，你在移动时会在表面上看到不同的物体。</span><span class="sxs-lookup"><span data-stu-id="c4cce-170">Think of a brand new car - when you move around it, light reflects and you see different objects in the surface as you move.</span></span> <span data-ttu-id="c4cce-171">对于跟踪器而言，表面上反射的不同物体代表不断变化的环境，并且设备会跟丢。</span><span class="sxs-lookup"><span data-stu-id="c4cce-171">To the tracker, the different objects reflected in the surface represent a changing environment, and the device loses tracking.</span></span>

<span data-ttu-id="c4cce-172">光泽度较低的物体更易于跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4cce-172">Less shiny objects are easier to track against.</span></span>

### <span data-ttu-id="c4cce-173">WLAN 指纹注意事项</span><span class="sxs-lookup"><span data-stu-id="c4cce-173">Wi-Fi fingerprint considerations</span></span>

<span data-ttu-id="c4cce-174">只要启用 WLAN，地图数据就会与 WLAN 指纹关联，即使未连接到实际 WLAN 网络/路由器也是如此。</span><span class="sxs-lookup"><span data-stu-id="c4cce-174">As long as Wi-Fi is enabled, map data will be correlated with a Wi-Fi fingerprint, even when not connected to an actual WiFi network/router.</span></span> <span data-ttu-id="c4cce-175">如果没有 WLAN 信息，空间和全息影像的识别速度可能会稍慢一些。</span><span class="sxs-lookup"><span data-stu-id="c4cce-175">Without Wi-Fi info, the space and holograms may be slightly slower to recognize.</span></span> <span data-ttu-id="c4cce-176">如果 WLAN 信号发生了重大变化，则设备可能会认为它完全位于另一个空间中。</span><span class="sxs-lookup"><span data-stu-id="c4cce-176">If the Wi-Fi signals change significantly, the device may think it is in a different space altogether.</span></span>

<span data-ttu-id="c4cce-177">网络标识（例如 SSID 或 MAC 地址）不会发送到 Microsoft，并且所有 WLAN 引用都将保留在 HoloLens 本地上。</span><span class="sxs-lookup"><span data-stu-id="c4cce-177">Network identification (such as SSID or MAC address) is not sent to Microsoft, and all Wi-Fi references are kept local on the HoloLens.</span></span>

## <span data-ttu-id="c4cce-178">映射新空间</span><span class="sxs-lookup"><span data-stu-id="c4cce-178">Mapping new spaces</span></span>

<span data-ttu-id="c4cce-179">进入新空间（或加载现有空间）时，你将看到一个网格图形遍布于该空间。</span><span class="sxs-lookup"><span data-stu-id="c4cce-179">When you enter a new space (or load an existing one), you’ll see a mesh graphic spreading over the space.</span></span> <span data-ttu-id="c4cce-180">这意味着设备正在映射周围环境。</span><span class="sxs-lookup"><span data-stu-id="c4cce-180">This means your device is mapping your surroundings.</span></span> <span data-ttu-id="c4cce-181">尽管 HoloLens 将在一段时间内了解空间，但有一些用于映射空间的提示和技巧。</span><span class="sxs-lookup"><span data-stu-id="c4cce-181">While a HoloLens will learn a space over time, there are tips and tricks to map spaces.</span></span>

## <span data-ttu-id="c4cce-182">环境管理</span><span class="sxs-lookup"><span data-stu-id="c4cce-182">Environment management</span></span>

<span data-ttu-id="c4cce-183">用户可以使用两个设置来“清理”全息影像并使 HoloLens“忘记”空间。</span><span class="sxs-lookup"><span data-stu-id="c4cce-183">There are two settings which enable users to “clean up” holograms and cause HoloLens to “forget" a space.</span></span> <span data-ttu-id="c4cce-184">它们存在于“设置”应用内的**全息影像和环境**中，并且第二个设置还会出现在“设置”应用中的**隐私**下面。</span><span class="sxs-lookup"><span data-stu-id="c4cce-184">They exist in **Holograms and environments** in the settings app, with the second setting also appearing under **Privacy** in the settings app.</span></span>  

1. <span data-ttu-id="c4cce-185">**删除附近的全息影像**。</span><span class="sxs-lookup"><span data-stu-id="c4cce-185">**Delete nearby holograms**.</span></span> <span data-ttu-id="c4cce-186">如果选择此设置，则 HoloLens 将擦除设备所在“当前空间”的所有固定全息影像和所有已存储地图数据。</span><span class="sxs-lookup"><span data-stu-id="c4cce-186">When you select this setting, HoloLens will erase all anchored holograms and all stored map data for the “current space” where the device is located.</span></span> <span data-ttu-id="c4cce-187">将全息影像再次放在该空间时，会针对该位置在数据库中创建并存储一个新的地图部分。</span><span class="sxs-lookup"><span data-stu-id="c4cce-187">A new map section would be created and stored in the database for that location once holograms are again placed in that same space.</span></span>

1. <span data-ttu-id="c4cce-188">**删除所有全息影像**。如果选择此设置，HoloLens 将擦除整个空间数据库中的所有地图数据和固定全息影像。</span><span class="sxs-lookup"><span data-stu-id="c4cce-188">**Delete all holograms**.By selecting this setting, HoloLens will erase ALL map data and anchored holograms in the entire databases of spaces.</span></span> <span data-ttu-id="c4cce-189">将不会重新发现全息影像，并且需要重新放置任何全息影像以再次将地图部分存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="c4cce-189">No holograms will be rediscovered and any holograms need to be newly placed to again store map sections in the database.</span></span>

## <span data-ttu-id="c4cce-190">全息影像质量</span><span class="sxs-lookup"><span data-stu-id="c4cce-190">Hologram quality</span></span>

<span data-ttu-id="c4cce-191">全息影像可以放在整个环境中，包括高处、低处以及你周围的任何地方，但是，你将通过位于眼前的[全息框](https://docs.microsoft.com/windows/mixed-reality/holographic-frame)来观看它们。</span><span class="sxs-lookup"><span data-stu-id="c4cce-191">Holograms can be placed throughout your environment—high, low, and all around you—but you’ll see them through a [holographic frame](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) that sits in front of your eyes.</span></span> <span data-ttu-id="c4cce-192">若要获取最佳视图，请确保调整设备，以便可以看到整个框。</span><span class="sxs-lookup"><span data-stu-id="c4cce-192">To get the best view, make sure to adjust your device so you can see the entire frame.</span></span> <span data-ttu-id="c4cce-193">记住在环境中随意转转，简单探索一下！</span><span class="sxs-lookup"><span data-stu-id="c4cce-193">And don’t hesitate to walk around your environment and explore!</span></span>

<span data-ttu-id="c4cce-194">为了使[全息影像](https://docs.microsoft.com/windows/mixed-reality/hologram)看起来简洁、清晰且稳定，需要仅为你校准 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="c4cce-194">For your [holograms](https://docs.microsoft.com/windows/mixed-reality/hologram) to look crisp, clear, and stable, your HoloLens needs to be calibrated just for you.</span></span> <span data-ttu-id="c4cce-195">首次设置 HoloLens 时，系统将指导你完成此过程。</span><span class="sxs-lookup"><span data-stu-id="c4cce-195">When you first set up your HoloLens, you’ll be guided through this process.</span></span> <span data-ttu-id="c4cce-196">之后，如果全息影像看起来不正确或者你看到大量错误，可以进行调整。</span><span class="sxs-lookup"><span data-stu-id="c4cce-196">Later on, if holograms don’t look right or you’re seeing a lot of errors, you can make adjustments.</span></span>

<span data-ttu-id="c4cce-197">如果你在映射空间时遇到问题，请尝试删除附近的全息影像并重新映射空间。</span><span class="sxs-lookup"><span data-stu-id="c4cce-197">If you are having trouble mapping spaces, try deleting nearby holograms and remapping the space.</span></span>

### <span data-ttu-id="c4cce-198">校准</span><span class="sxs-lookup"><span data-stu-id="c4cce-198">Calibration</span></span>

<span data-ttu-id="c4cce-199">如果全息影像看起来抖动或晃动，或者如果在放置全息影像时遇到问题，请首先尝试[“校准”应用](hololens-calibration.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cce-199">If your holograms look jittery or shaky, or if you’re having trouble placing holograms, the first thing to try is the [Calibration app](hololens-calibration.md).</span></span> <span data-ttu-id="c4cce-200">如果在使用 HoloLens 时遇到任何不适，此应用也可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="c4cce-200">This app can also help if you’re experiencing any discomfort while using your HoloLens.</span></span>

<span data-ttu-id="c4cce-201">若要访问“校准”应用，请转到**设置** > **系统** > **实用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4cce-201">To get to the Calibration app, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="c4cce-202">选择**打开校准**，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c4cce-202">Select **Open Calibration** and follow the instructions.</span></span>

<span data-ttu-id="c4cce-203">如果其他人要使用你的 HoloLens，那么他们应该首先运行“校准”应用，这样设备才能为他们正确设置。</span><span class="sxs-lookup"><span data-stu-id="c4cce-203">If someone else is going to be using your HoloLens, they should run the Calibration app first so the device is set up properly for them.</span></span>

## <span data-ttu-id="c4cce-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4cce-204">See also</span></span>

- [<span data-ttu-id="c4cce-205">空间映射设计</span><span class="sxs-lookup"><span data-stu-id="c4cce-205">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [<span data-ttu-id="c4cce-206">全息影像</span><span class="sxs-lookup"><span data-stu-id="c4cce-206">Holograms</span></span>](https://docs.microsoft.com/windows/mixed-reality/hologram)