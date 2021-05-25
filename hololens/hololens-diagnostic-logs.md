---
title: 从 HoloLens 设备收集和使用诊断信息
description: 了解如何从 HoloLens 设备收集、使用和保留诊断信息。
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
ms.openlocfilehash: c1d5205d4faa4384600c489167c9581de8e4b62c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397838"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>从 HoloLens 设备收集和使用诊断信息

HoloLens 用户和管理员可以从四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：

- 反馈中心应用
- DiagnosticLog 云解决方案提供商
- “设置”应用
- 脱机诊断

> [!IMPORTANT]  
> 设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作过程中启动的进程或应用程序。 例如，当多个用户共享一台 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到相同的设备) 诊断日志可能包含适用于多个用户的 PII 信息。 有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

下表比较了不同的收集方法。 方法名称链接到该表后面各节中更详细的信息。

|方法 |先决条件 |数据位置 |数据访问和使用 |数据保留 |
| --- | --- | --- | --- | --- |
|[反馈中心](#feedback-hub) |网络和 internet 连接<br /><br />反馈中心应用<br /><br />将文件上传到 Microsoft 云的权限 |Microsoft 云<br /><br />HoloLens 设备 (可选)  |用户请求协助，同意使用条款，并上传数据<br /><br />Microsoft 员工查看数据，与使用条款一致 |云中的数据保留在下一代隐私 (NGP) 定义的时间段内。 然后，将自动删除数据。<br /><br />具有设备所有者或管理员权限的用户随时都可以 **删除设备上的数据**。  |
|[设置疑难解答](#settings-troubleshooter) |“设置”应用 |HoloLens 设备<br /><br />连接的计算机 (可选)  |用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享) 。 |数据将保留在设备上，直到用户将其删除。* |
|[DiagnosticLog 云解决方案提供商](#diagnosticlog-csp) |网络连接<br /><br />支持 DiagnosticLog CSP 的 MDM 环境 |管理员配置存储位置 |在托管环境中，用户隐式同意管理员访问数据。<br /><br />管理员配置访问角色和权限。 | 数据保留在云存储中，管理员配置保留策略。 |
|[脱机诊断](#offline-diagnostics) |设备配置：<ul><li>已打开并连接到计算机</li><li>电源和音量按钮正常运行</li></ul> |HoloLens 设备<br /><br />连接的计算机 |用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享) 。 |数据保留在设备上，直到用户将其删除。 |

* 最终用户负责负责任地与他人共享日志。 联系客户服务和支持人员时，这些文件主要很有用。  

## <a name="feedback-hub"></a>反馈中心

HoloLens 用户可以使用 Microsoft 反馈中心桌面应用将诊断信息发送到Microsoft 支持。 有关详细信息和完整说明，请参阅 [向我们提供反馈](hololens-feedback.md)。  

> [!NOTE]  
> **商业或企业用户：** 如果使用反馈中心应用报告与 MDM、预配或任何其他设备管理方面相关的问题，请将应用类别更改为 **企业管理**  >  **设备类别**。

>[!IMPORTANT]
> 为了提供可解决问题的最佳数据，我们强烈建议将设备遥测设置为 " **可选**"。 您可以在 (OOBE) 或使用 " **设置** " 应用程序的全新体验期间设置此值。 若要通过使用设置来执行此操作，请选择 **"开始 > 设置" > 隐私 > "应用诊断 >"**。
### <a name="prerequisites"></a>先决条件

- 设备已连接到网络。
- 反馈中心应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。

### <a name="data-locations-access-and-retention"></a>数据位置、访问和保留

通过同意反馈中心的使用条款，用户明确同意该协议) 定义的数据 (的存储和使用情况。

反馈中心为用户提供了两个用于存储诊断信息的位置：

- **Microsoft 云**。 用户使用反馈中心应用上传的数据存储在与下一代隐私 (NGP) 要求一致的天数内。 Microsoft 员工可以使用 NGP 兼容查看器来访问此期间的信息。

   > [!NOTE]  
   > 这些要求适用于所有反馈中心类别中的数据。

- **HoloLens 设备**。 在反馈中心中存档报表时，用户可以选择 " **保存在提供反馈时创建的诊断和附件的本地副本**"。 如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。 此信息仍可供用户 (或使用该帐户登录到 HoloLens) 的任何人访问。 若要删除此信息，用户必须具有设备 **所有者** 或设备的 **管理员** 权限。 具有相应权限的用户可以登录到 反馈中心，选择"设置""查看诊断日志"  >  并删除信息。

## <a name="settings-troubleshooter"></a>设置疑难解答

HoloLens 用户可以使用设备上的设置应用来排查问题并收集诊断信息。 要实现这一点，请执行下列操作：

1. 打开"设置"应用，然后选择 **"&安全**  >  **疑难解答"** 页。
1. 选择适当的区域，然后选择"启动 **"。**
1. 重现此问题。
1. 重现问题后，返回到"设置"，然后选择"停止 **"。**

用户还可以配置"设置"应用中 **回退诊断的行为** 。 导航到 **"隐私 ->故障排除"** 页以配置此设置。
> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。

### <a name="os-update-troubleshooter"></a>OS 更新疑难解答
在内部 [版本中，Windows Holographic 版本 21H1 ](hololens-release-notes.md#windows-holographic-version-21h1) 及及之后版本：
- 除了"设置"应用中前面的疑难解答之外，还添加了新的疑难解答，并添加了新的"OS 更新设置"应用。 导航到 **"设置"->更新&安全性 ->故障排除 -> Windows 更新并选择"****启动"。** 这样，在重现 OS 更新问题时可以收集跟踪，以更好地帮助 IT 或支持人员进行故障排除。
### <a name="prerequisites"></a>先决条件

- **"** 设置"应用安装在设备上，可供用户使用。

### <a name="data-locations-access-and-retention"></a>数据位置、访问权限和保留期

由于用户启动数据收集，因此用户隐式同意存储诊断信息。 只有用户或与之共享数据的任何人都可以访问数据。

诊断信息存储在设备上。 如果设备已连接到用户的计算机，则信息也驻留在计算机中的以下文件中：

> 此电脑 \\ \<*HoloLens device name*> \\ 内部存储 \\ 文档 \\ 跟踪 \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 在此文件路径和名称中， \<*HoloLens device name*> 表示 HoloLens 设备的名称，并 \<*ddmmyyhhmmss*> 表示创建该文件的日期和时间。

诊断信息将保留在这些位置，直到用户删除它。

## <a name="diagnosticlog-csp"></a>DiagnosticLog 云解决方案提供商

在移动设备管理 (MDM) 环境中，IT 管理员可以使用 [DiagnosticLog 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 来配置已注册的 HoloLens 设备上的诊断设置。 IT 管理员可以将这些设置配置为从注册的设备收集日志。

查看详细信息：
- [从 Windows 设备收集诊断信息](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Intune 公共预览版-Windows 10 设备诊断](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>先决条件

- 设备已连接到网络。
- 设备在支持 DiagnosticLog CSP 的 MDM 环境中注册。

### <a name="data-locations-access-and-retention"></a>数据位置、访问和保留

由于设备是托管环境的一部分，因此用户隐式同意对诊断信息的管理访问权限。

IT 管理员使用 DiagnosticLog CSP 来配置数据存储、保留和访问策略，包括控制以下各项的策略：

- 存储诊断信息的云基础结构。
- 诊断信息的保持期。
- 控制诊断信息访问的权限。

## <a name="offline-diagnostics"></a>脱机诊断
如果设备无法通过反馈中心或设置疑难解答收集诊断信息，则可以手动收集诊断信息。 这是必需的一种情况是：设备无法连接到 Wi-Fi 或无法访问上面提到的其他方法。 诊断从设备收集崩溃转储和日志，帮助 Microsoft 支持工程师隔离问题。

当设备通过 USB 电缆连接到电脑后，在文件资源管理器中显示时，这会起作用。

> [!NOTE]
> 脱机诊断的生成和管理根据 OS 版本以不同方式进行控制。 以前，它由遥测设置控制，但现在通过 MDM 策略直接控制。 如果通过设置或 MDM 策略禁用，则不能使用此机制收集诊断日志。

[Windows Holographic 版本 20H2 之前的行为](hololens-release-notes.md#windows-holographic-version-20h2)：
 - 只有在用户通过 OOBE 或 [将 System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为 Full (Basic 是 HoloLens) 时，才启用脱机诊断。 
- 若要禁用脱机诊断，请转到"设置应用>**隐私"页，****然后选择"诊断** 数据"中的"**基本"。** 在脱机诊断依赖于遥测设置的生成上，它仅影响是否收集任何日志。 它不会影响收集哪些文件。
- 如果设备已锁定，则不显示日志。

在内部 [版本中，Windows Holographic 版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 及之后版本：
- 启用回退诊断时，由特定 MDM 策略控制，并相应地设置 [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- 如果设备已锁定，则不显示日志。

观看此视频，了解详细信息。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

请按照以下步骤收集诊断信息：
1.  使用 USB 电缆将设备连接到电脑。
2.  在文件资源管理器中，导航到 **"此电脑 \<hololens-device> \内部存储"。**
3.  如果未 **显示** "内部存储"文件夹，则设备正在等待用户登录。 通过按住 POWER 按钮 10 秒来登录或关闭设备电源。
4.  同时按下并立即释放 **"电源 + 音量降低** "按钮。
5.  等待一分钟，让设备准备 zip 存档。  (生成 zip 存档时，名为 HololensDiagnostics.temp 的临时文件可能会变得可见。 不要访问或保存该文件。 当进程完成时，它将替换为 zip 存档。 ) 
6.  刷新文件资源管理器，然后导航到 **"\Documents"** 文件夹。
7.  复制诊断 ZIP 文件并将其与 Microsoft 支持团队共享。

> [!NOTE]
> 某些诊断 ZIP 文件可能包含 PII。
