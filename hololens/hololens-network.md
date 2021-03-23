---
title: 将 HoloLens 连接到网络
description: 了解如何设置并通过 Hologens 连接到 internet，以及如何识别设备 IP 地址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 无线, Internet, ip, ip 地址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442585"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="3610c-104">将 HoloLens 连接到网络</span><span class="sxs-lookup"><span data-stu-id="3610c-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="3610c-105">要想在 HoloLens 上进行更多操作，则必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="3610c-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="3610c-106">HoloLens 包含支持 802.11ac 的 2x2 Wi-Fi 无线电，将其连接到网络类似于将 Windows 10 台式机或移动设备连接到 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="3610c-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="3610c-107">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="3610c-107">This guide will help you:</span></span>

- <span data-ttu-id="3610c-108">使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络</span><span class="sxs-lookup"><span data-stu-id="3610c-108">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="3610c-109">禁用并重新启用 WLAN</span><span class="sxs-lookup"><span data-stu-id="3610c-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="3610c-110">了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="3610c-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="3610c-111">首次连接</span><span class="sxs-lookup"><span data-stu-id="3610c-111">Connecting for the first time</span></span>

<span data-ttu-id="3610c-112">首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="3610c-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="3610c-113">如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。</span><span class="sxs-lookup"><span data-stu-id="3610c-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="3610c-114">另外确认网络不需要使用证书进行连接。</span><span class="sxs-lookup"><span data-stu-id="3610c-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="3610c-115">完成设置后，你可以连接到其他类型的 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="3610c-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="3610c-116">在 HoloLens 2 设备上，用户也可以[使用 USB-C 以太网适配器](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接连接到 Wi-Fi，帮助协助设置设备。</span><span class="sxs-lookup"><span data-stu-id="3610c-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="3610c-117">设置好设备后，用户可以继续使用该适配器，或者可将设备从适配器断开，并且[在设置完毕后连接到 Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="3610c-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="3610c-118">设置完成后连接到 WLAN</span><span class="sxs-lookup"><span data-stu-id="3610c-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="3610c-119">执行**开始手势**并选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="3610c-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="3610c-120">“设置”应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="3610c-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3610c-121">选择**网络和 Internet** > **WLAN**。</span><span class="sxs-lookup"><span data-stu-id="3610c-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="3610c-122">确保 WLAN 已打开。</span><span class="sxs-lookup"><span data-stu-id="3610c-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="3610c-123">如果未看到你的网络，请向下滚动列表。</span><span class="sxs-lookup"><span data-stu-id="3610c-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="3610c-124">选择一个网络，然后选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="3610c-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="3610c-125">如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3610c-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens WLAN 设置](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="3610c-127">如果要确认已连接至 Wi-Fi 网络，请在**开始**菜单中检查 Wi-Fi 状态：</span><span class="sxs-lookup"><span data-stu-id="3610c-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="3610c-128">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="3610c-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3610c-129">查看**开始**菜单左上方的 WLAN 状态。</span><span class="sxs-lookup"><span data-stu-id="3610c-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="3610c-130">那里将显示 WLAN 状态和已连接网络的 SSID。</span><span class="sxs-lookup"><span data-stu-id="3610c-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="3610c-131">如果 Wi-Fi 不可用，还可以 [连接到手机网络和 5G 网络](https://docs.microsoft.com/hololens/hololens-cellular)。</span><span class="sxs-lookup"><span data-stu-id="3610c-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3610c-132">根据设计，用户无法微调 HoloLens 2 Wi-Fi 漫游行为 - 刷新 **Wi-Fi**列表的唯一方法就是将 Wi-Fi 切换为关闭和打开。</span><span class="sxs-lookup"><span data-stu-id="3610c-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="3610c-133">此操作可以防止出现许多问题，例如一旦设备超出范围，设备仍可以“卡在” AP上。</span><span class="sxs-lookup"><span data-stu-id="3610c-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="3610c-134">Wi-Fi 连接故障排除</span><span class="sxs-lookup"><span data-stu-id="3610c-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="3610c-135">如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。</span><span class="sxs-lookup"><span data-stu-id="3610c-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="3610c-136">在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。</span><span class="sxs-lookup"><span data-stu-id="3610c-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="3610c-137">将 HoloLens 连接到企业 Wi-Fi 网络</span><span class="sxs-lookup"><span data-stu-id="3610c-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="3610c-138">企业 Wi-Fi 配置文件使用可扩展的身份验证协议 (EAP) 对 Wi-Fi 连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3610c-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="3610c-139">HoloLens 企业 Wi-Fi 配置文件可以通过使用 [Windows 配置设计器](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)创建的 MDM 或预配程序包进行配置。</span><span class="sxs-lookup"><span data-stu-id="3610c-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="3610c-140">对于 Microsoft Intune 托管的设备，请参阅 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 了解配置说明。</span><span class="sxs-lookup"><span data-stu-id="3610c-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="3610c-141">若要在 WCD 中创建 Wi-Fi 预配程序包，需要预配置的 Wi-Fi 配置文件 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="3610c-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="3610c-142">下面是使用 EAP-TLS 身份验证的 WPA2-企业的示例 Wi-Fi 配置文件：</span><span class="sxs-lookup"><span data-stu-id="3610c-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="3610c-143">可能需要在设备上预配服务器根 CA 证书和客户端证书，具体取决于 EAP 类型。</span><span class="sxs-lookup"><span data-stu-id="3610c-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="3610c-144">其他资源：</span><span class="sxs-lookup"><span data-stu-id="3610c-144">Additional resources:</span></span>

- <span data-ttu-id="3610c-145">WLANv1Profile 架构：[[MS-GPWL]：无线 LAN 配置文件 V1 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="3610c-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="3610c-146">EAP-TLS 架构：[[MS-GPWL]：MICROSOFT EAP TLS 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="3610c-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <a name="eap-troubleshooting"></a><span data-ttu-id="3610c-147">EAP 疑难解答</span><span class="sxs-lookup"><span data-stu-id="3610c-147">EAP Troubleshooting</span></span>

1. <span data-ttu-id="3610c-148">仔细检查 Wi-Fi 配置文件具有适当的设置：</span><span class="sxs-lookup"><span data-stu-id="3610c-148">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="3610c-149">EAP 类型配置正确，常见 EAP 类型：EAP-TLS (13)、EAP-TTLS (21) 和 PEAP (25)。</span><span class="sxs-lookup"><span data-stu-id="3610c-149">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="3610c-150">Wi-Fi SSID 名称是正确的，并且与十六进制字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="3610c-150">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="3610c-151">对于 EAP-TLS，TrustedRootCA 包含服务器的受信任根 CA 证书的 SHA-1 哈希。</span><span class="sxs-lookup"><span data-stu-id="3610c-151">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="3610c-152">在 Windows 电脑上，&quot;certutil.exe -dump cert\_file\_name&quot; 命令将显示证书的 SHA-1 哈希字符串。</span><span class="sxs-lookup"><span data-stu-id="3610c-152">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="3610c-153">在接入点或控制器或 AAA 服务器日志上收集网络数据包捕获，了解 EAP 会话失败的位置。</span><span class="sxs-lookup"><span data-stu-id="3610c-153">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="3610c-154">如果 HoloLens 提供的 EAP 标识不是预期的，请检查该标识是否已通过 Wi-Fi 配置文件或客户端证书正确预配。</span><span class="sxs-lookup"><span data-stu-id="3610c-154">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="3610c-155">如果服务器拒绝 HoloLens 客户端证书，请检查是否已在设备上预配了所需的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="3610c-155">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="3610c-156">如果 HoloLens 拒绝服务器证书，请检查服务器根 CA 证书是否已在 HoloLens 上预配。</span><span class="sxs-lookup"><span data-stu-id="3610c-156">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="3610c-157">如果企业配置文件是通过 Wi-Fi 预配程序包预配的，请考虑在 Windows 10 电脑上应用预配程序包。</span><span class="sxs-lookup"><span data-stu-id="3610c-157">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="3610c-158">如果在 Windows 10 电脑上也失败，请按照 [Windows 客户端 802.1X 身份验证疑难解答指南](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)进行操作。</span><span class="sxs-lookup"><span data-stu-id="3610c-158">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="3610c-159">通过[反馈中心](https://docs.microsoft.com/hololens/hololens-feedback)向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="3610c-159">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3610c-160">其他资源：</span><span class="sxs-lookup"><span data-stu-id="3610c-160">Additional resources:</span></span>
- [<span data-ttu-id="3610c-161">从 Windows 设备导出 Wi-Fi 设置</span><span class="sxs-lookup"><span data-stu-id="3610c-161">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a><span data-ttu-id="3610c-162">VPN</span><span class="sxs-lookup"><span data-stu-id="3610c-162">VPN</span></span>
<span data-ttu-id="3610c-163">VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。</span><span class="sxs-lookup"><span data-stu-id="3610c-163">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="3610c-164">HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。</span><span class="sxs-lookup"><span data-stu-id="3610c-164">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="3610c-165">支持的内置 VPN 协议：</span><span class="sxs-lookup"><span data-stu-id="3610c-165">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="3610c-166">IKEv2</span><span class="sxs-lookup"><span data-stu-id="3610c-166">IKEv2</span></span>
- <span data-ttu-id="3610c-167">L2TP</span><span class="sxs-lookup"><span data-stu-id="3610c-167">L2TP</span></span>
- <span data-ttu-id="3610c-168">PPTP</span><span class="sxs-lookup"><span data-stu-id="3610c-168">PPTP</span></span>

<span data-ttu-id="3610c-169">如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。</span><span class="sxs-lookup"><span data-stu-id="3610c-169">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="3610c-170">要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。</span><span class="sxs-lookup"><span data-stu-id="3610c-170">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="3610c-171">HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。</span><span class="sxs-lookup"><span data-stu-id="3610c-171">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="3610c-172">VPN 可以由 MDM 通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 进行管理，并通过 [Vpnv2-CSP 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)进行设置。</span><span class="sxs-lookup"><span data-stu-id="3610c-172">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="3610c-173">参阅[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)，了解有关[如何配置 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3610c-173">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="3610c-174">VPN（通过 UI）</span><span class="sxs-lookup"><span data-stu-id="3610c-174">VPN via UI</span></span>

<span data-ttu-id="3610c-175">VPN 默认情况下未启用，但可以通过打开“**设置**”应用并导航到“**网络和 Internet”->“VPN**”来手动启用。</span><span class="sxs-lookup"><span data-stu-id="3610c-175">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="3610c-176">选择 VPN 提供商。</span><span class="sxs-lookup"><span data-stu-id="3610c-176">Select a VPN provider.</span></span>
1. <span data-ttu-id="3610c-177">创建连接名称。</span><span class="sxs-lookup"><span data-stu-id="3610c-177">Create a connection name.</span></span> 
1. <span data-ttu-id="3610c-178">输入服务器名称或地址。</span><span class="sxs-lookup"><span data-stu-id="3610c-178">Enter your server name or address.</span></span>
1. <span data-ttu-id="3610c-179">选择 VPN 类型。</span><span class="sxs-lookup"><span data-stu-id="3610c-179">Select the VPN type.</span></span>
1. <span data-ttu-id="3610c-180">选择登录信息的类型。</span><span class="sxs-lookup"><span data-stu-id="3610c-180">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="3610c-181">（可选）添加用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="3610c-181">Optionally add user name and password.</span></span>
1. <span data-ttu-id="3610c-182">应用 VPN 设置。</span><span class="sxs-lookup"><span data-stu-id="3610c-182">Apply the VPN settings.</span></span> 

![HoloLens VPN 设置](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="3610c-184">通过预配程序包进行 VPN 设置</span><span class="sxs-lookup"><span data-stu-id="3610c-184">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="3610c-185">在我们的 Windows 全息版 20H2 中，我们修复了 VPN 连接的代理配置问题。</span><span class="sxs-lookup"><span data-stu-id="3610c-185">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="3610c-186">如果你打算使用此流程，请考虑将设备升级到此内部版本。</span><span class="sxs-lookup"><span data-stu-id="3610c-186">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="3610c-187">启动 Windows 配置设计器。</span><span class="sxs-lookup"><span data-stu-id="3610c-187">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="3610c-188">单击“**预配 HoloLens 设备**”，然后选择目标设备和“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3610c-188">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="3610c-189">输入程序包名称和路径。</span><span class="sxs-lookup"><span data-stu-id="3610c-189">Enter package name and path.</span></span>
1. <span data-ttu-id="3610c-190">单击“**切换到高级编辑器**”。</span><span class="sxs-lookup"><span data-stu-id="3610c-190">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="3610c-191">打开“**运行时设置**” -> “**ConnectivityProfiles**” -> “**VPN**” -> “**VPNSettings**”。</span><span class="sxs-lookup"><span data-stu-id="3610c-191">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="3610c-192">配置 VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="3610c-192">Configure VPNProfileName</span></span>
1. <span data-ttu-id="3610c-193">选择 ProfileType：**本机**或**第三方**。</span><span class="sxs-lookup"><span data-stu-id="3610c-193">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="3610c-194">对于本机配置文件，请选择“**NativeProtocolType**”，然后配置服务器、路由策略、身份验证类型和其他设置。</span><span class="sxs-lookup"><span data-stu-id="3610c-194">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="3610c-195">对于“第三方”配置文件，配置服务器 URL、VPN 插件应用程序包系列名称（仅预定义3个）和自定义配置。</span><span class="sxs-lookup"><span data-stu-id="3610c-195">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="3610c-196">导出程序包。</span><span class="sxs-lookup"><span data-stu-id="3610c-196">Export your package.</span></span>
1. <span data-ttu-id="3610c-197">连接 HoloLens 并将 .ppkg 文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="3610c-197">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="3610c-198">在 HoloLens 上，通过打开“开始”菜单并选择“**设置**” -> “**帐户**” -> “**访问工作单位或学校**” -> “**添加或删除预配程序包**”-> 选择你的 VPN 程序包，来应用 VPN .ppkg。</span><span class="sxs-lookup"><span data-stu-id="3610c-198">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="3610c-199">通过 Intune 设置 VPN</span><span class="sxs-lookup"><span data-stu-id="3610c-199">Setting up VPN via Intune</span></span>
<span data-ttu-id="3610c-200">只需按照 Intune 文档开始。</span><span class="sxs-lookup"><span data-stu-id="3610c-200">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="3610c-201">按照这些步骤操作时，请记住 HoloLens 设备支持的内置 VPN 协议。</span><span class="sxs-lookup"><span data-stu-id="3610c-201">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="3610c-202">[创建 VPN 配置文件以连接到 Intune 中的 VPN 服务器](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="3610c-202">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="3610c-203">[用于使用 Intune 添加 VPN 连接的 Windows 10 和 Windows 全息设备设置](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="3610c-203">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="3610c-204">完成后，请记得[分配配置文件](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="3610c-204">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="3610c-205">通过第三方 MDM 解决方案的 VPN</span><span class="sxs-lookup"><span data-stu-id="3610c-205">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="3610c-206">第三方 VPN 连接示例：</span><span class="sxs-lookup"><span data-stu-id="3610c-206">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="3610c-207">本机 IKEv2 VPN 示例：</span><span class="sxs-lookup"><span data-stu-id="3610c-207">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="3610c-208">在 HoloLens（第一代）上禁用 WLAN</span><span class="sxs-lookup"><span data-stu-id="3610c-208">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="3610c-209">在 HoloLens 上使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="3610c-209">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="3610c-210">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="3610c-210">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3610c-211">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="3610c-211">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3610c-212">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="3610c-212">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3610c-213">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="3610c-213">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3610c-214">选择 WLAN 滑块开关将其移至**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="3610c-214">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="3610c-215">这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="3610c-215">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3610c-216">禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="3610c-216">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="3610c-217">将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="3610c-217">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="3610c-218">选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。</span><span class="sxs-lookup"><span data-stu-id="3610c-218">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="3610c-219">识别你的 HoloLens 在 WLAN 网络上的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3610c-219">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="3610c-220">通过使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="3610c-220">By using the Settings app</span></span>

1. <span data-ttu-id="3610c-221">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="3610c-221">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3610c-222">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="3610c-222">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3610c-223">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="3610c-223">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3610c-224">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="3610c-224">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3610c-225">向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。</span><span class="sxs-lookup"><span data-stu-id="3610c-225">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="3610c-227">IP 地址出现在 **IPv4 地址**旁边。</span><span class="sxs-lookup"><span data-stu-id="3610c-227">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="3610c-228">通过使用语音命令</span><span class="sxs-lookup"><span data-stu-id="3610c-228">By using voice commands</span></span>

<span data-ttu-id="3610c-229">根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3610c-229">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="3610c-230">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="3610c-230">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="3610c-231">然后它会显示。</span><span class="sxs-lookup"><span data-stu-id="3610c-231">and it will be displayed.</span></span> <span data-ttu-id="3610c-232">对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="3610c-232">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="3610c-233">Cortana 便会显示并读出你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3610c-233">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="3610c-234">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="3610c-234">By using Windows Device Portal</span></span>

1. <span data-ttu-id="3610c-235">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="3610c-235">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="3610c-236">导航到**网络**部分。</span><span class="sxs-lookup"><span data-stu-id="3610c-236">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="3610c-237">此部分将显示你的 IP 地址和其他网络信息。</span><span class="sxs-lookup"><span data-stu-id="3610c-237">This section displays your IP address and other network information.</span></span> <span data-ttu-id="3610c-238">通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3610c-238">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
