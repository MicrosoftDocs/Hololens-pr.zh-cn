---
title: 证书管理器
description: 了解如何在 HoloLens 2 混合现实设备上手动安装、管理和删除证书。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283683"
---
# 证书管理器

- 通过新的证书管理器改进了设备安全性和合规性的审核、诊断和验证工具。 此功能将使您能够在商业环境中大规模部署、排查和验证证书。

在 Windows Holographic 版本 20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 转到" **设置>更新&安全>证书**。 此功能提供在设备上查看、安装和删除证书的简单且用户友好的方式。 借助新的证书管理器，管理员和用户现在拥有改进的审核、诊断和验证工具，以确保设备保持安全与合规。 

-   **审核：** 能够验证证书是否正确部署或确认证书已正确删除。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间并帮助进行故障排除。 
-   **验证：** 在大规模部署证书之前，验证证书是否达到预期目的并正常工作，可以节省大量时间，尤其是在商业环境中。

若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。 用户还可以直接搜索证书。 若要查看单个证书属性，请选择证书并单击 **"信息"。** 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户中。 用户只能删除直接从"设置"UI 安装的证书。 如果证书是通过其他方式安装的，则还必须使用同一机制将其删除。

## 安装证书： 

1.  将 HoloLens 2 连接到电脑。
1.  将你想要安装的证书文件放在 HoloLens 2 上的位置。
1.  导航到 **"设置>更新&安全>证书**，然后选择"安装证书"。
1.  单击 **"导入** 文件"并导航到保存证书的位置。
1.  选择 **"存储位置"。**
1.  选择 **证书存储**。
1.  单击**安装**。

现在应在设备上安装证书。

## 若要删除证书，请： 
1. 导航到 **设置应用>更新和安全>证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 **"删除"**
1. 当 **系统** 提示确认时，选择"是"。


![Ceritifcates 下的"设置"应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 在"设置"中安装证书的图片。](images/certificate-device-install.jpg)
