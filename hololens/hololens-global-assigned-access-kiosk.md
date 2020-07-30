---
title: 全局分配的访问权限
description: 全局分配的访问权限展台 OMA-URI 使用指南
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902297"
---
# 全局分配的访问权限 – 展台

此功能配置适用于多应用展台模式的 Hololens 2 设备，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。 

> [!NOTE]
> 此功能目前仅适用于 Windows 预览体验成员版本。 如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [ Windows 预览体验成员](hololens-insider.md)版本的更多信息。
 
## 如何在 Intune 中使用此功能？ 

> [!NOTE]
> 请注意标记有 "<!-" 的区域。 这些区域将要求你根据自己的偏好进行修改。 

1.  按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：![Intune 中的全局分配访问权限](images/global-assigned-access-omauri.png)

2.  对于数值，请更新并粘贴以下内容： 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## 如何在 Windows 配置设计器中使用此功能？ 
 
1.  更新并保存上面提及的 XML 文件。 

2.  请按照[使用预配包设置单应用或多应用展台](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作，特别是“预配 程序包，步骤 2 – 向预配包添加展台配置 XML 文件”一节并参考上一步中保存的 XML 文件。 

## 我是否能够创建可全局应用至除 1 个 AAD 账户或 AAD 组之外的所有人的配置？ 

可以，请参阅下面的示例 XML blob。 如果未找到登录用户的特定用户，则全局分配的访问权限配置文件将应用于 Hololens，因此它是登录用户的默认展台模式配置。 下面是要使用的 XML blob 示例： 

> [!NOTE]
> 请注意标记有 "<!-" 的高亮区域，这些区域将要求你根据自己的偏好进行修改。 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## 从全局分配的访问配置文件中排除设备所有者

此功能允许在 Hololens 上被视为“ [设备所有者](security-adminless-os.md)”的用户被排除在全局分配的访问权限之外。 若要使用此功能，请在适用于多应用程序展台配置的 XML blob 中，确保添加突出显示的行： 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
