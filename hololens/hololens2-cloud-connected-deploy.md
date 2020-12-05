---
title: 部署指南-云通过远程辅助功能在扩展时连接到 HoloLens 2 部署
description: 如何通过连接到云的网络上的 HoloLens 设备验证注册和远程协助
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196273"
---
# 部署-云连接指南

既然已配置所有内容，您就可以分发设备了。 但是，这是你应该首先验证你的设置。 首先应验证 AAD 联接和 MDM 注册过程，然后验证是否可以放置远程协助呼叫。

## 注册验证

现在，所有为 AAD 和 MDM 注册配置的内容都应该是快照。 你&#39;需要 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 AAD 用户帐户之一。

如果你的设备目前&#39;t 处于工厂设置状态，现在可以将 [设备 reflash](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。

1. 一旦设备在 OOBE 中，你&#39;需要开始交互并遵循提示。 
1. 当系统询问**谁拥有此 HoloLens**时，关键提示将是什么？ 选择 **"我的工作或学校拥有它"** ，然后输入 AAD 帐户凭据。
1. 注册成功后，系统将提示你&#39;设置 PIN。 此用户的此设备独有。 你还会收到虹膜扫描、语音数据和遥测设置的提示，最后，你&#39;能够了解如何打开 "开始" 菜单和完成 OOBE。
1. 在混合现实开始时，请使用刚刚学习的 " **开始** " 菜单打开 "开始" 菜单。 
1. 选择 " **设置** " 应用，然后选择 " **系统"。** 你&#39;看到的第一条信息是你的设备名称，而你的 HoloLens 2 设备的第一条信息将是 &quot; hololens， &quot; 后跟6个字符的字符串。 
1. 记下此名称。

![HoloLens 2 设置-关于](./images/hololens2-settings-about.jpg)

7. 你可以在 "设置" 应用中验证你的设备是否已成功注册到 AAD 中。 从 "**设置**" 中选择 "**帐户**  ->  **访问工作或学校**"。 在此屏幕上，你可以通过查看已 &quot; 连接到 _nameofAAD_&#39;s Azure AD 来验证是否已成功注册。 通过_用户名_ @ _nameofAAD_ &quot; 连接。

若要验证设备是否已加入 AAD，我们可以从[azure Portal](https://portal.azure.com/#home)  ->  **azure active directory**设备中检查所有设备的 azure active directory  ->  **Devices**  ->  **All devices** ，并搜索设备名称。 你&#39;能够看到该设备是 Azure Active Directory 的一部分。

![Azure Active Directory-设备](./images/aad-enrollment.png)

接下来，你&#39;需要登录到 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com/#home)。 登录并选择 " **设备** "，然后选择 " **所有设备**"。 在此处，您可以搜索您的 HoloLens 设备&#39;s 名称。 你应该能够查看 Intune 上列出的 HoloLens。

![Intune-设备](./images/endpoint-all-devices-enrolled.png)

## 远程协助呼叫验证

一旦你&#39;验证你的设备已在 AAD 和 MDM 中注册，它将&#39;s 次进行测试远程协助呼叫。 对于此验证，你&#39;需要安装 HoloLens 设备和 Windows 10 电脑，以及电脑的第二个 AAD 用户帐户。

此验证步骤将假定你之前已完成最后一个验证步骤，并且你的设备已注册，并且你的 AAD 用户位于设备上。

1. 如果你未在电脑上安装 Microsoft 团队&#39;则可以在 [此处下载团队](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。
2. 使用当前登录到 HoloLens 的第二个 AAD 用户帐户登录团队。 登录电脑后，您就可以接收呼叫了。
3. 解锁 HoloLens 并登录。
4. 若要启动远程协助应用，请打开 " **开始" 菜单** ，然后选择 " **远程协助**"。 远程协助不仅捆绑为收件箱应用，还固定到 HoloLens 2&#39;s "开始" 菜单。 在事件中，你不&#39;t 看到它固定到 "开始" 菜单，然后打开 " **所有应用** " 列表以查找它。
5. 远程协助启动后，它应通过 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 确定设备的用户并登录到该应用。
6. 在应用内，选择 " **搜索** "，然后搜索电脑上的第二个用户。 选择要开始呼叫的用户。
7. 您的电脑接听通话。

恭喜，您&#39;已成功连接，并且在您的远程协助呼叫中。 请确保尝试使用特定的远程协助功能，例如使用：

- [墨迹书写批注](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [在混合现实中共享文件和视图](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在其他 HoloLens 应用中获取帮助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 下一步

> [!div class="nextstepaction"]
> [云连接部署-维护](hololens2-cloud-connected-maintain.md)