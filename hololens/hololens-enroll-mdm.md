---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理HoloLens MDM (注册) ，以便更轻松地管理多个设备。
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
ms.openlocfilehash: 3c17ad2397d87660cb2013604029864f9c36abdbf520710c4fe5952e3440e3a5
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664229"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中注册 HoloLens

可以使用 Microsoft HoloLens Microsoft Intune 等解决方案同时管理多个 Microsoft Intune[设备。](/intune/windows-holographic-for-business) 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## <a name="requirements"></a>要求

 组织需要设置 Mobile 设备管理 (MDM) 才能管理HoloLens设备。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。
 
## <a name="different-ways-to-enroll"></a>注册的不同方法

根据在 OOBE 或登录后选择的标识类型，有不同的注册方法。 [](hololens-identity.md)

- 如果标识Azure AD，则 OOBE 或 设置 **应用** 访问  ->  **工作或学校连接**  ->  按钮。
    - 例如 [Azure AD，只有在](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 已使用注册 URL 配置Azure AD MDM 注册时，才进行自动 MDM 注册。
     
- 如果标识Azure AD且设备已预先注册到分配有特定配置文件的 Intune MDM 服务器，则 Azure AD-Join 和自动 [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 注册将在 OOBE 期间进行。
    - 也称为 [Autopilot 流](hololens2-autopilot.md) 在 [19041.1103+ 内部版本中可用](hololens-release-notes.md#windows-holographic-version-2004)。
    

- 如果"标识"为 MSA，则  ->  **设置"应用访问工作或学校连接**  ->  按钮。
    - 也称为将工作帐户 (AWA) 流。
- 如果"标识"是本地用户，**则设置"** 应用访问  ->  **工作或** 学校注册  ->  **"链接**。
    - 也称为纯 MDM 注册流。

向 MDM 服务器注册设备后，设置应用将反映设备已注册到设备管理中。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自动注册

如果组织具有[Azure 高级版](https://azure.microsoft.com/overview/)订阅 ，则 使用 Azure Active Directory (Azure AD) 和 MDM 解决方案，该解决方案接受 Azure AD 令牌进行身份验证 (（目前仅在 Microsoft Intune 和 AirWatch) 中受支持）时，IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，无需额外的手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

如果设备已Azure AD，则可能会影响将设备所有者 [视为的所有者](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>从 Intune HoloLens取消注册

根据注册方法，取消注册设备可能不可用。

如果设备已注册到 Azure AD 或 Autopilot，则不能从 Intune 取消注册。 如果要从 HoloLens取消Azure AD或重新加入其他租户Azure AD，则必须[重置/重新运行](hololens-recovery.md#reset-the-device)设备。

如果设备从添加了工作帐户的 MSA 帐户注册，或者从仅在设备管理中注册的本地帐户注册，则你可以取消注册该设备。 打开""开始"菜单"，然后选择"设置"应用访问  ->  **工作或学校**  ->  *YourAccount*  ->  **断开连接"** 按钮。