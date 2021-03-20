---
title: 在Visual Studio Code和Azure DevOps中使用Git进行版本控制
layout: page
sidebar: vsts
permalink: /labs/azuredevops/git/
folder: /labs/azuredevops/git/
version: Lab version - 1.31.1
updated: Last updated - 06/11/2020
redirect_from: "/labs/vsts/git/index.htm"
---

<div class="rw-ui-container"></div>
<a name="Overview"></a>

Azure DevOps支持两种类型的版本控制，Git和Team Foundation版本控制（TFVC）。这是两个版本控制系统的快速概述：

* **团队基础版本控制（TFVC）**：TFVC是集中式版本控制系统。通常，团队成员在其开发机器上每个文件只有一个版本。历史数据仅在服务器上维护。分支是基于路径的，并在服务器上创建。
    
* ** Git **：Git是一个分布式版本控制系统。 Git信息库可以位于本地（例如，在开发人员的计算机上）。每个开发人员在其开发机上都有源存储库的副本。开发人员可以在其开发机器上提交每组更改，并执行版本控制操作（例如历史记录），并且无需网络连接即可进行比较。
    

Git是新项目的默认版本控制提供程序。除非您特别需要TFVC中的集中式版本控制功能，否则应在项目中使用Git进行版本控制。

在本实验中，您将学习如何建立本地Git存储库，可以轻松地将其与Azure DevOps中的集中式Git存储库同步。此外，您还将了解有关Git分支和合并支持的信息。您将使用Visual Studio Code，但是相同的过程适用于将任何与Git兼容的客户端与Azure DevOps一起使用。

*安装了[C＃]（https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp）扩展名的[Visual Studio代码]（https://code.visualstudio.com/）。
    
* [Git for Windows]（https://gitforwindows.org/）2.21.0或更高版本。
    
*本实验要求您从[先决条件说明]（chrome-extension：// cjedbglnccaioiolemnfhjncicchinao / prereq）中完成任务1（跳过克隆，在练习中完成）。
    

1.打开** Visual Studio代码**。在此任务中，您将配置Git凭据帮助器以安全地存储用于与Azure DevOps通信的Git凭据。如果您已经配置了凭据助手和Git身份，则可以跳到下一个任务。
    
2.从主菜单中，选择** Terminal |。新终端**以打开终端窗口。
    
3.执行以下命令以配置凭据帮助器。
    
         git config --global credential.helper wincred
        
    
4.下面的命令将为Git提交配置您的用户名和电子邮件。将参数替换为您的首选用户名并通过电子邮件发送并执行它们。
    
         git config --global user.name“ John Doe”
         git config --global user.email johndoe@example.com
        
    

1.在浏览器选项卡中，导航到Azure DevOps上的团队项目。
    
2.获取Git存储库的本地副本称为“克隆”。每个主流开发工具都支持此功能，并且将能够连接到Azure Repos来获取最新的可使用资源。导航到** Repos **中心。
     
![](images/000.png)

    
3.单击**克隆**。
    
![](images/001.png)
    
4.单击回购克隆URL旁边的“复制到剪贴板”按钮。您可以将此URL插入任何与Git兼容的工具中，以获取代码库的副本。
    
  ![](images/002.png)
    
5.打开** Visual Studio Code **的实例。
    
6.按** Ctrl + Shift + P **以显示**命令面板**。命令面板提供了一种轻松便捷的方法来访问各种任务，包括第三方扩展提供的任务。
    
7.执行** Git：Clone **命令。输入**“ Git” **使其进入候选列表可能会有所帮助。
    
  ![](images/003.png)
    
8.将URL粘贴到您的仓库中，然后按** Enter **。
    
  ![](images/004.png)
    
9.选择一个本地路径以将存储库克隆到。
    
10.出现提示时，登录到您的Azure DevOps帐户。
    
11.克隆完成后，单击“打开”以打开克隆的存储库。您可以忽略有关打开项目的任何警告。解决方案可能无法处于可构建状态，但这没关系，因为我们将专注于与Git一起工作，并且不需要构建项目本身。
    
  ![](images/005_new.png)
    

