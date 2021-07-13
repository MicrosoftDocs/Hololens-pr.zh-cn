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
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="fab66-104">配置 - 企业连接指南</span><span class="sxs-lookup"><span data-stu-id="fab66-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="fab66-105">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="fab66-105">Azure Users and Groups</span></span>

<span data-ttu-id="fab66-106">Azure 和 Intune（按该扩展）使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="fab66-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="fab66-107">为了验证此部署流并检查你能否创作和操作指南，&#39;需要用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fab66-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="fab66-108">我们可以创建一个专用于分配许可证的用户组。</span><span class="sxs-lookup"><span data-stu-id="fab66-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="fab66-109">如果尚未&#39;两个用户帐户Azure AD可以使用的用户帐户;下面是以下快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="fab66-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="fab66-110">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="fab66-110">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="fab66-111">如何创建组</span><span class="sxs-lookup"><span data-stu-id="fab66-111">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="fab66-112">[将用户添加到组](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组</span><span class="sxs-lookup"><span data-stu-id="fab66-112">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="fab66-113">[配置Azure AD以允许用户组加入设备](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 确保新用户组有权将设备注册到Azure AD</span><span class="sxs-lookup"><span data-stu-id="fab66-113">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="fab66-114">自动注册HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fab66-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="fab66-115">若要获得顺畅无缝的体验，可以设置 Azure Active Directory Join (AADJ) ，以及自动注册到 HoloLens 2 设备的 Intune。</span><span class="sxs-lookup"><span data-stu-id="fab66-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="fab66-116">这允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="fab66-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="fab66-117">通过使用[Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几页，直到选择"获取高级版试用版。</span><span class="sxs-lookup"><span data-stu-id="fab66-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="fab66-118">你可能会注意到存在Azure Active Directory Premium 1 和 2 - 自动注册 P1 已足够。</span><span class="sxs-lookup"><span data-stu-id="fab66-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="fab66-119">可以选择 Intune 并选择自动注册的用户范围，然后选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="fab66-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="fab66-120">有关完整详细信息和步骤，请阅读有关 [如何为 Intune 启用自动注册的指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="fab66-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="fab66-121">企业Wi-Fi连接</span><span class="sxs-lookup"><span data-stu-id="fab66-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="fab66-122">企业Wi-Fi连接通常要求使用证书身份验证的客户进行基于证书HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="fab66-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="fab66-123">将需要使用与 MDM 解决方案集成的 简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。</span><span class="sxs-lookup"><span data-stu-id="fab66-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="fab66-124">使用 Intune 部署Wi-Fi配置文件、证书和代理设置，为最终用户创建无缝体验。</span><span class="sxs-lookup"><span data-stu-id="fab66-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="fab66-125">部署证书和Wi-Fi配置文件</span><span class="sxs-lookup"><span data-stu-id="fab66-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="fab66-126">若要通过证书和配置文件Microsoft Endpoint Manager，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fab66-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="fab66-127">为每个根证书和中间证书创建配置文件 (创建[受信任的证书配置文件) 。](/intune/protect/certificates-configure#create-trusted-certificate-profiles)</span><span class="sxs-lookup"><span data-stu-id="fab66-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="fab66-128">其中每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的说明。</span><span class="sxs-lookup"><span data-stu-id="fab66-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="fab66-129">**不会部署没有到期日期的证书配置文件**。</span><span class="sxs-lookup"><span data-stu-id="fab66-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2. <span data-ttu-id="fab66-130">为每个 SCEP 或 PKCS 证书创建配置文件 (请参阅创建 SCEP 证书配置文件或创建 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 证书配置文件) 其中每个配置文件都必须具有包含 DD/MM/YYYY 格式的到期日期的说明。</span><span class="sxs-lookup"><span data-stu-id="fab66-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="fab66-131">**不会部署没有到期日期的证书配置文件。**</span><span class="sxs-lookup"><span data-stu-id="fab66-131">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!Note]
    > <span data-ttu-id="fab66-132">由于HoloLens 2被视为共享设备，即每个设备的多个用户，因此建议在可能的情况下部署设备证书而不是用户Wi-Fi身份验证。</span><span class="sxs-lookup"><span data-stu-id="fab66-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3. <span data-ttu-id="fab66-133">若要创建企业网络Wi-Fi配置文件 (请参阅适用于 Windows 10 及更高版本设备的[Wi-Fi](/intune/wi-fi-settings-windows)) 。</span><span class="sxs-lookup"><span data-stu-id="fab66-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="fab66-134">在Wi-Fi配置文件中，可以选择在组织中使用代理设置。</span><span class="sxs-lookup"><span data-stu-id="fab66-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>

    <span data-ttu-id="fab66-135">选项包括：</span><span class="sxs-lookup"><span data-stu-id="fab66-135">Your options:</span></span>
    - <span data-ttu-id="fab66-136">**无**：不配置任何代理设置。</span><span class="sxs-lookup"><span data-stu-id="fab66-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="fab66-137">**手动配置**：输入“代理服务器 IP 地址”及其“端口号” 。</span><span class="sxs-lookup"><span data-stu-id="fab66-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="fab66-138">**自动配置**：输入指向代理自动配置 (PAC) 脚本的 URL。</span><span class="sxs-lookup"><span data-stu-id="fab66-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="fab66-139">例如，输入 http://proxy.contoso.com/proxy.pac  。</span><span class="sxs-lookup"><span data-stu-id="fab66-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="fab66-140">有关 PAC 文件的详细信息，请参阅[代理自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)（将打开非 Microsoft 网站）。</span><span class="sxs-lookup"><span data-stu-id="fab66-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="fab66-141">建议尽可能将Wi-Fi配置文件分配给设备组而不是用户组。</span><span class="sxs-lookup"><span data-stu-id="fab66-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="fab66-142">还可以从企业网络上Wi-Fi电脑Windows 10工作配置文件。</span><span class="sxs-lookup"><span data-stu-id="fab66-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="fab66-143">此导出将创建包含所有当前设置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fab66-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="fab66-144">然后，将此文件导入 Intune，并使用它Wi-Fi设备HoloLens 2配置文件。</span><span class="sxs-lookup"><span data-stu-id="fab66-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="fab66-145">请参阅[导出和导入 Windows 设备的 Wi-Fi 设置](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。</span><span class="sxs-lookup"><span data-stu-id="fab66-145">See [Export and import Wi-Fi settings for Windows devices](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="fab66-146">[将](/mem/intune/configuration/device-profile-assign)设备配置文件分配给HoloLens组。</span><span class="sxs-lookup"><span data-stu-id="fab66-146">[Assign](/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="fab66-147">[在](/mem/intune/configuration/device-profile-monitor) Intune 中监视设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="fab66-147">[Monitor](/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="fab66-148">如果配置文件存在问题，Wi-Fi [Intune Wi-Fi配置文件疑难解答](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。</span><span class="sxs-lookup"><span data-stu-id="fab66-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="fab66-149">排查公司连接时的外部 Internet 访问问题</span><span class="sxs-lookup"><span data-stu-id="fab66-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="fab66-150">当服务尝试不通过设置的代理时，它们可能会尝试通过防火墙进行连接。</span><span class="sxs-lookup"><span data-stu-id="fab66-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="fab66-151">可以将终结点特定列表添加到防火墙规则，以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="fab66-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="fab66-152">如果在防火墙端口上受阻，请为防火墙[端口启用一些](/hololens/hololens-offline)HoloLens。</span><span class="sxs-lookup"><span data-stu-id="fab66-152">If you're blocked at firewall ports, enable some common [endpoints](/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="fab66-153">还可以启用指南特定端口：连接到 Microsoft Dynamics CRM Online 所需的[Internet Microsoft Dynamics CRM Online。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)</span><span class="sxs-lookup"><span data-stu-id="fab66-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="fab66-154">应用部署</span><span class="sxs-lookup"><span data-stu-id="fab66-154">App Deployment</span></span>

<span data-ttu-id="fab66-155">通过 MDM 部署 LOB 应用是一种易于缩放的方法，可以在已创建的组中注册时自动部署到设备。</span><span class="sxs-lookup"><span data-stu-id="fab66-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="fab66-156">如果仍在开发应用或还没有应用，可以使用 MRTK 示例中心的示例应用。</span><span class="sxs-lookup"><span data-stu-id="fab66-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="fab66-157">此示例应用已准备就绪，无需使用 Unity 或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fab66-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="fab66-158">[下载 MRTK 示例示例应用](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。</span><span class="sxs-lookup"><span data-stu-id="fab66-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="fab66-159">如果希望使用自己的应用或对混合现实的应用开发感兴趣，请随意查看我们的 [混合现实开发人员文档](/windows/mixed-reality/design/design)。</span><span class="sxs-lookup"><span data-stu-id="fab66-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="fab66-160">设备HoloLens要求基于应用构建的体系结构。</span><span class="sxs-lookup"><span data-stu-id="fab66-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="fab66-161">HoloLens 2使用 ARM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="fab66-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="fab66-162">在 Visual Studio 中生成应用时，请确保为设备选择了正确的体系结构，并包含任何所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fab66-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fab66-163">部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配给打算使用该应用的同一组，否则无法正确安装。</span><span class="sxs-lookup"><span data-stu-id="fab66-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="fab66-164">Upload并分配应用</span><span class="sxs-lookup"><span data-stu-id="fab66-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="fab66-165">导航到 [MEM 管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="fab66-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="fab66-166">选择 **"**  ->  **应用""所有** 应用"，然后选择 **"+ 添加"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fab66-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="fab66-167">在"其他"下，**选择"业务线应用"。**</span><span class="sxs-lookup"><span data-stu-id="fab66-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="fab66-168">单击 **"选择"。**</span><span class="sxs-lookup"><span data-stu-id="fab66-168">Click **select**.</span></span>

4. <span data-ttu-id="fab66-169">选择应用包文件，这是 APPXBUNDLE 文件，或在我们的示例中，应用是 _MRTK 示例中心 \_ 2.4.2.0 \_ arm \_ Master.appxbundle_。</span><span class="sxs-lookup"><span data-stu-id="fab66-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="fab66-170">系统将会通知你缺少依赖项。</span><span class="sxs-lookup"><span data-stu-id="fab66-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="fab66-171">在这种情况下，需要上传 _Microsoft.VCLibs.ARM.14.00.appx_。</span><span class="sxs-lookup"><span data-stu-id="fab66-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="fab66-172">在"选择文件 **"下搜索它**。</span><span class="sxs-lookup"><span data-stu-id="fab66-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="fab66-173">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="fab66-173">Select OK.</span></span>

7. <span data-ttu-id="fab66-174">下一屏幕中，必填字段将被自动填充。</span><span class="sxs-lookup"><span data-stu-id="fab66-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="fab66-175">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fab66-175">Select **Next**.</span></span>

8. <span data-ttu-id="fab66-176">在"必需"下，添加我们之前创建的组，使该组需要此应用。</span><span class="sxs-lookup"><span data-stu-id="fab66-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="fab66-177">这会使应用自动下载到组中已注册的设备。</span><span class="sxs-lookup"><span data-stu-id="fab66-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="fab66-178">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fab66-178">Select **Next**.</span></span>

9. <span data-ttu-id="fab66-179">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="fab66-179">Select **Create**.</span></span>

<span data-ttu-id="fab66-180">阅读更多：[将应用分配到 Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)</span><span class="sxs-lookup"><span data-stu-id="fab66-180">Read more: [Assign apps to groups in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="fab66-181">设置指南：应用程序许可证、dataverse 和创作</span><span class="sxs-lookup"><span data-stu-id="fab66-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="fab66-182">若要使用Dynamics 365 Guides，需要做好一些准备。</span><span class="sxs-lookup"><span data-stu-id="fab66-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="fab66-183">需要准备三个方面：用户、dataverse 和指南本身。</span><span class="sxs-lookup"><span data-stu-id="fab66-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="fab66-184">用户和应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="fab66-184">Users and application licenses</span></span>

<span data-ttu-id="fab66-185">对于使用指南的人，他们需要使用Azure AD之前在本指南中设置的帐户。</span><span class="sxs-lookup"><span data-stu-id="fab66-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="fab66-186">还需要将Dynamics 365 Guides许可证分配给已创建的用户。</span><span class="sxs-lookup"><span data-stu-id="fab66-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="fab66-187">你将从中执行[Microsoft 365 管理中心。](https://admin.microsoft.com/AdminPortal/Home)</span><span class="sxs-lookup"><span data-stu-id="fab66-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="fab66-188">此外，将许可证分配给主要 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="fab66-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="fab66-189">有关 [应用应用程序许可证](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 的分步说明，请遵循此简短指南和图片。</span><span class="sxs-lookup"><span data-stu-id="fab66-189">Follow [this short guide](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="fab66-190">设置 Dataverse</span><span class="sxs-lookup"><span data-stu-id="fab66-190">Set up the Dataverse</span></span>

<span data-ttu-id="fab66-191">若要 [设置生产环境，](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 需要满足两个先决条件。</span><span class="sxs-lookup"><span data-stu-id="fab66-191">In order to [set up a production environment](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="fab66-192">必须具有系统管理员角色，[](/power-platform/admin/database-security)并且必须具有 Power Apps许可证 (或[](/power-platform/admin/signup-question-and-answer)Dynamics 365 Guides 许可证，Power Apps许可证) 。 [](/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="fab66-192">You must have the [**System Administrator**](/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="fab66-193">如果按照本指南创建Azure AD，则满足系统管理员的角色要求。</span><span class="sxs-lookup"><span data-stu-id="fab66-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="fab66-194">我们还在上一步中分配了指南许可证。</span><span class="sxs-lookup"><span data-stu-id="fab66-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="fab66-195">在本指南中 [，创建 Microsoft Dataverse 环境](/dynamics365/mixed-reality/guides/setup-step-two)：</span><span class="sxs-lookup"><span data-stu-id="fab66-195">Within this guide to [create a Microsoft Dataverse environment](/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="fab66-196">首先，使用 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments) 并创建新环境。</span><span class="sxs-lookup"><span data-stu-id="fab66-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="fab66-197">创建新环境 **时，** 对于"**类型"，&#39;** 选择"生产 **"。**</span><span class="sxs-lookup"><span data-stu-id="fab66-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="fab66-198">为此环境切换" **创建数据库"很重要？**</span><span class="sxs-lookup"><span data-stu-id="fab66-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="fab66-199">选项为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="fab66-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="fab66-200">在"  **添加数据库"**  对话框中，将"  **启用 Dynamics 365 应用"**  选项设置为"  **是"。**</span><span class="sxs-lookup"><span data-stu-id="fab66-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="fab66-201">你需要增加 dataverse 中项目的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="fab66-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="fab66-202">增加最大文件大小后，你就可以上传更多的3D 模型或视频文件，稍后将在指南中使用。</span><span class="sxs-lookup"><span data-stu-id="fab66-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="fab66-203">请按照简短指南 [更改最大上载文件大小](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。</span><span class="sxs-lookup"><span data-stu-id="fab66-203">Follow a short guide [to change the maximum upload file size](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="fab66-204">最后，需要 [安装并配置解决方案](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。</span><span class="sxs-lookup"><span data-stu-id="fab66-204">Lastly, you'll need to [install and configure the solution](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="fab66-205">在 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments)，选择 "**资源**" \& g t; **Dynamics 365 应用**，在列表中选择 " **Dynamics 365 Guides** "，然后选择 "**安装**"。  </span><span class="sxs-lookup"><span data-stu-id="fab66-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="fab66-206">你需要 [添加指南安全角色](/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用应用。</span><span class="sxs-lookup"><span data-stu-id="fab66-206">You need [add a Guides security role](/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="fab66-207">通过创作在你的电脑上创建测试指南</span><span class="sxs-lookup"><span data-stu-id="fab66-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="fab66-208">创建指南时，你将始终在电脑上启动。</span><span class="sxs-lookup"><span data-stu-id="fab66-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="fab66-209">创建步骤，选择模型，以及如何定位指南。</span><span class="sxs-lookup"><span data-stu-id="fab66-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="fab66-210">接下来，在你的 HoloLens 设备上的创作模式下，稍后将内容放入指南。</span><span class="sxs-lookup"><span data-stu-id="fab66-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="fab66-211">出于本指南的目的，我们建议使用少量步骤和模型进行简短的测试指南。</span><span class="sxs-lookup"><span data-stu-id="fab66-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="fab66-212">如果你想要开始了解指南的创作，请从 [创作概述](/dynamics365/mixed-reality/guides/authoring-overview)开始。</span><span class="sxs-lookup"><span data-stu-id="fab66-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="fab66-213">若要获取快速跟踪概述，请观看此视频。</span><span class="sxs-lookup"><span data-stu-id="fab66-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="fab66-214">可选：展台模式</span><span class="sxs-lookup"><span data-stu-id="fab66-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="fab66-215">展台模式是一种模式，使 IT 管理员能够将 "开始" 菜单的 UI 配置为仅显示单个应用程序或应用程序的选择。</span><span class="sxs-lookup"><span data-stu-id="fab66-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="fab66-216">展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台排除某些用户仍允许他们访问常规开始菜单。</span><span class="sxs-lookup"><span data-stu-id="fab66-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="fab66-217">展台模式包含多个不同的变量，可在范围和配置中进行设置，以及将展台部署到 HoloLens 的方法。</span><span class="sxs-lookup"><span data-stu-id="fab66-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="fab66-218">由于所有这些变量的原因，展台模式将在本指南中保留为可选，并且不会被视为 _可选_ 。</span><span class="sxs-lookup"><span data-stu-id="fab66-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="fab66-219">如果你认为你的业务需要将可用应用限制为用户，或者想要了解详细信息，则可以随时了解如何[将 HoloLens 设置为展台](/hololens/hololens-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="fab66-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="fab66-220">可选： WDAC</span><span class="sxs-lookup"><span data-stu-id="fab66-220">Optional: WDAC</span></span>

<span data-ttu-id="fab66-221">WDAC 允许 IT 管理员配置其设备，以阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="fab66-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="fab66-222">这不同于设备限制的方法，例如展台模式，其中用户向用户提供了一个用户界面，用于隐藏设备上的应用程序，但仍可以启动这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="fab66-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="fab66-223">实现 WDAC 后，应用仍会显示在 "所有应用" 列表中，但 WDAC 会阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="fab66-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="fab66-224">有关详细信息，请参阅[使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="fab66-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="fab66-225">Windows Defender 应用程序控制 - WDAC</span><span class="sxs-lookup"><span data-stu-id="fab66-225">Windows Defender Application Control - WDAC</span></span>](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="fab66-226">下一步</span><span class="sxs-lookup"><span data-stu-id="fab66-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="fab66-227">企业连接部署-部署</span><span class="sxs-lookup"><span data-stu-id="fab66-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)