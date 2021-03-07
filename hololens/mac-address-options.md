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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393836"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>MAC 地址中 HoloLens 设备的企业注册限制 WLAN 环境

本文将介绍在客户环境中标识的一种常见方案，其中WLAN 受 MAC 地址的限制，或者需要证书来加入无线网络。

## <a name="example-scenario"></a>示例方案

安全环境中的许多客户对其无线或有线网络有限制，这将只允许批准的设备（基于 MAC 地址）成功连接。 这可以通过无线访问点上的 MAC 地址筛选或通过 DHCP 服务器强制执行。 此外，一些无线网络可通过 PEAP 进行保护，这要求在无线网络上进行身份验证之前，先将证书应用于设备。

在这种情况下，将 HoloLens 设备连接到网络时，两个关键要求可能会导致延迟或需要人工干预：

- 在设备成功加入无线网络之前必须将无线 PEAP 证书应用于设备。
- 必须注册 HoloLens WLAN 适配器的 MAC 地址。

上述要求的核心挑战包括：

1. 目前，MAC 地址只能从设备上的设置应用中标识，或在成功进行注册后从 Intune 标识。
2. 没有 MAC 地址，设备就无法加入 WLAN 网络开始注册。
3. 手动解决这些问题需要技术人员与设备交互。

## <a name="solutions"></a>解决方案

有许多方法可以改善这种情况，具体取决于环境中可用的基础设施。

| 解决方案 | 优势 | 要求 |
| --- | --- | --- |
| 使用以太网适配器预配程序包 | 改进 OOBE 体验，更快地提供技术人员体验。 | HoloLens 兼容的 USB C 集线器和以太网适配器，技术人员仍需与设备进行交互，以实现 MAC 捕获和 OOBE 最终定稿 |
| Autopilot 在以太网上使用 Intune 注册 | 这是设备到客户环境的单步骤连接和注册。 MAC 捕获无需与设备交互即可完成 | Intune 已为客户 AAD 租户和 HoloLens 兼容的 USB-C 以太网适配器启用 |
| 自动报告 MAC 地址 | 在 Intune 租户中注册设备后，脚本可以将 MAC 地址报告给技术人员。 | Intune Powershell Commandlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>使用以太网适配器预配程序包

> [!NOTE] 
> 如果有线网络还受 MAC 限制的约束，则需要预批准 USB-C 集线器和以太网适配器的 MAC 地址。 请注意，这种适配器将允许从其他设备访问网络。

### <a name="requirements"></a>要求

- 可访问客户网络的有线网络端口
- HoloLens 兼容的 USB-C 集线器，含有一个以太网适配器 - 不&#39;需要任何额外的驱动程序或应用程序安装的任何适配器均适用。
- 预配程序包包括：
  - 包含无线网络信息和证书
  - （可选）包含组织 Azure AD 的注册信息
  - 包含所有其他必需的预配设置

### <a name="process"></a>过程

该过程可能有所不同，具体取决于设备的软件级别。 如果该设备已于 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，请遵循以下步骤。

1. 将预配程序包放到 USB 棒的根位置，然后插入集线器。
2. 将以太网缆线连接到集线器和以太网适配器。
3. 将 USB-C 集线器连接到 HoloLens 设备。
4. 打开 HoloLens，然后戴上设备。
5. 按**音量和电源按钮**应用预配程序包。
6. 技术人员现在可以按照 OOBE 操作，完成后打开设置应用，然后检索设备的 MAC 地址。

如果该设备在 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前进行了操作系统构建，请遵循以下步骤。

1. 打开 HoloLens，然后将设备插入电脑。
2. 设备应在电脑上显示为文件存储设备。
3. 预配程序包复制到设备
4. 将以太网缆线连接到集线器。
5. 将 USB-C 集线器连接到 HoloLens 设备。
6. 戴上 HoloLens
7. 按**音量和电源**按钮应用预配程序包。
8. 技术人员现在可以按照 OOBE 操作，完成后打开设置应用，然后检索设备的 MAC 地址。

### <a name="benefits"></a>优势

这将允许设备&quot;单一触控&quot;应用正确的预配程序包并收集设备的 MAC 地址。 [可按此指南创建预配程序包。](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>具有 Intune 注册的 Autopilot

### <a name="requirements"></a>要求

- 可访问客户网络的有线网络端口
- 运行 Windows Holographic 2004 的 HoloLens 设备
- HoloLens 兼容的 USB-C 以太网适配器
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

### <a name="process"></a>过程

1. 将以太网电缆连接到适配器，然后将适配器插入 HoloLens 2 设备上的 USB-C 端口。
2. 打开 HoloLens。
3. 设备应在 OOBE 期间通过以太网适配器自动连接到 Internet。 它应检测 Autopilot 配置，并自动向 Azure AD 和 Intune 注册
4. 设备将根据需要通过 Intune 应用所需的 Wlan 证书和其他配置
5. 完成后，技术人员可加载 Intune （终结点管理器）门户，并钻取到**主页 > 设备 -> 设备名称- > 硬件**的设备属性页面。
6. Wifi MAC 地址将显示在 Intune 门户中

![通过 Intune 检索 MAC 地址](images/mac-address-intune.jpg)

7. 技术人员将此 MAC 地址添加为允许的设备。

### <a name="benefits"></a>优势

这将允许技术人员获得&quot;直接的&quot; 部署体验，并且设备可以从盒中到 Azure AD 和 Intune 中注册，而技术人员无需佩戴设备或手动与 HoloLens 环境进行交互。

## <a name="reporting-of-mac-addresses-to-the-technician"></a>向技术人员报告 MAC 地址

### <a name="requirements"></a>要求

- 针对客户租户 &quot;Intune Graph PowerShell&quot; 进行授权
- 安装技术人员机器上的 Intune Graph PowerShell。
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

### <a name="process"></a>过程

Intune 注册完成后，技术人员将运行以上脚本检索 MAC 地址。
