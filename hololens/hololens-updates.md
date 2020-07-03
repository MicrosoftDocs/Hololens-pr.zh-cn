---
title: 管理 HoloLens 更新
description: 管理员可以使用移动设备管理来管理 HoloLens 设备更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827668"
---
# 管理 HoloLens 更新

HoloLens 使用 Windows 更新的方式与其他 Windows 10 设备相同。 当有可用更新时，下次设备接通电源并连接到网络时，会自动下载并安装。 本文介绍如何在企业或其他托管环境中管理 HoloLens 更新。 有关管理单个 HoloLens 设备更新的信息，请参阅[更新 HoloLens](hololens-update-hololens.md)。

## 自动管理更新

Windows Holographic for Business 可使用[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)管理更新。 所有 HoloLens 2 设备均可使用 Windows Holographic for Business。 确保你的 HoloLens 2 设备使用 Windows Holographic for Business 10.0.18362.1042 或更高版本。 如果你使用的是 HoloLens（第一代）设备，则必须[将它们升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 以管理更新。

适用于企业的 Windows 更新将 HoloLens 设备直接连接到 Windows 更新服务。 通过使用适用于企业的 Windows 更新，你可以控制更新过程的多个方面&mdash;：具体而言，哪些设备将在什么时候获取哪些更新。 例如，可先将更新部署到设备的某个子集进行测试，日后再对剩余的设备进行更新。 或是为不同类型的更新制定不同的更新计划。

> [!NOTE]  
> 你可以自动管理 HoloLens 设备的功能更新（每年发布两次）和质量更新（每月发布或根据需要发布，包括关键安全更新）。 有关更新类型的更多信息，请参阅[适用于企业的 Windows 更新托管的更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。

可以使用移动设备管理 (MDM) 解决方案中的 Microsoft Intune 等策略为 HoloLens 配置适用于企业的 Windows 更新设置。

如需详细了解如何使用 Intune 配置适用于企业的 Windows 更新，请参阅[在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。

> [!IMPORTANT]  
> Intune 提供两种更新管理策略，分别是：*Windows 10 更新通道*和 *Windows 10 功能更新*。 Windows 10 功能更新策略目前尚处于公共预览版阶段，暂不支持 HoloLens。
>  
> 你可以使用 Windows 10 更新通道策略管理 HoloLens 2 更新。

### 配置 HoloLens 2 或 HoloLens（第一代）更新策略

本节介绍用于管理 HoloLens 2 或 HoloLens（第一代）更新的策略。 有关 HoloLens 2 更多可用功能的信息，请参阅[规划和配置 HoloLens 2 更新推出](#plan-and-configure-update-rollouts-for-hololens-2)。

[策略配置服务提供商 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) 制定配置适用于企业的 Windows 更新的策略。

> [!NOTE]  
> 如需详细了解 HoloLens 特定版本支持的具体策略，请参阅 [HoloLens 设备支持的策略](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)。

#### 配置自动检查更新

可以使用 **Update/AllowAutoUpdate** 策略自动管理扫描、下载和安装更新等更新行为。

该策略支持以下值：

- **0** - 当适用于设备的更新已准备好下载时通知用户。
- **1** - 自动安装更新，然后通知用户计划设备重启。  
- **2** - 自动安装更新，然后重启设备。 该策略默认使用并推荐该值。  

- **3** - 自动安装更新，然后在特定时间重启设备。 指定日期和时间安装更新。 如不指定具体日期和时间，则默认在每天凌晨 3 点安装。  

- **4** - 自动安装更新，然后重启设备。 该选项同样会将“设置”页面设置为“只读”。

- **5** - 关闭自动更新。

如需详细了解该策略的可用设置，请参阅 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。

> [!NOTE]  
> 在 Microsoft Intune 中，你可以使用**自动更新行为**更改该策略。 如需了解更多信息，请参阅[在 Microsoft Intune 中管理软件更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。

#### 配置更新计划

要配置应用更新的方式和时间，请使用以下策略：

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。  
   - 值的范围：**0**–**7**（其中 0 代表每天，1 代表周日，7 代表周六）
   - 默认值：**0**（每天）
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。
   - 值的范围：0-23（其中 0 代表午夜，23 代表晚上 11 点）
   - 默认值：凌晨 3 点

#### 只针对运行 Windows 10 1607 版本的设备

可以使用以下更新策略配置设备从 Windows Server Update Services (WSUS) 而非 Windows 更新获取更新：

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### 规划和配置 HoloLens 2 更新推出

相比 HoloLens（第一代），HoloLens 2 支持更多自动化更新功能。 如果你使用 Microsoft Intune 来管理适用于企业的 Windows 更新策略，尤其如此。 借助这些功能，可更轻松地规划和部署整个组织的更新。

#### 规划更新策略

适用于企业的 Windows 更新支持延期策略。 Microsoft 发布更新后，你可以使用延期策略定义在设备上等待多久后安装该更新。 通过将设备子集（称为“*更新通道*”）与不同的延期策略相关联，可协调组织的更新推出策略。

例如，假设某个组织拥有 1,000 台设备，并且必须通过 5 种方式更新这些设备。 该组织可按下表所示，创建 5 个更新通道。

|组 |设备数量 |延期（天数） |
| ---| :---: | :---: |
|组 1（IT 人员） |5 |0 |
|组 2（早期采用者） |50 |60 |
|组 3（主要设备 1） |250 |120 |
|组 4（主要设备 2） |300 |150 |
|组 5（主要设备 3） |395 |180 |

随着时间推移，整个组织将按照此过程推出更新。

![更新部署日程表](./images/hololens-updates-timeline.png)

#### 配置更新延期策略

延期策略指定可用更新日期和向设备提供更新日期之间间隔的天数。

可为功能更新和质量更新配置不同的延期天数。 下表列出了每种类型要使用的具体策略，以及每个类型最多可以延期的天数。

|类别 |策略 |最大延迟 |
| --- | --- | --- |
|功能更新 |DeferFeatureUpdatesPeriodInDays |365 天 |
|质量更新 |DeferQualityUpdatesPeriodInDays |30 天 |

####  示例：使用 Intune 管理更新

**示例 1：创建和分配更新通道**

有关此示例的更详细版本，请参阅[创建和分配更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。

1. 登录到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然后导航到你的 Intune 配置文件。
1. 选择“**软件更新**” > “**Windows 10 更新通道**” > “**创建**”。
1. 在“**基础**”下，指定名称和说明（选填），然后选择“**下一步**”。
1. 在“**更新通道设置**”下，**服务频道**请选择“**半年频道**”，然后将**功能更新延期期限更改**为 **120 天**。 然后选择“**下一步**”。
1. 在“**分配**”下，选择“**+ 选择要包含的组**”，然后将更新通道分配给一个或多个组。 使用“**+ 选择要排除的组**”微调分配。 然后选择“**下一步**”。
1. 在**审核 + 创建**下，查看设置。 当你准备好保存更新通道配置时，请选择“**创建**”。

更新通道列表现在包括新的 Windows 10 更新通道。

**示例 2：暂停更新通道**

如果部署功能或质量更新时遇到问题，可暂停更新 35 天（从指定日期开始计算）。 暂停后会阻止其他设备安装更新，直至你解决或缓解该问题。 即使暂停功能更新，仍会向设备提供质量更新以确保它们保持安全。 指定时间过后，暂停将自动过期。 此时，将恢复更新过程。

若要暂停 Intune 中的更新通道，请按照如下步骤操作：

1. 在更新通道的“概述”页面，选择“**暂停**”。
1. 选择要暂停的更新类型（**功能**或**质量**更新），然后选择“**确定**”。

暂停更新类型后，相应通道的“概述”窗格会显示更新类型恢复前剩余的天数。

暂停更新通道时，可选择以下任一选项：

- 若要延长更新类型暂停期限 35 天，请选择“**延长**”。
- 若要将该通道的更新还原为活动操作，请选择“**恢复**”。 如果有必要，可以再次暂停更新通道。

> [!NOTE]  
> HoloLens 2 设备不支持更新通道的“**卸载**”操作。

## 手动检查更新

虽然 HoloLens 会定期检查系统更新，免去手动检查之苦，但在某些情况下，仍可能需要手动检查。

若要手动检查更新，请转到“**设置**” > “**更新和安全**” > “**检查更新**”。 如果“设置”应用指示你的设备已是最新版本，则表示你已安装所有可用更新。

## 手动还原更新

在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。 视您使用的是 HoloLens 2 还是 HoloLens（第一代），请选择以下对应的操作流程。

### HoloLens 2 如何返回到早期版本

可使用“高级恢复助手”将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens 2 的早期版本。

> [!NOTE]
> 还原到早期版本会删除你的个人文件和设置。

若要返回到 HoloLens 2 的早期版本，请按照如下步骤操作：

1. 请确保你没有任何手机或 Windows 设备连接到电脑。
1. 在你的电脑上，从 Microsoft 应用商店下载[高级恢复助手](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下载[最新版本的 HoloLens 2](https://aka.ms/hololens2download)。
1. 完成以上下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。
1. 使用 USB-A 到 USB-C 数据线将 HoloLens 设备连接到电脑。 即使你在连接 HoloLens 时一直使用的是其他数据线，但此数据线的使用效果更好。
1. “高级恢复助手”会自动检测到 HoloLens 设备。 选择“**Microsoft HoloLens**”磁贴。
1. 在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。 
1. 选择安装文件（扩展名为 .ffu 的文件）。
1. 选择**安装软件**，然后按照说明操作。

### HoloLens（第一代）如何返回到早期版本

可使用“Windows Device Recovery Tool”将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens（第一代）的早期版本。

> [!NOTE]
> 还原到早期版本会删除你的个人文件和设置。

要返回到 HoloLens（第一代）的早期版本，请按照如下步骤操作：

1. 请确保你没有任何手机或 Windows 设备连接到电脑。
1. 在你的电脑上，下载并安装 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 完成下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。
1. 使用与 HoloLens 设备随附的 micro-USB 数据线将 HoloLens 设备连接到电脑。 即使你在连接 HoloLens 时一直使用的是其他数据线，但原厂数据线的使用效果更好。
1. Windows Device Recovery Tool 会自动检测到 HoloLens 设备。 选择“**Microsoft HoloLens**”磁贴。
1. 在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。 
1. 选择安装文件（扩展名为 .ffu 的文件）。
1. 选择**安装软件**，然后按照说明操作。

> [!NOTE]
> 如果 Windows Device Recovery Tool 未检测到 HoloLens 设备，请尝试重启电脑。 如果重启不起作用，请选择“**未检测到我的设备**”，选择“**Microsoft HoloLens**”，然后按照说明操作。

## 相关文章

- [使用适用于企业的 Windows 更新部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [将设备分配给 Windows 10 更新的服务分支](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
