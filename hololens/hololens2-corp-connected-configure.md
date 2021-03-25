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
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="c8ab6-104">配置 - 企业连接指南</span><span class="sxs-lookup"><span data-stu-id="c8ab6-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="c8ab6-105">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="c8ab6-105">Azure Users and Groups</span></span>

<span data-ttu-id="c8ab6-106">Azure 和 Intune 通过该扩展使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="c8ab6-107">为了验证此部署流并能够检查你能否创作和操作指南，&#39;需要用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="c8ab6-108">我们可以创建一个专门用于分配许可证的用户组。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="c8ab6-109">如果尚未&#39;用户组中的两个 Azure AD 帐户，可以使用;以下是以下快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="c8ab6-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="c8ab6-110">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="c8ab6-110">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="c8ab6-111">如何创建组</span><span class="sxs-lookup"><span data-stu-id="c8ab6-111">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="c8ab6-112">[向组添加用户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组</span><span class="sxs-lookup"><span data-stu-id="c8ab6-112">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="c8ab6-113">[配置 Azure AD 以允许](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 用户组加入设备 – 确保新用户组具有将设备注册到 Azure AD 的权限</span><span class="sxs-lookup"><span data-stu-id="c8ab6-113">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="c8ab6-114">HoloLens 2 上的自动注册</span><span class="sxs-lookup"><span data-stu-id="c8ab6-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="c8ab6-115">若要获得流畅而无缝的体验，可以设置 Azure Active Directory 加入 (AADJ) 以及自动注册到适用于 HoloLens 2 设备的 Intune。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="c8ab6-116">这允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册，将设备注册到 MDM 中。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="c8ab6-117">通过使用 [Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几个页面，直到我们可以选择获取高级试用版。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="c8ab6-118">你可能会注意到 Azure Active Directory Premium 1 和 2 - 对于自动注册 P1 已足够。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="c8ab6-119">我们可以选择 Intune 并选择用户作用域进行自动注册，然后选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="c8ab6-120">有关完整详细信息和步骤，请阅读如何为 [Intune 启用自动注册的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="c8ab6-121">企业Wi-Fi连接</span><span class="sxs-lookup"><span data-stu-id="c8ab6-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="c8ab6-122">公司Wi-Fi连接通常需要使用 HoloLens 2 的客户进行基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="c8ab6-123">你需要使用与 MDM 解决方案集成的简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="c8ab6-124">使用 Intune 部署Wi-Fi配置文件、证书和代理设置，为最终用户打造无缝体验。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="c8ab6-125">部署证书和Wi-Fi配置文件</span><span class="sxs-lookup"><span data-stu-id="c8ab6-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="c8ab6-126">若要通过 Microsoft Endpoint Manager 部署证书和配置文件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c8ab6-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="c8ab6-127">为每个根证书和中间证书创建配置文件 (请参阅创建 [受信任的](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) 证书配置文件) 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="c8ab6-128">其中每个配置文件必须具有包含 DD/MM/YYYYY 格式到期日期的说明。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > <span data-ttu-id="c8ab6-129">**不会部署没有过期日期的证书配置文件**。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2.  <span data-ttu-id="c8ab6-130">为每个 SCEP 或 PKCS 证书创建一个配置文件（请参阅[创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。这些配置文件中的每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的描述。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > **<span data-ttu-id="c8ab6-131">将不会部署无到期日期的证书配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-131">Certificate profiles without an expiration date will not be deployed.</span></span>**

    > [!Note]
    > <span data-ttu-id="c8ab6-132">由于 HoloLens 2 被视为共享设备，即每个设备有多个用户，因此建议在可能的情况下部署设备证书，而不是Wi-Fi身份验证的用户证书。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3.  <span data-ttu-id="c8ab6-133">创建适用于企业网络Wi-Fi配置文件 ([Windows 10](https://docs.microsoft.com/intune/wi-fi-settings-windows) 及更高版本设备的 WLAN 设置) 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="c8ab6-134">在Wi-Fi配置文件中，可以选择在组织中使用代理设置。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>
 
    <span data-ttu-id="c8ab6-135">你的选项：</span><span class="sxs-lookup"><span data-stu-id="c8ab6-135">Your options:</span></span>
    - <span data-ttu-id="c8ab6-136">**无**：未配置代理设置。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="c8ab6-137">**手动配置**：输入代理服务器 **IP 地址** 及其 **端口号**。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="c8ab6-138">**自动配置**：输入指向 PAC (PAC) 配置的 URL。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="c8ab6-139">例如，输入 *http://proxy.contoso.com/proxy.pac* 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="c8ab6-140">有关 PAC 文件详细信息，请参阅代理 [自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (打开非 Microsoft 站点) 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="c8ab6-141">建议尽可能将 Wi-Fi 配置文件分配给设备组，而不是用户组。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="c8ab6-142">此外，还可从公司网络上的 Windows 10 电脑导出有效的 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="c8ab6-143">此导出将创建包含所有当前设置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="c8ab6-144">然后，将此文件导入到 Intune 中，并将其用作 HoloLens 2 设备的 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="c8ab6-145">请参阅 [导出和Wi-Fi Windows 设备的自定义设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-145">See [Export and import Wi-Fi settings for Windows devices](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="c8ab6-146">[将](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 设备配置文件分配给 HoloLens 设备组。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-146">[Assign](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="c8ab6-147">[在](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune 中监视设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-147">[Monitor](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="c8ab6-148">如果配置文件中Wi-Fi问题，Wi-Fi [Intune 中的设备配置文件疑难解答](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="c8ab6-149">公司连接时的外部 Internet 访问疑难解答</span><span class="sxs-lookup"><span data-stu-id="c8ab6-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="c8ab6-150">当服务尝试不通过设置代理时，它们可能会尝试通过防火墙进行连接。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="c8ab6-151">你可以将终结点特定项列表添加到防火墙规则中，以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="c8ab6-152">如果在防火墙端口被阻止，请为 HoloLens 启用 [一](https://docs.microsoft.com/hololens/hololens-offline) 些常见终结点。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-152">If you're blocked at firewall ports, enable some common [endpoints](https://docs.microsoft.com/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="c8ab6-153">还可以启用指南特定端口：连接到 Microsoft Dynamics CRM Online 所需的 Internet[访问Microsoft Dynamics CRM Online。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)</span><span class="sxs-lookup"><span data-stu-id="c8ab6-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="c8ab6-154">应用部署</span><span class="sxs-lookup"><span data-stu-id="c8ab6-154">App Deployment</span></span>

<span data-ttu-id="c8ab6-155">通过 MDM 部署 LOB 应用是一种易于缩放的方法，可在注册已创建的组时自动部署到设备。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="c8ab6-156">如果你仍在开发应用或还没有应用，可以使用 MRTK 示例中心的示例应用。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="c8ab6-157">此示例应用已准备就绪，无需使用 Unity 或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="c8ab6-158">[下载 MRTK 示例示例应用](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="c8ab6-159">如果你希望使用自己的应用或对混合现实的应用开发感兴趣，请随时查看我们的 [混合现实开发人员文档](https://docs.microsoft.com/windows/mixed-reality/design/design)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](https://docs.microsoft.com/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="c8ab6-160">HoloLens 设备的系统要求基于应用内部版本的体系结构。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="c8ab6-161">HoloLens 2 设备使用ARM体系结构。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="c8ab6-162">在 Visual Studio 中生成应用时，请确保你已针对设备选择了正确的体系结构，并包括任何所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8ab6-163">部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配给打算使用该应用的同一组，否则无法正确安装。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="c8ab6-164">上载和分配应用</span><span class="sxs-lookup"><span data-stu-id="c8ab6-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="c8ab6-165">导航到 [MEM 管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="c8ab6-166">选择 **"**  ->  **应用""所有**应用"，然后选择 **"+ 添加"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="c8ab6-167">在"其他"下方，**选择"业务线应用"。**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="c8ab6-168">单击 **"选择"。**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-168">Click **select**.</span></span>

4. <span data-ttu-id="c8ab6-169">选择应用包文件，这是 APPXBUNDLE 文件，或者在我们的示例中，应用是_MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle。_</span><span class="sxs-lookup"><span data-stu-id="c8ab6-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="c8ab6-170">你将收到缺少依赖项的通知。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="c8ab6-171">在这种情况下，我们需要上载_Microsoft.VCLibs.ARM.14.00.appx。_</span><span class="sxs-lookup"><span data-stu-id="c8ab6-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="c8ab6-172">在"选择文件 **"下搜索它**。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="c8ab6-173">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-173">Select OK.</span></span>

7. <span data-ttu-id="c8ab6-174">下一个屏幕中，必填字段将被自动填充。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="c8ab6-175">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-175">Select **Next**.</span></span>

8. <span data-ttu-id="c8ab6-176">在"必需"下，添加我们之前创建的组，使此应用成为组必需的。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="c8ab6-177">这会使应用自动下载到组中注册的设备。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="c8ab6-178">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-178">Select **Next**.</span></span>

9. <span data-ttu-id="c8ab6-179">选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-179">Select **Create**.</span></span>

<span data-ttu-id="c8ab6-180">阅读更多： [在 Microsoft Intune 中向组分配应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span><span class="sxs-lookup"><span data-stu-id="c8ab6-180">Read more: [Assign apps to groups in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="c8ab6-181">设置指南：应用程序许可证、dataverse 和创作</span><span class="sxs-lookup"><span data-stu-id="c8ab6-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="c8ab6-182">为了使用 Dynamics 365 Guides，你需要做一些准备工作。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="c8ab6-183">我们需要在三个方面做好准备;用户、dataverse 和参考线本身。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="c8ab6-184">用户和应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="c8ab6-184">Users and application licenses</span></span>

<span data-ttu-id="c8ab6-185">对于使用指南的人，他们将需要使用 Azure AD 帐户，我们之前在本指南中设置了该帐户。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="c8ab6-186">你还需要将 Dynamics 365 Guides 许可证分配给你创建的用户。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="c8ab6-187">你将从 [Microsoft 365 管理中心进行此操作](https://admin.microsoft.com/AdminPortal/Home)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="c8ab6-188">此外，将许可证分配给主 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="c8ab6-189">按照 [包含图片的](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 简短指南，查看应用应用程序许可证的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-189">Follow [this short guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="c8ab6-190">设置 Dataverse</span><span class="sxs-lookup"><span data-stu-id="c8ab6-190">Set up the Dataverse</span></span>

<span data-ttu-id="c8ab6-191">为了设置 [生产环境，](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 您需要满足两个先决条件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-191">In order to [set up a production environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="c8ab6-192">你必须具有[**系统管理员**](https://docs.microsoft.com/power-platform/admin/database-security)角色，并且必须具有\*\*\*\*[**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)许可证 (或[**Dynamics 365 Guides**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)许可证，其中包含 Power Apps 许可证) 。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-192">You must have the [**System Administrator**](https://docs.microsoft.com/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="c8ab6-193">如果按照本指南创建 Azure AD，则满足系统管理员的角色要求。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="c8ab6-194">我们还在上一步中分配了指南许可证。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="c8ab6-195">在本指南 [中，创建 Microsoft Dataverse 环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：</span><span class="sxs-lookup"><span data-stu-id="c8ab6-195">Within this guide to [create a Microsoft Dataverse environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="c8ab6-196">首先使用 [Power Platform 管理中心并](https://admin.powerplatform.microsoft.com/environments) 创建新环境。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="c8ab6-197">创建新环境**时，对于\*\*\*\*"类型**"，&#39;选择"生产 **"。**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="c8ab6-198">是否必须切换为此 **环境创建数据库？**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="c8ab6-199">选项为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="c8ab6-200">在"  **添加数据库"**  对话框中，将"  **启用 Dynamics 365 应用"**  选项设置为  **"是"。**</span><span class="sxs-lookup"><span data-stu-id="c8ab6-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="c8ab6-201">你将希望增加 dataverse 中项目的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="c8ab6-202">增加最大文件大小将允许你上载更大的 3D 模型或视频文件，你将在指南中稍后使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="c8ab6-203">按照简短指南 [更改最大上载文件大小](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-203">Follow a short guide [to change the maximum upload file size](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="c8ab6-204">最后，您需要安装和 [配置解决方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-204">Lastly, you'll need to [install and configure the solution](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="c8ab6-205">在[Power Platform 管理](https://admin.powerplatform.microsoft.com/environments)中心中，选择 **"资源**   \ &gt; **""Dynamics 365**应用"，在列表中选择 **"Dynamics 365 指南**"，然后选择"安装 **"。**  </span><span class="sxs-lookup"><span data-stu-id="c8ab6-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="c8ab6-206">你需要 [添加 Guides 安全角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用这些应用。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-206">You need [add a Guides security role](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="c8ab6-207">通过创作在电脑上创建测试指南</span><span class="sxs-lookup"><span data-stu-id="c8ab6-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="c8ab6-208">创建指南时，你将始终在电脑上启动。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="c8ab6-209">创建步骤、选择模型以及如何定位指南。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="c8ab6-210">然后，在 HoloLens 设备上将指南内容置于创作模式下。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="c8ab6-211">对于本指南，我们建议使用最少的步骤和模型制作一个简短的测试指南。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="c8ab6-212">如果你想要开始学习有关"指南"的创作，请从此处的创作 [概述开始](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="c8ab6-213">或者，若要获取快速跟踪概述，请观看此简短视频。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="c8ab6-214">可选：展台模式</span><span class="sxs-lookup"><span data-stu-id="c8ab6-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="c8ab6-215">展台模式是一种模式，IT 管理员可以将"开始"菜单的 UI 配置为只显示单个应用或选择的应用。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="c8ab6-216">展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台中排除某些用户仍允许他们访问常规的"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="c8ab6-217">展台模式具有许多不同的变量，在作用域和配置中都可以设置，还可以将展台部署到 HoloLens 的方法。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="c8ab6-218">由于所有这些变量，展台模式将作为本指南的可选模式__ 离开，并且不会重新访问。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="c8ab6-219">如果你相信有业务需要将可用应用限制为用户，或者希望了解更多信息，那么请随意了解如何将 [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)设置为展台。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](https://docs.microsoft.com/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="c8ab6-220">可选：WDAC</span><span class="sxs-lookup"><span data-stu-id="c8ab6-220">Optional: WDAC</span></span>

<span data-ttu-id="c8ab6-221">WDAC 允许 IT 管理员配置其设备以阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="c8ab6-222">这不同于设备限制方法（如展台模式）的方法，即向用户显示隐藏设备上应用的 UI，但仍可以启动它们。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="c8ab6-223">实现 WDAC 时，应用仍显示在"所有应用"列表中，但 WDAC 会阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="c8ab6-224">有关详细信息，请参阅使用 WDAC 和 Windows PowerShell使用 Microsoft Intune 允许或阻止 [HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="c8ab6-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="c8ab6-225">Windows Defender 应用程序控制 - WDAC</span><span class="sxs-lookup"><span data-stu-id="c8ab6-225">Windows Defender Application Control - WDAC</span></span>](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="c8ab6-226">下一步</span><span class="sxs-lookup"><span data-stu-id="c8ab6-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="c8ab6-227">企业连接的部署 - 部署</span><span class="sxs-lookup"><span data-stu-id="c8ab6-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)