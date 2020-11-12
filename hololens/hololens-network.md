---
title: 将 HoloLens 连接到网络
description: 介绍如何使用 HoloLens 连接到 Internet 以及如何识别设备的 IP 地址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 无线, Internet, ip, ip 地址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 7932ba493f8434c0fa5fc7a0efdd4d43eedd51bd
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163032"
---
# 将 HoloLens 连接到网络

要想在 HoloLens 上进行更多操作，则必须连接到网络。 本指南将帮助你：

- 使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络
- 禁用并重新启用 WLAN

了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。

## 首次连接

首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。 如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。 确保不需要使用证书就能连接网络。 完成设置后，你可以连接到其他类型的 WLAN 网络。

在 HoloLens 2 设备上，用户也可以[使用 USB-C 以太网适配器](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接连接到 Wi-Fi，帮助协助设置设备。 设置好设备后，用户可以继续使用该适配器，或者可将设备从适配器断开，并且[在设置完毕后连接到 wi-fi](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## 设置完成后连接到 WLAN

1. 执行**开始手势**并选择**设置**。 “设置”应用将自动放置在你面前。
1. 选择**网络和 Internet** > **WLAN**。 确保 WLAN 已打开。 如果未看到你的网络，请向下滚动列表。
1. 选择一个网络，然后选择**连接**。
1. 如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。

HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。 将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：

1. 打开**开始**菜单。
1. 查看**开始**菜单左上方的 WLAN 状态。 那里将显示 WLAN 状态和已连接网络的 SSID。

## Wi-Fi 连接故障排除

如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。

在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。

## 将 HoloLens 连接到企业 Wi-Fi 网络

企业 Wi-Fi 配置文件使用可扩展的身份验证协议 (EAP) 对 Wi-Fi 连接进行身份验证。 HoloLens 企业 Wi-Fi 配置文件可以通过使用 [Windows 配置设计器](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)创建的 MDM 或预配程序包进行配置。

对于 Microsoft Intune 托管的设备，请参阅 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 了解配置说明。

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

- WLANv1Profile 架构：[[MS-GPWL]：无线 LAN 配置文件 V1 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 架构：[[MS-GPWL]：MICROSOFT EAP TLS 架构 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### EAP 疑难解答

1. 仔细检查 Wi-Fi 配置文件具有适当的设置：
   1. EAP 类型配置正确，常见 EAP 类型：EAP-TLS (13)、EAP-TTLS (21) 和 PEAP (25)。
   1. Wi-Fi SSID 名称是正确的，并且与十六进制字符串匹配。
   1. 对于 EAP-TLS，TrustedRootCA 包含服务器的受信任根 CA 证书的 SHA-1 哈希。 在 Windows 电脑上，&quot;certutil.exe -dump cert\_file\_name&quot; 命令将显示证书的 SHA-1 哈希字符串。
1. 在接入点或控制器或 AAA 服务器日志上收集网络数据包捕获，了解 EAP 会话失败的位置。
   1. 如果 HoloLens 提供的 EAP 标识不是预期的，请检查该标识是否已通过 Wi-Fi 配置文件或客户端证书正确预配。
   1. 如果服务器拒绝 HoloLens 客户端证书，请检查是否已在设备上预配了所需的客户端证书。
   1. 如果 HoloLens 拒绝服务器证书，请检查服务器根 CA 证书是否已在 HoloLens 上预配。
1. 如果企业配置文件是通过 Wi-Fi 预配程序包预配的，请考虑在 Windows 10 电脑上应用预配程序包。 如果在 Windows 10 电脑上也失败，请按照 [Windows 客户端 802.1X 身份验证疑难解答指南](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)进行操作。
1. 通过[反馈中心](https://docs.microsoft.com/hololens/hololens-feedback)向我们发送反馈。

### 其他资源：
- [从 Windows 设备导出 Wi-Fi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。 HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。 

支持的内置 VPN 协议：
- IKEv2
- L2TP
- PPTP

如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。 要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。 HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。

 VPN 可以由 MDM 通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 进行管理，并通过 [Vpnv2-CSP 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)进行设置。

参阅[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)，了解有关[如何配置 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) 的详细信息。  

### VPN（通过 UI）

VPN 默认情况下未启用，但可以通过打开“**设置**”应用并导航到“**网络和 Internet”->“VPN**”来手动启用。
1. 选择 VPN 提供商。
1. 创建连接名称。 
1. 输入服务器名称或地址。
1. 选择 VPN 类型。
1. 选择登录信息的类型。 
1. （可选）添加用户名和密码。
1. 应用 VPN 设置。 

![HoloLens VPN 设置](./images/vpn-settings-ui.jpg)

### 通过预配程序包进行 VPN 设置

> [!TIP] 
> 在我们的 Windows 全息版 20H2 中，我们修复了 VPN 连接的代理配置问题。 如果你打算使用此流程，请考虑将设备升级到此内部版本。

1. 启动 Windows 配置设计器。
1. 单击“**预配 HoloLens 设备**”，然后选择目标设备和“**下一步**”。
1. 输入程序包名称和路径。
1. 单击“**切换到高级编辑器**”。
1. 打开“**运行时设置**” -> “**ConnectivityProfiles**” -> “**VPN**” -> “**VPNSettings**”。
1. 配置 VPNProfileName
1. 选择 ProfileType：**本机**或**第三方**。
    1. 对于本机配置文件，请选择“**NativeProtocolType**”，然后配置服务器、路由策略、身份验证类型和其他设置。
    1. 对于“第三方”配置文件，配置服务器 URL、VPN 插件应用程序包系列名称（仅预定义3个）和自定义配置。
1. 导出程序包。
1. 连接 HoloLens 并将 .ppkg 文件复制到设备。 
1. 在 HoloLens 上，通过打开“开始”菜单并选择“**设置**” -> “**帐户**” -> “**访问工作单位或学校**” -> “**添加或删除预配程序包**”-> 选择你的 VPN 程序包，来应用 VPN .ppkg。


### 通过 Intune 设置 VPN
只需按照 Intune 文档开始。 按照这些步骤操作时，请记住 HoloLens 设备支持的内置 VPN 协议。 

[创建 VPN 配置文件以连接到 Intune 中的 VPN 服务器](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。

[用于使用 Intune 添加 VPN 连接的 Windows 10 和 Windows 全息设备设置](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。

完成后，请记得[分配配置文件](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。

### 通过第三方 MDM 解决方案的 VPN
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
## 在 HoloLens（第一代）上禁用 WLAN

### 在 HoloLens 上使用“设置”应用

1. 打开**开始**菜单。
1. 从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。 **设置**应用将自动放置在你面前。
1. 选择**网络和 Internet**。
1. 选择 WLAN 滑块开关将其移至**关闭**位置。 这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。

    > [!WARNING]
    > 禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。

1. 将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。 选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。

## 识别你的 HoloLens 在 WLAN 网络上的 IP 地址

### 通过使用“设置”应用

1. 打开**开始**菜单。
1. 从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。 **设置**应用将自动放置在你面前。
1. 选择**网络和 Internet**。
1. 向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   IP 地址出现在 **IPv4 地址**旁边。

### 通过使用语音命令

根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？” 然后它会显示。 对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？” Cortana 便会显示并读出你的 IP 地址。

### 通过使用 Windows 设备门户

1. 在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 导航到**网络**部分。  
   此部分将显示你的 IP 地址和其他网络信息。 通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。
