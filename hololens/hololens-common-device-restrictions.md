---
title: 常见设备限制
description: 随时更新混合现实设备的常见设备HoloLens设置。
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
ms.openlocfilehash: 6a09766a06fff912aae20dc07974b723d812bd370562a33297552dc0d2f7f12c
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664279"
---
# <a name="common-device-restrictions"></a>常见设备限制 

本指南可帮助 IT 专业人员了解适用于企业中 Windows 10 全息版 OS 的更常用管理选项。 请查阅你的 MDM 系统文档，以了解 MDM 供应商如何启用这些策略。 并非所有 MDM 系统都支持本指南中所述的每个设置。 一些系统通过 OMA-URI XML 文件支持自定义策略。 请参阅[对自定义策略的 Microsoft Intune 支持](/mem/intune/configuration/custom-settings-windows-10)。 命名约定在各个 MDM 供应商之间可能也会不同。

## <a name="prevent-changing-of-settings"></a>防止设置更改
通常允许员工更改某些你可能希望在公司设备上锁定的个人设备设置。 员工可以通过设置 UI 以交互方式HoloLens特定设置。 使用 MDM，你可以限制允许用户更改的内容。 下面列出了用于配置设置Windows 10 全息版的常用 MDM 设置：
-   [允许 VPN：](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允许用户更改 VPN 设置
-   [允许手动 WiFi 配置：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允许用户在 MDM Wi-Fi网络外部建立连接
-   [允许手动 MDM 取消注册](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允许用户删除工作区帐户 (即从 MDM 系统帐户取消注册) 

在[Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2)版中为HoloLens 2添加：
- [允许添加预配包：](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 切换用户能否添加新的预配包，覆盖新值。
- [允许删除预配包：](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 切换用户能否删除预配包，从而切换以前锁定的设置。

在受支持的策略HOLOLENS中查找有关策略选项[的更多详细信息](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>硬件限制
Windows 10 全息版设备使用最先进的技术，其中包括常用硬件功能，例如相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-Fi。 可使用硬件限制控制这些功能的可用性。
下面列出了用于配置硬件Windows 10 全息版的常用 MDM 设置：

> [!NOTE]
> 其中一些硬件限制会影响连接性，有助于数据保护。

-   [允许 Wi-Fi：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在设备上启用和使用 WiFi 无线电。
-   [允许 USB 连接：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB (不会影响 USB 充电。) 
-   [允许蓝牙：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)用户是否可以在设备上启用蓝牙无线无线广播。
-   [限制相机：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera)指定Windows应用是否可以访问相机。
-   [限制麦克风：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone)指定Windows是否可以访问麦克风。

已添加到[Windows Holographic，verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中HoloLens 2设备。 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 设置显示关闭之前的时间，通过关闭显示器锁定设备。 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 设置显示关闭之前的时间，通过关闭显示器锁定设备。 