当您对文件进行更改时，Git会将更改记录在本地存储库中。您可以通过暂存更改来选择要提交的更改。提交总是针对您本地的Git存储库，因此您不必担心提交是完美的或准备与他人共享。您可以在继续工作时进行更多提交，并在准备好将其共享时将更改推送给其他人。

提交中有什么内容？

Git提交包含以下内容：

*文件在提交中已更改。 Git在提交中将所有文件更改的内容保留在您的存储库中。这样可以使其保持快速并允许智能合并。
    
*对父提交的引用。 Git使用这些引用来管理您的代码历史记录。
    
*描述提交的消息。您在创建提交时将此消息提供给Git。最好保持此消息的描述性，但要直言不讳。
    

1.从“资源管理器”选项卡中，打开“ ** / PartsUnlimited-aspnet45 / src / PartsUnlimitedWebsite / Models / CartItem.cs **”。
    
  ![](images/012.png)
    
2.在文件中添加注释。评论的内容并不重要，因为目标只是做出改变。按** Ctrl + S **保存文件。
    
  ![](images/013.png)
    
3.选择“源代码管理”选项卡以查看解决方案的一项更改。
    
  ![](images/014.png)
    
4.输入提交消息“ **”“我的提交” **，然后按** Ctrl + Enter **在本地提交。
    
  ![](images/015.png)
    
5.如果询问您是否要自动暂存更改并直接提交更改，请单击“始终”。我们将在稍后的实验中讨论“分期”。
    
  ![](images/016.png)
    
6.单击“同步更改”按钮以将您的更改与服务器同步。如果出现提示，请确认同步。
    
  ![](images/017.png)
    

1.切换到Azure DevOps浏览器选项卡。您可以在** Repos **中心的** Commits **选项卡下查看Azure DevOps上的最新提交。
    
  ![](images/018.png)
    
2.最近的提交应该在顶部。
    
  ![](images/019.png)
    

暂存更改使您可以有选择地将某些文件添加到提交中，而忽略其他文件中所做的更改。

1.返回到“ Visual Studio代码” **。
    
2.通过编辑您之前的注释并保存文件来更新打开的** CartItem.cs **类。
    
  ![](images/020.png)
    
3.同时打开** Category.cs **。
    
  ![](images/021.png)
    
4.在** Category.cs **中添加一个新注释，这样将有两个具有更改的文件。保存文件。
    
  ![](images/022.png)
    
5.从“源代码控制”选项卡中，单击“ CartItem.cs **”的“阶段更改”按钮。
    
  ![](images/023.png)
    
6.这将为** CartItem.cs **准备提交而无需** Category.cs **。
    
  ![](images/024.png)
    
7.输入**“添加的评论” **的评论。从“更多操作”下拉列表中，选择“提交分段”。
    
  ![](images/025_new.png)
    
8.单击“同步更改”按钮以将提交的更改与服务器同步。请注意，由于仅提交了分阶段的更改，因此其他更改仍在本地挂起。
    
  ![](images/026.png)
    

Git使用存储在每个提交中的父级参考信息来管理开发的完整历史记录。您可以轻松地查看此提交历史记录，以找出何时进行文件更改，并使用终端或从许多可用的Visual Studio Code扩展之一中确定代码版本之间的差异。您还可以使用Azure DevOps门户查看更改。

Git对** Branches and Merges **功能的使用通过请求请求起作用，因此您开发的提交历史记录不一定按时间顺序排列。使用历史记录比较版本时，请考虑两次提交之间的文件更改，而不是两个时间点之间的文件更改。 master分支中文件的最新更改可能来自两周前在feature分支中创建的提交，但直到昨天才合并。

1.在“源代码管理”选项卡中，选择“ Category.cs **”。
    
  ![](images/027.png)
    
2.将打开一个比较视图，使您可以轻松找到所做的更改。在这种情况下，这只是一条评论。
    
  ![](images/028.png)
    
3.转到“ Azure DevOps”中的“提交”视图，以找到一些源分支和合并。这些提供了一种方便的方式来可视化对源进行更改的时间和方式。
    
  ![](images/031.png)
    
