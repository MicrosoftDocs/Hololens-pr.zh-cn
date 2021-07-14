---
title: 将 HoloLens 连接到网络
description: 了解如何设置并通过 Hologens 连接到 Internet，以及如何识别设备 IP 地址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 无线, Internet, ip, ip 地址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923595"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="19d8c-104">将 HoloLens 连接到网络</span><span class="sxs-lookup"><span data-stu-id="19d8c-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="19d8c-105">要想在 HoloLens 上进行更多操作，则必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="19d8c-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="19d8c-106">HoloLens 包含支持 802.11ac 的 2x2 Wi-Fi 无线电，将其连接到网络类似于将 Windows 10 台式机或移动设备连接到 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="19d8c-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="19d8c-107">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="19d8c-107">This guide will help you:</span></span>

- <span data-ttu-id="19d8c-108">使用 Wi-Fi、仅适用于 HoloLens 2 的网络、Wi-Fi Direct 或通过 USB-C 的以太网连接到网络</span><span class="sxs-lookup"><span data-stu-id="19d8c-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="19d8c-109">禁用并重新启用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19d8c-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="19d8c-110">阅读有关[脱机使用 HoloLens ](hololens-offline.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="19d8c-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="19d8c-111">首次连接</span><span class="sxs-lookup"><span data-stu-id="19d8c-111">Connecting for the first time</span></span>

