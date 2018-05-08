---

copyright:
  years: 2015, 2018
lastupdated: "2018-3-26"

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

# Estendendo o Delivery Pipeline
{: #deliverypipeline_extending}

É possível estender os recursos do {{site.data.keyword.deliverypipeline}} do {{site.data.keyword.contdelivery_full}} configurando suas tarefas para usar serviços suportados. Por exemplo, as tarefas de teste executam varreduras de código
estático e as tarefas de construção podem globalizar as sequências.
{:shortdesc}

<!-- Include a sentence to briefly introduce the steps/subtopics. Example: -->

As tarefas a seguir descrevem como integrar ferramentas selecionadas com um Pipeline de entrega.

## Executando varreduras de código estático usando o pipeline

{: #deliverypipeline_scan}

Deseja encontrar os problemas de segurança em seu código antes de implementá-lo? Quando você usa o {{site.data.keyword.staticanalyzerfull}} como parte de seu pipeline, é possível executar verificações automatizadas com relação aos arquivos binários de construção `.war`, `.ear`, `.jar` ou `.class` estáticos do app Java™.

Um pipeline que usa o serviço {{site.data.keyword.staticanalyzershort}} normalmente inclui estes estágios:

+ Um estágio de construção para construir os arquivos de origem
+ Um estágio de processamento que inclui estas tarefas:
  + Uma tarefa de construção para executar o serviço Analisador estático
  + Uma tarefa de compilação para executar uma compilação de
contêiner
+ Um estágio de implementação para implementar o contêiner


### Criando uma varredura de código estático

Antes de iniciar, [revise os Termos de uso do serviço ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://www.ibm.com/software/sla/sladb.nsf/sla/bm-6814-01){: new_window}

<!-- Use ordered list markup for the step section. Include code examples as needed. -->

1. Crie um estágio de processamento.

  a. Clique em **INCLUIR ESTÁGIO**.

  b. Nomeie o estágio, por exemplo, `Processamento`.

  c. Para o tipo de entrada, selecione **Artefatos de construção**.

  d. Para o estágio e tarefa, verifique os valores e atualize-os se necessário.

2. No estágio de processamento, inclua uma tarefa de compilação
para executar a varredura de código.

  a. Na guia **TAREFAS**, clique em **INCLUIR TAREFA**.

  b. Para o tipo de tarefa, selecione **Testar**.

  c. Para o tipo de testador, selecione **IBM Security Static Analyzer**.

  d. Para a organização e o espaço, verifique os valores e atualize-os se necessário.

  e. Selecione ou limpe a caixa de seleção **Configurar serviço e espaço para mim** conforme necessário.

    * Se você desejar que o pipeline verifique o espaço do {{site.data.keyword.Bluemix_short}} para o serviço e um app que liga o serviço ao contêiner, marque a caixa de seleção. Se o serviço ou o app
vinculado não existir, o pipeline incluirá o plano grátis do serviço em seu espaço. O
app vinculado que é criado se chama `pipeline_bridge_app`. Em
seguida, o pipeline usa as credenciais do pipeline_bridge_app para acessar os serviços
vinculados.

    * Se você já configurou o serviço e ligou o app em seu espaço {{site.data.keyword.Bluemix_short}} ou se desejar [configurar esses requisitos manualmente](/docs/containers/container_integrations.html#container_binding_pipeline){: new_window}, deixe a caixa de seleção limpa.

  f. No campo **Minutos de espera para a análise ser concluída**, digite um valor de 0 - 59 minutos. O valor padrão é de 5 minutos. Uma URL para o painel do {{site.data.keyword.staticanalyzershort}} está nos logs do console no término da tarefa.

     Se a varredura do {{site.data.keyword.staticanalyzershort}} não for concluída antes do tempo especificado, a tarefa falhará. No entanto, a análise de varredura continua em execução e é possível visualizá-la no painel do {{site.data.keyword.staticanalyzershort}}. Depois que varredura do {{site.data.keyword.staticanalyzershort}} for concluída, se você executar novamente a tarefa, a solicitação de varredura não será reenviada e a tarefa de pipeline poderá ser concluída. Como alternativa, é possível configurar o pipeline para não ser bloqueado
no caso de um resultado de varredura bem-sucedida. Para obter instruções, consulte a
próxima etapa.

  g. Selecione ou limpe a caixa de seleção **Parar de executar este estágio se esta tarefa falhar** dependendo do que você desejar que aconteça se essa tarefa falhar ou atingir o tempo limite. As tarefas podem falhar quando as
vulnerabilidades são altas.

    * Se você marcar a caixa de seleção e a tarefa falhar, as tarefas posteriores
no estágio e nos estágios posteriores não serão executadas.

    * Se você desmarcar a caixa de seleção e a tarefa falhar, o estágio
continuará sem bloquear as tarefas e os estágios posteriores. Por exemplo, se você souber
que o relatório inclui muitos problemas a serem processados, poderá configurar o estágio
para continuar porque a varredura pode levar um longo tempo. Neste cenário, você pode não desejar que o
restante das tarefas e dos estágios parem apenas porque a
varredura está demorando muito.

  h. Clique em **SALVAR**.

3. Quando a tarefa for concluída, visualize os resultados clicando em
**Visualizar logs e histórico**. Se a análise for bem-sucedida ou
atingir o tempo limite, uma URL será mostrada nos resultados da varredura. Se o status da
varredura estiver pendente, aguarde até que a varredura seja concluída para ver os
resultados completos.

4. Se você precisar executar o estágio de processamento novamente antes que a
análise seja concluída, será possível. Entretanto, nas situações a seguir, uma nova
análise não será submetida novamente e os resultados anteriores serão usados:
  * O estágio de processamento ainda estava em execução quando você iniciou uma nova análise
  * Uma varredura já foi enviada para a construção
  * Uma nova construção de origem não foi executada ainda

5. Para iniciar uma nova análise, conclua uma destas etapas:
  * Execute o estágio de construção que entra no estágio de processamento e, em
seguida, execute o estágio de processamento novamente.
  * Abra a URL dos resultados da varredura e clique no ícone
**Lixeira**. Em seguida, execute o estágio de processamento novamente.

Exemplos de saída do
console:

**Varredura bem-sucedida**
![Exemplo de varredura bem-sucedida](images/analyzer_success.png)

**Varredura pendente**
![Exemplo de varredura pendente](images/analyzer_pending.png)

Para obter mais informações sobre como usar o serviço {{site.data.keyword.staticanalyzershort}}, veja os [docs do serviço {{site.data.keyword.staticanalyzershort}}](/docs/services/ApplicationSecurityonCloud/index.html){: new_window}.

<!--

## Globalizing strings by using the pipeline
{: #deliverypipeline_globalize}

You can translate strings automatically into other languages when you use the IBM Globalization Pipeline service with your pipeline. IBM Globalization Pipeline uses machine translation to translate your source files as part of the pipeline's build and deployment process.

You can also update the machine-translated strings within the globalization project. A translator or native speaker of the language can then review the machine-translated strings to ensure that they are of a high quality.

To see an example of a typical pipeline that uses the Globalization Pipeline service, watch this video:

<iframe width="640" height="360" src="https://www.youtube.com/embed/UToj7FIomCg?feature=player_embedded" frameborder="0" allowfullscreen></iframe>

### Creating a globalization stage and job
Before you begin:

1. All English-translatable strings should be included in one or more `filename_en.properties` or `filename_en.json` files that all use the same name. For example: `messages_en.properties`.

2. If your messages are in `.json` files, remove the depth from the structure by removing any subkeys. To remove the subkeys, change instances of `{key: {subkey: value, subkey:value}}` to `{key:value, key:value}`.

To create the globalization stage and job:

1. Create a globalization stage.

  a. Click **ADD STAGE**.

  b. Name the stage; for example, `Globalization`.

  c. For the input type, select **SCM repository**.

2. In the globalization stage, add a job to translate the source files.

  a. On the **JOBS** tab, click **ADD JOB**.

  b. For the job type, select **Build**.

  c. For the builder type, select **IBM Globalization Pipeline**.

  d. For the organization and space, verify the values and update them if needed.

  e. In the **Source file name** field, type the name and extension of the `.properties` or `.json` input file. If you have files in different subdirectories, but they all have the same name, you need to type the file name once only. For example, if you have a `messages_en.properties` file in three directories, type `messages_en.properties` for the source file name, and all files with that name will be translated.

  f. Determine whether to select the **Set up service and space for me** check box.

    * If you want the pipeline to check your {{site.data.keyword.Bluemix_notm}} space for the service and an app that binds the service to the container, select this check box. If the service or bound app does not exist, the pipeline adds the free plan of the service to your space for you. The bound app that is created is named `pipeline_bridge_app`. Then, the pipeline uses the credentials from pipeline_bridge_app to access the bound services.

    * If you configured the service and bound app in your {{site.data.keyword.Bluemix_notm}} space already or if you want to [configure these requirements manually](/docs/containers/container_integrations.html#container_binding_pipeline), leave this check box cleared.

  g. For the Globalization bundle prefix, enter a prefix for the bundle name, which is structured in this format: `<globalization_bundle_prefix>.path.to.source.file`. The pipeline job creates this Globalization bundle for you in the Globalization Pipeline service.


    **Tip:** Use the DevOps Services project name in the prefix so that the project can be identified easily in the Globalization Pipeline service.


  h. Click **SAVE**.

3. Create another stage to package your app. For the input of the job in this stage, use the IBM Globalization Pipeline job from the previous stage. Do not use the source as the input. The Globalization Pipeline job augments the source files with the machine-translated strings.

4. To ensure that the machine-translated content is included in the packaged app, create another stage to package the app in. For the input to that stage, include the Globalization Pipeline job.

The machine translated files are placed in the same directory as the source `.properties` or `.json` file. To view the files, click **Job > Artifacts**.

After the stage is completed, you can review the translated files from the console output. You can also direct translators to the files so that they can review the machine-translation output and provide revisions to improve quality. The revisions are stored in a Cloudant™ database and take precedence over any future machine translations of the same strings.

For more information about using the Globalization Pipeline service from the {{site.data.keyword.Bluemix_notm}} Dashboard, [see the Globalization Pipeline service documentation](https://www.ng.bluemix.net/docs/services/GlobalizationPipeline/index.html).

-->
<!--

## Creating Slack notifications for builds in the pipeline
{: #deliverypipeline_slack}

You can send notifications about {{site.data.keyword.containerlong}}, {{site.data.keyword.staticanalyzershort}}, and {{site.data.keyword.globalizationfull}} build results from your Delivery Pipeline to your Slack channels.

Before you begin, create or copy a Slack WebHook URL:

1. Open the Slack Integration page for your team: `https://_project_name_.slack.com/services`
2. In the list of integrations, locate **Incoming WebHooks** and click **Add**.
3. Select a channel and click **Add Incoming WebHooks Integration**.
4. Add a **WebHook URL** or copy an existing one.

For more information, see [Incoming WebHooks in the Slack documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://api.slack.com/incoming-webhooks){: new_window}.

To create Slack notifications:

1. In the pipeline, open the configuration for a stage.
2. In the **ENVIRONMENT PROPERTIES** tab, click **ADD PROPERTY**.
3. Select **Text property**.
4. Enter the name and a value for the environment property. Repeat to create multiple environment properties.

  _Table 1. Environment properties for configuring Slack notifications_

  <table>
  <tr>
  <th>Name</th>
  <th>Value</th>
  <th>Description</th>
  <tr/>
  <tr>
    <td><code>SLACK_WEBHOOK_PATH</code></td>
    <td>A URL</td>
    <td>Required. The WebHook URL that is saved in the settings for your Slack Project.</td>
  </tr>
  <tr>
    <td><code>SLACK_COLOR</code></td>
    <td>You can enter one of the following values:
      <ul><li><code>good</code></li>
      <li><code>warning</code></li>
      <li><code>danger</code></li>
      <li>Any hexadecimal color, such as #439FEO</li></ul></td>
    <td>Optional. The color of the border that is displayed along the side of the message in Slack. The default colors are green for good messages, red for bad messages, and gray for informational messages.</td>
  </tr>
  <tr>
    <td><code>NOTIFY_FILTER</code></td>
    <td>To receive only a subset of the message types, enter one of the following values:
      <ul>
      <li><code>good</code>: Get unknown, good and info messages only. Bad messages are not sent.</li>
      <li><code>bad</code>: Get all messages.</li>
      <li><code>info</code>: Get info messages only. Good, bad, and unknown messages are not sent.</li>
      <li><code>unknown</code>: Get all messages.</li></ul>
      Example: If you set <code>NOTIFY_FILTER = bad</code>, error notifications are only displayed in the Slack Channel.</td>
    <td>Optional. Decide which type of messages to send notifications for. By default, good and bad messages are sent, but not informational messages.
      <ul><li><code>good</code>: Successful build results.</li>
      <li><code>bad</code>: Unsuccessful build results.</li>
      <li><code>info</code>: Informational messages about the build process.</li>
      <li><code>unknown</code>: Unknown messages are not assigned a type.</li></ul></td>
   </table>

5. Click **Save**.

6. Repeat these steps to send Slack notifications for other stages that include IBM Container Service, IBM Security Analyzer, and IBM Globalization jobs.

The build notification that is displayed in Slack includes a link to the project and sometimes to the project's dashboard. For a Slack user to open these links, the user must be registered with {{site.data.keyword.Bluemix_notm}} and be a member of the organization that the pipeline is configured in.

## Creating HipChat notifications for builds in the pipeline
{: #deliverypipeline_hipchat}

You can send notifications about IBM Container Service, IBM Security Static Analyzer, and IBM Globalization build results from your Delivery Pipeline to your HipChat rooms.

Before you begin, create or copy and existing HipChat token:

1. Go to your HipChat Account page for your team: `https://_project_name_.hipchat.com/account/api`
2. Create a new token, or use an existing one.

To create HipChat notifications:

1. In the pipeline, open the configuration for a stage.
2. In the **ENVIRONMENT PROPERTIES** tab, click **ADD PROPERTY**.
3. Select **Text Property**.
4. Enter the name and a value for the environment property. Repeat to create multiple environment properties.

  _Table 2. Environment Properties for configuring HipChat notifications_

  <table>
  <tr>
  <th>Name</th>
  <th>Value</th>
  <th>Description</th>
  </tr>
  <tr>
    <td><code>HIP_CHAT_TOKEN</code></td>
    <td>Alphanumeric String</td>
    <td>Required. See "Before you begin" for instructions on creating or copying an existing HipChat token.</td>
  </tr>
  <tr>
    <td><code>HIP_CHAT_ROOM_NAME</code></td>
    <td>Room name</td>
    <td>Required.</td>
  </tr>
  <tr>
    <td><code>HIP_CHAT_COLOR</code></td>
    <td>Enter one of the following values:
      <ul><li><code>yellow</code></li>
      <li><code>red</code></li>
      <li><code>green</code></li>
      <li><code>purple</code></li>
      <li><code>gray</code></li>
      <li><code>random</code></li></ul>
    </td>
    <td>Optional: Specify the background color and the border color of HipChat notifications. If you set <code>HIP_CHAT_COLOR</code>, you do not need to specify the color when you call the script.
     <p><code>-l notification_level</code></p> </td>
  </tr>
  <tr>
    <td><code>NOTIFICATION_COLOR</code></td>
    <td>Enter one of the following values:
      <ul><li><code>good</code></li>
      <li><code>danger</code></li>
      <li><code>info</code></li></ul>
    This variable applies to both HipChat and Clack notification colors. If you specify <code>NOTIFICATION_COLOR</code>, you do not need to specify <code>HIP_CHAT_COLOR</code> or <code>SLACK_COLOR</code>.</td>
    <td>Optional: Specify the background color and the border color of both HipChat and Slack notifications. If you set <code>NOTIFICATION_COLOR</code>, you do not need to specify the color when you call the script.
     <p><code>-l notification_level</code></p> </td>
  </tr>
  <tr>
    <td><code>NOTIFICATION_LEVEL</code></td>
    <td>Enter one of the following values:
      <ul><li><code>good</code></li>
      <li><code>info</code></li>
      <li><code>bad</code></li></ul></td>
    <td>Optional: Specify the notification level. See <code>NOTIFICATION_FILTER</code> for more detail on what triggers the notification.</td>
  </tr>
  <tr>
    <td><code>NOTIFICATION_FILTER</code></td>
    <td>Enter one of the following values:
      <ul><li><code>good</code></li>
      <li><code>info</code></li>
      <li><code>bad</code></li></ul>
    <td>Optional: Specify the notification filter level. Notifications are sent when the following parameters are met:
      <ul><li><code>NOTIFICATION_FILTER = good</code> and <code>NOTIFICATION_LEVEL = bad</code>, <code>good</code>, or <code>unknown</code></li>
      <li><code>NOTIFICATION_FILTER = info</code> and <code>NOTIFICATION_LEVEL = bad</code>, <code>good</code>, <code>info</code>, or <code>unknown</code></li>
      <li><code>NOTIFICATION_FILTER = bad</code> and <code>NOTIFICATION_LEVEL = bad</code> or <code>unknown</code></li>
      <li><code>NOTIFICATION_FILTER = unknown</code> and <code>NOTIFICATION_LEVEL = bad</code>, <code>good</code>, or <code>unknown</code></li></ul></td>
    </tr>
  </table>

5. Click **Save**.

6. Repeat these steps to send HipChat notifications for other stages that include IBM Container Service, IBM Security Static Analyzer, and IBM Globalization jobs.

-->
