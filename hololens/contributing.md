---
title: 参与说明
description: 了解如何使用 GitHub 风格 Markdown 为 docs.microsoft.com 平台上的 HoloLens 文档做贡献。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253812"
---
# 为 HoloLens 文档做贡献

欢迎使用 [HoloLens 文档](https://github.com/MicrosoftDocs/Hololens)！ 在此存储库创建或编辑的任何文章 **都将对公众可见。** 

HoloLens 文档显示在 Docs.microsoft.com 平台上，该平台将 GitHub 风格 Markdown 与 Markdig 功能一起使用。 在此存储库编辑的内容格式化为样式化页面，显示在 https://docs.microsoft.com/hololens 。 

此页面介绍有关提供 Markdown 基础知识和链接的基本步骤和指南。 感谢您的贡献！

## 可用 repos

| 存储库名称 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 混合现实 | [MicrosoftDocs/mixed-reality](https://docs.microsoft.com/windows/mixed-reality) |
| VR Enthusiasts 指南 | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## 准备工作

如果还没有帐户，则需要创建 [GitHub 帐户](https://github.com/join)。

>[!NOTE]
>如果你是 Microsoft 员工，将 GitHub 帐户链接到 Microsoft 开放源代码门户 [上的 Microsoft 别名](https://repos.opensource.microsoft.com/)。 加入 **"Microsoft"和****"MicrosoftDocs"** 组织。

设置 GitHub 帐户时，我们还建议采取以下安全预防措施：
- 为 [GitHub 帐户创建强密码](https://github.com/settings/admin)。
- 启用 [双重身份验证](https://github.com/settings/two_factor_authentication/configure)。
- 将 [恢复代码保存在](https://github.com/settings/auth/recovery-codes) 安全的位置。
- 更新 [公共配置文件设置](https://github.com/settings/profile)。
   - 设置你的姓名，并考虑将*公用电子邮件*设置为 *"不显示我的电子邮件地址"。*
   - 我们建议您上传个人资料图片，因为缩略图显示在你参与的文档页面上。
- 如果计划使用命令行，请考虑为 Windows 设置 [Git 凭据管理器](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。 这样，你每次进行贡献时就不需要输入密码。

发布系统与 GitHub 关联，因此这些步骤非常重要。 使用 GitHub 别名将你列为每篇文章的作者或参与者。

## 编辑现有文章

使用以下工作流在 Web 浏览器中通过** GitHub 更新现有文章：

1. 导航到想要在"mixed-reality-docs"文件夹中编辑的文章。

2. 选择右上角 (铅笔) 图标的编辑按钮，该图标将自动将可释放的分支从"master"分支中分叉。

   ![编辑文章。](images/editpage.png)
   
3. 根据 ["Markdown](#markdown-basics)基础知识"编辑文章的内容。

4. 更新每篇文章顶部的元数据：

   * **title：** Page title that appears in the browser tab when the article is being viewed. 页面标题用于 SEO 和索引编制，因此除非有必要，否则不要更改标题 (尽管文档在公开更新之前) 。
   * **description：** Write a brief description of the article's content， which boosts SEO and discovery.
   * **author**： If you're the primary owner of the page， add your GitHub alias here.
   * **ms.author：** 如果你是页面的主要所有者，请在此处添加 Microsoft 别名 (无需 @microsoft.com，只需别名) 。
   * **ms.date：** Update the date if you're adding major content to the page， but not for fixes like clarification， formatting， grammar， or spelling.
   * **关键字：** 关键字有助于 SEO (搜索引擎优化) 。 添加关键字，用逗号和空格分隔，这些关键字特定于您的文章，但列表中最后一个关键字后面没有标点符号。 无需添加适用于所有文章的全局关键字，因为这些关键字在其他地方进行管理。 
   
5. 完成文章编辑后，向下滚动并选择"建议**文件更改"。**

6. 下一页上，选择 **"创建拉取请求** "，将自动创建的分支合并到"主控"中。

7. 对要编辑的下一篇文章重复上述步骤。

## 重命名或删除现有文章

如果更改将重命名或删除现有文章，请务必添加重定向。 这样，任何具有指向现有文章的链接的人最终仍将在正确的位置。 重定向由存储库根.openpublishing.redirection.js上的文件管理。

若要添加指向.openpublishing.redirection.js的重定向，请向数组添加 `redirections` 一个条目：

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`它是要删除的旧文章的相对存储库路径。 请确保路径以 `mixed-reality-docs` . `.md`

- 它是 `redirect_url` 从旧文章到新文章的相对公用 URL。 确保此 URL **不包含** 或 ，因为它引用的是公用 `mixed-reality-docs` `.md` URL，而不是存储库路径。 允许链接到新文章中使用 `#section` 的部分。 如有必要，您还可以在此处使用指向另一个站点的绝对路径。

- `redirect_document_id` 指示是否要保留上一个文件的文档 ID。 默认值为 `false` 。 `true`如果要保留重定向文章中 `ms.documentid` 的属性值，请使用。 如果保留文档 ID，则页面视图和排名等数据将传输到目标文章。 如果重定向主要是重命名，而不是指向仅涵盖部分相同内容的不同文章的指针，请执行此操作。

如果添加重定向，请务必同时删除旧文件。

## 创建新文章

使用以下工作流在 *Web* 浏览器中通过 GitHub 在文档存储库中创建新文章：

1. 使用右上方的"分叉"按钮 (MicrosoftDocs/mixed-reality"master"分支分支****) 。

   ![分支主分支。](images/forkbranch.png)
   
2. 在"mixed-reality-docs"文件夹中，选择右上方 **的** "创建新文件"。

3. 为文章创建页面名称 (使用连字符而不是空格，并且不使用标点符号或撇号) 并追加".md"

   ![命名新页面。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >请确保从"mixed-reality-docs"文件夹中创建新文章。 可以通过检查新文件名行中的"/mixed-reality-docs/"来确认这一点。

4. 在新建页面顶部，添加以下元数据块：

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

5. 按照上述部分中的说明填写相关的 [元数据字段](#editing-an-existing-article)。

6. 使用 [Markdown 基础知识编写文章内容](#markdown-basics)。

7. 在 `## See also` 文章底部添加一个包含指向其他相关文章的链接的部分。

8. 完成后，选择 **"提交新文件"。**

9. 选择 **"新建** 拉取请求"，将分叉的"主"分支合并到 MicrosoftDocs/混合现实"主 (确保箭头以正确的方式指向) 。

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

## Markdown 基础知识

以下资源将帮助您了解如何使用 Markdown 语言编辑文档：

- [Markdown 基础知识](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [用于编写 Markdown for docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### 添加表

由于样式表docs.microsoft.com，即使尝试内联 CSS，它们也不会具有边框或自定义样式。 它看起来会在短时间内工作，但最终平台会从表中去除样式设置。 因此请提前规划并保持表格简单。 [下面是一个使 Markdown 表变得简单的网站](https://www.tablesgenerator.com/markdown_tables)。

如果您使用的是 Visual Studio Code (，Visual Studio Code 的 [Docs Markdown](https://docs.microsoft.com/teamblog/docs-extension) [Extension ](#using-visual-studio-code) 还便于生成) 文档。

### 添加图像

你需要将图像上载到存储库的"mixed-reality-docs/images"文件夹，然后在文章中适当地引用它们。 图像将自动以全尺寸显示，这意味着大图像将填满文章的整个宽度。 我们建议在上传图像之前对图像进行预大小调整。 虽然建议的宽度介于 600 和 700 像素之间，但如果是一个密集屏幕截图或屏幕截图的一小部分，应分别向上或向下调整大小。

>[!IMPORTANT]
>在合并之前，只能将图像上载到分叉存储库。 因此，如果您计划向文章添加图像，您需要首先使用 [Visual Studio 代码](#using-visual-studio-code) 将图像添加到分叉的"images"文件夹中，或确保已完成 Web 浏览器中的下列操作：
>
>1. 分叉 MicrosoftDocs/混合现实存储库。
>2. 在分叉中编辑了文章。
>3. 将文章中引用的图像上载到分叉中的"mixed-reality-docs/images"文件夹。
>4. 创建了一 **个拉取** 请求，用于将分叉合并到 MicrosoftDocs/mixed-reality"master"分支中。
>
>若要了解如何设置自己的分叉存储库，请按照创建新 [文章的说明操作](#creating-a-new-article)。

## 预览你的工作

通过 Web 浏览器在 GitHub 中编辑时，可以选择**** 页面顶部附近的"预览"选项卡，在提交之前预览你的工作。 

>[!NOTE]
>预览更改review.docs.microsoft.com仅适用于 Microsoft 员工

Microsoft 员工：一旦你的贡献合并到"主"分支中，就可以在内容公开之前查看内容 https://review.docs.microsoft.com/hololens?branch=master 。 使用左侧列中的目录查找文章。

## 在浏览器中编辑与使用桌面客户端编辑

在浏览器中编辑是进行快速更改的最简单方法，但存在一些缺点：

- 你无法进行拼写检查。
- 如果必须手动键入文章的文件名， (其他文章的任何智能链接) 。
- 上载和引用图像可能很麻烦。

如果不愿意处理这些问题，请使用桌面客户端（如Visual Studio [代码](https://code.visualstudio.com/) ）在参与时 [提供几个有用的](#useful-extensions) 扩展。

## 使用Visual Studio代码

出于 [上述原因，](#editing-in-the-browser-vs-editing-with-a-desktop-client)你可能更喜欢使用桌面客户端来编辑文档，而不是 Web 浏览器。 我们建议使用Visual Studio [代码](https://code.visualstudio.com/)。

### 安装

按照以下步骤配置Visual Studio代码以用于此存储库：

1. 在 Web 浏览器中：
    1. 为[电脑安装 Git。](https://git-scm.com/downloads)
    2. 安装 [Visual Studio代码](https://code.visualstudio.com/)。
    3. [Fork MicrosoftDocs/mixed-reality（](#creating-a-new-article) 如果尚未创建）。
    4. 在分叉中，选择 **"克隆"或下载** 并复制 URL。
2. 使用代码创建分叉的本地Visual Studio克隆：
    1. 从"**视图"** 菜单中，选择 **"命令调色板"。**
    2. 键入"Git： Clone"。
    3. 粘贴您复制的 URL。
    4. 选择在电脑上保存克隆位置。
    5. 在 **弹出窗口中选择** "打开存储库"。

### 编辑文档

使用以下工作流对包含以下代码的文档Visual Studio代码：

>[!NOTE]
>以上有关编辑[和创建](#editing-an-existing-article)文章的所有[](#creating-a-new-article)指南以及编辑[Markdown](#markdown-basics)的基础知识也适用于使用 Visual Studio Code。

1. 使用官方存储库确保克隆的分叉是最新的。

   1. 在 Web 浏览器中，创建拉取请求，将 MicrosoftDocs/mixed-reality"master"中其他参与者的最新更改同步到分叉 (确保箭头指向正确的方向) 。
      
      ![将更改从 MicrosoftDocs/mixed-reality 同步到分叉](images/sync-repos.png)
      
   2. 在Visual Studio代码中，选择同步按钮以将最新更新的分叉同步到本地克隆。
      
      ![单击同步按钮图像](images/sync-clone.png)
      
2. 使用代码创建或编辑克隆的Visual Studio文章。

   1. 编辑一个或多个文章 (图像添加到"images"文件夹（如有必要) ）。
   
   2. **在** 资源管理器中 **保存更改**。
      
      ![在资源管理器中选择"全部保存"](images/explorer-save.png)
      
   3. **在出现提示** 时，提交源 **控件 (写入** 提交消息) 。
      
   4. 选择 **同步按钮** ，将更改同步回 GitHub (分支中的源) 。
      
      ![单击同步按钮](images/sync-back.png)
      
3. 在 Web 浏览器中，创建拉取请求，将分叉中的新更改同步回 MicrosoftDocs/混合现实"主 (确保箭头以正确的方式) 。

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

### 有用的扩展

以下Visual Studio代码扩展在编辑文档时很有用：

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like：
   - 搜索和引用已上传的图像。
   - 添加格式，如列表、表和文档特定的调用，如 `>[!NOTE]` 。
   - 搜索和引用内部链接和书签 (链接到页面中特定) 。
   - 将突出显示格式错误 (将鼠标悬停在错误上方，以了解) 。
- [代码拼写检查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 器 - 拼写错误的单词将带下划线;右键单击拼写错误的单词以将其更改或保存到词典。
