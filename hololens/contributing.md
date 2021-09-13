---
title: 参与说明
description: 了解如何使用HoloLens Markdown 在 docs.microsoft.com 平台上参与GitHub文档。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031976"
---
# <a name="contributing-to-the-hololens-documentation"></a>参与HoloLens文档

欢迎使用[HoloLens文档](https://github.com/MicrosoftDocs/Hololens)！ 在此存储库创建或编辑的任何文章 **都将对公众可见。** 

HoloLens文档显示在 docs.microsoft.com 平台上，该平台将GitHub Markdown 与 Markdig 功能一同使用。 在此存储库编辑的内容将格式化为显示在 /hololens 中的样式化页面。

本页介绍参与和链接 Markdown 基础知识的基本步骤和指南。 感谢你的贡献！

## <a name="available-repos"></a>可用 repos

| 存储库名称 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 混合现实 | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| VR 友元指南 | [MicrosoftDocs/mixed-reality/用户指南](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>准备工作

如果还没有帐户，则需要创建一个GitHub[帐户](https://github.com/join)。

>[!NOTE]
>如果你是 Microsoft 员工，请GitHub Microsoft 开源门户 上的[Microsoft 别名](https://repos.opensource.microsoft.com/)。 加入 **"Microsoft"和****"MicrosoftDocs"** 组织。

在设置GitHub帐户时，我们还建议采取以下安全预防措施：
- 为[帐户 创建GitHub密码](https://github.com/settings/admin)。
- 启用 [双因素身份验证](https://github.com/settings/two_factor_authentication/configure)。
- 将 [恢复代码保存在](https://github.com/settings/auth/recovery-codes) 安全的位置。
- 更新 [公共配置文件设置](https://github.com/settings/profile)。
   - 设置你的姓名，并考虑将 *"公共电子邮件*"设置为 *"不显示我的电子邮件地址"。*
   - 建议上传个人资料图片，因为缩略图显示在你参与的文档页面上。
- 如果打算使用命令行，请考虑为 凭据管理器 Git [Windows。](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) 这样，就不需要每次贡献时都输入密码。

发布系统与 GitHub关联，因此这些步骤非常重要。 你将使用你的别名作为每篇文章的作者GitHub参与者。

## <a name="editing-an-existing-article"></a>编辑现有文章

使用以下工作流通过 Web 浏览器中的 *GitHub* 更新现有文章：

1. 导航到想要在"mixed-reality-docs"文件夹中编辑的文章。

2. 选择右上方 (铅笔图标) 编辑按钮。

   ![编辑文章。](images/editpage.png)

   这将自动从默认分支 master 分支分支可 _释放分支_。

   > [!NOTE]
   > 本文包含对 _master（Microsoft_ 不再使用的术语）的引用。 在从软件中删除该术语后，我们会将其从本文中删除。
   
3. 根据 Markdown 基础知识编辑 [文章的内容](#markdown-basics)。

4. 更新每篇文章顶部的元数据：

   * **title：** 查看文章时显示在浏览器选项卡中的页标题。 页面标题用于 SEO 和索引编制，因此除非有必要更改标题， (不过在文档公开公开之前) 。
   * **description：** 编写文章内容的简要说明，这将提升 SEO 和发现。
   * **author：** 如果你是页面的主要所有者，请在此处GitHub别名。
   * **ms.author：** 如果你是页面的主要所有者，请在此处添加 Microsoft 别名 (不需要 ，只需将别名 @microsoft.com) 。
   * **ms.date：** 如果要将主要内容添加到页面，请更新日期，但不能更新说明、格式设置、语法或拼写等修复。
   * **关键字**：关键字有助于 SEO (搜索引擎优化) 。 添加关键字，以逗号和空格分隔，这些关键字特定于你的文章，但在列表中的最后一个关键字后面没有标点符号。 无需添加适用于所有文章的全局关键字，因为这些关键字在其他地方进行管理。 
   
5. 完成文章编辑后，向下滚动并选择"建议 **文件更改"。**

6. 下一页选择" **创建拉取请求** "，将自动创建的分支合并到默认分支 master _中_。

7. 对要编辑的下一篇文章重复上述步骤。

## <a name="renaming-or-deleting-an-existing-article"></a>重命名或删除现有项目

如果更改将重命名或删除现有项目，请务必添加重定向。 这样一来，任何链接到现有文章的人仍然会最终处于正确的位置。 重定向由存储库根目录的 .openpublishing.redirection.json 文件管理。

若要向 .openpublishing.redirection.json 添加重定向，请向 数组添加 `redirections` 一个条目：

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`是要删除的旧文章的相对存储库路径。 请确保路径以 开头 `mixed-reality-docs` ，以 结尾 `.md` 。

- `redirect_url`是旧文章到新文章的相对公共 URL。 请确保此 URL **不包含** 或 ，因为它引用的是公共 `mixed-reality-docs` `.md` URL，而不是存储库路径。 允许使用 链接到新文章中 `#section` 的节。 如有必要，还可以在此处使用另一个站点的绝对路径。

- `redirect_document_id` 指示是否要保留上一个文件的文档 ID。 默认值为 `false`。 `true`如果要保留重定向项目 `ms.documentid` 中的属性值，请使用 。 如果保留文档 ID，数据（如页面视图和排名）将传输到目标项目。 如果重定向主要用于重命名，而不是指向仅涵盖一些相同内容的不同项目，则执行此操作。

如果添加重定向，请确保也删除旧文件。

## <a name="creating-a-new-article"></a>创建新文章

使用以下工作流通过 *Web 浏览器中* 的 GitHub在文档存储库创建新文章：

1. 使用右上方的"分支"按钮，从 MicrosoftDocs/mixed-reality 的默认分支master 创建分支。

   ![为默认分支创建分支，当前命名为"master"。](images/forkbranch.png)

   > [!NOTE]
   > 本文包含对 _master（Microsoft_ 不再使用的术语）的引用。 在从软件中删除该术语后，我们会将其从本文中删除。
   
2. 在"mixed-reality-docs"文件夹中，选择右上方 **的** "创建新文件"。

3. 为文章创建页名称， (连字符而不是空格，并且不使用标点符号或撇号) 并追加".md"

   ![将新页面命名。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >请确保从"mixed-reality-docs"文件夹中创建新文章。 可以通过检查新文件名行中的"/mixed-reality-docs/"来确认这一点。

4. 在新建页面的顶部，添加以下元数据块：

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. 填写相关元数据字段，如编辑现有文章 [中所述](#editing-an-existing-article)。

6. 使用 Markdown 基础知识 [编写文章内容](#markdown-basics)。

7. 在 `## See also` 文章底部添加一个部分，并包含指向其他相关文章的链接。

8. 完成后，选择"**提交新文件"。**

9. 选择 **"新建拉** 取请求"，将分叉的主分支合并到 MicrosoftDocs/混合现实主 (确保箭头指向正确的目标) 。

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求。](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 基础知识

以下资源将帮助你了解如何使用 Markdown 语言编辑文档：

- [Markdown 基本信息](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [用于编写 Markdown for docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>添加表

由于样式 docs.microsoft.com，即使尝试内联 CSS，它们也不会具有边框或自定义样式。 它看起来会在短时间内正常工作，但最终平台会从表中去除样式。 因此，请提前规划并简化表。 下面是一个使 Markdown 表变得简单的站点：[表生成器 https://www.tablesgenerator.com/markdown_tables) ]] (。

如果使用[Visual Studio Code，Docs Markdown Extension for](/teamblog/docs-extension) Visual Studio Code 还可轻松生成表，Visual Studio Code (以下) 编辑文档。 [](#using-visual-studio-code)

### <a name="adding-images"></a>添加图像

需要将映像上传到存储库中的 "混合现实文档/映像" 文件夹，并在文章中对它们进行相应的引用。 图像将自动以全尺寸显示，这意味着大型图像将填充整个文章的宽度。 建议在上传映像之前对其进行预先调整大小。 建议宽度介于600到700像素之间，不过，如果它是密集屏幕截图或屏幕截图的小部分，则应调整大小。

>[!IMPORTANT]
>在合并前，只能将图像上传到分叉存储库。 因此，如果你计划将图像添加到项目中，则需要先[使用 Visual Studio Code](#using-visual-studio-code)将图像添加到分叉的 "images" 文件夹，或者确保已在 web 浏览器中完成以下操作：
>
>1. 分叉 MicrosoftDocs/mixed reality 存储库。
>2. 已编辑分叉中的项目。
>3. 将你在项目中引用的映像上传到你的分支中的 "混合现实文档/映像" 文件夹。
>4. 创建了用于将分叉合并到 MicrosoftDocs/mixed reality _主_ 分支的 **拉取请求**。
>
>若要了解如何设置自己的分叉存储库，请按照 [创建新文章](#creating-a-new-article)的说明进行操作。

## <a name="previewing-your-work"></a>预览工作

通过 web 浏览器进行 GitHub 编辑时，可以选择页面顶部附近的 "**预览**" 选项卡来预览你的工作，然后再提交。 

>[!NOTE]
>在 review.docs.microsoft.com 上预览所做的更改仅适用于 Microsoft 员工

Microsoft 员工：如果你的贡献已合并到默认分支 _master_，你可以在 </hololens？分支 = master> 之前查看内容。 使用左栏中的目录查找文章。

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>在浏览器中编辑与使用桌面客户端进行编辑

在浏览器中进行编辑是进行快速更改的最简单方法，但有几个缺点：

- 不会进行拼写检查。
- 您不会获得任何智能链接到其他文章 (您必须手动键入文章的文件名) 。
- 这可能是上传和引用图像的麻烦。

如果你不想处理这些问题，请使用类似于[Visual Studio Code](https://code.visualstudio.com/)的桌面客户端，并在参与时使用几个[有用的扩展](#useful-extensions)。

## <a name="using-visual-studio-code"></a>使用 Visual Studio Code

出于 [上面](#editing-in-the-browser-vs-editing-with-a-desktop-client)列出的原因，您可能更倾向于使用桌面客户端编辑文档而不是 web 浏览器。 建议使用[ Visual Studio Code](https://code.visualstudio.com/)。

### <a name="setup"></a>设置

请按照以下步骤配置 Visual Studio Code 以使用此存储库：

1. 在 web 浏览器中：
    1. 安装 [适用于你的电脑的 Git](https://git-scm.com/downloads)。
    2. 安装 [Visual Studio Code](https://code.visualstudio.com/)。
    3. [分叉 MicrosoftDocs/混合现实（](#creating-a-new-article) 如果尚未这样做）。
    4. 在分支中，选择 " **克隆" 或 "下载** 并复制 URL"。
2. 在 Visual Studio Code 中创建分叉的本地复本：
    1. 从 " **视图** " 菜单中选择 " **命令面板**"。
    2. 键入 "Git： Clone"。
    3. 粘贴复制的 URL。
    4. 选择要在电脑上保存克隆的位置。
    5. 在弹出窗口中选择 " **打开** 存储库"。

### <a name="editing-documentation"></a>编辑文档

使用以下工作流，通过 Visual Studio Code 对文档进行更改：

>[!NOTE]
>在使用 Visual Studio Code 时，所有有关[编辑](#editing-an-existing-article)和[创建](#creating-a-new-article)文章的指南以及[编辑 Markdown 的基础知识](#markdown-basics)也适用。

1. 请确保你的克隆分叉与官方存储库保持最新。

   1. 在 web 浏览器中，创建一个拉取请求，将最近的更改从 MicrosoftDocs/mixed _reality 的默认_ 分支中的其他参与者同步到分叉 (确保箭头指向正确的目标) 。
      
      ![将更改从 MicrosoftDocs/混合现实同步到你的分支。](images/sync-repos.png)
      
   2. 在 Visual Studio Code 中，选择 "同步" 按钮，将最新更新的分支同步到本地克隆。
      
      ![单击 "同步" 按钮图像。](images/sync-clone.png)
      
2. 使用 Visual Studio Code 在克隆的存储库中创建或编辑项目。

   1. 编辑一个或多个项目 (如有必要，将图像添加到 "images" 文件夹) 。
   
   2. 在 **资源管理器** 中 **保存** 更改。
      
      ![在资源管理器中选择 "全部保存"](images/explorer-save.png)
      
   3. ) 提示时，提交 **源代码管理** 中的 **所有** 更改 (写入提交消息。
   
      ![在源代码管理中选择 "全部提交"](images/source-control-commit.png)
      
   4. 选择 "**同步**" 按钮，将所做的更改同步回 GitHub) 上的分叉 (源。
      
      ![单击 "同步" 按钮。](images/sync-back.png)
      
3. 在 web 浏览器中，创建一个拉取请求，将分支中的新更改同步回 MicrosoftDocs/mixed reality _master_ (确保箭头指向正确的目标) 。

   ![创建从分叉到 MicrosoftDocs/混合现实的拉取请求。](images/pr-to-master.png)

### <a name="useful-extensions"></a>有用的扩展

编辑文档时，以下 Visual Studio Code 扩展很有用：

- [用于 Visual Studio Code 的文档 Markdown 扩展](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)-使用 **Alt + M** 显示文档创作选项的菜单，如下所示：
   - 搜索和引用已上传的映像。
   - 添加格式（如列表、表和文档） `>[!NOTE]` 。
   - 搜索和引用内部链接和书签 (指向) 页面内特定部分的链接。
   - 突出显示格式错误 (将鼠标悬停在错误上以了解详细) 。
- [代码拼写检查器](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -将为拼写错误的单词加下划线。右键单击拼写错误的单词以对其进行更改或将其保存到字典中。
