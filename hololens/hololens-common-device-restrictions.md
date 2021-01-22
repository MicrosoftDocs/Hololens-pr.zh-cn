---
title: 通用设备限制
description: 使用 HoloLens 混合现实设备的常见设备限制和设置保持最新。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283353"
---
# 通用设备限制 

本指南可帮助 IT 专业人员了解企业中适用于 Windows 10 全息操作系统的更常用管理选项。 请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。 并非所有 MDM 系统都支持本指南中所述的每个设置。 一些系统通过 OMA-URI XML 文件支持自定义策略。 请参阅[对自定义策略的 Microsoft Intune 支持](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。 命名约定在各个 MDM 供应商之间可能也会不同。

## 防止设置更改
通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。 员工可以通过设置 UI 以交互方式调整 HoloLens 的某些设置。 使用 MDM，你可以限制允许用户更改的内容。 下面列出了 Windows 10 全息版支持配置设置限制的常用 MDM 设置：
-   [允许 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置
-   [允许手动 WiFi 配置：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM Wi-Fi网络外部建立连接
-   [允许手动 MDM 注销](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (例如，从 MDM 系统帐户注销) 

在适用于 HoloLens 2 设备的 [Windows 全息版版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中添加：
- [允许添加预配包：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 切换用户能否添加新的预配包，并覆盖新值。
- [允许删除预配包：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 如果用户可以删除预配包，则切换，以允许用户切换以前锁定的设置。

在 HoloLens 支持的策略[CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中查找有关策略选项的更多详细信息

## 硬件限制
Windows 10 全息版设备使用现代技术，其中包括热门硬件功能，例如相机、麦克风、扬声器、USB 接口、Bluetooth接口和 WLAN。 可使用硬件限制控制这些功能的可用性。
下面列出了 Windows 10 全息版支持配置硬件限制的常用 MDM 设置：

> [!NOTE]
> 其中一些硬件限制会影响连接性并有助于数据保护。

-   [允许 WLAN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在设备上启用和使用 WiFi 无线电。
-   [允许 USB 连接：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 连接是否已启用 (不会影响 USB 充电。) 
-   [允许Bluetooth：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在设备上启用和使用Bluetooth无线广播。
-   [限制相机：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 应用是否可以访问相机。
-   [限制麦克风：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 应用是否可以访问麦克风。

在[Windows 全息版中为 HoloLens 2 设备添加了 verison 20H2。](hololens-release-notes.md#windows-holographic-version-20h2) 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 设置在屏幕关闭之前的时间量，然后通过关闭屏幕锁定设备。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 设置在屏幕关闭之前的时间量，然后通过关闭屏幕锁定设备。 
