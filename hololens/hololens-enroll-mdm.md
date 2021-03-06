---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理中注册 HoloLens (MDM) 更轻松地管理多个设备。
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
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399380"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中注册 HoloLens

可以使用 Microsoft [Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## <a name="requirements"></a>要求

 组织需要设置移动设备管理 (MDM) 才能管理 HoloLens 设备。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。
 
## <a name="different-ways-to-enroll"></a>注册的不同方法

根据在 OOBE 或登录后选择的标识类型，存在不同的注册方法。 若要了解有关 HoloLens 上每种类型的标识的信息，请访问 [此页面](hololens-identity.md)。

- 如果 Identity 为 Azure AD，则 OOBE 或"设置应用访问工作"****  ->  **或"学校连接"按钮**  ->  **期间**。
    - 对于 Azure AD，只有当 Azure AD 已配置注册 URL 时，才进行自动 MDM 注册。
- 如果 Identity 为 Azure AD，并且设备已在 Intune MDM 服务器中预先注册并分配了特定配置文件，则 Azure AD-Join 和注册将在 OOBE 期间自动发生。
    - 也称为 [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ 版本](hololens-release-notes.md#windows-holographic-version-2004)。
- 如果 Identity 为 MSA，则使用"设置**应用**  ->  **访问工作"或"学校**  ->  **连接"** 按钮。
    - 也称为"添加工作帐户 (AWA) 流。
- 如果 Identity 为本地用户，**则仅在设备**管理链接中使用"设置应用访问工作  ->  ****  ->  **"或"学校注册**"。
    - 也称为纯 MDM 注册流。

设备注册 MDM 服务器后，"设置"应用现在将反映设备已注册到设备管理中。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自动注册

如果你的组织使用 Azure Active Directory (Azure AD) 和接受 Azure AD 令牌进行身份验证的 MDM 解决方案 (目前仅在 Microsoft Intune 和 AirWatch) 中受支持，则 IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，不需要其他手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

当设备已加入 Azure AD 时，可能会影响被视为设备 [所有者的人](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>从 Intune 注销 HoloLens

尽管 HoloLens 2 是 Windows 10 设备，但无法简单地从 Intune 注销。 如果你希望从 Azure AD 中取消加入 HoloLens 或重新加入其他 Azure AD 租户，则必须重置 [/重新调整](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 设备。