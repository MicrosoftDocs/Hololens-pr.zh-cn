---
title: 将 HoloLens 连接到网络
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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883146"
---
# 将 HoloLens 连接到网络

要想在 HoloLens 上进行更多操作，则必须连接到网络。 本指南将帮助你：

- 使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络
- 禁用并重新启用 WLAN

了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。

## 首次连接

首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。 如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。 确保不需要使用证书就能连接网络。 完成设置后，你可以连接到其他类型的 WLAN 网络。

## 设置完成后连接到 WLAN

1. 执行**开始手势**并选择**设置**。 “设置”应用将自动放置在你面前。
1. 选择**网络和 Internet** > **WLAN**。 确保 WLAN 已打开。 如果未看到你的网络，请向下滚动列表。
1. 选择一个网络，然后选择**连接**。
1. 如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。

HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。 将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：

1. 打开**开始**菜单。
1. 查看**开始**菜单左上方的 WLAN 状态。 那里将显示 WLAN 状态和已连接网络的 SSID。

## Wi-Fi 连接故障排除

如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。

在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。

## VPN
VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。 HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。 

支持的内置 VPN 协议：
- IKEv2
- L2TP
- PPTP

如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。 要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。 HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。

默认情况下 VPN 未启用，可通过打开 **设置** 应用然后导航到 **网络和 Internet -> VPN** 手动启用。 MDM 通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)可管理VPN，并通过 [Vpnv2-csp 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 进行设置。
了解更多关于[如何配置 VPN ](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)的信息，可参阅[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)。  

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

### 通过使用语音命令

根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？” 然后它会显示。 对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？” Cortana 便会显示并读出你的 IP 地址。

### 通过使用 Windows 设备门户

1. 在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 导航到**网络**部分。  
   此部分将显示你的 IP 地址和其他网络信息。 通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。
