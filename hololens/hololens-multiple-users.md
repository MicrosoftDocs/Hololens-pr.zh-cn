---
title: 与多人共享你的 HoloLens
description: 可以将 HoloLens 配置为由多个 Azure Active Directory 帐户共享，也可以由使用单个帐户的多个用户共享。
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600723"
---
# <a name="share-your-hololens-with-multiple-people"></a>与多人共享你的 HoloLens

## <a name="overview"></a>概述

企业经常投入许多共享 HoloLens 设备。 使用 HoloLens 在整个板中是灵活的，具体取决于您的个人需求。 下面是一些多用户体验的示例：

- HoloLens 2 设备的一组设置通过 Windows Autopilot 用于 HoloLens 2，并在每个设备上提供一致的公司应用程序组合。 已设置了几个不同的展台配置文件，面向不同的 Azure AD 组。 每个用户都使用 FIDO2 密钥登录到 HoloLens，并登录到自己的 Azure AD 帐户，并提供定制体验。
- 独立软件供应商 (ISV) rents HoloLens 2 具有 D365 远程协助的设备，并将其业务线 (LOB) 应用程序提供给客户的公司。 这些设备配置为仅包含其 LOB 应用和远程协助的展台，并跨多个最终用户共享。 使用 WDAC 来保持设置应用和 Microsoft Edge 的启动。 租赁附带了一个 USB-C 电池组，使设备在多个班次上保持完全充电。
- 企业中的最终用户尝试对设备上的蓝牙进行调整，使其能够连接到新设备，但启用了页面设置可见性策略，以限制设备页面被查看。 它们仍允许根据需要访问其他页面，如 Wi-Fi，因此它们可以在具有相同 HoloLens 的多个位置使用远程协助。

## <a name="best-practices"></a>最佳做法

规划共享设备时，需要考虑几个事项，以根据业务需求优化设备环境。

