---
title: 使用语音运行 HoloLens
description: 了解 Cortana 如何帮助你在 HoloLens 混合现实设备上执行所有类型的操作，包括语音命令、听写和全息影像交互。
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393866"
---
# <a name="use-your-voice-to-operate-hololens"></a><span data-ttu-id="9cd1b-104">使用语音运行 HoloLens</span><span class="sxs-lookup"><span data-stu-id="9cd1b-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="9cd1b-105">你可以使用语音在 HoloLens 上执行几乎任何操作，例如拍摄快照或打开应用。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="9cd1b-106">许多语音命令内置于 HoloLens 中，其他的语音命令则可通过 Cortana 实现。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="9cd1b-107">本文将告诉你如何通过语音和 Cortana 来控制 HoloLens 和你的全息世界。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="9cd1b-108">语音功能仅支持[某些语言](hololens2-language-support.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="9cd1b-109">语音语言基于 Windows 显示语言，而非键盘语言。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="9cd1b-110">你可以通过选择**设置** > **时间和语言** > **语言**来验证 Windows 显示语言。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <a name="built-in-voice-commands"></a><span data-ttu-id="9cd1b-111">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-111">Built-in voice commands</span></span>

<span data-ttu-id="9cd1b-112">使用以下基本命令可以更快地操作 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="9cd1b-113">要使用这些命令，需要在首次运行设备时启用语音，或在 **“设置”** > **“隐私”** > **“语音”** 中启用语音。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="9cd1b-114">你可以通过查看“开始”菜单顶部的状态，随时检查是否启用了语音功能。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="9cd1b-115">为了获得最佳语音识别效果，HoloLens 2 使用基于 Microsoft 云的服务。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="9cd1b-116">但是，你可以使用“设置”来禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="9cd1b-117">若要执行此操作，请在“设置”中关闭**在线语音识别**。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="9cd1b-118">更改此设置后，HoloLens 2 将仅在本地处理语音数据以识别命令和听写，并且 Cortana 将不可用。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <a name="general-speech-commands"></a><span data-ttu-id="9cd1b-119">常规语音命令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-119">General speech commands</span></span>

<span data-ttu-id="9cd1b-120">在整个 Windows Mixed Reality 中使用这些命令，以便更快地进行访问。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="9cd1b-121">某些命令使用凝视光标，说出“选择”即可调出该光标。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="9cd1b-122">HoloLens（第一代）不支持手控光线。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="9cd1b-123">说出语音指令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-123">Say this</span></span> | <span data-ttu-id="9cd1b-124">实际执行操作</span><span class="sxs-lookup"><span data-stu-id="9cd1b-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="9cd1b-125">“选择”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-125">"Select"</span></span> | <span data-ttu-id="9cd1b-126">说出“选择”以调出凝视光标。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="9cd1b-127">然后，转动头部，将光标放在你想要选择的内容上，然后再次说 “选择”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
| <span data-ttu-id="9cd1b-128">“去开始菜单”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-128">"Go to Start"</span></span> |  <span data-ttu-id="9cd1b-129">打开“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="9cd1b-129">Open the Start menu</span></span> |
| <span data-ttu-id="9cd1b-130">“关闭”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-130">"Close"</span></span>  | <span data-ttu-id="9cd1b-131">关闭“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="9cd1b-131">Close the Start menu</span></span> |
| <span data-ttu-id="9cd1b-132">说出“去开始菜单”以调出快速操作菜单，然后说出“混合现实主页”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-132">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span>  | <span data-ttu-id="9cd1b-133">离开沉浸式应用</span><span class="sxs-lookup"><span data-stu-id="9cd1b-133">Leave an immersive app</span></span> |
| <span data-ttu-id="9cd1b-134">“隐藏手部射线”/“显示手部射线”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-134">"Hide hand ray" / "Show hand ray"</span></span> | <span data-ttu-id="9cd1b-135">隐藏和显示手部射线</span><span class="sxs-lookup"><span data-stu-id="9cd1b-135">Hide and show hand ray</span></span> |
| <span data-ttu-id="9cd1b-136">“我可以说什么？”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-136">"What can I say?"</span></span>  | <span data-ttu-id="9cd1b-137">查看可用的语音命令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-137">See available speech commands</span></span> |

