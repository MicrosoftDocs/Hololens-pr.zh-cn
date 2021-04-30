---
title: 有关 HoloLens 设备和全息影像的常见问题
description: 你是否有关于 HoloLens 的快速问题，或与全息影像交互？  本文提供快速的答案和更多资源。
keywords: hololens，常见问题解答，已知问题，帮助
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 660c3b4d3a35a7794de5e3e2fb18f2a4aba03c0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308183"
---
# <a name="frequently-asked-questions-about-hololens-devices-and-holograms"></a>有关 HoloLens 设备和全息影像的常见问题

本文回答了有关如何使用 HoloLens 的一些问题，其中包括如何放置全息影像、使用空间等。

遇到问题时，请确保已对 HoloLens 进行 [收费](https://support.microsoft.com/help/12627/hololens-charge-your-hololens)。 尝试 [重新启动它](hololens-restart-recover.md) 以查看是否修复了问题。 请使用反馈应用向我们发送有关此问题的信息。 你将在 " [**开始** " 菜单](holographic-home.md)上找到 "反馈" 应用。

有关如何磨损 HoloLens 的提示，请参阅 [hololens (第一代) 适合并舒适](hololens1-fit-comfort-faq.md)的常见问题。

本文解决了以下问题和问题： <a id="list"></a>

- [我的全息影像看起来不正确或正在四处移动](#my-holograms-dont-look-right-or-are-moving-around)
- [显示一条消息，显示 "查找你的空间"](#i-see-a-message-that-says-finding-your-space)
- [我看不到我希望在我的空间中看到的全息影像](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [我无法在我想的位置放置全息影像](#i-cant-place-holograms-where-i-want-to)
- [全息影像或 try](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [我可以看到位于墙的另一端的全息影像](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [在墙壁上放置全息影像时，全息图似乎是浮动的](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [尝试移动应用时，应用显示太近](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [磁盘空间不足错误](#im-getting-a-low-disk-space-error)
- [HoloLens 未响应我的手势](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens 未响应我的语音](#hololens-doesnt-respond-to-my-voice)
- [我在配对或使用 Bluetooth 设备时遇到问题](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens 设置将设备列出为可用，但设备不起作用](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [使用 HoloLens clicker 时遇到问题](#im-having-problems-using-the-hololens-clicker)
- [我无法连接到 Wi-fi](#i-cant-connect-to-wi-fi)
- [HoloLens 运行不正常，无响应或无法启动](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [我无法登录到 HoloLens 设备，因为以前为其他人设置了它](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [有关管理 HoloLens 设备的问题](#questions-about-managing-hololens-devices)
- [有关保护 HoloLens 设备的问题](#questions-about-securing-hololens-devices)
- [如何实现删除所有空格？](#how-do-i-delete-all-spaces)
- [我找不到或无法使用键盘键入 HoloLens 2 模拟器](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## <a name="my-holograms-dont-look-right-or-are-moving-around"></a>我的全息影像看起来不正确或正在四处移动

例如，如果你的全息影像看上去不正常 (例如，它们抖动或晃动，或者你) 上看到了黑色的修补程序，请尝试以下解决方法之一：

- [清洁你的设备面板](hololens1-hardware.md#care-and-cleaning) ，确保没有任何传感器阻止。
- 请确保你处于一个良好的空间，不会有很多直接阳光。
- 尝试在你的环境中浏览和 gazing，以便 HoloLens 可以更完整地扫描它们。
- 如果你已放入大量全息影像，请尝试删除一些全息影像。

如果仍有问题，请尝试运行校准应用。 此应用校准你的 HoloLens，只是为了帮助你保持全息的外观。 为此，请在 "**设置**" "系统" "  >    >  **实用程序**"。 在 **校准** 下，选择 " **打开校准**"。

[返回到列表](#list)

## <a name="i-see-a-message-that-says-finding-your-space"></a>显示一条消息，显示 "查找你的空间"

当 HoloLens 正在学习或加载空间时，可能会看到一条简短消息，其中显示 "查找你的空间"。 如果此消息显示超过几秒钟，则会在 "开始" 菜单下看到另一条消息，显示 "仍在查找你的空间"。

这些消息表示 HoloLens 在映射空间时遇到问题。 发生这种情况时，可以打开应用程序，但不能在环境中放置全息影像。

如果经常看到这些消息，请尝试下列一项或多项修复：

- 请确保你处于一个良好的空间，不会有很多直接阳光。
- 确保设备面板清晰。 [了解如何清理面板](hololens1-hardware.md#care-and-cleaning)。
- 请确保有一个强 Wi-Fi 信号。 如果输入的新环境没有 Wi-Fi 或弱 Wi-Fi 信号，则 HoloLens 将找不到你的空间。 转到 **设置**  >  **网络 &amp; Internet**  >  **wi-fi** 来检查 Wi-Fi 连接。
- 尝试移动速度缓慢。

[返回到列表](#list)

## <a name="im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space"></a>我看不到我希望在我的空间中看到的全息影像

如果看不到你所放置的全息影像，或者你看到的是不需要的影像，请尝试以下一项或多项修复：

- 开启一些光源。 HoloLens 最好在良好的空间中运行。
- 转到 "**设置**" "  >  **系统**  >  **全息影像**"，删除不需要的全息影像  >  。 或者，如果需要，请选择 " **删除所有全息影像**"。

  > [!NOTE]
  > 如果空间中的布局或光照发生了重大变化，则设备可能无法识别空间并显示全息影像。

[返回到列表](#list)

## <a name="i-cant-place-holograms-where-i-want-to"></a>我无法在我想的位置放置全息影像

如果在放置全息影像时遇到问题，请尝试以下操作：

- 介于您尝试放置全息影像的一到三米之间。
- 请勿在黑色或反光的表面上放置全息影像。
- 请确保你处于一个良好的空间，不会有很多直接阳光。
- 四处浏览房间，以便 HoloLens 可以重新扫描您的环境。 若要查看已扫描的内容，请点击以显示地图网格图。

[返回到列表](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>全息影像或 try

如果你的全息图太近，则会暂时将其消失 &mdash; ，以便还原全息图，只需离开。 此外，如果将多个全息影像放置在一起，某些影像可能会消失。 请尝试删除一些。

还可以通过其他全息影像或对象（如墙壁）阻止或 try 全息影像。 如果发生这种情况，请尝试以下修复之一：

- 如果在另一个全息图中 try 全息图，请将 try 全息图移到另一个位置。 为此，请选择 " **调整**"，然后点击并按住以定位它。
- 如果在墙壁中 try 全息图，请选择 " **调整**"，然后向墙壁方向直到出现全息图。 点击并按住，并向前和向外拉出全息影像。
- 如果无法通过使用笔势移动全息图，请使用语音将其删除。 注视全息图，然后说 "删除"。 然后重新打开全息图，并将其放在新位置。

[返回到列表](#list)

## <a name="i-can-see-holograms-that-are-on-the-other-side-of-a-wall"></a>我可以看到位于墙的另一端的全息影像

如果你非常接近墙壁，或者 HoloLens 尚未扫描墙壁，则可以看到下一个房间中的全息影像。 若要扫描墙壁，请从墙壁开始到3米之间，看看。

黑色或反射对象 (例如，在墙壁附近的黑色沙发或 stainless 钢冰箱) 会导致在 HoloLens 尝试扫描墙壁时出现问题。 如果有此类对象，请扫描墙壁的另一面。

[返回到列表](#list)

## <a name="when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float"></a>在墙壁上放置全息影像时，全息图似乎是浮动的

放置在墙壁上的全息图通常会显得一英寸或远离墙壁。 如果看上去更远离，请尝试以下一项或多项修复：

- 在墙壁上放置全息影像时，从墙壁开始到一到3米之间，并直接面对墙壁。
- 单击墙壁即可显示地图网格图。 请确保网格与墙壁对齐。 如果没有，请删除全息图，重新扫描墙，然后重试。
- 如果问题仍然存在，请运行校准应用。 你将在 "**设置**" "  >  **系统**  >  **实用工具**" 中找到它。

[返回到列表](#list)

## <a name="apps-appear-too-close-to-me-when-im-trying-to-move-them"></a>尝试移动应用时，应用显示太近

尝试浏览并查看放置应用程序的区域，以便 HoloLens 从不同角度扫描区域。 [清除设备面板](hololens1-hardware.md#care-and-cleaning) 也可能会有所帮助。

[返回到列表](#list)

## <a name="im-getting-a-low-disk-space-error"></a>磁盘空间不足错误

通过执行以下一项或多项操作来释放一些存储空间：

- 删除某些已放置的全息影像，或从应用中删除某些已保存的数据。 [如何实现查找我的数据？](holographic-data.md)
- 删除照片应用中的某些图片和视频。
- 从 HoloLens 卸载某些应用。 在 " **所有应用** " 列表中，点击并按住你要卸载的应用，然后选择 " **卸载**"。  (卸载应用程序还会删除应用程序存储在设备上的所有数据。 ) 

[返回到列表](#list)

## <a name="hololens-doesnt-respond-to-my-gestures"></a>HoloLens 未响应我的手势

若要确保 HoloLens 能看到您的手势，请将您的手保持在手势帧中。 手势帧会在你的任意一侧扩展几个英尺。 如果你不需要精确了解这一) ，则在你将其放在 (正文的前面时，还可以更好地了解你的手。 当 HoloLens 能看到你的手时，光标将从点变为圆圈。 详细了解如何 [使用 hololens 2 中的笔势，](hololens2-basic-usage.md) 或 [使用 hololens (第一代) 中的笔势 ](hololens1-basic-usage.md)。

[返回到列表](#list)

## <a name="hololens-doesnt-respond-to-my-voice"></a>HoloLens 未响应我的语音

HoloLens (第一代) 和 HoloLens 2 内置语音识别功能，并且还支持 Cortana (online 语音识别) 。

### <a name="built-in-voice-commands-do-not-work"></a>内置语音命令不起作用

在 HoloLens (第一代) 上，内置语音识别不可配置。 始终打开。 在 HoloLens 2 上，你可以选择是否在设备设置期间打开语音识别和 Cortana。

如果 HoloLens 2 未响应语音，请确保已启用语音识别。 转到 "**开始**  >  **设置**  >  " "**隐私**  >  **语音**" 并打开 **语音识别**。

### <a name="cortana-or-dictation-doesnt-work"></a>Cortana 或听写不起作用

如果 Cortana 或听写未对你的语音做出响应，请确保已启用联机语音识别。 转到 "**开始**  >  **设置**  >  " "**隐私**  >  **语音**" 并验证 "**联机语音识别**" 设置。 

如果 Cortana 仍未响应，请执行以下操作之一来验证 Cortana 本身是否已打开：

- 在 "**所有应用**" 中，选择 " **Cortana** > 选择"**菜单**""  >  **笔记本**  >  **设置**"进行更改。
- 在 HoloLens 2 上，选择 " **语音设置** " 按钮或说 "语音设置"。

若要详细了解你可以说的内容，请参阅 [将你的语音与 HoloLens 配合使用](hololens-cortana.md)。

[返回到列表](#list)

## <a name="im-having-problems-pairing-or-using-a-bluetooth-device"></a>我在配对或使用 Bluetooth 设备时遇到问题

如果在 [配对蓝牙设备](hololens-connect-devices.md)时遇到问题，请尝试以下操作：

- 转到 "**设置**  >  " "**设备**"，并确保已启用 "蓝牙"。 如果是，请将其关闭，然后重新打开。
- 请确保蓝牙设备已完全充电，或具有新电池。
- 如果仍然无法连接，请 [重新启动 HoloLens](hololens-recovery.md)。

[返回到列表](#list)

## <a name="hololens-settings-lists-devices-as-available-but-the-devices-dont-work"></a>HoloLens 设置将设备列出为可用，但设备不起作用

HoloLens (第一代) 不支持蓝牙音频配置文件。 蓝牙音频设备（如扬声器和耳机）在 HoloLens 设置中可能显示为可用，但不受支持。

HoloLens 2 支持用于立体声播放的蓝牙 A2DP 音频配置文件。 HoloLens 2 上不支持通过蓝牙外设启用麦克风捕获的蓝牙免提配置文件。

如果使用 Bluetooth 设备时遇到问题，请确保它是受支持的设备。 支持的设备包括：

- 使用英语语言的蓝牙键盘 (可以在任何使用全息键盘) 的地方使用。
- 蓝牙鼠标。
- [HoloLens clicker](hololens1-clicker.md)。

可以将其他蓝牙 HID 和 GATT 设备与 HoloLens 配对。 但是，你可能需要从 Microsoft Store 安装相应的随附应用才能实际使用设备。

[返回到列表](#list)

## <a name="im-having-problems-using-the-hololens-clicker"></a>使用 HoloLens clicker 时遇到问题

使用 [clicker](hololens1-clicker.md) 可选择、滚动、移动全息影像并调整其大小。 单个应用程序可以支持其他 clicker 手势。

如果在使用 clicker 时遇到问题，请确保它已计费，并与 HoloLens 配对。 如果电池电量低，指示灯闪烁表示琥珀色。 若要验证 clicker 是否配对，请访问 "**设置**" "  >  **设备**"，并查看其是否显示在该处。 有关详细信息，请参阅 [配对 clicker](hololens1-clicker.md)。

如果 clicker 的费用和配对并且仍有问题，请通过按住主按钮和 "配对" 按钮15秒来重置。 然后再将 clicker 与 HoloLens 配对。

如果重置 clicker 不起作用，请参阅 [重新启动或恢复 HoloLens clicker](hololens1-clicker.md#restart-or-recover-the-clicker)。

[返回到列表](#list)

## <a name="i-cant-connect-to-wi-fi"></a>我无法连接到 Wi-Fi

如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：

- 请确保已打开 Wi-Fi。 若要检查，请使用 "开始手势"，然后选择 "**设置**" "  >  **网络 &amp; Internet**  >  **wi-fi**"。 如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。
- 移动以靠近路由器或接入点。
- 重新启动 Wi-Fi 路由器，然后 [重新启动 HoloLens](hololens-recovery.md)。 请再次尝试连接。
- 如果这些操作都不起作用，请检查以确保路由器使用的是最新的固件。 你可以在制造商网站上找到此信息。

[返回到列表](#list)

## <a name="my-hololens-isnt-running-well-is-unresponsive-or-wont-start"></a>HoloLens 运行不正常，无响应或无法启动

如果设备运行不正常，请参阅 [重新启动、重置或恢复 HoloLens](hololens-recovery.md)。

[返回到列表](#list)

## <a name="i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else"></a>我无法登录到 HoloLens 设备，因为以前为其他人设置了它

如果你的设备以前是为其他人设置的，无论是针对客户端还是以前的员工，你都没有密码来解锁设备，你可以执行以下操作之一：

- 对于在 Intune 移动设备管理 (MDM) 中注册的设备，你可以使用 Intune 远程 [擦除](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 设备。 然后，设备会重新闪烁自身。  
   > [!IMPORTANT]  
   > 擦除设备时，请确保取消选中 " **保留注册状态和用户帐户** "。
- 对于非 MDM 设备，可以 [使设备进入 **闪烁模式** ，并使用高级恢复助理](hololens-recovery.md#clean-reflash-the-device) 来恢复设备。

[返回到列表](#list)

## <a name="questions-about-managing-hololens-devices"></a>有关管理 HoloLens 设备的问题

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>是否可以使用 System Center Configuration Manager (SCCM) 来管理 HoloLens 设备？

不是。 必须使用 MDM 系统来管理 HoloLens 设备。

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>是否可以使用 Active Directory 域服务 (AD DS) 管理 HoloLens 用户帐户？

不是。 必须使用 Azure Active Directory (Azure AD) 来管理 HoloLens 设备的用户帐户。

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>是否支持 HoloLens 自动数据捕获系统 (ADCS) 自动注册？

不是。

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens 是否可以参与集成的 Windows 身份验证？

不是。

### <a name="does-hololens-support-branding"></a>HoloLens 是否支持品牌？

不是。 不过，可以使用以下方法之一解决此问题：

- 创建一个自定义应用，然后 [启用展台模式](hololens-kiosk.md)。 自定义应用程序可以具有署名，还可以启动其他应用 (如远程协助) 。  
- 将 Azure AD 中的所有用户配置文件图片更改为你的公司徽标。 但是，这可能不适合所有方案。

### <a name="what-logging-capabilities-do-hololens-1st-gen-and-hololens-2-offer"></a>HoloLens (第一代) 和 HoloLens 2 产品/服务的哪种日志记录功能？

日志记录仅限于跟踪，可在开发或故障排除方案或设备发送到 Microsoft 服务器的遥测数据中捕获。

[返回到列表](#list)

## <a name="questions-about-securing-hololens-devices"></a>有关保护 HoloLens 设备的问题

请参阅 [HoloLens 2 安全信息](security-overview.md)。
对于 HoloLens 第一代设备，请查看 [此常见问题解答](hololens1-faq-security.md)。

[返回到列表](#list)

## <a name="how-do-i-delete-all-spaces"></a>如何实现删除所有空格？

*即将推出*

[返回到列表](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>我找不到或无法使用键盘键入 HoloLens 2 模拟器

*即将推出*

[返回到列表](#list)
