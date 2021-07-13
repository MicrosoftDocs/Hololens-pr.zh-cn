---
title: 参与说明
description: 了解如何使用HoloLens Markdown 在 docs.microsoft.com 平台上GitHub文档。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635664"
---
# <a name="contributing-to-the-hololens-documentation"></a>参与HoloLens文档

欢迎使用[HoloLens文档](https://github.com/MicrosoftDocs/Hololens)！ 在此存储库创建或编辑的任何文章 **都将对公众可见。** 

HoloLens文档显示在 docs.microsoft.com 平台上，该平台将GitHub Markdown 与 Markdig 功能一同使用。 在此存储库编辑的内容将格式化为显示在 /hololens 中的样式化页面。

本页介绍参与和链接 Markdown 基础知识的基本步骤和指南。 感谢你的贡献！

## <a name="available-repos"></a>可用 repos

| 存储库名称 | 代码 |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 混合现实 | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| VR 友元指南 | [MicrosoftDocs/mixed-reality/reality-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>开始之前

如果还没有帐户，则需要创建一个GitHub[帐户](https://github.com/join)。

>[!NOTE]
>如果你是 Microsoft 员工，请GitHub Microsoft 开放源代码门户 上的[Microsoft 别名](https://repos.opensource.microsoft.com/)。 加入 **"Microsoft"和****"MicrosoftDocs"** 组织。

在设置GitHub帐户时，我们还建议采取以下安全预防措施：
- 为[帐户 创建GitHub密码](https://github.com/settings/admin)。
- 启用 [双因素身份验证](https://github.com/settings/two_factor_authentication/configure)。
- 将 [恢复代码保存在](https://github.com/settings/auth/recovery-codes) 安全的位置。
- 更新 [公共配置文件设置](https://github.com/settings/profile)。
   - 设置你的姓名，并考虑将 *"公共电子邮件*"设置为 *"不显示我的电子邮件地址"。*
   - 建议上传个人资料图片，因为缩略图显示在你参与的文档页面上。
- 如果打算使用命令行，请考虑为 凭据管理器 Git [Windows。](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) 这样，就不需要每次贡献时都输入密码。

发布系统与 GitHub关联，因此这些步骤非常重要。 你将使用你的别名作为每篇文章的作者或参与者GitHub列表。

## <a name="editing-an-existing-article"></a>编辑现有文章

使用以下工作流通过 Web 浏览器中的 *GitHub* 更新现有文章：

1. 导航到想要在"mixed-reality-docs"文件夹中编辑的文章。

2. 选择右上角 (铅笔) 图标的编辑按钮，该图标会自动从"master"分支可释放分支。

   ![编辑文章。](images/editpage.png)
   
3. 根据 ["Markdown](#markdown-basics)基础知识"编辑文章内容。

4. 更新每篇文章顶部的元数据：

   * **title：** 查看文章时显示在浏览器选项卡中的页标题。 页面标题用于 SEO 和索引编制，因此除非有必要更改标题， (不过在文档公开之前，这不太) 。
   * **description：** 编写文章内容的简要说明，这将提升 SEO 和发现。
   * **author：** 如果你是页面的主要所有者，请在此处GitHub别名。
   * **ms.author：** 如果你是页面的主要所有者，请在此处添加 Microsoft 别名 (不需要 ，只需添加 @microsoft.com) 。
   * **ms.date：** 如果要将主要内容添加到页面，请更新日期，但不能更新说明、格式设置、语法或拼写等修复。
   * **关键字**：关键字有助于 SEO (搜索引擎优化) 。 添加关键字，以逗号和空格分隔，这些关键字特定于你的文章，但在列表中的最后一个关键字后面没有标点符号。 无需添加适用于所有文章的全局关键字，因为这些关键字在其他地方进行管理。 
   
5. 完成文章编辑后，向下滚动并选择"建议 **文件更改"。**

6. 下一页选择" **创建拉取请求** "，将自动创建的分支合并到"master"中。

7. 对要编辑的下一篇文章重复上述步骤。

## <a name="renaming-or-deleting-an-existing-article"></a>重命名或删除现有项目

如果更改将重命名或删除现有项目，请务必添加重定向。 这样一来，任何链接到现有文章的人仍然会最终处于正确的位置。 重定向由存储库根.openpublishing.redirection.js中的 on 文件托管。

若要将重定向添加到 .openpublishing.redirection.json，请向 数组添加 `redirections` 一个条目：

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

- `redirect_document_id` 指示是否要保留上一个文件的文档 ID。 默认值为 `false`。 `true`如果要保留重定向项目 `ms.documentid` 中的属性值，请使用 。 如果保留文档 ID，数据（如页面视图和排名）将传输到目标项目。 如果重定向主要是重命名，而不是指向仅涵盖某些相同内容的不同文章的指针，请执行此操作。

如果添加重定向，请确保也删除旧文件。

## <a name="creating-a-new-article"></a>创建新文章

使用以下工作流通过 *Web 浏览器中* 的 GitHub在文档存储库创建新文章：

1. 使用右上方的"分支"按钮从 MicrosoftDocs/混合现实"master"分支分支 (创建分支) 。

   ![为主分支分叉。](images/forkbranch.png)
   
2. 在"mixed-reality-docs"文件夹中，选择右上方 **的** "创建新文件"。

3. 为文章创建页名称 (连字符而不是空格，并且不使用标点符号或撇号) 并追加".md"

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

5. 按照上述 部分中的说明填写相关的 [元数据字段](#editing-an-existing-article)。

6. 使用 [Markdown 基础知识 编写文章内容](#markdown-basics)。

7. 在 `## See also` 文章底部添加一个部分，并包含指向其他相关文章的链接。

8. 完成后，选择"**提交新文件"。**

9. 选择 **"新建拉** 取请求"，将分叉的"master"分支合并到 MicrosoftDocs/混合现实"master" (确保箭头指向正确的) 。

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 基础知识

以下资源将帮助你了解如何使用 Markdown 语言编辑文档：

- [Markdown 基本信息](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [用于编写 Markdown for docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>添加表

由于样式表 docs.microsoft.com，即使尝试内联 CSS，它们也不会具有边框或自定义样式。 它看起来会在短时间内正常工作，但最终平台会从表中去除样式。 因此，请提前规划并简化表。 [下面是一个使 Markdown 表变得简单的站点](https://www.tablesgenerator.com/markdown_tables)。

如果使用文档，Visual Studio Code的[Docs Markdown](/teamblog/docs-extension)扩展还使表生成变得Visual Studio Code ([请参阅](#using-visual-studio-code)) 编辑文档。

### <a name="adding-images"></a>添加图像

需要将图像上传到存储库的"mixed-reality-docs/images"文件夹，然后在文章中适当地引用它们。 图像将自动以全尺寸显示，这意味着大型图像将填满文章的整个宽度。 建议在上传图像之前预先调整图像大小。 建议的宽度介于 600 和 700 像素之间，但如果是密集屏幕截图或屏幕截图的一小部分，则应该放大或缩小。

>[!IMPORTANT]
>在合并之前，只能将图像上传到分支存储库。 因此，如果计划将图像添加到文章，则需要先使用[Visual Studio Code](#using-visual-studio-code)将图像添加到分叉的"images"文件夹，或者确保已完成 Web 浏览器中的以下操作：
>
>1. 为 MicrosoftDocs/混合现实存储库分叉。
>2. 编辑了分叉中的文章。
>3. 将文章中引用的图像上传到分叉中的"mixed-reality-docs/images"文件夹。
>4. 创建了一 **个拉取** 请求，用于将分支合并到 MicrosoftDocs/混合现实"master"分支中。
>
>若要了解如何设置自己的分叉存储库，请按照创建新 [文章 的说明操作](#creating-a-new-article)。

## <a name="previewing-your-work"></a>预览工作

通过 Web 浏览器GitHub预览时，可以选择页面顶部附近的"预览"选项卡，在提交之前预览工作。 

>[!NOTE]
>预览更改review.docs.microsoft.com 仅适用于 Microsoft 员工

Microsoft 员工：将贡献内容合并到"master"分支后，可以在发布内容之前在 </hololens？branch=master>。 使用左侧列中的目录查找文章。

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>在浏览器中编辑与使用桌面客户端进行编辑

在浏览器中编辑是进行快速更改的最简单方法，但存在一些缺点：

- 不会进行拼写检查。
- 如果必须手动键入文章的文件名， (无法智能链接到其他) 。
- 上传和引用图像可能很麻烦。

如果愿意不解决这些问题，请使用桌面客户端（如[Visual Studio Code在参与](https://code.visualstudio.com/)时[提供一些](#useful-extensions)有用的扩展。

## <a name="using-visual-studio-code"></a>使用 Visual Studio Code

出于 [上述原因，](#editing-in-the-browser-vs-editing-with-a-desktop-client)你可能更喜欢使用桌面客户端来编辑文档，而不是 Web 浏览器。 建议使用[ Visual Studio Code](https://code.visualstudio.com/)。

### <a name="setup"></a>设置

按照以下步骤配置Visual Studio Code存储库：

1. 在 Web 浏览器中：
    1. 为[电脑安装 Git。](https://git-scm.com/downloads)
    2. 安装 [Visual Studio Code](https://code.visualstudio.com/)。
    3. [为 MicrosoftDocs/mixed-reality](#creating-a-new-article) 创建分叉（如果尚未创建）。
    4. 在分叉中，选择" **克隆或下载** 并复制 URL"。
2. 在 Visual Studio Code 中创建分叉的本地Visual Studio Code：
    1. 在"视图 **"菜单中**，选择"**命令面板"。**
    2. 键入"Git： Clone"。
    3. 粘贴复制的 URL。
    4. 选择在电脑上保存克隆的地方。
    5. 在 **弹出窗口中选择** "打开存储库"。

### <a name="editing-documentation"></a>编辑文档

使用以下工作流对文档进行更改，并Visual Studio Code：

>[!NOTE]
>上述有关[编辑和创建](#editing-an-existing-article)文章的所有[](#creating-a-new-article)指南以及编辑[Markdown](#markdown-basics)的基础知识也适用于使用 Visual Studio Code。

1. 使用官方存储库确保克隆的分叉是最新的。

   1. 在 Web 浏览器中，创建拉取请求，将 MicrosoftDocs/混合现实"master"中其他参与者的最新更改同步到分叉 (确保箭头指向正确的) 。
      
      ![将更改从 MicrosoftDocs/mixed-reality 同步到分叉](images/sync-repos.png)
      
   2. 在Visual Studio Code"中，选择"同步"按钮，将新更新的分叉同步到本地克隆。
      
      ![单击同步按钮图像](images/sync-clone.png)
      
2. 使用 Visual Studio Code 在克隆的存储库创建或编辑Visual Studio Code。

   1. 根据需要编辑一个或多个 (图像添加到"images"文件夹) 。
   
   2. **在** 资源管理器 中 **保存更改**。
      
      ![在资源管理器中选择"全部保存"](images/explorer-save.png)
      
   3. **在源代码管理** 中 **提交所有 (** 在系统提示时写入提交) 。
   
      ![在源代码管理中选择"全部提交"](images/source-control-commit.png)
      
   4. 选择同步 **按钮**，将更改同步回源 (上的分叉GitHub) 。
      
      ![单击同步按钮](images/sync-back.png)
      
3. 在 Web 浏览器中，创建拉取请求，将分叉中的新更改同步回 MicrosoftDocs/混合现实"master" (确保箭头指向正确的) 。

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

### <a name="useful-extensions"></a>有用的扩展

编辑Visual Studio Code时，以下扩展非常有用：

- [Docs Markdown 扩展Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - 使用 **Alt+M** 打开文档创作选项的菜单，例如：
   - 搜索和引用已上传的图像。
   - 添加格式设置，如列表、表和文档特定的调用（如 `>[!NOTE]` ）。
   - 搜索和引用内部链接和书签 (链接到页面中特定部分) 。
   - 格式设置错误突出显示 (将鼠标悬停在错误上方，了解) 。
- [代码拼写检查器](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - 拼写错误的单词将带有下划线;右键单击拼写错误的单词以将其更改或保存到字典中。