- [标识和身份验证](#identity-and-authentication)
- [设备管理](#device-management)
- [高级设备管理-展台和 WDAC](#advanced-device-management---kiosk-and-wdac)
- [物理管理](#physical-management)

### <a name="identity-and-authentication"></a>[标识和身份验证](hololens-identity.md)

如果你计划在一个设备上有多个帐户，则你将拥有使用所有身份验证模式的 Azure AD 帐户。 这些身份验证方法将基于[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)，包括 Iris 和 FIDO2 键。

- 如果有多个设备、多个用户或经常使用新设备，FIDO 2 安全密钥会很好。
- 如果用户拥有10个或更少的用户，Iris 是一种快速的解决方案，用于登录以前登录到相同设备的用户。

### <a name="device-management"></a>[设备管理](hololens-csp-policy-overview.md)

如果在用户之间共享设备，则可能需要使用设备限制。 通过使用设备管理，你可以设置某些策略，以更好地允许用户使用设备、管理更新或限制设备可以执行的操作。 建议你查看 [常见的设备限制](hololens-common-device-restrictions.md)，并查看这些建议是否适合你的组织。 确定要使用的策略后，可以通过[Microsoft 的 Endpoint Manager (MDM) ](hololens-mdm-configure.md)或预配包应用它们。

### <a name="advanced-device-management---kiosk-and-wdac"></a>高级设备管理- [展台](hololens-kiosk.md) 和 [WDAC](windows-defender-application-control-wdac.md)

在某些情况下，可能需要限制最终用户可以访问的应用程序。 使用 [展台模式](hololens-kiosk.md)，可以在 "开始" 菜单中限制用户显示的应用。 展台可以配置为基于用户、Azure 组或特殊用户类型显示不同的 "开始" 菜单;此类访问者或排除设备所有者。 你可以选择多个应用程序，也可以只选择一个应用。 多应用展台不会阻止一个应用程序启动另一个应用程序，因此，如果应用商店或其他应用程序可用，则用户仍然可以启动其他应用程序。

你可能还希望使用[Windows Defender 应用程序控件 (WDAC) ](windows-defender-application-control-wdac.md)来完全停止启动应用或服务，以限制应用。 WDAC 不同于展台，因为它不会更改 HoloLens 的 UI，而是不允许启动被阻止的应用程序。

[页面设置可见性](settings-uri-list.md)是将限制添加到设备的另一种方法。 在此事件中，你需要授予用户访问设置应用中某些页面的权限，但并非所有用户都可以使用页面设置可见性来限制访问权限。 这很有用，例如，如果用户需要更改 Wi-fi，但不希望他们访问 "帐户" 页。

### <a name="physical-management"></a>物理管理

当在多个用户之间共享设备时，有一些物理注意事项。

- 确保设备在班次间充电。
- 如果移动需要设备，并且需要最后多次移动，请考虑在班次开始时使用外部电池，但设备仍会按 [管理温度](hololens2-charging.md#managing-heat)的费率收费。
- 当存储设备时，设备将其插入并连接到网络。 这是确保操作系统和应用程序更新的最佳方法。
- 考虑如何计划在用户之间 [清理设备](hololens2-maintenance.md) 。
- 对于具有单个共享用户的设备，如果为单一用户使用共享 PIN/密码，请不要将 PIN/密码放在设备的一侧。
- 对于具有单个共享用户的多个设备，请使用不同的 Pin/密码。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>与多个用户共享，每个人使用自己的帐户

单个 Azure Active Directory (Azure AD) 帐户是 HoloLens 2 用户首选且最安全的标识用例。 使用自己的 Azure AD 帐户时，多个用户可以在设备上保留自己的用户设置和用户数据。 一次只能有一个用户登录。 当用户登录时，HoloLens 注销上一个用户。

若要确保多个用户可以在 HoloLens 上使用自己的帐户，请按照以下步骤进行配置：

1. [设置设备](hololens2-start.md)时，请选择 **"我的工作" 或 "学校拥有**"，并使用 Azure AD 帐户登录。
1. 完成设置后，请确保 "帐户设置" (设置 > 帐户) 包括 "**其他用户**"。

> [!NOTE]
> 如果未使用 Azure AD 帐户设置设备，则需要 [重置或 reflashed](hololens-recovery.md) 并正确设置。

若要使用 HoloLens，每个用户都遵循以下步骤：

1. 如果另一位用户使用了该设备，请选择下列选项之一：
   - 按下电源按钮进入待机状态，然后再次按下电源按钮，返回到锁定屏幕
   - 从 **"开始"菜单** 中选择用户磁贴，或从 "Power"**菜单** 中选择 "注销" 以注销当前用户。

1. 使用你的 Azure AD 帐户凭据登录到设备。  
    - 如果是第一次使用设备，则会要求您将 HoloLens[校准](hololens-calibration.md)到您自己的眼睛。
    - 如果以前使用过该设备：
        - [Windows 全息版本20H2、版本 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本，显示器无缝调整质量和舒适的观看体验。
        - 以前的生成需要手动校准才能调整到你的眼睛。

> [!TIP]
> 如果用户尚未登录到设备，请尝试使用以下两种方法之一进行更快速的登录：
>
> - **FIDO 2 安全密钥** ：将自动识别你的 FIDO2 安全密钥，并且用户无需键入其用户凭据或使用 MFA。 这是在新设备上登录的最快方法。
> - **Web 身份验证** ：登录到新设备时，你可以选择 **从其他设备登录** ，这会生成9个字符代码，你可以在 [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) 上使用该代码以用户身份登录到设备上，或者使用键盘键入你的用户名和密码以方便使用。

若要查看设备用户列表或从设备中删除用户，请访问 **设置**  >  **帐户**""  >  **其他用户**"。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>使用同一个帐户与多个用户共享

使用单个用户帐户时，多个用户还可以共享 HoloLens 设备。 尽管 HoloLens 用户使用各自的标识登录到设备 (Azure AD 帐户) ，但这并不是某些组织中的选项。

有两种可用的共享设备方法：

- **多个最终用户共享1个设备**-HoloLens 设备分配给指定空间，任何员工都可以使用该设备。 示例是一个完整的房间或外科套件。

- **共享多个设备的多个最终用户**-HoloLens 设备位于共享存储空间中，员工可以使用任何设备。 例如，石油远程测试机组或自动信得过/车库。

当新用户第一次进入设备，同时保持同一帐户登录时，设备会提示用户快速校准并个性化查看体验。 设备将存储校准信息，以自动优化质量并使每个用户的观看体验更加舒适。 用户无需再次校准设备。
