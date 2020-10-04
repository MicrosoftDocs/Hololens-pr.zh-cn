---
title: MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境
description: 如何在 HoloLens 2 设备上获取网络的 MAC 地址
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093220"
---
# MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境

本文将介绍在客户环境中标识的一种常见方案，其中WLAN 受 MAC 地址的限制，或者需要证书来加入无线网络。

## 示例方案

在安全环境中，许多客户对其无线或有线网络有限制，这将仅允许已批准的设备（基于 MAC 地址）连接成功（在无线访问点或 DHCP 服务器上进行 MAC 地址筛选）。 此外，一些无线网络可通过 PEAP 进行保护，这要求在能够成功对无线网络进行身份验证前，向设备应用证书。

HoloLens 设备可能会产生两个重要问题，这可能会导致延迟和在将 HoloLens 设备加入到网络时需要进行手动操作。

- 在设备成功加入无线网络之前必须将无线 PEAP 证书应用于设备。
- 必须注册 HoloLens WLAN 适配器的 MAC 地址。

其关键挑战有：

1. 目前，MAC 地址只能从设备上的设置应用中标识，或在成功进行 Intune 注册后从 Intune 标识。
2. 没有 MAC 地址，设备就无法加入 WLAN 网络开始注册。
3. 这些挑战的手动解决方案要求技术人员通过设备参与。

## 解决方案

可通过多种方法来改善这种情况，具体取决于环境中提供的基础结构。

| 解决方案 | 优势 | 要求 |
| --- | --- | --- |
| 使用以太网适配器预配程序包 | 改进 OOBE 体验，更快地提供技术人员体验。 | HoloLens 兼容的 USB C HubTechnician 仍需与设备进行交互，以实现 MAC 捕获和 OOBE 最终定稿 |
| Autopilot 在以太网上使用 Intune 注册 | 单步连接和将设备注册到客户 environmentMAC 捕获可以在不与设备交互的情况下完成 | 已为客户 AAD TenantHoloLens 启用 Intune 兼容的 USB-C 网络适配器 |
| 自动报告 MAC 地址 | 在 Intune 租户内注册设备后，将 MAC 地址的报告脚本给技术人员。 | Intune Powershell Commandlets |

## 使用以太网适配器预配程序包

> [!NOTE] 
> 如果有线网络还受 MAC 限制的约束，则需要预批准 USB-C 以太网适配器/集线器的 MAC 地址。 请注意，这种集线器将允许从其他设备访问网络。

### 要求

- 可访问客户网络的有线网络端口
- HoloLens 兼容的 USB-C 集线器，包括一个以太网适配器 - 不&#39;需要任何额外的驱动程序或应用程序安装的任何集线器均适用。
- 预配程序包包括：
  - 包含无线网络信息和证书
  - 可选择包含针对组织 &#39;的 Azure AD 证书注册
  - 包含所有其他必需的预配设置

### 过程

该过程可能有所不同，具体取决于设备的软件级别。 如果该设备已于 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，请遵循以下步骤。

1. 将预配程序包放到 USB 棒的根位置，然后插入集线器。
2. 将以太网缆线连接到集线器。
3. 将 USB-C 集线器连接到 HoloLens 设备。
4. 打开 HoloLens 设备并佩戴设备。
5. 按**音量和电源按钮**应用预配程序包。
6. 技术人员现在可以按照 OOBE 操作，完成后，打开设置应用，然后检索设备的 MAC 地址。

如果该设备在 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前进行了操作系统构建，请遵循以下步骤。

1. 打开 HoloLens 设备，然后将设备插入电脑。
2. 设备应在电脑上显示为文件存储设备。
3. 预配程序包复制到设备
4. 将以太网缆线连接到集线器。
5. 将 USB-C 集线器连接到 HoloLens 设备。
6. 佩戴设备。
7. 按**音量和电源**按钮应用预配程序包。
8. 技术人员现在可以按照 OOBE 操作，完成后，打开设置应用，然后检索设备的 MAC 地址。

### 优势

这将允许设备&quot;单一触控&quot;应用正确的预配程序包并收集设备的 MAC 地址。 [可按此指南创建预配程序包。](https://docs.microsoft.com/hololens/hololens-provisioning)

## Autopilot 使用 Intune 注册

### 要求

- 可访问客户网络的有线网络端口
- 运行 Windows Holographic 2004 的 HoloLens 设备
- HoloLens 兼容的 USB-C 集线器
- 已为客户租户设置并启用 Intune
- 为 Autopilot 注册并导入客户租户的设备
- 已为设备定义 Intune 策略：
   - 包含无线网络信息和证书
   - 包含所有其他必需的预配设置

这将允许有高级网络需求的客户以一种不干涉的、可伸缩的方式注册设备。

需要更多先决条件，如下所示：
1. [为 Autopilot 预览版启用租户](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. 创建 HoloLens 策略以替换 Intune 内的预配程序包。
1. 创建 HoloLens Intune 策略。
1. 向正确的组分配设备。

### 过程

1. 将 USB-C 集线器和以太网缆线插入 HoloLens 2 设备。
2. 打开 HoloLens 2。
3. 设备应通过以太网适配器在 OOBE 处自动连接到网络，检测 Autopilot 配置，并使用 Azure AD 和 Intune 自动注册
4. 设备将根据需要通过 Intune 应用所需的 Wlan 证书和其他配置
5. 完成后，技术人员将能够加载 Intune （终结点管理器）门户，并钻取到**主页 > 设备 -> 设备名称- > 硬件**的设备属性页面。
6. Wifi MAC 地址将显示在 Intune 门户中

![通过 Intune 检索 MAC 地址](images/mac-address-intune.jpg)

7. 技术人员将此 MAC 地址添加为允许的设备。

### 优势

这将允许技术人员获得&quot;直接的&quot; 部署体验，并且设备可以从盒中到 AAD 和 Intune 中注册，而技术人员无需佩戴设备或手动与 HoloLens 环境进行交互。

## 向技术人员报告 MAC 地址

### 要求

- 针对客户租户 &quot;Intune Graph Powershell&quot; 进行授权
- 安装技术人员机器上的 Intune Graph Powershell。
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune 元素&quot;托管设备&quot;的读取权限。 （支持人员过程调用或更高版本或自定义角色）

目前，还没有一种&quot;简单&quot;的方法来触发基于在Intune中注册新设备的自动命令。 因此，此命令将为技术人员提供一种检索 MAC 地址的简单方法，无需登录到门户并手动检索。

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

这将返回最近 30 天内已注册的任何 HoloLens 设备的名称和 MAC 地址。

![通过 Powershell 检索 MAC 地址](images/mac-address-powershell.jpg)

### 过程

Intune 注册完成后，技术人员将运行以上脚本检索 MAC 地址。
