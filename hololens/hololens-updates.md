---
title: 管理 HoloLens 更新
description: 了解管理员如何使用移动设备管理来管理 HoloLens 设备更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 635e2cc274101fcf08fd05f2b3b54ce6c2f79182011d76409a51c722ea47ecc7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662787"
---
# <a name="manage-hololens-updates"></a>管理 HoloLens 更新

HoloLens 使用 Windows 更新的方式与其他 Windows 10 设备相同。 当有可用更新时，下次设备接通电源并连接到 Internet 时，会自动下载并安装。 本文介绍如何在企业或其他托管环境中管理 HoloLens 更新。 有关如何管理单个 HoloLens 设备更新的信息，请参阅[更新 HoloLens](hololens-update-hololens.md)。

## <a name="manage-updates-automatically"></a>自动管理更新

### <a name="managing-updates-by-using-windows-update-for-business"></a>使用适用于企业的 Windows 更新管理更新

Windows Holographic for Business 可以使用[适用于企业的 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb)管理更新。 所有 HoloLens 2 设备均可使用 Windows Holographic for Business。 确保它们使用 Windows Holographic for Business 内部版本 10.0.18362.1042 或更高内部版本。 如果使用的是 HoloLens（第一代）设备，则必须[将其升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 才能管理其更新。

适用于企业的 Windows 更新将 HoloLens 设备直接连接到 Windows 更新服务。 通过使用适用于企业的 Windows 更新，你可以控制更新过程的多个方面&mdash;：具体而言，哪些设备将在什么时候获取哪些更新。 例如，可先将更新部署到设备的某个子集进行测试，随后再对剩余的设备进行更新。 或是为不同类型的更新制定不同的更新计划。

> [!NOTE]  
> 可以自动管理 HoloLens 设备的功能更新（每年发布两次）和质量更新（每月发布或根据需要发布，包括关键安全更新）。 有关更新类型的详细信息，请参阅[适用于企业的 Windows 更新管理的更新类型](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。

可以使用移动设备管理 (MDM) 解决方案中的 Microsoft Intune 等策略为 HoloLens 配置适用于企业的 Windows 更新设置。

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>使用 Microsoft Intune 管理适用于企业的 Windows 更新

如需详细了解如何使用 Intune 配置适用于企业的 Windows 更新，请参阅[在 Intune 中管理 Windows 10 软件更新](/intune/protect/windows-update-for-business-configure)。 有关 HoloLens 支持的特定 Intune 功能的详细信息，请参阅 [HoloLens 支持的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。

> [!IMPORTANT]  
> Intune 提供两种管理更新的策略类型，分别是：Windows 10 更新通道和 Windows 10 功能更新。 Windows 10 功能更新策略目前尚处于公共预览版阶段，暂不支持 HoloLens。
>  
> 你可以使用 Windows 10 更新通道策略管理 HoloLens 2 更新。

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>配置 HoloLens 2 或 HoloLens（第一代）更新策略

本部分介绍用于管理 HoloLens 2 或 HoloLens（第一代）更新的策略。 有关可用于 HoloLens 2 的功能的详细信息，请参阅[规划和配置 HoloLens 2 更新推出](#plan-and-configure-update-rollouts-for-hololens-2)。

[策略 CSP - 更新](/windows/client-management/mdm/policy-csp-update)定义配置适用于企业的 Windows 更新的策略。

> [!NOTE]  
> 有关特定版本的 HoloLens 支持的特定策略配置服务提供程序 (CSP) 的列表，请参阅 [HoloLens 设备支持的策略 CSP](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。

#### <a name="configure-automatic-checks-for-updates"></a>配置自动检查更新

可以使用“Update/AllowAutoUpdate”策略管理扫描、下载和安装更新等自动更新行为。 有关此策略的可用设置的详细信息，请参阅 [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。

> [!NOTE]  
> 在 Microsoft Intune 中，可以使用 **自动更新行为** 来更改此策略。 有关详细信息，请参阅[在 Intune 中管理 Windows 10 软件更新](/intune/windows-update-for-business-configure)。

#### <a name="configure-an-update-schedule"></a>配置更新计划

若要配置应用更新的方式和时间，请使用以下策略：

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 值的范围：0–7（其中 0 代表每天，1 代表周日，7 代表周六）
  - 默认值：0（每天）
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - 值的范围：0-23（其中 0 代表午夜，23 代表晚上 11 点）
  - 默认值：凌晨 3 点

#### <a name="configure-active-hours"></a>配置使用时段
从 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 开始，IT 管理员可以指定 HoloLens 2 设备的使用时段范围。

“使用时段”可标识你希望设备正在使用中的时段。 更新后自动重启将在使用时段外发生。 指定的范围将从使用时段开始时间计算。 可以使用 MDM，如[使用 MDM 配置使用时段](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)中所述。 MDM 使用策略 CSP 中的 Update/ActiveHoursStart 和 Update/ActiveHoursEnd 以及 Update/ActiveHoursMaxRange 设置配置使用时段。

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - 此值设置结束时间。 从开始时间起最长为 12 小时。
    -   支持的值为 0-23，其中 0 为中午 12 点，1 为凌晨 1 点，依此类推。
    -   默认值为 17（下午 5 点）。
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - 此值设置从开始时间起的最大使用时段。
    -   支持的值为 8-18。
    -   默认值为 18（小时）。
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - 此值设置开始时间。 从结束时间起最长为 12 小时。
    -   支持的值为 0-23，其中 0 为中午 12 点，1 为凌晨 1 点，依此类推。
    -   默认值为 8（早上 8 点）。

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>只针对运行 Windows 10 1607 版本的设备

可以使用以下更新策略配置设备从 Windows Server Update Services (WSUS) 而非从 Windows 更新获取更新：

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>规划和配置 HoloLens 2 更新推出

相比 HoloLens（第一代），HoloLens 2 支持更多自动化更新功能。 如果你使用 Microsoft Intune 来管理适用于企业的 Windows 更新策略，尤其如此。 借助这些功能，可更轻松地规划和部署整个组织的更新。

#### <a name="plan-the-update-strategy"></a>规划更新策略

适用于企业的 Windows 更新支持延期策略。 Microsoft 发布更新后，你可以使用延期策略定义在设备上等待多久后安装该更新。 通过将设备子集（即“更新通道”）与不同的延期策略相关联，可协调组织的更新推出策略。

例如，假设某个组织拥有 1,000 台设备，并且必须通过 5 种方式更新设备。 该组织可按下表所示，创建 5 个更新通道。

|Group |设备数 |延期（天数） |
| ---| :---: | :---: |
|组 1（IT 人员） |5 |0 |
|组 2（早期采用者） |50 |60 |
|组 3（主要设备 1） |250 |120 |
|组 4（主要设备 2） |300 |150 |
|组 5（主要设备 3） |395 |180 |

随着时间推移，整个组织将按照此过程推出更新。

![更新部署日程表](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>配置更新延期策略

延期策略指定可用更新日期和向设备提供更新日期之间间隔的天数。

可为功能更新和质量更新配置不同的延期天数。 下表列出了每种类型要使用的具体策略及每个类型最多可以延期的天数。

|类别 |策略 |最大延迟 |
| --- | --- | --- |
|功能更新 |DeferFeatureUpdatesPeriodInDays |365 天 |
|质量更新 |DeferQualityUpdatesPeriodInDays |30 天 |

#### <a name="pause-updates-via-device"></a>通过设备暂停更新

如果用户无权访问 MDM，则他们可以在包含内部版本 [Windows 全息版 2004](hololens-release-notes.md#windows-holographic-version-2004) 或更高版本的 HoloLens 2 设备上分别手动暂停更新长达 35 天。 用户可以通过导航至“设置”>“更新和安全”>“高级选项”并滚动至“暂停更新”，选择将暂停更新的结束日期，来实现此设置。 用户达到暂停限制后，设备将需要获取新的更新，然后它们才能再次暂停。 

从 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 开始，可以为 HoloLens 2 设备管理此暂停更新功能。 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。
    - 0（默认值）– 已启用
    - 1 – 已禁用

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens 支持的 Intune 更新管理功能

可使用下列 Intune 更新管理功能来管理 HoloLens 更新。

- 创建和分配：这些功能将 Windows 10 更新通道添加到更新通道列表中。 有关详细信息，请参阅[创建和分配更新通道](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。

- 暂停：如果部署功能或质量更新时遇到问题，可暂停更新 35 天（从指定日期开始计算）。 暂停后会阻止其他设备安装更新，直至你解决或缓解该问题。 即使暂停功能更新，仍会向设备提供质量更新以确保它们保持安全。 暂停更新类型后，该通道的“概述”窗格将显示该更新类型恢复之前剩余的天数。 指定时间过后，暂停将自动过期，并继续更新进程。

  暂停更新通道时，可选择以下任一选项：

  - 延长：延长更新类型暂停期限 35 天。
  - 恢复：将该通道的更新还原为活动操作。 如果有必要，可以再次暂停更新通道。

  > [!NOTE]  
  > HoloLens 2 设备不支持更新通道的“卸载”操作。

### <a name="delivery-optimization-preview"></a>传递优化预览版

[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 已启用传递优化设置的早期预览版，以减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能的更完整说明以及建议的网络配置：[Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

以下设置作为管理图面的一部分启用，并且[可以从 Intune 进行配置](/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

有关此预览版产品/服务的一些注意事项：

- 此预览版中的 HoloLens 支持仅限于 OS 更新。
- Windows Holographic for Business 仅支持 HTTP 下载模式并从 [Microsoft 联网缓存终结点](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)进行下载；目前，HoloLens 设备不支持对等下载模式和组分配。
- HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。
- 故障排除将需要对联网缓存服务器进行诊断，或通过“设置” > “更新和安全” >  “故障排除” >  “Windows 更新”在 HoloLens 上收集跟踪。

## <a name="manually-check-for-updates"></a>手动检查更新

虽然 HoloLens 会定期检查系统更新，但在某些情况下，仍可能需要手动检查。

若要手动检查更新，请转到“更新” > “更新和安全” > “检查更新”。 如果“设置”应用指示你的设备已是最新版本，则表示你已安装所有可用更新。

## <a name="manually-roll-back-an-update"></a>手动回滚更新

在某些情况下，你可能想要还原到 HoloLens 软件的早期版本。 根据使用的是 HoloLens 2 还是 HoloLens（第一代），选择以下对应的操作流程。

### <a name="revert-to-a-previous-version-hololens-2"></a>还原到早期版本 (HoloLens 2)

可使用 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens 2 的早期版本。

> [!NOTE]
> 还原到早期版本会删除你的个人文件和设置。

若要还原到 HoloLens 2 的早期版本，请按照如下步骤操作：

1. 请确保你没有任何手机或 Windows 设备连接到电脑。
1. 在计算机上，从 Microsoft Store 下载 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下载[最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
1. 完成这些下载后，打开“文件资源管理器” > “下载”，右键单击刚才下载的压缩 (.zip) 文件夹，然后选择“全部解压缩” > “解压缩”以展开该文件。
1. 使用 USB-A 到 USB-C 数据线将 HoloLens 设备连接到电脑。 即使你在连接 HoloLens 时一直使用的是其他数据线，但此数据线的使用效果更好。
1. “Advanced Recovery Companion”会自动检测到 HoloLens 设备。 选择“Microsoft HoloLens”磁贴。
1. 在下一个屏幕中，选择“手动包选择”，然后打开先前展开的文件夹。
1. 选择安装 (.ffu) 文件。
1. 选择“安装软件”，然后按照说明进行操作。

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>还原到早期版本（HoloLens (第一代)）

可使用 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) 将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens（第一代）的早期版本。

> [!NOTE]
> 还原到 HoloLens 早期版本会删除你的个人文件和设置。

要还原到 HoloLens（第一代）的早期版本，请按照如下步骤操作：

1. 请确保你没有任何手机或 Windows 设备连接到电脑。
1. 在计算机上，下载 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 完成这些下载后，打开“文件资源管理器” > “下载”，右键单击刚才下载的压缩 (.zip) 文件夹，然后选择“全部解压缩” > “解压缩”以展开该文件。
1. 使用与 HoloLens 设备随附的 micro-USB 数据线将 HoloLens 设备连接到电脑。 即使你在连接 HoloLens 时一直使用的是其他数据线，但原厂数据线的使用效果更好。
1. WDRT 会自动检测到 HoloLens 设备。 选择“Microsoft HoloLens”磁贴。
1. 在下一个屏幕中，选择“手动包选择”，然后打开先前展开的文件夹。
1. 选择安装 (.ffu) 文件。
1. 选择“安装软件”，然后按照说明进行操作。

如果 WDRT 未检测到你的设备

如果 WDRT 未检测到 HoloLens 设备，请尝试重启电脑。 如果重启不起作用，请选择“未检测到我的设备”，选择“Microsoft HoloLens”，然后按照说明操作。

## <a name="related-articles"></a>相关文章

- [HoloLens 2 发行说明](hololens-release-notes.md)
- [什么是适用于企业的 Windows 更新？](/windows/deployment/update/waas-manage-updates-wufb)
- [将设备分配给 Windows 10 更新的服务分支](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [在 Intune 中管理 Windows 10 软件更新](/mem/intune/protect/windows-update-for-business-configure)
