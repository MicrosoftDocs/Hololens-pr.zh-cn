---
title: 有关 HoloLens 设备和全息影像的常见问题
description: 你是否有关于 HoloLens 或与全息影像交互的快速问题？  本文提供了快速答案和更多资源。
keywords: hololens, 常见问题, 已知问题, 帮助
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
ms.openlocfilehash: cb9234556d0b5c654747e0f404d1d10d8a2cd539
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827857"
---
# 有关 HoloLens 设备和全息影像的常见问题

本文回答了有关如何使用 HoloLens 的一些问题，包括如何放置全息影像、如何使用空间等。

无论何时遇到问题，都请确保 HoloLens [已充满电](https://support.microsoft.com/help/12627/hololens-charge-your-hololens)。 请尝试[重启它](hololens-restart-recover.md)以查看是否修复了问题。 请使用反馈应用向我们发送有关该问题的信息。 可在[“**开始**”菜单上找到反馈应用](holographic-home.md)。

有关如何佩戴 HoloLens 的提示，请参阅 [HoloLens（第 1 代）舒适佩戴常见问题](hololens1-fit-comfort-faq.md)。

本文将解决以下问题：
<a id="list"></a>

- [我的全息影像看起来不正常或四处移动](#my-holograms-dont-look-right-or-are-moving-around)
- [我看到一条消息，显示“正在查找你的空间”](#i-see-a-message-that-says-finding-your-space)
- [我在自己的空间中看不到所期望的全息影像](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [我无法将全息影像放置在所需的位置](#i-cant-place-holograms-where-i-want-to)
- [全息影像消失或被其他全息影像或物体遮挡](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [我看到位于墙壁另一面的全息影像](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [将全息影像放置在墙壁上时，全息影像好像是浮动的](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [尝试移动应用时，它们似乎离我太近了](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [我收到磁盘空间不足的错误](#im-getting-a-low-disk-space-error)
- [HoloLens 未响应我的手势](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens 未响应我的语音](#hololens-doesnt-respond-to-my-voice)
- [我在配对或使用蓝牙设备时遇到问题](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens 设置列出了可用的设备，但该设备无法正常工作](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [我在使用 HoloLens 遥控器时遇到问题](#im-having-problems-using-the-hololens-clicker)
- [我无法连接到 Wi-Fi](#i-cant-connect-to-wi-fi)
- [我的 HoloLens 未正常运行、没有响应或无法启动](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [我无法登录到 HoloLens 设备，因为该设备以前是为其他人设置的](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [有关管理 HoloLens 设备的问题](#questions-about-managing-hololens-devices)
- [有关保护 HoloLens 设备的问题](#questions-about-securing-hololens-devices)
- [如何删除所有空间？](#how-do-i-delete-all-spaces)
- [我在 HoloLens 2 模拟器中找不到或无法使用键盘进行键入](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## 我的全息影像看起来不正常或四处移动

如果你的全息影像看起来不正常（例如抖动或晃动，或者你在其上方看到黑色斑点），请尝试以下修复方法之一：

- [清洁设备面板](hololens1-hardware.md#care-and-cleaning)并确保没有任何物体挡住传感器。
- 确保房间光线充足，但阳光照射不至于太强烈。
- 尝试四处走动并注视四周，以便 HoloLens 能够更全面地扫描它们。
- 如果你放置了大量全息影像，请尝试删除某些全息影像。

如果仍有问题，请尝试运行“校准”应用。 此应用旨在为你校准 HoloLens，以帮助保持全息影像的最佳效果。 若要执行此操作，请转到“**设置**” > “**系统**” > “**实用工具**”。 在“**校准**”下，选择“**打开校准**”。

[返回列表](#list)

## 我看到一条消息，显示“正在查找你的空间”

当 HoloLens 正在记忆或加载空间时，你可能会看到一条简短消息，显示“正在查找你的空间”。 如果此消息显示超过几秒钟，你将在“开始”菜单下看到另一条消息，显示“仍在查找你的空间”。

这些消息表示 HoloLens 无法映射你的空间。 发生这种情况时，你可以打开应用，但无法将全息影像放置在环境中。

如果你经常看到这些消息，请尝试以下一种或多种修复方法：

- 确保房间光线充足，但阳光照射不至于太强烈。
- 确保设备面板清洁干净。 [了解如何清洁面板](hololens1-hardware.md#care-and-cleaning)。
- 确保你使用的是强 Wi-Fi 信号。 如果你进入一个没有 Wi-Fi 或 Wi-Fi 信号较弱的新环境，则 HoloLens 将无法找到你的空间。 通过进入“**设置**” > “**网络 &amp; Internet**” > “**Wi-Fi**”来检查你的 Wi-Fi 连接。
- 尝试缓慢移动。

[返回列表](#list)

## 我在自己的空间中看不到所期望的全息影像

如果你看不到放置的全息影像，或者你看到的全息投影未达到预期效果，请尝试以下一种或多种修复方法：

- 打开灯光。 HoloLens 在光线良好的空间中工作效果最佳。
- 通过进入“**设置**” > “**系统**” > “**Holograms**” > “**删除附近的全息影像**”来删除不需要的全息影像。 或者，如果需要，选择“**删除所有全息影像**”。

  > [!NOTE]
  > 如果空间内的布局或光线发生显著变化，则设备可能无法识别你的空间和显示全息影像。

[返回列表](#list)

## 我无法将全息影像放置在所需的位置

如果你在放置全息影像时遇到问题，请尝试以下操作：

- 站在离全息影像放置位置 1 到 3 米的地方。
- 不要将全息影像放置在黑色或反光表面上。
- 确保房间光线充足，但阳光照射不至于太强烈。
- 在房间内四处走动，以便 HoloLens 能够重新扫描你的环境。 若要查看已扫描的内容，请空中点击以显示映射网格图形。

[返回列表](#list)

## 全息影像消失或被其他全息影像或物体遮挡

如果你离全息影像太近，它会暂时消失&mdash;若要恢复全息影像，只需远离它即可。 此外，如果已将多个全息影像放置在一起，则某些全息影像可能会消失。 尝试删除一些全息影像。

全息影像也可能被其他全息影像或物体（如墙壁）阻挡或遮挡。 如果发生这种情况，请尝试以下修复方法之一：

- 如果全息影像被其他全息影像遮挡，请将被遮挡的全息影像移到另一个位置。 若要执行此操作，请选择“**调整**”，然后点击并按住以进行定位。
- 如果全息影像被墙壁遮挡，请选择“**调整**”，然后走向墙壁，直至显示全息影像。 点击并按住，然后将全息影像向前拉出墙壁。
- 如果无法通过手势移动全息影像，请通过语音将其删除。 注视全息影像，然后说“删除”。 重新打开全息影像，并将其放置在新位置。

[返回列表](#list)

## 我看到位于墙壁另一面的全息影像

如果你离墙壁很近，或者 HoloLens 尚未扫描墙壁，则可能会看到隔壁房间的全息影像。 若要扫描墙壁，请站在离墙壁 1 到 3 米的地方，然后注视。

当 HoloLens 尝试扫描墙壁时，靠近墙壁的黑色或反光物体（如黑色沙发或不锈钢冰箱）可能会导致问题。 如果有此类物体，请扫描墙壁的另一面。

[返回列表](#list)

## 将全息影像放置在墙壁上时，全息影像好像是浮动的

放置在墙壁上的全息影像通常看起来距离墙壁一英寸左右。 如果看起来更远，请尝试以下一种或多种修复方法：

- 将全息影像放置在墙壁上时，站在离墙壁 1 到 3 米的地方，并直视墙面。
- 空中点击墙壁以显示映射网格图形。 请确保网格与墙壁对齐。 如果没有，请删除全息影像，重新扫描墙壁，然后重试。
- 如果问题仍然存在，请运行“校准”应用。 可在“**设置**” > “**系统**” > “**实用工具**”中找到该应用。

[返回列表](#list)

## 尝试移动应用时，它们似乎离我太近了

请尝试四处走动并查看你放置应用的区域，以便 HoloLens 从不同角度扫描该区域。 [清洁设备面板](hololens1-hardware.md#care-and-cleaning)可能有用。

[返回列表](#list)

## 我收到磁盘空间不足的错误

请执行下列一项或多项操作以释放一些存储空间：

- 删除某些已放置的全息影像，或从应用中删除某些保存的数据。 [如何查找我的数据？](holographic-data.md)
- 在“照片”应用中删除某些图片和视频。
- 从 HoloLens 中卸载某些应用。 在“**所有应用**”列表中，点击并按住要卸载的应用，然后选择“**卸载**”。 （卸载应用也会删除该应用存储在设备上的所有数据。）

[返回列表](#list)

## HoloLens 未响应我的手势

若要确保 HoloLens 可以看到你的手势，请将手放在手势框中。 手势框在你的两边延伸了几英尺。 当保持在你身前大约 18 英寸的位置（你不必精确到此距离）时，HoloLens 可以更好地看到你的手。 如果 HoloLens 可以看到你的手，光标将从圆点变为圆环。 了解有关[在 HoloLens 2 中使用手势](hololens2-basic-usage.md)或[在 HoloLens（第一代）中使用手势](hololens1-basic-usage.md)的详细信息。

[返回列表](#list)

## HoloLens 未响应我的语音

HoloLens（第一代）和 HoloLens 2 具有内置语音识别功能，并且还支持 Cortana（联机语音识别）。

### 内置语音命令无法正常工作

在 HoloLens（第一代）上，无法配置内置语音识别。 它始终处于开启状态。 在 HoloLens 2 上，你可以选择是否在设备设置过程中打开语音识别和 Cortana。

如果 HoloLens 2 未对你的语音作出响应，请确保语音识别处于开启状态。 转到“**开始**” > “**设置**” > “**隐私**” > “**语音**”并打开“**语音识别**”。

### Cortana 或听写无法正常工作

如果 Cortana 或听写未对你的语音作出响应，请确保联机语音识别处于开启状态。 转到“**开始**” > “**设置**” > “**隐私**” > “**语音**”，并验证“**联机语音识别**”设置。 

如果 Cortana 仍未响应，请执行下列操作之一，以验证 Cortana 自身是否已开启：

- 在“**所有应用**”中，选择“**Cortana**”>“**菜单**” > “**笔记本**” > “**设置**”以进行更改。
- 在 HoloLens 2 上，选择“**语音设置**”按钮或说“语音设置”。

若要了解有关可以说出的内容的详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。

[返回列表](#list)

## 我在配对或使用蓝牙设备时遇到问题

如果在[配对蓝牙设备](hololens-connect-devices.md)时遇到问题，请尝试以下操作：

- 转到“**设置**” > “**设备**”，并确保蓝牙已开启。 如果是，请将其关闭并重新打开。
- 确保你的蓝牙设备已充满电或装有新电池。
- 如果仍然无法连接，请[重启 HoloLens](hololens-recovery.md)。

[返回列表](#list)

## HoloLens 设置列出了可用的设备，但该设备无法正常工作

HoloLens 不支持蓝牙音频配置文件。 蓝牙音频设备（如扬声器和耳机）在 HoloLens 设置中可能会显示为可用，但它们不受支持。

如果你在使用蓝牙设备时遇到问题，请确保它是受支持的设备。 支持的设备包括：

- 英语 QWERTY 蓝牙键盘（可在使用全息影像键盘的任何位置使用它们）。
- 蓝牙鼠标。
- [HoloLens 遥控器](hololens1-clicker.md)。

可将其他蓝牙 HID 和 GATT 设备与 HoloLens 配对。 但是，你可能必须从 Microsoft Store 安装相应的配套应用，才能实际使用这些设备。

[返回列表](#list)

## 我在使用 HoloLens 遥控器时遇到问题

可使用[遥控器](hololens1-clicker.md)选择、滚动、移动和调整全息影像。 单个应用可能支持其他遥控器手势。

如果你在使用遥控器时遇到问题，请确保它已充电并与 HoloLens 配对。 如果电池电量低，指示灯将呈琥珀色闪烁。 若要验证遥控器是否已配对，请转到“**设置**” > “**设备**”，然后查看它是否显示在那里。 有关详细信息，请参阅[配对遥控器](hololens-connect-devices.md#hololens-1st-gen-pair-the-clicker)。

如果遥控器已充电并且已配对，但仍有问题，请按住主按钮和配对按钮 15 秒钟以将其重置。 然后再次将遥控器与 HoloLens 配对。

如果重置遥控器不起作用，请参阅[重启或恢复 HoloLens 遥控器](hololens1-clicker.md#restart-or-recover-the-clicker)。

[返回列表](#list)

## 我无法连接到 Wi-Fi

如果无法将 HoloLens 连接到 Wi-fi 网络，请尝试以下操作：

- 确保 Wi-Fi 已打开。 若要进行检查，请使用“开始”手势，然后选择“**设置**” > “**网络 &amp; Internet**” > “**Wi-Fi**”。 如果 Wi-fi 处于开启状态，请尝试将其关闭，然后再打开。
- 移至更靠近路由器或接入点的位置。
- 重启 Wi-Fi 路由器，然后[重启 HoloLens](hololens-recovery.md)。 再次尝试连接。
- 如果这些都不起作用，请进行检查以确保你的路由器使用的是最新固件。 可在制造商网站中找到此信息。

[返回列表](#list)

## 我的 HoloLens 未正常运行、没有响应或无法启动

如果设备未正常运行，请参阅[重启、重置或恢复 HoloLens](hololens-recovery.md)。

[返回列表](#list)

## 我无法登录到 HoloLens 设备，因为该设备以前是为其他人设置的

如果你的设备以前是为其他人（客户或前员工）设置的，而你没有解锁设备的密码，则可以执行以下操作之一：

- 对于在 Intune 移动设备管理 (MDM) 中注册的设备，你可以使用 Intune 远程[擦除](https://docs.microsoft.com/intune/remote-actions/devices-wipe)该设备。 然后设备会重新刷机。  
   > [!IMPORTANT]  
   > 擦除设备时，请确保未选中“**保留注册状态和用户帐户**”。
- 对于非 MDM 设备，你可以[将该设备置于**刷机模式**并使用高级恢复助手](hololens-recovery.md#clean-reflash-the-device)来恢复该设备。

[返回列表](#list)

## 有关管理 HoloLens 设备的问题

### 是否可以使用 System Center Configuration Manager (SCCM) 来管理 HoloLens 设备？

否。 必须使用 MDM 系统来管理 HoloLens 设备。

### 是否可以使用 Active Directory 域服务 (AD DS) 来管理 HoloLens 用户帐户？

否。 必须使用 Azure Active Directory (AAD) 来管理 HoloLens 设备的用户帐户。

### HoloLens 是否支持自动数据采集系统 (ADCS) 自动注册？

否。

### HoloLens 是否可以参与集成的 Windows 身份验证？

否。

### HoloLens 是否支持品牌宣传？

否。 但是，你可以使用以下方法之一来解决此问题：

- 创建自定义应用，然后[启用展台模式](hololens-kiosk.md)。 自定义应用可以进行品牌宣传，并且可以其他其他应用（如远程协助）。  
- 将 AAD 中的所有用户个人资料图片更改为贵公司徽标。 但是，并非所有方案都需要此操作。

### HoloLens（第一代）和 HoloLens 2 提供哪些日志记录功能？

日志记录仅限于在开发或故障排除方案中捕获的跟踪，或由设备发送到 Microsoft 服务器的遥测。

[返回列表](#list)

## 有关保护 HoloLens 设备的问题

请参阅[有关保护 HoloLens 设备的常见问题](hololens-faq-security.md)。

[返回列表](#list)

## 如何删除所有空间？

*即将推出*

[返回列表](#list)

## 我在 HoloLens 2 模拟器中找不到或无法使用键盘进行键入

*即将推出*

[返回列表](#list)
