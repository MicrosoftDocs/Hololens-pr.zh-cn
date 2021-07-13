---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 配置
description: 了解如何设置配置，以使用 HoloLens 2 通过企业连接网络部署Dynamics 365 Guides。
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637075"
---
# <a name="configure---corporate-connected-guide"></a>配置 - 企业连接指南

## <a name="azure-users-and-groups"></a>Azure 用户和组

Azure 和 Intune（按该扩展）使用用户和组来帮助分配配置和许可证。 为了验证此部署流并检查你能否创作和操作指南，&#39;需要用户帐户。

我们可以创建一个专用于分配许可证的用户组。

如果尚未&#39;两个用户帐户Azure AD可以使用的用户帐户;下面是以下快速入门指南：

- [如何创建用户](/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](/mem/intune/fundamentals/quickstart-create-group)
- [将用户添加到组](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组
- [配置Azure AD以允许用户组加入设备](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 确保新用户组有权将设备注册到Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>自动注册HoloLens 2

若要获得顺畅无缝的体验，可以设置 Azure Active Directory Join (AADJ) ，以及自动注册到 HoloLens 2 设备的 Intune。 这允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM。

通过使用[Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几页，直到选择"获取高级版试用版。 你可能会注意到存在Azure Active Directory Premium 1 和 2 - 自动注册 P1 已足够。 可以选择 Intune 并选择自动注册的用户范围，然后选择之前创建的组。

有关完整详细信息和步骤，请阅读有关 [如何为 Intune 启用自动注册的指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="corporate-wi-fi-connectivity"></a>企业Wi-Fi连接

企业Wi-Fi连接通常要求使用证书身份验证的客户进行基于证书HoloLens 2。 将需要使用与 MDM 解决方案集成的 简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。 使用 Intune 部署Wi-Fi配置文件、证书和代理设置，为最终用户创建无缝体验。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>部署证书和Wi-Fi配置文件

若要通过证书和配置文件Microsoft Endpoint Manager，请执行以下步骤：

1. 为每个根证书和中间证书创建配置文件 (创建[受信任的证书配置文件) 。](/intune/protect/certificates-configure#create-trusted-certificate-profiles) 其中每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的说明。

    > [!CAUTION]
    > **不会部署没有到期日期的证书配置文件**。

2. 为每个 SCEP 或 PKCS 证书创建配置文件 (请参阅创建 SCEP 证书配置文件或创建 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 证书配置文件) 其中每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的说明。

    > [!CAUTION]
    > **不会部署没有到期日期的证书配置文件。**

    > [!Note]
    > 由于HoloLens 2被视为共享设备，即每个设备的多个用户，因此建议在可能的情况下部署设备证书而不是用户Wi-Fi身份验证。

3. 若要创建企业网络Wi-Fi配置文件 (请参阅适用于 Windows 10 及更高版本设备的[Wi-Fi](/intune/wi-fi-settings-windows)) 。 在Wi-Fi配置文件中，可以选择在组织中使用代理设置。

    选项包括：
    - **无**：不配置任何代理设置。
    - **手动配置**：输入“代理服务器 IP 地址”及其“端口号” 。
    - **自动配置**：输入指向代理自动配置 (PAC) 脚本的 URL。 例如，输入 http://proxy.contoso.com/proxy.pac  。

    有关 PAC 文件的详细信息，请参阅[代理自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)（将打开非 Microsoft 网站）。
 
    > [!Note]
    > 建议尽可能将Wi-Fi配置文件分配给设备组而不是用户组。
     
    > [!Tip]
    > 还可以从企业网络上Wi-Fi电脑Windows 10工作配置文件。 此导出将创建包含所有当前设置的 XML 文件。 然后，将此文件导入 Intune，并使用它Wi-Fi设备HoloLens 2配置文件。 请参阅[导出和导入 Windows 设备的 Wi-Fi 设置](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [将](/mem/intune/configuration/device-profile-assign)设备配置文件分配给HoloLens组。

2.  [在](/mem/intune/configuration/device-profile-monitor) Intune 中监视设备配置文件。

如果配置文件存在问题，Wi-Fi [Intune Wi-Fi配置文件疑难解答](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>排查公司连接时的外部 Internet 访问问题
当服务尝试不通过设置的代理时，它们可能会尝试通过防火墙进行连接。 可以将终结点特定列表添加到防火墙规则，以解决这些问题。

如果在防火墙端口上受阻，请为防火墙[端口启用一些](/hololens/hololens-offline)HoloLens。

还可以启用指南特定端口：连接到 Microsoft Dynamics CRM Online 所需的[Internet Microsoft Dynamics CRM Online。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>应用部署

通过 MDM 部署 LOB 应用是一种易于缩放的方法，可以在已创建的组中注册时自动部署到设备。

如果仍在开发应用或还没有应用，可以使用 MRTK 示例中心的示例应用。 此示例应用已准备就绪，无需使用 Unity 或 Visual Studio。 [下载 MRTK 示例示例应用](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

如果希望使用自己的应用或对混合现实的应用开发感兴趣，请随意查看我们的 [混合现实开发人员文档](/windows/mixed-reality/design/design)。

> [!NOTE]
> 设备HoloLens要求基于应用构建的体系结构。 HoloLens 2使用 ARM 体系结构。 在 Visual Studio 中生成应用时，请确保为设备选择了正确的体系结构，并包含任何所需的依赖项。

> [!IMPORTANT]
> 部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配给打算使用该应用的同一组，否则无法正确安装。

### <a name="upload-and-assign-the-app"></a>Upload并分配应用

1. 导航到 [MEM 管理中心](https://endpoint.microsoft.com/#home)。

2. 选择 **"**  ->  **应用""所有** 应用"，然后选择 **"+ 添加"** 按钮。

3. 在"其他"下，**选择"业务线应用"。** 单击 **"选择"。**

4. 选择应用包文件，这是 APPXBUNDLE 文件，或在我们的示例中，应用是 _MRTK 示例中心 \_ 2.4.2.0 \_ arm \_ Master.appxbundle_。

5. 系统将会通知你缺少依赖项。 在这种情况下，需要上传 _Microsoft.VCLibs.ARM.14.00.appx_。 在"选择文件 **"下搜索它**。

6. 选择“确定”。

7. 下一屏幕中，必填字段将被自动填充。 选择“下一步”。

8. 在"必需"下，添加我们之前创建的组，使该组需要此应用。 这会使应用自动下载到组中已注册的设备。 选择“下一步”。

9. 选择“创建”。

阅读更多：[将应用分配到 Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>设置指南：应用程序许可证、dataverse 和创作

若要使用Dynamics 365 Guides，需要做好一些准备。 需要准备三个方面：用户、dataverse 和指南本身。

### <a name="users-and-application-licenses"></a>用户和应用程序许可证

对于使用指南的人，他们需要使用Azure AD之前在本指南中设置的帐户。

还需要将Dynamics 365 Guides许可证分配给已创建的用户。 你将从中执行[Microsoft 365 管理中心。](https://admin.microsoft.com/AdminPortal/Home) 此外，将许可证分配给主要 Azure 帐户。

有关 [应用应用程序许可证](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 的分步说明，请遵循此简短指南和图片。

### <a name="set-up-the-dataverse"></a>设置 Dataverse

若要 [设置生产环境，](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 需要满足两个先决条件。 必须具有系统管理员角色，[](/power-platform/admin/database-security)并且必须具有 Power Apps许可证 (或[](/power-platform/admin/signup-question-and-answer)Dynamics 365 Guides 许可证，Power Apps许可证) 。 [](/dynamics365/mixed-reality/guides/setup-step-one) 如果按照本指南创建Azure AD，则满足系统管理员的角色要求。 我们还在上一步中分配了指南许可证。

在本指南中 [，创建 Microsoft Dataverse 环境](/dynamics365/mixed-reality/guides/setup-step-two)：

1. 首先，使用 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments) 并创建新环境。
2. 创建新环境 **时，** 对于"**类型"，&#39;** 选择"生产 **"。**
3. 为此环境切换" **创建数据库"很重要？**  选项为 **"是"。**
4. 在"  **添加数据库"**  对话框中，将"  **启用 Dynamics 365 应用"**  选项设置为"  **是"。**

你需要增加 dataverse 中项目的最大文件大小。 增加最大文件大小后，你就可以上传更多的3D 模型或视频文件，稍后将在指南中使用。 请按照简短指南 [更改最大上载文件大小](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最后，需要 [安装并配置解决方案](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 在 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments)，选择 "**资源**" \& g t; **Dynamics 365 应用**，在列表中选择 " **Dynamics 365 Guides** "，然后选择 "**安装**"。  

你需要 [添加指南安全角色](/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用应用。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>通过创作在你的电脑上创建测试指南

创建指南时，你将始终在电脑上启动。 创建步骤，选择模型，以及如何定位指南。 接下来，在你的 HoloLens 设备上的创作模式下，稍后将内容放入指南。 出于本指南的目的，我们建议使用少量步骤和模型进行简短的测试指南。

如果你想要开始了解指南的创作，请从 [创作概述](/dynamics365/mixed-reality/guides/authoring-overview)开始。 若要获取快速跟踪概述，请观看此视频。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>可选：展台模式

展台模式是一种模式，使 IT 管理员能够将 "开始" 菜单的 UI 配置为仅显示单个应用程序或应用程序的选择。 展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台排除某些用户仍允许他们访问常规开始菜单。

展台模式包含多个不同的变量，可在范围和配置中进行设置，以及将展台部署到 HoloLens 的方法。 由于所有这些变量的原因，展台模式将在本指南中保留为可选，并且不会被视为 _可选_ 。 如果你认为你的业务需要将可用应用限制为用户，或者想要了解详细信息，则可以随时了解如何[将 HoloLens 设置为展台](/hololens/hololens-kiosk)。

## <a name="optional-wdac"></a>可选： WDAC

WDAC 允许 IT 管理员配置其设备，以阻止在设备上启动应用。 这不同于设备限制的方法，例如展台模式，其中用户向用户提供了一个用户界面，用于隐藏设备上的应用程序，但仍可以启动这些应用程序。 实现 WDAC 后，应用仍会显示在 "所有应用" 列表中，但 WDAC 会阻止设备用户启动这些应用和进程。

有关详细信息，请参阅[使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](/mem/intune/configuration/custom-profile-hololens)。

[Windows Defender 应用程序控制 - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接部署-部署](hololens2-corp-connected-deploy.md)