<span data-ttu-id="9cd1b-138">自 HoloLens 2 版本 19041.x 起，还可以使用下面这些命令：</span><span class="sxs-lookup"><span data-stu-id="9cd1b-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="9cd1b-139">说出语音指令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-139">Say this</span></span> | <span data-ttu-id="9cd1b-140">具体方法为</span><span class="sxs-lookup"><span data-stu-id="9cd1b-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="9cd1b-141">“重启设备”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-141">"Restart device"</span></span> | <span data-ttu-id="9cd1b-142">打开对话框，以确认你要重启设备。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="9cd1b-143">若要重启，可以说“是”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="9cd1b-144">“关闭设备”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-144">"Shutdown device"</span></span> | <span data-ttu-id="9cd1b-145">打开对话框，以确认你要关闭设备。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="9cd1b-146">若要确认，可以说“是”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="9cd1b-147">“增加亮度/降低亮度”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-147">"Brightness up/down"</span></span> | <span data-ttu-id="9cd1b-148">将显示器亮度增加或降低 10%。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="9cd1b-149">“调高音量/调低音量”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-149">"Volume up/down"</span></span> | <span data-ttu-id="9cd1b-150">将音量调高或调低 10%。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="9cd1b-151">“我的 IP 地址是什么”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-151">"What's my IP address"</span></span> | <span data-ttu-id="9cd1b-152">打开对话框，其中显示设备在本地网络上的当前 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="9cd1b-153">“拍摄照片”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-153">"Take a picture"</span></span> | <span data-ttu-id="9cd1b-154">拍摄当前所见内容的混合现实照片。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="9cd1b-155">“拍摄视频”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-155">"Take a video"</span></span> | <span data-ttu-id="9cd1b-156">开始录制混合现实视频。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="9cd1b-157">“停止录制”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-157">"Stop recording"</span></span> | <span data-ttu-id="9cd1b-158">停止当前的混合现实视频录制（若有正在进行中）。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <a name="hologram-commands"></a><span data-ttu-id="9cd1b-159">全息影像命令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-159">Hologram commands</span></span>

<span data-ttu-id="9cd1b-160">要使用这些命令，请凝视 3D 对象、全息影像或应用窗口。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="9cd1b-161">说出语音指令</span><span class="sxs-lookup"><span data-stu-id="9cd1b-161">Say this</span></span> | <span data-ttu-id="9cd1b-162">实际执行操作</span><span class="sxs-lookup"><span data-stu-id="9cd1b-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="9cd1b-163">“放大”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-163">"Bigger"</span></span> | <span data-ttu-id="9cd1b-164">将其放大</span><span class="sxs-lookup"><span data-stu-id="9cd1b-164">Make it bigger</span></span> |
| <span data-ttu-id="9cd1b-165">“缩小”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-165">"Smaller"</span></span> | <span data-ttu-id="9cd1b-166">将其缩小</span><span class="sxs-lookup"><span data-stu-id="9cd1b-166">Make it smaller</span></span> |
| <span data-ttu-id="9cd1b-167">“正面朝我”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-167">"Face me"</span></span> | <span data-ttu-id="9cd1b-168">调转目标，使其正面朝向自己</span><span class="sxs-lookup"><span data-stu-id="9cd1b-168">Turn it to face you</span></span> |
| <span data-ttu-id="9cd1b-169">“移动此项”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-169">"Move this"</span></span> | <span data-ttu-id="9cd1b-170">移动目标（跟随你的凝视点而移动）</span><span class="sxs-lookup"><span data-stu-id="9cd1b-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="9cd1b-171">“关闭”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-171">"Close"</span></span> | <span data-ttu-id="9cd1b-172">将其关闭</span><span class="sxs-lookup"><span data-stu-id="9cd1b-172">Close it</span></span> |
| <span data-ttu-id="9cd1b-173">“跟我走”/“停下来”</span><span class="sxs-lookup"><span data-stu-id="9cd1b-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="9cd1b-174">使其跟随你移动</span><span class="sxs-lookup"><span data-stu-id="9cd1b-174">Make it follow you as you move around</span></span> |

