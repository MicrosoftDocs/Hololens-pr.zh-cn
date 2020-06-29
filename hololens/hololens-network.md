---
title: 连接到网络
description: 介绍如何使用 HoloLens 连接到 Internet 以及如何识别设备的 IP 地址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 无线, Internet, ip, ip 地址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827978"
---
# 连接到网络

要想在 HoloLens 上进行更多操作，则必须连接到网络。 本指南将帮助你：

- 使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络
- 禁用并重新启用 WLAN

了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。

## 首次连接

首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。 如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。 确保不需要使用证书就能连接网络。 完成设置后，你可以连接到其他类型的 WLAN 网络。

## 设置完成后连接到 WLAN

1. 选择**开始** > **设置**。
   - *仅限 HoloLens（第一代）*：通过注视定位“设置”应用，然后通过隔空敲击或说“放置”来进行放置。
1. 选择**网络和 Internet** > **WLAN**。 如果未看到你的网络，请向下滚动列表。
1. 选择一个网络，然后选择**连接**。
1. 如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。

## 在 HoloLens（第一代）上连接到 WLAN

HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。 将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

1. 打开**开始**菜单。
1. 从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择“设置”应用。 “设置”应用将自动放置在你面前。
1. 选择**网络和 Internet**。
1. 确保 WLAN 已打开。
1. 从列表中选择 WLAN 网络。
1. 如果需要，请键入 WLAN 网络密码。

你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：

1. 打开**开始**菜单。
1. 查看**开始**菜单左上方的 WLAN 状态。 那里将显示 WLAN 状态和已连接网络的 SSID。

## Wi-Fi 连接故障排除

如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。

在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。

## 在 HoloLens（第一代）上禁用 WLAN

### 在 HoloLens 上使用“设置”应用

1. 打开**开始**菜单。
1. 从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。 **设置**应用将自动放置在你面前。
1. 选择**网络和 Internet**。
1. 选择 WLAN 滑块开关将其移至**关闭**位置。 这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。

    > [!WARNING]
    > 禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。

1. 将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。 选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。

## 识别你的 HoloLens 在 WLAN 网络上的 IP 地址

### 通过使用“设置”应用

1. 打开**开始**菜单。
1. 从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。 **设置**应用将自动放置在你面前。
1. 选择**网络和 Internet**。
1. 向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   IP 地址出现在 **IPv4 地址**旁边。

### 通过使用 Cortana

说：“你好小娜，我的 IP 地址是什么？”， Cortana 便会显示并读出你的 IP 地址。

### 通过使用 Windows 设备门户

1. 在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 导航到**网络**部分。  
   此部分将显示你的 IP 地址和其他网络信息。 通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。
