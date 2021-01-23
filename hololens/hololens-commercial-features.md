---
title: 商业功能
description: 了解使企业能够更轻松地管理 HoloLens 设备的 Microsoft HoloLens Commercial Suite 功能。
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, 商业, 功能, MDM, 移动设备管理, 展台模式
ms.openlocfilehash: 5aef764b1d7937832e162ab219131d8c3d768e68
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283443"
---
# 商业功能

HoloLens 具有使企业能够更轻松地管理 HoloLens 设备的功能。

每个 HoloLens 2 设备都具有商业功能。

HoloLens（第一代）附带两个许可选项：开发人员许可证和商业许可证。 要解锁 HoloLens 的商业功能，须从开发人员许可证升级到商业许可证。 要购买 Microsoft HoloLens Commercial Suite，请联系当地的 Microsoft 客户经理。

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## 主要商业功能

- **展台模式。** 你可以使用展台模式，在演示或展示体验中使用 HoloLens，从而限制可以运行的应用。

  ![使用展台模式时，HoloLens 会直接启动你选择的应用。](images/201608-kioskmode-400px.png)

- **适用于 HoloLens 的移动设备管理 (MDM)。** 你的 IT 部门可以使用 Microsoft Intune 等解决方案来同时管理多个 HoloLens 设备。 你可以管理设置、选择要安装的应用并根据组织需求设置安全配置。

  ![HoloLens 上的移动设备管理功能可在多个设备上提供企业级设备管理。](images/201608-enterprisemanagement-400px.png)

- **适用于企业的 Windows 更新。** 适用于企业的 Windows 更新为设备提供受控的操作系统更新，并支持长期服务渠道。
- **数据安全性。** 在 HoloLens 上启用 BitLocker 数据加密，从而提供与任何其他 Windows 设备相同的安全保护级别。
- **工作访问。** 组织中的任何员工都可以通过 HoloLens 上的虚拟专用网络 (VPN) 远程连接公司网络。 HoloLens 还可以访问需要凭据的 WLAN 网络。
- **适用于企业的 Microsoft Store。** 你的 IT 部门还可以建立企业专用商店，只供应针对你的特定 HoloLens 用途的公司应用。 安全地将企业软件分发给选定的企业用户组。

## 版本之间的功能比较

|功能 |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|设备加密 (BitLocker) | |✔️ |✔️ |
|虚拟专用网络 (VPN) | |✔️ |✔️ |
|[展台模式](hololens-kiosk.md) | |✔️ |✔️ |
|**管理和部署** | | | |
|移动设备管理 (MDM) | |✔️ |✔️ |
|阻止取消注册的功能 | |✔️ |✔️ |
|基于证书的企业 WLAN 访问 | |✔️ |✔️ |
|Microsoft Store（消费者） |消费者 |使用 MDM 进行筛选 |使用 MDM 进行筛选 |
|[业务应用商店门户](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**安全和身份** | | | |
|使用 Azure Active Directory (Azure AD) 账户登录 |✔️ |✔️ |✔️ |
|使用 Microsoft 帐户 (MSA) 登录 |✔️ |✔️ |✔️ |
|带 PIN 解锁密钥的下一代凭据 |✔️ |✔️ |✔️ |
|[安全启动](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**服务和支持** | | | |
|当更新可用时自动更新系统 |✔️ |✔️ |✔️ |
|[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|长期服务渠道 (LTSC) | |✔️ |✔️ |

## 启用商业功能

组织的 IT 管理员可以设置商业功能，如适用于企业的 Microsoft Store、展台模式和企业 WLAN 访问。 [Microsoft HoloLens](index.yml) 文档提供了从适用于企业的 Microsoft Store 注册设备和安装应用的分步说明。

## 另请参阅

- [Microsoft HoloLens](index.yml)
- [展台模式](hololens-kiosk.md)
- [HoloLens 设备支持的云解决方案提供商](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [适用于企业的 Microsoft Store 和业务线应用](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [使用业务线应用](/microsoft-store/working-with-line-of-business-apps)
