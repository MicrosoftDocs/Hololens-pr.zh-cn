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
# <span data-ttu-id="90eca-104">全局分配的访问权限 – 展台</span><span class="sxs-lookup"><span data-stu-id="90eca-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="90eca-105">此功能配置适用于多应用展台模式的 Hololens 2 设备，此模式适用于系统级别，与系统上的任何身份无关，并且适用于登录此设备的每个人。</span><span class="sxs-lookup"><span data-stu-id="90eca-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="90eca-106">此功能目前仅适用于 Windows 预览体验成员版本。</span><span class="sxs-lookup"><span data-stu-id="90eca-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="90eca-107">如果想在 HoloLens 发行版普遍提供此功能前对其进行试用，请阅读有关 [ Windows 预览体验成员](hololens-insider.md)版本的更多信息。</span><span class="sxs-lookup"><span data-stu-id="90eca-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="90eca-108">如何在 Intune 中使用此功能？</span><span class="sxs-lookup"><span data-stu-id="90eca-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="90eca-109">请注意标记有 "<!-" 的区域。</span><span class="sxs-lookup"><span data-stu-id="90eca-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="90eca-110">这些区域将要求你根据自己的偏好进行修改。</span><span class="sxs-lookup"><span data-stu-id="90eca-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="90eca-111">按照以下方式创建自定义 OMA URI 设备配置文件，并将其应用到 HoloLens 设备组：![Intune 中的全局分配访问权限</span><span class="sxs-lookup"><span data-stu-id="90eca-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="90eca-112">对于数值，请更新并粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="90eca-112">For value, update and paste following content:</span></span> 

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

## <span data-ttu-id="90eca-113">如何在 Windows 配置设计器中使用此功能？</span><span class="sxs-lookup"><span data-stu-id="90eca-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="90eca-114">更新并保存上面提及的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="90eca-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="90eca-115">请按照[使用预配包设置单应用或多应用展台](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)中的步骤进行操作，特别是“预配</span><span class="sxs-lookup"><span data-stu-id="90eca-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="90eca-116">程序包，步骤 2 – 向预配包添加展台配置 XML 文件”一节并参考上一步中保存的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="90eca-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="90eca-117">我是否能够创建可全局应用至除 1 个 AAD 账户或 AAD 组之外的所有人的配置？</span><span class="sxs-lookup"><span data-stu-id="90eca-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="90eca-118">可以，请参阅下面的示例 XML blob。</span><span class="sxs-lookup"><span data-stu-id="90eca-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="90eca-119">如果未找到登录用户的特定用户，则全局分配的访问权限配置文件将应用于 Hololens，因此它是登录用户的默认展台模式配置。</span><span class="sxs-lookup"><span data-stu-id="90eca-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="90eca-120">下面是要使用的 XML blob 示例：</span><span class="sxs-lookup"><span data-stu-id="90eca-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="90eca-121">请注意标记有 "<!-" 的区域，这些区域将要求你根据自己的偏好进行修改。</span><span class="sxs-lookup"><span data-stu-id="90eca-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

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
