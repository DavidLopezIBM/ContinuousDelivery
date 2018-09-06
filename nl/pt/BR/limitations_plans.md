---

copyright:
  years: 2016, 2018
lastupdated: "2018-7-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Limitações e uso do plano
{: #limitations_usage}

O uso do {{site.data.keyword.contdelivery_full}} está limitado a operações de construção, implementação, teste e em andamento de aplicativos na plataforma do {{site.data.keyword.Bluemix_notm}} ou em outras ofertas de plataforma como serviço ou infraestrutura como serviço compatíveis.

## Usuários autorizados
{: #authorized_users}

Os planos de serviço do {{site.data.keyword.contdelivery_short}} são definidos e
precificados com base no número de usuários autorizados de uma instância de serviço. Quem contribui para um
esforço deve ser contado como um usuário autorizado, incluindo:

 * Os usuários que interagem com problemas, conselhos de problemas, código-fonte ou outros artefatos em
um repositório do {{site.data.keyword.gitrepos}}.
 * Os usuários que manipulam, acionam (seja diretamente na UI ou indiretamente confirmando em um
repositório) ou visualizam o status de um pipeline de entrega.
 * Os usuários que interagem com o Eclipse Orion {{site.data.keyword.webide}}.
 
### Como os usuários são contados para instâncias do {{site.data.keyword.contdelivery_short}} em organizações?

Os usuários autorizados são contados observando todos os usuários na organização do Cloud (org) que contém
o serviço do {{site.data.keyword.contdelivery_short}}. 

Para visualizar a lista de usuários em sua organização em um ambiente do {{site.data.keyword.Bluemix_notm}} Public, na barra de menus, clique em **Gerenciar > Conta > Organizações do Cloud Foundry**.

Para visualizar a lista de usuários em sua organização em um ambiente do {{site.data.keyword.Bluemix_notm}} Dedicated, na barra de menus, clique em **Conta > Gerenciar organizações**.

Também é possível visualizar todas as instâncias do serviço {{site.data.keyword.contdelivery_short}} em sua conta e o número de usuários que são relatados com relação a cada instância em um ambiente do {{site.data.keyword.Bluemix_notm}} Public.

1. Na barra de menus, clique em **Gerenciar > Faturamento e uso > Uso **.
2. Clique em **Painel de uso**.
3. No menu Conta, clique em **Organizações do Cloud Foundry**.
4. Clique na organização para a qual você deseja visualizar informações de uso.

Para visualizar todas as instâncias do serviço {{site.data.keyword.contdelivery_short}} em sua conta e o número de usuários que são relatados com relação a cada instância em um ambiente do {{site.data.keyword.Bluemix_notm}} Dedicated:

1. Na barra de menus, clique em **Conta > Gerenciar organizações**.
2. Clique em **Painel de uso**.

### Como os usuários são contados para instâncias do {{site.data.keyword.contdelivery_short}} em grupos de recursos?

Os usuários autorizados são contados examinando a lista de usuários na guia Gerenciar dentro da instância do serviço {{site.data.keyword.contdelivery_short}}. 

Para visualizar a lista de usuários autorizados, abra o painel da instância de serviço e clique na guia Gerenciar.

Também é possível visualizar todas as instâncias do
serviço do {{site.data.keyword.contdelivery_short}}
em sua conta e o número de usuários que são relatados em cada instância.

1. Na barra de menus, clique em **Gerenciar > Faturamento e uso > Uso **.
2. Clique em **Painel de uso**.
3. No menu Conta, clique em **Grupos de recursos**.
4. Clique no grupo de recursos para o qual você deseja visualizar informações de uso.

### O que acontece quando você excede os limites de seu plano de serviço? 

Alguns planos de serviços podem ter outras limitações, como o número de tarefas do Delivery Pipeline que
podem ser executadas ou o consumo de armazenamento. Para obter mais informações, consulte a descrição do plano
no catálogo. Se quaisquer limitações do plano forem excedidas em um período de faturamento, o serviço poderá
ser suspenso. Por exemplo, as tarefas do Delivery Pipeline podem não ser executadas para o restante do período
de faturamento.

## Uso do Delivery Pipeline
{: #pipeline_usage}

Os comportamentos de uso aceitáveis incluem, mas não estão limitados a estes comportamentos:

* A compilação e o conjunto de artefatos para linguagens de programação suportadas
* A implementação automatizada de artefatos de aplicativo, configurações e recursos ou serviços de suporte
* Teste, validação e outro comportamento gerado pelo evento de desenvolvimento que é acionado como resultado de um processo de desenvolvimento

Os comportamentos de uso que não são permitidos incluem, mas não estão limitados a estes comportamentos:

* O uso de tarefas ou trabalhadores de pipeline para comportamentos de cálculo geral, como mineração de Bitcoin, ataques de negação de serviço distribuídos e comportamento malicioso ou ofensivo para outros clientes ou usuários dentro da plataforma IBM Cloud ou usuários gerais da Internet
* O uso no processo de desenvolvimento normal para sites ou serviços que promovem discurso de ódio ou outras atividades que violam as IBM Business Conduct Guidelines
* O uso de comportamento gerado pelo evento para intrusão maliciosa ou ataques contra o {{site.data.keyword.Bluemix_notm}} ou outros sites

A critério da IBM, os usuários que violam os comportamentos de uso aceitáveis dos serviços {{site.data.keyword.contdelivery_short}} ou as [IBM Business Conduct Guidelines ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/investor/governance/business-conduct-guidelines.html){: new_window} podem ser desativados sem aviso. A critério da IBM, alguns serviços poderão ser restaurados se os usuários corrigirem seus comportamentos de uso depois de serem notificados da ação ofensiva. Caso contrário, as contas poderão ser suspensas ou finalizadas.

## Limitações do Git Repos and Issue Tracking
{: #git_limitations}

O {{site.data.keyword.gitrepos}} é construído no GitLab Community Edition e hospedado pela IBM no {{site.data.keyword.Bluemix_notm}}, no entanto, algumas opções do GitLab não estão disponíveis:

 * Como o {{site.data.keyword.deliverypipeline}} fornece a integração contínua e entrega contínua para o {{site.data.keyword.Bluemix_notm}}, os recursos de integração contínua no GitLab não são suportados.
 * As funções de administração do GitLab não estão disponíveis porque elas são gerenciadas pela IBM.
 * O {{site.data.keyword.gitrepos}} pode não ser totalmente acessível.

## Informações sobre o usuário e conteúdo do Git Repos and Issue Tracking
{: #git_projects}

Três tipos de projetos do {{site.data.keyword.gitrepos}} estão disponíveis:

  1. Os projetos públicos são visíveis para todos os visitantes do site. O conteúdo em um projeto público está visível para todos que acessam o {{site.data.keyword.contdelivery_short}}, mesmo se eles não forem convidados para o projeto.
  2. Os projetos privados são visíveis somente para usuários selecionados. Para obter detalhes sobre como conceder acesso de usuário a um projeto, veja [Usuários do projeto ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://git.ng.bluemix.net/help/workflow/add-user/add-user.md){: new_window}.
  3. Os projetos internos são visíveis para todos os usuários com login efetuado. Qualquer usuário que tenha uma conta do {{site.data.keyword.Bluemix_notm}} pode visualizar esses projetos.

É possível modificar o tipo de projeto nas configurações do projeto. Para obter mais informações, veja [Como mudar a visibilidade do projeto ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://git.ng.bluemix.net/help/public_access/public_access#how-to-change-project-visibility){: new_window}.

Quando você usa o {{site.data.keyword.gitrepos}}, o conteúdo contribuído para um projeto é licenciado sob os termos que são especificados nesse projeto. Ao criar um projeto, inclua um arquivo que descreva a licença que se aplica ao conteúdo. Quando você contribui para um projeto, seu nome e o endereço de e-mail que está associado às suas confirmações podem ser visíveis para o público. O endereço de e-mail que está associado à sua conta do {{site.data.keyword.Bluemix_notm}} é usado quando você cria confirmações por meio da interface da web do {{site.data.keyword.gitrepos}}.

<!-- ###Privacy with Git Repos and Issue Tracking profiles -->

<!-- A few features of {{site.data.keyword.gitrepos}} require the use of a profile page that publicly displays information that you provide. You give IBM the following permissions: -->

  <!-- a. Make the information in your profile&mdash;such as your name, email, picture, bio, social media links, and user activity&mdash;visible to other users of the service. -->

  <!-- b. Publicly disclose your name and other public information and activities that are associated with your use of the service, or otherwise publicize the fact that you are a user of the service, without any further notice to you. -->

<!-- The email address that is associated with your profile page is derived from your {{site.data.keyword.Bluemix_notm}} account details. To modify the email address that is displayed on your profile page, modify your {{site.data.keyword.Bluemix_notm}} account. -->

<!-- ## Deprecated services
{: #deprecated_services} -->

<!--{{site.data.keyword.trackplan}} and {{site.data.keyword.deliverypipeline}} Classic, which are part of IBM Bluemix {{site.data.keyword.jazzhub_short}} (JazzHub), are being retired. For more information, see [Track & Plan Retirement ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/bluemix/2017/04/track-plan-retirement/){: new_window} and [Delivery Pipeline Retirement ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/bluemix/2017/04/delivery-pipeline-retirement/){: new_window}. -->

<!-- Starting on May 25, no new JazzHub projects can be created. Through automatic rolling upgrades, JazzHub projects will be upgraded to {{site.data.keyword.contdelivery_short}} toolchains. The JazzHub site will be removed from service in early July. For more information about the upgrade, see [Upgrading JazzHub project to Bluemix Continuous Delivery toolchains ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/devops-services/2017/4/18/upgrading-jazzhub-projects-bluemix-continuous-delivery-toolchains/){: new_window} -->
