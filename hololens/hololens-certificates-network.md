---
title: 为 HoloLens 2 准备证书和网络配置文件
description: 了解如何在 HoloLens 2 混合现实设备上对网络的证书进行配置、使用、部署和疑难解答。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de9f2c4f136a26a5956ba8a8f3b9faba1e90ea66
ms.sourcegitcommit: 86dba9e8a5e25f0bf29f4c0580970c25c44b7359
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470050"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>为 HoloLens 2 准备证书和网络配置文件

基于证书的身份验证是使用 HoloLens 2 的客户的常见要求。 你可能需要证书才能访问 Wi-Fi、连接到 VPN 解决方案或访问组织中的内部资源。

由于 HoloLens 2 设备通常已加入 Azure Active Directory (Azure AD) 并且由 Intune 或其他 MDM 提供程序进行管理，因此你将需要使用简单证书注册协议 (SCEP) 或与你的 MDM 解决方案集成的公钥加密标准 (PKCS) 证书来部署此类证书。 

>[!NOTE]
> 如果没有 MDM 提供商，仍然可以通过 [Windows 配置设计器](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)中的[预配程序包](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages)或通过[证书管理员](https://docs.microsoft.com/hololens/certificate-manager)（转到 **“设置”>“更新和安全”>“证书管理员”**）部署证书。

## <a name="certificate-requirements"></a>证书要求
需要根证书才能通过 SCEP 或 PKCS 基础结构部署证书。 你的组织中的其他应用程序和服务可能还需要将根证书部署到 HoloLens 2 设备上。 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 连接要求
为了自动为设备提供企业网络所需的 Wi-Fi 配置，你需要一个 Wi-Fi 配置配置文件。 你可以配置 Intune 或其他 MDM 提供程序以将这些配置文件部署到你的设备。 如果你的网络安全要求设备是本地域的一部分，则你可能还需要评估 Wi-Fi 网络基础结构，以确保它与 HoloLens 2 设备兼容（HoloLens 2 设备仅加入 Azure AD）。

## <a name="deploy-certificate-infrastructure"></a>部署证书基础结构
如果未存在 SCEP 或 PKCS 基础结构，则需要准备一个。 若要支持使用 SCEP 或 PKCS 证书进行身份验证，则 Intune 需要使用[证书连接器](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)。

> [!NOTE]
> 将 SCEP 与 Microsoft CA 配合使用时，还必须配置[网络设备注册服务 (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

有关详细信息，请参阅[在 Microsoft Intune 中配置设备的证书配置文件](https://docs.microsoft.com/intune/certificates-configure)。

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署证书和 Wi-Fi/VPN 配置文件
若要部署证书和配置文件，请按照下列步骤进行操作：
1.  为每个根证书和中间证书创建一个配置文件（请参阅[创建受信任的证书配置文件](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)。）这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。 **将不会部署无到期日期的证书配置文件。**
1.  为每个 SCEP 或 PKCS 证书创建一个配置文件（请参阅[创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。 **将不会部署无到期日期的证书配置文件。**

    > [!NOTE]
    > 由于 HoloLens 2 将多个设备视为一个共享设备，并且每个设备上有多个用户，因此建议尽可能部署设备证书（而不是用户证书）进行 Wi-Fi 身份验证

3.  为每个公司 Wi-Fi 网络创建一个配置文件（请参阅 [Windows 10 和更高版本的设备的 Wi-Fi 设置](https://docs.microsoft.com/intune/wi-fi-settings-windows)）。 
    > [!NOTE]
    > 建议尽可能将 Wi-Fi 配置文件[分配](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)给设备组，而不是用户组。 

    > [!TIP]
    > 此外，还可从公司网络上的 Windows 10 电脑导出有效的 Wi-Fi 配置文件。 此导出将创建包含所有当前设置的 XML 文件。 然后，将此文件导入到 Intune 中，并将其用作 HoloLens 2 设备的 Wi-Fi 配置文件。 请参阅[导出和导入 Windows 设备的 Wi-Fi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

4.  为每个公司 VPN 创建一个配置文件（请参阅 [Windows 10 和 Windows Holographic 设备设置，使用 Intune 添加 VPN 连接](https://docs.microsoft.com/intune/vpn-settings-windows-10)）。

## <a name="troubleshooting-certificates"></a>证书疑难解答

如果你需要验证是否正确部署了证书，请使用设备上的[证书管理器](certificate-manager.md)验证你的证书是否存在。  


