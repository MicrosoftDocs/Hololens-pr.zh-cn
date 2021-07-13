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
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="43512-103">参与HoloLens文档</span><span class="sxs-lookup"><span data-stu-id="43512-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="43512-104">欢迎使用[HoloLens文档](https://github.com/MicrosoftDocs/Hololens)！</span><span class="sxs-lookup"><span data-stu-id="43512-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="43512-105">在此存储库创建或编辑的任何文章 **都将对公众可见。**</span><span class="sxs-lookup"><span data-stu-id="43512-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="43512-106">HoloLens文档显示在 docs.microsoft.com 平台上，该平台将GitHub Markdown 与 Markdig 功能一同使用。</span><span class="sxs-lookup"><span data-stu-id="43512-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="43512-107">在此存储库编辑的内容将格式化为显示在 /hololens 中的样式化页面。</span><span class="sxs-lookup"><span data-stu-id="43512-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="43512-108">本页介绍参与和链接 Markdown 基础知识的基本步骤和指南。</span><span class="sxs-lookup"><span data-stu-id="43512-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="43512-109">感谢你的贡献！</span><span class="sxs-lookup"><span data-stu-id="43512-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="43512-110">可用 repos</span><span class="sxs-lookup"><span data-stu-id="43512-110">Available repos</span></span>

