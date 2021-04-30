---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理 (MDM) 中注册 HoloLens，以便更轻松地管理多个设备。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308469"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中注册 HoloLens

你可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## <a name="requirements"></a>要求

 你的组织需要 (MDM) 设置移动设备管理，以便管理 HoloLens 设备。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。
 
## <a name="different-ways-to-enroll"></a>注册的不同方法

根据在 OOBE 或 post 登录期间选择的 [标识](hololens-identity.md) 类型，有不同的注册方法。

- 如果 Azure AD，则在 OOBE 期间或 **设置应用**  ->  **访问工作或学校**  ->  **连接** 按钮。
    - 对于 Azure AD，仅当 Azure AD 配置了注册 Url 时才会进行 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。
     
- 如果标识是 Azure AD 的，并且设备已预先向分配了特定配置文件的 Intune MDM 服务器注册，则 Azure AD-Join 和 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 将在 OOBE 期间进行。
    - 也称为[19041.1103 + build](hololens-release-notes.md#windows-holographic-version-2004)中的[Autopilot 流](hololens2-autopilot.md)。
    

- 如果标识为 MSA，则使用 **设置应用**  ->  **访问工作或学校**  ->  **连接** 按钮。
    - 也称为添加工作帐户 (AWS) flow。
- 如果 "标识" 为本地用户，则使用 "设置" "**应用**  ->  **访问工作" 或**  ->  **"仅在设备管理中注册"** 链接。
    - 也称为纯 MDM 注册流。

设备注册到 MDM 服务器后，"设置" 应用将立即反映设备是否已在 "设备管理" 中注册。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自动注册

如果你的组织具有 [Azure Premium 订阅](https://azure.microsoft.com/overview/)，则使用 Azure Active Directory (Azure AD) ，并使用接受 Azure AD 令牌进行身份验证的 MDM 解决方案 (目前仅支持 Microsoft Intune 和 AirWatch) 中的 Azure AD，你的 IT 管理员可以将 Azure AD 配置为在用户使用其帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，无需进行额外的手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

Azure AD 联接设备时，可能会影响被认为是 [设备所有者](security-adminless-os.md#device-owner)的用户。

## <a name="unenroll-hololens-from-intune"></a>从 Intune 取消注册 HoloLens

根据注册方法，取消注册设备可能不可用。

如果设备已使用 Azure AD 帐户或 Autopilot 注册，则无法从 Intune 取消注册。 如果要从 Azure AD 中脱离 HoloLens，或将其重新加入到 Azure AD 租户以外的其他设备，则必须 [重置/刷新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 设备。

如果设备是从添加了工作帐户的 MSA 帐户或从仅在设备管理中注册的本地帐户注册的，则可以取消注册设备。 打开 "开始" 菜单，然后选择 "设置" "**应用**  ->  **访问工作或学校**  ->  *YourAccount*  ->  **断开连接**" 按钮。