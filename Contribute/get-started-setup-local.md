---
title: 设置本地 Git 存储库
description: 本文介绍创建本地 Git 存储库和提供文档的指南，包括创建分支和克隆过程。
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d9c7211641fb05aaca8a76e10c7216ff61a5d23c
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="8f962-103">设置本地 Git 文档存储库</span><span class="sxs-lookup"><span data-stu-id="8f962-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="8f962-104">本文介绍在本地计算机上设置 Git 存储库的步骤，旨在为 Microsoft 文档提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8f962-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="8f962-105">参与者可以使用本地克隆的存储库来添加新项目，对现有文章进行主要编辑或更改图片。</span><span class="sxs-lookup"><span data-stu-id="8f962-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="8f962-106">运行这些一次性设置活动即可开始参与其中：</span><span class="sxs-lookup"><span data-stu-id="8f962-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8f962-107">确定相应的存储库</span><span class="sxs-lookup"><span data-stu-id="8f962-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="8f962-108">对 GitHub 帐户创建存储库分支</span><span class="sxs-lookup"><span data-stu-id="8f962-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="8f962-109">为克隆文件选择一个本地文件夹</span><span class="sxs-lookup"><span data-stu-id="8f962-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="8f962-110">将存储库克隆到本地计算机</span><span class="sxs-lookup"><span data-stu-id="8f962-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="8f962-111">配置上游远程值</span><span class="sxs-lookup"><span data-stu-id="8f962-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f962-112">如果要对文章进行次要更改，无需完成本文中的相关步骤。</span><span class="sxs-lookup"><span data-stu-id="8f962-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="8f962-113">可直接转到[次要/间歇更改工作流](light-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="8f962-113">You can continue directly to the [minor/infrequent changes workflow](light-workflow.md).</span></span>
>

## <a name="overview"></a><span data-ttu-id="8f962-114">概述</span><span class="sxs-lookup"><span data-stu-id="8f962-114">Overview</span></span>

<span data-ttu-id="8f962-115">要为 Microsoft 文档站点供稿，可以通过克隆相应的文档存储库在本地创建和编辑 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="8f962-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="8f962-116">Microsoft 要求对你自己的 github 帐户创建相应的存储库分支，以便在其中具有读/写权限来存储建议的更改。</span><span class="sxs-lookup"><span data-stu-id="8f962-116">Microsoft requires you to fork the appropriate repository into your own github account, so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="8f962-117">然后，使用拉取请求将更改合并到只读的中央共享存储库。</span><span class="sxs-lookup"><span data-stu-id="8f962-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![GitHub 三角形](./media/git-and-github-initial-setup.png)

<span data-ttu-id="8f962-119">如果你刚接触 GitHub，请观看以下视频，了解创建分支和克隆过程的概念性概述：</span><span class="sxs-lookup"><span data-stu-id="8f962-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="8f962-120">确定存储库</span><span class="sxs-lookup"><span data-stu-id="8f962-120">Determine the repository</span></span>

