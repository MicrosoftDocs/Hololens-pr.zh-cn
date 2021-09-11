---
title: 管理 HoloLens 的连接终结点
description: 了解在管理和配置连接终结点的同时，如何通过 Wi-Fi 网络设置 HoloLens。
keywords: hololens, 脱机, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428574"
---
# <a name="manage-connection-endpoints-for-hololens"></a>管理 HoloLens 的连接终结点

某些 HoloLens 组件、应用和相关服务将数据传输到 Microsoft 网络终结点。 本文列出了网络配置（例如代理或防火墙）中需要允许用于这些组件正常运行的不同终结点和 URL。    

## <a name="near-offline-setup"></a>近离线设置

对于具有网络环境限制的客户，HoloLens 支持一组有限的脱机体验。 但是，HoloLens 需要网络连接才能进行初始设备设置，并且必须启用以下 URL：

| 目的 | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>终结点配置

除了上面的列表以外，要充分利用 HoloLens 功能，还需要在网络配置中启用以下终结点。


| 目的 | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD 多重身份验证                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune 和 MDM 配置                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | microsoft.com/pkiops/                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| 证书                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana 和搜索                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| 设备身份验证                               | login.live.com*                                                     |
| 设备元数据                                     | dmd.metaservices.microsoft.com                                      |
| 位置                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| 诊断数据                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| 许可                                           | licensing.mp.microsoft.com                                          |
| Microsoft 帐户                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft 正向链接重定向服务 (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| 网络连接状态指示器 (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos office365 s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| 照片应用                                          | evoke-windowsservices-tas.msedge.net                                |
| 设置                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen prod.microsoft.com                         |
| Windows 聚焦                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows 更新                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>参考

> [!NOTE]
> 如果要部署 D365 Remote Assist，必须启用 [Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)中为 SharePoint Online 和 OneDrive for Business 列出的终结点。

- [配置组织中的 Windows 诊断数据](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [管理 Windows 10 企业版版本 1903 的连接终结点](/windows/privacy/manage-windows-1903-endpoints)
- [管理从 Windows 10 操作系统组件到 Microsoft 服务的连接](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [使用 Microsoft Intune MDM 服务器管理从 Windows 10 操作系统组件到 Microsoft 服务的连接](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Intune 网络配置要求和带宽](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Microsoft Intune 的网络终结点](/intune/fundamentals/intune-endpoints)
- [Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)
- [Azure AD Connect 的先决条件](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens 限制

设置 HoloLens 后，可以在没有 Wi-Fi 连接的情况下使用它，但是脱机使用 HoloLens 时，使用 Internet 连接的应用程序功能将受到限制。
