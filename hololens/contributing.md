---
title: 参与说明
description: 了解如何使用 GitHub 风格 Markdown 为 docs.microsoft.com 平台上的 HoloLens 文档做贡献。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283654"
---
# <span data-ttu-id="b426c-103">为 HoloLens 文档做贡献</span><span class="sxs-lookup"><span data-stu-id="b426c-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="b426c-104">欢迎使用 [HoloLens 文档](https://github.com/MicrosoftDocs/Hololens)！</span><span class="sxs-lookup"><span data-stu-id="b426c-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="b426c-105">在此存储库创建或编辑的任何文章 **都将对公众可见。**</span><span class="sxs-lookup"><span data-stu-id="b426c-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="b426c-106">HoloLens 文档显示在 Docs.microsoft.com 平台上，该平台将 GitHub 风格 Markdown 与 Markdig 功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="b426c-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="b426c-107">在此存储库编辑的内容格式化为样式化页面，显示在 https://docs.microsoft.com/hololens 。</span><span class="sxs-lookup"><span data-stu-id="b426c-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="b426c-108">此页面介绍有关提供 Markdown 基础知识和链接的基本步骤和指南。</span><span class="sxs-lookup"><span data-stu-id="b426c-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="b426c-109">感谢您的贡献！</span><span class="sxs-lookup"><span data-stu-id="b426c-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="b426c-110">可用 repos</span><span class="sxs-lookup"><span data-stu-id="b426c-110">Available repos</span></span>

