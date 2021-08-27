---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理中注册 HoloLens (MDM) ，以便更轻松地管理多个设备。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979349"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中注册 HoloLens

你可以使用[Microsoft Intune](/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## <a name="requirements"></a>要求

 你的组织需要 (MDM) 设置移动设备管理，以便管理 HoloLens 设备。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。

## <a name="different-ways-to-enroll"></a>注册的不同方法

根据在 OOBE 或 post 登录期间选择的 [标识](hololens-identity.md) 类型，有不同的注册方法。

- 如果 Azure AD，则在 OOBE 期间或 **设置应用**  ->  **访问工作或学校**  ->  **连接**"按钮。
    - 对于 Azure AD，仅当 Azure AD 配置了注册 Url 时才会进行 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。

- 如果标识是 Azure AD 的，并且设备已预先向分配了特定配置文件的 Intune MDM 服务器注册，则 Azure AD-Join 和 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 将在 OOBE 期间进行。
    - 也称为[19041.1103 + build](hololens-release-notes.md#windows-holographic-version-2004)中的[Autopilot 流](hololens2-autopilot.md)。


- 如果身份为 MSA，则使用 **设置应用**  ->  **访问工作或学校**  ->  **连接**"按钮。
    - 也称为添加工作帐户 (AWS) flow。
- 如果身份为本地用户，则使用 **设置应用**  ->  **访问工作或**  ->  **仅在设备管理链接中注册**。
    - 也称为纯 MDM 注册流。

在将设备注册到 MDM 服务器后，设置应用将立即反映设备是否已注册到设备管理中。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自动注册

如果你的组织具有[Azure 高级版订阅](https://azure.microsoft.com/overview/)，则使用 Azure Active Directory 的 (Azure AD) 和一个 MDM 解决方案，该解决方案接受 Azure AD 令牌以进行身份验证 (当前只支持 Microsoft Intune 和 AirWatch) 中，你的 IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，无需进行额外的手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

Azure AD 联接设备时，可能会影响被认为是 [设备所有者](security-adminless-os.md#device-owner)的用户。

## <a name="unenroll-hololens-from-intune"></a>从 Intune 取消注册 HoloLens

根据注册方法，取消注册设备可能不可用。

如果设备已使用 Azure AD 帐户或 Autopilot 注册，则无法从 Intune 取消注册。 如果希望将 HoloLens 从 Azure AD 中脱离或重新加入到 Azure AD 租户以外的其他用户，则必须[重置/刷新](hololens-recovery.md#reset-the-device)设备。

如果设备是从添加了工作帐户的 MSA 帐户或从仅在设备管理中注册的本地帐户注册的，则可以取消注册设备。 打开 "开始"菜单，然后选择 **设置应用**  ->  **访问工作或学校**  ->  *YourAccount*  ->  **断开连接**"按钮。

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>确保 Windows 设备不阻止 MDM 注册

为了成功注册，需要确保 HoloLens 设备可以注册。 由于 HoloLens 被视为 Windows 设备，因此将需要不会阻止部署的注册限制。 [查看此限制列表](/mem/intune/enrollment/enrollment-restrictions-set) ，并确保能够注册设备。