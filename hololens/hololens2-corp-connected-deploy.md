---
title: 部署指南–企业连接 HoloLens 2 与 Dynamics 365 Guides 部署
description: 了解如何通过 Dynamics 365 Guides 在公司连接的网络上设置 HoloLens 2 设备的部署。
keywords: HoloLens，管理，公司连接，Dynamics 365 Guides，AAD，Azure AD，MDM，移动设备管理
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637056"
---
# <a name="deploy---corporate-connected-guide"></a>部署-企业连接指南

每个部署的一个重要部分是确保在测试部署之前正确设置部署，以确保对最终用户的流畅体验。

由于我们要通过 MDM 部署 Wi-Fi 证书，因此，我们需要在打开的 Wi-Fi 网络或不需要该证书的网络上设置 HoloLens 并注册设备。 在 HoloLens 完成 OOBE 并注册后，设备将接收先前配置的网络证书和 LOB，同时我们能够验证设备是否已收到这两者。

之后，你将可以确认是否可以编写和运行测试指南。

## <a name="enrollment-validation"></a>注册验证

现在，所有内容都已正确配置 Azure AD 和 MDM 注册，接下来应该是一个快照。 需要 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 Azure AD 用户帐户之一。

如果设备当前处于出厂设置状态，现在就可以 [刷新设备](/hololens/hololens-recovery#clean-reflash-the-device)了。

1. 设备进入 OOBE 后，将需要开始交互并按照提示进行操作。

2. 连接开放 Wi-Fi 网络，无需证书即可加入 Wi-fi。 这将允许设备下载初始设置后在组织的 Wi-Fi 上使用的证书。

3. 当系统询问 **Who 拥有此 HoloLens** 时，将会出现严重提示？ 选择 **"我的工作" 或 "学校拥有"** ，然后输入 Azure AD 帐户凭据。

4. 注册成功后，系统将提示你设置 PIN。 此 PIN 对于此用户是唯一的。 系统还会提示你输入 Iris 扫描、语音数据和遥测设置，最后，你将能够了解如何打开 "开始" 菜单并完成 OOBE。

5. 在混合现实家里，使用刚刚学习的 **开始手势** 打开 "开始"菜单。

6. 选择 **设置** 应用，并选择 "**系统**"。 你将看到的第一条信息是你的设备名称，你的 HoloLens 2 设备将为 &quot; HoloLens， &quot; 后跟六个字符串。

7. 记下此名称。

    ![HoloLens 2 设置屏幕](./images/hololens2-settings-about.jpg)

8. 验证设备是否已成功加入到 Azure AD。 有两种方法：

    1.  设置应用。 从 **设置** 选择 "**帐户**" "  ->  **访问工作或学校**"。 在此屏幕中，可以通过查看 &quot; 连接到 nameofAAD&#39;s Azure AD 来验证是否已成功注册。 通过连接 *yourusername@nameofAAD.onmicrosoft.com* 。 这将验证是否已将你的设备加入到你的组织&#39;Azure AD。

    1. [Azure 门户](https://portal.azure.com/#home)。 中转到 **Azure Active Directory**  ->  **设备**""  ->  **所有设备**"，然后搜索设备名称。 在 "联接类型" 下，它将显示为 "Azure AD 联接"。
        ![验证 Azure AD 中的联接类型](./images/hololens2-devices-all-devices.png)

9. 验证你的设备是否已注册 MDM。 有两种方法：

    1. 在 **设置** 中，选择 "**帐户**" "  ->  **访问工作或学校**"。 在此屏幕中，可以通过查看 &quot; 连接到 nameofAAD&#39;s Azure AD 来验证是否已成功注册。 通过连接 *yourusername@nameofAAD.onmicrosoft.com* 。 通过选择 " &quot; 连接到 nameofAAD&#39;s Azure AD，从该访问工作或学校帐户。 连接方式 yourusername@nameofAAD.onmicrosoft.com &quot; 并选择 "**信息**" 按钮。

    1. [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。 登录并选择 "  **设备**  "，然后选择 "  **所有设备**"。 可从此处搜索 HoloLens 设备&#39;的名称。 你应该能够看到你在 Intune 上列出的 HoloLens。

        ![验证 Azure AD 中的 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi 证书验证

现在，设备应收到 Wi-Fi 证书。 可以执行的最简单验证是尝试连接到&#39;为其收到证书的 Wi-Fi 连接。 打开 **设置** 应用并导航到 "**网络 &amp; Internet**  ->  **wi-fi** "，并选择 "wi-fi 连接"。 连接后，请打开 Microsoft Edge 应用并确认你可以导航到网站。

若要确认是否已在设备上收到证书，可以使用 [证书管理器](/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>验证 LOB 应用安装

若要查看托管应用的安装进度，你可以查看应用是否已安装或检查设置。 通过将 LOB 应用配置为组所需的安装，在向分配的组中的用户注册 HoloLens 后，应用将自动下载到 HoloLens 中。

打开 "开始"菜单，并选择 "**所有应用**"。 你可能需要使用 **page up** 或 **page down** 按钮，具体取决于你所拥有的应用数。

若要在设备上验证应用的安装，你可以通过 **设置**  ->  **帐户**  ->  **访问工作或学校** 进行操作; 选择帐户，然后选择 "**信息**" 按钮，然后向下滚动查看从 MDM 应用到设备的不同配置和应用。

若要从 Intune 验证安装，请导航到 "[内存门户](https://endpoint.microsoft.com/#home)  ->  **应用**-> 所有 **应用**"  -> *TheNameOfYourApp*"  ->  **设备安装状态**" 页。

查看详细信息： [Intune 应用部署 HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>验证 Dynamics 365 Guides

HoloLens、创作和操作的指南应用模式有多种。 在操作之前，需要完成编写指南。

### <a name="authoring-the-guide"></a>创作指南

对于此快速验证，我们不需要这么做。 只需选择你在电脑上准备的指南即可。 你需要 [定位指南](/dynamics365/mixed-reality/guides/hololens-app-anchor)，以便快速验证你可以使用全息锚。 之后，应 [放置步骤和模型](/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> 你将需要 **创作** 角色才能登录到电脑和 HoloLens 上的作者。 操作员角色为只读，不能访问电脑应用。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>操作指南

全息影像准备就绪后，即可测试操作指南。 
- 选择 **操作员模式**
- 单击指导的步骤。

若要深入了解如何操作指南，请查看以下资源：

[Dynamics 365 Guides 中的指南操作概述](/dynamics365/mixed-reality/guides/operator-overview)

[在 Dynamics 365 Guides 中，使用步骤卡作为操作员](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接部署-维护](hololens2-corp-connected-maintain.md)
