---
title: 在 MDM 中注册 HoloLens
description: 在移动设备管理 (MDM) 中注册 HoloLens，以便轻松管理多个设备。
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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102321"
---
# 在 MDM 中注册 HoloLens

你可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。 你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## 要求

 你的组织需要 (MDM) 设置才能管理 HoloLens 设备的移动设备管理。 你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。
 
## 不同的注册方式

根据在 OOBE 或发布登录期间选择的标识类型，有不同的注册方法。 若要了解有关 HoloLens 的每种类型的标识的详细信息，请访问 [此页面](hololens-identity.md)。

- 如果 Identity 为 AAD，则在 OOBE 期间或**设置应用**  ->  **访问工作或学校**  ->  **连接**按钮时。
    - 对于 AAD，仅当已为 AAD 配置注册 Url 时，才会自动 MDM 注册。
- 如果身份为 AAD 且已预先向已分配了特定配置文件的 Intune MDM 服务器注册了设备，则在 OOBE 期间将自动进行 AAD 加入和注册。
    - 也称为[19041.1103 + 内部版本](hololens-release-notes.md#windows-holographic-version-2004)中提供的[Autopilot 流](hololens2-autopilot.md)。
- 如果身份为 MSA，则使用 "**设置应用**  ->  **访问工作或学校**  ->  **连接**" 按钮。
    - 也称为 "添加工作帐户" (AWA) 流程 "。
- 如果身份为本地用户，则使用 "**设置" 应用**  ->  访问 "仅在设备管理链接中使用**工作或学校**  ->  **注册**"。
    - 也称为纯 MDM 注册流程。

在设备注册到你的 MDM 服务器后，"设置" 应用将立即反映设备是否已注册到 "设备管理" 中。

## 在 MDM 中自动注册

如果你的组织使用 Azure Active Directory (Azure AD) 和接受 AAD 令牌的 MDM 解决方案进行身份验证（目前仅在 Microsoft Intune 和 AirWatch 中支持），则 IT 管理员可以配置 Azure AD，以在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，不需要其他手动注册。 当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。

当设备已进行 AAD 联接时，它可能会影响被视为 [设备所有者](security-adminless-os.md#device-owner)的人员。

## 从 Intune 取消 HoloLens

若要了解有关通过设备的详细信息，请访问 [此页面](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。 
