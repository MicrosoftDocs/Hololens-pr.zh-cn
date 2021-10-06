---
title: HoloLens 2 电池和充电
description: 如何对 HoloLens 进行充电并使用外部电池组。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: a0ae0ccade01d7df520cd6cb142a9b51e63a2b05
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2021
ms.locfileid: "129163975"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 电池和充电

本页提供有关 HoloLens 2 充电和使用外部电池组的详细信息。

## <a name="charging-the-device"></a>对设备充电

使用 HoloLens 2 自带的[充电器和 USB Type-C 线缆](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因为这是设备充电的最快途径。 HoloLens 2 附带的充电器提供最多 9V @ 2A (18W)。 借助提供的壁式充电器，HoloLens 2 设备可在待机状态下在 65 分钟内将电池充满电。 如果这些附件不可用，请确保可用的充电器支持至少 15W 的功率。

> [!NOTE]
> 如果可能，请避免使用电脑通过 USB 给设备充电（速度很慢）。

## <a name="checking-the-battery-charge-level"></a>检查电池电量
如果设备已正确启动且运行，有三种方法可以检查电池电量：

- 从 HoloLens 设备 UI 的主菜单。
- 查看靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。
    - 为设备充电时，电池指示灯将亮起，以指示当前的充电进度。  最后一盏灯将不停闪烁，表示正在充电。
    - 当 HoloLens 处于打开状态时，电池指示灯以五个增量方式显示电池剩余电量。
    - 当五盏灯中只有一盏亮起时，表示电池剩余电量低于 20%。
    - 如果在电池剩余电量严重不足时你尝试打开设备，则一盏灯将会短暂闪烁，然后熄灭。
- 在主机上，打开“文件资源管理器”，然后在左侧的“这台电脑”下查找 HoloLens 2 设备。 右键单击该设备，并选择“属性”。 对话框将显示电池电量。

   ![HoloLens 2 属性屏幕显示电量变化情况。](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>备选充电规范

[USB 电力输送](https://www.usb.org/usb-charger-pd)源最多可为 HoloLens 2 充入 27 瓦电量。 如果源至少能提供 10 瓦，HoloLens 的工作时间可以延长（某些工作负载可能无限期）。 

> [!NOTE]
> 使用 USB-A 到 USB-C 充电线缆会将充电限制为 7.5 瓦。 工作时间仍会延长，但前提是使用 USB-C 到 C。

当 HoloLens 处于待机模式时，18 瓦足以达到内部电池的最大充电率。 如果 HoloLens 正在使用中，则可能会降低充电率，因为 HoloLens 会优先考虑操作而不是充电。

> [!IMPORTANT]
> 建议至少在 5V/1.5A 下对 HoloLens 2 进行充电。 不能使用无法提供至少 5V/1.5A 的充电器。 

### <a name="external-battery-packs"></a>外部电池组

满足上述规范的电池组可用于 HoloLens 2。 但请注意，某些 USB-C 电池组会再次充电，并通过相同的 USB-C 端口供电。 这些电池组务必要要实现 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)，确保它们是对 HoloLens 充电，而不是从中充电。 

### <a name="managing-heat"></a>热管理

与任何设备一样，HoloLens 充电会产生热量。 充电越快，生成的热量越多。 此外，在电池电量较低的情况下开始充电会比电池几乎全满时开始充电产生更多热量。 需要在热环境中长时间运行 HoloLens 的客户可以使用以下技术：

- 即使内部电池完全充电，也可以将 HoloLens 2 连接到外部电源。
- 当外部电池电量耗尽时，HoloLens 将继续运行其内部电池。    
- 如果在执行上述步骤后仍存在发热问题，请考虑使用将充电限制为 1.5A 的充电器或电池组。 请注意，由于内部电池仍将缓慢耗尽，这个选项不会提供足够的运行时间。

## <a name="troubleshooting"></a>疑难解答


### <a name="hololens-charges-external-battery"></a>HoloLens 对外部电池进行充电
如果 HoloLens 2 向外部电池充电而不是通过外部电池充电，则表明电池不能实现 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。 若要解决此问题，建议切换到较新的电池组，但也可以尝试切换到 USB-A 到 USB-C 线缆。 请记住，这会将充电率限制为 7.5 瓦。