<span data-ttu-id="19d8c-112">首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="19d8c-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="19d8c-113">如果在设置期间连接到 Wi-Fi 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。</span><span class="sxs-lookup"><span data-stu-id="19d8c-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="19d8c-114">另外确认网络不需要使用证书进行连接。</span><span class="sxs-lookup"><span data-stu-id="19d8c-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="19d8c-115">完成设置后，你可以连接到其他类型的 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="19d8c-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="19d8c-116">在 HoloLens 2 设备上，用户也可以[使用适用于以太网适配器的 USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) 直接连接到 Wi-Fi，帮助协助设置设备。</span><span class="sxs-lookup"><span data-stu-id="19d8c-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="19d8c-117">设置好设备后，用户可以继续使用该适配器，或者可将设备从适配器断开，并且[在设置后连接到 Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="19d8c-118">设置完成后连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19d8c-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="19d8c-119">执行“开始手势”并选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="19d8c-120">随即自动显示“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19d8c-121">选择“网络和 Internet” > “Wi-Fi”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="19d8c-122">确保 WLAN 已打开。</span><span class="sxs-lookup"><span data-stu-id="19d8c-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="19d8c-123">如果未看到网络，请向下滚动列表。</span><span class="sxs-lookup"><span data-stu-id="19d8c-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="19d8c-124">选择一个网络，然后选择“连接”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="19d8c-125">如果系统提示你输入网络密码，请键入密码，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi 设置](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="19d8c-127">如果要确认已连接至 Wi-Fi 网络，请在“开始”菜单中检查 Wi-Fi 状态：</span><span class="sxs-lookup"><span data-stu-id="19d8c-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="19d8c-128">打开 **“开始”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="19d8c-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19d8c-129">查看“开始”菜单左上方的 Wi-Fi 状态。</span><span class="sxs-lookup"><span data-stu-id="19d8c-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="19d8c-130">那里将显示 Wi-Fi 状态和已连接网络的 SSID。</span><span class="sxs-lookup"><span data-stu-id="19d8c-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="19d8c-131">如果 Wi-Fi 不可用，还可以[连接到手机网络和 5G 网络](hololens-cellular.md)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19d8c-132">按照设计，用户无法微调 HoloLens 2 Wi-Fi 漫游行为 - 刷新 Wi-Fi 列表的唯一方法是打开和关闭 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="19d8c-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="19d8c-133">此操作可以防止许多问题，比如一旦超出范围，设备就会“粘”在 AP 上。</span><span class="sxs-lookup"><span data-stu-id="19d8c-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="19d8c-134">将 HoloLens 连接到企业 Wi-Fi 网络</span><span class="sxs-lookup"><span data-stu-id="19d8c-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="19d8c-135">企业 Wi-Fi 配置文件使用可扩展的身份验证协议 (EAP) 对 Wi-Fi 连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="19d8c-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="19d8c-136">HoloLens 企业 Wi-Fi 配置文件可以通过使用 [Windows 配置设计器](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)创建的 MDM 或预配程序包进行配置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="19d8c-137">对于 Microsoft Intune 托管的设备，请参阅 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 了解配置说明。</span><span class="sxs-lookup"><span data-stu-id="19d8c-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="19d8c-138">若要在 WCD 中创建 Wi-Fi 预配程序包，需要预配置的 Wi-Fi 配置文件 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="19d8c-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="19d8c-139">下面是使用 EAP-TLS 身份验证的 WPA2-企业的示例 Wi-Fi 配置文件：</span><span class="sxs-lookup"><span data-stu-id="19d8c-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="19d8c-140">可能需要在设备上预配服务器根 CA 证书和客户端证书，具体取决于 EAP 类型。</span><span class="sxs-lookup"><span data-stu-id="19d8c-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="19d8c-141">其他资源：</span><span class="sxs-lookup"><span data-stu-id="19d8c-141">Additional resources:</span></span>

- <span data-ttu-id="19d8c-142">WLANv1Profile 架构：[[MS-GPWL]：无线 LAN 配置文件 v1 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="19d8c-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="19d8c-143">EAP-TLS 架构：[[MS-GPWL]：Microsoft EAP TLS 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="19d8c-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="19d8c-144">如果在连接到 Wi-Fi 时遇到问题，请查看[故障排除](hololens2-enterprise-troubleshooting.md#)页。</span><span class="sxs-lookup"><span data-stu-id="19d8c-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="19d8c-145">配置网络代理</span><span class="sxs-lookup"><span data-stu-id="19d8c-145">Configure Network Proxy</span></span>

<span data-ttu-id="19d8c-146">本部分介绍使用 Windows HTTP 堆栈的 HoloLens OS 和通用 Windows 平台 (UWP) 应用的网络代理。</span><span class="sxs-lookup"><span data-stu-id="19d8c-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="19d8c-147">使用非 Windows HTTP 堆栈的应用程序可能有自己的代理配置和处理。</span><span class="sxs-lookup"><span data-stu-id="19d8c-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="19d8c-148">代理配置</span><span class="sxs-lookup"><span data-stu-id="19d8c-148">Proxy Configurations</span></span> 

- <span data-ttu-id="19d8c-149">代理自动配置 (PAC) 脚本：一个 [PAC 文件](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file)（打开非 Microsoft 网站）包含 JavaScript 函数 FindProxyForURL(url, host)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="19d8c-150">静态代理：Server:Port 形式。</span><span class="sxs-lookup"><span data-stu-id="19d8c-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="19d8c-151">Web 代理自动发现协议 (WPAD)：通过 DHCP 或 DNS 提供代理配置文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="19d8c-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="19d8c-152">代理预配方法</span><span class="sxs-lookup"><span data-stu-id="19d8c-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="19d8c-153">预配代理的方法有以下三种：</span><span class="sxs-lookup"><span data-stu-id="19d8c-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="19d8c-154">设置 UI：</span><span class="sxs-lookup"><span data-stu-id="19d8c-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="19d8c-155">每用户代理（20H2 或早期版本）：</span><span class="sxs-lookup"><span data-stu-id="19d8c-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="19d8c-156">打开“开始”菜单，然后选择设置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="19d8c-157">选择“网络和 Internet”，然后选择左侧菜单上的“代理”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="19d8c-158">向下滚动到“手动代理设置”，并将“使用代理服务器”切换到“打开”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="19d8c-159">输入代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="19d8c-160">输入端口号。</span><span class="sxs-lookup"><span data-stu-id="19d8c-160">Enter the port number.</span></span>
        6. <span data-ttu-id="19d8c-161">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-161">Click Save.</span></span>
      1. <span data-ttu-id="19d8c-162">Wi-Fi 代理（21H1 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="19d8c-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="19d8c-163">打开“开始”菜单并转到 Wi-Fi 网络的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="19d8c-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="19d8c-164">向下滚动到“代理”</span><span class="sxs-lookup"><span data-stu-id="19d8c-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="19d8c-165">更改为“手动设置”</span><span class="sxs-lookup"><span data-stu-id="19d8c-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="19d8c-166">输入代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="19d8c-167">输入端口号。</span><span class="sxs-lookup"><span data-stu-id="19d8c-167">Enter the port number.</span></span>
          1. <span data-ttu-id="19d8c-168">单击“应用”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="19d8c-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="19d8c-169">**MDM**</span></span> 
     1. <span data-ttu-id="19d8c-170">Intune - 使用这些[步骤](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)在 Intune 中配置代理。</span><span class="sxs-lookup"><span data-stu-id="19d8c-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="19d8c-171">需要滚动到此部分底部。</span><span class="sxs-lookup"><span data-stu-id="19d8c-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="19d8c-172">其他第三方 MDM 解决方案 - 使用 [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="19d8c-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="19d8c-173">**PPKG**</span></span> 
    1. <span data-ttu-id="19d8c-174">打开 Windows 配置设计器</span><span class="sxs-lookup"><span data-stu-id="19d8c-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="19d8c-175">单击“高级预配”，输入新项目的名称，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="19d8c-176">选择“Windows 全息版(HoloLens 2)”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="19d8c-177">导入 PPKG（可选）并单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="19d8c-178">展开“运行时设置”->“连接性配置文件”->“WLAN”->“WLAN 代理”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="19d8c-179">输入 Wi-Fi 网络的 SSID，并单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="19d8c-180">在左窗口选择 Wi-Fi 网络，并输入所需的自定义项。</span><span class="sxs-lookup"><span data-stu-id="19d8c-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="19d8c-181">在左侧菜单中，启用的自定义将以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="19d8c-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="19d8c-182">单击“保存并退出”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="19d8c-183">将预配程序包[应用](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="19d8c-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="19d8c-184">[CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) 支持 Microsoft Intune 和非 Microsoft MDM 服务提供商中 Windows 10 的许多管理任务和策略。</span><span class="sxs-lookup"><span data-stu-id="19d8c-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="19d8c-185">还可以使用 [Windows 配置设计器](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd)来创建[预配程序包](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)，并将其应用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="19d8c-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="19d8c-186">最可能应用于你的 HoloLens 2 的 CSP 是：</span><span class="sxs-lookup"><span data-stu-id="19d8c-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="19d8c-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)：每个配置文件 Wi-Fi 代理</span><span class="sxs-lookup"><span data-stu-id="19d8c-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="19d8c-188">HoloLens 设备支持的其他 CSP</span><span class="sxs-lookup"><span data-stu-id="19d8c-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="19d8c-189">VPN</span><span class="sxs-lookup"><span data-stu-id="19d8c-189">VPN</span></span>
<span data-ttu-id="19d8c-190">VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。</span><span class="sxs-lookup"><span data-stu-id="19d8c-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="19d8c-191">HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。</span><span class="sxs-lookup"><span data-stu-id="19d8c-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="19d8c-192">支持的内置 VPN 协议：</span><span class="sxs-lookup"><span data-stu-id="19d8c-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="19d8c-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="19d8c-193">IKEv2</span></span>
- <span data-ttu-id="19d8c-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="19d8c-194">L2TP</span></span>
- <span data-ttu-id="19d8c-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="19d8c-195">PPTP</span></span>

<span data-ttu-id="19d8c-196">如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。</span><span class="sxs-lookup"><span data-stu-id="19d8c-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="19d8c-197">要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。</span><span class="sxs-lookup"><span data-stu-id="19d8c-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="19d8c-198">HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。</span><span class="sxs-lookup"><span data-stu-id="19d8c-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="19d8c-199">MDM 可通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 来管理 VPN，并通过 [Vpnv2-csp 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 进行设置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="19d8c-200">通过[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)详细了解[如何配置 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="19d8c-201">VPN（通过 UI）</span><span class="sxs-lookup"><span data-stu-id="19d8c-201">VPN via UI</span></span>

<span data-ttu-id="19d8c-202">VPN 默认情况下未启用，但可以通过打开“设置”应用并导航到“网络和 Internet”->“VPN”来手动启用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="19d8c-203">选择 VPN 提供商。</span><span class="sxs-lookup"><span data-stu-id="19d8c-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="19d8c-204">创建连接名称。</span><span class="sxs-lookup"><span data-stu-id="19d8c-204">Create a connection name.</span></span> 
1. <span data-ttu-id="19d8c-205">输入服务器名称或地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="19d8c-206">选择 VPN 类型。</span><span class="sxs-lookup"><span data-stu-id="19d8c-206">Select the VPN type.</span></span>
1. <span data-ttu-id="19d8c-207">选择登录信息的类型。</span><span class="sxs-lookup"><span data-stu-id="19d8c-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="19d8c-208">（可选）添加用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="19d8c-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="19d8c-209">应用 VPN 设置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-209">Apply the VPN settings.</span></span> 

![HoloLens VPN 设置](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="19d8c-211">通过预配程序包进行 VPN 设置</span><span class="sxs-lookup"><span data-stu-id="19d8c-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="19d8c-212">在我们的 Windows 全息版 20H2 中，我们修复了 VPN 连接的代理配置问题。</span><span class="sxs-lookup"><span data-stu-id="19d8c-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="19d8c-213">如果你打算使用此流程，请考虑将设备升级到此内部版本。</span><span class="sxs-lookup"><span data-stu-id="19d8c-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="19d8c-214">启动 Windows 配置设计器。</span><span class="sxs-lookup"><span data-stu-id="19d8c-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="19d8c-215">单击“预配 HoloLens 设备”，然后选择“目标设备”和“下一步”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="19d8c-216">输入程序包名称和路径。</span><span class="sxs-lookup"><span data-stu-id="19d8c-216">Enter package name and path.</span></span>
1. <span data-ttu-id="19d8c-217">单击“切换到高级编辑器”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="19d8c-218">打开“运行时设置” -> “ConnectivityProfiles” -> “VPN” -> “VPNSettings”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="19d8c-219">配置 VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="19d8c-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="19d8c-220">选择 ProfileType：“本机”或“第三方”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="19d8c-221">对于“本机”配置文件，请选择“NativeProtocolType”，然后配置服务器、路由策略、身份验证类型和其他设置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="19d8c-222">对于“第三方”配置文件，配置服务器 URL、VPN 插件应用程序包系列名称（仅预定义 3 个）和自定义配置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="19d8c-223">导出程序包。</span><span class="sxs-lookup"><span data-stu-id="19d8c-223">Export your package.</span></span>
1. <span data-ttu-id="19d8c-224">连接 HoloLens 并将 .ppkg 文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="19d8c-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="19d8c-225">在 HoloLens 上，通过打开“开始”菜单并选择“设置” -> “帐户” -> “访问工作或学校帐户”  -> “添加或删除预配程序包”-> 选择 VPN 包来应用 VPN .ppkg。</span><span class="sxs-lookup"><span data-stu-id="19d8c-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="19d8c-226">通过 Intune 设置 VPN</span><span class="sxs-lookup"><span data-stu-id="19d8c-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="19d8c-227">只需按照 Intune 文档开始。</span><span class="sxs-lookup"><span data-stu-id="19d8c-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="19d8c-228">按照这些步骤操作时，请记住 HoloLens 设备支持的内置 VPN 协议。</span><span class="sxs-lookup"><span data-stu-id="19d8c-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="19d8c-229">[在 Intune 中创建 VPN 配置文件以连接到 VPN 服务器](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="19d8c-230">[使用 Intune 添加 VPN 连接的 Windows 10 和 Windows 全息版设备](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="19d8c-231">完成后，请记得[分配配置文件](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="19d8c-232">通过第三方 MDM 解决方案的 VPN</span><span class="sxs-lookup"><span data-stu-id="19d8c-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="19d8c-233">第三方 VPN 连接示例：</span><span class="sxs-lookup"><span data-stu-id="19d8c-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="19d8c-234">本机 IKEv2 VPN 示例：</span><span class="sxs-lookup"><span data-stu-id="19d8c-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="19d8c-235">在 HoloLens (第一代)上禁用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19d8c-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="19d8c-236">在 HoloLens 上使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="19d8c-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="19d8c-237">打开 **“开始”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="19d8c-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19d8c-238">从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="19d8c-239">随即自动显示“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19d8c-240">选择“网络和 Internet”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="19d8c-241">选择 Wi-Fi 滑块开关将其移至“关闭”位置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="19d8c-242">这将关闭 Wi-Fi 无线电收发器的射频器件，并禁用 HoloLens 上的所有 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="19d8c-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="19d8c-243">禁用 Wi-Fi 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="19d8c-244">将滑块开关移至“打开”位置，打开 Wi-Fi 无线电收发器，并在 Microsoft HoloLens 上恢复 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="19d8c-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="19d8c-245">选定的 Wi-Fi 无线电收发器状态（“打开”或“关闭”）将在重启后保持原状态。</span><span class="sxs-lookup"><span data-stu-id="19d8c-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="19d8c-246">识别你的 HoloLens 在 Wi-Fi 网络上的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="19d8c-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="19d8c-247">通过使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="19d8c-247">By using the Settings app</span></span>

1. <span data-ttu-id="19d8c-248">打开 **“开始”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="19d8c-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19d8c-249">从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="19d8c-250">随即自动显示“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19d8c-251">选择“网络和 Internet”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="19d8c-252">向下滚动到可用 Wi-Fi 网络列表下方，选择“硬件属性”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="19d8c-254">IP 地址显示在“IPv4 地址”旁。</span><span class="sxs-lookup"><span data-stu-id="19d8c-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="19d8c-255">通过使用语音命令</span><span class="sxs-lookup"><span data-stu-id="19d8c-255">By using voice commands</span></span>

<span data-ttu-id="19d8c-256">根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="19d8c-257">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="19d8c-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="19d8c-258">然后它会显示。</span><span class="sxs-lookup"><span data-stu-id="19d8c-258">and it will be displayed.</span></span> <span data-ttu-id="19d8c-259">对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="19d8c-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="19d8c-260">Cortana 便会显示并读出你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="19d8c-261">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="19d8c-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="19d8c-262">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="19d8c-263">导航到“网络”部分。</span><span class="sxs-lookup"><span data-stu-id="19d8c-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="19d8c-264">此部分将显示你的 IP 地址和其他网络信息。</span><span class="sxs-lookup"><span data-stu-id="19d8c-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="19d8c-265">通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="19d8c-266">将 IP 地址更改为静态地址</span><span class="sxs-lookup"><span data-stu-id="19d8c-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="19d8c-267">通过使用设置</span><span class="sxs-lookup"><span data-stu-id="19d8c-267">By using Settings</span></span>
 
1. <span data-ttu-id="19d8c-268">打开 **“开始”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="19d8c-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19d8c-269">从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="19d8c-270">随即自动显示“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="19d8c-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19d8c-271">选择“网络和 Internet”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="19d8c-272">向下滚动到可用 Wi-Fi 网络列表下方，选择“硬件属性”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="19d8c-273">在“编辑 IP 设置”窗口中，将第一个字段更改为“手动”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="19d8c-274">在其余字段中输入所需的 IP 配置，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="19d8c-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="19d8c-275">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="19d8c-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="19d8c-276">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="19d8c-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="19d8c-277">导航到“网络”部分。</span><span class="sxs-lookup"><span data-stu-id="19d8c-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="19d8c-278">选择“IPv4 配置”按钮。</span><span class="sxs-lookup"><span data-stu-id="19d8c-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="19d8c-279">选择“使用以下 IP 地址”并输入所需的 TCP/IP 配置。</span><span class="sxs-lookup"><span data-stu-id="19d8c-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="19d8c-280">选择“使用以下 DNS 服务器地址”，并根据需要输入首选和备用 DNS 服务器地址。</span><span class="sxs-lookup"><span data-stu-id="19d8c-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="19d8c-281">单击“保存” 。</span><span class="sxs-lookup"><span data-stu-id="19d8c-281">Click **Save**.</span></span> 
