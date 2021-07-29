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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636871"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>实现和托管设备的故障排除 

本文介绍如何解决与 HoloLens 2 的实现和管理有关的几个问题或回答问题。

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%（如可能）。 通过位于电源按钮下的[电池指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level)可以快速验证电池容量（无需登录到设备）。


<a id="list"></a>
- [EAP 故障排除](#eap-troubleshooting)
- [Wi-Fi 故障排除](#wi-fi-troubleshooting)
- [网络故障排除](#network-troubleshooting)
- [无法登录到以前安装的 HoloLens 设备](#cant-sign-in-to-a-previously-setup-hololens-device)
- [更新为 Windows Holographic 21H1 后无法登录](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot 故障排除](#autopilot-troubleshooting)
- [托管 HoloLens 设备常见问题解答](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP 故障排除
1. 仔细检查 Wi-Fi 配置文件具有适当的设置：
    - EAP 类型配置正确，常见 EAP 类型：EAP-TLS (13)、EAP-TTLS (21) 和 PEAP (25)。
    - Wi-Fi SSID 名称是正确的，并且与十六进制字符串匹配。
    - 对于 EAP-TLS，TrustedRootCA 包含服务器的受信任根 CA 证书的 SHA-1 哈希。 在 Windows 电脑上，“certutil.exe -dump cert_file_name”命令将显示证书的 SHA-1 哈希字符串。
2. 在接入点或控制器或 AAA 服务器日志上收集网络数据包捕获，了解 EAP 会话失败的位置。
    - 如果 HoloLens 提供的 EAP 标识不是预期的，请检查该标识是否已通过 Wi-Fi 配置文件或客户端证书正确预配。
    - 如果服务器拒绝 HoloLens 客户端证书，请检查是否已在设备上预配了所需的客户端证书。
    - 如果 HoloLens 拒绝服务器证书，请检查服务器根 CA 证书是否已在 HoloLens 上预配。
3. 如果企业配置文件是通过 Wi-Fi 预配程序包预配的，请考虑在 Windows 10 电脑上应用预配程序包。 如果它在 Windows 10 电脑上也失败，则按照 Windows 客户端 802.1X 身份验证故障排除指南进行操作。
4. 通过反馈中心向我们发送反馈。

[返回到列表](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi 故障排除

如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：

1. 确保 Wi-Fi 已打开。 若要进行检查，请使用“开始手势”，然后选择“设置”>“网络和 Internet”>“Wi-Fi”。 如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。
2. 移动以靠近路由器或接入点。
3. 重启 Wi-Fi 路由器，然后重启 HoloLens。 请再次尝试连接。
4. 如果这些操作都不起作用，请进行检查以确保路由器使用的是最新固件。 你可以在制造商网站上找到此信息。

在设备上登录到企业或组织帐户时，如果策略由 IT 管理员配置，也可能应用移动设备管理 (MDM) 策略。

[返回到列表](#list)

## <a name="network-troubleshooting"></a>网络故障排除
如果网络问题是在组织中成功部署和使用 HoloLens 2 的障碍，请配置 Fiddler 和/或 Wireshark 以捕获和分析 HTTP/HTTPS 流量。 

### <a name="configure-fiddler-to-capture-http-traffic"></a>配置 Fiddler 以捕获 HTTP 流量
Fiddler 是 Web 调试代理，用于解决 HTTP(S) 问题。 它捕获计算机发出的每个 HTTP 请求并记录与之相关的所有内容。 发现 HTTPS 应用的最终用户身份验证问题可提高目标 HoloLens 2 用例的生产力和效率。 

#### <a name="prerequisites"></a>必备条件
 
- HoloLens 2 设备和 PC 必须位于同一网络
- 记下 PC 的 IP 地址

#### <a name="install-and-configure-fiddler"></a>安装和配置 Fiddler

1. 在 PC 上 - [安装](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure)并启动 Fiddler。  
1. 在 PC 上 - 配置 Fiddler 以允许远程计算机连接。
    1. 转到“Fiddler 设置”->“连接”
    1. 记下 Fiddler 的监听端口（默认为 8866）
    1. 勾选“允许远程计算机连接”
    1. 点击“保存”
3. 在 HoloLens 2 上 - 将 Fiddler 配置为代理服务器<sup>1</sup>：
    1. 打开“开始”菜单，然后选择“设置”
    1. 选择“网络和 Internet”，然后选择左侧菜单上的“代理”
    1. 向下滚动到“手动代理设置”，并将“使用代理服务器”切换到“打开”
    1. 输入安装了 Fiddler 的 PC 的 IP 地址
    1. 输入先前记下的端口号（默认为 8866）
    1. 点击“保存”

<sup>1</sup> 对于内部版本 20279.1006+（预览体验成员和即将发布的版本），请按照以下步骤配置代理：
1. 打开“开始”菜单并转到 Wi-Fi 网络的“属性”页 
1. 向下滚动到“代理”
1. 更改为“手动设置”
1. 输入安装了 Fiddler 的 PC 的 IP 地址
1. 输入先前记下的端口号。 （默认为 8866）
1. 单击“应用”
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>解密来自 HoloLens 2 的 HTTPS 流量

1. 在 PC 上 - 导出 Fiddler 证书。
    1. 转到“Fiddler 设置”->“HTTPS”，并展开“高级设置”
    2. 单击“导出 Fiddler 证书”。 它将保存到桌面
    3. 将证书移至 HoloLens 2 上的 Downloads 文件夹

2.  在 HoloLens 2 上 - 导入 Fiddler 证书。
    1. 转到“设置”->“更新和安全”->“证书”
    2. 单击“安装证书”，浏览 Downloads 文件夹并选择 Fiddler 证书
    3. 将“存储位置”更改为“本地计算机”
    4. 将“证书存储”更改为“根文件夹”
    5. 选择“安装”
    6. 确认证书是否显示在证书列表中。 如果否，重复上述步骤

#### <a name="inspect-https-sessions"></a>检查 HTTP (S) 会话

在 PC 上，Fiddler 将显示 HoloLens 2 的实时 HTTP(S) 会话。 Fiddler 中的“检查者”面板可以在不同的视图中显示 HTTP(S) 请求/响应 - 例如，“原始”视图以纯文本形式显示原始请求或响应。 

### <a name="configure-wireshark-to-capture-network-traffic"></a>配置 Wireshark 以捕获网络流量
Wireshark 是网络协议分析器，用于检查进出 HoloLens 2 设备的 TCP/UDP 流量。 这样即可轻松识别经网络流向 HoloLens 2 的流量、流量多少、频率，以及某些跃点之间的延迟等。

#### <a name="prerequisites"></a>先决条件：
- PC 必须可以访问 Internet 并支持通过 Wi-Fi 在 Internet 中进行共享

#### <a name="install-and-configure-wireshark"></a>安装和配置 Wireshark
1. 在 PC 上 - 安装 [Wireshark](https://www.wireshark.org/#download) 
1. 在 PC 上 - 启用移动热点通过 Wi-Fi 共享 Internet 连接。
1. 在 PC 上 - 启动 Wireshark 并从移动热点界面捕获流量。 
1. 在 HoloLens 2 上 - 将其 Wi-Fi 网络更改为 PC 的移动热点。 HoloLens 2 IP 流量将显示在 Wireshark 中。

#### <a name="analyze-wireshark-logs"></a>分析 Wireshark 日志
Wireshark 筛选器可帮助筛选出感兴趣的数据包。 

查看原始[博客](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)。

[返回到列表](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>无法登录到以前安装的 HoloLens 设备

如果你的设备以前是为其他人设置的，无论是针对客户端还是以前的员工，你都没有密码来解锁设备，你可以使用 Intune 远程[擦除](/intune/remote-actions/devices-wipe)设备。 然后，设备本身会重新刷写。  
> [!IMPORTANT]
> 擦除设备时，请确保取消选中“保留注册状态和用户帐户”。

[返回到列表](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>更新为 Windows Holographic 21H1 后无法登录

### <a name="symptoms"></a>症状
- 输入正确的 PIN 后，使用 PIN 进行登录会失败。
- 在网页上成功登录后，使用 Web 登录方法会失败。
- 设备未在 [Azure 门户](https://portal.azure.com/) ->“Azure Active Directory”->“设备”中列为“已加入 Azure AD”。

### <a name="cause"></a>原因
受影响的设备可能已从 Azure AD 租户中删除。 例如，发生这种情况可能是因为：

- 管理员或用户在 Azure 门户中或使用 PowerShell 删除设备。
- 由于不活动，已从 Azure AD 租户中删除设备。 对于有效托管的环境，我们通常建议 IT 管理员[从其 Azure AD 租户中删除过时的非活动设备](/azure/active-directory/devices/manage-stale-devices)。

当受影响的设备在被删除后尝试再次联系 Azure AD 租户后，将无法使用 Azure AD 进行身份验证。 此效果对于设备用户通常不可见，因为通过 PIN 缓存的登录将继续允许用户登录。

### <a name="mitigation"></a>缓解措施
目前没有办法将删除的 HoloLens 设备添加回 Azure AD。 受影响的设备需要按照[刷写其设备](hololens-recovery.md#clean-reflash-the-device)上的说明重新刷写干净。

[返回到列表](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot 故障排除

以下文章可能是你了解更多信息和解决 Autopilot 问题的有用资源，但请注意，这些文章是基于Windows 10 桌面版的，并非所有信息都适用于 HoloLens：

- [Windows Autopilot - 已知问题](/mem/autopilot/known-issues)
- [Microsoft Intune 中的 Windows 设备注册问题疑难解答](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 策略冲突](/mem/autopilot/policy-conflicts)

[返回到列表](#list)

## <a name="managed-hololens-devices-faqs"></a>托管 HoloLens 设备常见问题解答

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>是否可以使用 System Center Configuration Manager (SCCM) 来管理 HoloLens 设备？

否。 必须使用 MDM 系统来管理 HoloLens 设备。

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>能否使用 Active Directory 域服务 (AD DS) 管理 HoloLens 用户帐户？

否。 必须使用 Azure Active Directory (Azure AD) 管理 HoloLens 设备的用户帐户。

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens 是否能够进行自动数据捕获系统 (ADCS) 自动注册？

否。

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens 能否参与集成 Windows 身份验证？

否。

### <a name="does-hololens-support-branding"></a>HoloLens 是否支持品牌？

否。 但是，你可以使用以下方法之一来解决此问题：

- 创建一个自定义应用，然后[启用展台模式](hololens-kiosk.md)。 自定义应用可以具有品牌，还可以启动其他应用（如 Remote Assist）。  
- 将 Azure AD 中的所有用户配置文件图片更改为你的公司徽标。 但是，这可能并不适合所有方案。

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>HoloLens 2 提供哪些日志记录功能？

日志记录仅限于可以在开发或故障排除方案中捕获的跟踪，或者设备发送到 Microsoft 服务器的遥测。

## <a name="questions-about-securing-hololens-devices"></a>有关保护 HoloLens 设备的问题

请参阅[我们的 HoloLens 2 安全信息](security-overview.md)。
对于 HoloLens 第 1 代设备，请查看[此常见问题解答](hololens1-faq-security.yml)。

[返回到列表](#list)
