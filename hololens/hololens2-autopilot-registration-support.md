---
title: HoloLens 2 Windows Autopilot 注册支持
description: 了解如何在 HoloLens 2 设备上获取对 Autopilot 的注册支持。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034182"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Autopilot 注册支持

客户和 Microsoft 云解决方案提供商 (CSP) 现在可以通过直接向 Microsoft 支持部门提交请求来注册 HoloLens 2 设备。 本页概述了以下受支持的 Autopilot 注册情形的要求：

- HoloLens 2 设备 Autopilot 注册。 提交向 Windows Autopilot 注册 HoloLens 2 设备的请求。
- HoloLens 2 设备硬件哈希请求。 向 Microsoft 支持部门提交请求，以便为你提供客户或 CSP 可用于通过 Microsoft Intune 或 Microsoft 合作伙伴中心自行注册设备的硬件哈希。
- HoloLens 2 设备 Autopilot 取消注册。 提交从 Windows Autopilot 删除设备的请求，通常在设备生命周期结束情形中使用。

下表详细说明了向 Microsoft 支持部门提交注册请求之前需要收集的信息。

| 所需信息 | 说明 | Autopilot 注册  | 硬件哈希请求 | Autopilot 取消注册 |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory 租户 ID    |    Azure Active Directory 租户 ID 是一个全局唯一标识符 (GUID)，与组织名称或域不同。    若要查找租户 ID，请登录到 [Azure 门户](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory 域名    |   顶级域名；例如，contoso.com。    |     ✔️                         |                              |                         ✔️                        |
|  所有权证明    |   通过上传原始销售单或 PDF 格式的发票来验证所有权证明。 不接受屏幕截图。 销售单或发票必须包括以下内容：设备序列号。 公司名称。     |     ✔️                         |              ✔️                |                         ✔️                        |
|  设备序列号    |   上传 CSV 格式的 Excel 文件，其中每个设备序列号都位于一个新行。     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>提交支持请求

> [!div class="nextstepaction"]
> [提交 HoloLens 2 Autopilot 注册支持](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
