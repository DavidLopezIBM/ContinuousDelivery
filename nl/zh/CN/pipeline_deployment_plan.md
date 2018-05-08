---

copyright:
  years: 2017, 2018
lastupdated: "2018-1-9"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 定制组合管道的部署计划
{: #tasks_overview}

在组合管道的部署计划中，任务代表与软件部署相关联的一些对业务有意义的活动。任务在部署计划中定义。

{:shortdesc}

**注**：此功能仅在美国南部区域可用。

大部分任务都具有起始点、结束点和可测量的持续时间。任务可以是以下其中一种类型：

<ul>
<li>手动任务可以代表与软件部署相关联的任何活动，如使服务器脱机或更新数据库。</li>
<li>UrbanCode Deploy 任务代表 IBM&reg; UrbanCode&reg; Deploy 应用程序。您可以运行具有 IBM UrbanCode Deploy 类型任务的 IBM UrbanCode Deploy 应用程序。</li>
<li>Continuous Delivery Pipeline 任务代表 {{site.data.keyword.deliverypipeline}} 的实例，其为 {{site.data.keyword.contdelivery_full}} 的一部分。您可以管理具有此任务类型的 {{site.data.keyword.deliverypipeline}} 实例。</li>
<li>延迟任务代表在特定时间发生的紧急事件。</li>
<li>标头任务是组织元素。例如，您可以使用标头任务来识别任务组。</li>
</ul>

<!-- You can add tasks to deployment plans by creating tasks or you can import tasks from CSV files that are created by IBM UrbanCode Release or another application. You can also copy tasks from other deployment plans. See [Importing tasks](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) for information about the format of the CSV file. -->

## 创建任务
{: #tasks_create}

创建任务时，您选择要将任务添加到的部署计划。缺省情况下，新任务会插入到部署计划的结尾。创建任务后，您可以将其移动或复制并粘贴到其他部署计划。您还可以创建与其他[任务](/docs/services/ContinuousDelivery/pipeline_deployment_plan.html#tasks_dependencies)的依赖关系。

保存任务后，系统会显示该任务的操作图标。您可以使用操作图标，在部署期间更改任务的状态。所有任务都具有**跳过**操作图标。其他图标（如**启动**）会在上下文适当时显示。

![典型部署计划](../UCCR/images/deploy-plan-intro.png)

*图 1. 具有任务和操作图标的简单部署计划*

部署计划中的每个任务都包含在单独一行中。下表描述针对每个任务所显示的信息。

### 表 1. 任务属性

| 属性| 描述|
| ------------------ | ------------------ |
| 名称|任务名称|
| 类型|任务的类型：手动、Continuous Delivery Pipeline、延迟、电子邮件、标头 / 注释、UrbanCode Deploy|             
| 状态|任务状态：未启动、已完成、失败、已跳过、不适用|
| 所有者|任务分配给的人员|
| 开始时间|开始时间，或者根据计划开始或其他任务的估算持续时间预期的开始时间|
| 结束时间|解决完任务的时间|
| 持续时间|从任务开始到任务解决的时间长度（分钟）|
| 依赖关系数|任务先决条件和任务依赖项的合计任务数|

---
任务添加到部署计划后，您可以使用几种方法来对其进行管理：


   * 要移动任务，可将其拖动到新位置。

   * 要复制任务或组，可单击该任务，单击**复制**图标 <img class="inline" src="../UCCR/images/copy-group.png"  alt="复制图标">，将光标置于您要插入所复制任务的位置，然后单击**粘贴**图标 <img class="inline" src="../UCCR/images/paste-group.png"  alt="粘贴图标">。

   * 要从部署计划中剪切任务或组，可单击该任务并单击**剪切** <img class="inline" src="../UCCR/images/cut-group.png"  alt="剪切图标">。

   * 要删除任务，请单击该任务并单击**删除** <img class="inline" src="../UCCR/images/trash-group.png"  alt="删除图标">。此时即会从部署计划中除去任务。

## 创建手动任务
{: #tasks_manual}

一般而言，手动任务表示与具有起始点、结束点和可测量持续时间的软件发布相关联的一些活动。

要创建手动任务，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，单击**创建任务**。要在计划的特定位置插入任务，请在单击**创建任务**前，先选择某个任务。新任务即会插入到所选任务之前。

1. 在“创建任务”窗口的**类型**列表中，选择**手动**。

1. 在**名称**字段中，输入任务的名称。

3. 在**持续时间（分钟）**字段中，输入您期望任务从运行到完成的分钟数。估算的持续时间用于计算期望的部署时间。

3. 在**标记**列表中，将标记附加至任务。可选择多个标记。要创建标记，请在列表的字段中输入标记名称。

3. 在**分配的组和用户**列表中，向用户或组分配任务。已分配的用户在部署期间运行任务。

3. 从**所有者**列表中，选择任务所有者。缺省所有者是创建任务的用户。在将任务分配给用户或组后会显示**所有者**列表。    

5. 单击**保存**。此时任务即会插入到部署计划中。

## 创建延迟任务
{: #tasks_delayed}

延迟类型的任务代表部署期间的里程碑或紧急事件。使用延迟任务，您可以确保重要的任务在预期时间开始。一般而言，延迟任务是其他重要任务的先决条件。

延迟任务在适合运行时即会启动，并在用户指定的时间完成。已启动的延迟类型任务在达到其计划运行时间之前，其状态为“进行中”，而达到运行时间时，其状态会更改为“已完成”。当延迟任务完成时，依赖于该任务的任务会开始运行。

要创建延迟任务，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，单击**创建任务**。如果您要在计划的特定位置插入任务，请在单击**创建任务**前，先选择某个任务。新任务即会插入到所选任务的上方。

1. 在“创建任务”窗口的**类型**列表中，选择**延迟**。

1. 在**名称**字段中，输入任务的名称。

3. 在**时间**字段中，输入或选择应该完成任务的时间。

3. 在**时区**列表中，针对在**时间**字段中输入的值，选择时区。    

5. 单击**保存**。此时任务即会插入到部署计划中。

## 创建标头任务
{: #tasks_header}

标头任务代表可以添加到部署计划的组织元素。如果您创建任务组，那么您可以使用标头任务识别组。标头任务可以像其他任何任务一样具有依赖关系。

<!-- When you import a deployment plan from IBM UrbanCode Release, segment tasks are bracketed by note-type Start Segment and End Segment tasks. Segment dependencies are represented by dependencies to End Segment tasks. -->

要创建标头任务，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，单击**创建任务**。如果您要在计划的特定位置插入任务，请在单击**创建任务**前，先选择某个任务。新任务即会插入到所选任务之前。

1. 在“创建任务”窗口的**类型**列表中，选择**标头**。

1. 在**名称**字段中，输入任务的名称。名称可以代表任务组名称。

3. 在**描述**字段中，输入或粘贴描述。您可以输入注释、提醒或其他指示信息。

5. 单击**保存**。此时任务即会插入到部署计划中。

## 创建 Delivery Pipeline 任务
{: #tasks_pipelineCD}

在 {{site.data.keyword.contdelivery_short}} 服务中，{{site.data.keyword.deliverypipeline}} 会自动执行 DevOps 工作流程。您可以使用管道任务来管理 {{site.data.keyword.deliverypipeline}} 实例。

要创建 Delivery Pipeline 任务，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，单击**创建任务**。如果您要在计划的特定位置插入任务，请在单击**创建任务**前，先选择某个任务。新任务即会插入到所选任务之前。

1. 在“创建任务”窗口的**类型**列表中，选择 **Continuous Delivery Pipeline**。

1. 在**名称**字段中，输入任务的名称。名称可以代表任务组名称。

3. 在**描述**字段中，输入或粘贴描述。您可以输入注释、提醒或其他指示信息。

3. 在**管道标识**字段中，输入或粘贴管道标识。

3. 在**阶段名称**字段中，输入或粘贴阶段名称。

5. 单击**保存**。此时任务即会插入到部署计划中。

## 管理任务组
{: #tasks_groups}

您可以将两个或多个任务组合到一个任务组中。当您创建组时，您会定义组的执行模式，即循序或并行。您可以在并行模式组中以任何顺序运行任务，只要没有依赖关系，就可以同时运行各任务。在顺序组中的任务以列表顺序执行，从第一个或最上面的任务开始。

您可以在其他组中嵌入组。您可以在顺序模式组中嵌入并行模式组，也可以在并行模式组中嵌入顺序模式组。但是，您无法在另一个循序组中嵌入循序模式组，或在另一个并行组中嵌入并行模式组。  

要创建任务组，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，选择两个或多个任务。

1. 根据您要创建的组类型，完成以下某个步骤：

  <ul>
  <li>要创建并行组，请单击**并行**图标 <img class="inline" src="../UCCR/images/para-icon.png"  alt="并行组图标">。如果您无法使用所选任务创建并行组，那么该图标会是禁用状态。例如，如果所选的全部任务都已经位于并行组中，那么您可能无法创建并行组。
</li>
  <li>要创建循序组，请单击**循序**图标 <img class="inline" src="../UCCR/images/seq-icon.png"  alt="循序组图标">。</li>
  </ul>

此时将形成组，且组选择栏会添加到部署计划中。如果您已选择不连续任务，那么任务会形成从最顶部所选任务开始的连续列表。

下图显示并行组。组选择栏可识别组的类型：并行 <img class="inline" src="../UCCR/images/para-select.png"  alt="并行组选择"> 或循序 <img class="inline" src="../UCCR/images/seq-select.png"  alt="循序组选择">。

![典型部署计划](../UCCR/images/group-select.png)

*图 2. 并行组*

要移动组，请单击**组选择栏**，或单击组中的任何位置并将其拖动到新位置。

要复制组，请选择组，单击**复制**图标 <img class="inline" src="../UCCR/images/copy-group.png"  alt="复制图标">，将光标置于您要插入所复制组的位置，然后单击**粘贴**图标 <img class="inline" src="../UCCR/images/paste-group.png"  alt="粘贴图标">。

要剪切组，请选择组并单击**剪切**图标 <img class="inline" src="../UCCR/images/cut-group.png"  alt="剪切图标">。

要对某个组取消分组，请选择该组并单击组选择栏上的**取消分组**图标 <img class="inline" src="../UCCR/images/ungroup-icon.png"  alt="取消分组图标">。

要删除某个组中的任务，请选择该组并单击**删除**图标 <img class="inline" src="../UCCR/images/trash-group.png"  alt="删除图标">。此时即会从部署计划中除去任务。

## 管理任务标记
{: #tasks_tags}

标记是可添加到任务的组织元素。您可以按标记对部署计划进行过滤。例如，在部署到生产环境期间，您可以禁用包含 `DEV_only` 标记的任务，该标记指示这些任务仅适用于开发环境。

要向任务添加标记，请遵循以下步骤：

1. 在“部署计划详细信息”页面上，选择任务或任务组并单击**管理标记** <img class="inline" src="../UCCR/images/task-tag.png"  alt="管理标记">。您可以选择多个任务和组。

1. 在“管理所选任务的标记”窗口的**常用标记**列表中，选择标记。您可以通过在列表的文本框中输入名称来创建标记。

1. 单击**保存**。

此时标记会显示在“部署计划详细信息”页面的任务行中。在下图中，“部署 WAR”任务具有两个标记：`Deployment` 和 `Critical`。

部署计划所使用的标记在“部署计划详细信息”页面的**版本**选项卡上显示。要将任务呈现为不适用于部署，请清除任务的标记。具有“不适用”状态的任务无法启动。  

![典型部署计划](../UCCR/images/task-tag-labels.png)

*图 3. 任务标记*

## 创建任务依赖关系
{: #tasks_dependencies}

您可以使某个任务成为其他任务的先决条件。如果某个任务是先决条件，那么在解决先决条件任务之前，从属任务无法启动，即使它们另外获得资格也是如此。

一个任务可以具有多个从属任务和多个先决条件任务。可定义一个任务与部署计划中任何其他任务的依赖关系。但是，您无法创建循环依赖关系。例如，如果一个任务依赖于另一个任务，那么您无法再使后者依赖于前者。

通过控制任务依赖关系，您可以确保事件以其期望的顺序发生。

要使某个任务成为其他任务的先决条件，请完成以下步骤：

1. 在“部署计划详细信息”页面上，选择任务或任务组并单击**管理先决条件** <img class="inline" src="../UCCR/images/task-depend.png"  alt="任务先决条件">。您可以选择多个任务和组。

1. 在“管理所选任务的先决条件”窗口的**所选任务的先决条件任务**列表中，选择先决条件任务。

1. 单击**保存**。

任务依赖关系显示在“部署计划详细信息”页面的“依赖关系”列中。上箭头表示任务先决条件；下箭头表示任务依赖关系。

在下图中，第一个任务没有任何先决条件，但有两个任务依赖它。第二个任务具有一个先决条件任务，但没有任务依赖它。

![典型部署计划](../UCCR/images/plan-w-depend.png)

*图 4. 任务依赖关系*

要复查或修改依赖关系，请选择任务并单击**管理先决条件** <img class="inline" src="../UCCR/images/task-depend.png"  alt="任务先决条件">。