| <span data-ttu-id="43512-111">存储库名称</span><span class="sxs-lookup"><span data-stu-id="43512-111">Repository name</span></span> | <span data-ttu-id="43512-112">代码</span><span class="sxs-lookup"><span data-stu-id="43512-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="43512-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="43512-113">HoloLens</span></span> | [<span data-ttu-id="43512-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="43512-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="43512-115">混合现实</span><span class="sxs-lookup"><span data-stu-id="43512-115">Mixed Reality</span></span> | [<span data-ttu-id="43512-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="43512-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="43512-117">VR 友元指南</span><span class="sxs-lookup"><span data-stu-id="43512-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="43512-118">MicrosoftDocs/mixed-reality/reality-guide</span><span class="sxs-lookup"><span data-stu-id="43512-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="43512-119">开始之前</span><span class="sxs-lookup"><span data-stu-id="43512-119">Before you start</span></span>

<span data-ttu-id="43512-120">如果还没有帐户，则需要创建一个GitHub[帐户](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="43512-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="43512-121">如果你是 Microsoft 员工，请GitHub Microsoft 开放源代码门户 上的[Microsoft 别名](https://repos.opensource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="43512-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="43512-122">加入 **"Microsoft"和\*\*\*\*"MicrosoftDocs"** 组织。</span><span class="sxs-lookup"><span data-stu-id="43512-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="43512-123">在设置GitHub帐户时，我们还建议采取以下安全预防措施：</span><span class="sxs-lookup"><span data-stu-id="43512-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="43512-124">为[帐户 创建GitHub密码](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="43512-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="43512-125">启用 [双因素身份验证](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="43512-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="43512-126">将 [恢复代码保存在](https://github.com/settings/auth/recovery-codes) 安全的位置。</span><span class="sxs-lookup"><span data-stu-id="43512-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="43512-127">更新 [公共配置文件设置](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="43512-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="43512-128">设置你的姓名，并考虑将 *"公共电子邮件*"设置为 *"不显示我的电子邮件地址"。*</span><span class="sxs-lookup"><span data-stu-id="43512-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="43512-129">建议上传个人资料图片，因为缩略图显示在你参与的文档页面上。</span><span class="sxs-lookup"><span data-stu-id="43512-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="43512-130">如果打算使用命令行，请考虑为 凭据管理器 Git [Windows。](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="43512-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="43512-131">这样，就不需要每次贡献时都输入密码。</span><span class="sxs-lookup"><span data-stu-id="43512-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="43512-132">发布系统与 GitHub关联，因此这些步骤非常重要。</span><span class="sxs-lookup"><span data-stu-id="43512-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="43512-133">你将使用你的别名作为每篇文章的作者或参与者GitHub列表。</span><span class="sxs-lookup"><span data-stu-id="43512-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="43512-134">编辑现有文章</span><span class="sxs-lookup"><span data-stu-id="43512-134">Editing an existing article</span></span>

<span data-ttu-id="43512-135">使用以下工作流通过 Web 浏览器中的 *GitHub* 更新现有文章：</span><span class="sxs-lookup"><span data-stu-id="43512-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="43512-136">导航到想要在"mixed-reality-docs"文件夹中编辑的文章。</span><span class="sxs-lookup"><span data-stu-id="43512-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="43512-137">选择右上角 (铅笔) 图标的编辑按钮，该图标会自动从"master"分支可释放分支。</span><span class="sxs-lookup"><span data-stu-id="43512-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![编辑文章。](images/editpage.png)
   
3. <span data-ttu-id="43512-139">根据 ["Markdown](#markdown-basics)基础知识"编辑文章内容。</span><span class="sxs-lookup"><span data-stu-id="43512-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="43512-140">更新每篇文章顶部的元数据：</span><span class="sxs-lookup"><span data-stu-id="43512-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="43512-141">**title：** 查看文章时显示在浏览器选项卡中的页标题。</span><span class="sxs-lookup"><span data-stu-id="43512-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="43512-142">页面标题用于 SEO 和索引编制，因此除非有必要更改标题， (不过在文档公开之前，这不太) 。</span><span class="sxs-lookup"><span data-stu-id="43512-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="43512-143">**description：** 编写文章内容的简要说明，这将提升 SEO 和发现。</span><span class="sxs-lookup"><span data-stu-id="43512-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="43512-144">**author：** 如果你是页面的主要所有者，请在此处GitHub别名。</span><span class="sxs-lookup"><span data-stu-id="43512-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="43512-145">**ms.author：** 如果你是页面的主要所有者，请在此处添加 Microsoft 别名 (不需要 ，只需添加 @microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="43512-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="43512-146">**ms.date：** 如果要将主要内容添加到页面，请更新日期，但不能更新说明、格式设置、语法或拼写等修复。</span><span class="sxs-lookup"><span data-stu-id="43512-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="43512-147">**关键字**：关键字有助于 SEO (搜索引擎优化) 。</span><span class="sxs-lookup"><span data-stu-id="43512-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="43512-148">添加关键字，以逗号和空格分隔，这些关键字特定于你的文章，但在列表中的最后一个关键字后面没有标点符号。</span><span class="sxs-lookup"><span data-stu-id="43512-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="43512-149">无需添加适用于所有文章的全局关键字，因为这些关键字在其他地方进行管理。</span><span class="sxs-lookup"><span data-stu-id="43512-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="43512-150">完成文章编辑后，向下滚动并选择"建议 **文件更改"。**</span><span class="sxs-lookup"><span data-stu-id="43512-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="43512-151">下一页选择" **创建拉取请求** "，将自动创建的分支合并到"master"中。</span><span class="sxs-lookup"><span data-stu-id="43512-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="43512-152">对要编辑的下一篇文章重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="43512-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="43512-153">重命名或删除现有项目</span><span class="sxs-lookup"><span data-stu-id="43512-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="43512-154">如果更改将重命名或删除现有项目，请务必添加重定向。</span><span class="sxs-lookup"><span data-stu-id="43512-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="43512-155">这样一来，任何链接到现有文章的人仍然会最终处于正确的位置。</span><span class="sxs-lookup"><span data-stu-id="43512-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="43512-156">重定向由存储库根.openpublishing.redirection.js中的 on 文件托管。</span><span class="sxs-lookup"><span data-stu-id="43512-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="43512-157">若要将重定向添加到 .openpublishing.redirection.json，请向 数组添加 `redirections` 一个条目：</span><span class="sxs-lookup"><span data-stu-id="43512-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="43512-158">`source_path`是要删除的旧文章的相对存储库路径。</span><span class="sxs-lookup"><span data-stu-id="43512-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="43512-159">请确保路径以 开头 `mixed-reality-docs` ，以 结尾 `.md` 。</span><span class="sxs-lookup"><span data-stu-id="43512-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="43512-160">`redirect_url`是旧文章到新文章的相对公共 URL。</span><span class="sxs-lookup"><span data-stu-id="43512-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="43512-161">请确保此 URL **不包含** 或 ，因为它引用的是公共 `mixed-reality-docs` `.md` URL，而不是存储库路径。</span><span class="sxs-lookup"><span data-stu-id="43512-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="43512-162">允许使用 链接到新文章中 `#section` 的节。</span><span class="sxs-lookup"><span data-stu-id="43512-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="43512-163">如有必要，还可以在此处使用另一个站点的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="43512-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="43512-164">`redirect_document_id` 指示是否要保留上一个文件的文档 ID。</span><span class="sxs-lookup"><span data-stu-id="43512-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="43512-165">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="43512-165">The default is `false`.</span></span> <span data-ttu-id="43512-166">`true`如果要保留重定向项目 `ms.documentid` 中的属性值，请使用 。</span><span class="sxs-lookup"><span data-stu-id="43512-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="43512-167">如果保留文档 ID，数据（如页面视图和排名）将传输到目标项目。</span><span class="sxs-lookup"><span data-stu-id="43512-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="43512-168">如果重定向主要是重命名，而不是指向仅涵盖某些相同内容的不同文章的指针，请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="43512-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="43512-169">如果添加重定向，请确保也删除旧文件。</span><span class="sxs-lookup"><span data-stu-id="43512-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="43512-170">创建新文章</span><span class="sxs-lookup"><span data-stu-id="43512-170">Creating a new article</span></span>

<span data-ttu-id="43512-171">使用以下工作流通过 *Web 浏览器中* 的 GitHub在文档存储库创建新文章：</span><span class="sxs-lookup"><span data-stu-id="43512-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="43512-172">使用右上方的"分支"按钮从 MicrosoftDocs/混合现实"master"分支分支 (创建分支) 。</span><span class="sxs-lookup"><span data-stu-id="43512-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![为主分支分叉。](images/forkbranch.png)
   
2. <span data-ttu-id="43512-174">在"mixed-reality-docs"文件夹中，选择右上方 **的** "创建新文件"。</span><span class="sxs-lookup"><span data-stu-id="43512-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="43512-175">为文章创建页名称 (连字符而不是空格，并且不使用标点符号或撇号) 并追加".md"</span><span class="sxs-lookup"><span data-stu-id="43512-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![将新页面命名。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="43512-177">请确保从"mixed-reality-docs"文件夹中创建新文章。</span><span class="sxs-lookup"><span data-stu-id="43512-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="43512-178">可以通过检查新文件名行中的"/mixed-reality-docs/"来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="43512-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="43512-179">在新建页面的顶部，添加以下元数据块：</span><span class="sxs-lookup"><span data-stu-id="43512-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="43512-180">按照上述 部分中的说明填写相关的 [元数据字段](#editing-an-existing-article)。</span><span class="sxs-lookup"><span data-stu-id="43512-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="43512-181">使用 [Markdown 基础知识 编写文章内容](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="43512-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="43512-182">在 `## See also` 文章底部添加一个部分，并包含指向其他相关文章的链接。</span><span class="sxs-lookup"><span data-stu-id="43512-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="43512-183">完成后，选择"**提交新文件"。**</span><span class="sxs-lookup"><span data-stu-id="43512-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="43512-184">选择 **"新建拉** 取请求"，将分叉的"master"分支合并到 MicrosoftDocs/混合现实"master" (确保箭头指向正确的) 。</span><span class="sxs-lookup"><span data-stu-id="43512-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="43512-186">Markdown 基础知识</span><span class="sxs-lookup"><span data-stu-id="43512-186">Markdown basics</span></span>

<span data-ttu-id="43512-187">以下资源将帮助你了解如何使用 Markdown 语言编辑文档：</span><span class="sxs-lookup"><span data-stu-id="43512-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="43512-188">Markdown 基本信息</span><span class="sxs-lookup"><span data-stu-id="43512-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="43512-189">用于编写 Markdown for docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="43512-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="43512-190">添加表</span><span class="sxs-lookup"><span data-stu-id="43512-190">Adding tables</span></span>

<span data-ttu-id="43512-191">由于样式表 docs.microsoft.com，即使尝试内联 CSS，它们也不会具有边框或自定义样式。</span><span class="sxs-lookup"><span data-stu-id="43512-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="43512-192">它看起来会在短时间内正常工作，但最终平台会从表中去除样式。</span><span class="sxs-lookup"><span data-stu-id="43512-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="43512-193">因此，请提前规划并简化表。</span><span class="sxs-lookup"><span data-stu-id="43512-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="43512-194">[下面是一个使 Markdown 表变得简单的站点](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="43512-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="43512-195">如果使用文档，Visual Studio Code的[Docs Markdown](/teamblog/docs-extension)扩展还使表生成变得Visual Studio Code ([请参阅](#using-visual-studio-code)) 编辑文档。</span><span class="sxs-lookup"><span data-stu-id="43512-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="43512-196">添加图像</span><span class="sxs-lookup"><span data-stu-id="43512-196">Adding images</span></span>

<span data-ttu-id="43512-197">需要将图像上传到存储库的"mixed-reality-docs/images"文件夹，然后在文章中适当地引用它们。</span><span class="sxs-lookup"><span data-stu-id="43512-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="43512-198">图像将自动以全尺寸显示，这意味着大型图像将填满文章的整个宽度。</span><span class="sxs-lookup"><span data-stu-id="43512-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="43512-199">建议在上传图像之前预先调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="43512-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="43512-200">建议的宽度介于 600 和 700 像素之间，但如果是密集屏幕截图或屏幕截图的一小部分，则应该放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="43512-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="43512-201">在合并之前，只能将图像上传到分支存储库。</span><span class="sxs-lookup"><span data-stu-id="43512-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="43512-202">因此，如果计划将图像添加到文章，则需要先使用[Visual Studio Code](#using-visual-studio-code)将图像添加到分叉的"images"文件夹，或者确保已完成 Web 浏览器中的以下操作：</span><span class="sxs-lookup"><span data-stu-id="43512-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="43512-203">为 MicrosoftDocs/混合现实存储库分叉。</span><span class="sxs-lookup"><span data-stu-id="43512-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="43512-204">编辑了分叉中的文章。</span><span class="sxs-lookup"><span data-stu-id="43512-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="43512-205">将文章中引用的图像上传到分叉中的"mixed-reality-docs/images"文件夹。</span><span class="sxs-lookup"><span data-stu-id="43512-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="43512-206">创建了一 **个拉取** 请求，用于将分支合并到 MicrosoftDocs/混合现实"master"分支中。</span><span class="sxs-lookup"><span data-stu-id="43512-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="43512-207">若要了解如何设置自己的分叉存储库，请按照创建新 [文章 的说明操作](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="43512-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="43512-208">预览工作</span><span class="sxs-lookup"><span data-stu-id="43512-208">Previewing your work</span></span>

<span data-ttu-id="43512-209">通过 Web 浏览器GitHub预览时，可以选择页面顶部附近的"预览"选项卡，在提交之前预览工作。</span><span class="sxs-lookup"><span data-stu-id="43512-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="43512-210">预览更改review.docs.microsoft.com 仅适用于 Microsoft 员工</span><span class="sxs-lookup"><span data-stu-id="43512-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="43512-211">Microsoft 员工：将贡献内容合并到"master"分支后，可以在发布内容之前在 </hololens？branch=master>。</span><span class="sxs-lookup"><span data-stu-id="43512-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="43512-212">使用左侧列中的目录查找文章。</span><span class="sxs-lookup"><span data-stu-id="43512-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="43512-213">在浏览器中编辑与使用桌面客户端进行编辑</span><span class="sxs-lookup"><span data-stu-id="43512-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="43512-214">在浏览器中编辑是进行快速更改的最简单方法，但存在一些缺点：</span><span class="sxs-lookup"><span data-stu-id="43512-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="43512-215">不会进行拼写检查。</span><span class="sxs-lookup"><span data-stu-id="43512-215">You don't get spell-check.</span></span>
- <span data-ttu-id="43512-216">如果必须手动键入文章的文件名， (无法智能链接到其他) 。</span><span class="sxs-lookup"><span data-stu-id="43512-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="43512-217">上传和引用图像可能很麻烦。</span><span class="sxs-lookup"><span data-stu-id="43512-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="43512-218">如果愿意不解决这些问题，请使用桌面客户端（如[Visual Studio Code在参与](https://code.visualstudio.com/)时[提供一些](#useful-extensions)有用的扩展。</span><span class="sxs-lookup"><span data-stu-id="43512-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="43512-219">使用 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="43512-219">Using Visual Studio Code</span></span>

<span data-ttu-id="43512-220">出于 [上述原因，](#editing-in-the-browser-vs-editing-with-a-desktop-client)你可能更喜欢使用桌面客户端来编辑文档，而不是 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="43512-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="43512-221">建议使用[ Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="43512-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="43512-222">设置</span><span class="sxs-lookup"><span data-stu-id="43512-222">Setup</span></span>

<span data-ttu-id="43512-223">按照以下步骤配置Visual Studio Code存储库：</span><span class="sxs-lookup"><span data-stu-id="43512-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="43512-224">在 Web 浏览器中：</span><span class="sxs-lookup"><span data-stu-id="43512-224">In a web browser:</span></span>
    1. <span data-ttu-id="43512-225">为[电脑安装 Git。](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="43512-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="43512-226">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="43512-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="43512-227">[为 MicrosoftDocs/mixed-reality](#creating-a-new-article) 创建分叉（如果尚未创建）。</span><span class="sxs-lookup"><span data-stu-id="43512-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="43512-228">在分叉中，选择" **克隆或下载** 并复制 URL"。</span><span class="sxs-lookup"><span data-stu-id="43512-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="43512-229">在 Visual Studio Code 中创建分叉的本地Visual Studio Code：</span><span class="sxs-lookup"><span data-stu-id="43512-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="43512-230">在"视图 **"菜单中**，选择"**命令面板"。**</span><span class="sxs-lookup"><span data-stu-id="43512-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="43512-231">键入"Git： Clone"。</span><span class="sxs-lookup"><span data-stu-id="43512-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="43512-232">粘贴复制的 URL。</span><span class="sxs-lookup"><span data-stu-id="43512-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="43512-233">选择在电脑上保存克隆的地方。</span><span class="sxs-lookup"><span data-stu-id="43512-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="43512-234">在 **弹出窗口中选择** "打开存储库"。</span><span class="sxs-lookup"><span data-stu-id="43512-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="43512-235">编辑文档</span><span class="sxs-lookup"><span data-stu-id="43512-235">Editing documentation</span></span>

<span data-ttu-id="43512-236">使用以下工作流对文档进行更改，并Visual Studio Code：</span><span class="sxs-lookup"><span data-stu-id="43512-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="43512-237">上述有关[编辑和创建](#editing-an-existing-article)文章的所有[](#creating-a-new-article)指南以及编辑[Markdown](#markdown-basics)的基础知识也适用于使用 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="43512-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="43512-238">使用官方存储库确保克隆的分叉是最新的。</span><span class="sxs-lookup"><span data-stu-id="43512-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="43512-239">在 Web 浏览器中，创建拉取请求，将 MicrosoftDocs/混合现实"master"中其他参与者的最新更改同步到分叉 (确保箭头指向正确的) 。</span><span class="sxs-lookup"><span data-stu-id="43512-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![将更改从 MicrosoftDocs/mixed-reality 同步到分叉](images/sync-repos.png)
      
   2. <span data-ttu-id="43512-241">在Visual Studio Code"中，选择"同步"按钮，将新更新的分叉同步到本地克隆。</span><span class="sxs-lookup"><span data-stu-id="43512-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![单击同步按钮图像](images/sync-clone.png)
      
2. <span data-ttu-id="43512-243">使用 Visual Studio Code 在克隆的存储库创建或编辑Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="43512-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="43512-244">根据需要编辑一个或多个 (图像添加到"images"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="43512-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="43512-245">**在** 资源管理器 中 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="43512-245">**Save** changes in **Explorer**.</span></span>
      
      ![在资源管理器中选择"全部保存"](images/explorer-save.png)
      
   3. <span data-ttu-id="43512-247">**在源代码管理** 中 **提交所有 (** 在系统提示时写入提交) 。</span><span class="sxs-lookup"><span data-stu-id="43512-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![在源代码管理中选择"全部提交"](images/source-control-commit.png)
      
   4. <span data-ttu-id="43512-249">选择同步 **按钮**，将更改同步回源 (上的分叉GitHub) 。</span><span class="sxs-lookup"><span data-stu-id="43512-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![单击同步按钮](images/sync-back.png)
      
3. <span data-ttu-id="43512-251">在 Web 浏览器中，创建拉取请求，将分叉中的新更改同步回 MicrosoftDocs/混合现实"master" (确保箭头指向正确的) 。</span><span class="sxs-lookup"><span data-stu-id="43512-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="43512-253">有用的扩展</span><span class="sxs-lookup"><span data-stu-id="43512-253">Useful extensions</span></span>

<span data-ttu-id="43512-254">编辑Visual Studio Code时，以下扩展非常有用：</span><span class="sxs-lookup"><span data-stu-id="43512-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="43512-255">[Docs Markdown 扩展Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - 使用 **Alt+M** 打开文档创作选项的菜单，例如：</span><span class="sxs-lookup"><span data-stu-id="43512-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="43512-256">搜索和引用已上传的图像。</span><span class="sxs-lookup"><span data-stu-id="43512-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="43512-257">添加格式设置，如列表、表和文档特定的调用（如 `>[!NOTE]` ）。</span><span class="sxs-lookup"><span data-stu-id="43512-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="43512-258">搜索和引用内部链接和书签 (链接到页面中特定部分) 。</span><span class="sxs-lookup"><span data-stu-id="43512-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="43512-259">格式设置错误突出显示 (将鼠标悬停在错误上方，了解) 。</span><span class="sxs-lookup"><span data-stu-id="43512-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="43512-260">[代码拼写检查器](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - 拼写错误的单词将带有下划线;右键单击拼写错误的单词以将其更改或保存到字典中。</span><span class="sxs-lookup"><span data-stu-id="43512-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
