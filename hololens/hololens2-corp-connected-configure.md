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
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="eb214-104">配置-企业连接指南</span><span class="sxs-lookup"><span data-stu-id="eb214-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="eb214-105">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="eb214-105">Azure Users and Groups</span></span>

<span data-ttu-id="eb214-106">Azure 以及该扩展的 Intune 使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="eb214-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="eb214-107">为了验证此部署流并能够检查是否可以创作和操作指南，你&#39;需要一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="eb214-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="eb214-108">我们可以将单个用户组专门用于分配许可证。</span><span class="sxs-lookup"><span data-stu-id="eb214-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="eb214-109">如果你不&#39;t 已经有权访问用户组中可以使用的两个 Azure AD 帐户;下面是有关的快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="eb214-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="eb214-110">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="eb214-110">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="eb214-111">如何创建组</span><span class="sxs-lookup"><span data-stu-id="eb214-111">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="eb214-112">[将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –将创建的用户添加到创建组</span><span class="sxs-lookup"><span data-stu-id="eb214-112">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="eb214-113">[配置 Azure AD 允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –确保新的用户组有权注册设备 Azure AD</span><span class="sxs-lookup"><span data-stu-id="eb214-113">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="eb214-114">在 HoloLens 2 上自动注册</span><span class="sxs-lookup"><span data-stu-id="eb214-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="eb214-115">若要获得流畅且无缝的体验，请将 Azure Active Directory 加入 (AADJ) 和自动注册到 Intune 2 设备的 Intune，这就是一种方法。</span><span class="sxs-lookup"><span data-stu-id="eb214-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="eb214-116">这允许用户在 OOBE 期间输入其组织的登录凭据，并自动注册 Azure AD 并将设备注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="eb214-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="eb214-117">通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home)，我们可以选择 "服务" 并导航几个页面，直到可以选择 "获取高级试用版"。</span><span class="sxs-lookup"><span data-stu-id="eb214-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="eb214-118">你可能会注意到，Azure Active Directory Premium 1 和 2-自动注册 P1 已经足够。</span><span class="sxs-lookup"><span data-stu-id="eb214-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="eb214-119">我们可以选择 Intune 并选择自动注册的用户作用域，并选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="eb214-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="eb214-120">有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="eb214-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="eb214-121">企业 Wi-Fi 连接</span><span class="sxs-lookup"><span data-stu-id="eb214-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="eb214-122">企业 Wi-Fi 连接通常需要使用 HoloLens 2 的客户进行基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="eb214-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="eb214-123">需要使用与 MDM 解决方案集成的简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。</span><span class="sxs-lookup"><span data-stu-id="eb214-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="eb214-124">使用 Intune 部署 Wi-Fi 配置文件、证书和代理设置可为最终用户提供无缝体验。</span><span class="sxs-lookup"><span data-stu-id="eb214-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="eb214-125">部署证书和 Wi-Fi 配置文件</span><span class="sxs-lookup"><span data-stu-id="eb214-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="eb214-126">若要通过 Microsoft 终结点管理器部署证书和配置文件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb214-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="eb214-127">为每个根证书和中间证书创建一个配置文件 (参阅) [创建受信任的证书配置文件](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) "。</span><span class="sxs-lookup"><span data-stu-id="eb214-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="eb214-128">其中每个配置文件都必须包含一个说明，其中包含以 DD/MM/YYYY 格式表示的到期日期。</span><span class="sxs-lookup"><span data-stu-id="eb214-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > <span data-ttu-id="eb214-129">**不会部署没有到期日期的证书配置文件**。</span><span class="sxs-lookup"><span data-stu-id="eb214-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2.  <span data-ttu-id="eb214-130">为每个 SCEP 或 PKCS 证书创建一个配置文件 (参阅 [创建 SCEP 证书配置文件或创建 PKCS 证书配置文件](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 其中每个配置文件都必须具有包含以 DD/MM/YYYY 格式表示的到期日期的描述。</span><span class="sxs-lookup"><span data-stu-id="eb214-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > <span data-ttu-id="eb214-131">**不会部署没有到期日期的证书配置文件。**</span><span class="sxs-lookup"><span data-stu-id="eb214-131">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!Note]
    > <span data-ttu-id="eb214-132">因为 HoloLens 2 被视为一个共享设备（即每个设备多个用户），所以建议在可能的情况下部署设备证书，而不是使用用户证书进行 Wi-Fi 身份验证。</span><span class="sxs-lookup"><span data-stu-id="eb214-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3.  <span data-ttu-id="eb214-133">为企业 Wi-Fi 网络创建配置文件 (参阅 [适用于 Windows 10 及更高版本设备的 wi-fi 设置](https://docs.microsoft.com/intune/wi-fi-settings-windows)) 。</span><span class="sxs-lookup"><span data-stu-id="eb214-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="eb214-134">在 Wi-Fi 配置文件中，可以选择使用组织中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="eb214-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>
 
    <span data-ttu-id="eb214-135">选项包括：</span><span class="sxs-lookup"><span data-stu-id="eb214-135">Your options:</span></span>
    - <span data-ttu-id="eb214-136">**无**：不配置任何代理设置。</span><span class="sxs-lookup"><span data-stu-id="eb214-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="eb214-137">**手动配置**：输入“代理服务器 IP 地址”及其“端口号” 。</span><span class="sxs-lookup"><span data-stu-id="eb214-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="eb214-138">**自动配置**：输入指向代理自动配置 (PAC) 脚本的 URL。</span><span class="sxs-lookup"><span data-stu-id="eb214-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="eb214-139">例如，输入 http://proxy.contoso.com/proxy.pac  。</span><span class="sxs-lookup"><span data-stu-id="eb214-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="eb214-140">有关 PAC 文件的详细信息，请参阅[代理自动配置 (PAC) 文件](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)（将打开非 Microsoft 网站）。</span><span class="sxs-lookup"><span data-stu-id="eb214-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="eb214-141">建议在可能的情况下将 Wi-Fi 配置文件分配给设备组而不是用户组。</span><span class="sxs-lookup"><span data-stu-id="eb214-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="eb214-142">还可以从企业网络中的 Windows 10 PC 导出工作 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb214-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="eb214-143">此导出创建包含所有当前设置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="eb214-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="eb214-144">然后，将此文件导入 Intune，并将其用作你的 HoloLens 2 设备的 Wi-Fi 配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb214-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="eb214-145">请参阅[导出和导入 Windows 设备的 Wi-Fi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。</span><span class="sxs-lookup"><span data-stu-id="eb214-145">See [Export and import Wi-Fi settings for Windows devices](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="eb214-146">[将](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 设备配置文件分配给 HoloLens 设备组。</span><span class="sxs-lookup"><span data-stu-id="eb214-146">[Assign](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="eb214-147">在 Intune 中[监视](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor)设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb214-147">[Monitor](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="eb214-148">如果 Wi-Fi 配置文件出现问题，请参阅 [Intune 中 Wi-Fi 设备配置配置文件的故障排除](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。</span><span class="sxs-lookup"><span data-stu-id="eb214-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="eb214-149">对连接到公司的外部 Internet 访问进行故障排除</span><span class="sxs-lookup"><span data-stu-id="eb214-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="eb214-150">当服务尝试不通过设置代理时，它们可能会尝试通过防火墙进行连接。</span><span class="sxs-lookup"><span data-stu-id="eb214-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="eb214-151">可以将终结点详细信息的列表添加到防火墙规则，以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="eb214-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="eb214-152">如果阻止了防火墙端口，请为 HoloLens 启用一些常见 [终结点](https://docs.microsoft.com/hololens/hololens-offline) 。</span><span class="sxs-lookup"><span data-stu-id="eb214-152">If you're blocked at firewall ports, enable some common [endpoints](https://docs.microsoft.com/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="eb214-153">还可以启用指南特定端口： [连接到 Microsoft DYNAMICS CRM Online 所需的可访问 Internet 的 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)。</span><span class="sxs-lookup"><span data-stu-id="eb214-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="eb214-154">应用部署</span><span class="sxs-lookup"><span data-stu-id="eb214-154">App Deployment</span></span>

<span data-ttu-id="eb214-155">通过 MDM 部署 LOB 应用是一种易于缩放的方法，可以在创建的组中注册后自动部署到设备。</span><span class="sxs-lookup"><span data-stu-id="eb214-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="eb214-156">如果仍在开发应用程序，或者尚未开发应用程序，可以使用 MRTK 示例中心的示例应用。</span><span class="sxs-lookup"><span data-stu-id="eb214-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="eb214-157">此示例应用可以使用，不需要使用 Unity 或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="eb214-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="eb214-158">[下载 MRTK 示例应用程序](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。</span><span class="sxs-lookup"><span data-stu-id="eb214-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="eb214-159">如果你想要使用自己的应用或对混合现实的应用开发感兴趣，则可以随时查看我们的 [混合现实开发人员文档](https://docs.microsoft.com/windows/mixed-reality/design/design)。</span><span class="sxs-lookup"><span data-stu-id="eb214-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](https://docs.microsoft.com/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="eb214-160">HoloLens 设备的系统要求基于应用生成的体系结构。</span><span class="sxs-lookup"><span data-stu-id="eb214-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="eb214-161">HoloLens 2 设备使用 ARM 体系结构。</span><span class="sxs-lookup"><span data-stu-id="eb214-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="eb214-162">在 Visual Studio 中生成应用时，请确保已为设备选择了正确的体系结构，并包含所需的任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="eb214-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb214-163">部署 LOB 应用时，还必须将证书上传到 Intune，并将其分配到打算使用应用的同一组，否则它将无法正确安装。</span><span class="sxs-lookup"><span data-stu-id="eb214-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="eb214-164">上载并分配应用</span><span class="sxs-lookup"><span data-stu-id="eb214-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="eb214-165">导航到 " [MEM 管理中心](https://endpoint.microsoft.com/#home)"。</span><span class="sxs-lookup"><span data-stu-id="eb214-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="eb214-166">选择 "**应用**" "  ->  **所有应用**"，然后选择 " **+ 添加**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="eb214-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="eb214-167">然后选择 " **业务线应用**"。</span><span class="sxs-lookup"><span data-stu-id="eb214-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="eb214-168">单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="eb214-168">Click **select**.</span></span>

4. <span data-ttu-id="eb214-169">选择应用包文件，这是你的 .APPXBUNDLE 文件，或者在此示例中，应用为 _MRTK 示例中心 \_ 2.4.2.0 \_ arm \_ Master。_</span><span class="sxs-lookup"><span data-stu-id="eb214-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="eb214-170">系统会通知你缺少依赖项。</span><span class="sxs-lookup"><span data-stu-id="eb214-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="eb214-171">在这种情况下，我们需要上载 _VCLibs_。</span><span class="sxs-lookup"><span data-stu-id="eb214-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="eb214-172">在 " **选择文件**" 下搜索它。</span><span class="sxs-lookup"><span data-stu-id="eb214-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="eb214-173">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="eb214-173">Select OK.</span></span>

7. <span data-ttu-id="eb214-174">在下一个屏幕中，必填字段将自动填充。</span><span class="sxs-lookup"><span data-stu-id="eb214-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="eb214-175">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="eb214-175">Select **Next**.</span></span>

8. <span data-ttu-id="eb214-176">在 "必需" 下，添加我们以前创建的组，以使该组需要此应用。</span><span class="sxs-lookup"><span data-stu-id="eb214-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="eb214-177">这将导致应用自动下载到组中已注册的设备上。</span><span class="sxs-lookup"><span data-stu-id="eb214-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="eb214-178">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="eb214-178">Select **Next**.</span></span>

9. <span data-ttu-id="eb214-179">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="eb214-179">Select **Create**.</span></span>

<span data-ttu-id="eb214-180">阅读详细信息： [在 Microsoft Intune 中将应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span><span class="sxs-lookup"><span data-stu-id="eb214-180">Read more: [Assign apps to groups in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="eb214-181">设置指南：应用程序许可证、dataverse 和创作</span><span class="sxs-lookup"><span data-stu-id="eb214-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="eb214-182">为了使用 Dynamics 365 指南，你需要做一些准备工作。</span><span class="sxs-lookup"><span data-stu-id="eb214-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="eb214-183">需要准备三个方面：用户、dataverse 和指南。</span><span class="sxs-lookup"><span data-stu-id="eb214-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="eb214-184">用户和应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="eb214-184">Users and application licenses</span></span>

<span data-ttu-id="eb214-185">对于使用指南的人员，他们需要使用我们在本指南中设置的 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="eb214-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="eb214-186">还需要将 Dynamics 365 指南许可证分配给已创建的用户。</span><span class="sxs-lookup"><span data-stu-id="eb214-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="eb214-187">你将从 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/Home)完成此操作。</span><span class="sxs-lookup"><span data-stu-id="eb214-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="eb214-188">同时将许可证分配给你的主要 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="eb214-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="eb214-189">请参阅 [本简短指南](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ，其中包含有关应用应用程序许可证的分步说明。</span><span class="sxs-lookup"><span data-stu-id="eb214-189">Follow [this short guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="eb214-190">设置 Dataverse</span><span class="sxs-lookup"><span data-stu-id="eb214-190">Set up the Dataverse</span></span>

<span data-ttu-id="eb214-191">若要 [设置生产环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) ，需要满足两个先决条件。</span><span class="sxs-lookup"><span data-stu-id="eb214-191">In order to [set up a production environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="eb214-192">你必须具有 " [**系统管理员**](https://docs.microsoft.com/power-platform/admin/database-security) " 角色，  **并且**  必须具有 " [**power apps" 许可证**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (或包含 power Apps 许可证) 的 [**Dynamics 365 指南许可证**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) 。</span><span class="sxs-lookup"><span data-stu-id="eb214-192">You must have the [**System Administrator**](https://docs.microsoft.com/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="eb214-193">如果按照本指南创建 Azure AD，则满足系统管理员的角色要求。</span><span class="sxs-lookup"><span data-stu-id="eb214-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="eb214-194">我们还在上一步中分配了指南许可证。</span><span class="sxs-lookup"><span data-stu-id="eb214-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="eb214-195">在本指南中 [创建 Microsoft Dataverse 环境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：</span><span class="sxs-lookup"><span data-stu-id="eb214-195">Within this guide to [create a Microsoft Dataverse environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="eb214-196">首先使用 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments) 并创建新的环境。</span><span class="sxs-lookup"><span data-stu-id="eb214-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="eb214-197">创建 **新环境** 时，为所&#39;的 **类型** 选择 " **生产**"。</span><span class="sxs-lookup"><span data-stu-id="eb214-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="eb214-198">为 **此环境切换创建数据库** 非常重要？</span><span class="sxs-lookup"><span data-stu-id="eb214-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="eb214-199">选项为  **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eb214-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="eb214-200">在 "  **添加数据库**  " 对话框中，将 "  **启用 Dynamics 365 应用**  " 选项设置为  **"是"。**</span><span class="sxs-lookup"><span data-stu-id="eb214-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="eb214-201">你需要增加 dataverse 中项目的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="eb214-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="eb214-202">增加最大文件大小后，你就可以上传更多的3D 模型或视频文件，稍后将在指南中使用。</span><span class="sxs-lookup"><span data-stu-id="eb214-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="eb214-203">请按照简短指南 [更改最大上载文件大小](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。</span><span class="sxs-lookup"><span data-stu-id="eb214-203">Follow a short guide [to change the maximum upload file size](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="eb214-204">最后，需要 [安装并配置解决方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。</span><span class="sxs-lookup"><span data-stu-id="eb214-204">Lastly, you'll need to [install and configure the solution](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="eb214-205">在 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/environments)，选择 "**资源**" \& g t; **Dynamics 365 应用**，请在列表中选择 **Dynamics 365 指南**，然后选择 "**安装**"。  </span><span class="sxs-lookup"><span data-stu-id="eb214-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="eb214-206">你需要 [添加指南安全角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，然后才能使用应用。</span><span class="sxs-lookup"><span data-stu-id="eb214-206">You need [add a Guides security role](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="eb214-207">通过创作在你的电脑上创建测试指南</span><span class="sxs-lookup"><span data-stu-id="eb214-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="eb214-208">创建指南时，你将始终在电脑上启动。</span><span class="sxs-lookup"><span data-stu-id="eb214-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="eb214-209">创建步骤，选择模型，以及如何定位指南。</span><span class="sxs-lookup"><span data-stu-id="eb214-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="eb214-210">接下来，在你的 HoloLens 设备上的创作模式下，稍后将内容放在以后。</span><span class="sxs-lookup"><span data-stu-id="eb214-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="eb214-211">出于本指南的目的，我们建议使用少量步骤和模型进行简短的测试指南。</span><span class="sxs-lookup"><span data-stu-id="eb214-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="eb214-212">如果你想要开始了解指南的创作，请从 [创作概述](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)开始。</span><span class="sxs-lookup"><span data-stu-id="eb214-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="eb214-213">若要获取快速跟踪概述，请观看此视频。</span><span class="sxs-lookup"><span data-stu-id="eb214-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="eb214-214">可选：展台模式</span><span class="sxs-lookup"><span data-stu-id="eb214-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="eb214-215">展台模式是一种模式，使 IT 管理员能够将 "开始" 菜单的 UI 配置为仅显示单个应用程序或应用程序的选择。</span><span class="sxs-lookup"><span data-stu-id="eb214-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="eb214-216">展台还可以应用于特定用户、组或设备级别;在某些情况下，从展台排除某些用户仍允许他们访问常规开始菜单。</span><span class="sxs-lookup"><span data-stu-id="eb214-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="eb214-217">展台模式包含多个不同的变量，可在范围和配置中进行设置，以及将展台部署到 HoloLens 的方法。</span><span class="sxs-lookup"><span data-stu-id="eb214-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="eb214-218">由于所有这些变量的原因，展台模式将在本指南中保留为可选，并且不会被视为 _可选_ 。</span><span class="sxs-lookup"><span data-stu-id="eb214-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="eb214-219">如果你认为你的业务需要将可用应用限制为用户，或者想要了解详细信息，则可随时了解如何 [将 HoloLens 设置为展台](https://docs.microsoft.com/hololens/hololens-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="eb214-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](https://docs.microsoft.com/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="eb214-220">可选： WDAC</span><span class="sxs-lookup"><span data-stu-id="eb214-220">Optional: WDAC</span></span>

<span data-ttu-id="eb214-221">WDAC 允许 IT 管理员配置其设备，以阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="eb214-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="eb214-222">这不同于设备限制的方法，例如展台模式，其中用户向用户提供了一个用户界面，用于隐藏设备上的应用程序，但仍可以启动这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb214-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="eb214-223">实现 WDAC 后，应用仍会显示在 "所有应用" 列表中，但 WDAC 会阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="eb214-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="eb214-224">有关详细信息，请参阅 [使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="eb214-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="eb214-225">Windows Defender 应用程序控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="eb214-225">Windows Defender Application Control - WDAC</span></span>](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="eb214-226">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb214-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="eb214-227">企业连接部署-部署</span><span class="sxs-lookup"><span data-stu-id="eb214-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)