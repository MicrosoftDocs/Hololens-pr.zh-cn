---
title: 使用语音运行 HoloLens
description: 了解 Cortana 如何帮助你在 HoloLens 混合现实设备上执行所有类型的操作，包括语音命令、听写和全息影像交互。
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034030"
---
# <a name="use-your-voice-to-operate-hololens"></a>使用语音运行 HoloLens

你可以使用语音在 HoloLens 上执行几乎任何操作，例如拍摄快照或打开应用。 许多语音命令内置于 HoloLens 中，其他的语音命令则可通过 Cortana 实现。

本文将告诉你如何通过语音和 Cortana 来控制 HoloLens 和你的全息世界。

> [!NOTE]
> 只有[某些语言](hololens2-language-support.md)支持语音。 语音语言基于 Windows 显示语言，而非键盘语言。  
>  
> 可以通过选择“设置” > “时间和语言” > “语言”来验证 Windows 显示语言。

## <a name="built-in-voice-commands"></a>内置语音命令

使用以下基本命令可以更快地操作 HoloLens。 若要使用这些功能，需要在第一次运行设备时或在“设置” > “隐私” > “语音”中启用语音。 你可以通过查看“开始”菜单顶部的状态，随时检查是否启用了语音功能。 为了获得最佳语音识别效果，HoloLens 2 使用基于 Microsoft 云的服务。 但是，你可以使用“设置”来禁用此功能。 为此，请在“设置”中关闭“在线语音识别”。 更改此设置后，HoloLens 2 将仅在本地处理语音数据以识别命令和听写，并且 Cortana 将不可用。

### <a name="general-speech-commands"></a>常规语音命令

在整个 Windows Mixed Reality 中使用这些命令，以便更快地进行访问。 某些命令使用凝视光标，说出“选择”即可调出该光标。

> [!NOTE]
> HoloLens（第一代）不支持手部射线。

| 说出的内容 | 要执行此操作 |
| - | - |
| “选择” | 说出“选择”以调出凝视光标。 然后，转动头部，将光标放在你想要选择的内容上，然后再次说“选择”。 |
| 转到“开始”菜单 |  打开“开始”菜单 |
| “关闭”  | 关闭“开始”菜单 |
| 说出“去开始菜单”以调出快速操作菜单，然后说出“混合现实主页”。  | 离开沉浸式应用 |
| “隐藏手部射线”/“显示手部射线” | 隐藏和显示手部射线 |
| “我可以说什么？”  | 查看可用的语音命令 |

自 HoloLens 2 版本 19041.x 起，还可以使用下面这些命令：

| 说出的内容 | 要执行此操作 |
| - | - |
| “重启设备” | 打开对话框，以确认你要重启设备。 若要重启，可以说“是”。 |
| “关闭设备” | 打开对话框，以确认你要关闭设备。 若要确认，可以说“是”。 |
| “增加亮度/降低亮度” | 将显示器亮度增加或降低 10%。 |
| “调高音量/调低音量” | 将音量调高或调低 10%。 |
| “我的 IP 地址是什么” | 打开对话框，其中显示设备在本地网络上的当前 IP 地址。 |
| “拍摄照片” | 拍摄当前所见内容的混合现实照片。 |
| “拍摄视频” | 开始录制混合现实视频。 | 
| “停止录制” | 停止当前的混合现实视频录制（若有正在进行中）。 |

### <a name="hologram-commands"></a>全息影像命令

要使用这些命令，请凝视 3D 对象、全息影像或应用窗口。

| 说出的内容 | 要执行此操作 |
| - | - |
| “放大” | 将其放大 |
| “缩小” | 将其缩小 |
| “正面朝我” | 调转目标，使其正面朝向自己 |
| “移动此项” | 移动目标（跟随你的凝视点而移动） |
| “关闭” | 关闭它 |
| “跟我走”/“停下来” | 使其跟随你移动 |

### <a name="see-it-say-it"></a>看到它，说出来

HoloLens 中的许多按钮和其他元素也会响应你的语音 - 例如，应用栏上的“跟我走”和“关闭”、或 Edge 中的“返回”按钮。   若要确定按钮是否已启用语音，请将凝视光标、触摸光标或手部射线暂时停留在其上。   如果该按钮已启用语音功能，你将看到语音提示。

### <a name="dictation-mode"></a>听写模式

厌倦了打字？ 在全息键盘启用后可随时切换到听写模式。 如果要开始听写，请选择麦克风按钮或说“开始听写”。 若要停止听写，请再次选择该按钮或说“停止听写”。 若要删除刚才听写的内容，请说“删除那个”。 

> [!NOTE]
> 若要使用听写模式，你必须具有 Internet 连接。

HoloLens 听写使用明确的标点符号，也就是说，你需要说出要使用的标点符号的名称。 例如，你可能会说“你好，逗号，你想做什么，问号”。 

下面是你可以使用的标点关键字：

- 句号、逗号、问号、感叹号
- 换行/新段落
- 分号、冒号
- 左引号、右引号
- 井号标签、微笑/笑脸、悲伤、眨眼
- 美元、百分比

有时，拼写出像电子邮件地址之类的内容很有用。 例如，若要口述 example@outlook.com，应该说“E X A M P L E at outlook dot com”。

## <a name="do-more-with-cortana"></a>通过 Cortana 执行更多操作

Cortana 有助于在 HoloLens 上执行各种操作，但具体功能可能因所使用的 Windows Holographic 版本而有所不同。 你可以在此处了解 Cortana 最新版本的更新功能：[即将发布的 Windows 10 版本中的 Cortana：享受增强的安全和隐私，专注提升你的工作效率](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。 

![你好小娜！](images/cortana-on-hololens.png)

你可以尝试使用以下语音操作（请记住首先说“你好小娜”）。

你好小娜…

- 我可以说什么？
- 启动 <应用名称>。
- 几点了？
- 显示最新 NBA 比分。
- 给我讲个笑话。

如果使用版本 18362.x 或更旧的版本，还可以使用以下命令：

你好小娜…

- 增大音量。
- 降低亮度。
- “关机”。
- 重启。
- 进入睡眠状态。
- 静音。
- 将 <应用名称> 移动到此处（凝视你希望应用移动到的位置）。
- 转到“开始”。
- 拍摄照片。
- 开始记录。 （开始录制视频。）
- 停止录制。 （停止录制视频。）
- 我还剩多少电量？

在 Windows 电脑或手机中常用的某些 Cortana 功能（例如，提醒和通知），在 Microsoft HoloLens 上并不支持，并且 Cortana 体验可能因地区而异。

### <a name="turn-cortana-off"></a>关闭 Cortana

如果启用了语音功能，则第一次使用 HoloLens 时就会开启 Cortana。 你可以在 Cortana 的设置中将其关闭。 在“所有应用”列表中，选择“Cortana”  > “设置”。 然后关闭 Cortana 能够为你提供建议、意见、提醒、警告等。

如果 Cortana 不响应“你好小娜”，请在“开始”处检查是否打开了语音，并转到 Cortana 设置并检查以确保已打开她。
