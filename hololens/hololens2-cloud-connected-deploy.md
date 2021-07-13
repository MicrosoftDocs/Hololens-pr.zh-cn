---
title: 部署指南–云连接 HoloLens 2 大规模部署与远程协助部署
description: 了解如何通过云连接网络验证 HoloLens 设备的注册和远程协助。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635171"
---
# <a name="deploy---cloud-connected-guide"></a>部署-云连接指南

完成所有配置后，应准备好分发设备。 不过，现在您应该首先验证您的设置。 首先，应验证 Azure AD 联接和 MDM 注册过程，然后验证是否可以发出远程协助呼叫。

## <a name="enrollment-validation"></a>注册验证

现在，所有内容都已正确配置 Azure AD 和 MDM 注册，接下来应该是一个快照。 &#39;要求 Wi-Fi 连接和 HoloLens 设备，以及以前配置的 AAD 用户帐户之一。

如果设备目前处于出厂设置状态&#39;t，现在是 [刷新设备](/hololens/hololens-recovery#clean-reflash-the-device)的好时机。

1. 设备进入 OOBE 后，您&#39;需要开始交互，并按照提示进行操作。 
1. 当系统询问 **Who 拥有此 HoloLens** 时，将会出现严重提示？ 选择 **"我的工作" 或 "学校拥有"** ，然后输入 Azure AD 帐户凭据。
1. 注册成功后，将提示您&#39;设置 PIN。 此 PIN 对于此用户是唯一的。 系统还会提示你进行 Iris 扫描、语音数据和遥测设置，最后&#39;可以了解如何打开 "开始" 菜单并完成 OOBE。
1. 进入混合现实后，使用刚刚学习的 **开始手势** 打开 "开始"菜单。
1. 选择 **设置** 应用，并选择 "**系统"。** 你&#39;的第一条信息是你的设备名称，HoloLens 2 设备的名称将为 HoloLens， &quot; &quot; 后跟六个字符串。
1. 记下此名称。

![HoloLens 2 设置-关于](./images/hololens2-settings-about.jpg)

7. 可以验证设备是否已成功注册到设置应用内的 Azure AD 中。 从 **设置** 选择 "**帐户**" "  ->  **访问工作或学校**"。 在此屏幕上，可以通过查看 &quot; 连接到 _nameofAAD_&#39;s Azure AD 来验证是否已成功注册。 通过 _yourusername_ @ _nameofAAD_. onmicrosoft.com 连接 &quot; 。


若要验证设备是否已 Azure AD 联接，我们可以从[Azure 门户](https://portal.azure.com/#home)Azure Active Directory 设备 "" 所有设备 "中检查 Azure Active Directory  ->    ->    ->  ，并搜索设备名称。 &#39;可以看到该设备是 Azure Active Directory 的一部分。


![Azure Active Directory-设备](./images/aad-enrollment.png)

接下来&#39;需要登录到[Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)。 登录并选择 " **设备** "，然后选择 " **所有设备**"。 可从此处搜索 HoloLens 设备&#39;的名称。 你应该能够看到你在 Intune 上列出的 HoloLens。

![Intune-设备](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>远程协助呼叫验证

&#39;ve 验证你的设备是否已注册到 AAD 和 MDM 后，就&#39;了下一次测试远程协助呼叫。 对于此验证，&#39;需要具有 HoloLens 设备和 Windows 10 pc，以及计算机的第二个 Azure AD 用户帐户。

此验证步骤将假定你之前已完成了上一次验证步骤，并且你的设备已注册，并且你的 Azure AD 用户在设备上。


1. 如果计算机上尚未安装 Microsoft Teams，则可以在[此处下载 Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。
2. 使用第二个 Azure AD 用户帐户（而不是当前登录的 HoloLens）登录 Teams。 登录到你的电脑后，你将可以接收呼叫。
3. 解锁 HoloLens 并登录。
4. 若要启动远程协助应用，请打开 " **开始" 菜单** ，然后选择 " **远程协助**"。 远程协助不仅捆绑为收件箱应用，还会固定到 HoloLens 2&#39;s "开始" 菜单。 在不&#39;的事件中，会看到它固定到 "开始"菜单中，然后打开 "**所有应用**" 列表以查找。
5. 远程协助启动后，它应通过 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 确定设备的用户，并登录到该应用。
6. 在应用中，选择 " **搜索** "，然后搜索计算机上的第二个用户。 选择要开始呼叫的用户。
7. 在电脑上，回答呼叫。

恭喜，你&#39;ve 已成功连接，并且在远程协助呼叫上。 请确保尝试特定的远程协助功能，如使用：

- [墨迹批注](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [在混合现实中共享文件和视图](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在另一个 HoloLens 应用中获取帮助](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>下一步

> [!div class="nextstepaction"]
> [云连接部署-维护](hololens2-cloud-connected-maintain.md)