| <span data-ttu-id="b426c-111">存储库名称</span><span class="sxs-lookup"><span data-stu-id="b426c-111">Repository name</span></span> | <span data-ttu-id="b426c-112">URL</span><span class="sxs-lookup"><span data-stu-id="b426c-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="b426c-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="b426c-113">HoloLens</span></span> | [<span data-ttu-id="b426c-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="b426c-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="b426c-115">混合现实</span><span class="sxs-lookup"><span data-stu-id="b426c-115">Mixed Reality</span></span> | [<span data-ttu-id="b426c-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="b426c-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="b426c-117">VR Enthusiasts 指南</span><span class="sxs-lookup"><span data-stu-id="b426c-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="b426c-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="b426c-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="b426c-119">准备工作</span><span class="sxs-lookup"><span data-stu-id="b426c-119">Before you start</span></span>

<span data-ttu-id="b426c-120">如果还没有帐户，则需要创建 [GitHub 帐户](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="b426c-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="b426c-121">如果你是 Microsoft 员工，将 GitHub 帐户链接到 Microsoft 开放源代码门户 [上的 Microsoft 别名](https://repos.opensource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b426c-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="b426c-122">加入 **"Microsoft"和\*\*\*\*"MicrosoftDocs"** 组织。</span><span class="sxs-lookup"><span data-stu-id="b426c-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="b426c-123">设置 GitHub 帐户时，我们还建议采取以下安全预防措施：</span><span class="sxs-lookup"><span data-stu-id="b426c-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="b426c-124">为 [GitHub 帐户创建强密码](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="b426c-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="b426c-125">启用 [双重身份验证](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="b426c-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="b426c-126">将 [恢复代码保存在](https://github.com/settings/auth/recovery-codes) 安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b426c-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="b426c-127">更新 [公共配置文件设置](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="b426c-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="b426c-128">设置你的姓名，并考虑将*公用电子邮件*设置为 *"不显示我的电子邮件地址"。*</span><span class="sxs-lookup"><span data-stu-id="b426c-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="b426c-129">建议上传个人资料图片，因为缩略图显示在你参与的文档页面上。</span><span class="sxs-lookup"><span data-stu-id="b426c-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="b426c-130">如果计划使用命令行，请考虑为 Windows 设置 [Git 凭据管理器](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。</span><span class="sxs-lookup"><span data-stu-id="b426c-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="b426c-131">这样，你每次进行贡献时就不需要输入密码。</span><span class="sxs-lookup"><span data-stu-id="b426c-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="b426c-132">发布系统与 GitHub 关联，因此这些步骤非常重要。</span><span class="sxs-lookup"><span data-stu-id="b426c-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="b426c-133">使用 GitHub 别名将你列为每篇文章的作者或参与者。</span><span class="sxs-lookup"><span data-stu-id="b426c-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="b426c-134">编辑现有文章</span><span class="sxs-lookup"><span data-stu-id="b426c-134">Editing an existing article</span></span>

<span data-ttu-id="b426c-135">使用以下工作流在 Web 浏览器中通过\*\* GitHub 更新现有文章：</span><span class="sxs-lookup"><span data-stu-id="b426c-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="b426c-136">导航到想要在"mixed-reality-docs"文件夹中编辑的文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="b426c-137">选择右上角 (铅笔) 图标的编辑按钮，该图标将自动将可释放的分支从"master"分支中分叉。</span><span class="sxs-lookup"><span data-stu-id="b426c-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![编辑文章。](images/editpage.png)
   
3. <span data-ttu-id="b426c-139">根据 ["Markdown](#markdown-basics)基础知识"编辑文章的内容。</span><span class="sxs-lookup"><span data-stu-id="b426c-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="b426c-140">更新每篇文章顶部的元数据：</span><span class="sxs-lookup"><span data-stu-id="b426c-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="b426c-141">**title**： 查看文章时显示在浏览器选项卡中的页面标题。</span><span class="sxs-lookup"><span data-stu-id="b426c-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="b426c-142">页面标题用于 SEO 和索引编制，因此除非有必要，否则不要更改标题 (尽管这不太关键，然后再将文档公开) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="b426c-143">**description：** Write a brief description of the article's content， which boosts SEO and discovery.</span><span class="sxs-lookup"><span data-stu-id="b426c-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="b426c-144">**author**： If you're the primary owner of the page， add your GitHub alias here.</span><span class="sxs-lookup"><span data-stu-id="b426c-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="b426c-145">**ms.author：** 如果你是页面的主要所有者，请在此处添加 Microsoft 别名 (无需 @microsoft.com，只需别名) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="b426c-146">**ms.date：** Update the date if you're adding major content to the page， but not for fixes like clarification， formatting， grammar， or spelling.</span><span class="sxs-lookup"><span data-stu-id="b426c-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="b426c-147">**关键字：** 关键字有助于 SEO (搜索引擎优化) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="b426c-148">添加关键字，用逗号和空格分隔，这些关键字特定于您的文章，但列表中最后一个关键字后面没有标点符号。</span><span class="sxs-lookup"><span data-stu-id="b426c-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="b426c-149">无需添加适用于所有文章的全局关键字，因为这些关键字在其他地方进行管理。</span><span class="sxs-lookup"><span data-stu-id="b426c-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="b426c-150">完成文章编辑后，向下滚动并选择"建议**文件更改"。**</span><span class="sxs-lookup"><span data-stu-id="b426c-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="b426c-151">下一页上，选择 **"创建拉取请求** "，将自动创建的分支合并到"主控"中。</span><span class="sxs-lookup"><span data-stu-id="b426c-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="b426c-152">对要编辑的下一篇文章重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="b426c-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="b426c-153">重命名或删除现有文章</span><span class="sxs-lookup"><span data-stu-id="b426c-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="b426c-154">如果更改将重命名或删除现有文章，请务必添加重定向。</span><span class="sxs-lookup"><span data-stu-id="b426c-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="b426c-155">这样，任何具有指向现有文章的链接的人最终仍将在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="b426c-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="b426c-156">重定向由存储库根.openpublishing.redirection.js上的文件管理。</span><span class="sxs-lookup"><span data-stu-id="b426c-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="b426c-157">若要添加指向.openpublishing.redirection.js的重定向，请向数组添加 `redirections` 一个条目：</span><span class="sxs-lookup"><span data-stu-id="b426c-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="b426c-158">`source_path`它是要删除的旧文章的相对存储库路径。</span><span class="sxs-lookup"><span data-stu-id="b426c-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="b426c-159">请确保路径以 `mixed-reality-docs` . `.md`</span><span class="sxs-lookup"><span data-stu-id="b426c-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="b426c-160">它是 `redirect_url` 从旧文章到新文章的相对公用 URL。</span><span class="sxs-lookup"><span data-stu-id="b426c-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="b426c-161">确保此 URL **不包含** 或 ，因为它引用的是公用 `mixed-reality-docs` `.md` URL，而不是存储库路径。</span><span class="sxs-lookup"><span data-stu-id="b426c-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="b426c-162">允许链接到新文章中使用 `#section` 的部分。</span><span class="sxs-lookup"><span data-stu-id="b426c-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="b426c-163">如有必要，您还可以在此处使用指向另一个站点的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="b426c-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="b426c-164">指示是否要保留上一个文件的文档 ID。</span><span class="sxs-lookup"><span data-stu-id="b426c-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="b426c-165">默认值为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="b426c-165">The default is `false`.</span></span> <span data-ttu-id="b426c-166">`true`如果要保留重定向文章中 `ms.documentid` 的属性值，请使用。</span><span class="sxs-lookup"><span data-stu-id="b426c-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="b426c-167">如果保留文档 ID，则页面视图和排名等数据将传输到目标文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="b426c-168">如果重定向主要是重命名，而不是指向仅涵盖部分相同内容的不同文章的指针，请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b426c-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="b426c-169">如果添加重定向，请务必同时删除旧文件。</span><span class="sxs-lookup"><span data-stu-id="b426c-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="b426c-170">创建新文章</span><span class="sxs-lookup"><span data-stu-id="b426c-170">Creating a new article</span></span>

<span data-ttu-id="b426c-171">使用以下工作流在 *Web* 浏览器中通过 GitHub 在文档存储库中创建新文章：</span><span class="sxs-lookup"><span data-stu-id="b426c-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="b426c-172">使用右上方的"分叉"按钮 (MicrosoftDocs/mixed-reality"master"分支分支\*\*\*\*) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![分支主分支。](images/forkbranch.png)
   
2. <span data-ttu-id="b426c-174">在"mixed-reality-docs"文件夹中，选择右上方 **的** "创建新文件"。</span><span class="sxs-lookup"><span data-stu-id="b426c-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="b426c-175">为文章创建页面名称 (使用连字符而不是空格，并且不使用标点符号或撇号) 并追加".md"</span><span class="sxs-lookup"><span data-stu-id="b426c-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![命名新页面。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="b426c-177">请确保从"mixed-reality-docs"文件夹中创建新文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="b426c-178">可以通过检查新文件名行中的"/mixed-reality-docs/"来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="b426c-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="b426c-179">在新建页面顶部，添加以下元数据块：</span><span class="sxs-lookup"><span data-stu-id="b426c-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="b426c-180">按照上述部分中的说明填写相关的 [元数据字段](#editing-an-existing-article)。</span><span class="sxs-lookup"><span data-stu-id="b426c-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="b426c-181">使用 [Markdown 基础知识编写文章内容](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="b426c-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="b426c-182">在 `## See also` 文章底部添加一个包含指向其他相关文章的链接的部分。</span><span class="sxs-lookup"><span data-stu-id="b426c-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="b426c-183">完成后，选择 **"提交新文件"。**</span><span class="sxs-lookup"><span data-stu-id="b426c-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="b426c-184">选择 **"新建** 拉取请求"，将分叉的"主"分支合并到 MicrosoftDocs/混合现实"主 (确保箭头以正确的方式指向) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

## <span data-ttu-id="b426c-186">Markdown 基础知识</span><span class="sxs-lookup"><span data-stu-id="b426c-186">Markdown basics</span></span>

<span data-ttu-id="b426c-187">以下资源将帮助您了解如何使用 Markdown 语言编辑文档：</span><span class="sxs-lookup"><span data-stu-id="b426c-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="b426c-188">Markdown 基础知识</span><span class="sxs-lookup"><span data-stu-id="b426c-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="b426c-189">用于编写 Markdown for docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b426c-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="b426c-190">添加表</span><span class="sxs-lookup"><span data-stu-id="b426c-190">Adding tables</span></span>

<span data-ttu-id="b426c-191">由于样式表docs.microsoft.com，即使尝试内联 CSS，它们也不会具有边框或自定义样式。</span><span class="sxs-lookup"><span data-stu-id="b426c-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="b426c-192">它看起来会在短时间内工作，但最终平台会从表中去除样式设置。</span><span class="sxs-lookup"><span data-stu-id="b426c-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="b426c-193">因此请提前规划并保持表格简单。</span><span class="sxs-lookup"><span data-stu-id="b426c-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="b426c-194">[下面是一个使 Markdown 表变得简单的网站](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="b426c-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="b426c-195">如果您 [使用的是 Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) (，Visual Studio [Code ](#using-visual-studio-code) 文档扩展还便于生成) 文档。</span><span class="sxs-lookup"><span data-stu-id="b426c-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="b426c-196">添加图像</span><span class="sxs-lookup"><span data-stu-id="b426c-196">Adding images</span></span>

<span data-ttu-id="b426c-197">你需要将图像上载到存储库的"mixed-reality-docs/images"文件夹，然后在文章中适当地引用它们。</span><span class="sxs-lookup"><span data-stu-id="b426c-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="b426c-198">图像将自动以全尺寸显示，这意味着大图像将填满文章的整个宽度。</span><span class="sxs-lookup"><span data-stu-id="b426c-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="b426c-199">我们建议在上传图像之前对图像进行预大小调整。</span><span class="sxs-lookup"><span data-stu-id="b426c-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="b426c-200">虽然建议的宽度介于 600 和 700 像素之间，但如果它是一个密集屏幕截图或屏幕截图的一小部分，应分别向上或向下调整大小。</span><span class="sxs-lookup"><span data-stu-id="b426c-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b426c-201">在合并之前，只能将图像上载到分叉存储库。</span><span class="sxs-lookup"><span data-stu-id="b426c-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="b426c-202">因此，如果您计划向文章添加图像，您需要首先使用 [Visual Studio 代码](#using-visual-studio-code) 将图像添加到分叉的"images"文件夹中，或确保已完成 Web 浏览器中的下列操作：</span><span class="sxs-lookup"><span data-stu-id="b426c-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="b426c-203">分叉 MicrosoftDocs/混合现实存储库。</span><span class="sxs-lookup"><span data-stu-id="b426c-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="b426c-204">在分叉中编辑了文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="b426c-205">将文章中引用的图像上载到分叉中的"mixed-reality-docs/images"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b426c-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="b426c-206">创建了一 **个拉取** 请求，用于将分叉合并到 MicrosoftDocs/mixed-reality"master"分支中。</span><span class="sxs-lookup"><span data-stu-id="b426c-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="b426c-207">若要了解如何设置自己的分叉存储库，请按照创建新 [文章的说明操作](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="b426c-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="b426c-208">预览你的工作</span><span class="sxs-lookup"><span data-stu-id="b426c-208">Previewing your work</span></span>

<span data-ttu-id="b426c-209">通过 Web 浏览器在 GitHub 中编辑时，可以选择\*\*\*\* 页面顶部附近的"预览"选项卡，在提交之前预览你的工作。</span><span class="sxs-lookup"><span data-stu-id="b426c-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="b426c-210">预览更改review.docs.microsoft.com仅适用于 Microsoft 员工</span><span class="sxs-lookup"><span data-stu-id="b426c-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="b426c-211">Microsoft 员工：一旦你的贡献合并到"主"分支，你可以先查看内容，然后再在它 https://review.docs.microsoft.com/hololens?branch=master 公开。</span><span class="sxs-lookup"><span data-stu-id="b426c-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="b426c-212">使用左侧列中的目录查找文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="b426c-213">在浏览器中编辑与使用桌面客户端进行编辑</span><span class="sxs-lookup"><span data-stu-id="b426c-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="b426c-214">在浏览器中编辑是进行快速更改的最简单方法，但存在一些缺点：</span><span class="sxs-lookup"><span data-stu-id="b426c-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="b426c-215">你无法进行拼写检查。</span><span class="sxs-lookup"><span data-stu-id="b426c-215">You don't get spell-check.</span></span>
- <span data-ttu-id="b426c-216">如果必须手动键入文章的文件名， (其他文章的任何智能链接) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="b426c-217">上载和引用图像可能很麻烦。</span><span class="sxs-lookup"><span data-stu-id="b426c-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="b426c-218">如果不愿意处理这些问题，请使用桌面客户端（如Visual Studio [代码](https://code.visualstudio.com/) ，提供 [一些有用的](#useful-extensions) 扩展。</span><span class="sxs-lookup"><span data-stu-id="b426c-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="b426c-219">使用Visual Studio代码</span><span class="sxs-lookup"><span data-stu-id="b426c-219">Using Visual Studio Code</span></span>

<span data-ttu-id="b426c-220">出于 [上述原因，](#editing-in-the-browser-vs-editing-with-a-desktop-client)你可能更喜欢使用桌面客户端来编辑文档，而不是 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="b426c-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="b426c-221">我们建议使用Visual Studio [代码](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="b426c-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="b426c-222">安装</span><span class="sxs-lookup"><span data-stu-id="b426c-222">Setup</span></span>

<span data-ttu-id="b426c-223">按照以下步骤配置Visual Studio代码以用于此存储库：</span><span class="sxs-lookup"><span data-stu-id="b426c-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="b426c-224">在 Web 浏览器中：</span><span class="sxs-lookup"><span data-stu-id="b426c-224">In a web browser:</span></span>
    1. <span data-ttu-id="b426c-225">为[电脑安装 Git。](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="b426c-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="b426c-226">安装 [Visual Studio代码](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="b426c-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="b426c-227">[Fork MicrosoftDocs/mixed-reality（](#creating-a-new-article) 如果尚未创建）。</span><span class="sxs-lookup"><span data-stu-id="b426c-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="b426c-228">在分叉中，选择 **"克隆"或下载** 并复制 URL。</span><span class="sxs-lookup"><span data-stu-id="b426c-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="b426c-229">使用代码创建分叉的本地Visual Studio克隆：</span><span class="sxs-lookup"><span data-stu-id="b426c-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="b426c-230">从"**视图"** 菜单中，选择 **"命令调色板"。**</span><span class="sxs-lookup"><span data-stu-id="b426c-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="b426c-231">键入"Git： Clone"。</span><span class="sxs-lookup"><span data-stu-id="b426c-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="b426c-232">粘贴您复制的 URL。</span><span class="sxs-lookup"><span data-stu-id="b426c-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="b426c-233">选择在电脑上保存克隆位置。</span><span class="sxs-lookup"><span data-stu-id="b426c-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="b426c-234">在 **弹出窗口中选择** "打开存储库"。</span><span class="sxs-lookup"><span data-stu-id="b426c-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="b426c-235">编辑文档</span><span class="sxs-lookup"><span data-stu-id="b426c-235">Editing documentation</span></span>

<span data-ttu-id="b426c-236">使用以下工作流对包含以下代码的文档Visual Studio代码：</span><span class="sxs-lookup"><span data-stu-id="b426c-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="b426c-237">以上有关编辑[和创建](#editing-an-existing-article)文章的所有[](#creating-a-new-article)指南以及编辑[Markdown](#markdown-basics)的基础知识也适用于使用 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="b426c-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="b426c-238">使用官方存储库确保克隆的分叉是最新的。</span><span class="sxs-lookup"><span data-stu-id="b426c-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="b426c-239">在 Web 浏览器中，创建拉取请求，将 MicrosoftDocs/mixed-reality"master"中其他参与者的最新更改同步到分叉 (确保箭头指向正确的方向) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![将更改从 MicrosoftDocs/mixed-reality 同步到分叉](images/sync-repos.png)
      
   2. <span data-ttu-id="b426c-241">在Visual Studio代码中，选择同步按钮以将最新更新的分叉同步到本地克隆。</span><span class="sxs-lookup"><span data-stu-id="b426c-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![单击同步按钮图像](images/sync-clone.png)
      
2. <span data-ttu-id="b426c-243">使用代码创建或编辑克隆的Visual Studio文章。</span><span class="sxs-lookup"><span data-stu-id="b426c-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="b426c-244">编辑一个或多个文章 (图像添加到"images"文件夹（如有必要) ）。</span><span class="sxs-lookup"><span data-stu-id="b426c-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="b426c-245">**在** 资源管理器中 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="b426c-245">**Save** changes in **Explorer**.</span></span>
      
      ![在资源管理器中选择"全部保存"](images/explorer-save.png)
      
   3. <span data-ttu-id="b426c-247">**在出现提示** 时，提交源 **控件 (写入** 提交消息) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![在源代码管理中选择"全部提交"](images/source-control-commit.png)
      
   4. <span data-ttu-id="b426c-249">选择 **同步按钮** ，将更改同步回 GitHub (分支中的源) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![单击同步按钮](images/sync-back.png)
      
3. <span data-ttu-id="b426c-251">在 Web 浏览器中，创建拉取请求，将分叉中的新更改同步回 MicrosoftDocs/混合现实"主 (确保箭头以正确的方式) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![创建从分叉到 MicrosoftDocs/mixed-reality 的拉取请求](images/pr-to-master.png)

### <span data-ttu-id="b426c-253">有用的扩展</span><span class="sxs-lookup"><span data-stu-id="b426c-253">Useful extensions</span></span>

<span data-ttu-id="b426c-254">以下Visual Studio代码扩展在编辑文档时很有用：</span><span class="sxs-lookup"><span data-stu-id="b426c-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="b426c-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like：</span><span class="sxs-lookup"><span data-stu-id="b426c-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="b426c-256">搜索和引用已上传的图像。</span><span class="sxs-lookup"><span data-stu-id="b426c-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="b426c-257">添加格式，如列表、表和文档特定的调用，如 `>[!NOTE]` 。</span><span class="sxs-lookup"><span data-stu-id="b426c-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="b426c-258">搜索和引用内部链接和书签 (链接到页面中特定) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="b426c-259">将突出显示格式错误 (将鼠标悬停在错误上方，以了解) 。</span><span class="sxs-lookup"><span data-stu-id="b426c-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="b426c-260">[代码拼写检查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 器 - 拼写错误的单词将带下划线;右键单击拼写错误的单词以将其更改或保存到词典。</span><span class="sxs-lookup"><span data-stu-id="b426c-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
