---
title: 部署指南-通过 Dynamics 365 指南连接公司的 HoloLens 2-配置
description: 了解如何设置配置以使用 Dynamics 365 指南通过企业连接的网络部署 HoloLens 2 设备。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308167"
---
# <a name="configure---corporate-connected-guide"></a>配置-企业连接指南

## <a name="azure-users-and-groups"></a>Azure 用户和组

Azure 以及该扩展的 Intune 使用用户和组来帮助分配配置和许可证。 为了验证此部署流并能够检查是否可以创作和操作指南，你&#39;需要一个用户帐户。

我们可以将单个用户组专门用于分配许可证。

如果你不&#39;t 已经有权访问用户组中可以使用的两个 Azure AD 帐户;下面是有关的快速入门指南：

- [如何创建用户](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –将创建的用户添加到创建组
- [配置 Azure AD 允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –确保新的用户组有权注册设备 Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>在 HoloLens 2 上自动注册

若要获得流畅且无缝的体验，请将 Azure Active Directory 加入 (AADJ) 和自动注册到 Intune 2 设备的 Intune，这就是一种方法。 这允许用户在 OOBE 期间输入其组织的登录凭据，并自动注册 Azure AD 并将设备注册到 MDM。

通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home)，我们可以选择 "服务" 并导航几个页面，直到可以选择 "获取高级试用版"。 你可能会注意到，Azure Active Directory Premium 1 和 2-自动注册 P1 已经足够。 我们可以选择 Intune 并选择自动注册的用户作用域，并选择之前创建的组。

有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## <a name="corporate-wi-fi-connectivity"></a>企业 Wi-Fi 连接

企业 Wi-Fi 连接通常需要使用 HoloLens 2 的客户进行基于证书的身份验证。 需要使用与 MDM 解决方案集成的简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。 使用 Intune 部署 Wi-Fi 配置文件、证书和代理设置可为最终用户提供无缝体验。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>部署证书和 Wi-Fi 配置文件

若要通过 Microsoft 终结点管理器部署证书和配置文件，请执行以下步骤：

1. 为每个根证书和中间证书创建一个配置文件 (参阅) [创建受信任的证书配置文件](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) "。 其中每个配置文件都必须包含一个说明，其中包含以 DD/MM/YYYY 格式表示的到期日期。 

    > [!CAUTION]
    > **不会部署没有到期日期的证书配置文件**。

2.  为每个 SCEP 或 PKCS 证书创建一个配置文件 (参阅 [创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 其中每个配置文件都必须具有包含以 DD/MM/YYYY 格式表示的到期日期的描述。 

    > [!CAUTION]
    > **不会部署没有到期日期的证书配置文件。**

    > [!Note]
    > 因为 HoloLens 2 被视为一个共享设备（即每个设备多个用户），所以建议在可能的情况下部署设备证书，而不是使用用户证书进行 Wi-Fi 身份验证。

3.  为企业 Wi-Fi 网络创建配置文件 (参阅 [适用于 Windows 10 及更高版本设备的 wi-fi 设置](https://docs.microsoft.com/intune/wi-fi-settings-windows)) 。 在 Wi-Fi 配置文件中，可以选择使用组织中的代理设置。
 
    选项包括：
    - **无**：不配置任何代理设置。
    - **手动配置**：输入“代理服务器 IP 地址”及其“端口号” 。
    - **自动配置**：输入指向代理自动配置 (PAC) 脚本的 URL。 例如，输入 http://proxy.contoso.com/proxy.pac  。

    有关 PAC 文件的详细信息，请参阅[代理自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)（将打开非 Microsoft 网站）。
 
    > [!Note]
    > 建议在可能的情况下将 Wi-Fi 配置文件分配给设备组而不是用户组。
     
    > [!Tip]
    > 还可以从企业网络中的 Windows 10 PC 导出工作 Wi-Fi 配置文件。 此导出创建包含所有当前设置的 XML 文件。 然后，将此文件导入 Intune，并将其用作你的 HoloLens 2 设备的 Wi-Fi 配置文件。 请参阅[导出和导入 Windows 设备的 Wi-Fi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [将](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 设备配置文件分配给 HoloLens 设备组。

2.  在 Intune 中[监视](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor)设备配置文件。

如果 Wi-Fi 配置文件出现问题，请参阅 [Intune 中 Wi-Fi 设备配置配置文件的故障排除](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>对连接到公司的外部 Internet 访问进行故障排除
当服务尝试不通过设置代理时，它们可能会尝试通过防火墙进行连接。 可以将终结点详细信息的列表添加到防火墙规则，以解决这些问题。

如果阻止了防火墙端口，请为 HoloLens 启用一些常见 [终结点](https://docs.microsoft.com/hololens/hololens-offline) 。

还可以启用指南特定端口： [连接到 Microsoft DYNAMICS CRM Online 所需的可访问 Internet 的 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)。

## <a name="app-deployment"></a>应用部署

通过 MDM 部署 LOB 应用是一种易于缩放的方法，可以在创建的组中注册后自动部署到设备。

如果仍在开发应用程序，或者尚未开发应用程序，可以使用 MRTK 示例中心的示例应用。 此示例应用可以使用，不需要使用 Unity 或 Visual Studio。 [下载 MRTK 示例应用程序](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

如果你想要使用自己的应用或对混合现实的应用开发感兴趣，则可以随时查看我们的 [混合现实开发人员文档](https://docs.microsoft.com/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens 设备的系统要求基于应用生成的体系结构。 HoloLens 2 设备使用 ARM 体系结构。 在 Visual Studio 中生成应用时，请确保已为设备选择了正确的体系结构，并包含所需的任何依赖项。

> [!IMPORTANT]
> 部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配到打算使用应用的同一组，否则它将无法正确安装。

### <a name="upload-and-assign-the-app"></a>上载并分配应用

1. 导航到 " [MEM 管理中心](https://endpoint.microsoft.com/#home)"。

2. 选择 "**应用**" "  ->  **所有应用**"，然后选择 " **+ 添加**" 按钮。

3. 然后选择 " **业务线应用**"。 单击 " **选择**"。

4. 选择应用包文件，这是你的 .APPXBUNDLE 文件，或者在此示例中，应用为 _MRTK 示例中心 \_ 2.4.2.0 \_ arm \_ Master。_

5. 系统会通知你缺少依赖项。 在这种情况下，我们需要上载 _VCLibs_。 在 " **选择文件**" 下搜索它。

6. 选择“确定”。

7. 在下一个屏幕中，必填字段将自动填充。 选择“**下一页**”。

8. 在 "必需" 下，添加我们以前创建的组，以使该组需要此应用。 这将导致应用自动下载到组中已注册的设备上。 选择“**下一页**”。

9. 选择“创建”。

阅读详细信息： [在 Microsoft Intune 中将应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>设置指南：应用程序许可证、dataverse 和创作

为了使用 Dynamics 365 指南，你需要做一些准备工作。 需要准备三个方面：用户、dataverse 和指南。

### <a name="users-and-application-licenses"></a>用户和应用程序许可证

对于使用指南的人员，他们需要使用我们在本指南中设置的 Azure AD 帐户。

还需要将 Dynamics 365 指南许可证分配给已创建的用户。 你将从 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/Home)完成此操作。 同时将许可证分配给你的主要 Azure 帐户。

请参阅 [本简短指南](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ，其中包含有关应用应用程序许可证的分步说明。

### <a name="set-up-the-dataverse"></a>设置 Dataverse

若要 [设置生产环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) ，需要满足两个先决条件。 你必须具有 " [**系统管理员**](https://docs.microsoft.com/power-platform/admin/database-security) " 角色，  **并且**  必须具有 " [**power apps" 许可证**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (或包含 power Apps 许可证) 的 [**Dynamics 365 指南许可证**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) 。 如果按照本指南创建 Azure AD，则满足系统管理员的角色要求。 我们还在上一步中分配了指南许可证。

在本指南中 [创建 Microsoft Dataverse 环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：

1. 首先使用 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments) 并创建新的环境。
2. 创建 **新环境** 时，为所&#39;的 **类型** 选择 " **生产**"。
3. 为 **此环境切换创建数据库** 非常重要？  选项为  **"是"**。
4. 在 "  **添加数据库**  " 对话框中，将 "  **启用 Dynamics 365 应用**  " 选项设置为  **"是"。**

你需要增加 dataverse 中项目的最大文件大小。 增加最大文件大小后，你就可以上传更多的3D 模型或视频文件，稍后将在指南中使用。 请按照简短指南 [更改最大上载文件大小](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最后，需要 [安装并配置解决方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 在 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments)，选择 "**资源**" \& g t; **Dynamics 365 应用**，请在列表中选择 **Dynamics 365 指南**，然后选择 "**安装**"。  

你需要 [添加指南安全角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用应用。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>通过创作在你的电脑上创建测试指南

创建指南时，你将始终在电脑上启动。 创建步骤，选择模型，以及如何定位指南。 接下来，在你的 HoloLens 设备上的创作模式下，稍后将内容放在以后。 出于本指南的目的，我们建议使用少量步骤和模型进行简短的测试指南。

如果你想要开始了解指南的创作，请从 [创作概述](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)开始。 若要获取快速跟踪概述，请观看此视频。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>可选：展台模式

展台模式是一种模式，使 IT 管理员能够将 "开始" 菜单的 UI 配置为仅显示单个应用程序或应用程序的选择。 展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台排除某些用户仍允许他们访问常规开始菜单。

展台模式包含多个不同的变量，可在范围和配置中进行设置，以及将展台部署到 HoloLens 的方法。 由于所有这些变量的原因，展台模式将在本指南中保留为可选，并且不会被视为 _可选_ 。 如果你认为你的业务需要将可用应用限制为用户，或者想要了解详细信息，则可随时了解如何 [将 HoloLens 设置为展台](https://docs.microsoft.com/hololens/hololens-kiosk)。

## <a name="optional-wdac"></a>可选： WDAC

WDAC 允许 IT 管理员配置其设备，以阻止在设备上启动应用。 这不同于设备限制的方法，例如展台模式，其中用户向用户提供了一个用户界面，用于隐藏设备上的应用程序，但仍可以启动这些应用程序。 实现 WDAC 后，应用仍会显示在 "所有应用" 列表中，但 WDAC 会阻止设备用户启动这些应用和进程。

有关详细信息，请参阅 [使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。

[Windows Defender 应用程序控制-WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>后续步骤 
> [!div class="nextstepaction"]
> [企业连接部署-部署](hololens2-corp-connected-deploy.md)