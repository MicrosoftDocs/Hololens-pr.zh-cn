---
title: 安装 HoloLens 的本地化版本
description: 了解如何安装 HoloLens (第一代) 的本地化版本，包括中文版和日语版。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308538"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="fb205-103">安装 HoloLens (第一代的本地化版本) </span><span class="sxs-lookup"><span data-stu-id="fb205-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="fb205-104">若要切换到中文版或日语版的 HoloLens，需要使用 Windows 设备恢复工具 (WDRT) 下载计算机上的语言版本，然后将其安装在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="fb205-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb205-105">使用 WDRT 安装 HoloLens 的中文版或日语版时，会从你的 HoloLens 中删除现有数据，如个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="fb205-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="fb205-106">在电脑上，下载并安装 [Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="fb205-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="fb205-107">下载所需的计算机语言包：  [简体中文](https://aka.ms/hololensdownload-ch) 或 [日语](https://aka.ms/hololensdownload-jp)。</span><span class="sxs-lookup"><span data-stu-id="fb205-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="fb205-108">下载完成后，选择 "**文件资源管理器**  >  **下载**"。</span><span class="sxs-lookup"><span data-stu-id="fb205-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="fb205-109">右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="fb205-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="fb205-110">使用随附的微 USB 电缆将你的 HoloLens 连接到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="fb205-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="fb205-111">即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) </span><span class="sxs-lookup"><span data-stu-id="fb205-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="fb205-112">工具自动检测到 HoloLens 后，选择 "Microsoft HoloLens" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="fb205-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="fb205-113">在下一个屏幕上，选择 " **手动包选择**"，   然后选择在步骤4中解压缩的文件夹中所安装的安装文件。</span><span class="sxs-lookup"><span data-stu-id="fb205-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="fb205-114"> (查找扩展名为 "ffu" 的文件。 ) </span><span class="sxs-lookup"><span data-stu-id="fb205-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="fb205-115">选择 " **安装软件** "，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fb205-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="fb205-116">生成安装后，HoloLens 安装程序将自动启动。</span><span class="sxs-lookup"><span data-stu-id="fb205-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="fb205-117">放入设备并按照安装说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fb205-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="fb205-118">完成安装后，请参阅 "**设置**" "  >  **更新" "更新 & 安全**  >  **Windows 预览体验计划**"，并检查是否已配置为接收最新的预览版。</span><span class="sxs-lookup"><span data-stu-id="fb205-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="fb205-119">与英语预览版一样，Windows 预览体验计划将更新的中文版和日语版与最新的预览版本保持最新。</span><span class="sxs-lookup"><span data-stu-id="fb205-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="fb205-120">不能使用 "设置" 应用更改英语、日语和中文的系统语言。</span><span class="sxs-lookup"><span data-stu-id="fb205-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="fb205-121">闪烁新的版本是唯一受支持的更改设备系统语言的方法。</span><span class="sxs-lookup"><span data-stu-id="fb205-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="fb205-122">虽然可以使用屏幕拼音键盘输入简体中文或日语文本，但目前不支持使用蓝牙硬件键盘键入简体中文或日语文本。</span><span class="sxs-lookup"><span data-stu-id="fb205-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="fb205-123">但是，在中文或日语版 HoloLens 上，你可以继续使用蓝牙键盘键入英语 (以将硬件键盘切换为输入英语，按 ~ 键) 。</span><span class="sxs-lookup"><span data-stu-id="fb205-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
