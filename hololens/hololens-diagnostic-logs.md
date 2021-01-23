---
title: 收集和使用来自 HoloLens 设备的诊断信息
description: 了解如何收集、使用和保留 HoloLens 设备的诊断信息。
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
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283223"
---
# 收集和使用来自 HoloLens 设备的诊断信息

HoloLens 用户和管理员可以从四种不同方法中选择从 HoloLens 收集诊断信息：

- 反馈中心应用
- DiagnosticLog 云解决方案提供商
- “设置”应用

> [!IMPORTANT]  
> 设备诊断日志包含个人身份信息 (PII) ，例如有关用户在典型操作期间启动的进程或应用程序。 例如，当多个用户共享 HoloLens 设备 (时，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。 有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

下表比较了三种集合方法。 方法名称链接到表后各节中的更多详细信息。

|方法 |必备条件 |数据位置 |数据访问和使用 |数据保留 |
| --- | --- | --- | --- | --- |
|[反馈中心](#feedback-hub) |网络和 Internet 连接<br /><br />反馈中心应用<br /><br />将文件上传到 Microsoft 云的权限 |Microsoft 云<br /><br />HoloLens 设备 (可选)  |用户请求帮助、同意使用条款并上载数据<br /><br />Microsoft 员工根据使用条款查看数据 |云中的数据将保留由 NGP 组织下一代隐私 (定义的) 。 然后，数据将自动删除。<br /><br />拥有设备所有者或管理员权限的用户随时都可以删除**设备上的数据。** **** |
|[设置疑难解答程序](#settings-troubleshooter) |“设置”应用 |HoloLens 设备<br /><br />连接的计算机 (可选)  |用户存储数据，只有用户访问数据 (除非用户专门与其他用户共享数据) 。 |数据将一直保留，直到用户将其删除。 |
|[DiagnosticLog 云解决方案提供商](#diagnosticlog-csp) |网络连接<br /><br />支持 DiagnosticLog CSP 的 MDM 环境 |管理员配置存储位置 |在托管环境中，用户隐式同意管理员访问数据。<br /><br />管理员配置访问角色和权限。 | 管理员配置保留策略。 |
|[脱机诊断](#offline-diagnostics) |设备配置：<ul><li>已打开并连接到计算机</li><li>电源和音量按钮正常工作</li></ul> |HoloLens 设备<br /><br />已连接计算机 |用户存储数据，只有用户访问数据 (除非用户专门与其他用户共享数据) 。 |数据将一直保留，直到用户将其删除。 | 


-   最终用户负责与他人负责共享日志。 这些文件在联系客户服务和支持人员时主要用于。  

## 反馈中心

HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。 有关详细信息和完整说明，请参阅["提供反馈"。](hololens-feedback.md)  

> [!NOTE]  
> **商业或企业用户：** 如果你使用反馈中心应用报告与 MDM、预配或其他任何设备管理方面相关的问题，请更改应用类别为 **"企业管理**  >  **设备"类别**。

### 必备条件

- 设备已连接到网络。
- 反馈中心应用在用户的台式计算机上可用，用户可以将文件上载到 Microsoft 云。

### 数据位置、访问和保留

通过同意反馈中心的使用条款，用户明确同意按照该协议 (存储和使用数据) 。

反馈中心为用户提供了两个存储诊断信息的位置：

- **Microsoft 云**。 用户使用"反馈中心"应用上载的数据存储天数与"下一代隐私" (NGP) 要求一致。 在此期间，Microsoft 员工可以使用符合 NGP 的查看器访问信息。
   > [!NOTE]  
   > 这些要求适用于所有反馈中心类别的数据。

- **HoloLens 设备**。 在反馈中心中提交报告时，用户可以选择"保存提供反馈时创建的诊断和**附件的本地副本"。** 如果用户选择此选项，反馈中心将存储 HoloLens 设备上诊断信息的副本。 用户或使用此帐户 (HoloLens 帐户的任何人仍可以访问此信息) 。 若要删除此信息， **用户必须对设备** 拥有设备所有者 **或** 管理员权限。 具有相应权限的用户可以登录到反馈中心，选择"设置视图"诊断****  >  **日志**并删除信息。

## 设置疑难解答程序

HoloLens 用户可以使用设备的"设置"应用解决问题并收集诊断信息。 为此，请执行下列步骤：

1. 打开"设置"应用，**** 然后选择"&  >  **安全疑难解答**"页。
1. 选择相应的区域，然后选择"开始 **"。**
1. 重现问题。
1. 重现问题后，返回到"设置"，然后选择"**停止"。**

### 必备条件

- The Settings app is installed on the device and is available to the user.

### 数据位置、访问和保留

由于用户启动数据收集，因此用户隐式同意存储诊断信息。 只有用户或与之共享数据的任何人才能访问数据。

诊断信息存储在设备上。 如果设备连接到用户的计算机，则信息也驻留在计算机中的以下文件中：

> 此电脑\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 在此文件路径和名称中，表示 HoloLens 设备的名称，并代表文件的 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 创建日期和时间。

诊断信息将一直保留在这些位置，直到用户将其删除。

## DiagnosticLog 云解决方案提供商

在移动设备管理 (MDM) 环境中，IT 管理员可以使用 [DiagnosticLog ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 配置服务提供程序 (CSP) 在已注册的 HoloLens 设备上配置诊断设置。 IT 管理员可以将这些设置配置为从已注册的设备收集日志。

### 必备条件

- 设备已连接到网络。
- 设备在支持 DiagnosticLog CSP 的 MDM 环境中注册。

### 数据位置、访问和保留

由于设备是托管环境的一部分，因此用户隐式同意对诊断信息进行管理访问。

IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括控制以下内容的策略：

- 存储诊断信息的云基础结构。
- 诊断信息的保留期。
- 控制对诊断信息的访问的权限。

## 脱机诊断
如果设备无法通过反馈中心或设置疑难解答收集诊断，可以手动收集诊断。 其中一个场景是必需的，即设备无法连接到 WLAN 的情况。 诊断从设备收集故障转储和日志，以帮助 Microsoft 支持工程师隔离问题。

当设备在通过 USB 电缆连接到电脑后在文件资源管理器中显示时，此功能有效。 

> [!NOTE]
> 脱机诊断生成和管理的控制方式因操作系统版本不同而不同。 以前它由遥测设置控制，但现在通过策略直接控制。 

Windows 全息版[之前的行为，verison 20H2：](hololens-release-notes.md#windows-holographic-version-20h2)
 - 仅在用户通过 OOBE 或 [系统\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为"完全" (Basic 是 HoloLens) 。 
- 若要禁用脱机诊断，请转到"设置应用>**隐私**"页，然后选择**诊断数据****中的"基本"。** 在脱机诊断依赖于遥测设置内部版本上，它仅影响是否收集任何日志。 它不会影响收集的文件。
- 如果设备已锁定，将不会显示日志。

在版本 [Windows Holographic、verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 及前向版本上：
- 启用回退诊断时，由具有相应[设置 MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 策略控制
- 如果设备已锁定，将不会显示日志。


观看此视频了解更多信息。 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

按照以下步骤收集诊断：
1.  使用 USB 电缆将设备连接到电脑。
2.  在电脑上的文件资源管理器中，导航到 **"此电脑 \<hololens-device> \内部存储"。**
3.  如果 **"内部** 存储"文件夹未显示，设备将等待用户登录。 通过按住 POWER 按钮 10 秒来登录或电源循环设备。
4.  同时按下并立即释放 **POWER + VOLUME DOWN** 按钮。
5.  等待一分钟，设备准备 zip 存档。  (生成 zip 存档时，名为 HololensDiagnostics.temp 的临时文件可能会变为可见。 请勿访问或保存该文件。 此过程完成后，它将替换为 zip archives.) 
6.  刷新文件资源管理器，然后导航到 **"\Documents"** 文件夹。
7.  复制诊断 ZIP 文件，并与 Microsoft 支持团队共享这些文件。

> [!NOTE]
> 某些诊断 ZIP 文件可能包含个人身份信息。



