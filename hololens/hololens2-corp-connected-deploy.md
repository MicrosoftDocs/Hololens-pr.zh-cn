---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 部署
description: 了解如何使用 HoloLens 2 企业联网网络设置设备部署Dynamics 365 Guides。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032112"
---
# <a name="deploy---corporate-connected-guide"></a>部署 - 企业连接指南

每个部署的一个重要部分是确保在自己测试部署之前正确设置部署，以确保最终用户获得顺畅的体验。

由于我们要通过 MDM 部署 Wi-Fi 证书，因此首先需要在开放 Wi-Fi 网络或不需要证书的网络上设置 HoloLens 并注册设备。 完成HoloLens OOBE 和注册后，设备将收到之前配置的网络证书和 LOB，并且我们可以验证设备是否同时收到这两者。

之后，你将能够确认可以创作和操作测试指南。

## <a name="enrollment-validation"></a>注册验证

现在，所有内容都正确配置了Azure AD注册和 MDM 注册，其余部分现在应该是一个快照。 需要一个Wi-Fi连接HoloLens设备，以及以前配置Azure AD用户帐户之一。

如果设备当前未处于出厂设置状态，那么现在是重新 [运行设备的不错时间](/hololens/hololens-recovery#clean-reflash-the-device)。

1. 设备进入 OOBE 后，需要开始交互并遵循提示。

2. 连接连接到Wi-Fi加入 Wi-Fi 的开放网络。 这将允许设备下载证书，以在初始设置后Wi-Fi组织证书。

3. 当系统要求你拥有此Who时，关键 **提示HoloLens？** 选择 **"我的工作或学校拥有它"，Azure AD** 帐户凭据。

4. 注册成功后，系统会提示你设置 PIN。 对于此用户，此 PIN 对于此设备是唯一的。 系统还会提示你输入 Iris 扫描、语音数据和遥测设置，最后，你将了解如何打开开始菜单并完成 OOBE。

5. 进入混合现实主页后，使用刚"开始"菜单 **的"** 开始"手势打开该应用。

6. 选择设置 **应用**，然后选择"系统 **"。** 你将看到的第一条信息是设备名称，对于设备HoloLens 2为 &quot; HOLOLENS- 后跟 &quot; 一个六个字符字符串。

7. 记下此名称。

    ![HoloLens 2 设置屏幕。](./images/hololens2-settings-about.jpg)

8. 验证设备是否成功加入 Azure AD。 有两种方法：

    1.  设置应用。 从 **设置** 选择"**帐户**  ->  **访问工作或学校"。** 在此屏幕中，可以通过看到"连接到 &quot; nameofAAD"&#39;验证Azure AD。 通过 连接 *yourusername@nameofAAD.onmicrosoft.com* 。 这将验证设备已加入组织&#39;Azure AD。

    1. [Azure 门户](https://portal.azure.com/#home)。 转到  ->    ->  **Azure Active Directory"所有设备"，** 并搜索设备名称。 在"联接类型"下，它将显示为"Azure AD联接"。
        ![验证"联接类型"Azure AD。](./images/hololens2-devices-all-devices.png)

9. 验证设备是否注册了 MDM。 有两种方法：

    1. 从 **设置，** 选择"**帐户**  ->  **访问工作或学校"。** 在此屏幕中，可以通过看到"连接到 &quot; nameofAAD"&#39;验证Azure AD。 通过 连接 *yourusername@nameofAAD.onmicrosoft.com* 。 在此"访问工作或学校帐户"中，选择"连接到 &quot; nameofAAD"&#39;Azure AD。 通过 连接 yourusername@nameofAAD.onmicrosoft.com &quot; 并选择"信息 **"** 按钮。

    1. [Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com/#home)。 登录并选择"**设备"，然后选择**"**所有设备"。** 可在此处搜索设备HoloLens&#39;名称。 应能够看到 Intune 上HoloLens列表。

        ![验证由 Intune 在 Azure AD。](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi证书验证

现在，设备应已收到Wi-Fi证书。 最简单的验证是尝试连接到已Wi-Fi证书&#39;的连接。 打开 **设置** 应用，导航到"网络 **&amp; Internet**  ->  **Wi-Fi"** 并选择 Wi-fi 连接。 连接后，打开Microsoft Edge应用并确认可以导航到网站。

若要确认你已收到设备上证书，可以使用证书 [管理器](/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>验证 LOB 应用安装

若要查看托管应用的安装进度，请查看该应用是否已安装或检查设置。 将 LOB 应用配置为组所需的安装后，向分配HoloLens中的用户注册该 LOB 应用后，该应用将自动下载到 HoloLens。

打开""开始"菜单并选择"**所有应用"。** 根据拥有的应用数，可能需要使用"向上"或"**下一页"** 按钮。 

若要验证设备上应用的安装，可以通过 **"设置** 帐户访问工作或学校"来验证安装;选择帐户，然后选择"信息"按钮，然后向下滚动以查看从  ->    ->  MDM应用到设备的不同配置和应用。

若要从 Intune 验证安装，请导航到 [MEM](https://endpoint.microsoft.com/#home)门户"应用  ->  "->"所有应用  -> *""NameOfYourApp*  ->  **设备安装状态"** 页。

有关详细信息，请参阅[Intune 应用部署HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>验证Dynamics 365 Guides

在应用、创作和操作方面，HoloLens指南应用的模式。 在操作指南之前，需要完成创作指南。

### <a name="authoring-the-guide"></a>创作指南

对于此快速验证，我们不需要执行太多操作。 只需选择电脑上准备的指南。 需要锚定指南 [，](/dynamics365/mixed-reality/guides/hololens-app-anchor)以便快速验证，可以使用全息定位点。 然后，应 [放置步骤和模型](/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> 需要"**创作"** 角色才能登录到电脑，并创作HoloLens。 操作员角色是只读的，无法访问电脑应用。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>操作指南

全息影像就位后，可以测试操作指南。 
- 选择 **运算符模式**
- 单击指南的步骤。

有关如何操作指南的更深入的指导，请查看以下资源：

[有关在 Dynamics 365 Guides 中操作指南的概述](/dynamics365/mixed-reality/guides/operator-overview)

[使用 Step 卡作为数据中的操作员Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>后续步骤 
> [!div class="nextstepaction"]
> [企业连接部署 - 维护](hololens2-corp-connected-maintain.md)
