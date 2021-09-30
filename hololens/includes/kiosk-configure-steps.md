---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220634"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune 单应用展台模板](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune 单应用展台模板

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

3. 选择单应用展台或多应用展台，并选择展台模式的目标用户类型 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. 选择要在展台模式下运行的应用 <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 将其余的选项保留原样 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 选择应该将此配置文件分配给哪些组/设备或用户 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 查看并创建以保存配置文件
8. 从设备或 Intune 开始执行 MDM 同步，以将配置应用于设备。 通过“设置”->“帐户”->“工作或学校”-> 选择连接的帐户 ->“信息”->“同步”，[从 Intune 同步设备](/mem/intune/remote-actions/device-sync#sync-a-device)或在设备上同步设备 
9. 以目标用户身份登录以体验展台。

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune 多应用展台模板](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune 多应用展台模板

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

3. 选择单应用展台或多应用展台，并选择展台模式的目标用户类型 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. 选择要在展台模式下运行的应用 <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 将其余的选项保留原样 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 选择应该将此配置文件分配给哪些组/设备或用户 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 查看并创建以保存配置文件
8. 从设备或 Intune 开始执行 MDM 同步，以将配置应用于设备。 通过“设置”->“帐户”->“工作或学校”-> 选择连接的帐户 ->“信息”->“同步”，[从 Intune 同步设备](/mem/intune/remote-actions/device-sync#sync-a-device)或在设备上同步设备 
9. 以目标用户身份登录以体验展台。

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune 自定义模板](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune 自定义模板

1. 针对所需的展台体验创建 xml 配置。 若要开始操作，请参阅此处的[示例](../hololens-kiosk-reference.md#kiosk-xml-code-samples)。

1. 创建自定义配置文件 <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. 指定自定义配置文件的名称，然后单击“配置设置”部分中的“添加”以添加 OMA-URI 设置。 <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. 指定 OMA-URI 设置的名称。

    1. 在“OMA-URI”文本框中，输入 ./Device/Vendor/MSFT/AssignedAccess/Configuration
    1. 将“数据类型”选择为“字符串”。
    1. 在“值”文本框中，复制粘贴分配的访问配置 xml（请参阅参考链接以了解基于你的场景的示例，并在复制粘贴前根据需要进行更新）。
    1. 选择“保存”按钮。保存设置和配置。

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. 选择应该将此配置文件分配给哪些组/设备或用户。 <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 查看并创建以保存配置文件。
1. 从设备或 Intune 开始执行 MDM 同步，以将配置应用于设备。 通过“设置”->“帐户”->“工作或学校”-> 选择连接的帐户 ->“信息”->“同步”，[从 Intune 同步设备](/mem/intune/remote-actions/device-sync#sync-a-device)或在设备上同步设备 
1. 以目标用户身份登录以体验展台。

# <a name="runtime-provisioning---multi-app"></a>[运行时预配 - 多应用](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>运行时预配 - 多应用

1. 针对所需的展台体验创建 xml 配置。 若要开始操作，请参阅此处的[示例](../hololens-kiosk-reference.md#kiosk-xml-code-samples)。

1. 打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。

1. 在“开始”页上，选择“预配 HoloLens 设备”。 <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. 选择“预配 HoloLens 2 设备”，然后选择“下一步”。 <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. 为项目命名。 选择性地编写说明。 选择“完成”以继续。

6. 在屏幕左下角，选择“切换到高级编辑器”。 选择“是”，确认切换到高级编辑器。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 在左侧，展开“运行时设置”的“AssignedAccess”，然后选择“MultiAppAssignedAccess”。 <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. 选择“浏览...” 按钮，打开文件资源管理器。 选择配置的展台 xml 文件。

9. 依次选择“导出”->“预配程序包” 。

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 将“所有者类型”更改为“IT 管理员”。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. 选择“下一步”三次。  然后，选择“生成”。

12. 生成预配程序包后，打开“输出位置”文件夹。 .ppkg 文件就是你的预配程序包。 可选步骤：保存你的项目。

13. 现在，可应用你的预配程序包。 可[在安装过程中将预配程序包应用于 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)，或[在安装后将预配程序包应用于 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。

14. 以目标用户身份登录以体验展台。

# <a name="runtime-provisioning---single-app"></a>[运行时预配 - 单应用](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>运行时预配 - 单应用

1. 打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。

1. 在“开始”页上，选择“预配 HoloLens 设备”。 <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. 选择“预配 HoloLens 2 设备”，然后选择“下一步”。 <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. 为项目命名。 选择性地编写说明。 选择“完成”以继续。

5. 在屏幕左下角，选择“切换到高级编辑器”。 选择“是”，确认切换到高级编辑器。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 在左侧，展开“运行时设置”的“AssignedAccess”，然后选择“AssignedAccessSettings”。 <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. 在文本框中定义你的展台。 例如，以下内容为名为 LocalAccount 的本地帐户（即“设置”应用）创建单应用展台。
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. 依次选择“导出”->“预配程序包” 。 <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 将“所有者类型”更改为“IT 管理员”。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. 选择“下一步”三次。  然后，选择“生成”。

11. 生成预配程序包后，打开“输出位置”文件夹。 .ppkg 文件就是你的预配程序包。 可选步骤：保存你的项目。

12. 现在，可应用你的预配程序包。 可[在安装过程中将预配程序包应用于 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)，或[在安装后将预配程序包应用于 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。