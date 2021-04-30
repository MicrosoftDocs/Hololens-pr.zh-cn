---
title: 常见设备限制
description: 随时了解最新的适用于 HoloLens 混合现实设备的设备限制和设置。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308164"
---
# <a name="common-device-restrictions"></a>常见设备限制 

本指南可帮助 IT 专业人员了解适用于企业中的 Windows 10 全息版 OS 的更常用的管理选项。 请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。 并非所有 MDM 系统都支持本指南中所述的每个设置。 一些系统通过 OMA-URI XML 文件支持自定义策略。 请参阅[对自定义策略的 Microsoft Intune 支持](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。 命名约定在各个 MDM 供应商之间可能也会不同。

## <a name="prevent-changing-of-settings"></a>防止设置更改
通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。 员工可以通过 "设置" UI 交互调整 HoloLens 的某些设置。 使用 MDM，你可以限制允许用户更改的内容。 下面列出了 Windows 10 全息版支持的用于配置设置限制的常用 MDM 设置：
-   [允许 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置
-   [允许手动配置 WiFi：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM 预配的网络以外建立 Wi-Fi 连接
-   [允许手动取消注册 mdm](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (例如，从 MDM 系统取消注册设备) 

在适用于 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中添加：
- [允许添加预配包：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 如果用户可以添加新的预配包，则切换，并将其替换为新值。
- [允许删除预配包：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 如果用户可以删除预配包，则切换，使其可以切换以前锁定的设置。

在 HoloLens 支持的[策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中查找有关策略选项的更多详细信息

## <a name="hardware-restrictions"></a>硬件限制
Windows 10 全息版设备使用最先进的技术，其中包括相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-fi 等常用硬件功能。 可使用硬件限制控制这些功能的可用性。
下面列出了 Windows 10 全息版支持的、用于配置硬件限制的常用 MDM 设置：

> [!NOTE]
> 其中一些硬件限制会影响连接性，并帮助保护数据。

-   [允许 wi-fi：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用并使用 WiFi 收音机。
-   [允许 USB 连接：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (不会影响 USB 充电 ) 
-   [允许蓝牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在其设备上启用和使用蓝牙收音机。
-   [限制照相机：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 应用是否可以访问相机。
-   [限制麦克风：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 应用是否可以访问麦克风。

添加在适用于 HoloLens 2 设备的 [Windows 全息版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中。 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 设置显示关闭后的时间长度，并关闭显示，锁定设备。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 设置显示关闭后的时间长度，并关闭显示，锁定设备。 
