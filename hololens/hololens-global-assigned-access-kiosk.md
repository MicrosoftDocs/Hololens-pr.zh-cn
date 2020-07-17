---
title: 全局分配的访问权限
description: 全局分配的访问权限展台 OMA-URI 使用指南
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882436"
---
# 全局分配的访问权限 – 展台

此功能配置适用于多应用展台模式的 Hololens 2 设备，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。 

> [!NOTE]
> 此功能目前仅适用于 Windows 预览体验成员版本。 如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [ Windows 预览体验成员](hololens-insider.md)版本的更多信息。
 
## 如何在 Intune 中使用此功能？ 

> [!NOTE]
> 请注意标记有 "<!-" 的区域。 这些区域将要求你根据自己的偏好进行修改。 

1.  按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：![Intune 中的全局分配访问权限](images/global-assigned-access-omauri.png)

2.  对于数值，请更新并粘贴以下内容： 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## 如何在 Windows 配置设计器中使用此功能？ 
 
1.  更新并保存上面提及的 XML 文件。 

2.  请按照[使用预配包设置单应用或多应用展台](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作，特别是“预配 程序包，步骤 2 – 向预配包添加展台配置 XML 文件”一节并参考上一步中保存的 XML 文件。 

## 我是否能够创建可全局应用至除 1 个 AAD 账户或 AAD 组之外的所有人的配置？ 

可以，请参阅下面的示例 XML blob。 如果未找到登录用户的特定用户，则全局分配的访问权限配置文件将应用于 Hololens，因此它是登录用户的默认展台模式配置。 下面是要使用的 XML blob 示例： 

> [!NOTE]
> 请注意标记有 "<!-" 的区域，这些区域将要求你根据自己的偏好进行修改。 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
