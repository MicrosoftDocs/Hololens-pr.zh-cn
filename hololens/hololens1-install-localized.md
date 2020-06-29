---
title: 安装 HoloLens 的本地化版本
description: 了解如何安装 HoloLens 的中文或日语版本
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828035"
---
# <span data-ttu-id="ec3ab-103">安装 HoloLens（第一代）的本地化版本</span><span class="sxs-lookup"><span data-stu-id="ec3ab-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="ec3ab-104">若要切换到 HoloLens 的中文或日语版本，你需要在电脑上使用 Windows Device Recovery Tool (WDRT) 下载相应语言的内部版本，然后将其安装到 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec3ab-105">使用 WDRT 安装 HoloLens 的中文或日语版本时，将从 HoloLens 中删除现有数据，如个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="ec3ab-106">在你的电脑上，下载并安装 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="ec3ab-107">将所需语言的程序包下载到电脑：[简体中文](https://aka.ms/hololensdownload-ch)或[日语](https://aka.ms/hololensdownload-jp)。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="ec3ab-108">下载完成后，选择**文件资源管理器** > **下载**。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="ec3ab-109">右键单击刚刚下载的压缩文件夹，然后选择**全部提取** > **提取**将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="ec3ab-110">使用随附的微型 USB 电缆将 HoloLens 连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="ec3ab-111">（即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）</span><span class="sxs-lookup"><span data-stu-id="ec3ab-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="ec3ab-112">在工具自动检测到 HoloLens 后，选择 Microsoft HoloLens 磁贴。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="ec3ab-113">在下一个屏幕上，选择 **手动选择程序包** ，然后选择你在步骤 4 中解压缩的文件夹中的安装文件。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="ec3ab-114">（查找扩展名为“.ffu”的文件。）</span><span class="sxs-lookup"><span data-stu-id="ec3ab-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="ec3ab-115">选择 **安装软件**，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="ec3ab-116">在安装版本后，HoloLens 设置将自动启动。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="ec3ab-117">戴上设备，按照设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="ec3ab-118">完成设置后，转到**设置** > "**更新和安全** > **Windows 预览体验计划**，检查是否已配置为接收最新预览版。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="ec3ab-119">与英语预览版一样，Windows 预览体验计划将使用最新预览版让 HoloLens 的中文和日语版本保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="ec3ab-120">你无法使用“设置”应用在英语、日语和中文之间更改系统语言。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="ec3ab-121">支持更改设备系统语言的唯一方法是更新新版本。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="ec3ab-122">虽然你可以使用屏幕上的拼音键盘输入简体中文或日语文本，但目前不支持使用蓝牙硬件键盘键入简体中文或日语文本。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="ec3ab-123">但是，在中文或日语版 HoloLens 中，你可以继续使用蓝牙键盘键入英文（若要将硬件键盘切换为键入英文，请按 ~ 键）。</span><span class="sxs-lookup"><span data-stu-id="ec3ab-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
