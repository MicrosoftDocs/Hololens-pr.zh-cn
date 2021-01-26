---
title: 部署指南 – 通过远程协助大规模部署云连接的 HoloLens 2 - 部署
description: 了解如何通过云连接网络验证 HoloLens 设备的注册和远程协助。
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282933"
---
# 部署 - 云连接指南

现在，你已配置所有内容，你应该已准备好分发设备。 不过，现在应该先验证设置。 首先应验证 Azure AD 加入和 MDM 注册过程，然后验证能否进行远程协助呼叫。

## 注册验证

现在，已针对 Azure AD 和 MDM 注册正确配置了一切，其余部分现在应该可以贴靠了。 你需要&#39;连接Wi-Fi HoloLens 设备，以及之前配置的 AAD 用户帐户之一。

如果你的设备当前&#39;处于出厂设置状态，那么现在应该重新调整[设备。](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. 设备进入 OOBE 后，&#39;开始交互并遵循提示。 
1. 当系统询问谁拥有此**HoloLens**时，关键提示将是？ 选择 **我的工作或学校拥有它** ，然后输入你的 Azure AD 帐户凭据。
1. 注册成功后，&#39;提示你设置 PIN。 对于此用户，此 PIN 对于此设备是唯一的。 系统还会提示你进行虹膜扫描、语音数据和遥测设置，最后，&#39;了解如何打开"开始"菜单并完成 OOBE。
1. 进入混合现实主页后，使用刚学习的"开始"手势 **打开"开始** "菜单。
1. 选择" **设置"** 应用，然后选择 **"系统"。** 你将看到的第&#39;一条信息是设备名称，对于 HoloLens 2 设备，它将是 &quot; HOLOLENS，后跟 &quot; 一个六个字符字符串。
1. 记下此名称。

![HoloLens 2 设置 - 关于](./images/hololens2-settings-about.jpg)

7. 你可以验证设备在"设置"应用中是否成功注册了 Azure AD。 从 **"设置****"中选择**  ->  **"帐户访问工作或学校"。** 从此屏幕中，可以通过查看 Azure AD 中"已连接到 &quot; _nameofAAD"&#39;_ 验证是否成功注册。 通过_yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; 连接。


若要验证设备已加入 Azure AD，我们可以从[Azure](https://portal.azure.com/#home)门户 Azure Active Directory 设备所有设备检查  ->  **Azure Active Directory，** 并搜索  ->  ****  ->  **** 设备名称。 你可以&#39;设备是 Azure Active Directory 的一部分。


![Azure Active Directory - 设备](./images/aad-enrollment.png)

接下来&#39;登录 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。 登录并选择**设备**，然后选择 **"所有设备"。** 你可以在此处搜索 HoloLens&#39;名称。 你应该能够看到你的 HoloLens 列在 Intune 上。

![Intune - 设备](./images/endpoint-all-devices-enrolled.png)

## 远程协助呼叫验证

确认&#39;AAD 和 MDM 中注册设备后，&#39;测试远程协助呼叫。 对于此验证&#39;你需要拥有 HoloLens 设备和 Windows 10 电脑，以及电脑的第二个 Azure AD 用户帐户。

此验证步骤将假定你之前已完成最后一个验证步骤，并且你的设备已注册，并且你的 Azure AD 用户位于设备上。


1. 如果你的电脑上尚未安装 Microsoft Teams，可以在此处[下载 Teams。](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. 使用当前登录到 HoloLens 的第二个 Azure AD 用户帐户登录到 Teams。 登录电脑后，即可接收呼叫。
3. 解锁 HoloLens 并登录。
4. 若要启动远程协助应用，请打开 **"开始"菜单并选择****"远程协助"。** 远程协助不仅捆绑为收件箱应用，还固定到 HoloLens 2&#39;菜单。 如果看不到&#39;固定到"开始"菜单，请打开"所有 **应用** "列表来查找它。
5. 远程协助启动后，它应通过 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 标识设备用户并登录到应用。
6. 在应用中，选择 **"搜索** "，然后搜索电脑上的第二个用户。 选择用户以开始呼叫。
7. 从电脑应答呼叫。

恭喜，&#39;已成功连接并正在拨打远程协助电话。 请确保试用特定的远程协助功能，例如：

- [墨迹书写批注](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [在混合现实中共享文件和视图](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在另一个 HoloLens 应用中获取帮助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 下一步

> [!div class="nextstepaction"]
> [云连接部署 - 维护](hololens2-cloud-connected-maintain.md)