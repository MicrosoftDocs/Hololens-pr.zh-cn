---
title: 收集和使用来自 HoloLens 设备的诊断信息
description: 收集和使用来自 HoloLens 设备的诊断信息
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
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
ms.openlocfilehash: e1302a3d482648b1ebbf7fee71ceec3ca4261d23
ms.sourcegitcommit: 87d503434339fc6c9b41aa9473e35ddfde845cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120143"
---
# 收集和使用来自 HoloLens 设备的诊断信息

HoloLens 用户和管理员可以从以下四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：

- 反馈中心应用
- DiagnosticLog 云解决方案提供商
- “设置”应用

> [!IMPORTANT]  
> 设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作期间启动哪些进程或应用程序。 当多个用户共享 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (AAD) 帐户登录到同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。 有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

下表比较了这三个集合方法。 "方法名称" 链接到表格后面部分中的详细信息。

|方法 |必备条件 |数据位置 |数据访问和使用 |数据保留 |
| --- | --- | --- | --- | --- |
|[反馈中心](#feedback-hub) |网络和 internet 连接<br /><br />反馈中心应用<br /><br />将文件上传到 Microsoft 云的权限 |Microsoft cloud<br /><br />HoloLens 设备 (可选)  |用户请求协助、同意使用条款以及上载数据<br /><br />Microsoft 员工查看数据（与使用条款一致） |云中的数据在由下一代隐私 (NGP) 定义的期间内保留。 然后，将自动删除该数据。<br /><br />具有 **设备所有者** 或 **管理员** 权限的用户可以随时删除设备上的数据。 |
|[设置疑难解答](#settings-troubleshooter) |“设置”应用 |HoloLens 设备<br /><br />已连接的计算机 (可选)  |用户存储数据，只有用户访问数据 (除非用户特别与另一个用户共享数据) 。 |数据将保留，直到用户删除它。 * |
|[DiagnosticLog 云解决方案提供商](#diagnosticlog-csp) |网络连接<br /><br />支持 DiagnosticLog CSP 的 MDM 环境 |管理员配置存储位置 |在托管环境中，用户隐式内容对数据的管理员访问。<br /><br />管理员配置访问角色和权限。 | 管理员配置保留策略。 |
|[离线诊断](#offline-diagnostics) |设备配置：<ul><li>已接通电源并已连接到计算机</li><li>电源和音量按钮正常工作</li></ul> |HoloLens 设备<br /><br />已连接计算机 |用户存储数据，只有用户访问数据 (除非用户特别与另一个用户共享数据) 。 |数据将保留，直到用户删除它。 | 


-   最终用户负责与其他人共享日志。 这些文件主要用于联系客户服务和支持人员。  

## 反馈中心

HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。 有关详细信息和完整说明，请参阅 [向我们提供反馈](hololens-feedback.md)。  

> [!NOTE]  
> **商业版或企业版用户：** 如果你使用 "反馈中心" 应用报告与 MDM、资源调配或任何其他设备管理方面相关的问题，请将应用类别更改为 "**企业管理**  >  **设备" 类别**。

### 必备条件

- 设备已连接到网络。
- "反馈中心" 应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。

### 数据位置、访问和保留

通过同意 "反馈中心" 的使用条款，用户明确内容该协议) 所定义的数据 (的存储和使用。

反馈中心为用户提供两个位置来存储诊断信息：

- **Microsoft 云**。 用户使用 "反馈中心" 应用上载的数据将存储在与下一代隐私 (NGP) 要求一致的天数内。 Microsoft 员工可以使用 NGP 兼容的查看器在此期间访问信息。
   > [!NOTE]  
   > 这些要求适用于所有 "反馈中心" 类别中的数据。

- **HoloLens 设备**。 在 "反馈中心" 中存档报表时，用户可以选择 " **保存诊断的本地副本" 和 "在提供反馈时创建的附件**"。 如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。 此信息仍可供用户访问 (或使用该帐户登录 HoloLens) 的任何人。 若要删除此信息，用户必须拥有设备 **所有者** 或设备的 **管理员** 权限。 具有相应权限的用户可以登录到反馈中心，选择 "**设置**  >  "**查看诊断日志**，然后删除信息。

## 设置疑难解答

HoloLens 用户可以使用设备上的 "设置" 应用对问题进行故障排除和收集诊断信息。 为此，请执行下列步骤：

1. 打开 "设置" 应用，然后选择 "**更新 & 安全**  >  **疑难解答**" 页面。
1. 选择相应的区域，然后选择 " **开始**"。
1. 重现问题。
1. 重现问题后，返回到 "设置"，然后选择 " **停止**"。

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

在 (MDM) 环境的移动设备管理中，IT 管理员可以使用 [DiagnosticLog 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 来配置已注册的 HoloLens 设备上的诊断设置。 IT 管理员可以配置这些设置以从注册的设备收集日志。

### 必备条件

- 设备已连接到网络。
- 设备注册到支持 DiagnosticLog CSP 的 MDM 环境中。

### 数据位置、访问和保留

由于设备是托管环境的一部分，因此用户隐式内容对诊断信息的管理访问。

IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括管理以下各项的策略：

- 存储诊断信息的云基础结构。
- 诊断信息的保留期。
- 控制诊断信息访问权限的权限。

## 离线诊断
如果设备不能通过 "反馈中心" 或 "设置疑难解答" 收集诊断，则可以手动收集诊断。 需要此功能的一种情况是设备无法连接到 Wi-fi。 诊断程序从设备收集故障转储和日志，帮助 Microsoft 支持工程师隔离问题。

在通过 USB 电缆将设备连接到电脑后，在文件资源管理器中显示该设备时，此操作将起作用。 

> [!NOTE]
> 仅当用户通过 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为 "完全" 时，才会启用脱机诊断。在 Hololens) 上，"基本" 默认值为 " (基本"。 

如果设备处于锁定状态，则不会显示日志。 若要禁用脱机诊断，请转到 "**设置" 应用 > 隐私**"页面，然后选择" 在**诊断数据**中**基本**"。 在 "离线诊断" 依赖 "遥测" 设置的版本中，它只会影响是否收集任何日志。 它不会影响收集的文件。

观看此视频以了解详细信息。 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

请按照以下步骤收集诊断：
1.  将设备与 USB 电缆连接到电脑。
2.  在电脑上的文件资源管理器中，导航到 **"这台电脑 \<hololens-device> \Internal 存储"**。
3.  如果未显示 " **内部存储** " 文件夹，则表示设备正在等待用户登录。 您可以通过按住电源按钮10秒钟来登录或重启设备。
4.  按下并立即释放 **+ "音量按下** " 按钮。
5.  等待一分钟，让设备准备 zip 存档。  (在设备生成 zip 存档时，名为 HololensDiagnostics 的临时文件可能会变得可见。 不要访问或保存该文件。 过程完成后，zip 存档将替换该过程。 ) 
6.  刷新文件资源管理器，并导航到 **"\Documents"** 文件夹。
7.  复制诊断 ZIP 文件，并将其与 Microsoft 支持团队共享。

> [!NOTE]
> 某些诊断 ZIP 文件可能包含个人身份信息。