### <a name="see-it-say-it"></a><span data-ttu-id="9cd1b-175">看到什么，就说什么</span><span class="sxs-lookup"><span data-stu-id="9cd1b-175">See it, say it</span></span>

<span data-ttu-id="9cd1b-176">HoloLens 中的许多按钮和其他元素也会响应你的语音 - 例如，应用栏上的**跟我走**、**关闭**或 Edge 中的**后退**按钮。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="9cd1b-177">如果要了解一个按钮是否启用语音功能，请将**凝视光标**、**触摸光标**或一条**手部射线**停留在该按钮上一会儿。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-177">To find out if a button is voice-enabled, rest your **gaze cursor**, **touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="9cd1b-178">如果该按钮已启用语音功能，你将看到语音提示。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <a name="dictation-mode"></a><span data-ttu-id="9cd1b-179">听写模式</span><span class="sxs-lookup"><span data-stu-id="9cd1b-179">Dictation mode</span></span>

<span data-ttu-id="9cd1b-180">厌倦了打字？</span><span class="sxs-lookup"><span data-stu-id="9cd1b-180">Tired of typing?</span></span> <span data-ttu-id="9cd1b-181">在全息键盘启用后可随时切换到听写模式。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-181">Switch to dictation mode anytime that the holographic keyboard is active.</span></span> <span data-ttu-id="9cd1b-182">如果要开始听写，请选择麦克风按钮或说“开始听写”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="9cd1b-183">若要停止听写，请再次选择该按钮或说“停止听写”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="9cd1b-184">若要删除刚才听写的内容，请说“删除那个”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="9cd1b-185">若要使用听写模式，你必须具有 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="9cd1b-186">HoloLens 听写使用明确的标点符号，也就是说，你需要说出要使用的标点符号的名称。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="9cd1b-187">例如，可以说“你好**逗号**你在忙什么呢**问号**”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="9cd1b-188">下面是你可以使用的标点关键字：</span><span class="sxs-lookup"><span data-stu-id="9cd1b-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="9cd1b-189">句号、逗号、问号、感叹号</span><span class="sxs-lookup"><span data-stu-id="9cd1b-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="9cd1b-190">换行/新段落</span><span class="sxs-lookup"><span data-stu-id="9cd1b-190">New line/new paragraph</span></span>
- <span data-ttu-id="9cd1b-191">分号、冒号</span><span class="sxs-lookup"><span data-stu-id="9cd1b-191">Semicolon, colon</span></span>
- <span data-ttu-id="9cd1b-192">左引号、右引号</span><span class="sxs-lookup"><span data-stu-id="9cd1b-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="9cd1b-193">井号标签、微笑/笑脸、悲伤、眨眼</span><span class="sxs-lookup"><span data-stu-id="9cd1b-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="9cd1b-194">美元、百分比</span><span class="sxs-lookup"><span data-stu-id="9cd1b-194">Dollar, percent</span></span>

<span data-ttu-id="9cd1b-195">有时，拼写出像电子邮件地址之类的内容很有用。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="9cd1b-196">例如，若要对 example@outlook.com 进行听写，可以说“E X A M P L E at outlook dot com”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <a name="do-more-with-cortana"></a><span data-ttu-id="9cd1b-197">通过 Cortana 执行更多操作</span><span class="sxs-lookup"><span data-stu-id="9cd1b-197">Do more with Cortana</span></span>