4.从“合并的PR 27”的下拉列表中，选择“浏览文件”。
    
  ![](images/032_new.png)
    
5.此视图提供了在该提交时浏览源状态的功能，因此您可以查看和下载这些文件。
    
  ![](images/033_new.png)
    

您可以从Web上的“分支”视图在Azure DevOps Git存储库中管理工作。您还可以自定义视图以跟踪您最关心的分支，以便您可以掌握团队所做的更改。

向分支提交更改不会影响其他分支，您可以与其他分支共享分支，而不必将更改合并到主项目中。您还可以创建新分支，以将功能或错误修复的更改与您的主分支和其他工作隔离开。由于分支是轻量级的，因此在分支之间进行切换既快捷又容易。当使用分支时，Git不会创建源的多个副本，而是在您开始处理分支时使用提交中存储的历史记录信息在分支上重新创建文件。您的Git工作流程应创建并使用分支机构来管理功能和错误修正。 Git工作流程的其余部分，例如共享代码和使用拉取请求查看代码，全部通过分支进行。隔离分支中的工作使通过简单地更改当前分支来更改正在处理的内容变得非常简单。

1.返回到“ Visual Studio代码” **。
    
2.单击左下方的** master **分支。
    
  ![](images/034.png)
    
3.选择**从...创建新分支。
    
  ![](images/035.png)
    
4.为新分支输入名称**“ dev” **，然后按** Enter **。
    
  ![](images/036.png)
    
5.选择** master **作为参考分支。
    
  ![](images/037.png)
    
6.您现在正在该分支上工作。
    
  ![](images/038.png)
    

Git跟踪正在处理的分支，并确保在签出分支时文件与该分支上的最新提交相匹配。分支使您可以同时使用同一本地Git存储库中的多个版本的源代码。您可以使用Visual Studio Code来发布，签出和删除分支。

1.单击分支旁边的“发布更改”按钮。
    
  ![](images/039.png)
    
2.在“ Azure DevOps”浏览器选项卡中，选择“分支”。
    
  ![](images/040.png)
    
3.您应该看到新推送的** dev **分支。单击更多操作下拉菜单，然后选择“删除分支”按钮将其删除。确认删除。
    
  ![](images/041_new.png)
    
4.返回到“ Visual Studio代码” **。
    
5.单击** dev **分支。
    
  ![](images/042.png)
    
6.请注意，列出了两个** dev **分支。存在本地（** dev **）分支，因为在删除服务器分支时不会将其删除。服务器（** origin / dev **）在那里，因为它尚未被修剪。选择** master **分支以将其签出。
    
  ![](images/043.png)
    
7.按** Ctrl + Shift + P **打开**命令面板**。
    
8.开始输入**“ Git：删除” **，然后在可见时选择** Git：删除分支**。
    
  ![](images/044.png)
    
9.只有一个本地分支要删除，因此选择它。
    
  ![](images/045.png)
    
10.单击** master **分支。
    
  ![](images/046.png)
    
11.请注意，本地** dev **分支消失了，但是远程** origin / dev **仍然显示。
    
  ![](images/047.png)
    
12.按** Ctrl + Shift + P **打开**命令面板**。
    
13.开始输入**“ Git：Fetch” **，然后在可见时选择** Git：Fetch（Prune）**。此命令将更新本地快照中的原始分支，并删除不再存在的原始分支。
    
  ![](images/048.png)
    
14.您可以通过选择屏幕底部的** Output **窗口来准确检查这些任务在做什么。
    
  ![](images/049.png)
    
15.请注意，如果在输出控制台中看不到Git日志，则可能需要选择** Git **作为源。
    
  ![](images/050.png)
    
16.单击** master **分支。
    
  ![](images/051.png)
    
17. ** origin / dev **分支不应再出现在列表中。
    
  ![](images/052.png)
    

除了Visual Studio Code中可用的所有功能之外，您还可以从Azure DevOps门户管理回购分支。

1.切换到Azure DevOps浏览器选项卡。
    
