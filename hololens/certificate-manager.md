---
title: 证书管理器
description: 了解如何在混合现实设备上手动安装、管理和HoloLens 2证书。
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
ms.openlocfilehash: 438a132a6bafd8c93b148b9c2c817ec93cc3bc73651f08275acc130695fa09c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665176"
---
# <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能可让你在商业环境中大规模部署、排查和验证证书。

在 Windows Holographic 版本 20H2 中，我们将在 HoloLens 2 设置 应用中添加证书管理器。 转到 **"设置 >更新&安全>证书"。** 此功能提供了一种简单且用户友好的方式来查看、安装和删除设备上证书。 借助新的证书管理器，管理员和用户现在改进了审核、诊断和验证工具，以确保设备保持安全且合规。 

-   **审核：** 能够验证证书是否正确部署，或确认证书已正确删除。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间，并有助于进行故障排除。 
-   **验证：** 验证证书是否符合预期目的且正常运行，可以节省大量时间，尤其是在商业环境中，然后再大规模部署证书。

若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。 用户还可以直接搜索证书。 若要查看单个证书属性，请选择证书，然后单击"信息 **"。** 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户中。

## <a name="to-install-a-certificate"></a>安装证书： 

1.  连接HoloLens 2电脑。
1.  将要安装的证书文件放在证书HoloLens 2。
1.  导航 **到设置应用>更新&安全>证书"，** 然后选择"安装证书"。
1.  单击 **"导入** 文件"并导航到保存证书的位置。
1.  选择"**存储位置"。**
1.  选择 **"证书存储"。**
1.  单击“安装”  。

现在应在设备上安装证书。

![证书应用下设置证书查看器。](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 在证书颁发机构中安装证书设置。](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>删除证书：

> [!WARNING]
> 使用证书管理器，用户只能从证书 UI 中删除设置证书。 如果证书是通过其他方式安装的，则也必须使用相同的机制将其删除，并且不能从证书管理器中删除该证书。 虽然可以在证书管理器中查看 MDM 部署的证书，但是无法在证书管理器中将其卸载。 必须通过 MDM 将其卸载。

1. 导航到 **"设置应用>更新和安全>证书"。**
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击" **删除"**
1. 出现确认提示时，选择“是”。

