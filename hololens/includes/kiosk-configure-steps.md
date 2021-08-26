---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859089"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune 单应用展台模板](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune 单应用展台模板

1. 创建配置文件 <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 选择展台模板 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 选择单个应用还是多个应用展台，同时为展台模式选择用户目标种类 <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. 选择要在展台模式下运行的应用 <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 将其余选项保留原样 <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 选择应将此配置文件分配到的组/设备或用户 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 查看和创建以保存配置文件
8. 从设备或 Intune 开始执行 MDM 同步，以将配置应用到设备。 通过设置-> 帐户 [从 Intune 或设备同步设备](/mem/intune/remote-actions/device-sync#sync-a-device) **-> 工作或学校 >** 选择连接的帐户 **-> 信息-> 同步**
9. 以目标用户身份登录，以体验展台。

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune 多个应用展台模板](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune 多个应用展台模板

1. 创建配置文件 <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 选择展台模板 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 选择单个应用还是多个应用展台，同时为展台模式选择用户目标种类 <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. 选择要在展台模式下运行的应用 ()  <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 将其余选项保留原样 <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 选择应将此配置文件分配到的组/设备或用户 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 查看和创建以保存配置文件
8. 从设备或 Intune 开始执行 MDM 同步，以将配置应用到设备。 通过设置-> 帐户 [从 Intune 或设备同步设备](/mem/intune/remote-actions/device-sync#sync-a-device) **-> 工作或学校 >** 选择连接的帐户 **-> 信息-> 同步**
9. 以目标用户身份登录，以体验展台。

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune 自定义模板](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune 自定义模板

1. 为所需的展台体验创建 xml 配置。 若要开始，请参阅此处的 [示例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 。

1. 创建自定义配置文件 <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. 指定自定义配置文件的名称，然后在 "配置设置" 部分中单击 "添加" 以添加 OMA URI 设置。 <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. 指定 OMA-URI 设置的名称。

    1. 在 "OMA URI" 文本框中，输入 **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. 选择 "数据类型" 作为 **字符串**。
    1. 在 "值" 文本框中，复制并粘贴分配的访问配置 xml (参阅基于方案的示例的引用链接，并根据需要在复制粘贴) 之前进行更新。
    1. 选择 "保存" 按钮以保存设置和配置。

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. 选择应将此配置文件分配到的组/设备或用户。 <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 查看并创建以保存配置文件。
1. 从设备或 Intune 开始执行 MDM 同步，以将配置应用到设备。 通过设置-> 帐户 [从 Intune 或设备同步设备](/mem/intune/remote-actions/device-sync#sync-a-device) **-> 工作或学校 >** 选择连接的帐户 **-> 信息-> 同步**
1. 以目标用户身份登录，以体验展台。

# <a name="runtime-provisioning---multi-app"></a>[运行时预配-多个应用](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>运行时预配-多个应用

1. 为所需的展台体验创建 xml 配置。 若要开始，请参阅此处的 [示例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 。

1. 打开[Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。

1. 在起始页上，选择 "设置" "**设置" HoloLens 设备 "。** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. 选择 **"预配 HoloLens 2 设备"，** 然后选择 "下一步"。 <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. 为项目命名。 根据需要写入说明。 选择 " **完成** " 以继续。

6. 在屏幕左下角，选择 " **切换到高级编辑器"。** 通过选择 **"是"** 确认切换到高级编辑器。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 在左侧，展开 "运行时设置"，AssignedAccess，然后选择 " **MultiAppAssignedAccess**"。 <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. 选择“浏览...” 按钮打开文件资源管理器。 并选择配置的展台 xml 文件。

9. 选择 " **导出** "，然后选择 " **设置包**"。

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 将所有者类型更改为 **IT 管理员**。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. 选择“下一步”三次。  然后选择 " **生成**"。

12. 预配包生成完成后，打开 "输出位置" 文件夹。 Ppkg 文件是预配包。 可选步骤：保存项目。

13. 现在，你可以应用预配包。 您可以在[安装过程中将预配包应用到 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ，或在[安装后将设置包应用于 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。

14. 以目标用户身份登录，以体验展台。

# <a name="runtime-provisioning---single-app"></a>[运行时预配-单个应用](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>运行时预配-单个应用

1. 打开[Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。

1. 在起始页上，选择 "设置" "**设置" HoloLens 设备 "。** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. 选择 **"预配 HoloLens 2 设备"，** 然后选择 "下一步"。 <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. 为项目命名。 根据需要写入说明。 选择 " **完成** " 以继续。

5. 在屏幕左下角，选择 " **切换到高级编辑器"。** 通过选择 **"是"** 确认切换到高级编辑器。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 在左侧，展开 "运行时设置"，AssignedAccess，然后选择 " **AssignedAccessSettings**"。 <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. 在文本框中定义展台。 例如，以下是一个名为 "LocalAccount" 的本地帐户（即 "设置" 应用）的单个应用展台。
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. 选择 " **导出** "，然后选择 " **设置包**"。 <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 将所有者类型更改为 **IT 管理员**。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. 选择“下一步”三次。  然后选择 " **生成**"。

11. 预配包生成完成后，打开 "输出位置" 文件夹。 Ppkg 文件是预配包。 可选步骤：保存项目。

12. 现在，你可以应用预配包。 您可以在[安装过程中将预配包应用到 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ，或在[安装后将设置包应用于 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。