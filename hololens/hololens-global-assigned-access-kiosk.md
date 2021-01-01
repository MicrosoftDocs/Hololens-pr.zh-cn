---
title: 全局分配的访问权限
description: 全局分配的访问权限展台 OMA-URI 使用指南
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253199"
---
# 全局分配的访问权限 – 展台

此功能配置适用于多应用展台模式的 HoloLens 2 设备，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。

> [!NOTE]
> 此功能目前仅适用于 Windows 预览体验成员版本。 如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [ Windows 预览体验成员](hololens-insider.md)版本的更多信息。

## 如何在 Intune 中使用全局分配的访问权限？

> [!NOTE]
> 请注意标记有 "<!-" 的区域。 这些区域将要求你根据自己的偏好进行修改。

1. 按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：

    URI 值：./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune 中全局分配的访问权限 OMA URI](images/global-assigned-access-omauri.png)

2. 对于数值，请更新并粘贴以下内容：

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## 如何在 Windows 配置设计器中使用全局分配的访问权限？

1. 更新并保存上面提及的 XML 文件。 

2. 请按照[使用预配包设置单应用或多应用展台](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作，特别是“预配 程序包，步骤 2 – 向预配包添加展台配置 XML 文件”一节并参考上一步中保存的 XML 文件。

## 我可以创建一个配置，其中全局应用于所有人，单独的配置应用于 1 个 Azure AD 帐户或 Azure AD 组吗？ 

可以，请参阅下面的示例 XML blob。 如果未找到登录用户的特定用户，则全局分配的访问权限配置文件将应用于 HoloLens，因此它是登录用户的默认展台模式配置。
下面是要使用的 XML blob 示例：

> [!NOTE]
> 请注意标记有 `<!-` 的突出显示的区域。 这些区域将要求你根据自己的偏好进行修改。

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## 从全局分配的访问配置文件中排除设备所有者

此功能允许在 HoloLens 上被视为“ [设备所有者](security-adminless-os.md)”的用户被排除在全局分配的访问权限之外。 若要使用此功能，请在适用于多应用程序展台配置的 XML blob 中，确保添加突出显示的行：

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## 其他的全局指定访问示例

这是示例全局分配访问网亭，当任何用户登录时，他们将拥有一个多应用网亭，其中包含设置应用程序、反馈中心和 Microsoft Edge。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

此示例是全局分配的访问网亭，不包括设备所有者，当任何其他 Azure AD 用户登录时，他们将拥有带有设置应用程序、反馈中心和 Microsoft Edge 的多应用程序网亭。 此网亭还包括访客帐户的辅助信息网亭配置，任何人都可以在锁屏上登录。 用户登录到访问者帐户时，将拥有一个仅有反馈中心应用的多应用应用程序。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
