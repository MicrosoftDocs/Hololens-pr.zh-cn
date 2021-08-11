---
title: 收集和使用来自 HoloLens 设备的诊断信息
description: 了解如何从设备收集、使用和保留HoloLens信息。
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
ms.openlocfilehash: 96fe9492da035747a22123ee1cd0c1481cd821a4f2e549b6414a21810ec268d6
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665295"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>收集和使用来自 HoloLens 设备的诊断信息

HoloLens用户和管理员可以从四种不同的方法中选择，从以下方法收集诊断HoloLens：

- 反馈中心应用
- DiagnosticLog 云解决方案提供商
- “设置”应用
- 脱机诊断

> [!IMPORTANT]  
> 设备诊断日志包含 PII (个人身份) ，例如有关用户在典型操作期间启动的进程或应用程序的信息。 例如，当多个用户HoloLens设备 (时，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到同一设备) 诊断日志中可能包含适用于多个用户的 PII 信息。 有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

下表比较了不同的收集方法。 方法名称链接到表后各节中的更多详细信息。

|方法 |先决条件 |数据位置 |数据访问和使用 |数据保留 |
| --- | --- | --- | --- | --- |
|[反馈中心](#feedback-hub) |网络和 Internet 连接<br /><br />反馈中心应用<br /><br />将文件上传到 Microsoft 云的权限 |Microsoft 云<br /><br />HoloLens设备 (可选)  |用户请求协助，同意使用条款，并上传数据<br /><br />Microsoft 员工查看数据，与使用条款一致 |云中数据将保留由 NGP 下一代隐私 (定义的) 。 然后自动删除数据。<br /><br />具有设备所有者或管理员权限的用户随时都可以 **删除设备上的数据**。  |
|[设置疑难解答](#settings-troubleshooter) |“设置”应用 |HoloLens 设备<br /><br />连接的计算机 (可选)  |用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享) 。 |数据将保留在设备上，直到用户将其删除。* |
|[DiagnosticLog 云解决方案提供商](#diagnosticlog-csp) |网络连接<br /><br />支持 DiagnosticLog CSP 的 MDM 环境 |管理员配置存储位置 |在托管环境中，用户隐式同意管理员访问数据。<br /><br />管理员配置访问角色和权限。 | 数据保留在云存储中，管理员配置保留策略。 |
|[脱机诊断](#offline-diagnostics) |设备配置：<ul><li>已打开并连接到计算机</li><li>电源和音量按钮正常运行</li></ul> |HoloLens 设备<br /><br />连接的计算机 |用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享) 。 |数据保留在设备上，直到用户将其删除。 |

* 最终用户负责负责任地与他人共享日志。 联系客户服务和支持人员时，这些文件主要很有用。  

## <a name="feedback-hub"></a>反馈中心

用户HoloLens Microsoft 反馈中心桌面应用将诊断信息发送到 Microsoft 支持。 有关详细信息和完整说明，请参阅 [提供反馈](hololens-feedback.md)。  

> [!NOTE]  
> **商业或企业用户：** 如果使用 反馈中心 应用报告与 MDM、预配或其他任何设备管理方面相关的问题，请更改应用类别，Enterprise **管理**  >  **设备类别**。

>[!IMPORTANT]
> 为了提供最佳数据来解决问题，强烈建议将设备遥测设置为"可选 **"。** 可以在 OOBE 的"开箱即用" (期间) 此值，或者使用 设置 **应用。** 若要使用"应用诊断"设置，请选择"> 设置 >**应用诊断>">"打开"。**
### <a name="prerequisites"></a>先决条件

- 设备已连接到网络。
- 反馈中心应用在用户的台式计算机上可用，用户可以将文件上传到 Microsoft 云。

### <a name="data-locations-access-and-retention"></a>数据位置、访问权限和保留期

通过同意协议使用条款反馈中心，用户显式同意 (协议协议所定义的数据的存储和) 。

该反馈中心为用户提供两个存储诊断信息的位置：

- **Microsoft 云**。 用户使用新应用上传反馈中心数据的天数与 NGP 下一代隐私 (一) 要求。 在此期间，Microsoft 员工可以使用符合 NGP 的查看器来访问信息。

   > [!NOTE]  
   > 这些要求适用于所有类别反馈中心数据。

- **HoloLens设备**。 在提交报表反馈中心，用户可以选择"保存提供反馈时创建的诊断和 **附件的本地副本"。** 如果用户选择此选项，则反馈中心将诊断信息的副本存储在HoloLens设备上。 此信息仍可供用户或 (该帐户登录登录的任何人访问HoloLens) 。 若要删除此信息，用户必须对设备 **拥有** "设备所有者 **"** 或"管理员"权限。 具有相应权限的用户可以登录到 反馈中心，选择"设置  >  **查看诊断** 日志"并删除信息。

## <a name="settings-troubleshooter"></a>设置疑难解答

用户HoloLens设备上使用 设置 应用来排查问题并收集诊断信息。 要实现这一点，请执行下列操作：

1. 打开"设置"应用，然后选择"&**安全**  >  **疑难解答"** 页。
1. 选择适当的区域，然后选择"启动 **"。**
1. 重现问题。
1. 重现问题后，返回到设置，然后选择"停止 **"。**

用户还可以从应用配置回退诊断 **设置** 行为。 导航到 **"隐私 ->故障排除"** 页以配置此设置。
> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。

### <a name="os-update-troubleshooter"></a>OS 更新疑难解答
在[Holographic Windows版本 21H1 及之后](hololens-release-notes.md#windows-holographic-version-21h1)的版本上：
- 除了之前在 设置 应用中的疑难解答之外，还添加了新的疑难解答，并添加了新的 设置 OS 更新应用。 导航到 **"设置 -> 更新&安全性 ->故障排除 -> Windows 更新"，然后选择"** 启动 **"。** 这样，在重现 OS 更新问题时可以收集跟踪，以更好地帮助 IT 或支持人员进行故障排除。
### <a name="prerequisites"></a>先决条件

- 设置 **应用** 安装在设备上，可供用户使用。

### <a name="data-locations-access-and-retention"></a>数据位置、访问权限和保留期

由于用户启动数据收集，因此用户隐式同意存储诊断信息。 只有用户或与之共享数据的任何人都可以访问数据。

诊断信息存储在设备上。 如果设备已连接到用户的计算机，则信息也驻留在计算机中的以下文件中：

> 此电脑 \\ \<*HoloLens device name*> \\ 内部存储 \\ \\ 文档跟踪 \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 在此文件路径和名称中， 表示HoloLens的名称，表示文件的 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 创建日期和时间。

诊断信息将保留在这些位置，直到用户将其删除。

## <a name="diagnosticlog-csp"></a>DiagnosticLog 云解决方案提供商

在 Mobile 设备管理 (MDM) 环境中，IT 管理员可以使用[DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp)配置服务提供程序 (CSP) 在已注册的 HOLOLENS 设备上配置诊断设置。 IT 管理员可以将这些设置配置为从已注册的设备收集日志。

查看更多：
- [从 Windows 设备收集诊断信息](/mem/intune/remote-actions/collect-diagnostics)
- [Intune 公共预览版 - Windows 10设备诊断](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>先决条件

- 设备已连接到网络。
- 设备在支持 DiagnosticLog CSP 的 MDM 环境中注册。

### <a name="data-locations-access-and-retention"></a>数据位置、访问权限和保留期

由于设备是托管环境的一部分，因此用户隐式同意对诊断信息的管理访问权限。

IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括控制以下各项的策略：

- 存储诊断信息的云基础结构。
- 诊断信息的保留期。
- 控制对诊断信息的访问的权限。

## <a name="offline-diagnostics"></a>脱机诊断
如果设备无法通过诊断程序或故障排除反馈中心收集设置，可以手动收集诊断信息。 需要这样做的一种情况是设备无法连接到 Wi-Fi或者无法访问上述其他方法。 诊断从设备收集故障转储和日志，以帮助 Microsoft 支持工程师隔离问题。

当设备通过 USB 电缆连接到电脑文件资源管理器设备显示在电脑中时，此操作有效。

> [!NOTE]
> 脱机诊断的生成和管理根据 OS 版本以不同方式进行控制。 以前，它由遥测设置控制，但现在通过 MDM 策略直接控制。 如果通过设置或 MDM 策略禁用，则不能使用此机制收集诊断日志。

Holographic 版本[20H2 Windows之前的行为](hololens-release-notes.md#windows-holographic-version-20h2)：
 - 只有在用户通过 OOBE 或[System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)策略值设置为 Full (Basic 是 HoloLens) 时，才启用脱机HoloLens) 。 
- 若要禁用脱机诊断，请转到"设置 **应用>隐私**"页，然后选择 **"诊断数据**"中的"**基本"。** 在脱机诊断依赖于遥测设置的生成上，它仅影响是否收集任何日志。 它不会影响收集哪些文件。
- 如果设备已锁定，则不显示日志。

在[Holographic Windows版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)及之后的版本上：
- 启用回退诊断时，由特定 MDM 策略控制，并相应地设置 [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- 如果设备已锁定，则不显示日志。

观看此视频，了解详细信息。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

请按照以下步骤收集诊断信息：
1.  连接 USB 电缆将设备连接到电脑。
2.  在文件资源管理器中，导航到 **"此电脑 \<hololens-device> \内部存储"。**
3.  如果 **"存储"** 文件夹未显示，则设备正在等待用户登录。 通过按住 POWER 按钮 10 秒来登录或关闭设备电源。
4.  同时按下并立即释放 **"电源 + 音量降低** "按钮。
5.  等待一分钟，让设备准备 zip 存档。  (生成 zip 存档时，名为 HololensDiagnostics.temp 的临时文件可能会变得可见。 请勿访问或保存该文件。 该过程完成后，它将替换为 zip archives.) 
6.  刷新文件资源管理器，并导航到 **"\Documents"** 文件夹。
7.  复制诊断 ZIP 文件，并与 Microsoft 支持团队共享这些文件。

> [!NOTE]
> 某些诊断 ZIP 文件可能包含 PII。
