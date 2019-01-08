---

copyright:
  years: 2015, 2018
lastupdated: "2018-12-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:download: .download}   

# 配置工具集成
{: #integrations}

您可以在创建开放式工具链时配置支持开发、部署和操作任务的工具集成，也可以添加并配置工具集成，以定制现有工具链。  
{:shortdesc}

根据您是在 {{site.data.keyword.Bluemix_notm}} Public 还是 {{site.data.keyword.Bluemix_notm}} Dedicated 中使用工具链，工具链可添加和配置的工具集成有所不同。如果要在 {{site.data.keyword.Bluemix_notm}} Public 上使用工具链，那么哪些工具集成可用取决于工具链的区域以及该区域中工具集成的可用性。如果要在 {{site.data.keyword.Bluemix_notm}} Dedicated 上使用工具链，那么哪些工具集成可用将取决于 {{site.data.keyword.contdelivery_full}} 在您的特定环境中如何设置。

|工具集成|在 {{site.data.keyword.Bluemix_notm}} Public 中可用|在 {{site.data.keyword.Bluemix_notm}} Dedicated 中可用（具体取决于环境）|
|:----------|:------------------------------|:------------------|
|{{site.data.keyword.alertnotificationshort}}		|美国南部|否|
|Artifactory|美国南部、美国东部、德国、东京、英国|是|
|Availability Monitoring|美国南部|否|
|Bitbucket		|美国南部、美国东部、德国、东京、英国|否|
|Cloud Event Management|美国南部|否|
|{{site.data.keyword.deliverypipeline}} 		|美国南部、美国东部、德国、东京、英国|是|
|{{site.data.keyword.DRA_short}} 		|美国南部、德国和英国|否|
|Eclipse Orion {{site.data.keyword.webide}}|美国南部、美国东部、德国、东京、英国|是|
|{{site.data.keyword.gitrepos}}	|美国南部、美国东部、德国、东京、英国|否|
|GitHub		|美国南部、美国东部、德国、东京、英国|是|
|Dedicated {{site.data.keyword.ghe_short}} 和 Issues|否|是|
|GitLab|美国南部、美国东部、德国、东京、英国|否|
|Jenkins|美国南部、美国东部、德国、东京、英国|是|
|JIRA|美国南部、美国东部、德国、东京、英国|是|
|Nexus|美国南部、美国东部、德国、东京、英国|是|
|其他工具|美国南部、美国东部、德国、东京、英国|是|
|PagerDuty|美国南部、美国东部、德国、东京、英国|是|
|Rational Team Concert|美国南部、美国东部、德国、东京、英国|是|
|Sauce Labs|美国南部、美国东部、德国、东京、英国|否|
|Slack|美国南部、美国东部、德国、东京、英国|是|
|SonarQube|美国南部、美国东部、德国、东京、英国|是|
{: caption="表 1. 在 {{site.data.keyword.Bluemix_notm}} Public 和 Dedicated 中，工具链可使用的工具集成" caption-side="top"}

如果您想要在 {{site.data.keyword.Bluemix_notm}} Public 中开始使用源代码进行开发，请先配置 GitHub 工具集成或 {{site.data.keyword.gitrepos}} 工具集成，然后再配置 {{site.data.keyword.deliverypipeline}}。如果要在 {{site.data.keyword.Bluemix_notm}} Dedicated 上开始使用您的代码进行开发，请先配置 {{site.data.keyword.ghe_short}} 工具集成或 GitHub 工具集成，然后再配置 {{site.data.keyword.deliverypipeline}}。
{: tip}


## 配置 Alert Notification
{: #alertnotification}

{{site.data.keyword.alertnotificationfull}} 是基于混合云的解决方案，您可用于集中和简化通知策略。它使用其他基于云和内部部署的应用程序。使用安全的 RESTful API，可将警报转递给 {{site.data.keyword.alertnotificationshort}}。

配置 {{site.data.keyword.alertnotificationshort}} 以在 DevOps 过程中接收有关问题的通知。

### 先决条件

1. 如果您没有 {{site.data.keyword.alertnotificationshort}} 帐户，请注册帐户：

 a. 在 IBM Marketplace 中打开 [IBM {{site.data.keyword.alertnotificationshort}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/us-en/marketplace/alert-notification){: new_window} 页面。

 b. 购买预订或注册 90 天免费试用。

1. 在设置 {{site.data.keyword.alertnotificationshort}} 帐户后，打开[我的 IBM 仪表板 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://myibm.ibm.com/dashboard/){: new_window}。
1. 在 IBM {{site.data.keyword.alertnotificationshort}} 旁边，单击**启动**。
1. 单击**管理 API 密钥**并单击**创建 API 密钥**。
1. 在**创建 API 密钥**字段中，输入描述。
1. 单击**生成**。此时将显示新 API 密钥信息，其中包括名称和密码。您需要该信息用于工具集成配置，因此请保持“新建 API 密钥”窗口处于打开状态。鉴于安全目的，您稍后无法检索 API 密钥密码。

### 配置 Alert Notification

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **{{site.data.keyword.alertnotificationshort}}**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **{{site.data.keyword.alertnotificationshort}}**。

1. 针对您要使用的 {{site.data.keyword.alertnotificationshort}} API，输入 URL。您可以在 {{site.data.keyword.alertnotificationshort}} 服务的“管理 API 密钥”页面上找到 URL；例如 `https://ibmnotifybm.mybluemix.net/api/alerts/v1`。
1. 针对 {{site.data.keyword.alertnotificationshort}}，输入 API 密钥的名称。您可以在“新建 API 密钥”窗口中找到 API 密钥名称。
1. 输入 {{site.data.keyword.alertnotificationshort}} 针对 API 密钥生成的密码。您可以在“新建 API 密钥”窗口中找到 API 密钥密码。
1. 单击**创建集成**。
1. 从您的工具链，单击 **{{site.data.keyword.alertnotificationshort}}**。

### 了解有关 Alert Notification 的更多信息

要了解有关 {{site.data.keyword.alertnotificationshort}} 的更多信息，请参阅 IBM Cloud Garage Method 上的 [IBM {{site.data.keyword.alertnotificationshort}} 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/manage/tool_alert_notification/){: new_window} 或学习以下教程：

  * [将工具集成添加到工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/add-a-tool-integration-to-a-toolchain){:new_window}

  * [使用 {{site.data.keyword.Bluemix_notm}} Availability Monitoring 和 Alert Notification 来管理 {{site.data.keyword.Bluemix_notm}} 应用程序 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## 配置 Artifactory
{: #artifactory}

配置 Artifactory 存储库管理器，以在 Artifactory 存储库中存储构建工件：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Artifactory**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Artifactory**。

1. 输入在您单击 Artifactory 卡时想要打开的 Artifactory 存储库的 URL。
1. 选择您要连接到的存储库类型。
1. 如果您使用 Artifactory npm 注册表，请遵循以下步骤：

 a. 输入与注册表相关联的电子邮件地址。

 b. 输入与注册表相关联的认证令牌。

 c. 输入 Artifactory 发布存储库的 URL，这是您在 Artifactory 服务器上的专用注册表。

 d. 输入用于组合多个公共和专用 npm 注册表的镜像或公共注册表的 URL。例如，此 URL 可能是可访问专用注册表和 npm 全局 注册表高速缓存的 Artifactory 服务器上虚拟注册表的 URL。

1. 如果您使用 Artifactory Maven 存储库，请遵循以下步骤：

 a. 输入与存储库相关联的用户标识。

 b. 输入与存储库相关联的密码。

 c. 输入 Artifactory 发布存储库的 URL，这是您在 Artifactory 服务器上的专用发布存储库。

 d. 输入 Artifactory 快照存储库的 URL，这是您在 Artifactory 服务器上的专用快照存储库。

 e. 输入用于组合多个公共和专用 Maven 存储库的镜像或公共存储库的 URL。例如，此 URL 可能是可访问专用存储库和 Maven 中央存储库高速缓存的 Artifactory 服务器上虚拟存储库的 URL。

1. 单击**创建集成**。
1. 单击您要使用的 Artifactory 存储库的卡。这将打开 Artifactory Web 站点，您可在其中查看存储库的内容。
1. 可选：如果您在 {{site.data.keyword.Bluemix_notm}} Public 上使用工具链，并且想要使用 Artifactory 与 npm 来构建应用程序，请配置管道以添加 npm 构建作业。有关配置构建作业的指示信息，请参阅[在管道中配置 Artifactory npm 构建作业](#config_artifactory_npm)一节。
1. 可选：如果您在 {{site.data.keyword.Bluemix_notm}} Public 上使用工具链，并且想要使用 Artifactory 与 Maven 来构建应用程序，请配置管道以添加 Maven 构建作业。有关配置构建作业的指示信息，请参阅[在管道中配置 Artifactory Maven 构建作业](#config_artifactory_maven)一节。

### 在管道中配置 Artifactory npm 构建作业
{: #config_artifactory_npm}

在管道中配置 npm 构建作业之前，您必须具有可使用构建 SCM 存储库作为输入的工作管道。还必须为工具链配置 Artifactory。有关配置 Artifactory 的指示信息，请参阅 [Artifactory](#artifactory) 一节。

配置 {{site.data.keyword.deliverypipeline}} 以添加 npm 构建作业：

1. 创建阶段并设置适当 SCM 存储库的输入。
1. 在阶段上，添加构建作业。
1. 配置构建作业：![npm 构建作业](images/artifactory_npm_job.png)

  a. 对于构建器类型，请选择 **NPM 构建**。

  b. 如果已配置 Artifactory 工具集成的多个实例，请输入要为其配置 npm 构建作业的 Artifactory 工具集成的名称。

  c. 对于工具集成类型，请选择 **Artifactory**。

  d. 对于构建命令，请输入用于构建 npm 模块或将其发布到注册表的命令。此示例显示构建模块或进行发布的命令。
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  您可以在 Artifactory 工具集成的配置设置中，查找用于连接到注册表的 URL 和用户凭证。
  {: tip}

  e. 如果您的构建作业发布到 Artifactory 注册表且您节点模块版本的格式为 `x.y.z-SNAPSHOT.w`，请选中**增量快照模块版本**复选框。构建作业会在作业发布到 Artifactory 注册表之前，自动更新模块版本。作业会从 npm 注册表和本地 `package.json` 文件中选择最高的模块版本，并使用 semver 递增模块版本。 构建作业不会将更改交付到 SCM 存储库。

1. 单击**保存**。管道无论何时运行，此构建作业都会使用 Artifactory 工具集成中的配置信息来连接到您的 npm 注册表。

### 在管道中配置 Artifactory Maven 构建作业
{: #config_artifactory_maven}

在管道中配置 Maven 构建作业之前，您需要可使用构建 SCM 存储库作为输入的工作管道，并且您必须为工具链配置 Artifactory。有关配置 Artifactory 的指示信息，请参阅 [Artifactory](#artifactory) 一节。

配置 {{site.data.keyword.deliverypipeline}} 以添加 Maven 构建作业：

1. 创建阶段并设置适当 SCM 存储库的输入。
1. 在阶段上，添加构建作业。
1. 配置构建作业：![Maven 构建作业](images/artifactory_maven_job.png)

  a. 对于构建器类型，请选择 **Maven 构建**。

  b. 如果已配置 Artifactory 工具集成的多个实例，请输入要为其配置 Maven 构建作业的 Artifactory 工具集成的名称。

  c. 对于工具集成类型，请选择 **Artifactory**。

  d. 对于构建命令，请输入用于构建 Maven 模块或将其发布到快照注册表的命令。此示例显示构建模块或将其发布到快照注册表的命令。
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  您可以在 Artifactory 工具集成的配置设置中，查找用于连接到注册表的 URL 和用户凭证。
  {: tip}

1. 单击**保存**。管道无论何时运行，此构建作业都会使用 Artifactory 工具集成中的配置信息来连接到您的 Maven 存储库。

### 了解有关 Artifactory 的更多信息

要了解有关 Artifactory 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Artifactory 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/deliver/tool_artifactory/){: new_window}。


## 添加 Availability Monitoring
{: #availabilitymonitoring}

{{site.data.keyword.prf_hublong}} 可在问题影响到用户之前，隔离问题、识别模式并改进性能。您可以从世界各地测试您的应用程序、与 Delivery Pipeline 集成，以及深入了解如何持续优化代码。

此工具集成是预配置的，不需要任何配置参数。无法对此工具集成进行重新配置。
{: tip}

要在构建应用程序时对应用程序的运行状况进行测试、监视和改进，请添加 {{site.data.keyword.prf_hubshort}} 工具集成：

1. 在 DevOps 仪表板的“工具链”页面上，单击要将 {{site.data.keyword.prf_hubshort}} 添加到的工具链。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **{{site.data.keyword.prf_hubshort}}**。

1. 单击**创建集成**。
1. 单击 **{{site.data.keyword.prf_hubshort}}** 以打开 {{site.data.keyword.prf_hubshort}} 仪表板，选择应用程序并为应用程序配置监视。

### 了解有关 Availability Monitoring 的更多信息

要了解有关 {{site.data.keyword.prf_hubshort}} 的更多信息，请参阅 IBM Cloud Garage Method 上的 [{{site.data.keyword.prf_hublong}} 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/manage/tool_bluemix_availability_monitoring/){: new_window} 或学习以下教程：

  * [使用 {{site.data.keyword.Bluemix_notm}} Availability Monitoring 和 Alert Notification 来管理 {{site.data.keyword.Bluemix_notm}} 应用程序 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## 配置 Bitbucket
{: #bitbucket}

将源代码存储在 bitbucket.org 上新的或现有存储库中，并通过 Wiki、问题跟踪和拉取请求来参与社交编码。

配置 Bitbucket 以与团队协作编写代码：

1. 在 DevOps 仪表板上，单击**工具链**。单击要将 Bitbucket 添加到的工具链。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Bitbucket**。

   如果要在 {{site.data.keyword.Bluemix_notm}} Public 上配置此工具集成，但尚未授权 {{site.data.keyword.Bluemix_notm}} 访问 Bitbucket，请单击**授权**以转至 Bitbucket Web 站点。如果您没有活动的 Bitbucket 会话，那么系统会提示您登录。单击**授予访问权**以允许 {{site.data.keyword.Bluemix_notm}} 工具链访问 Bitbucket 帐户的以下部分：
   
   * **读取帐户信息**。获取基本用户信息以填充用户界面。
   
   * **读取和修改存储库的问题**。允许 {{site.data.keyword.contdelivery_short}} 更新问题以指示管道何时部署连接到这些问题的落实。 
   
   * **读取团队项目设置和读取团队项目中包含的存储库**。允许 {{site.data.keyword.contdelivery_short}} 与团队拥有的存储库相集成。
   
   * **读取和修改存储库及其拉取请求**。允许 {{site.data.keyword.contdelivery_short}} 在用户请求代码时将样本代码推送到存储库。
   
   * **管理存储库**。允许 {{site.data.keyword.contdelivery_short}} 在用户请求时创建新存储库。
   
   * **读取团队成员资格信息**。允许 {{site.data.keyword.contdelivery_short}} 在创建新存储库时显示的**所有者**菜单中显示团队列表。
   
   * **读取和修改存储库的 Webhook**。允许管道在将落实推送到存储库时触发构建。
   {: tip}
   
   如果您有活动的 Bitbucket 会话，但最近未输入过密码，那么系统可能会提示您输入 Bitbucket 密码以进行确认。

1. 单击要使用的 Bitbucket 服务器。
1. 如果您有要使用的 Bitbucket 存储库，请输入该存储库的 URL。对于存储库类型，请单击**现有**。
1. 如果您想要使用新的 Bitbucket 存储库，请输入存储库的名称，输入您要克隆或派生的存储库的 URL，然后选择存储库类型：

 a. 要创建空的存储库，请单击**新建**。

 b. 要创建存储库的副本，请单击**克隆**。

 c. 要派生存储库以便您可以通过拉出请求来提供更改，请单击**派生**。

1. 要在服务器上创建专用存储库，请选中**使此存储库成为专用**复选框。
1. 要使用 Bitbucket Issues 进行问题跟踪，请选中**启用 Bitbucket Issues** 复选框。
1. 要通过在落实上创建标记和注释以及在落实所引用的问题上创建标签和注释来跟踪代码更改的部署，请选择**跟踪代码更改的部署**复选框。有关更多信息，请参阅[使用工具链跟踪代码部署位置 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}。
1. 单击**创建集成**。
1. 在工具链中，单击要使用的 Bitbucket 存储库的卡。这将打开 Bitbucket Web 站点，您可在其中查看存储库的内容。
1. 如果您已启用 Bitbucket Issues，请单击 **Bitbucket Issues**，以将其打开。您可以对整个工具链使用此 Bitbucket Issues 实例，即使工具链包含多个 Bitbucket 存储库也不例外。    

如果您对要链接到的存储库没有所有者或支配者特权，那么您的集成将受到限制，因为您无法使用 Webhook。将提交推送到存储库时，需要 Webhook 才能自动运行管道。没有 Webhook，您必须手动启动管道。
{: tip}

### 了解有关 Bitbucket 的更多信息

要了解有关 Bitbucket 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Bitbucket 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_bitbucket/){: new_window}。


## 添加 Cloud Event Management
{: #cloudeventmanagement}

{{site.data.keyword.evtmgt_full}} 提供服务、应用程序和基础架构所发生问题的统一视图。您可以设置实时事件管理，以更高效地解决问题。

此工具集成是预配置的，不需要任何配置参数。无法对其重新配置。
{: tip}

要帮助 DevOps 团队实现可靠的可操作运行状况、服务质量和持续改进目标，请向工具链添加 Cloud Event Management：

1. 在 DevOps 仪表板上，单击**工具链**。单击要将 Cloud Event Management 添加到的工具链。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Cloud Event Management**。

1. 单击**创建集成**。
1. 从您的工具链，单击以下任何工具卡：

 * **Cloud Event Management** 以开始使用 Cloud Event Management。

 * **{{site.data.keyword.alertnotificationshort}}** 以创建策略，确定用户何时收到事件通知。

 * **操作手册自动化**以在 Cloud Event Management 中管理操作手册的目录。

### 了解有关 Cloud Event Management 的更多信息

要了解有关 Cloud Event Management 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Cloud Event Management 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/manage/tool_cloud_event_mgt/){: new_window}。


## 配置 Delivery Pipeline
{: #deliverypipeline}

{{site.data.keyword.deliverypipeline}} 可自动完成项目的持续部署，按顺序执行检索输入和运行作业的每个阶段（如构建、测试和部署）。

配置 {{site.data.keyword.deliverypipeline}} 以自动持续构建、测试和部署应用程序：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **{{site.data.keyword.deliverypipeline}}**。根据您所使用的模板，可能会有不同的字段可用。请复查缺省字段值，如果必要，更改那些设置。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **{{site.data.keyword.deliverypipeline}}**。

1. 指定新管道的名称。
1. 如果您计划使用管道来部署用户界面，请选中**在“查看应用程序”菜单中显示应用程序**复选框。管道所创建的所有应用程序都会显示在工具链“概述”页面上的**查看应用程序**列表中。
1. 单击**创建集成**，以向工具链添加 {{site.data.keyword.deliverypipeline}}。
1. 单击 **{{site.data.keyword.deliverypipeline}}** 以查看管道并对其进行配置。要了解配置管道的基础知识，请参阅[构建和部署管道](/docs/services/ContinuousDelivery/pipeline_build_deploy.html){: new_window}。

  如果要在向 GitHub、{{site.data.keyword.ghe_short}} 或 Git 存储库推送提交时自动运行管道，请执行以下步骤：

   a. 为工具链配置 GitHub、{{site.data.keyword.ghe_short}} 或 {{site.data.keyword.gitrepos}}，然后再为管道定义阶段。管道阶段需要存储库的 Git URL。每一个管道阶段仅可以参考与工具链相关联的其中一个 GitHub、{{site.data.keyword.ghe_short}} 或 Git 存储库。有关配置 GitHub 的指示信息，请参阅 [GitHub](#github) 一节。有关配置 Dedicated {{site.data.keyword.ghe_short}} 的指示信息，请参阅 [{{site.data.keyword.ghe_long}} 入门](/docs/services/ghededicated/index.html){: new_window}。有关配置 {{site.data.keyword.gitrepos}} 的指示信息，请参阅 [{{site.data.keyword.gitrepos}}](#gitbluemix) 一节。

   b. 使用 Webhook。没有 Webhook，您只能手动运行管道。要在链接至 GitHub 或{{site.data.keyword.ghe_short}} 存储库时使用 Webhook，需要管理员特权。要链接到 {{site.data.keyword.gitrepos}} 存储库，您需要支配者或所有者特权。

1. 可选：如果您在 {{site.data.keyword.Bluemix_notm}} Public 中使用工具链，并且想要 Sauce Labs 对您的应用程序运行测试，请配置 {{site.data.keyword.deliverypipeline}} 以添加 Sauce Labs 测试作业。有关配置测试作业的指示信息，请参阅[在管道中配置 Sauce Labs 测试作业](#config_saucelabs)一节。

### 在管道中配置 Sauce Labs 测试作业
{: #config_saucelabs}

在管道中配置 Sauce Labs 测试作业之前，您需要具有构建和部署应用程序阶段的工作管道。还必须为工具链配置 Sauce Labs。有关配置 Sauce Labs 的指示信息，请参阅 [Sauce Labs](#saucelabs) 一节。

配置 {{site.data.keyword.deliverypipeline}} 以添加 Sauce Labs 测试作业：

1. 如果您没有部署应用程序测试版本的阶段，请创建一个。
1. 在该阶段上，在部署作业之后添加测试作业。通过将这些作业置于相同的阶段中，它们可以访问相同的环境属性集。
   
  ![测试作业](images/toolchain_test_job.png)

1. 配置阶段。在**环境属性**选项卡上，创建 CF_APP_NAME 属性。

  Sauce Labs 用户名和访问密钥在测试作业脚本中作为 SAUCE_USERNAME 和 SAUCE_ACCESS_KEY 环境变量提供。编写测试时，必须使用这两个环境变量向 Sauce Labs 进行认证。
  {: tip}

1. 配置部署作业。在**部署脚本**字段中，包括以下命令：`export CF_APP_NAME="$CF_APP"`。该命令会将应用程序名称导出为环境属性。
1. 配置测试作业。 

  **服务实例**、**目标**、**组织**和**空间**字段中会填充您使用的 Sauce Labs 用户名、区域、组织和空间。
  {: tip}

  a. 对于测试器类型，请选择 **Sauce Labs**。

  b. 对于服务实例，请选择您为工具链配置 Sauce Labs 时所使用的 Sauce Labs 用户名。

   要查看您为工具链配置 Sauce Labs 时所使用的用户名和访问密钥，请单击**配置**。
   {: tip}

  c. 在**测试执行命令**字段中，输入安装测试所需依赖项的命令，然后运行测试。例如，对于 Node.js 应用程序，您可能会输入以下命令：
     ```
     npm install
     node_modules/grunt-cli/bin/grunt test:sauce:parallel
     ```

    d. 如果要在测试作业日志中查看测试报告，请选中**启用测试报告**复选框，然后将“测试结果文件模式”设置为 `test/*.xml`。

1. 单击**保存**。管道无论何时运行，Sauce Labs 测试都会运行。

### 了解有关 Delivery Pipeline 的更多信息

要了解有关 {{site.data.keyword.deliverypipeline}} 的更多信息，请参阅 IBM Cloud Garage Method 上的[使用管道](/docs/services/ContinuousDelivery/pipeline_working.html){: new_window}和 [Delivery Pipeline 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/deliver/tool_delivery_pipeline/){: new_window}，或学习以下教程：

  * [创建管道 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/create-a-pipeline){:new_window}

  * [使用“开发 Cloud Foundry 应用程序”工具链来创建和使用第一个工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## 添加 DevOps Insights
{: #dra}

{{site.data.keyword.DRA_full}} 会从单元测试、功能测试和代码覆盖工具收集和分析结果，以确定您的代码是否符合部署过程中指定检测点的预定义条件。如果您的代码不符合条件或超出条件，那么会停止部署以防产生风险。您可以使用 {{site.data.keyword.DRA_short}} 作为持续交付环境的安全网，或用于实施和提高质量标准。

 此工具集成仅在 {{site.data.keyword.Bluemix_notm}} Public 上可用。它是预配置的，不需要任何配置参数。无法对此工具集成进行重新配置。
 {: tip}

添加 {{site.data.keyword.DRA_short}} 来监视部署以便在部署发布之前发现风险，从而保持和提高 {{site.data.keyword.Bluemix_notm}} 中代码的质量。

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **{{site.data.keyword.DRA_short}}**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **{{site.data.keyword.DRA_short}}**。

1. 单击**创建集成**。
1. 单击 **{{site.data.keyword.DRA_short}}**，然后完成入门步骤：创建条件、将条件连接到管道并运行管道。

### 了解有关 DevOps Insights 的更多信息

要了解有关 {{site.data.keyword.DRA_short}} 的更多信息，请参阅 IBM Cloud Garage Method 上的 [{{site.data.keyword.DRA_short}} 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/learn/tool_devops_insights/){: new_window} 或学习以下教程：

  * [使用“开发和测试 Cloud Foundry 应用程序”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [通过使用“具有 GitHub 和 Jenkins 的 Deployment Risk Analytics”工具链来确保部署质量 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}


## 添加 Eclipse Orion Web IDE
{: #webide}

Eclipse Orion {{site.data.keyword.webide}} 是基于 Web 的集成环境，您可以在其中创建、编辑、运行、调试和完成源代码控制任务。您可以无缝地完成从编辑到运行到提交再到部署的移动。

 此工具集成是预配置的。它不需要任何配置参数，您无法对其重新配置。
 {: tip}

要完成源代码控制任务，请添加 Eclipse Orion {{site.data.keyword.webide}} 工具集成：

1. 如果要在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Eclipse Orion {{site.data.keyword.webide}}**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Eclipse Orion {{site.data.keyword.webide}}**。

1. 单击**创建集成**。
1. 单击 **Eclipse Orion {{site.data.keyword.webide}}**。此时，您的工作空间会预填充 GitHub 或 {{site.data.keyword.ghe_short}} 存储库。与您当前工具链相关联的存储库会突出显示。

### 了解有关 Eclipse Orion Web IDE 的更多信息

要了解有关 Eclipse Orion {{site.data.keyword.webide}} 的更多信息，请参阅[使用 Eclipse Orion {{site.data.keyword.webide}} 编辑代码](/docs/services/ContinuousDelivery/web_ide.html){: new_window}。还可以阅读 IBM Cloud Garage Method 上的 [Eclipse Orion {{site.data.keyword.webide}} 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_eclipse_orion_web_ide/){: new_window}。根据这些教程尝试使用 Eclipse Orion {{site.data.keyword.webide}}：

  * [使用“开发 Cloud Foundry 应用程序”工具链来创建和使用第一个工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}


## 配置 Git Repos and Issue Tracking
{: #gitbluemix}

{{site.data.keyword.gitrepos}} 工具集成基于 GitLab Community Edition，其为 Git 存储库基于 Web 的托管服务。您可以同时具有存储库的本地和远程副本。要了解更多信息，请参阅 [{{site.data.keyword.gitrepos}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://git.ng.bluemix.net/help){:new_window}。

如果您在创建工具链时配置 {{site.data.keyword.gitrepos}}，请遵循以下步骤：    

1. 在“可配置的集成”部分中，单击 **Git Repos and Issue Tracking**。
1. 复查 Git 存储库的缺省目标位置。那些存储库是从样本存储库克隆而来的。如果需要，请更改目标存储库的名称。


如果您有工具链，并且希望将工具链中的 Git 存储库迁移到 {{site.data.keyword.gitrepos}}，请执行以下步骤：

这些指示信息适用于已包含要迁移到 {{site.data.keyword.gitrepos}} 的 Git 存储库的工具链。有关将不同类型的 Git 存储库添加到工具链的信息，请参阅[配置 GitHub](#github)、[在 {{site.data.keyword.Bluemix_notm}}Dedicated](#configghe) 中配置 GitHub Enterprise 和 Issues 以及[配置 GitHub](#gitlab) 部分。
{: tip}

1. 在 DevOps 仪表板的“工具链”页面上，单击工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。
1. 单击**添加工具**。
1. 在“工具集成”部分中，单击 **Git Repos and Issue Tracking**。
1. 要创建 Git 存储库的副本，对于存储库类型，请单击**克隆**。输入新存储库名称和源存储库的 URL。
1. 如果您想要使用 Issues 进行问题跟踪，请选中**启用 Issues** 复选框。
1. 如果您要通过在提交上创建标记和注释，在提交所参考的问题上创建标签和注释，跟踪代码更改的部署，请选择**跟踪代码更改的部署**复选框。有关更多信息，请参阅[使用工具链跟踪代码部署位置 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}。
1. 单击**创建集成**。

克隆 Git 存储库后，可以将其从工具链中除去。
{: tip}

如果您具有工具链且要向其添加 {{site.data.keyword.gitrepos}}，请遵循以下步骤：    

1. 在 DevOps 仪表板的“工具链”页面上，单击工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。
1. 单击**添加工具**。
1. 在“工具集成”部分中，单击 **Git Repos and Issue Tracking**。
1. 选择存储库类型：     

  a. 要创建空的存储库，对于存储库类型，请单击**新建**并输入存储库名称。    
  b. 要派生 Git 存储库以便您可以通过合并请求来提供更改，对于存储库类型，请单击**派生**。输入源存储库的 URL。    
  c. 要创建 Git 存储库的副本，对于存储库类型，请单击**克隆**。输入新存储库名称和源存储库的 URL。     
  d. 如果您有 GitHub 存储库并且要使用该存储库，那么对于存储库类型，请单击**现有**。输入 URL。    

1. 如果您想要使用 Issues 进行问题跟踪，请选中**启用 Issues** 复选框。
1. 如果您要通过在提交上创建标记和注释，在提交所参考的问题上创建标签和注释，跟踪代码更改的部署，请选择**跟踪代码更改的部署**复选框。有关更多信息，请参阅[使用工具链跟踪代码部署位置 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}。
1. 单击**创建集成**。
1. 单击您要使用的 Git 存储库的卡。此时将打开项目概述页面。    

如果您对要链接到的存储库没有支配者或所有者特权，那么您的集成将受到限制，因为您无法使用 Webhook。将提交推送到存储库时，需要 Webhook 才能自动运行管道。没有 Webhook，您必须手动启动管道。
{: tip}

### 了解有关 Git Repos and Issue Tracking 的更多信息

要了解有关 {{site.data.keyword.gitrepos}} 的更多信息，请参阅 IBM Cloud Garage Method 上的 [{{site.data.keyword.gitrepos}}：IBM 托管的社交编码文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_git_repos_and_issue_tracking/){: new_window} 或学习以下教程：

  * [使用“开发 Cloud Foundry 应用程序”工具链来创建和使用第一个工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## 配置 GitHub
{: #github}

GitHub 是 Git 存储库基于 Web 的托管服务。您可以同时具有存储库的本地和远程副本，这使协作变得更加轻松。

{{site.data.keyword.ghe_short}} 是 Git 存储库基于 Web 的内部部署托管服务。

GitHub Issues 是一种跟踪工具，可将您的全部工作和计划保留在一个地方。它与您的开发存储库相集成，以便您可将关注点放在重要的任务上。

您可以将 GitHub 配置为工具链中的工具集成，以便您可以管理 GitHub.com 上或您公司 {{site.data.keyword.ghe_short}} 实例中新存储库或现有存储库中的源代码。通过 Wiki、问题跟踪和拉取请求，可参与社交编码。

如果您在创建工具链时配置此工具集成，请遵循以下步骤：

1. 如果要将源代码存储在 GitHub 存储库中，请在“可配置的集成”部分中，单击 **GitHub**。如果要在 {{site.data.keyword.Bluemix_notm}} Public 上配置此工具集成，但尚未授权 {{site.data.keyword.Bluemix_notm}} 访问 GitHub，请单击**授权**以转至 GitHub Web 站点。如果您没有活动的 GitHub 会话，那么系统会提示您登录。单击**授权应用程序**，以允许 {{site.data.keyword.Bluemix_notm}} 访问 GitHub 帐户。如果您有活动的 GitHub 会话，但最近未输入过密码，那么系统可能会提示您输入 GitHub 密码以进行确认。
1. 如果要使用您自己的 {{site.data.keyword.ghe_short}} 服务器上的存储库，请在“可配置的集成”部分中，单击**添加定制服务器**。

 网络必须能够从 {{site.data.keyword.Bluemix_notm}} Dedicated 环境访问目标 Git 服务器。如果您的 GitHub 服务器在公用因特网上不可用，或者主机名在公共域名服务器 (DNS) 上无法解析，请[开具支持凭单](/docs/services/ContinuousDelivery/cd_support.html#support-ticket){: new_window}。您可以使用支持凭单来提交请求以打开网络路由或更新 DNS 设置。
 {: important}

 输入定制 GitHub 服务器的标题，并指定该服务器的根 URL。输入您的个人访问令牌，然后单击**保存定制集成**。

  如果您没有个人访问令牌，可以进行创建：

     a. 在任何 GitHub 页面上，单击“概要文件”图标，然后单击**设置**。

     b. 在侧边栏上，单击**个人访问令牌**。

     c. 单击**生成新令牌**。

     d. 添加令牌的描述。

     e. 选中**存储库**和**用户**复选框，以定义个人令牌的访问权。

     f. 单击**生成令牌**。

     g. 将令牌复制到安全的位置或密码管理应用程序。出于安全原因，离开此页面后，您将无法再看到该令牌。

1. 复查 GitHub 存储库的缺省目标存储库位置。那些存储库是从样本存储库克隆而来的。如果需要，请更改目标存储库的名称。![缺省目标存储库位置](images/toolchain_github_config.png)


如果您有工具链且要向其添加此工具集成，请执行以下步骤：

1. 在 DevOps 仪表板的“工具链”页面上，单击工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。
1. 单击**添加工具**。
1. 在“工具集成”部分中，单击 **GitHub**。
1. 单击要使用的 GitHub 服务器。
1. 如果您有 GitHub 或 {{site.data.keyword.ghe_short}} 存储库并且想要使用该存储库，那么对于存储库类型，请单击**现有**并输入 URL。
1. 如果要使用新的 GitHub 或 {{site.data.keyword.ghe_short}} 存储库，请输入存储库的名称，输入您要克隆或派生的存储库的 URL，然后选择存储库类型：

 a. 要创建空的存储库，请单击**新建**。

 b. 要创建 GitHub 或 {{site.data.keyword.ghe_short}} 存储库的副本，请单击**克隆**。

 c. 要派生 GitHub 或 {{site.data.keyword.ghe_short}} 存储库以便您可以通过拉出请求来提供更改，请单击**派生**。

1. 如果您是具有升级帐户的 GitHub.com 用户，或者选择了 {{site.data.keyword.ghe_short}} 服务器，并且希望在该服务器上创建新的专用存储库，请选中**使此存储库成为专用**复选框。
1. 如果您想要使用 GitHub Issues 进行问题跟踪，请选中**启用 GitHub Issues** 复选框。
1. 如果您要通过在提交上创建标记和注释，在提交所参考的问题上创建标签和注释，跟踪代码更改的部署，请选择**跟踪代码更改的部署**复选框。有关更多信息，请参阅[使用工具链跟踪代码部署位置 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}。
1. 单击**创建集成**。
1. 单击要使用的 GitHub 或 {{site.data.keyword.ghe_short}} 存储库的卡。根据您选择的存储库，将打开 GitHub Web 站点或您公司的 {{site.data.keyword.ghe_short}} 存储库，您可在其中查看存储库的内容。

  您可以在 Eclipse Orion {{site.data.keyword.webide}} 中使用集成的源代码管理工具，以编辑 GitHub 存储库，并从您的工作空间部署应用程序。
  {: tip}

1. 如果您已启用 GitHub Issues，请单击 **GitHub Issues**，以将其打开。您可以对整个工具链使用此 GitHub Issues 的实例，即使工具链包含多个 GitHub 或 {{site.data.keyword.ghe_short}} 存储库也是如此。    

如果您对要链接到的存储库没有管理员特权，那么您的集成将受到限制，因为您无法使用 Webhook。将提交推送到存储库时，需要 Webhook 才能自动运行管道。没有 Webhook，您必须手动启动管道。
{: tip}

### 了解有关 GitHub 的更多信息

要了解有关 GitHub 的更多信息，请参阅 IBM Cloud Garage Method 上的 [GitHub 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_github/){: new_window} 和 [GitHub Issues 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window}，或者学习以下教程：

 * [使用“开发和测试 Cloud Foundry 应用程序”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

  * [通过使用“具有 GitHub 和 Jenkins 的 Deployment Risk Analytics”工具链来确保部署质量 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

  * [创建定制工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/create-a-custom-toolchain){:new_window}


## 在 {{site.data.keyword.Bluemix_notm}} Dedicated 上配置 GitHub Enterprise 和 Issues
{: #configghe}

 以下指示信息仅适用于 {{site.data.keyword.Bluemix_notm}} Dedicated for {{site.data.keyword.ghe_short}}。如果您使用自己的 {{site.data.keyword.ghe_short}} 受管版本，那么根据您的内部过程，有些步骤可能有所不同。
 {: important}

{{site.data.keyword.ghe_long}} 是 Git 存储库基于 Web 的内部部署托管服务。Dedicated {{site.data.keyword.ghe_short}} 仅适用于 {{site.data.keyword.Bluemix_notm}} Dedicated 客户。GitHub Issues 是一种跟踪工具，可将您的工作和计划保留在一个地方。它与您的开发存储库相集成，以便您可将关注点放在重要的任务上。有关 Dedicated {{site.data.keyword.ghe_short}} 和 GitHub Issues 的更多信息，请参阅 IBM Cloud Garage Method 上的 [{{site.data.keyword.ghe_long}} 入门](/docs/services/ghededicated/index.html){: new_window}和 [GitHub Issues 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window}。

您可以将 {{site.data.keyword.ghe_short}} 配置为工具链中的工具集成，以便您可以管理公司 [{{site.data.keyword.Bluemix_notm}} Dedicated](/docs/dedicated/index.html#dedicated){: new_window} 实例中的源代码。

1. 如果您在创建工具链时配置此工具集成，请遵循以下步骤：

 a. 首次登录到 Dedicated {{site.data.keyword.ghe_short}} 之前，请要求公司的区域管理员使用 LDAP，将您在公司的用户注册表中的用户标识添加到 {{site.data.keyword.Bluemix_notm}} Dedicated 实例。有关设置 {{site.data.keyword.ghe_short}} 帐户的信息，请参阅 [{{site.data.keyword.ghe_long}} 入门](/docs/services/ghededicated/index.html){: new_window}。

 b. 在“可配置的集成”部分中，单击 **{{site.data.keyword.ghe_short}}**。    

 c. 复查新 {{site.data.keyword.ghe_short}} 存储库的缺省名称。如果需要，请更改新存储库的名称。下图显示了从样本存储库克隆的存储库示例。您可以使用现有存储库或新存储库。要使用新存储库，您可以创建空的存储库、克隆存储库或派生存储库。![缺省存储库位置](images/toolchain_ghe_config.png)

1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **{{site.data.keyword.ghe_short}}**。

1. 如果您具有 {{site.data.keyword.ghe_short}} 存储库且想要使用，请输入该存储库的 URL。对于存储库类型，请单击**现有**。
1. 如果您想要使用新的 {{site.data.keyword.ghe_short}} 存储库，请输入存储库的名称，输入您要克隆或派生的存储库的 URL，然后选择存储库类型：

 a. 要创建空的存储库，请单击**新建**。

 b. 要创建存储库的副本，请单击**克隆**。

 c. 要派生存储库以便您可以通过拉出请求来提供更改，请单击**派生**。

1. 要使用 GitHub Issues 进行问题跟踪，请选中**启用 GitHub Issues** 复选框。
1. 单击**创建集成**。
1. 单击您要使用的 {{site.data.keyword.ghe_short}} 存储库的卡。此时将打开您公司的 {{site.data.keyword.ghe_short}} 存储库。

  您可以在 Eclipse Orion {{site.data.keyword.webide}} 中使用集成的源代码管理工具，以编辑 {{site.data.keyword.ghe_short}} 存储库，并从您的工作空间部署应用程序。
  {: tip}

1. 如果您已启用 GitHub Issues，请单击 **GitHub Issues**。您可以对整个工具链使用此 GitHub Issues 的实例，即使工具链包含多个 GitHub 存储库也是如此。    

如果您对要链接到的存储库没有管理员特权，那么您的集成将受到限制，因为您无法使用 Webhook。将提交推送到存储库时，需要 Webhook 才能自动运行管道。没有 Webhook，您必须手动启动管道。
{: tip}


## 配置 GitLab
{: #gitlab}

GitLab 是 Git 存储库基于 Web 的托管服务。您可以同时具有存储库的本地和远程副本，这使协作变得更加轻松。

您可以将 GitLab 配置为工具链中的工具集成，以便您可以管理 GitLab.com 上或您公司 GitLab 实例中新存储库或现有存储库中的源代码。通过 Wiki、问题跟踪和合并请求，可参与社交编码。

如果您在创建工具链时配置此工具集成，请遵循以下步骤：

1. 如果要将源代码存储在 GitLab 存储库中，请在“可配置的集成”部分中，单击 **GitLab**。如果要在 {{site.data.keyword.Bluemix_notm}} Public 上配置此工具集成，而您并未授权 {{site.data.keyword.Bluemix_notm}} 访问 GitLab，请单击**授权**以转至 GitLab Web 站点。如果您没有活动的 GitLab 会话，那么系统会提示您登录。单击**授权应用程序**，以允许 {{site.data.keyword.Bluemix_notm}} 访问 GitLab 帐户。如果您有活动的 GitLab 会话，但最近未输入过密码，那么系统可能会提示您输入 GitLab 密码以进行确认。
1. 如果要使用您自己的 GitLab 服务器上的存储库，请在“可配置的集成”部分中，单击**添加定制服务器**。

 网络必须能够从 {{site.data.keyword.Bluemix_notm}} Dedicated 环境访问目标 GitLab 服务器。
 {: tip}

 输入定制 GitLab 服务器的标题，并指定该服务器的根 URL。输入您的个人访问令牌，然后单击**保存定制集成**。

  如果您没有个人访问令牌，可以进行创建：

     a. 在任何 GitLab 页面上，单击“概要文件”图标，然后单击**设置**。

     b. 在“访问令牌”页面上，输入要为其创建个人访问令牌的应用程序的名称。

     c. 可选。选择访问令牌的到期日期。

     d. 选中 **API** 复选框，以定义个人令牌的访问权。

     e. 单击**创建个人访问令牌**。

     f. 将令牌复制到安全的位置或密码管理应用程序。出于安全原因，离开此页面后，您将无法再看到该令牌。

1. 复查 GitLab 存储库的缺省目标存储库位置。那些存储库是从样本存储库克隆而来的。如果需要，请更改目标存储库的名称。


如果您有工具链且要向其添加此工具集成，请执行以下步骤：

1. 在 DevOps 仪表板的“工具链”页面上，单击工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。
1. 单击**添加工具**。
1. 在“工具集成”部分中，单击 **GitLab**。
1. 单击要使用的 GitLab 服务器。
1. 如果您有 GitLab 存储库并且想要使用该存储库，那么对于存储库类型，请单击**现有**并输入 URL。
1. 如果要使用新的 GitLab 存储库，请输入存储库的名称，输入您要克隆或派生的存储库的 URL，然后选择存储库类型：

 a. 要创建空的存储库，请单击**新建**。

 b. 要创建 GitLab 存储库的副本，请单击**克隆**。

 c. 要派生 GitLab 存储库以便您可以通过拉出请求来提供更改，请单击**派生**。

1. 如果要在服务器上创建公共存储库，请清除**使此存储库成为专用**复选框。
1. 如果要使用 GitLab Issues 进行问题跟踪，请选中**启用 GitLab Issues** 复选框。
1. 如果您要通过在提交上创建标记和注释，在提交所参考的问题上创建标签和注释，跟踪代码更改的部署，请选择**跟踪代码更改的部署**复选框。有关更多信息，请参阅[使用工具链跟踪代码部署位置 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}。
1. 单击**创建集成**。
1. 单击要使用的 GitLab 存储库的卡。根据您选择的存储库，将打开 GitLab Web 站点或您公司的 GitLab 存储库，您可在其中查看存储库的内容。

  您可以在 Eclipse Orion {{site.data.keyword.webide}} 中使用集成的源代码管理工具来编辑 GitLab 存储库，并从您的工作空间部署应用程序。
  {: tip}

1. 如果您已启用 GitLab Issues，请单击 **GitLab Issues**，以将其打开。即使工具链中包含多个 GitLab 存储库，也可以将此 GitLab Issues 实例用于整个工具链。    

如果您对要链接到的存储库没有所有者或支配者特权，那么您的集成将受到限制，因为您无法使用 Webhook。将提交推送到存储库时，需要 Webhook 才能自动运行管道。没有 Webhook，您必须手动启动管道。
{: tip}

### 了解有关 GitLab 的更多信息

要了解有关 GitLab 的更多信息，请参阅 IBM Cloud Garage Method 上的 [GitLab 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_gitlab/){: new_window}。


## 配置 Jenkins
{: #jenkins}

Jenkins 是基于服务器的开放式源代码工具，其可持续构建并测试软件，支持持续集成和持续交付的实践。

创建 Jenkins 工具集成之前，您必须具有 Jenkins 服务器。
{: important}

使用 Jenkins 工具集成，您可以将 Jenkins 作业通知发送到工具链中的其他工具，如 Slack 和 PagerDuty。要跟踪部署中的代码，可以向 Git 落实及相关的 Git 或 JIRA 问题添加部署消息。您还可以在“工具链连接”页面上查看您的部署。您可以将测试结果提供给 {{site.data.keyword.DRA_short}}、添加自动化质量检测点并跟踪您的部署风险。

配置 Jenkins 以自动持续构建、测试和部署应用程序：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Jenkins**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Jenkins**。

1. 在工具链的 Jenkins 卡上，输入您要针对此工具集成显示的名称。
1. 输入在您单击工具链中 Jenkins 卡时想要打开的 Jenkins 服务器的 URL。
1. 复制生成的工具链 Webhook。
1. 在 Jenkins 服务器中，完成以下步骤：

 a. [安装 IBM Cloud DevOps 插件 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Installingtheplugin){: new_window}。

 b. [配置 Jenkins 以通知工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Notifyingtoolchains){: new_window}。

 c. 返回到“配置集成”页面，以进行 Jenkins 工具集成。

1. 单击**创建集成**。
1. 从工具链中单击 **Jenkins** 以查看 Jenkins 服务器。  

### 了解有关 Jenkins 的更多信息

要了解有关 Jenkins 的更多信息，请参阅 IBM Cloud Garage Method 上的 [ 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/deliver/tool_jenkins/){: new_window} 或学习以下教程：

  * [通过使用“具有 GitHub 和 Jenkins 的 Deployment Risk Analytics”工具链来确保部署质量 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

## 配置 JIRA
{: #jira}

JIRA 是跟踪与软件相关的问题和错误的工具。JIRA 工具集成会在 Jenkins 或 {{site.data.keyword.deliverypipeline}} 运行部署时，更新项目的问题。要让 JIRA 工具集成跟踪问题，您必须在提交消息中使用 JIRA 智能提交。要了解有关 JIRA 智能提交的更多信息，请参阅[使用智能提交 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://confluence.atlassian.com/fisheye/using-smart-commits-298976812.html){: new_window}。

配置 JIRA 以计划、跟踪和交付质量代码：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **JIRA**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **JIRA**。

1. 如果您有 JIRA 项目且想要与其进行连接，那么对于 JIRA 类型，请单击**现有**：

 a. 输入 JIRA 项目的 JIRA 项目密钥。您可以在 JIRA 项目的 URL 中找到项目密钥。

 b. 输入 JIRA 实例的基本 API URL。您可以从 JIRA 实例的标头中找到 API URL。单击**管理**图标并单击**系统**。

 c. 如果要连接到专用 JIRA 实例，或者要接收来自公用 JIRA 实例的可跟踪性信息，请输入 JIRA 用户名和密码。

 d. 要通过创建所参考问题的标签和注释来跟踪项目的代码更改部署，请选中**跟踪代码更改的部署**复选框。请确保您使用 JIRA 智能提交来参考 GitHub 提交中的 JIRA 问题。如果您未选择此选项，那么 JIRA 工具集成将忽略任何提交。

1. 如果您想要创建 JIRA 项目，那么对于 JIRA 类型，请单击**新建**：

 a. 输入要用于新项目的 JIRA 项目密钥。此密钥用作项目 URL 中的唯一标识。

 b. 输入 JIRA 项目的名称。

 c. 输入 JIRA 实例的基本 API URL。您可以从 JIRA 实例的标头中找到 API URL。单击**管理**图标并单击**系统**。

 d. 输入要用于此项目的 JIRA 项目主管的用户名。要将某人指定为 JIRA 项目主管，该人员必须在 JIRA 中具有项目主管许可权。

 e. 输入此 JIRA 实例的管理员用户名。

 f. 输入此 JIRA 实例的管理员密码。

 g. 要通过创建所参考问题的标签和注释来跟踪项目的代码更改部署，请选中**跟踪代码更改的部署**复选框。请确保您使用 JIRA 智能提交来参考 GitHub 提交中的 JIRA 问题。如果您未选择此选项，那么 JIRA 工具集成将忽略任何提交。

1. 单击**创建集成**。
1. 从工具链中单击 **JIRA** 以查看您所连接的 JIRA 项目的仪表板。

### 了解有关 JIRA 的更多信息

要了解有关 JIRA 的更多信息，请参阅 IBM Cloud Garage Method 上的 [JIRA 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/code/tool_jira/){: new_window} 或学习以下教程：

  * [通过使用“具有 GitHub 和 JIRA 的 Developer Insights 和 Team Dynamic”获取深入见解 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/gain-insights-developer-insights-and-team-dynamics-with-github-and-jira-toolchain){:new_window}


## 配置 Nexus
{: #nexus}

配置 Nexus 存储库管理器以在 Nexus 存储库中存储构建工件：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Nexus**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Nexus**。

1. 输入此 Nexus 工具集成实例的名称。
1. 输入在您单击工具链中 Nexus 卡时想要打开的 Nexus 存储库的 URL。
1. 选择您要连接到的存储库类型。
1. 如果您选择了 **npm 注册表**，请遵循以下步骤：

 a. 输入与注册表相关联的电子邮件地址。

 b. 输入与注册表相关联的认证令牌。

 c. 输入 Nexus 发布存储库的 URL，这是您在 Nexus 服务器上的专用注册表。

 d. 输入用于组合多个公共和专用 npm 注册表的镜像或公共注册表的 URL。例如，此 URL 可能是可访问专用注册表和 npm 全局注册表高速缓存的 Nexus 服务器上虚拟注册表的 URL。

1. 如果您选择了 **Maven 存储库**，请遵循以下步骤：

 a. 输入与存储库相关联的用户标识。

 b. 输入与存储库相关联的密码。

 c. 输入 Nexus 发布存储库的 URL，这是您在 Nexus 服务器上的专用发布存储库。

 d. 输入 Nexus 快照存储库的 URL，这是您在 Nexus 服务器上的专用快照存储库。

 e. 输入用于组合多个公共和专用 Maven 存储库的镜像或公共存储库的 URL。例如，此 URL 可能是可访问专用存储库和 Maven 中央存储库高速缓存的 Nexus 服务器上虚拟存储库的 URL。

1. 单击**创建集成**。
1. 从工具链中单击您要使用的 Nexus 存储库的卡。这将打开 Nexus Web 站点，您可在其中查看存储库的内容。
1. 可选：如果您在 {{site.data.keyword.Bluemix_notm}} Public 中使用工具链，并且想要使用 Nexus 与 npm 来构建应用程序，请配置管道以添加 npm 构建作业。有关配置构建作业的指示信息，请参阅[在管道中配置 Nexus npm 构建作业](#config_nexus_npm)一节。
1. 可选：如果您在 {{site.data.keyword.Bluemix_notm}} Public 中使用工具链，并且想要使用 Nexus 与 Maven 来构建应用程序，请配置管道以添加 Maven 构建作业。有关配置构建作业的指示信息，请参阅[在管道中配置 Nexus Maven 构建作业](#config_nexus_maven)一节。

### 在管道中配置 Nexus npm 构建作业
{: #config_nexus_npm}

在管道中配置 npm 构建作业之前，您需要可使用构建 SCM 存储库作为输入的工作管道，并且您必须为工具链配置 Nexus。有关配置 Nexus 的指示信息，请参阅 [Nexus](#nexus) 一节。

配置 {{site.data.keyword.deliverypipeline}} 以添加 npm 构建作业：

1. 创建阶段并设置适当 SCM 存储库的输入。
1. 在阶段上，添加构建作业。
1. 配置构建作业：![npm 构建作业](images/nexus_npm_job.png)

  a. 对于构建器类型，请选择 **NPM 构建**。

  b. 如果已配置 Nexus 工具集成的多个实例，请输入要为其配置 npm 构建作业的 Nexus 工具集成的名称。

  c. 对于工具集成类型，请选择 **Nexus**。

  d. 对于构建命令，请输入用于构建 npm 模块或将其发布到注册表的命令。此示例显示构建模块或进行发布的命令。
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  **提示**：您可以在 Nexus 工具集成的配置设置中，查找用于连接到注册表的 URL 和用户凭证。



  e. 如果您的构建作业发布到 Nexus 注册表且您节点模块版本的格式为 `x.y.z-SNAPSHOT.w`，请选中**增量快照模块版本**复选框。构建作业会在作业发布到 Nexus 注册表之前，自动更新模块版本。构建作业会从 npm 注册表和本地 `package.json` 文件中选择最高的模块版本，并使用 semver 递增模块版本。 构建作业不会将更改交付到 SCM 存储库。

1. 单击**保存**。管道无论何时运行，此构建作业都会使用 Nexus 工具集成中的配置信息来连接到您的 npm 注册表。

### 在管道中配置 Nexus Maven 构建作业
{: #config_nexus_maven}

在管道中配置 Maven 构建作业之前，您需要可使用构建 SCM 存储库作为输入的工作管道，并且您必须为工具链配置 Nexus。有关配置 Nexus 的指示信息，请参阅 [Nexus](#nexus) 一节。

配置 {{site.data.keyword.deliverypipeline}} 以添加 Maven 构建作业：

1. 创建阶段并设置适当 SCM 存储库的输入。
1. 在阶段上，添加构建作业。
1. 配置构建作业：![Maven 构建作业](images/nexus_maven_job.png)

  a. 对于构建器类型，请选择 **Maven 构建**。

  b. 如果已配置 Nexus 工具集成的多个实例，请输入要为其配置 Maven 构建作业的 Nexus 工具集成的名称。

  c. 对于工具集成类型，请选择 **Nexus**。

  d. 对于构建命令，请输入用于构建 Maven 模块或将其发布到快照注册表的命令。此示例显示构建模块或进行发布的命令。
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  您可以在 Nexus 工具集成的配置设置中，查找用于连接到注册表的 URL 和用户凭证。
  {: tip}

1. 单击**保存**。管道无论何时运行，此构建作业都会使用 Nexus 工具集成中的配置信息来连接到您的 Maven 存储库。

### 了解有关 Nexus 的更多信息

要了解有关 Nexus 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Nexus 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/deliver/tool_nexus/){: new_window}。


## 配置定制工具（其他工具）
{: #othertool}

如果您的团队使用工具链集成列表中不包含的工具，那么您可以集成定制工具。

配置定制工具，以便与工具链中的其他工具一起使用，并且可供您的团队使用：

1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击**其他工具**。

1. 输入工具名称。
1. 选择与该工具关联最紧密的生命周期阶段。此选择将决定在“概述”页面中，您的工具列在哪个类别之下。
1. 添加图标 URL。该图标将显示在工具集成的卡上。
1. 添加文档 URL。
1. 指定工具实例名称。例如：My Team Tool。
1. 添加工具实例 URL。无论何时单击工具集成的卡，此 URL 都会打开。
1. 添加工具的描述。
1. （高级）根据需要添加其他属性。例如，列出您的工具与工具链中其他工具集成所需的任何信息或属性。  
1. 单击**创建集成**。

### 了解有关定制工具的更多信息

要了解有关定制工具的更多信息，请参阅[为 {{site.data.keyword.Bluemix_notm}} 工具链引入定制工具集成 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2016/10/custom-tool-integration-with-bluemix-toolchains/){: new_window} 或学习以下教程：

  * [将定制工具集成添加到工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/add-a-custom-tool-integration-to-a-toolchain){:new_window}


## 配置 PagerDuty
{: #pagerduty}

PagerDuty 可将多个监视系统的数据集成到单一视图。发生问题时，PagerDuty 可确保及时通知当时最有能力修正该问题的团队成员。如果该团队成员未响应该问题，就会配置呈报，以将该问题传递给第二顺位的代表或操作管理员。

配置 PagerDuty 在发生管道阶段失败时发送通知，以便您可以更快速地修正问题，并缩短停机时间：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **PagerDuty**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **PagerDuty**。

1. 如果要使用 API 密钥在帐户级别集成 PagerDuty，请单击**帐户**：

 a. 输入 PagerDuty 帐户的 API 访问密钥。如果您没有 PagerDuty 帐户，请[注册帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://signup.pagerduty.com/accounts/new){: new_window}。有关查找密钥的指示信息，请参阅[生成 API 密钥 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://support.pagerduty.com/hc/en-us/articles/202829310-Generating-an-API-Key){: new_window}。

 b. 输入 PagerDuty 服务的名称。

 c. 输入主要 PagerDuty 联系人的电子邮件地址。

 d. 输入主要 PagerDuty 联系人的电话号码。

1. 如果要使用集成密钥在服务级别集成 PagerDuty，请单击**服务**：

 a. 输入要向其发布警报的 PagerDuty 服务的 URL。

 b. 输入 PagerDuty 集成密钥。您可以在 PagerDuty 服务页面的“集成”部分中找到密钥或创建密钥。

1. 单击**创建集成**。
1. 单击 **PagerDuty** 以转至 pagerduty.com。您可以查看与您在为工具链配置此工具集成时所指定的 PagerDuty 服务相关联的事件。

### 了解有关 PagerDuty 的更多信息

要了解有关 PagerDuty 的更多信息，请参阅 IBM Cloud Garage Method 上的 [PagerDuty 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/manage/tool_pagerduty/){: new_window}，或者学习以下教程和 Garage Method 推广课程：

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [成为 Garage Method 推广者 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## 配置 Rational Team Concert
{: #rationalteamconcert}

IBM Rational Team Concert&trade; 是集成开发任务的团队协作工具，包括迭代规划、变更管理、缺陷跟踪、源代码控制、构建自动化和报告。

配置 Rational Team Concert 以在开发环境中应用 DevOps 方法和持续交付：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Rational Team Concert**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Rational Team Concert**。

1. 输入在您单击工具链中 Rational Team Concert 卡时想要打开的 Rational Team Concert 服务器的 URL。
1. 输入您要用于访问 Rational Team Concert 服务器的用户标识。
1. 输入您要用于访问 Rational Team Concert 服务器的密码。
1. 如果您具有要添加到工具链的 Rational Team Concert 项目区域，请遵循以下步骤：

 a. 从**项目区域类型**列表中，选择**现有项目区域**。

 b. 输入要添加到工具链的项目区域的名称。

1. 如果您想要创建要添加到工具链的 Rational Team Concert 项目区域，请遵循以下步骤：

 a. 从**项目区域类型**列表中，选择**新项目区域**。

 b. 输入要添加到工具链的新项目区域的名称。

 c. 输入要用于创建项目的 Rational Team Concert 流程模板的名称。

1. 要通过创建工作项的标签和注释来跟踪项目的代码更改部署，请选择**跟踪代码更改的部署**复选框。
1. 单击**创建集成**。
1. 从工具链单击 **Rational Team Concert** 以打开所配置的 Rational Team Concert 仪表板。

### 了解有关 Rational Team Concert 的更多信息

要了解有关 Rational Team Concert 的更多信息，请参阅 IBM Cloud Garage Method 上的 [IBM Rational Team Concert 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/think/tool_rtc/){: new_window}。


## 配置 Sauce Labs
{: #saucelabs}

Sauce Labs 运行功能单元测试。如果将 Sauce Labs 测试套件配置为 {{site.data.keyword.deliverypipeline}} 中的测试作业，作为持续交付过程的一部分，该测试套件可对您的 Web 或移动应用程序运行测试。这些测试可为您的项目提供有价值的流程控制，充当防止部署错误代码的检测点。

 此工具集成仅在 {{site.data.keyword.Bluemix_notm}} Public 上可用。
 {: tip}

配置 Sauce Labs 在多个操作系统和浏览器上运行自动功能测试，以便您可以模拟用户可能使用 Web 站点或应用程序的方式：

1. 如果在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Sauce Labs**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Sauce Labs**。

1. 输入与 Sauce Labs 帐户相关联的用户名。您可以[在 Sauce Labs 帐户页面的欢迎消息中查找用户名 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://saucelabs.com/account){: new_window}。
1. 输入 Sauce Labs 帐户的访问密钥。您可以[在 Sauce Labs 帐户页面中查找密钥 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://saucelabs.com/account){: new_window}。
1. 单击**创建集成**。
1. 单击 **Sauce Labs**，以转至 saucelabs.com 并查看工具链的测试活动。

 如果您将 Sauce Labs 测试作业添加到 {{site.data.keyword.deliverypipeline}}，那么可以选择该服务实例。有关在管道中配置测试作业的指示信息，请参阅[在管道中配置 Sauce Labs 测试作业](#config_saucelabs)一节。
 {: tip}

### 了解有关 Sauce Labs 的更多信息

要了解有关 Sauce Labs 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Sauce Labs 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/deliver/tool_sauce_labs/){: new_window} 或学习以下教程：

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}



## 配置 Slack
{: #slack}

团队中的每一个人都可以看到发布到公共 Slack 通道的通知。您要对发布的内容负责。
{: important}

Slack 是基于云的实时消息传递和通知系统。Slack 提供持久交谈，可替代电子邮件用于团队协作，其互动性更高。您可以通过专用通道或与您工作直接相关的一组通道，与团队进行通信。您还可以通过通道或直接消息，在两人或多人之间共享文件和图像。直接消息和通道的通信会保留，以便您可以对它们进行搜索。

配置 Slack，以从工具集成接收有关工具链的通知，如测试和部署活动：

1. 如果您在创建工具链时配置此工具集成，请在“可配置的集成”部分中，单击 **Slack**。
1. 如果您有工具链，并且要将此工具集成添加到该工具链，请在 DevOps 仪表板的“工具链”页面上单击该工具链，以打开其“概述”页面。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**，然后单击**概述**。

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **Slack**。

1. 输入 Slack Webhook URL，其由 Slack 作为入局 Webhook 生成。您需要 Slack Webhook URL，Slack 通道才能从工具集成接收有关工具链的通知。有关创建或查找 Webhook 的指示信息，请参阅[入局 Webhook ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://api.slack.com/incoming-webhooks){: new_window}。

 如果您使用 API 密钥让 Slack 通道从工具集成接收有关工具链的通知，那么您必须更新配置以改用 Webhook。
 {: tip}

1. 输入您想要发送通知的目标 Slack 通道的名称。在 Slack 团队中，该通道必须已经存在且处于活动状态。
1. 为 Slack 团队输入 URL 主机名，其为团队 URL 中 `.slack.com` 前的单词或短语。例如，如果团队 URL 为 `https://team.slack.com`，那么主机名为 `team`。
1. 单击**创建集成**。

 如果无法访问您指定的 Slack 通道和团队，那么在 Slack 卡上会显示`设置失败`错误。将鼠标悬停在`设置失败`消息上并单击**重新配置**。请确保为 Slack 团队的 Slack Webhook URL、Slack 通道和 URL 主机名，使用有效的配置参数。按需要更新设置并单击**保存集成**。
 {: tip}

1. 单击 **Slack**。您可以在已配置的 Slack 通道中查看工具链的所有活动。

### 了解有关 Slack 的更多信息

要了解有关 Slack 的更多信息，请参阅 IBM Cloud Garage Method 上的 [Slack 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/culture/tool_slack/){: new_window}，或者学习以下教程和 Garage Method 推广课程：

  * [使用“在 Cloud Foundry 上开发和测试微服务”工具链 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [成为 Garage Method 推广者 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## 配置 SonarQube
{: #sonarqube}

SonarQube 提供了源代码总体运行状况和质量的概述，并重点阐述了在新代码中发现的问题。代码分析器可检测到超过 20 种代码编写语言的棘手错误，例如空指针取消引用、逻辑错误和资源泄漏。

配置 SonarQube 以持续分析和测量源代码的质量：

1. 在 DevOps 仪表板上，单击**工具链**。单击要将 SonarQube 添加到的工具链。或者，在应用程序“概述”页面的“持续交付”卡上，单击**查看工具链**。然后，单击**概述**。  

 a. 单击**添加工具**。

 b. 在“工具集成”部分中，单击 **SonarQube**。

1. 输入此 SonarQube 工具集成实例的名称。
1. 输入在您单击工具链中 SonarQube 卡时想要打开的 SonarQube 实例的 URL。
1. 可选：输入用于连接到 SonarQube 服务器的用户名。

 仅当使用密码连接到 SonarQube 服务器时，才需要指定用户名。如果是使用认证令牌进行连接，请将此字段保留为空。
 {: tip}

1. 输入用于连接到 SonarQube 服务器的密码或认证令牌。
1. 单击**创建集成**。
1. 从工具链中单击 **SonarQube** 以查看您所连接到的 SonarQube 实例的仪表板。

### 了解有关 SonarQube 的更多信息

要了解有关 SonarQube 的更多信息，请参阅 IBM Cloud Garage Method 上的 [SonarQube 文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/garage/content/learn/tool_sonarqube/){: new_window}。
