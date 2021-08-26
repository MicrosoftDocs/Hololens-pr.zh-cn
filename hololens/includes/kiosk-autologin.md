---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859087"
---
# <a name="non-aad-configuration"></a>[非 AAD 配置](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>非 AAD 配置

1. 创建一个预配包，其中：
    1. 将运行时设置 AssignedAccess 配置为允许访问者帐户。
    1. （可选）在 MDM (运行时设置/工作区/注册) 中注册设备，以便以后可以对其进行管理。
    1. 不创建本地帐户
2. [应用设置包](../hololens-provisioning.md)。

# <a name="aad-configuration"></a>[AAD 配置](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD 配置

为展台模式配置的 AAD 加入设备可以在登录屏幕上点击一次按钮，只登录一次访问者帐户。 登录到访问者帐户后，在从 "开始" 菜单中显式注销访问者或重新启动设备之前，该设备不会提示登录。

可以通过 [自定义 OMA URI 策略](/mem/intune/configuration/custom-settings-windows-10)来管理访问者自动登录：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 策略 | 描述 | 配置 |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 允许访问者自动登录到展台。 | 1 (是) ，0 (否，默认值为 )  |