---
title: 在商业环境中设置 HoloLens
description: 了解有关在企业环境中部署和管理 HoloLens 的详细信息。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865561"
---
# 在商业环境中部署 HoloLens

你可以在商业设置中按比例部署和配置 HoloLens。 本文提供了有关在商业环境中部署 HoloLens 设备的说明。 本指南假设您对 HoloLens 基本熟悉。 请按照[入门指南](hololens1-setup.md)首次设置 HoloLens。

本文档还假设 HoloLens 已被安全团队评估为安全团队在企业网络上使用。  
> [!Tip]
> 了解有关[HoloLens 安全性](security-overview.md)的详细信息。
> 对于 HoloLens (第一代) 安全请查看[此常见问题解答](hololens1-faq-security.md)。

## 部署步骤概述

1. [确定所需功能](hololens-requirements.md#step-1-determine-what-you-need)
1. [确定所需的许可证](hololens-licenses-requirements.md)
1. [为 HoloLens 配置你的网络](hololens-commercial-infrastructure.md)。
    1. 本部分包括需要在防火墙上允许的带宽要求、URL 和端口;Azure AD 指南;移动设备管理 (MDM) 指南;应用部署/管理指南;和证书指南。
1.  (可选) [使用预配包配置 HoloLens](hololens-provisioning.md)
1. [注册设备](hololens-enroll-mdm.md)
1. [为 HoloLens 设置基于圈的更新](hololens-updates.md)
1. [启用适用于 HoloLens 的 Bitlocker 设备加密](security-encryption-data-protection.md)

## 步骤 1： 确定所需内容

在你的环境中部署 HoloLens 之前，首先确定需要哪些功能、应用和标识类型非常重要。 确保安全团队在公司网络上使用 HoloLens 的批准也非常重要。 有关其他安全信息，请参阅[HoloLens2 security](security-overview.md) 。

### 标识的类型

确定将用于登录设备的标识类型。

1. **本地帐户：** 此帐户在 windows 电脑上的本地管理员帐户 () 。 这将仅允许1个用户登录到设备。
2. **MSA：** 这是个人帐户 (如 outlook、hotmail、gmail、yahoo 等，) 这将仅允许1个用户登录到设备。
3. Azure **Active Directory (AZURE AD) 帐户：** 这是在 Azure AD 中创建的帐户。 这会授予您的公司管理 HoloLens 设备的能力。 这将允许多个用户登录到 HoloLens 第一代商业版套件/HoloLens 2 设备。

有关标识类型的详细信息，请访问我们的[HoloLens 标识](hololens-identity.md)文章。

### 功能类型

您的功能要求将确定所需的 HoloLens。 我们在客户环境中经常部署的一个常用功能是 Kiosk 模式。 可在[此处](hololens-commercial-features.md)找到 hololens 密钥功能的列表以及支持它们的 hololens 版本。

**什么是 Kiosk 模式？**

展台模式是一种限制用户有权访问的应用的方式。 这意味着仅允许用户访问某些应用程序。

**我需要什么 Kiosk 模式？**

展台模式有两种类型：单个应用和多应用。 单应用展台模式允许用户仅访问一个应用，而多应用展台模式允许用户访问多个指定的应用。 要确定哪种展台模式适合您的公司，需要回答以下两个问题：

1. **不同用户是否需要不同的体验/限制？** 请考虑以下示例：用户 A 是一种仅需要访问远程协助的现场服务工程师。 用户 B 是仅需要访问指南的 trainee。
    1. 如果是，您将需要以下各项：
        1. Azure AD 帐户作为登录设备的方法。
        1. **多应用**展台模式。
    1. 如果不是，请继续提问二
1. **是否需要多个应用体验？**
    1. 如果是，则需要**多路应用**展台模式
    1. 如果问题1和2的答案都不是，则可以使用**单应用**展台模式

**如何配置展台模式：**

有两种主要方法 ([预配程序包](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)和[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) 为 HoloLens 部署展台模式。 这些选项稍后将在文档中进行讨论;但是，你可以使用上面的链接跳转到此文档中的各个部分。

### 应用和应用特定方案

本文档中的大部分步骤也将应用于以下应用：

| 应用 | 特定于应用的方案 |
| --- | --- |
| 远程协助 | [跨租户通信](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| 指南  | *即将推出* |
|自定义应用 | *即将推出* |

### 确定注册方法

1. 使用预配包中的安全令牌进行批量注册。  
  专业人员：这是最自动化的方法 \
  缺点：获取初始服务器端设置  
1. 自动注册用户登录。  
  专业人士：最简单的方法  
  缺点：在应用预配包后，用户将需要完成设置
1. _不推荐_-手动注册安装后。  
  专业人员：设置完成后可能注册  
  缺点：在手动注册之前，大多数手动方法和设备不能集中管理。

  可[在此处](hololens-enroll-mdm.md)找到详细信息

### 确定是否需要创建预配包

可使用两种方法配置 HoloLens 设备 (预配软件包和 MDMs) 。 建议使用 MDM 配置 HoloLens 设备。 但是，在某些情况下，使用预配包是更好的选择：

1. 你希望配置 HoloLens 以跳过 Box 体验 (OOBE) 
1. 在复杂网络中部署证书时遇到问题。 即使在复杂的环境) 中，也可以使用 MDM (部署证书。 但是，某些方案需要通过预配包来部署证书。

以下是可在预配包中应用的部分 HoloLens 配置：

- 将证书应用到设备
- 设置 Wi-Fi 连接
- 预配置现成的设置，例如语言和区域设置
- (HoloLens 2) 在移动设备管理中批量注册
- (HoloLens v1) 应用密钥以启用 Windows Holographic for Business

如果您决定使用预配程序包，请按照[本指南](hololens-provisioning.md)操作。

## 获取支持

通过 Microsoft 支持网站获取支持。

[文件 a 支持请求](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