2.导航到** Repos |分行**。点击**新建分支**。
    
  ![](images/053_new.png)
    
3.为新分支输入名称“ ** release” **。使用“工作项目链接”下拉菜单选择一个或多个工作项目以链接到该新分支。点击**创建分支**以创建它。
    
  ![](images/054_new.png)
    
4.创建分支后，它将在列表中可用。
    
  ![](images/055.png)
    
5.返回到“ Visual Studio代码” **。
    
6.按** Ctrl + Shift + P **打开**命令面板**。
    
7.开始输入**“ Git：Fetch” **，然后在可见时选择** Git：Fetch **。此命令将更新本地快照中的原始分支。
    
  ![](images/056.png)
    
8.单击** master **分支。
    
  ![](images/057.png)
    
9.选择**来源/发行**。这将创建一个名为**“ release” **的新本地分支，并将其签出。
    
  ![](images/058.png)
    

1.返回到Azure DevOps，然后从更多操作下拉列表中单击“删除分支”以将其删除。
    
  ![](images/059_new.png)
    
2.如果需要，可以通过搜索确切的分支名称来“还原分支”。选择“还原分支**”，如下所示。
    
  ![](images/060_new.png)
    

对于防止可能与重要合并冲突的新更改或将分支置于只读状态，锁定是理想的选择。另外，如果您只是想确保在合并分支之前对其进行更改，则可以使用分支策略和拉取请求而不是锁定请求。

锁定不会阻止克隆存储库或将分支中所做的更新提取到本地存储库中。如果您锁定分支，请与您的团队分享原因，并确保他们知道解锁分支后该如何处理。

1.从** master **上下文菜单中，选择** Lock **。
    
  ![](images/061.png)
    
2.分支现已锁定。
    
  ![](images/062.png)
    
3.现在，使用相同的过程来“解锁”分支。
    
  ![](images/063.png)
    

1.尽管看起来似乎不多，但产品团队已决定该网站的版本正是v1.1所需的版本。为了将其标记为此类，请导航至“标签”标签。
    
  ![](images/064.png)
    
2.单击“创建标签”。
    
  ![](images/065.png)
    
3.输入**“ v1.1” **的名称**和**“ Great release！” **的**说明**。点击**创建**。
    
  ![](images/066.png)
    
4.现在，您已经在此版本中标记了该项目。您可以出于多种原因标记提交，Azure DevOps提供了编辑和删除它们以及管理其权限的灵活性。
    
    \ ##！[]（chrome-extension：//cjedbglnccaioiolemnfhjncicchinao/labs/azuredevops/git/images/067.png)##
    

您可以在团队项目中创建Git仓库，以管理项目的源代码。每个Git存储库都有其自己的权限集和分支，以使其自身与项目中的其他工作隔离。

1.从项目“添加”下拉列表中，选择“新存储库”。
    
  ![](images/068.png)
    
2.将“存储库名称”设置为““新存储库”” **。请注意，您还可以选择创建一个名为** README.md **的文件。这将是当有人在浏览器中导航到存储库根目录时呈现的默认markdown文件。此外，您可以使用**。gitignore **文件预先配置存储库。该文件基于命名模式和/或路径指定从源代码管理中忽略哪些文件。有多个模板可用，其中包括基于要创建的项目类型而忽略的常见模式和路径。点击**创建**。
    
  ![](images/069.png)
    
3.就这样。您的仓库已准备就绪。现在，您可以使用Visual Studio或您选择的工具克隆它。
    
  ![](images/070.png)
    

###任务2：删除并重命名Git仓库

1.有时您需要重命名或删除存储库，这很容易。打开“项目设置” **。
    
  ![](images/ps.png)
    
2.在“仓库”下选择“仓库”。
    
  ![](images/settings-repos.png)
    
3.从“新建仓库”上下文菜单中，选择“删除存储库”。或者，您可以在此处重命名。
    
  ![](images/repo-delete.png)
    
4.输入名称“新仓库”以确认仓库，然后单击“删除”。
    
  ![](images/deleterepowindow.png)！


[来源]（https://azuredevopslabs.com/labs/azuredevops/git/）