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
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640213"
---
# <a name="connect-hololens-to-a-network"></a>将 HoloLens 连接到网络

要想在 HoloLens 上进行更多操作，则必须连接到网络。 HoloLens 包含支持 802.11ac 的 2x2 Wi-Fi 无线电，将其连接到网络类似于将 Windows 10 台式机或移动设备连接到 Wi-Fi 网络。 本指南将帮助你：

- 使用 Wi-Fi、仅适用于 HoloLens 2 的网络、Wi-Fi Direct 或通过 USB-C 的以太网连接到网络
- 禁用并重新启用 Wi-Fi

阅读有关[脱机使用 HoloLens ](hololens-offline.md)的信息。

## <a name="connecting-for-the-first-time"></a>首次连接

首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。 如果在设置期间连接到 Wi-Fi 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。 另外确认网络不需要使用证书进行连接。 完成设置后，你可以连接到其他类型的 Wi-Fi 网络。

在 HoloLens 2 设备上，用户也可以[使用适用于以太网适配器的 USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) 直接连接到 Wi-Fi，帮助协助设置设备。 设置好设备后，用户可以继续使用该适配器，或者可将设备从适配器断开，并且[在设置后连接到 Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## <a name="connecting-to-wi-fi-after-setup"></a>设置完成后连接到 Wi-Fi

1. 执行“开始手势”并选择“设置”。 随即自动显示“设置”应用。
1. 选择“网络和 Internet” > “Wi-Fi”。 确保 WLAN 已打开。 如果未看到网络，请向下滚动列表。
1. 选择一个网络，然后选择“连接”。
1. 如果系统提示你输入网络密码，请键入密码，然后选择“下一步”。

![HoloLens Wi-Fi 设置](./images/hololens-2-wifi-settings.jpg)

如果要确认已连接至 Wi-Fi 网络，请在“开始”菜单中检查 Wi-Fi 状态：

1. 打开 **“开始”** 菜单。
1. 查看“开始”菜单左上方的 Wi-Fi 状态。 那里将显示 Wi-Fi 状态和已连接网络的 SSID。

> [!TIP]
> 如果 Wi-Fi 不可用，还可以[连接到手机网络和 5G 网络](hololens-cellular.md)。

> [!IMPORTANT]
> 按照设计，用户无法微调 HoloLens 2 Wi-Fi 漫游行为 - 刷新 Wi-Fi 列表的唯一方法是打开和关闭 Wi-Fi。 此操作可以防止许多问题，比如一旦超出范围，设备就会“粘”在 AP 上。

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>将 HoloLens 连接到企业 Wi-Fi 网络

企业 Wi-Fi 配置文件使用可扩展的身份验证协议 (EAP) 对 Wi-Fi 连接进行身份验证。 HoloLens 企业 Wi-Fi 配置文件可以通过使用 [Windows 配置设计器](/windows/configuration/provisioning-packages/provisioning-packages)创建的 MDM 或预配程序包进行配置。

对于 Microsoft Intune 托管的设备，请参阅 [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 了解配置说明。

若要在 WCD 中创建 Wi-Fi 预配程序包，需要预配置的 Wi-Fi 配置文件 .xml 文件。 下面是使用 EAP-TLS 身份验证的 WPA2-企业的示例 Wi-Fi 配置文件：

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


可能需要在设备上预配服务器根 CA 证书和客户端证书，具体取决于 EAP 类型。

其他资源：

- WLANv1Profile 架构：[[MS-GPWL]：无线 LAN 配置文件 v1 架构 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 架构：[[MS-GPWL]：Microsoft EAP TLS 架构 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

如果在连接到 Wi-Fi 时遇到问题，请查看[故障排除](hololens2-enterprise-troubleshooting.md#)页。

## <a name="configure-network-proxy"></a>配置网络代理

本部分介绍使用 Windows HTTP 堆栈的 HoloLens OS 和通用 Windows 平台 (UWP) 应用的网络代理。 使用非 Windows HTTP 堆栈的应用程序可能有自己的代理配置和处理。 

### <a name="proxy-configurations"></a>代理配置 

- 代理自动配置 (PAC) 脚本：一个 [PAC 文件](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file)（打开非 Microsoft 网站）包含 JavaScript 函数 FindProxyForURL(url, host)。 
- 静态代理：Server:Port 形式。  
- Web 代理自动发现协议 (WPAD)：通过 DHCP 或 DNS 提供代理配置文件的 URL。 

### <a name="proxy-provisioning-methods"></a>代理预配方法 
预配代理的方法有以下三种：

 

1.  设置 UI： 
    1. 每用户代理（20H2 或早期版本）：
        1. 打开“开始”菜单，然后选择设置。
        2. 选择“网络和 Internet”，然后选择左侧菜单上的“代理”。
        3. 向下滚动到“手动代理设置”，并将“使用代理服务器”切换到“打开”。
        4. 输入代理服务器的 IP 地址。
        5. 输入端口号。
        6. 单击“保存”。
      1. Wi-Fi 代理（21H1 或更高版本）：
          1. 打开“开始”菜单并转到 Wi-Fi 网络的“属性”页。
          1. 向下滚动到“代理”
          1. 更改为“手动设置”
          1. 输入代理服务器的 IP 地址。
          1. 输入端口号。
          1. 单击“应用”。
        
 2. **MDM** 
     1. Intune - 使用这些[步骤](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)在 Intune 中配置代理。 需要滚动到此部分底部。
     1. 其他第三方 MDM 解决方案 - 使用 [WiFi CSP](/windows/client-management/mdm/wifi-csp)。

3. **PPKG** 
    1. 打开 Windows 配置设计器
    1. 单击“高级预配”，输入新项目的名称，然后单击“下一步”。
    1. 选择“Windows 全息版(HoloLens 2)”，然后单击“下一步”。
    1. 导入 PPKG（可选）并单击“完成”。
    1. 展开“运行时设置”->“连接性配置文件”->“WLAN”->“WLAN 代理”。
    1. 输入 Wi-Fi 网络的 SSID，并单击“添加”。
    1. 在左窗口选择 Wi-Fi 网络，并输入所需的自定义项。 在左侧菜单中，启用的自定义将以粗体显示。
    1. 单击“保存并退出”。
    1. 将预配程序包[应用](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)于 HoloLens。

[CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) 支持 Microsoft Intune 和非 Microsoft MDM 服务提供商中 Windows 10 的许多管理任务和策略。 还可以使用 [Windows 配置设计器](/windows/configuration/provisioning-packages/provisioning-install-icd)来创建[预配程序包](/windows/configuration/provisioning-packages/provisioning-packages)，并将其应用于 HoloLens 2。
最可能应用于你的 HoloLens 2 的 CSP 是：

- [WiFi CSP](/windows/client-management/mdm/wifi-csp)：每个配置文件 Wi-Fi 代理 

[HoloLens 设备支持的其他 CSP](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。 HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。 

支持的内置 VPN 协议：
- IKEv2
- L2TP
- PPTP

如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。 要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。 HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。

 MDM 可通过 [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 来管理 VPN，并通过 [Vpnv2-csp 策略](/windows/client-management/mdm/vpnv2-csp) 进行设置。

通过[这些指南](/windows/security/identity-protection/vpn/vpn-guide)详细了解[如何配置 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。  

### <a name="vpn-via-ui"></a>VPN（通过 UI）

VPN 默认情况下未启用，但可以通过打开“设置”应用并导航到“网络和 Internet”->“VPN”来手动启用。
1. 选择 VPN 提供商。
1. 创建连接名称。 
1. 输入服务器名称或地址。
1. 选择 VPN 类型。
1. 选择登录信息的类型。 
1. （可选）添加用户名和密码。
1. 应用 VPN 设置。 

![HoloLens VPN 设置](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>通过预配程序包进行 VPN 设置

> [!TIP] 
> 在我们的 Windows 全息版 20H2 中，我们修复了 VPN 连接的代理配置问题。 如果你打算使用此流程，请考虑将设备升级到此内部版本。

1. 启动 Windows 配置设计器。
1. 单击“预配 HoloLens 设备”，然后选择“目标设备”和“下一步”。
1. 输入程序包名称和路径。
1. 单击“切换到高级编辑器”。
1. 打开“运行时设置” -> “ConnectivityProfiles” -> “VPN” -> “VPNSettings”。
1. 配置 VPNProfileName
1. 选择 ProfileType：“本机”或“第三方”。
    1. 对于“本机”配置文件，请选择“NativeProtocolType”，然后配置服务器、路由策略、身份验证类型和其他设置。
    1. 对于“第三方”配置文件，配置服务器 URL、VPN 插件应用程序包系列名称（仅预定义 3 个）和自定义配置。
1. 导出程序包。
1. 连接 HoloLens 并将 .ppkg 文件复制到设备。 
1. 在 HoloLens 上，通过打开“开始”菜单并选择“设置” -> “帐户” -> “访问工作或学校帐户”  -> “添加或删除预配程序包”-> 选择 VPN 包来应用 VPN .ppkg。


### <a name="setting-up-vpn-via-intune"></a>通过 Intune 设置 VPN
只需按照 Intune 文档开始。 按照这些步骤操作时，请记住 HoloLens 设备支持的内置 VPN 协议。 

[在 Intune 中创建 VPN 配置文件以连接到 VPN 服务器](/mem/intune/configuration/vpn-settings-configure)。

[使用 Intune 添加 VPN 连接的 Windows 10 和 Windows 全息版设备](/mem/intune/configuration/vpn-settings-windows-10)。

完成后，请记得[分配配置文件](/mem/intune/configuration/device-profile-assign)。

### <a name="vpn-via-3rd-party-mdm-solutions"></a>通过第三方 MDM 解决方案的 VPN
第三方 VPN 连接示例：
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

本机 IKEv2 VPN 示例：
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>在 HoloLens (第一代)上禁用 Wi-Fi

### <a name="using-the-settings-app-on-hololens"></a>在 HoloLens 上使用“设置”应用

1. 打开 **“开始”** 菜单。
1. 从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。 随即自动显示“设置”应用。
1. 选择“网络和 Internet”。
1. 选择 Wi-Fi 滑块开关将其移至“关闭”位置。 这将关闭 Wi-Fi 无线电收发器的射频器件，并禁用 HoloLens 上的所有 Wi-Fi 功能。

    > [!WARNING]
    > 禁用 Wi-Fi 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。

1. 将滑块开关移至“打开”位置，打开 Wi-Fi 无线电收发器，并在 Microsoft HoloLens 上恢复 Wi-Fi 功能。 选定的 Wi-Fi 无线电收发器状态（“打开”或“关闭”）将在重启后保持原状态。

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>识别你的 HoloLens 在 Wi-Fi 网络上的 IP 地址

### <a name="by-using-the-settings-app"></a>通过使用“设置”应用

1. 打开 **“开始”** 菜单。
1. 从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。 随即自动显示“设置”应用。
1. 选择“网络和 Internet”。
1. 向下滚动到可用 Wi-Fi 网络列表下方，选择“硬件属性”。

    ![Wi-Fi 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   IP 地址显示在“IPv4 地址”旁。

### <a name="by-using-voice-commands"></a>通过使用语音命令

根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？” 然后它会显示。 对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？” Cortana 便会显示并读出你的 IP 地址。

### <a name="by-using-windows-device-portal"></a>通过使用 Windows 设备门户

1. 在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 导航到“网络”部分。  
   此部分将显示你的 IP 地址和其他网络信息。 通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。

## <a name="change-ip-address-to-static-address"></a>将 IP 地址更改为静态地址
### <a name="by-using-settings"></a>通过使用设置
 
1. 打开 **“开始”** 菜单。
1. 从“开始”或“开始”菜单左侧的“所有应用”列表中选择“设置”应用。 随即自动显示“设置”应用。
1. 选择“网络和 Internet”。
1. 向下滚动到可用 Wi-Fi 网络列表下方，选择“硬件属性”。
1. 在“编辑 IP 设置”窗口中，将第一个字段更改为“手动”。
1. 在其余字段中输入所需的 IP 配置，然后单击“保存”。

### <a name="by-using-windows-device-portal"></a>通过使用 Windows 设备门户

1. 在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 导航到“网络”部分。
1. 选择“IPv4 配置”按钮。
1. 选择“使用以下 IP 地址”并输入所需的 TCP/IP 配置。
1. 选择“使用以下 DNS 服务器地址”，并根据需要输入首选和备用 DNS 服务器地址。
1. 单击“保存” 。 
