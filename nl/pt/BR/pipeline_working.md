---

copyright:
  years: 2015, 2018
lastupdated: "2018-3-21"

---


{:screen: .screen}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:shortdesc: .shortdesc}

# Trabalhando com pipelines {: #pipeline-working}

Para automatizar suas construções e implementações para o {{site.data.keyword.Bluemix}}, use pipelines do {{site.data.keyword.contdelivery_full}}.
{: shortdesc}

Com pipelines, é possível escolher entre diversos tipos de construção. Forneça o script de construção
e o {{site.data.keyword.contdelivery_short}} o executará; não é necessário
configurar sistemas de construção. Em seguida, com um clique, é possível implementar automaticamente seu app para um ou
vários espaços de {{site.data.keyword.Bluemix_notm}}, servidores públicos de Cloud Foundry ou contêineres Docker no IBM Containers para {{site.data.keyword.Bluemix_notm}}.

Tarefas de construção compilam e compactam o código-fonte do app a partir de
repositórios Git. As tarefas de construção produzem artefatos implementáveis, como arquivos WAR ou contêineres Docker para IBM Containers. Além disso,
é possível executar testes de unidade automaticamente em sua construção. É possível configurar suas tarefas de construção para que a cada confirmação enviada por push, uma construção seja acionada.

Uma tarefa de implementação toma a saída de uma tarefa de construção e a implementa para servidores IBM Containers ou Cloud Foundry como {{site.data.keyword.Bluemix_notm}}.

