---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理HoloLens MDM (注册) 以便更轻松地管理多个设备。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904338"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中注册 HoloLens

可以使用 Microsoft HoloLens 等解决方案同时管理多个[Microsoft Intune](/intune/windows-holographic-for-business)设备。 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## <a name="requirements"></a>要求

 组织需要设置 Mobile 设备管理 (MDM) 才能管理HoloLens设备。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。

## <a name="different-ways-to-enroll"></a>注册的不同方法

根据在 OOBE 或登录后选择的标识类型，有不同的注册方法。 [](hololens-identity.md)

- 如果标识Azure AD，则 OOBE 或 设置应用访问  ->  **工作或学校连接**  ->  按钮。
    - 例如 [Azure AD，只有在](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 已使用注册 URL 配置Azure AD MDM 注册时，才进行自动 MDM 注册。

- 如果标识Azure AD且设备已预先注册到分配了特定配置文件的 Intune MDM 服务器，则 Azure AD-Join 和自动 [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 注册将在 OOBE 期间进行。
    - 也称为 [Autopilot 流](hololens2-autopilot.md) 在 [19041.1103+ 内部版本中可用](hololens-release-notes.md#windows-holographic-version-2004)。


- 如果"标识"为 MSA，则  ->  **设置"应用访问工作或学校连接**  ->  按钮。
    - 也称为将工作帐户 (AWA) 流。
- 如果"标识"是本地用户，**则设置"** 应用访问  ->  **工作或** 学校注册  ->  **"链接**。
    - 也称为纯 MDM 注册流。

向 MDM 服务器注册设备后，设置应用将反映设备已注册到设备管理中。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自动注册

如果组织具有[Azure 高级版](https://azure.microsoft.com/overview/)订阅 ，则 使用 Azure Active Directory (Azure AD) 和 MDM 解决方案，该解决方案接受 Azure AD 令牌进行身份验证 (（目前仅在 Microsoft Intune 和 AirWatch) 中受支持）时，IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，无需额外的手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

当设备已Azure AD加入时，可能会影响被视为设备 [所有者 的人](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>从 Intune HoloLens取消注册

根据注册方法，取消注册设备可能不可用。

如果设备已注册到 Azure AD 或 Autopilot，则不能从 Intune 取消注册。 如果要从 HoloLens取消Azure AD或重新加入其他租户Azure AD，则必须[重置/重新运行](hololens-recovery.md#reset-the-device)设备。

如果设备从添加了工作帐户的 MSA 帐户注册，或者从仅在设备管理中注册的本地帐户注册，则你可以取消注册该设备。 打开"开始"菜单，然后选择 **"设置**  ->  **工作或学校**  ->  *YourAccount*  ->  **断开连接"** 按钮。

## <a name="enrollment-troubleshooting"></a>注册故障排除

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>确保向用户分配有效的许可证

请参阅[以下Windows中](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors)解决设备注册Microsoft Intune问题，即检查设备类型限制和向用户分配[](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions)[有效许可证。](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>确保 MDM 注册未针对设备Windows阻止

若要成功注册，需要确保设备HoloLens注册。 由于 HoloLens 被认为是 Windows 设备，因此需要杜绝可能阻止部署的任何注册限制。 [查看此限制列表](/mem/intune/enrollment/enrollment-restrictions-set)，确保能够注册设备。