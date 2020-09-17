---
title: 常见设备限制
description: 通常在 HoloLens 上设置的设备 restrctions。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016761"
---
# 常见设备限制 

本指南可帮助 IT 专业人员了解适用于企业中的 Windows 10 全息操作系统的更常用的管理选项。 请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。 并非所有 MDM 系统都支持本指南中所述的每个设置。 一些系统通过 OMA-URI XML 文件支持自定义策略。 请参阅[对自定义策略的 Microsoft Intune 支持](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。 命名约定在各个 MDM 供应商之间可能也会不同。

## 防止设置更改
通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。 员工可以通过 "设置" UI 以交互方式调整 HoloLens 的某些设置。 使用 MDM，你可以限制允许用户更改的内容。 以下列出了 Windows 10 全息支持配置设置限制的常用 MDM 设置：
-   [允许 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置
-   [允许手动 WiFi 配置：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM 预配网络外建立 Wlan 连接
-   [允许手动取消注册](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (也就是说，从 MDM 系统取消注册设备) 

在 HoloLens 支持的[策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中查找有关策略选项的更多详细信息

## 硬件限制
Windows 10 全息版设备使用包含常用硬件功能（如相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-fi）的一流技术。 可使用硬件限制控制这些功能的可用性。
以下列出了 Windows 10 全息支持配置硬件限制的常用 MDM 设置：

> [!NOTE]
> 其中一些硬件限制会影响连接并帮助保护数据。

-   [允许 wi-fi：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用和使用 WiFi 收音机。
-   [允许 USB 连接：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (不会影响 USB 收费。 ) 
-   [允许蓝牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在其设备上启用和使用蓝牙收音机。
-   [限制相机：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 应用是否可以访问相机。
-   [限制麦克风：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 应用是否可以访问麦克风。
