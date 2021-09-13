---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 部署
description: 了解如何验证通过云Remote Assist HoloLens设备注册和注册。
keywords: HoloLens、管理、云连接、Remote Assist、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032117"
---
# <a name="deploy---cloud-connected-guide"></a>部署 - 云连接指南

配置所有内容后，应准备好分发设备。 但是，现在应首先验证设置。 首先Azure AD联接和 MDM 注册过程，然后验证Remote Assist调用。

## <a name="enrollment-validation"></a>注册验证

现在，所有内容都正确配置了Azure AD注册和 MDM 注册，其余部分现在应该是一个快照。 你&#39;需要一Wi-Fi连接HoloLens设备，以及以前配置的 AAD 用户帐户之一。

如果设备当前&#39;处于出厂设置状态，则现在是重新 [运行设备的不错时间](/hololens/hololens-recovery#clean-reflash-the-device)。

1. 设备进入 OOBE 后，&#39;需要开始交互并遵循提示。 
1. 当系统要求你拥有此Who时，关键 **提示HoloLens？** 选择 **"我的工作或学校拥有它"，Azure AD** 帐户凭据。
1. 注册成功后，&#39;系统会提示你设置 PIN。 对于此用户，此 PIN 对于此设备是唯一的。 系统还会提示你输入 Iris 扫描、语音数据和遥测设置，最后&#39;了解如何打开开始菜单并完成 OOBE。
1. 进入混合现实主页后，使用刚"开始"菜单 **的"** 开始"手势打开应用程序。
1. 选择 **"设置** 应用"，然后选择"系统 **"。** 你将看到的第一&#39;是设备名称，对于设备HoloLens 2为 &quot; HOLOLENS- 后跟 &quot; 一个六个字符字符串。
1. 记下此名称。

![HoloLens 2 设置 - 关于。](./images/hololens2-settings-about.jpg)

7. 可以验证设备是否已成功注册到 Azure AD 应用设置注册。 从 **设置选择"****帐户**  ->  **访问工作或学校"。** 在此屏幕中，可以通过在"已连接到 &quot; _nameofAAD"&#39;验证_ Azure AD。 通过 _yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; 连接。


若要验证设备是否Azure AD已加入Azure Active Directory，可以从"Azure 门户Azure Active Directory设备"中检查设备名称，[](https://portal.azure.com/#home)并搜索  ->    ->    ->  设备名称。 你可以&#39;设备是设备Azure Active Directory。


![Azure Active Directory - 设备。](./images/aad-enrollment.png)

接下来&#39;需要登录到 Microsoft Endpoint Manager[管理中心](https://endpoint.microsoft.com/#home)。 登录并选择"**设备"，然后选择**"**所有设备"。** 可在此处搜索设备HoloLens&#39;名称。 应能够看到 Intune 上HoloLens列表。

![Intune - 设备。](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist调用验证

验证&#39;AAD 和 MDM 中注册设备后，&#39;测试调用Remote Assist时间。 对于此验证&#39;需要具有 HoloLens 设备和 Windows 10 电脑，以及电脑的第二Azure AD用户帐户。

此验证步骤将假定你之前已完成最后一个验证步骤，并且设备已注册，Azure AD用户位于设备上。


1. 如果尚未在电脑上Microsoft Teams，可以在此处下载[Teams。](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. 使用Teams当前登录到Azure AD帐户的第二个用户帐户登录HoloLens。 登录电脑后，即可接收呼叫。
3. 解锁HoloLens并登录。
4. 若要启动Remote Assist应用，请打开"**开始"菜单并选择****Remote Assist。** Remote Assist不仅捆绑为收件箱应用，还固定到HoloLens 2&#39;菜单。 如果看不到&#39;已固定到 "开始"菜单，请打开"所有应用"列表来查找它。 
5. 启动Remote Assist，它应通过 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 标识设备的用户并登录到应用。
6. 在应用中，选择" **搜索** "，然后搜索电脑上的第二个用户。 选择用户以开始呼叫。
7. 在电脑上，接听电话。

祝贺你，&#39;已成功连接并正在远程协助呼叫。 请确保试用特定的远程辅助功能，例如使用：

- [墨迹书写批注](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [在混合现实中共享文件和视图](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在另一个应用HoloLens帮助](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [云连接部署 - 维护](hololens2-cloud-connected-maintain.md)