É possível implementar para uma ou várias regiões e serviços. Por exemplo, é
possível configurar seu {{site.data.keyword.deliverypipeline}} para usar um ou
mais serviços, testar em uma região e implementar para produção em múltiplas regiões. Para obter informações adicionais, consulte
[Regiões](/docs/overview/whatisbluemix.html#ov_intro_reg){: new_window}.

Se você usar múltiplos pipelines em uma cadeia de ferramentas aberta, será possível criar um pipeline composto para gerenciar a implementação de todos os pipelines em um único local.

Há várias maneiras de criar um pipeline, incluindo adicionar um pipeline para um aplicativo existente e criar um pipeline sem um aplicativo existente. Se
você ainda não tem um serviço de {{site.data.keyword.deliverypipeline}} em sua
organização, será possível acessar o catálogo, clicar em
{{site.data.keyword.deliverypipeline}} e clicar em Criar.

Conclua estas etapas para configurar um {{site.data.keyword.deliverypipeline}} para um aplicativo existente.

1. No Painel do app {{site.data.keyword.Bluemix_notm}}, clique em seu app.
1. No menu da barra de menus do {{site.data.keyword.Bluemix_notm}}, clique em **Serviços** e, em seguida, clique em **DevOps**.
1. Clique em **Pipelines** e depois clique em **Criar um pipeline**.

Para [criar um pipeline ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/devops/pipelines/dashboard/create){: new_window} que esteja configurado para implementar um aplicativo Cloud Foundry, siga estas etapas:

1. Clique em **Cloud Foundry**.
1. Se você desejar usar um nome diferente para o pipeline, mude o nome padrão.
1. Se você desejar usar um nome diferente para o aplicativo, mude o nome padrão. Esse nome é o aplicativo no qual o pipeline é implementado.
1. Se você deseja criar o pipeline em uma organização diferente (org), mude sua organização padrão.
É possível criar os pipelines em organizações às quais você pertence.
1. Se você desejar criar o pipeline em um espaço diferente, mude seu espaço padrão. É possível criar o pipeline em um espaço que está em sua organização.
1. Se você não tiver uma cadeia de ferramentas, será criada uma com um nome padrão. Se você desejar usar um nome diferente para a cadeia de ferramentas, mude o nome. Com a cadeia de ferramentas, é possível ampliar os recursos de seu pipeline por meio da integração com outras ferramentas e serviços. Para obter mais informações sobre cadeias de ferramentas, veja [Criando cadeias de ferramentas](/docs/services/ContinuousDelivery/toolchains_working.html){: new_window}.

 **Dica**: os pipelines e as cadeias de ferramentas pertencem às
organizações (orgs). Se você pertencer a uma organização que tenha cadeias de ferramentas, será possível ser incluído na lista de controle de acesso de qualquer uma de suas cadeias de ferramentas associadas. Depois de ser incluído na lista de controle de acesso para uma cadeia de ferramentas, será possível visualizar essa cadeia de ferramentas e quaisquer pipelines associados, mesmo se você não os tiver criado. Se privilégios de administrador tiverem sido concedidos a você, também será possível modificar e excluir a cadeia de ferramentas. Para obter mais informações sobre o controle de acesso de cadeias de ferramentas, veja [Gerenciando o acesso](/docs/services/ContinuousDelivery/toolchains_using.html#managing_access){: new_window}.

1. Selecione a cadeia de ferramentas que deseja usar ou digite um nome para a nova cadeia de ferramentas que deseja criar.
1. Selecione seu provedor Git.

 **Dica**: se você não estiver autorizado o {{site.data.keyword.Bluemix_notm}} a acessar o GitHub, será solicitado a clicar em **Autorizar** para acessar o website do GitHub. Se você não
tiver uma sessão GitHub ativa, será solicitado que efetue login. Clique em **Autorizar aplicativo** para permitir que o {{site.data.keyword.Bluemix_notm}} acesse sua conta GitHub. Se
você tiver uma sessão GitHub ativa, mas não tiver inserido sua senha recentemente, poderá ser solicitado que insira sua senha GitHub para
confirmar.

   * Se você tiver um repositório e desejar usá-lo, para o tipo de repositório, selecione **Link**. Procure o local do repositório e
selecione-o na lista de repositórios disponíveis.

   * Se desejar criar um repositório vazio, para o tipo de repositório, selecione **Novo**. Digite um nome para o repositório.

   * Se desejar criar um clone de um repositório, para o tipo de repositório, selecione **Copiar**. Procure o local do repositório e
selecione-o na lista de repositórios disponíveis.

   * Se desejar bifurcar um repositório para que possa contribuir com mudanças por meio de solicitações pull, selecione **Bifurcar**. Procure o local do repositório e
selecione-o na lista de repositórios disponíveis.

1. Selecione um repositório ou insira uma URL de repositório.
1. Clique em **Criar**. O pipeline é criado, configurado e exibido na página Visão Geral da cadeia de ferramentas. ![Placa do Pipeline](images/cd_pipeline.png)
1. Se você criou um pipeline em uma cadeia de ferramentas que contenha um pipeline composto, o novo pipeline será incluído no pipeline composto. Modifique o plano de implementação para incluir tarefas de implementação para o novo pipeline. Veja [Criando tarefas do Delivery Pipeline](/docs/services/ContinuousDelivery/pipeline_deployment_plan.html#tasks_pipelineCD){: new_window}.

Para criar um [pipeline vazio ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/devops/pipelines/dashboard/create){: new_window} sem nenhum estágio pré-configurado:

1. Clique em **Customizado**.
1. Se você desejar usar um nome diferente para o pipeline, mude o nome padrão.
1. Se você desejar criar o pipeline em uma organização diferente, mude sua organização padrão. É possível criar pipelines em organizações às quais você pertence.
1. Se você desejar criar o pipeline em um espaço diferente, mude seu espaço padrão. É possível criar o pipeline em um espaço que está em sua organização.
1. Se você não tiver uma cadeia de ferramentas, será criada uma com um nome padrão. Se você desejar usar um nome diferente para a cadeia de ferramentas, mude o nome. Com a cadeia de ferramentas, é possível ampliar os recursos de seu pipeline por meio da integração com outras ferramentas e serviços.
1. Selecione a cadeia de ferramentas que deseja usar ou digite um nome para a nova cadeia de ferramentas que deseja criar.
1. Clique em **Criar**. Um pipeline vazio é criado e representado como um cartão na página Visão geral da cadeia de ferramentas.

No {{site.data.keyword.deliverypipeline}}, mude a configuração, verifique o status das construções, o app implementado e as implementações recentes; veja os logs mais recentes e os detalhes da implementação ou exclua seu pipeline.

## Fazer um tutorial: {{site.data.keyword.deliverypipeline}}
{: #pipeline-tutorial}

Consulte este tutorial no [IBM&reg; Cloud Garage Method ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/garage){:new_window}:
  * [Criar um pipeline ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/garage/tutorials/tutorial_first_pipeline?task=1){:new_window}
