---

copyright:
  years: 2017, 2018
lastupdated: "2018-2-26"
---
<!-- Copyright info at top of file: REQUIRED
    The copyright info is YAML content that must occur at the top of the MD file, before attributes are listed.
    It must be surrounded by 3 dashes.
    The value "years" can contain just one year or a two years separated by a comma. (years: 2014, 2016)
    Indentation as per the previous template must be preserved.
-->

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 使用组合管道（试验性）
{: #deliverypipeline_create_composite}

使用 {{site.data.keyword.deliverypipeline}} 的组合管道功能，您可以管理相关软件应用程序的可重复持续集成和持续交付流程。
{:shortdesc}

**注**：此功能仅在美国南部区域可用。

您创建组合管道来管理工具链中的应用程序。如果工具链包含 {{site.data.keyword.deliverypipeline}} 部署的应用程序，那么在工具链中添加或除去 Delivery Pipeline 时，可以设置要更新的组合管道。您还可以将应用程序从外部源添加到组合管道。

## 创建组合管道
{: #compositepipeline_create_for_toolchain}

1. 从 {{site.data.keyword.Bluemix_notm}} 菜单栏上的菜单中，单击**服务**，然后单击 **DevOps**。

2. 从左侧导航中，单击**管道**。

3. 通过单击**了解更多**，然后单击**启用**，启动组合管道功能。组合管道会针对每个用户启用，因此只有选择试验性功能的组织成员才能看到您所创建的组合管道。

4. 单击**创建管道** > **组合管道**。

5. 输入组合管道的名称。您还可以修改管道描述。

6. 从**工具链**列表中，选择工具链。

    a. 要创建空的工具链和组合管道，请选择**新建**。

    b. 要为其中一个工具链创建组合管道，请选择其名称。

7. 如果您创建空工具链，请选择**添加缺省环境**。您使用这些缺省逻辑环境，通过组合管道来控制流程执行。

8. 要在将管道添加到工具链、从工具链中除去管道或修改工具链管道的阶段时更新组合管道，请选择**自动将此组合管道与所选工具链同步**。

  **注**：在更改工具链的管道之前，必须启用自动同步。只有启用了自动同步，组合管道中才会包含所做的更改。

9. 单击**创建**。

您所配置的阶段会自动映射到您组织的相应空间，且会针对组合管道创建部署计划。

如果您为包含 Delivery Pipeline 的工具链创建了组合管道，那么该工具链中所有管道的应用程序都会添加到组合管道。您在 Delivery Pipeline 中所配置的阶段会自动映射到您组织的相应空间，且会显示其状态。要查看应用程序中每个作业的状态，请展开应用程序。

还会针对组合管道创建部署计划。缺省情况下，某个空间中所有应用程序的作业会并行运行，但是您可以在计划中更改应用程序的部署顺序。

如果您为新工具链创建了组合管道，那么会为您创建部署计划以进行定制。

![展开每个应用程序以查看其管道中的每个作业](images/composite_view.png "展开每个应用程序")

## 修改部署计划
{: #compositepipeline_modify_dp}

缺省情况下，会针对组合管道创建部署计划。此部署计划会捕获工具链中任何 Delivery Pipeline 内的所有阶段信息。您可以查看和修改每个阶段的部署计划。

在您要修改部署计划的阶段中，单击菜单并单击**部署计划**。

![打开部署计划](images/open_deployment_plan.png "打开部署计划")

此时将显示环境的部署任务列表。

![包含三个不同管道的组合管道的缺省部署计划](images/composite_deploy_plan.png)

有关修改部署计划的更多信息，请参阅[定制组合管道的部署计划](/docs/services/ContinuousDelivery/pipeline_deployment_plan.html)。

## 修改单个管道
{: #compositepipeline_add_job}

您可以修改组合管道中的单个管道。

1. 展开应用程序。

2. 从阶段的菜单中，单击**配置**。

3. 在阶段中添加、修改或删除作业。有关详细指示信息，请参阅[向阶段添加作业](pipeline_build_deploy.html#deliverypipeline_add_job)。

## 运行组合管道中的作业
{: #compositepipeline_run_jobs}

展开应用程序以显示其作业后，您可以手动运行其在阶段中的所有作业。在应用程序的空间中，单击 **部署到 *stage*** 图标。

![在单个应用程序中运行某个阶段](images/composite_run_stage.png)

要运行空间中所有应用程序中的所有作业，请单击组合管道空间中的**部署到 *space*** 图标。

![在所有应用程序中运行某个阶段](images/composite_run_space.png)

作业根据组合蓝图的部署计划运行。

##添加交付管道部署的应用程序
{: #compositepipeline_add_apps}

只能通过将组合管道与工具链同步来添加 Delivery Pipeline 部署的应用程序。由于组合管道与单个工具链相关联，因此可以仅包含其 Delivery Pipeline 位于该工具链中的应用程序。

要将 Delivery Pipeline 部署的应用程序添加到组合管道，请执行以下步骤：

1. 打开组合管道。

2. 选择**自动将此组合管道与工具链同步**。

  **注**：在创建 Delivery Pipeline 之前，必须启用自动同步。只有启用了自动同步，组合管道中才会包含所做的更改。

3. 为应用程序创建 Delivery Pipeline。确保将 Delivery Pipeline 与组合管道分配给相同的工具链。

4. 配置 Delivery Pipeline 的阶段和作业。

应用程序将添加到组合管道，并且每个阶段的部署计划都包含用于运行您配置的作业的任务。


##在组合管道中更新 Delivery Pipeline
{: #compositepipeline_sync}

必须先在组合管道中启用自动同步，然后才能添加或更改作为其中一部分的管道。

1. 打开组合管道。

2. 选择**自动将此组合管道与工具链同步**。

## 查看日志
{: #compositepipeline_view_logs}

要查看某个作业的日志，请展开包含该作业的应用程序，然后单击该作业。

## 使用 {{site.data.keyword.Bluemix_notm}} DevOps Connect 与 IBM UrbanCode Deploy 集成
{: #compositepipeline_devops_connect}

{{site.data.keyword.Bluemix_notm}} DevOps Connect 协调内部部署 IBM&reg; UrbanCode&reg; Deploy 安装与 {{site.data.keyword.contdelivery_short}} 之间的通信。在您安装 DevOps Connect 后，可以创建集成，您可以使用这些集成来管理具有组合管道的 IBM UrbanCode Deploy 应用程序。

**先决条件**

   * 要注册 DevOps Connect，您必须具有 IBM 标识。

   * 请确保主机系统上有 [Java&trade; 运行时环境 V8 Update 121 或更新版本 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://java.com/en/download/){:new_window}，且系统 PATH 变量设置为其位置。

   * 您需要从 IBM UrbanCode Deploy 获得管理授权令牌。

要使用 DevOps Connect 来与 IBM UrbanCode Deploy 集成，请遵循以下步骤：

1. 安装 DevOps Connect 并使用它将您组织与 IBM UrbanCode Deploy 集成。

  1. 在组合管道中，单击**添加应用程序**。从**管理者**列表中，选择 **IBM UrbanCode Deploy**。

  1. 显示集成步骤。如果您看到应用程序列表，首先按**应用程序**单击信息图标 (![信息图标](/images/info.png))，然后单击**配置此组织的 IBM UrbanCode Deploy**。

  1. 在“配置 UrbanCode Deploy 集成”窗口中，单击**下载**以下载 DevOps Connect。将 JAR 文件放置在具有 IBM UrbanCode Deploy 访问权的计算机上。

  1. 从该窗口中，复制 DevOps Connect 安装脚本。该脚本包含启动 DevOps Connect 的命令，以及识别 {{site.data.keyword.contdelivery_short}} 服务所需的凭证。

  1. 在您放置 DevOps Connect 的计算机上，打开命令 shell，并将复制的脚本粘贴到其中。

  1. 运行该脚本。此时，DevOps Connect 将显示启动消息。

1. 注册 DevOps Connect。

  1.  在您放置 DevOps Connect 的计算机上，使用 Web 浏览器打开 DevOps Connect 仪表板。缺省 URL 为 https://localhost:8443。要更改 URL 并了解其他启动选项，请参阅 [DevOps Connect 文档 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window}。


1. 在“登录到 IBM”页面上，输入您的 IBM 标识和密码，然后单击**登录**。每次启动 DevOps Connect 时都进行登录。

1. 有了 DevOps Connect，使用 IBM UrbanCode Deploy for DevOps Connect 插件，可以创建组织和 IBM UrbanCode Deploy 之间的集成。

    1. 在“集成”页面上，单击**添加新的**。

    1. 在**名称**字段中，输入集成的名称。

    1. 从**集成类型**列表中，选择 **IBM UrbanCode Deploy for DevOps Connect**。

    1. 在**服务器 URI** 字段中，输入 IBM UrbanCode Deploy 服务器的公共 URL；例如，`https://my_UCD.example.com:8443`。

    1. 在**认证令牌**字段中，输入或粘贴 IBM UrbanCode Deploy 生成的认证令牌。

    1. 在**管理用户电子邮件**字段中，输入您的电子邮件地址。

    1. 要确认已成功集成，请单击**运行集成**。DevOps Connect 将连接至**服务器 URI** 字段中指定的 IBM UrbanCode Deploy 实例。DevOps Connect 由**认证令牌**字段中粘贴的令牌授权。

    1. 单击**保存**。

如果成功集成，那么您可以将 IBM UrbanCode Deploy 应用程序添加到组合管道。有关更多信息，请参阅[从 IBM UrbanCode Deploy 添加应用程序](/docs/services/ContinuousDelivery/pipeline_composites.html#compositepipeline_add_apps)。


## 从 IBM UrbanCode Deploy 添加应用程序
{: #compositepipeline_add_apps}

如果您是某组织的成员，而该组织使用 DevOps Connect 与 IBM UrbanCode Deploy 集成，那么您可以将 UrbanCode Deploy 中您有权访问的应用程序添加到组合管道中。有关安装指示信息，请参阅[使用 {{site.data.keyword.Bluemix_notm}} DevOps Connect 与 IBM UrbanCode Deploy 集成](/docs/services/ContinuousDelivery/pipeline_composites.html#compositepipeline_devops_connect)。

当您是连接到 IBM UrbanCode Deploy 的组织的成员时，您可以将 UrbanCode Deploy 应用程序添加到组合管道，选择要包含在部署计划中的应用程序流程，并定制应用程序的部署。

1. 从组合管道中，单击**添加应用程序**。

2. 从**管理者**列表中，选择 **IBM UrbanCode Deploy**。如果您最近将 {{site.data.keyword.contdelivery_short}} 与 IBM UrbanCode Deploy 进行了集成，那么您可能需要刷新浏览器才能看到服务器。

3. 选择要添加的应用程序并单击**继续**。此时将显示 IBM UrbanCode Deploy 应用程序可用的所有应用程序流程。用于运行所选流程的条目会添加到部署计划。

4. 选择要用于应用程序的应用程序流程。使用搜索和过滤选项来查找流程。

5. 单击**保存**。您所选的每个 IBM UrbanCode Deploy 应用程序都会显示为组合管道中的应用程序。

6. 将环境从 IBM UrbanCode Deploy 应用程序映射到组合管道的逻辑环境：

    1. 从逻辑环境名称附近的菜单中，选择**管理逻辑环境**。

    ![选择“管理逻辑环境”](images/composite_logical_env.png)

    2. 对于组合管道中的每个应用程序，选择您在 IBM UrbanCode Deploy 中所定义的环境。您所选择的应用程序流程仅会在该应用程序的环境中运行。

    3. 单击**保存**。

    4. 针对您使用的每个逻辑环境重复上述步骤。

##学习教程：组合管道
{: #composite_pipeline-tutorial}

查阅 [IBM&reg; Cloud Garage Method ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage){:new_window} 上的本教程：

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}。

  **注**：{{site.data.keyword.DRA_short}} 仅在美国南部区域可用。