<span data-ttu-id="8f962-121">在 [docs.microsoft.com](https://docs.microsoft.com) 上托管的文档驻留在 [github.com](https://www.github.com) 上的多个不同存储库中。</span><span class="sxs-lookup"><span data-stu-id="8f962-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="8f962-122">如果不确定要使用的存储库，请使用 Web 浏览器访问 docs.microsoft.com 上的文章。</span><span class="sxs-lookup"><span data-stu-id="8f962-122">If you are unsure of which repository to use, then visit the article on docs.microsoft.com using your web browser.</span></span> <span data-ttu-id="8f962-123">选择文章右上方的“编辑”链接（铅笔图标）。</span><span class="sxs-lookup"><span data-stu-id="8f962-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![单击“编辑”来确定存储库和文件位置。](media/edit-article.png)

2. <span data-ttu-id="8f962-125">该链接会将你带到 github.com 位置，以获取相应存储库中对应的 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="8f962-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="8f962-126">请注意用于查看存储库名称的 URL。</span><span class="sxs-lookup"><span data-stu-id="8f962-126">Note the URL to view the repository name.</span></span>

   ![请注意用于确定存储库位置的 URL。](media/public-repo.png)

   <span data-ttu-id="8f962-128">例如，这些常用的存储库可用于下列公开发表的内容：</span><span class="sxs-lookup"><span data-stu-id="8f962-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="8f962-129">Azure 文档 [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="8f962-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="8f962-130">SQL Server 文档 [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="8f962-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="8f962-131">Visual Studio 文档 [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="8f962-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="8f962-132">.NET 文档 [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="8f962-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="8f962-133">Azure .Net SDK 文档 [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="8f962-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="8f962-134">为存储库创建分支</span><span class="sxs-lookup"><span data-stu-id="8f962-134">Fork the repository</span></span>
<span data-ttu-id="8f962-135">使用合适的存储库，通过 GitHub 网站，将存储库的一个分支创建到自己的 GitHub 帐户中。</span><span class="sxs-lookup"><span data-stu-id="8f962-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="8f962-136">因为所有主文档存储库都提供只读访问，所以需要个人分支，这表示无法直接更改存储库中的内容。</span><span class="sxs-lookup"><span data-stu-id="8f962-136">A personal fork is required since all main documentation repositories provide read-only access, which means you cannot make changes directly on content in the repositories.</span></span> <span data-ttu-id="8f962-137">要进行更改，必须将[拉取请求](git-github-fundamentals.md#pull-requests)从自己的分支提交到存储库。</span><span class="sxs-lookup"><span data-stu-id="8f962-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="8f962-138">为推进此过程，首先需要自己拥有一个存储库副本并对其具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="8f962-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="8f962-139">GitHub 分支就很适合该用途。</span><span class="sxs-lookup"><span data-stu-id="8f962-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="8f962-140">转到主存储库的 GitHub 页面，然后单击右上角的“创建分支”按钮。</span><span class="sxs-lookup"><span data-stu-id="8f962-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![GitHub 个人资料示例](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="8f962-142">如果出现提示，请选择 GitHub 帐户磁贴作为创建分支的目标位置。</span><span class="sxs-lookup"><span data-stu-id="8f962-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="8f962-143">此提示在 GitHub 帐户中创建存储库的副本，也就是分支。</span><span class="sxs-lookup"><span data-stu-id="8f962-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="8f962-144">选择本地文件夹</span><span class="sxs-lookup"><span data-stu-id="8f962-144">Choose a local folder</span></span>
<span data-ttu-id="8f962-145">将存储库的副本保存在本地文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8f962-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="8f962-146">有些存储库可能会很大；例如，azure-docs，最高可达 5 GB。</span><span class="sxs-lookup"><span data-stu-id="8f962-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="8f962-147">选择具有可用磁盘空间的位置。</span><span class="sxs-lookup"><span data-stu-id="8f962-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="8f962-148">所选的文件夹名称应便于记忆和键入。</span><span class="sxs-lookup"><span data-stu-id="8f962-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="8f962-149">例如，将根文件夹设为 `C:\docs\` 或在用户配置文件目录 `~/Documents/docs/` 中创建文件夹</span><span class="sxs-lookup"><span data-stu-id="8f962-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8f962-150">避免选择嵌套在另一个 git 存储库文件夹位置内的本地文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="8f962-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="8f962-151">尽管可以将 git 克隆文件夹存储在另一个文件夹旁边，但将 git 文件夹嵌套在另一个文件夹内会导致文件跟踪错误。</span><span class="sxs-lookup"><span data-stu-id="8f962-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="8f962-152">启动 Git Bash</span><span class="sxs-lookup"><span data-stu-id="8f962-152">Launch Git Bash</span></span>

   ![启动 Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="8f962-154">Git Bash 启动的默认位置通常都在主目录 (~) 或在 Windows OS 上的 `/c/users/<Windows-user-account>/`。</span><span class="sxs-lookup"><span data-stu-id="8f962-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="8f962-155">要确定当前目录，请在 $ 提示符处键入 `pwd`。</span><span class="sxs-lookup"><span data-stu-id="8f962-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="8f962-156">将目录更改为创建用于在本地托管存储库的的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8f962-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="8f962-157">请注意，Git Bash 的文件夹路径使用正斜杠的 Linux 约定，而不是反斜杠。</span><span class="sxs-lookup"><span data-stu-id="8f962-157">Note that Git Bash uses Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="8f962-158">例如，`cd /c/docs/ ` 或 `cd ~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="8f962-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="8f962-159">创建本地克隆</span><span class="sxs-lookup"><span data-stu-id="8f962-159">Create a local clone</span></span>

<span data-ttu-id="8f962-160">使用 Git Bash，准备运行 clone 命令，将存储库（分支）副本下载到当前目录上的设备。</span><span class="sxs-lookup"><span data-stu-id="8f962-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="8f962-161">使用 Git 凭据管理器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="8f962-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="8f962-162">如果安装了适用于 Windows 的 Git 的最新版本并接受了默认安装，则默认启用 Git 凭据管理器。</span><span class="sxs-lookup"><span data-stu-id="8f962-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="8f962-163">Git 凭据管理器使身份验证更加简便，因为在使用 GitHub 重新建立经过身份验证的连接和远程时，不需要撤回个人访问令牌。</span><span class="sxs-lookup"><span data-stu-id="8f962-163">Git Credential Manager makes authentication much easier, because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="8f962-164">通过提供存储库名称来运行 clone 命令。</span><span class="sxs-lookup"><span data-stu-id="8f962-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="8f962-165">克隆在本地计算机上下载（克隆）分支存储库。</span><span class="sxs-lookup"><span data-stu-id="8f962-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="8f962-166">可以通过 GitHub UI 中的“克隆或下载”按钮获取分支的克隆命令的 GitHub URL：</span><span class="sxs-lookup"><span data-stu-id="8f962-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![克隆或下载](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="8f962-168">确保在克隆期间指定分支的路径，而不是在其中创建分支的主存储库。</span><span class="sxs-lookup"><span data-stu-id="8f962-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="8f962-169">否则，无法提供更改。</span><span class="sxs-lookup"><span data-stu-id="8f962-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="8f962-170">通过个人 GitHub 用户帐户引用分支，例如 `github.com/<github-username>/<repo>`。</span><span class="sxs-lookup"><span data-stu-id="8f962-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="8f962-171">克隆命令应类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="8f962-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="8f962-172">在系统提示时输入 GitHub 凭据。</span><span class="sxs-lookup"><span data-stu-id="8f962-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![GitHub 登录](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="8f962-174">在系统提示时输入双因素身份验证代码。</span><span class="sxs-lookup"><span data-stu-id="8f962-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![GitHub 双因素身份验证](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="8f962-176">凭据将进行保存并用于对未来的 GitHub 请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f962-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="8f962-177">每台计算机仅需执行此身份验证一次。</span><span class="sxs-lookup"><span data-stu-id="8f962-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="8f962-178">克隆命令运行分支的存储库文件副本并将其下载到本地磁盘上的新文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8f962-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="8f962-179">在当前文件夹中创建新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8f962-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="8f962-180">这可能需要花费几分钟，具体取决于存储库大小。</span><span class="sxs-lookup"><span data-stu-id="8f962-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="8f962-181">可以浏览文件夹，查看完成后的结构。</span><span class="sxs-lookup"><span data-stu-id="8f962-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="8f962-182">配置远程上游</span><span class="sxs-lookup"><span data-stu-id="8f962-182">Configure remote upstream</span></span>
<span data-ttu-id="8f962-183">克隆存储库后，为名为“上游”的主存储库设置只读的远程连接。</span><span class="sxs-lookup"><span data-stu-id="8f962-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="8f962-184">利用此上游 URL，使本地存储库与其他人所做的最新更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="8f962-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="8f962-185">git remote 命令用于设值配置值。</span><span class="sxs-lookup"><span data-stu-id="8f962-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="8f962-186">使用 fetch 命令从上游存储库刷新分支信息。</span><span class="sxs-lookup"><span data-stu-id="8f962-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="8f962-187">如果使用的是 Git 凭据管理器，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="8f962-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="8f962-188">替换 \<repo\> 和 \<organization\> 占位符。</span><span class="sxs-lookup"><span data-stu-id="8f962-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="8f962-189">查看配置值并确认 URL 是正确的。</span><span class="sxs-lookup"><span data-stu-id="8f962-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="8f962-190">确保“源”URL 指向个人分支。</span><span class="sxs-lookup"><span data-stu-id="8f962-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="8f962-191">确保“上游”URL 指向主存储库，例如 MicrosoftDocs 或 Azure。</span><span class="sxs-lookup"><span data-stu-id="8f962-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="8f962-192">显示远程输出示例。</span><span class="sxs-lookup"><span data-stu-id="8f962-192">Example remote output is shown.</span></span> <span data-ttu-id="8f962-193">名为 MyGitAccount 的虚构 git 帐户配置了个人访问令牌来访问存储库 azure-docs：</span><span class="sxs-lookup"><span data-stu-id="8f962-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="8f962-194">如果出错，可以删除远程值。</span><span class="sxs-lookup"><span data-stu-id="8f962-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="8f962-195">要删除上游值，请运行命令 `git remote remove upstream`。</span><span class="sxs-lookup"><span data-stu-id="8f962-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f962-196">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8f962-196">Next steps</span></span>
- <span data-ttu-id="8f962-197">了解有关添加和更新内容的详细信息，请继续访问 [GitHub 参与工作流](how-to-write-workflows-major.md)。</span><span class="sxs-lookup"><span data-stu-id="8f962-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>