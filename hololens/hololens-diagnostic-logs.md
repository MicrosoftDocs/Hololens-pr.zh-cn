---
title: 从 HoloLens 设备收集和使用诊断信息
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827973"
---
# 从 HoloLens 设备收集和使用诊断信息

HoloLens 用户和管理员可以从以下四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：

- 反馈中心应用
- DiagnosticLog 云解决方案提供商
- “设置”应用

> [!IMPORTANT]  
> 设备诊断日志包含个人身份信息（PII），如用户在典型操作期间启动的进程或应用程序。 当多个用户共享 HoloLens 设备时（例如，用户使用不同的 Microsoft Azure Active Directory （AAD）帐户登录到同一设备），诊断日志可能包含适用于多个用户的 PII 信息。 有关详细信息，请参阅[Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

下表比较了这三个集合方法。 "方法名称" 链接到表格后面部分中的详细信息。

|方法 |必备条件 |数据位置 |数据访问和使用 |数据保留 |
| --- | --- | --- | --- | --- |
|[反馈中心](#feedback-hub) |网络和 internet 连接<br /><br />反馈中心应用<br /><br />将文件上传到 Microsoft 云的权限 |Microsoft cloud<br /><br />HoloLens 设备（可选） |用户请求协助、同意使用条款以及上载数据<br /><br />Microsoft 员工查看数据（与使用条款一致） |云中的数据在由下一代隐私（NGP）定义的时间段内保留。 然后，将自动删除该数据。<br /><br />具有**设备所有者**或**管理员**权限的用户可以随时删除设备上的数据。 |
|[设置疑难解答](#settings-troubleshooter) |“设置”应用 |HoloLens 设备<br /><br />已连接的计算机（可选） |用户存储数据，并且只有用户访问数据（除非用户特别与另一个用户共享数据）。 |数据将保留，直到用户删除它。 * |
|[DiagnosticLog 云解决方案提供商](#diagnosticlog-csp) |网络连接<br /><br />支持 DiagnosticLog CSP 的 MDM 环境 |管理员配置存储位置 |在托管环境中，用户隐式内容对数据的管理员访问。<br /><br />管理员配置访问角色和权限。 | 管理员配置保留策略。 |


-   最终用户负责与其他人共享日志。 这些文件主要用于联系客户服务和支持人员。  

## 反馈中心

HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。 有关详细信息和完整说明，请参阅[向我们提供反馈](hololens-feedback.md)。  

> [!NOTE]  
> **商业版或企业版用户：** 如果你使用 "反馈中心" 应用报告与 MDM、资源调配或任何其他设备管理方面相关的问题，请将应用类别更改为 "**企业管理**  >  **设备" 类别**。

### 必备条件

- 设备已连接到网络。
- "反馈中心" 应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。

### 数据位置、访问和保留

通过同意 "反馈中心" 的使用条款，用户明确内容数据的存储和使用情况（由该协议定义）。

反馈中心为用户提供两个位置来存储诊断信息：

- **Microsoft 云**。 用户使用 "反馈中心" 应用上载的数据将存储在与下一代隐私（NGP）要求一致的天数内。 Microsoft 员工可以使用 NGP 兼容的查看器在此期间访问信息。
   > [!NOTE]  
   > 这些要求适用于所有 "反馈中心" 类别中的数据。

- **HoloLens 设备**。 在 "反馈中心" 中存档报表时，用户可以选择 "**保存诊断的本地副本" 和 "在提供反馈时创建的附件**"。 如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。 该信息仍可供用户（或使用该帐户的任何人登录到 HoloLens）访问。 若要删除此信息，用户必须拥有设备**所有者**或设备的**管理员**权限。 具有相应权限的用户可以登录到反馈中心，选择 "**设置**  >  "**查看诊断日志**，然后删除信息。

## 设置疑难解答

HoloLens 用户可以使用设备上的 "设置" 应用对问题进行故障排除和收集诊断信息。 为此，请执行下列步骤：

1. 打开 "设置" 应用，然后选择 "**更新 & 安全**  >  **疑难解答**" 页面。
1. 选择相应的区域，然后选择 "**开始**"。
1. 重现问题。
1. 重现问题后，返回到 "设置"，然后选择 "**停止**"。

### 必备条件

- "设置" 应用已安装在设备上，可供用户使用。

### 数据位置、访问和保留

由于用户启动数据收集，因此用户隐式内容诊断信息的存储。 只有用户或与用户共享数据的任何人都可以访问数据。

诊断信息存储在设备上。 如果设备连接到用户的计算机，则该信息也驻留在计算机上的以下文件中：

> 此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*>

> [!NOTE]  
> 在此文件路径和名称中， \<*HoloLens device name*> 表示 HoloLens 设备的名称，并 \<*ddmmyyhhmmss*> 表示文件的创建日期和时间。

诊断信息将保留在这些位置中，直到用户删除它。

## DiagnosticLog 云解决方案提供商

在移动设备管理（MDM）环境中，IT 管理员可以使用[DiagnosticLog 配置服务提供程序（CSP）](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)配置已注册的 HoloLens 设备上的诊断设置。 IT 管理员可以配置这些设置以从注册的设备收集日志。

### 必备条件

- 设备已连接到网络。
- 设备注册到支持 DiagnosticLog CSP 的 MDM 环境中。

### 数据位置、访问和保留

由于设备是托管环境的一部分，因此用户隐式内容对诊断信息的管理访问。

IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括管理以下各项的策略：

- 存储诊断信息的云基础结构。
- 诊断信息的保留期。
- 控制诊断信息访问权限的权限。


