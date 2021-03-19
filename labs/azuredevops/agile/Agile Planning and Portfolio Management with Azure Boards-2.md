---
title: Agile Planning and Portfolio Management with Azure Boards
layout: page
sidebar: vsts
permalink: /labs/azuredevops/agile/
folder: /labs/azuredevops/agile/
version: Lab version - 1.37.1
updated: Last updated - 3/18/2021
redirect_from: "/labs/vsts/agile/index.htm"
---
<div class="rw-ui-container"></div>
<a name="Overview"></a>



# 使用Azure Boards进行敏捷规划和项目组合管理

> 更多Lab可以参考 https://aka.ms/devopslabs

*    
[主页](https://azuredevopslabs.com//default.html)/使用Azure Boards进行敏捷规划和项目组合管理

在本实验中，您将学习AzureBoards提供的敏捷计划和项目组合管理工具和流程，以及它们如何帮助您快速规划，管理和跟踪整个team的工作。您将探索产品积压，sprint积压和任务板，它们可用于跟踪Iterations过程中的工作流程。我们还将研究此版本中工具的增强功能，以适应更大的team和组织。

![MSteam](images/mslearn.png)是否需要其他学习？在Microsoft Learn上查看[**针对软件开发**](https://docs.microsoft.com/en-us/learn/modules/choose-an-agile-approach/)的 [**敏捷方法**](https://docs.microsoft.com/en-us/learn/modules/choose-an-agile-approach/)模块。

*   本实验要求您先完成<a href="../prereq/">先决条件</a>说明中任务1 。（此练习无需克隆，请跳过先决条件中的任务2）
  

### 任务1：创建及使用teams, areas, and iterations

1.  导航到Azure DevOps上的Parts Unlimited项目。它将类似于[https://dev.azure.com/YOURACCOUNT/Parts%20Unlimited](https://dev.azure.com/YOURACCOUNT/Parts%20Unlimited)。
    
2.  使用页面左下方的**Project settings**导航打开设置页面。
    
    ![](images/settings.png)
    
3.  选择**Teams**选项卡。此项目中已经有几个team，但是您将为此实验创建一个新的team。点击**New team**。
    
    ![](images/001.png)
    
4.  使用 **“ PUL-Web”**作为 **Team name**，然后单击**Create team** （保留默认值）。
    
    ![](images/002.png)
    
5.  选择新创建的team以查看其详细信息。
    
    ![](images/003.png)
    
6.  默认情况下，新team只有您一个成员。您可以使用此视图来管理成员资格，通知，仪表板等。但是首先，您将需要定义team的日程安排和范围。单击**Iterations和area路径**。
    
    ![](images/004.png)
    
7.  选择**Iterations**选项卡，然后单**Select Iteration**。该team将使用与其他team相同的Iterations计划，但是如果这对您的组织更好，您可以采用其他方法。
    
    ![](images/iteration.png)
    
8.  选择**Parts Unlimited\Sprint 1**，然后单击**Save and close**。请注意，第一个sprint已经通过。这是因为演示数据生成器旨在构建项目历史记录，以使该sprint发生在过去。
    
    ![](images/006.png)
    
9.  重复此过程以添加**Sprint 2**和**Sprint 3**（如上一步所述添加它们）。第二个sprint是我们当前的Iterations，第三个sprint是在不久的将来。
    
    ![](images/007.png)

    
10.  选择**Areas**选项卡。默认情况下，存在与team名称匹配的Area。
    
   ![](images/008.png)
    
11.  从area下拉列表中，选择**Include sub areas**。所有team的默认设置是排除sub areas路径。我们将对其进行更改以包括sub areas，以便team可以看到所有team的所有work items。可选地，管理team还可以选择不包括子area，从而在将work items目分配给team之一后立即将其从其视图中删除。
    
   ![](images/009.png)
    
<a name="Ex1Task2"></a>
### Task 2: 创建及使用work items-work items ###

work items在Azure DevOps中扮演着重要角色。无论是描述要完成的工作，发布的障碍，测试定义还是其他关键项，work items都是现代项目的主力军。在此任务中，您将集中于使用各种work items来设置计划，以扩展带有产品培训部分的Parts Unlimited网站。虽然要扩大公司产品的如此重要的部分可能会令人生畏，但Azure DevOps和Scrum流程使其非常易于管理。

![](images/010.png)

该任务旨在说明您可以使用多种方式创建不同类型的work items，并演示平台上可用功能的广泛性。因此，这些步骤不应被视为项目管理的规定性指导。这些功能旨在具有足够的灵活性以适合您的过程需求，因此您可以随时进行探索和试验。

1.  导航到**Overview \| Dashboards**。
    
    ![](images/011.png)
    
2.  选择**Parts Unlimited Team**的 **Overview** 仪表板。
    
    ![](images/012.png)
    
3.  在Azure DevOps中创建work items的方法有很多，我们将探讨其中的一些方法。有时，这就像从仪表板上解雇一样简单。在**New Work Item** 表单中，键入**"Product training"**，**然后选择**Epic**类型。点击**Create**。
    
    ![](images/new-wit.png) ![](images/013.png)
    
4.  将新work items分配给您自己，然后将**Areas**设置为**Parts Unlimited \\ PUL-Web**。将“**Iterations”**设置为**Parts Unlimited\Sprint 2** ，然后单击**Save & Close**。通常，您希望填写尽可能多的信息，但是出于本实验的目的，您可以在此处精益求精。
    
    ![](images/014.png)
    
5.  导航到**Boards \| Work Items**。
    
    ![](images/015.png)
    
6.  找到为**Product training**新创建的epic，然后将其打开。
    
    ![](images/016.png)
    
7.  work items表单包含您可能想要了解的有关work items的所有信息。这包括有关分配给谁的详细信息，其在许多参数中的状态以及自创建以来如何处理的所有相关信息和历史记录。**Related Work**是重点关注的领域之一。向此epic中添加功能的方法之一是选择**Add link \| New item**。
    
    ![](images/017.png)
    
8.  将**work items类型**设置为**Feature**，并将**Title** 设置为**"Training dashboard"**。单击**OK**。
    
    ![](images/018.png)
    
9.  该**Assignment**，**Area**和**Iteration**应该已经设置为与epic相同，甚至被链接到创建它的父项。点击**保存并关闭**。
    
    ![](images/019.png)
    
10.  导航到“ **Boards”**视图。
    
   ![](images/020.png)
    
11.  选择**PUL-Web板**。这将为该特定team打开Boards。
    
   ![](images/021.png)
    
12.  将板子从显示**待办事项**切换为显示**功能**。这将使向功能中添加任务和其他work items变得容易。
    
   ![](images/022.png)
    
13.  从“**培训”仪表板**下拉列表中，选择“**添加产品待办事项”**。
    
   ![](images/023.png)
    
14.  将第一个积压项目命名为**“作为客户，我想查看新教程”**，然后按**Enter键**保存。这将创建一个新的**Product Backlog Item**（PBI）work items，该work items是功能的子项，并共享其area和Iterations。
    
   ![](images/024.png)
    
15.  添加另外两个PBI，这些PBI旨在使客户能够查看他们最近查看的教程并请求新的教程。
    
   ![](images/025.png)
    
16.  将任务板视图切换回**Backlog项目**。
    
   ![](images/026.png)
    
17.  待办事项的状态定义了它们相对于完成的位置。尽管您可以使用该表单打开和编辑work items，但将卡拖到板上更容易。将第一个work items目**拖到“已批准”**。
    
   ![](images/027.png)
    
18.  您还可以扩展work items目卡，以方便地进行可编辑的详细信息。
    
   ![](images/028.png)
    
19.  将移动的PBI分配给您自己。
    
   ![](images/029.png)
    
20.  将第二个work items目拖到**Committed**阶段。
    
   ![](images/030.png)
    
21.  将最终的PBI拖到“**完成”**阶段。
    
   ![](images/031.png)
    
22.  任务板是积压工作的一个视图。通过单击“**查看为待办事项”**来**查看**表格形式。
    
   ![](images/032.png)
    
23.  单击“**扩展”**按钮，它使您可以查看这些work items下的嵌套任务。创建work items的另一种简单方法是使用待办事项列表上的“**添加”**按钮。单击它可将新任务添加到第一个积压项目。
    
   ![](images/033.png)
    
24.  将**标题**设置为**“添加最新教程的页面”**。将**剩余工作**设置为**“ 5”**，将**活动设置**为**“发展”**。点击**保存并关闭**。
    
   ![](images/034.png)
    
25.  向**“优化最新教程的数据查询”中**添加另一个任务。将其**剩余工作**设置为**“ 3”**，将其**活动设置**为**“设计”**。点击**保存并关闭**。
    
   ![](images/035.png)
    

### 任务3：管理sprint和容量

您的team通常在sprint的第一天举行的sprint计划会议期间建立sprint积压。每个sprint对应一个有时间限制的间隔，该间隔支持您的team使用敏捷流程和工具进行工作的能力。在计划会议期间，您的产品负责人与您的team一起确定那些故事或待办事项以在sprint中完成。

计划会议通常包括两个部分。在第一部分中，team和产品所有者根据以前的sprint经验，确定team认为可以在sprint中完成的积压项目。这些项目将添加到sprint待办事项列表中。在第二部分中，您的team确定如何开发和测试每个项目。然后，他们定义并估计完成每个项目所需的任务。最后，您的team承诺根据这些估计来实施部分或全部项目。

1.  您的sprint待办事项应包含您的team在分配的时间内成功计划和完成工作所需的所有信息，而不必着急。在开始计划sprint之前，您将需要创建，确定优先级并估算积压并定义sprint。使用导航导航到“ **Sprints”**视图。
    
    ![](images/036.png)
    
2.  从“**查看选项”**下拉列表中，选择“**工作详细信息”**面板选项。
    
    ![](images/037.png)
    
3.  当前的sprint范围非常有限。“**待办事项”**阶段有两个任务，需要进行8个小时的估计工作。此时，尚未分配任何任务。
    
    ![](images/038.png)
    
4.  将“**添加页面”**任务分配给自己。请注意，这将更新容量视图。
    
    ![](images/039.png)
    
5.  选择**容量**选项卡。通过此视图，您可以定义用户可以执行的活动以及达到的容量级别。在这种情况下，将您的容量设置为每天允许**“ 1”**小时的**开发**。请注意，您可以为每个用户添加其他活动，以防他们做的事不只是开发。
    
    ![](images/040.png)
    
6.  但是，假设您要去度假。点击**0天**下**休息日**。
    
    ![](images/041.png)
    
7.  将您的假期设置为在当前sprint期间（在接下来的几周内）跨越五个工作日。单击**确定**。
    
    ![](images/042.png)
    
8.  点击**保存**。
    
    ![](images/043.png)
    
9.  返回**任务栏**。
    
    ![](images/044.png)
    
10.  请注意，容量视图已更新以反映您的可用带宽。这个确切的数字可能会有所不同，但是对于此处的屏幕快照，sprint容量为11小时（11个工作日内每天1小时）。
    
   ![](images/045.png)
    
11.  评估板的一项便利功能是您可以轻松地在线更新关键数据。定期更新“**剩余工作”**估算值是一个好习惯，以反映每个任务的预期时间。假设您已经查看了“**添加页面”**任务的工作，发现实际上所需的时间比最初预期的要长。将其设置为该sprint的总容量。
    
   ![](images/046.png)
    
12.  请注意，这是如何最大程度地扩展**开发**和您的个人能力的。由于它们足够大以覆盖分配的任务，因此它们保持绿色。但是，由于其他任务需要额外的3个小时，因此超出了**Teams**的整体能力。
    
   ![](images/047.png)
    
13.  解决此容量问题的一种方法是将任务移至将来的Iterations。有几种方法可以完成此操作。首先，您可以在此处打开任务并在对话框中对其进行编辑。另一方面，“**待办事项”**视图提供了一个**嵌入式**菜单选项来移动它。现在不要移动它。
    
   ![](images/048.png)
    
14.  返回到**任务板**视图。
    
   ![](images/049.png)
    
15.  从**查看选项**下拉菜单中选择**人员**。
    
   ![](images/050.png)
    
16.  这将调整您的视图，以便您可以按人（而不是按积压项目）查看任务的进度。
    
   ![](images/051.png)
    
17.  还有很多可用的自定义。单击**配置team设置**按钮。
    
   ![](images/052.png)
    
18.  在“**样式”**选项卡上，单击“**添加样式规则”，**然后将“**名称****”**设置为**“ Development”**。选择**绿卡颜色**。如果符合以下规则标准，这会将所有卡涂成绿色。
    
   ![](images/053.png)
    
19.  为“**活动=开发”**添加规则。这会将分配给**开发**活动的所有卡设置为绿色。
    
   ![](images/054.png)
    
20.  “**待办事项”**选项卡允许您设置可用于导航的级别。默认情况下不包含epic，但您可以在此处进行更改。
    
   ![](images/055.png)
    
21.  您还可以指定team遵循的**工作日**。这适用于容量和燃尽计算。
    
   ![](images/056.png)
    
22.  “**使用错误”**选项卡允许您指定错误在板上的呈现方式。
    
   ![](images/057.png)
    
23.  单击“**保存并关闭”**以保存样式规则。
    
   ![](images/058.png)
    
24.  与**开发**相关的任务现在是绿色的，非常容易识别。
    
   ![](images/059.png)
    

To maximize a team’s ability to consistently deliver high quality software, Kanban emphasize two main practices. The first, visualize the flow of work, requires you to map your team’s workflow stages and configure your Kanban board to match. The second, constrain the amount of work in progress, requires you to set work-in-progress (WIP) limits. You’re then ready to track progress on your Kanban board and monitor key metrics to reduce lead or cycle time. Your Kanban board turns your backlog into an interactive signboard, providing a visual flow of work. As work progresses from idea to completion, you update the items on the board. Each column represents a work stage, and each card represents a user story (blue cards) or a bug (red cards) at that stage of work. However, every team develops its own process over time, so the ability to customize the Kanban board to match the way your team works is crucial.

1.  导航到**Boards**。
    
    ![](images/060.png)
    
2.  单击**配置team设置**按钮。
    
    ![](images/061.png)
    
3.  team正在强调处理数据的工作，因此，与访问或存储数据相关的任何任务都应特别注意。选择**标签颜色**标签。点击**添加标签颜色，**输入标签**“数据”**。每当积压的项目或错误用**data**标记时，该标记将突出显示。
    
    ![](images/062.png)
    
4.  您还可以指定要在卡片上包含的**注释**，以使其更易于阅读和浏览。启用注释后，可以通过单击每个卡上的可视化文件轻松访问该类型的子work items。
    
    ![](images/063.png)
    
5.  “**测试”**选项卡使您可以配置测试在卡上的显示方式和行为。
    
    ![](images/064.png)
    
6.  单击**保存并关闭**。
    
    ![](images/065.png)
    
7.  打开**查看新教程**积压项目。
    
    ![](images/066.png)
    
8.  为**“数据”**和**“ ux”**添加标签。点击**保存并关闭**。
    
    ![](images/067.png)
    
9.  请注意，这两个标签现在在卡上可见，尽管**数据**标签在配置时突出显示为黄色。
    
    ![](images/068.png)
    
10.  单击**配置team设置**按钮。
    
   ![](images/069.png)
    
11.  选择**列**选项卡。本部分允许您向工作流程添加新的阶段。单击**添加列，**然后将**名称**设置为**“已通过质量检查”**。将在**制品限制**设置为**“ 1”**，这表示在此阶段一次只能有一个work items目。通常，您可以将其设置得更高一些，但是这里只有两个work items来演示该功能。移动舞台，使其发生在**Committed**和**Done**之间。
    
   ![](images/070.png)
    
12.  单击**保存并关闭**。
    
   ![](images/071.png)
    
13.  现在，您将在工作流程中看到新的阶段。
    
   ![](images/072.png)
    
14.  将work items从“已**提交”**和**“完成”**移到“**质量检查已批准”中**。
    
   ![](images/073.png)
    
15.  现在，该载物台超出了其在**制品**限制，并以红色显示为警告。
    
   ![](images/074.png)
    
16.  将**最近查看的**积压项目移回**Committed**。
    
   ![](images/075.png)
    
17.  单击**配置team设置**按钮。
    
   ![](images/076.png)
    
18.  返回到“**列”**选项卡，然后选择“**质量检查已批准”**。在将工作移入列与开始工作之间通常存在滞后。为了克服这种滞后并显示实际的工作状态，您可以打开拆分列。拆分时，每列包含两个子列：**Doing**和**Done**。拆分列使您的team可以实现拉模型。如果没有拆分列，team将向前推进工作，以表明他们已经完成了工作阶段。但是，将其推进到下一个阶段并不一定意味着team成员立即开始对该项目进行工作。选中将**列拆分为do和done**来为此创建两个单独的列。
    
   ![](images/077.png)
    
19.  当您的team更新从一个阶段到下一个阶段的工作状态时，这有助于他们就**完成的工作**达成共识。通过为每个看板列指定**完成**条件的**定义**，可以帮助您共享将项目移至下游阶段之前需要完成的基本任务。添加使用markdown**完成**的**定义**，例如**“通过\*\*全部\*\*测试”。**。单击**保存并关闭**。
    
   ![](images/078.png)
    
20.  请注意，“**质量检查批准”**阶段现在具有“**执行”**和**“完成”**列。
    
   ![](images/079.png)
    
21.  您也可以单击列标题旁边的图标以阅读“**完成”**的**定义**。
    
   ![](images/080.png)
    
22.  单击**配置team设置**按钮。
    
   ![](images/081.png)
    
23.  您的看板板支持您可视化从新到完成的工作流程的能力。添加**泳道时**，还可以可视化支持不同服务级别类的工作状态。您可以创建泳道来表示支持您的跟踪需求的任何其他维度。在“**泳道”**选项卡上，单击“**添加Swimlane”，**然后将“**名称****”**设置为**“ Expedite”**。单击**保存并关闭**。
    
   ![](images/082.png)
    
24.  将“已**提交”**work items拖放到“**质量检查已批准” | 这样**做是为了在QA带宽可用时将其识别为优先级。
    
   ![](images/083.png)
    
25.  如果您想查看具有更多work items目的更复杂的电路板，请从team下拉列表中选择“**零件无限team**”。
    
   ![](images/084.png)
    
26.  该板为您提供了一个试验和查看结果的场所。
    
   ![](images/085.png)
    

1.  选择**概述| 仪表板**。
    
    ![](images/086.png)
    
2.  从仪表板下拉菜单中，选择**零件无限team概览**。仪表板使team可以可视化状态并监视整个项目的进度。一目了然，您可以做出明智的决定，而不必深入到team项目站点的其他部分。“概述”页面提供对默认team仪表板的访问，您可以通过添加，删除或重新排列磁贴来对其进行自定义。每个图块都对应一个小部件，该小部件可提供对一个或多个特征或功能的访问。
    
    ![](images/087.png)
    
3.  在信息中心下拉菜单中，选择**新建信息中心**。
    
    ![](images/088.png)
    
4.  将**名称**设置为**“产品培训”，**然后选择**PUL-Web**team。点击**创建**。
    
    ![](images/089.png)
    
5.  单击**添加窗口小部件**。
    
    ![](images/090.png)
    
6.  在“**添加小部件”**面板中，搜索**“ sprint”**以查找专注于**sprint的**现有小部件。选择“ **Sprint概述”**，然后单击“**添加”**。
    
    ![](images/091.png)
    
7.  许多小部件都有您可以配置的选项。单击**设置**按钮。
    
    ![](images/092.png)
    
8.  设置的数量和深度将因小部件而异。单击**关闭**以关闭。
    
    ![](images/093.png)
    
9.  再次在小部件中搜索**“ sprint”，**然后添加“ **Sprint Capacity”**小部件。
    
    ![](images/094.png)
    
10.  单击**完成编辑**。
    
   ![](images/095.png)
    
11.  现在，您可以在自定义仪表板上查看当前sprint的两个重要方面。
    
   ![](images/096.png)
    
12.  自定义仪表板的另一种方法是基于work items查询生成图表，您可以将其共享到仪表板。选择**板子| 查询**。
    
   ![](images/097.png)
    
13.  点击**新建查询**。
    
   ![](images/098.png)
    
14.  将第一项设置为**work items类型=任务**，将第二项设置为**area路径=零件无限制\\ PUL-Web**。
    
   ![](images/099.png)
    
15.  点击**保存查询**。
    
   ![](images/100.png)
    
16.  将**名称**设置为**“ Web任务”**，将**文件夹设置**为**共享查询**。单击**确定**。
    
   ![](images/101.png)
    
17.  选择“**图表”**选项卡，然后单击“**新建图表”**。
    
   ![](images/102.png)
    
18.  点击**新建图表**。
    
   ![](images/103.png)
    
19.  将图表的**名称**设置为**“ Web任务-按分配”**，**将“****分组依据”设置**为“**分配给”**。单击**确定**保存。
    
   ![](images/104.png)
    
20.  您现在可以将此图表添加到仪表板。
    
   ![](images/105.png)
    

在Azure DevOps中，您可以通过过程自定义工作跟踪体验。流程定义了work items跟踪系统以及您通过Azure DevOps访问的其他子系统的构建块。每当您创建team项目时，都将选择包含项目所需构建基块的过程。

Azure DevOps支持两种流程类型。首先，核心系统进程（Scrum，Agile和CMMI系统进程）被锁定。您无法自定义这些过程。第二种类型，即继承的过程，是从核心系统过程创建的。您可以自定义这些过程。

此外，所有进程都是共享的。也就是说，一个或多个team项目可以引用一个流程。您可以自定义流程，而不是自定义单个team项目。对流程所做的更改会自动更新所有引用该流程的team项目。

创建继承的流程后，您可以对其进行自定义，基于该流程创建team项目，并迁移现有的team项目以对其进行引用。在将Gitteam项目迁移到继承的流程之前，无法对其进行自定义。

在此任务中，我们将创建一个继承自Scrum的新流程。我们将要做的一项更改是添加一个积压项目字段，该字段旨在跟踪专有的PartsUnlimited票证ID。

1.  单击左上角的**Azure DevOps**徽标导航到帐户根目录。
    
    ![](images/106.png)
    
2.  在左下角，点击**组织设置**。
    
    ![](images/107.png)
    
3.  选择“**委员会”**下的“**流程”**选项卡。
    
    ![](images/process.png)
    
4.  从**Scrum**下拉列表中，选择**创建继承的流程**。
    
    ![](images/109.png)
    
5.  将继承的进程的名称设置为**Customized Scrum**，然后单击“**创建进程”**。
    
    ![](images/110.png)
    
6.  打开**自定义Scrum**。您可能需要刷新浏览器才能看到它。
    
    ![](images/111.png)
    
7.  选择**产品待办事项项目**。
    
    ![](images/112.png)
    
8.  单击**新建字段**。
    
    ![](images/113.png)
    
9.  将新字段的**名称**设置为**“ PUL Ticket ID”**。
    
    ![](images/114.png)
    
10.  在**布局**选项卡上，将**标签**设置为**“ Ticket ID”**。同时为**“ PartsUnlimited”****创建一个新组**。单击**添加字段**。
    
   ![](images/115.png)
    
11.  现在已经配置了自定义过程，让我们切换“零件无限”项目以使用它。使用面包屑返回到“**所有进程”**根目录。
    
   ![](images/116.png)
    
12.  我们的项目当前使用**Scrum**，因此请选择该过程。
    
   ![](images/117.png)
    
13.  切换到“**项目”**选项卡。
    
   ![](images/118.png)
    
14.  从“**零件无限”**的上下文菜单中。选择**更改过程**。
    
   ![](images/119.png)
    
15.  选择“**定制Scrum”**过程，然后单击“**保存”**。
    
   ![](images/120.png)
    
16.  使用徽标链接返回到帐户信息中心。
    
   ![](images/121.png)
    
17.  打开**零件无限**门户。
    
   ![](images/122.png)
    
18.  选择**板子| work items目**。
    
   ![](images/123.png)
    
19.  打开第一个积压项目。
    
   ![](images/124.png)
    
20.  现在，您将在流程定制过程中定义的**PartsUnlimited**组下看到**Ticket ID**字段。您可以像对待其他任何文本字段一样对待它。
    
   ![](images/125.png)
    
21.  保存work items后，Azure DevOps还将保存新的自定义信息，以便可用于查询以及其余的Azure DevOps。
    

您可以观看以下视频，引导您完成本实验中介绍的所有步骤
<iframe width="560" height="315" src="https://www.youtube.com/embed/WWUf5OWeBD0" frameborder="0" allowfullscreen="true"> </iframe>