<span data-ttu-id="9cd1b-198">Cortana 有助于在 HoloLens 上执行各种操作，但具体功能可能因所使用的 Windows Holographic 版本而有所不同。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capabilities may be different.</span></span> <span data-ttu-id="9cd1b-199">可在此处了解更多有关最新版本 Cortana 更新功能的信息：即 [Cortana 在即将发布的 Windows 10 版本中：通过增强安全性和隐私性来专注于生产力](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-199">You can learn more about the updated capabilities of the latest version of Cortana here: [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![你好小娜！](images/cortana-on-hololens.png)

<span data-ttu-id="9cd1b-201">你可以尝试使用以下语音操作（请记住首先说“你好小娜”）。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="9cd1b-202">**你好小娜**...</span><span class="sxs-lookup"><span data-stu-id="9cd1b-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="9cd1b-203">我可以说什么？</span><span class="sxs-lookup"><span data-stu-id="9cd1b-203">What can I say?</span></span>
- <span data-ttu-id="9cd1b-204">启动 <*应用名称*>。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="9cd1b-205">几点了？</span><span class="sxs-lookup"><span data-stu-id="9cd1b-205">What time is it?</span></span>
- <span data-ttu-id="9cd1b-206">显示最新 NBA 比分。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="9cd1b-207">给我讲个笑话。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-207">Tell me a joke.</span></span>

<span data-ttu-id="9cd1b-208">如果使用的是*版本 18362.x 或更低版本*，还可以使用下面这些命令：</span><span class="sxs-lookup"><span data-stu-id="9cd1b-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="9cd1b-209">**你好小娜**...</span><span class="sxs-lookup"><span data-stu-id="9cd1b-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="9cd1b-210">提高音量。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-210">Increase the volume.</span></span>
- <span data-ttu-id="9cd1b-211">降低亮度。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-211">Decrease the brightness.</span></span>
- <span data-ttu-id="9cd1b-212">关闭。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-212">Shut down.</span></span>
- <span data-ttu-id="9cd1b-213">重启。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-213">Restart.</span></span>
- <span data-ttu-id="9cd1b-214">进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-214">Go to sleep.</span></span>
- <span data-ttu-id="9cd1b-215">静音。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-215">Mute.</span></span>
- <span data-ttu-id="9cd1b-216">将 <*应用名称*> 移动到此处（凝视你希望应用移动到的位置）。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="9cd1b-217">去开始菜单。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-217">Go to Start.</span></span>
- <span data-ttu-id="9cd1b-218">拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-218">Take a picture.</span></span>
- <span data-ttu-id="9cd1b-219">开始录制。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-219">Start recording.</span></span> <span data-ttu-id="9cd1b-220">（开始录制视频。）</span><span class="sxs-lookup"><span data-stu-id="9cd1b-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="9cd1b-221">停止录制。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-221">Stop recording.</span></span> <span data-ttu-id="9cd1b-222">（停止录制视频。）</span><span class="sxs-lookup"><span data-stu-id="9cd1b-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="9cd1b-223">我还剩多少电量？</span><span class="sxs-lookup"><span data-stu-id="9cd1b-223">How much battery do I have left?</span></span>

<span data-ttu-id="9cd1b-224">在 Windows 电脑或手机中常用的某些 Cortana 功能（例如，提醒和通知），在 Microsoft HoloLens 上并不支持，并且 Cortana 体验可能因地区而异。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <a name="turn-cortana-off"></a><span data-ttu-id="9cd1b-225">关闭 Cortana</span><span class="sxs-lookup"><span data-stu-id="9cd1b-225">Turn Cortana off</span></span>

<span data-ttu-id="9cd1b-226">如果启用了语音功能，则第一次使用 HoloLens 时就会开启 Cortana。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="9cd1b-227">你可以在 Cortana 的设置中将其关闭。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="9cd1b-228">在**所有应用**列表中，选择 **Cortana** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="9cd1b-229">然后关闭“Cortana 可以为你提供建议、想法、提醒、通知等”。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="9cd1b-230">如果 Cortana 未对“你好小娜”作出响应，请检查是否已启用语音功能，并转到 Cortana 的设置进行检查，确保其处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9cd1b-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
