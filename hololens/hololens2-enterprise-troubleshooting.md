---
title: HoloLens 2 实现和托管设备故障排除
description: 企业环境中 HoloLens 2 设备的故障排除
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: 故障排除
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961496"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="f5323-104">实现和托管设备的故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="f5323-105">本文介绍如何解决与 HoloLens 2 的实现和管理有关的几个问题或回答问题。</span><span class="sxs-lookup"><span data-stu-id="f5323-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f5323-106">在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%（如可能）。</span><span class="sxs-lookup"><span data-stu-id="f5323-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="f5323-107">通过位于电源按钮下的[电池指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level)可以快速验证电池容量（无需登录到设备）。</span><span class="sxs-lookup"><span data-stu-id="f5323-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="f5323-108">EAP 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="f5323-109">Wi-Fi 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="f5323-110">网络故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="f5323-111">无法登录到以前安装的 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="f5323-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="f5323-112">更新为 Windows Holographic 21H1 后无法登录</span><span class="sxs-lookup"><span data-stu-id="f5323-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="f5323-113">Autopilot 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="f5323-114">托管 HoloLens 设备常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f5323-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="f5323-115">EAP 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="f5323-116">仔细检查 Wi-Fi 配置文件具有适当的设置：</span><span class="sxs-lookup"><span data-stu-id="f5323-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="f5323-117">EAP 类型配置正确，常见 EAP 类型：EAP-TLS (13)、EAP-TTLS (21) 和 PEAP (25)。</span><span class="sxs-lookup"><span data-stu-id="f5323-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="f5323-118">Wi-Fi SSID 名称是正确的，并且与十六进制字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="f5323-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="f5323-119">对于 EAP-TLS，TrustedRootCA 包含服务器的受信任根 CA 证书的 SHA-1 哈希。</span><span class="sxs-lookup"><span data-stu-id="f5323-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="f5323-120">在 Windows 电脑上，“certutil.exe -dump cert_file_name”命令将显示证书的 SHA-1 哈希字符串。</span><span class="sxs-lookup"><span data-stu-id="f5323-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="f5323-121">在接入点或控制器或 AAA 服务器日志上收集网络数据包捕获，了解 EAP 会话失败的位置。</span><span class="sxs-lookup"><span data-stu-id="f5323-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="f5323-122">如果 HoloLens 提供的 EAP 标识不是预期的，请检查该标识是否已通过 Wi-Fi 配置文件或客户端证书正确预配。</span><span class="sxs-lookup"><span data-stu-id="f5323-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="f5323-123">如果服务器拒绝 HoloLens 客户端证书，请检查是否已在设备上预配了所需的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="f5323-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="f5323-124">如果 HoloLens 拒绝服务器证书，请检查服务器根 CA 证书是否已在 HoloLens 上预配。</span><span class="sxs-lookup"><span data-stu-id="f5323-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="f5323-125">如果企业配置文件是通过 Wi-Fi 预配程序包预配的，请考虑在 Windows 10 电脑上应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="f5323-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="f5323-126">如果它在 Windows 10 电脑上也失败，则按照 Windows 客户端 802.1X 身份验证故障排除指南进行操作。</span><span class="sxs-lookup"><span data-stu-id="f5323-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="f5323-127">通过反馈中心向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="f5323-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="f5323-128">返回到列表</span><span class="sxs-lookup"><span data-stu-id="f5323-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="f5323-129">Wi-Fi 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="f5323-130">如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5323-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="f5323-131">确保 Wi-Fi 已打开。</span><span class="sxs-lookup"><span data-stu-id="f5323-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="f5323-132">若要进行检查，请使用“开始手势”，然后选择“设置”>“网络和 Internet”>“Wi-Fi”。</span><span class="sxs-lookup"><span data-stu-id="f5323-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="f5323-133">如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="f5323-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="f5323-134">移动以靠近路由器或接入点。</span><span class="sxs-lookup"><span data-stu-id="f5323-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="f5323-135">重启 Wi-Fi 路由器，然后重启 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f5323-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="f5323-136">请再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="f5323-136">Try connecting again.</span></span>
4. <span data-ttu-id="f5323-137">如果这些操作都不起作用，请进行检查以确保路由器使用的是最新固件。</span><span class="sxs-lookup"><span data-stu-id="f5323-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="f5323-138">你可以在制造商网站上找到此信息。</span><span class="sxs-lookup"><span data-stu-id="f5323-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="f5323-139">在设备上登录到企业或组织帐户时，如果策略由 IT 管理员配置，也可能应用移动设备管理 (MDM) 策略。</span><span class="sxs-lookup"><span data-stu-id="f5323-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="f5323-140">网络故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-140">Network Troubleshooting</span></span>
<span data-ttu-id="f5323-141">如果网络问题是在组织中成功部署和使用 HoloLens 2 的障碍，请了解两个著名的网络诊断工具 Fiddler 和 Wireshark 如何帮助你扫描、诊断和识别问题。</span><span class="sxs-lookup"><span data-stu-id="f5323-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="f5323-142">请查看此[博客](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5323-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="f5323-143">返回到列表</span><span class="sxs-lookup"><span data-stu-id="f5323-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="f5323-144">无法登录到以前安装的 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="f5323-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="f5323-145">如果你的设备以前是为其他人设置的，无论是针对客户端还是以前的员工，你都没有密码来解锁设备，你可以使用 Intune 远程[擦除](https://docs.microsoft.com/intune/remote-actions/devices-wipe)设备。</span><span class="sxs-lookup"><span data-stu-id="f5323-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="f5323-146">然后，设备本身会重新刷写。</span><span class="sxs-lookup"><span data-stu-id="f5323-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="f5323-147">擦除设备时，请确保取消选中“保留注册状态和用户帐户”。</span><span class="sxs-lookup"><span data-stu-id="f5323-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="f5323-148">返回到列表</span><span class="sxs-lookup"><span data-stu-id="f5323-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="f5323-149">更新为 Windows Holographic 21H1 后无法登录</span><span class="sxs-lookup"><span data-stu-id="f5323-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="f5323-150">症状</span><span class="sxs-lookup"><span data-stu-id="f5323-150">Symptoms</span></span>
- <span data-ttu-id="f5323-151">输入正确的 PIN 后，使用 PIN 进行登录会失败。</span><span class="sxs-lookup"><span data-stu-id="f5323-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="f5323-152">在网页上成功登录后，使用 Web 登录方法会失败。</span><span class="sxs-lookup"><span data-stu-id="f5323-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="f5323-153">设备未在 [Azure 门户](https://portal.azure.com/) ->“Azure Active Directory”->“设备”中列为“已加入 Azure AD”。</span><span class="sxs-lookup"><span data-stu-id="f5323-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="f5323-154">原因</span><span class="sxs-lookup"><span data-stu-id="f5323-154">Cause</span></span>
<span data-ttu-id="f5323-155">受影响的设备可能已从 Azure AD 租户中删除。</span><span class="sxs-lookup"><span data-stu-id="f5323-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="f5323-156">例如，发生这种情况可能是因为：</span><span class="sxs-lookup"><span data-stu-id="f5323-156">For example, this may happen because:</span></span>

- <span data-ttu-id="f5323-157">管理员或用户在 Azure 门户中或使用 PowerShell 删除设备。</span><span class="sxs-lookup"><span data-stu-id="f5323-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="f5323-158">由于不活动，已从 Azure AD 租户中删除设备。</span><span class="sxs-lookup"><span data-stu-id="f5323-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="f5323-159">对于有效托管的环境，我们通常建议 IT 管理员[从其 Azure AD 租户中删除过时的非活动设备](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)。</span><span class="sxs-lookup"><span data-stu-id="f5323-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="f5323-160">当受影响的设备在被删除后尝试再次联系 Azure AD 租户后，将无法使用 Azure AD 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f5323-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="f5323-161">此效果对于设备用户通常不可见，因为通过 PIN 缓存的登录将继续允许用户登录。</span><span class="sxs-lookup"><span data-stu-id="f5323-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="f5323-162">缓解措施</span><span class="sxs-lookup"><span data-stu-id="f5323-162">Mitigation</span></span>
<span data-ttu-id="f5323-163">目前没有办法将删除的 HoloLens 设备添加回 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="f5323-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="f5323-164">受影响的设备需要按照[刷写其设备](hololens-recovery.md#clean-reflash-the-device)上的说明重新刷写干净。</span><span class="sxs-lookup"><span data-stu-id="f5323-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="f5323-165">Autopilot 故障排除</span><span class="sxs-lookup"><span data-stu-id="f5323-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="f5323-166">以下文章可能是你了解更多信息和解决 Autopilot 问题的有用资源，但请注意，这些文章是基于Windows 10 桌面版的，并非所有信息都适用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="f5323-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="f5323-167">Windows Autopilot - 已知问题</span><span class="sxs-lookup"><span data-stu-id="f5323-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="f5323-168">Microsoft Intune 中的 Windows 设备注册问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="f5323-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="f5323-169">Windows Autopilot - 策略冲突</span><span class="sxs-lookup"><span data-stu-id="f5323-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="f5323-170">托管 HoloLens 设备常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f5323-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="f5323-171">是否可以使用 System Center Configuration Manager (SCCM) 来管理 HoloLens 设备？</span><span class="sxs-lookup"><span data-stu-id="f5323-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="f5323-172">否。</span><span class="sxs-lookup"><span data-stu-id="f5323-172">No.</span></span> <span data-ttu-id="f5323-173">必须使用 MDM 系统来管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="f5323-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="f5323-174">能否使用 Active Directory 域服务 (AD DS) 管理 HoloLens 用户帐户？</span><span class="sxs-lookup"><span data-stu-id="f5323-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="f5323-175">否。</span><span class="sxs-lookup"><span data-stu-id="f5323-175">No.</span></span> <span data-ttu-id="f5323-176">必须使用 Azure Active Directory (Azure AD) 管理 HoloLens 设备的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f5323-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="f5323-177">HoloLens 是否能够进行自动数据捕获系统 (ADCS) 自动注册？</span><span class="sxs-lookup"><span data-stu-id="f5323-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="f5323-178">否。</span><span class="sxs-lookup"><span data-stu-id="f5323-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="f5323-179">HoloLens 能否参与集成 Windows 身份验证？</span><span class="sxs-lookup"><span data-stu-id="f5323-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="f5323-180">否。</span><span class="sxs-lookup"><span data-stu-id="f5323-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="f5323-181">HoloLens 是否支持品牌？</span><span class="sxs-lookup"><span data-stu-id="f5323-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="f5323-182">否。</span><span class="sxs-lookup"><span data-stu-id="f5323-182">No.</span></span> <span data-ttu-id="f5323-183">但是，你可以使用以下方法之一来解决此问题：</span><span class="sxs-lookup"><span data-stu-id="f5323-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="f5323-184">创建一个自定义应用，然后[启用展台模式](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="f5323-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="f5323-185">自定义应用可以具有品牌，还可以启动其他应用（如 Remote Assist）。</span><span class="sxs-lookup"><span data-stu-id="f5323-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="f5323-186">将 Azure AD 中的所有用户配置文件图片更改为你的公司徽标。</span><span class="sxs-lookup"><span data-stu-id="f5323-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="f5323-187">但是，这可能并不适合所有方案。</span><span class="sxs-lookup"><span data-stu-id="f5323-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="f5323-188">HoloLens 2 提供哪些日志记录功能？</span><span class="sxs-lookup"><span data-stu-id="f5323-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="f5323-189">日志记录仅限于可以在开发或故障排除方案中捕获的跟踪，或者设备发送到 Microsoft 服务器的遥测。</span><span class="sxs-lookup"><span data-stu-id="f5323-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="f5323-190">有关保护 HoloLens 设备的问题</span><span class="sxs-lookup"><span data-stu-id="f5323-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="f5323-191">请参阅[我们的 HoloLens 2 安全信息](security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f5323-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="f5323-192">对于 HoloLens 第 1 代设备，请查看[此常见问题解答](hololens1-faq-security.md)。</span><span class="sxs-lookup"><span data-stu-id="f5323-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="f5323-193">返回到列表</span><span class="sxs-lookup"><span data-stu-id="f5323-193">Back to list</span></span>](#list)
