---
title: 部署指南 - 企业连接的 HoloLens 2 与 Dynamics 365 指南 - 配置
description: 了解如何设置配置，以使用 Dynamics 365 指南通过企业连接网络部署 HoloLens 2 设备。
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448516"
---
# <a name="configure---corporate-connected-guide"></a>配置 - 企业连接指南

## <a name="azure-users-and-groups"></a>Azure 用户和组

Azure 和 Intune 通过该扩展使用用户和组来帮助分配配置和许可证。 为了验证此部署流并能够检查你能否创作和操作指南，&#39;需要用户帐户。

我们可以创建一个专门用于分配许可证的用户组。

如果尚未&#39;用户组中的两个 Azure AD 帐户，可以使用;以下是以下快速入门指南：

- [如何创建用户](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [向组添加用户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组
- [配置 Azure AD 以允许](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 用户组加入设备 – 确保新用户组具有将设备注册到 Azure AD 的权限

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 上的自动注册

若要获得流畅而无缝的体验，可以设置 Azure Active Directory 加入 (AADJ) 以及自动注册到适用于 HoloLens 2 设备的 Intune。 这允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册，将设备注册到 MDM 中。

通过使用 [Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几个页面，直到我们可以选择获取高级试用版。 你可能会注意到 Azure Active Directory Premium 1 和 2 - 对于自动注册 P1 已足够。 我们可以选择 Intune 并选择用户作用域进行自动注册，然后选择之前创建的组。

有关完整详细信息和步骤，请阅读如何为 [Intune 启用自动注册的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="corporate-wi-fi-connectivity"></a>企业Wi-Fi连接

公司Wi-Fi连接通常需要使用 HoloLens 2 的客户进行基于证书的身份验证。 你需要使用与 MDM 解决方案集成的简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。 使用 Intune 部署Wi-Fi配置文件、证书和代理设置，为最终用户打造无缝体验。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>部署证书和Wi-Fi配置文件

若要通过 Microsoft Endpoint Manager 部署证书和配置文件，请按照以下步骤操作：

1. 为每个根证书和中间证书创建配置文件 (请参阅创建 [受信任的](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) 证书配置文件) 。 其中每个配置文件必须具有包含 DD/MM/YYYYY 格式到期日期的说明。 

    > [!CAUTION]
    > **不会部署没有过期日期的证书配置文件**。

2.  为每个 SCEP 或 PKCS 证书创建一个配置文件（请参阅[创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。 

    > [!CAUTION]
    > **将不会部署无到期日期的证书配置文件。**

    > [!Note]
    > 由于 HoloLens 2 被视为共享设备，即每个设备有多个用户，因此建议在可能的情况下部署设备证书，而不是Wi-Fi身份验证的用户证书。

3.  创建适用于企业网络Wi-Fi配置文件 ([Windows 10](https://docs.microsoft.com/intune/wi-fi-settings-windows) 及更高版本设备的 WLAN 设置) 。 在Wi-Fi配置文件中，可以选择在组织中使用代理设置。
 
    你的选项：
    - **无**：未配置代理设置。
    - **手动配置**：输入代理服务器 **IP 地址** 及其 **端口号**。
    - **自动配置**：输入指向 PAC (PAC) 配置的 URL。 例如，输入 *http://proxy.contoso.com/proxy.pac* 。

    有关 PAC 文件详细信息，请参阅代理 [自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (打开非 Microsoft 站点) 。
 
    > [!Note]
    > 建议尽可能将 Wi-Fi 配置文件分配给设备组，而不是用户组。
     
    > [!Tip]
    > 此外，还可从公司网络上的 Windows 10 电脑导出有效的 Wi-Fi 配置文件。 此导出将创建包含所有当前设置的 XML 文件。 然后，将此文件导入到 Intune 中，并将其用作 HoloLens 2 设备的 Wi-Fi 配置文件。 请参阅 [导出和Wi-Fi Windows 设备的自定义设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [将](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 设备配置文件分配给 HoloLens 设备组。

2.  [在](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune 中监视设备配置文件。

如果配置文件中Wi-Fi问题，Wi-Fi [Intune 中的设备配置文件疑难解答](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>公司连接时的外部 Internet 访问疑难解答
当服务尝试不通过设置代理时，它们可能会尝试通过防火墙进行连接。 你可以将终结点特定项列表添加到防火墙规则中，以解决这些问题。

如果在防火墙端口被阻止，请为 HoloLens 启用 [一](https://docs.microsoft.com/hololens/hololens-offline) 些常见终结点。

还可以启用指南特定端口：连接到 Microsoft Dynamics CRM Online 所需的 Internet[访问Microsoft Dynamics CRM Online。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>应用部署

通过 MDM 部署 LOB 应用是一种易于缩放的方法，可在注册已创建的组时自动部署到设备。

如果你仍在开发应用或还没有应用，可以使用 MRTK 示例中心的示例应用。 此示例应用已准备就绪，无需使用 Unity 或 Visual Studio。 [下载 MRTK 示例示例应用](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

如果你希望使用自己的应用或对混合现实的应用开发感兴趣，请随时查看我们的 [混合现实开发人员文档](https://docs.microsoft.com/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens 设备的系统要求基于应用内部版本的体系结构。 HoloLens 2 设备使用ARM体系结构。 在 Visual Studio 中生成应用时，请确保你已针对设备选择了正确的体系结构，并包括任何所需的依赖项。

> [!IMPORTANT]
> 部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配给打算使用该应用的同一组，否则无法正确安装。

### <a name="upload-and-assign-the-app"></a>上载和分配应用

1. 导航到 [MEM 管理中心](https://endpoint.microsoft.com/#home)。

2. 选择 **"**  ->  **应用""所有**应用"，然后选择 **"+ 添加"** 按钮。

3. 在"其他"下方，**选择"业务线应用"。** 单击 **"选择"。**

4. 选择应用包文件，这是 APPXBUNDLE 文件，或者在我们的示例中，应用是_MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle。_

5. 你将收到缺少依赖项的通知。 在这种情况下，我们需要上载_Microsoft.VCLibs.ARM.14.00.appx。_ 在"选择文件 **"下搜索它**。

6. 选择“确定”。

7. 下一个屏幕中，必填字段将被自动填充。 选择**下一步** 。

8. 在"必需"下，添加我们之前创建的组，使此应用成为组必需的。 这会使应用自动下载到组中注册的设备。 选择**下一步** 。

9. 选择**创建**。

阅读更多： [在 Microsoft Intune 中向组分配应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>设置指南：应用程序许可证、dataverse 和创作

为了使用 Dynamics 365 Guides，你需要做一些准备工作。 我们需要在三个方面做好准备;用户、dataverse 和参考线本身。

### <a name="users-and-application-licenses"></a>用户和应用程序许可证

对于使用指南的人，他们将需要使用 Azure AD 帐户，我们之前在本指南中设置了该帐户。

你还需要将 Dynamics 365 Guides 许可证分配给你创建的用户。 你将从 [Microsoft 365 管理中心进行此操作](https://admin.microsoft.com/AdminPortal/Home)。 此外，将许可证分配给主 Azure 帐户。

按照 [包含图片的](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 简短指南，查看应用应用程序许可证的分步说明。

### <a name="set-up-the-dataverse"></a>设置 Dataverse

为了设置 [生产环境，](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 您需要满足两个先决条件。 你必须具有[**系统管理员**](https://docs.microsoft.com/power-platform/admin/database-security)角色，并且必须具有****[**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)许可证 (或[**Dynamics 365 Guides**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)许可证，其中包含 Power Apps 许可证) 。 如果按照本指南创建 Azure AD，则满足系统管理员的角色要求。 我们还在上一步中分配了指南许可证。

在本指南 [中，创建 Microsoft Dataverse 环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：

1. 首先使用 [Power Platform 管理中心并](https://admin.powerplatform.microsoft.com/environments) 创建新环境。
2. 创建新环境**时，对于****"类型**"，&#39;选择"生产 **"。**
3. 是否必须切换为此 **环境创建数据库？**  选项为 **"是"。**
4. 在"  **添加数据库"**  对话框中，将"  **启用 Dynamics 365 应用"**  选项设置为  **"是"。**

你将希望增加 dataverse 中项目的最大文件大小。 增加最大文件大小将允许你上载更大的 3D 模型或视频文件，你将在指南中稍后使用这些文件。 按照简短指南 [更改最大上载文件大小](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最后，您需要安装和 [配置解决方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 在[Power Platform 管理](https://admin.powerplatform.microsoft.com/environments)中心中，选择 **"资源**   \ &gt; **""Dynamics 365**应用"，在列表中选择 **"Dynamics 365 指南**"，然后选择"安装 **"。**  

你需要 [添加 Guides 安全角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用这些应用。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>通过创作在电脑上创建测试指南

创建指南时，你将始终在电脑上启动。 创建步骤、选择模型以及如何定位指南。 然后，在 HoloLens 设备上将指南内容置于创作模式下。 对于本指南，我们建议使用最少的步骤和模型制作一个简短的测试指南。

如果你想要开始学习有关"指南"的创作，请从此处的创作 [概述开始](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)。 或者，若要获取快速跟踪概述，请观看此简短视频。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>可选：展台模式

展台模式是一种模式，IT 管理员可以将"开始"菜单的 UI 配置为只显示单个应用或选择的应用。 展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台中排除某些用户仍允许他们访问常规的"开始"菜单。

展台模式具有许多不同的变量，在作用域和配置中都可以设置，还可以将展台部署到 HoloLens 的方法。 由于所有这些变量，展台模式将作为本指南的可选模式__ 离开，并且不会重新访问。 如果你相信有业务需要将可用应用限制为用户，或者希望了解更多信息，那么请随意了解如何将 [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)设置为展台。

## <a name="optional-wdac"></a>可选：WDAC

WDAC 允许 IT 管理员配置其设备以阻止在设备上启动应用。 这不同于设备限制方法（如展台模式）的方法，即向用户显示隐藏设备上应用的 UI，但仍可以启动它们。 实现 WDAC 时，应用仍显示在"所有应用"列表中，但 WDAC 会阻止设备用户启动这些应用和进程。

有关详细信息，请参阅使用 WDAC 和 Windows PowerShell使用 Microsoft Intune 允许或阻止 [HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。

[Windows Defender 应用程序控制 - WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接的部署 - 部署](hololens2-corp-connected-deploy.md)