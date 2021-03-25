---
title: 部署指南 - 企业连接的 HoloLens 2 与 Dynamics 365 指南 - 部署
description: 了解如何使用 Dynamics 365 指南通过企业连接网络设置 HoloLens 2 设备的部署。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448517"
---
# <a name="deploy---corporate-connected-guide"></a>部署 - 企业连接指南

每个部署的一个重要部分是确保在自己测试部署之前正确设置部署，以确保最终用户获得流畅的体验。

由于我们要通过 MDM 部署 Wi-Fi 证书，因此，我们首先需要设置 HoloLens，并注册开放 Wi-Fi 网络或不需要证书的网络上的设备。 HoloLens 完成 OOBE 和注册后，设备将收到之前配置的网络证书和 LOB，并且我们能够验证设备是否收到这两者。

之后，你将能够确认可以创作和操作测试指南。

## <a name="enrollment-validation"></a>注册验证

现在，已针对 Azure AD 和 MDM 注册正确配置了一切，其余部分现在应该可以贴靠了。 你将需要连接Wi-Fi HoloLens 设备，以及之前配置的 Azure AD 用户帐户之一。

如果你的设备当前未处于出厂设置状态，那么现在应该重新[调整设备。](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. 设备进入 OOBE 后，你需要开始交互并遵循提示。

2. 连接到无需Wi-Fi加入 WLAN 的开放网络。 这将允许设备下载证书，以在初始设置后Wi-Fi组织证书。

3. 当系统询问"谁拥有此 **HoloLens"时，将看到关键提示？** 选择 **我的工作或学校拥有它** ，然后输入你的 Azure AD 帐户凭据。

4. 注册成功后，系统将提示你设置 PIN。 此 PIN 对于此用户是此设备所特有的。 系统还会提示你输入虹膜扫描、语音数据和遥测设置，最后，你将能够了解如何打开开始菜单并完成 OOBE。

5. 进入混合现实主页后，使用刚学习的"开始"手势 **打开** "开始"菜单。

6. 选择"**设置"** 应用，然后选择"**系统"。** 你将看到的第一条信息是设备名称，对于 HoloLens 2 设备，该名称将为 &quot; HOLOLENS-后跟 &quot; 六个字符字符串。

7. 记下此名称。

    ![HoloLens 2 设置屏幕](./images/hololens2-settings-about.jpg)

8. 验证设备是否成功加入 Azure AD。 有两种方法：

    1.  "设置"应用。 从 **"设置"****中选择"**  ->  **帐户""访问工作或学校"。** 从此屏幕中，你可以查看连接到 azure AD 中的 &quot; nameofAAD&#39;注册成功。 通过 *yourusername@nameofAAD.onmicrosoft.com*连接。 这将验证你的设备已加入你的组织&#39;Azure AD。

    1. [Azure 门户](https://portal.azure.com/#home)。 转到 **"Azure Active Directory**  ->  **设备**  ->  **""所有设备**"，然后搜索设备名称。 在"加入类型"下，它将显示为"已加入 Azure AD"。
        ![验证 Azure AD 中的加入类型](./images/hololens2-devices-all-devices.png)

9. 验证你的设备是否注册了 MDM。 有两种方法：

    1. 从 **"设置"** 中 **，选择"**  ->  **帐户""访问工作或学校"。** 从此屏幕中，你可以查看连接到 azure AD 中的 &quot; nameofAAD&#39;注册成功。 通过 *yourusername@nameofAAD.onmicrosoft.com*连接。 通过选择 Azure AD 中的"连接到 &quot; nameofAAD"，从此&#39;或学校帐户。 按 &quot; "yourusername@nameofAAD.onmicrosoft.com"，然后选择" **信息"** 按钮。

    1. [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。 登录并选择"**设备"，然后选择**"**所有设备"。** 在这里，你可以按名称搜索 HoloLens&#39;。 你应该能够看到在 Intune 上列出的 HoloLens。

        ![在 Azure AD 中验证由 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi证书验证

现在，设备应该已经收到Wi-Fi证书。 最简单的验证是尝试连接到已Wi-Fi证书&#39;连接。 打开"**设置"** 应用并导航到 **" &amp; 网络 Internet**  ->  **WLAN"，** 然后选择 WLAN 连接。 连接后，打开 Microsoft Edge 应用并确认你可以导航到网站。

若要确认你已接收设备上证书，可以使用证书 [管理器](https://docs.microsoft.com/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>验证 LOB 应用安装

若要查看托管应用的安装进度，你可以查看该应用是否已安装或检查"设置"。 通过配置 LOB 应用作为组所需的安装，在向分配组的用户注册 HoloLens 后，该应用将自动下载到 HoloLens。

打开"开始"菜单并选择"**所有应用"。** 根据你拥有的应用数量，你可能需要使用"上页"**或"下**页"**按钮。**

若要验证应用在设备上安装，可以通过"设置""帐户""**** 访问工作或学校"来进行验证;选择帐户，然后选择"信息"按钮，然后向下滚动以查看从  ->  ****  ->  **** MDM**** 应用到设备的不同配置和应用。

若要验证 Intune 中的安装，请导航到[MEM 门户](https://endpoint.microsoft.com/#home)应用  ->  ****->**应用**  -> *NameOfYourApp*  ->  **设备安装状态**页。

查看更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>验证 Dynamics 365 指南

HoloLens 上的 Guides 应用有一些创作和操作模式。 在操作指南之前，你需要完成指南的创作。

### <a name="authoring-the-guide"></a>创作指南

我们无需为此快速验证做很多工作。 只需选择你在电脑上准备的指南。 你需要定位 [指南](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)，以便快速验证你可使用全息定位标记。 之后，你应该 [放置你的步骤和模型](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> 你将需要 **Authoring** 角色才能登录到电脑，并创作 HoloLens。 接线员角色是只读的，并且无法访问电脑应用。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>操作指南

全息影像就位后，你可以测试操作指南。 
- 选择 **运算符模式**
- 单击指南的步骤。

有关如何操作指南的更深入指导，请查看以下资源：

[Dynamics 365 指南中的操作指南概述](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[使用"步骤"卡片作为 Dynamics 365 Guides 中的运算符进行定向](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接的部署 - 维护](hololens2-corp-connected-maintain.md)
