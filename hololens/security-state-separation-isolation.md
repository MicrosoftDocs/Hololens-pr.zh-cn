---
title: 状态分离和隔离
description: 了解 HoloLens 2 混合现实设备上的状态分离、隔离、代码签名和 Defender 应用程序。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全, hololens, 状态分离, 状态分离和隔离, hololens 2, hololens2 安全, 安全概述, 安全体系结构, 体系结构, hololens 2 体系结构
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034205"
---
# <a name="state-separation-and-isolation"></a>状态分离和隔离

状态分离和隔离可保护 Hololens 2 操作系统中的关键部分，防止其发生更改，例如操作系统启动进入受信任状态所需的部分。 借助隔离技术，不受信任的应用程序将被移至隔离的沙盒环境，以确保它们不会影响系统安全。

## <a name="state-separation"></a>状态分离

HoloLens 2 的状态分离极大地提高了安全性和可维护性（更新），并有助于保护应用程序数据。  状态分离的工作方式如下：
  * 核心操作系统存储在核心操作系统卷中（受信任或经验证的 Microsoft 操作系统更新操作系统）。
  * 操作系统中可以在运行时更改的部分（例如可下载的驱动程序和配置），使用进一步的状态分离来对数据进行分区，并将其存储在安全的独立存储位置中。
  * 每个安全存储位置都有与之关联的独特安全策略，从而提供了各种安全优势，如以下部分所述。

## <a name="state-separation-benefits"></a>状态分离优势

  * 安全性：HoloLens 2 中的状态分离功能可显著提高平台完整性、抵抗恶意软件和保护用户数据。 通过分离操作系统的不可更改部分并将其设置为只读或受完整性保护，状态分离使恶意软件在冷启动期间难以持久存在。 
  * 更新：使用 HoloLens 2，一旦核心操作系统不可修改且与设备上的其余数据完全分开，更新就变得简单而可靠。  此外，状态分离为显著加快更新速度奠定了重要基础，这使得可以在一个步骤（原子单元）中更换操作系统。
  * 设备重置：HoloLens 2 重置可清除设备上用户生成的数据和用户应用数据（包括内部和外部存储位置）。 它将保留当前的 OS 应用和安全关键应用以及当前的 Microsoft 和 OEM 自定义应用（预安装）。 重置完成后，可以在设备上为这些预安装应用解除冻结

### <a name="state-separation-states"></a>状态分离状态

状态分离确保操作系统只能由 Microsoft 信任的设备组件进行更改，并且仅允许高值状态在重新启动后保持不变；其他系统状态仅在启动会话期间存在，并且在重新启动后将被丢弃。 进行状态分离后，设备会迅速恢复到出厂状态。 Windows Holographic for Business 可以分为以下几种不同类别：
  * 核心操作系统 – 不可更改的状态
  * 操作系统数据 – 可更改的状态 
  * 用户数据 – 可更改的状态

下一节逐一介绍了这些 HoloLens 2 工作状态。

#### <a name="core-operating-system"></a>核心操作系统

不可变状态由不可更改的可执行文件和数据组成，并且只能由 Microsoft 在安装更新的过程中进行更改。 在核心操作系统的此类更新期间，将启用一个包含最新所需操作状态的新映像。
不可更改的状态被标记为只读（或以其他方式受完整性保护），从而防止任何具有提升特权的恶意软件持续存在。 以下可执行文件和数据以不可变状态受保护：
  * Windows Holographic 收件箱驱动程序
  * 操作系统二进制文件
  * Windows 收件箱驱动程序
  * Windows 注册表配置单元 (HKLM) 中存储的静态 Windows Holographic 设置
    * 示例：HKLM 存储安装在计算机上的应用的配置信息。 它还会存储信息来检测硬件和相应的驱动程序。
通过在不可变（完整性和只读保护）状态下保护它们，可确保核心操作系统始终启动到受信任状态。 此外，重置设备后，我们可以确保设备仅启动到该不可变部分的组件中。 

#### <a name="operating-system-data"></a>操作系统数据 

请务必注意，当数据损坏或泄露时，可在运行时更改（并且对操作系统功能并不重要）的可执行文件和数据可被丢弃，然后再重新创建。 高值可变状态要么是功能上操作系统要求持续存在，要么应在操作系统关闭期间和/或在受支持的 Windows 操作系统和设备方案重新启动之间持续存在。 高值可变状态的示例如下：
  * IT 管理员配置的全局设备设置，例如为所有用户禁用位置。
  * Wi-fi 网络连接访问数据设备记住的网络以及关联的连接密码。
  * 故障转储（包括设置、日志）。
  * 按需为新发现的设备下载的驱动程序。
HoloLens 2 上的高值可更改状态位于操作系统数据安全位置上，既可以作为磁盘上的已保存文件，也可以作为保留的注册表配置单元。

#### <a name="user-data"></a>用户数据

最后一个状态类别表示由 UWP 应用程序或操作系统生成或保留的用户数据。 “下载”、“文档”、“视频”等所有已知用户文件夹、用户配置文件和 HKEY_CURRENT_USER 配置单元也存储在此位置。 如果没有适当的凭据，则无法提取此数据；若要深入了解如何保护你的数据，请参阅[加密和数据保护](security-encryption-data-protection.md)。

##  <a name="isolation"></a>隔离

为实现此平衡，HoloLens 2 拥有一个核心操作系统，可用于启动、硬件控制、登录等主要功能。在核心操作系统（预安装的应用程序和 UWP 应用）上仅运行两组应用程序。

## <a name="code-signing"></a>代码签名

数字签名代码可以证明可执行文件和脚本没有被修改，因为它们是由受信任的源签名的，因此提供了真实性和完整性。 默认情况下，HoloLens 2 信任的机构是 Microsoft 和 Microsoft Store。 IT 管理员可以通过 [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) 和 [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP 向设备添加新证书。 还可以使用 [AllowAllTrustedApps 策略](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)来信任其他旁加载或[业务线应用](/intune/apps/lob-apps-windows)。 证书驻留在本地计算机证书存储中，如果使用“设备”，则存储在 HKLM/Root 中；如果使用“用户”，则存储在 HKCU 中。

## <a name="defender-protections"></a>Defender 保护
HoloLens 2 使用 Microsoft 服务为用户提供更高级别的安全性：

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 由操作系统自动在 Windows Holographic 上启用，可防止 Microsoft Edge 上的网络钓鱼和恶意软件以及潜在的恶意文件下载。 无法由用户关闭，但可通过策略禁用。

* [Defender 防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)会阻止未经授权的网络流量出入你的设备。 默认情况下，它处于启用状态，且不能由客户通过本地操作或策略进行配置。 

* [Windows Defender 应用程序控制](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)：HoloLens 2 支持 WDAC，它使 IT 管理员能够将应用程序控制策略推送到设备上。 有关详细信息，请参阅[在具有 MSFT Intune 的 HoloLens 2 设备上使用 WDAC](/mem/intune/configuration/custom-profile-hololens)。 

IT 管理员可以通过 [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) 管理 SmartScreen 行为，并通过[这些策略](/windows/client-management/mdm/policy-csps-supported-by-hololens2)管理浏览器行为。 

