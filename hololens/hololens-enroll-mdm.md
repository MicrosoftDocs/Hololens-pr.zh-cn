---
title: Enroll HoloLens in MDM
description: Enroll HoloLens in mobile device management (MDM) for easier management of multiple devices.
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
# Enroll HoloLens in MDM

You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need. 请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。

## Requirements

 Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices. Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.
 
## Different ways to enroll

Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment. To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).

- If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.
    - For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.
- If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.
    - Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).
- If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.
    - Also called Add Work Account (AWA) flow.
- If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.
    - Also called pure MDM enrollment flow.

Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.

## Auto-enrollment in MDM

如果你的组织使用 Azure Active Directory (Azure AD) 和接受 AAD 令牌的 MDM 解决方案进行身份验证（目前仅在 Microsoft Intune 和 AirWatch 中支持），则 IT 管理员可以配置 Azure AD，以在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。 [了解如何配置 Azure AD 注册。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

启用自动注册后，不需要其他手动注册。 When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.

When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).

## Unenroll HoloLens from Intune

To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
