---
title: 全局分配的访问权限
description: 开始使用我们的指南，在 Intune 和 Windows 配置设计器中使用全局分配的访问权限展台的 OMA-URI。
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
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640417"
---
# <a name="global-assigned-access--kiosk"></a>全局分配的访问权限 - 展台

此功能可将 HoloLens 2 设备配置为多应用展台模式，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。

> [!NOTE]
> 此功能目前仅适用于 Windows 预览体验成员版本。 如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [Windows 预览体验成员](hololens-insider.md)版本的更多信息。

## <a name="how-to-use-global-assigned-access-in-intune"></a>如何在 Intune 中使用全局分配的访问权限？

> [!NOTE]
> 请注意标记有“<!-”的区域。 这些区域将要求你根据自己的偏好进行修改。

1. 按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：

    URI 值：./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune 中全局分配的访问权限 OMA URI](images/global-assigned-access-omauri.png)

2. 对于“值”，请更新并粘贴以下内容：

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>如何在 Windows 配置设计器中使用全局分配的访问权限？

1. 更新并保存上面提及的 XML 文件。 

2. 按照[使用预配包设置单应用或多应用展台](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作 （具体为“预配包，第 2 步 - 将展台配置 XML 文件添加到预配包”部分），并参考上一步中保存的 XML 文件。

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>是否可以创建这样一个配置，全局应用于所有人，单独配置应用于 1 个 Azure AD 帐户或 Azure AD 组？ 

可以，请参阅下面的示例 XML blob。 如果未找到登录用户的特定配置文件，则全局分配的访问权限配置文件将应用于 HoloLens，因此它是登录用户的默认展台模式配置。
下面是要使用的 XML blob 示例：

> [!NOTE]
> 请注意标有 `<!-` 的突出显示区域。 这些区域将要求你根据自己的偏好进行修改。

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>从全局分配的访问权限配置文件中排除设备所有者

此功能允许在 HoloLens 上被视为“[设备所有者](security-adminless-os.md)”的用户被排除在全局分配的访问权限之外。 若要使用此功能，请在多应用展台配置的 XML blob 中，确保添加突出显示的行：

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>其他全局分配的访问权限示例

这是示例全局分配的访问权限展台，当任何用户登录时，他们将拥有一个包含设置应用、反馈中心和 Microsoft Edge 的多应用展台。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

此示例是不包括设备所有者的全局分配的访问权限展台，当任何其他 Azure AD 用户登录时，他们将拥有一个包含设置应用、反馈中心和 Microsoft Edge 的多应用展台。 此展台还包括访客帐户的辅助信息展台配置，任何人都可以在锁屏上登录。 用户登录到访问者帐户时，将拥有一个仅有反馈中心应用的多应用展台。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
