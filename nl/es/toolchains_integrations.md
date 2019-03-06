---

copyright:
  years: 2015, 2019
lastupdated: "2019-2-15"

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

# Configuración de la integración de herramientas
{: #integrations}

Puede configurar integraciones de herramientas que admitan tareas de desarrollo, despliegue y operaciones mientras crea una cadena de herramientas abierta, o bien puede añadir y configurar integraciones de herramientas para personalizar una cadena de herramientas existente.  
{:shortdesc}

Las integraciones de herramientas que están disponibles para añadirse y configurarse para la cadena de herramientas son distintas en función de si está utilizando cadenas de herramientas en {{site.data.keyword.Bluemix_notm}} Público o {{site.data.keyword.Bluemix_notm}} Dedicado. Si está utilizando cadenas de herramientas en {{site.data.keyword.Bluemix_notm}} Público, las integraciones de herramientas disponibles para usted dependerán de la región de la cadena de herramientas y de la disponibilidad de las integraciones de herramientas en dicha región. Si está utilizando cadenas de herramientas en {{site.data.keyword.Bluemix_notm}} Dedicado, las integraciones de herramientas disponibles para usted dependerán de cómo se haya configurado {{site.data.keyword.contdelivery_full}} en el entorno específico.

|Integración de herramientas |Disponible en {{site.data.keyword.Bluemix_notm}} Público	|Disponible en {{site.data.keyword.Bluemix_notm}} Dedicado (dependiente del entorno)|
|:----------|:------------------------------|:------------------|
|{{site.data.keyword.alertnotificationshort}}		|EE.UU. sur		|No		|
|Artifactory		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|Supervisión de disponibilidad		|EE.UU. sur		|No		|
|Bitbucket		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|No		|
|Gestión de sucesos de nube		|EE.UU. sur		|No		|
|{{site.data.keyword.deliverypipeline}} 		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido	   	|Sí  		|
|{{site.data.keyword.DRA_short}} 		|EE.UU. sur, Alemania, Reino Unido		|No			|
|Eclipse Orion {{site.data.keyword.webide}}		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí			|
|{{site.data.keyword.gitrepos}}	|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|No		|
|GitHub		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|{{site.data.keyword.ghe_short}} dedicado e Issues			|No		|Sí		|
|GitLab		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|No		|
|Jenkins		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|JIRA		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|Nexus			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|Otras herramientas			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|PagerDuty			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|Rational Team Concert			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|Sauce Labs		|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|No		|
|Slack			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
|SonarQube			|EE.UU. sur, EE.UU. este, Alemania, Tokio, Reino Unido		|Sí		|
{: caption="Tabla 1. Integraciones de herramientas disponibles para cadenas de herramientas en {{site.data.keyword.Bluemix_notm}} público y dedicado" caption-side="top"}

Si desea empezar a desarrollar su propio código en {{site.data.keyword.Bluemix_notm}} Público, configure la integración de herramientas GitHub o la integración de herramientas {{site.data.keyword.gitrepos}} antes de configurar el {{site.data.keyword.deliverypipeline}}. Si desea empezar a desarrollar su propio código en {{site.data.keyword.Bluemix_notm}} Dedicado, configure la integración de herramientas {{site.data.keyword.ghe_short}} o la integración de herramientas GitHub antes de configurar el {{site.data.keyword.deliverypipeline}}.
{: tip}


## Configuración de Alert Notification
{: #alertnotification}

{{site.data.keyword.alertnotificationfull}} es una solución híbrida basada en la nube que puede utilizar para centralizar y simplificar la estrategia de notificaciones. Funciona con otras aplicaciones en la nube y locales. Las alertas se reenvían a {{site.data.keyword.alertnotificationshort}} utilizando una API RESTful segura.

Configure {{site.data.keyword.alertnotificationshort}} de modo que reciba notificaciones sobre problemas durante el proceso de DevOps.

### Requisitos previos

1. Si no tiene una cuenta de {{site.data.keyword.alertnotificationshort}}, regístrese para obtener una:

 a. Abra la página [IBM {{site.data.keyword.alertnotificationshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/us-en/marketplace/alert-notification){: new_window} en IBM Marketplace.

 b. Adquiera una suscripción o regístrese para una prueba gratuita de 90 días.

1. Una vez configurada la cuenta de {{site.data.keyword.alertnotificationshort}}, abra [Mi panel de control de IBM ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://myibm.ibm.com/dashboard/){: new_window}.
1. Junto a IBM {{site.data.keyword.alertnotificationshort}}, pulse **Iniciar**.
1. Pulse **Gestionar claves de API** y pulse **Crear clave de API**.
1. En el campo **Crear clave de API**, escriba una descripción.
1. Pulse **Generar**. Se muestra la información de la nueva clave de API, incluido el nombre y la contraseña. Necesita esta información para la configuración de la integración de la herramienta, de modo que mantenga abierta la ventana Nueva clave de API. Por motivos de seguridad, no puede recuperar posteriormente la contraseña de la clave de API.

### Configuración de Alert Notification

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **{{site.data.keyword.alertnotificationshort}}**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **{{site.data.keyword.alertnotificationshort}}**.

1. Escriba el URL para la API de {{site.data.keyword.alertnotificationshort}} que desea utilizar. Encontrará el URL en la página Gestionar claves de API del servicio {{site.data.keyword.alertnotificationshort}}; por ejemplo, `https://ibmnotifybm.mybluemix.net/api/alerts/v1`.
1. Escriba el nombre de la clave de API correspondiente a {{site.data.keyword.alertnotificationshort}}. Encontrará el nombre de clave de API en la ventana Nueva clave de API.
1. Escriba la contraseña que {{site.data.keyword.alertnotificationshort}} ha generado para la clave de API. Encontrará la contraseña de clave de API en la ventana Nueva clave de API.
1. Pulse **Crear integración**.
1. En la cadena de herramientas, pulse **{{site.data.keyword.alertnotificationshort}}**.

### Más información sobre Alert Notification

Para obtener más información sobre {{site.data.keyword.alertnotificationshort}}, consulte el [artículo de IBM {{site.data.keyword.alertnotificationshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/manage/tool_alert_notification/){: new_window} en IBM Cloud Garage Method o realice estas guías de aprendizaje:

  * [Añadir una integración de herramientas a una cadena de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/add-a-tool-integration-to-a-toolchain){:new_window}

  * [Gestionar su aplicación {{site.data.keyword.Bluemix_notm}} utilizando {{site.data.keyword.Bluemix_notm}} Availability Monitoring and Alert Notification ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## Configuración de Artifactory
{: #artifactory}

Configure el gestor de repositorios Artifactory para que guarde los artefactos de compilación en el repositorio de Artifactory (repositorio):

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Artifactory**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Artifactory**.

1. Escriba el URL del repositorio de Artifactory que desea abrir al pulsar la tarjeta Artifactory.
1. Seleccione el tipo de repositorio con el que desea conectar.
1. Si utiliza un registro Artifactory npm, siga estos pasos:

 a. Escriba la dirección de correo electrónico asociada con el registro.

 b. Escriba la señal de autenticación asociada con el registro.

 c. Escriba el URL para el repositorio del release de Artifactory, que es su registro privado en el servidor de Artifactory.

 d. Escriba el URL para el registro de duplicación o público que utiliza para combinar varios registros npm públicos y privados. Por ejemplo, este URL podría ser el URL del registro virtual en el servidor de Artifactory que puede acceder tanto al registro privado como a la memoria caché del registro global de npm.

1. Si utiliza un repositorio Artifactory Maven, siga estos pasos:

 a. Escriba el ID de usuario asociado con el repositorio.

 b. Escriba la contraseña asociada con el repositorio.

 c. Escriba el URL para el repositorio del release de Artifactory, que es su repositorio del release privado del servidor de Artifactory.

 d. Escriba el URL del repositorio de instantáneas de Artifactory, que es el repositorio de instantáneas privado del servidor de Artifactory.

 e. Escriba el URL del repositorio de duplicación o público que utilice para combinar varios repositorios Maven públicos y privados. Por ejemplo, este URL podría ser el URL del repositorio virtual en el servidor de Artifactory que puede acceder tanto al repositorio privado como a la memoria caché del repositorio central de Maven.

1. Pulse **Crear integración**.
1. Pulse la tarjeta correspondiente al repositorio de Artifactory con el que desee trabajar. Se abrirá el sitio web de Artifactory, donde puede ver el contenido del repositorio.
1. Opcional: si utiliza una cadena de herramientas en {{site.data.keyword.Bluemix_notm}} Público y desea crear la app utilizando Artifactory con npm, configure el conducto para añadir un trabajo de compilación de npm. Para obtener instrucciones sobre cómo configurar el trabajo de creación, consulte [Configuración de un trabajo de compilación de npm de Artifactory en el conducto](#config_artifactory_npm).
1. Opcional: si utiliza una cadena de herramientas en {{site.data.keyword.Bluemix_notm}} Público y desea crear la app utilizando Artifactory con Maven, configure el conducto para añadir un trabajo de compilación de Maven. Para obtener instrucciones sobre cómo configurar el trabajo de compilación, consulte [Configuración de un trabajo de compilación de Maven de Artifactory en el conducto](#config_artifactory_maven).

### Configuración de un trabajo de compilación de npm de Artifactory en el conducto
{: #config_artifactory_npm}

Antes de configurar un trabajo de compilación de npm en el conducto, debe disponer de un conducto en funcionamiento que pueda utilizar para crear el repositorio SCM como entrada. También debe configurar Artifactory para la cadena de herramientas. Para obtener instrucciones sobre cómo configurar Artifactory, consulte la sección [Artifactory](#artifactory).

Configure el {{site.data.keyword.deliverypipeline}} para añadir un trabajo de compilación de npm:

1. Cree una etapa y establezca la entrada al repositorio SCM adecuado.
1. En la etapa, añada un trabajo de trabajo de compilación.
1. Configure el trabajo de compilación: ![Trabajo de compilación de npm](images/artifactory_npm_job.png)

  a. Para el tipo de constructor, seleccione **Compilación de NPM**.

  b. Si ha configurado varias instancias de la integración de la herramienta de Artifactory, especifique el nombre de la integración de herramientas de Artifactory para la que desee configurar el trabajo de compilación de npm.

  c. Para el tipo de integración de herramientas, seleccione **Artifactory**.

  d. Para el mandato de compilación, especifique los mandatos para crear el módulo npm o publicarlo en el registro. En este ejemplo se muestran los mandatos para crear el módulo o publicarlo.
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  Encontrará el URL y las credenciales de usuario que ha utilizado para conectar con el registro en los valores de configuración correspondientes a la integración de herramientas de Artifactory.
  {: tip}

  e. Si el trabajo de compilación se publica en el registro de Artifactory y el formato de su versión del módulo de nodo es `x.y.z-SNAPSHOT.w`, marque el recuadro de selección **Incrementar versión del módulo de instantáneas**. El trabajo de compilación actualiza automáticamente la versión del módulo antes de que el trabajo publique en el registro de Artifactory. El trabajo selecciona la versión más alta del módulo a partir del registro de npm y el archivo `package.json` local e incrementa la versión del módulo utilizando semver. El trabajo de compilación no envía los cambios al repositorio SCM.

1. Pulse **GUARDAR**. Siempre que se ejecute el conducto, este trabajo de compilación utilizará la información de configuración de la integración de herramientas de Artifactory para conectar con el registro de npm.

### Configuración de un trabajo de compilación de Maven de Artifactory en el conducto
{: #config_artifactory_maven}

Antes de configurar un trabajo de compilación de Maven en el conducto, necesita un conducto en funcionamiento que pueda utilizar para crear el repositorio SCM como entrada y debe configurar Artifactory para su cadena de herramientas. Para obtener instrucciones sobre cómo configurar Artifactory, consulte la sección [Artifactory](#artifactory).

Configure {{site.data.keyword.deliverypipeline}} para añadir un trabajo de compilación de Maven:

1. Cree una etapa y establezca la entrada al repositorio SCM adecuado.
1. En la etapa, añada un trabajo de trabajo de compilación.
1. Configure el trabajo de compilación: ![Trabajo de compilación de Maven](images/artifactory_maven_job.png)

  a. Para el tipo de constructor, seleccione **Compilación de Maven**.

  b. Si ha configurado varias instancias de la integración de herramientas de Artifactory, escriba el nombre de la integración de herramientas de Artifactory para la que desea configurar el trabajo de compilación de Maven.

  c. Para el tipo de integración de herramientas, seleccione **Artifactory**.

  d. Para el mandato de compilación, escriba los mandatos para crear el módulo de Maven o publicarlo en el registro de instantáneas. En este ejemplo se muestran los mandatos para crear el módulo o publicarlo en un registro de instantáneas.
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  Encontrará el URL y las credenciales de usuario que ha utilizado para conectar con el registro en los valores de configuración correspondientes a la integración de herramientas de Artifactory.
  {: tip}

1. Pulse **GUARDAR**. Siempre que se ejecute el conducto, este trabajo de compilación utilizará la información de configuración de la integración de herramientas de Artifactory para conectar con el registro de Maven.

### Más información sobre Artifactory

Para obtener más información sobre Artifactory, consulte el [artículo de Artifactory ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/deliver/tool_artifactory/){: new_window} en el IBM Cloud Garage Method.


## Adición de supervisión de disponibilidad
{: #availabilitymonitoring}

{{site.data.keyword.prf_hublong}} aísla problemas, identifica patrones y mejora el rendimiento antes de que los usuarios se vean afectados. Puede probar la app desde ubicaciones de todo el mundo, integrar con conductos de entrega y obtener información sobre cómo optimizar el código continuamente.

Esta integración de herramientas está preconfigurada y no requiere ningún parámetro de configuración. No puede volver a configurar esta integración de herramientas.
{: tip}

Para probar, supervisar y mejorar el estado de la app a medida que la crea, añada la integración de herramientas de {{site.data.keyword.prf_hubshort}}:

1. En el panel de control de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas a la que desea añadir {{site.data.keyword.prf_hubshort}}. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **{{site.data.keyword.prf_hubshort}}**.

1. Pulse **Crear integración**.
1. Pulse **{{site.data.keyword.prf_hubshort}}** para abrir el panel de control de {{site.data.keyword.prf_hubshort}}, seleccione una app y configure la supervisión para la app.

### Más información acerca de Availability Monitoring

Para obtener más información sobre {{site.data.keyword.prf_hubshort}}, consulte el [artículo de {{site.data.keyword.prf_hublong}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/manage/tool_bluemix_availability_monitoring/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje:

  * [Gestionar su aplicación {{site.data.keyword.Bluemix_notm}} utilizando {{site.data.keyword.Bluemix_notm}} Availability Monitoring and Alert Notification ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## Configuración de Bitbucket
{: #bitbucket}

Almacene el código fuente en un repositorio nuevo o existente en bitbucket.org y participe en la codificación social a través de wikis, rastreo de problemas y solicitudes de extracción.

Configure Bitbucket para colaborar con su equipo en código:

1. En el panel de control de DevOps, pulse **Cadenas de herramientas**. Pulse la página Cadenas de herramientas a la que desea añadir Bitbucket. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Bitbucket**.

   Si está configurando esta integración de herramientas en {{site.data.keyword.Bluemix_notm}} Público y no ha autorizado a {{site.data.keyword.Bluemix_notm}} para que acceda a Bitbucket, pulse **Autorizar** para ir al sitio web de Bitbucket. Si no tiene ninguna sesión de Bitbucket activa, se le solicitará que inicie sesión. Pulse **Otorgar acceso** para permitir que las Cadenas de herramientas de {{site.data.keyword.Bluemix_notm}} accedan a las siguientes partes de la cuenta de Bitbucket:
   
   * **Leer la información de su cuenta**. Obtener información básica de usuario para llenar la interfaz de usuario.
   
   * **Leer y modificar los problemas de los repositorios**. Permitir que {{site.data.keyword.contdelivery_short}} actualice los problemas para indicar cuándo despliega el conducto confirmaciones que se adjuntan a dichos problemas. 
   
   * **Leer los valores del proyecto de su equipo y leer los repositorios contenidos en los proyectos de su equipo**. Permitir que {{site.data.keyword.contdelivery_short}} se integre con los repositorios que son propiedad de los equipos.
   
   * **Leer y modificar los repositorios y sus solicitudes de extracción**. Permitir que {{site.data.keyword.contdelivery_short}} envíe código de ejemplo a los repositorios, cuando los usuarios soliciten el código.
   
   * **Administrar los repositorios**. Permitir que {{site.data.keyword.contdelivery_short}} cree nuevos repositorios, cuando lo soliciten los usuarios.
   
   * **Leer la información de la pertenencia al equipo**. Permitir que {{site.data.keyword.contdelivery_short}} muestre una lista de sus equipos en el menú **Propietario** que se visualiza al crear un nuevo repositorio.
   
   * **Leer y modificar los webhooks de sus repositorios**. Permitir que el conducto active las compilaciones cuando las confirmaciones se envíen a un repositorio.
   {: tip}
   
   Si tiene una sesión de Bitbucket activa pero no ha especificado la contraseña recientemente, es posible que se le solicite que especifique su contraseña de Bitbucket para confirmar.

1. Pulse el servidor de Bitbucket que desee utilizar.
1. Si tiene un repositorio de Bitbucket que desea utilizar, escriba el URL para el repositorio. Para el tipo de repositorio, pulse **Existente**.
1. Si desea utilizar un repositorio nuevo de Bitbucket, escriba un nombre para el repositorio, escriba el URL del repositorio que está clonando o bifurcando y seleccione el tipo de repositorio:

 a. Para crear un repositorio vacío, pulse **Nuevo**.

 b. Para crear una copia de un repositorio, pulse **Clonar**.

 c. Para bifurcar un repositorio para que pueda aportar cambios a través de solicitudes de extracción, pulse **Bifurcar**.

1. Para crear un repositorio privado en el servidor, marque el recuadro de selección **Convertir este repositorio en privado**.
1. Para utilizar Bitbucket Issues para realizar un seguimiento de los problemas, seleccione el recuadro de selección **Habilitar Bitbucket Issues**.
1. Para realizar un seguimiento del despliegue de cambios en el código mediante la creación de etiquetas y comentarios en las confirmaciones, y etiquetas y comentarios en los problemas a los que hacen referencia las confirmaciones, marque el recuadro de selección **Hacer un seguimiento del despliegue cambios de código**. Para obtener más información, consulte [Seguimiento de dónde se despliega el código con cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}.
1. Pulse **Crear integración**.
1. En la cadena de herramientas, pulse la tarjeta correspondiente al repositorio Bitbucket con el que desee trabajar. Se abrirá el sitio web de Bitbucket, donde puede ver el contenido del repositorio.
1. Si ha habilitado Bitbucket Issues, pulse **Bitbucket Issues** para abrirlo. Puede utilizar esta instancia de Bitbucket Issues para toda la cadena de herramientas, aunque la cadena de herramientas contenga varios repositorios Bitbucket.    

Si no tiene privilegios de propietario o maestro para el repositorio al que está enlazando, la integración estará limitada porque no puede utilizar un webhook. Los webhooks se necesitan para ejecutar automáticamente un conducto cuando se envía una confirmación al repositorio. Sin un webhook, debe iniciar los conductos manualmente.
{: tip}

### Más información sobre Bitbucket

Para obtener más información sobre Bitbucket, consulte el [artículo de Bitbucket ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_bitbucket/){: new_window} en el IBM Cloud Garage Method.


## Adición de Cloud Event Management
{: #cloudeventmanagement}

{{site.data.keyword.evtmgt_full}} proporciona una vista consolidada de los problemas que se producen con los servicios, las aplicaciones y la infraestructura. Puede configurar un sistema de gestión de incidentes en tiempo real para resolver los problemas de forma más eficiente.

Esta integración de herramientas está preconfigurada y no requiere ningún parámetro de configuración. No puede volverla a configurar.
{: tip}

Para ayudar al equipo de DevOps a alcanzar un estado operativo fiable, calidad de servicio y mejora continua de objetivos, añada la función de gestión de sucesos de nube (Cloud Event Management) a su cadena de herramientas:

1. En el panel de control de DevOps, pulse **Cadenas de herramientas**. Pulse la página Cadenas de herramientas a la que desea añadir gestión de sucesos de nube. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Cloud Event Management**.

1. Pulse **Crear integración**.
1. En la cadena de herramientas, pulse cualquiera de las siguientes tarjetas de herramientas:

 * **Gestión de sucesos de nube** para empezar a trabajar con la gestión de sucesos de nube.

 * **{{site.data.keyword.alertnotificationshort}}** para crear políticas que determinen cuándo recibirán los usuarios notificaciones de incidencias.

 * **Automatización de Runbook** para gestionar el catálogo de runbooks en la herramienta Cloud Event Management.

### Más información sobre Cloud Event Management

Para obtener más información sobre Cloud Event Management, consulte el [artículo Cloud Event Management ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/manage/tool_cloud_event_mgt/){: new_window} en el IBM Cloud Garage Method.


## Configuración de Delivery Pipeline
{: #deliverypipeline}

{{site.data.keyword.deliverypipeline}} automatiza el despliegue continuado de los proyectos a través de secuencias de fases que recuperan entradas y ejecutan trabajos, como compilaciones, pruebas y despliegues.

Configure {{site.data.keyword.deliverypipeline}} para automatizar la creación, las pruebas y el despliegue automáticos de sus apps:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **{{site.data.keyword.deliverypipeline}}**. En función de la plantilla que utilice, los campos disponibles serán distintos. Revise los valores del campo predeterminado y, si es necesario, realice cambios.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **{{site.data.keyword.deliverypipeline}}**.

1. Especifique un nombre para el nuevo conducto.
1. Si tiene previsto utilizar el conducto para desplegar una interfaz de usuario, seleccione el recuadro de selección **Mostrar apps en el menú VER APP**. Todas las apps creadas por el conducto se muestran en la lista **Ver app** de la página de visión general de la cadena de herramientas.
1. Pulse **Crear integración** para añadir el {{site.data.keyword.deliverypipeline}} a la cadena de herramientas.
1. Pulse **{{site.data.keyword.deliverypipeline}}** para ver el conducto y configurarlo. Para obtener información básica sobre cómo configurar un conducto, consulte [Creación y despliegue de conductos](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-deliverypipeline_build_deploy){: new_window}.

  Si desea que el conducto se ejecute automáticamente cuando se envíe una confirmación a su repositorio GitHub, {{site.data.keyword.ghe_short}} o Git (repo), siga estos pasos:

   a. Configure GitHub, {{site.data.keyword.ghe_short}} o {{site.data.keyword.gitrepos}} para la cadena de herramientas antes de definir las fases del conducto. Las etapas del conducto necesitan los URL Git para los repositorios. Cada etapa de conducto puede hacer referencia a un único repositorio de GitHub, {{site.data.keyword.ghe_short}} o Git que esté asociado con la cadena de herramientas. Para obtener instrucciones sobre cómo configurar GitHub, consulte la sección [GitHub](#github). Para obtener instrucciones sobre cómo configurar {{site.data.keyword.ghe_short}}, consulte [Iniciación a {{site.data.keyword.ghe_long}}](/docs/services/ghededicated?topic=ghededicated-gheded_getting_started){: new_window}. Para obtener instrucciones sobre cómo configurar {{site.data.keyword.gitrepos}}, consulte la sección [{{site.data.keyword.gitrepos}}](#gitbluemix).

   b. Utilice un webhook. Sin un webhook, solo podrá ejecutar los conductos manualmente. Para utilizar un webhook cuando enlaza con un repositorio GitHub o {{site.data.keyword.ghe_short}}, necesita privilegios de administración. Para enlazar un repositorio de {{site.data.keyword.gitrepos}}, necesita privilegios de maestro o de propietario.

1. Opcional: si utiliza una cadena de herramientas en {{site.data.keyword.Bluemix_notm}} Público y desea que Sauce Labs ejecute pruebas en la app, configure el {{site.data.keyword.deliverypipeline}} para añadir el trabajo de pruebas Sauce Labs. Para obtener instrucciones sobre cómo configurar el trabajo de pruebas, consulte [Configuración de un trabajo de pruebas Sauce Labs en el conducto](#config_saucelabs).

### Configuración de un trabajo de pruebas Sauce Labs en el conducto
{: #config_saucelabs}

Antes de configurar un trabajo de pruebas Sauce Labs en el conducto, necesita un conducto de trabajo que incluya fases para crear y desplegar la app. También debe configurar Sauce Labs para la cadena de herramientas. Para obtener instrucciones sobre cómo configurar Sauce Labs, consulte la sección [Sauce Labs](#saucelabs).

Configure el {{site.data.keyword.deliverypipeline}} para añadir un trabajo de pruebas Sauce Labs:

1. Si no tiene ninguna etapa que despliegue una versión de pruebas de su app, cree una.
1. En la etapa, añada un trabajo de prueba después del trabajo de despliegue. Disponer de estos trabajos en la misma etapa permite que accedan al mismo conjunto de propiedades del entorno.   
  ![Trabajo de prueba](images/toolchain_test_job.png)

1. Configurar la etapa. En el separador **PROPIEDADES DE ENTORNO**, cree la propiedad CF_APP_NAME.

  El nombre de usuario de Sauce Labs y la clave de acceso están disponibles en el script de trabajo de prueba como las variables de entorno SAUCE_USERNAME y SAUCE_ACCESS_KEY. Cuando escriba sus pruebas, debe utilizar estas variables de entorno para autenticarse con Sauce Labs.
  {: tip}

1. Configure el trabajo de despliegue. En el campo **Desplegar script**, incluya este mandato: `export CF_APP_NAME="$CF_APP"`. Este mandato exporta el nombre de la app como propiedad del entorno.
1. Configure el trabajo de prueba. 

  Los campos **Instancia de servicio**, **Destino**, **Organización** y **Espacio** se rellenan con el nombre de usuario de Sauce Labs, la región, la organización y el espacio que se está utilizando.
  {: tip}

  a. Para el tipo de probador, seleccione **Sauce Labs**.

  b. Para la instancia de servicio, seleccione el nombre de usuario de Sauce Labs que ha utilizado al configurar Sauce Labs para la cadena de herramientas.

   Para ver el nombre de usuario y la clave de acceso que ha utilizado al configurar Sauce Labs para su cadena de herramientas, pulse **Configurar**.
   {: tip}

  c. En el campo **Probar mandato de ejecución**, especifique los mandatos que instalan las dependencias necesarias para las pruebas y, a continuación, ejecute las pruebas. Por ejemplo, para una app Node.js, puede introducir estos mandatos:
     ```
     npm install
     node_modules/grunt-cli/bin/grunt test:sauce:parallel
     ```

    d. Si desea ver los informes de las pruebas en los registros del trabajo de prueba, seleccione el recuadro de selección **Habilitar informe de prueba** y establezca el valor de Probar patrón de archivo de resultado en `test/*.xml`.

1. Pulse **GUARDAR**. Siempre que se ejecute su conducto, se ejecutarán las pruebas de Sauce Labs.

### Más información acerca de Delivery Pipeline

Para obtener más información sobre {{site.data.keyword.deliverypipeline}}, consulte [Cómo trabajar con conductos](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-pipeline-working){: new_window} y el [artículo de Delivery Pipeline ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/deliver/tool_delivery_pipeline/){: new_window} en IBM Cloud Garage Method o realice estas guías de aprendizaje:

  * [Crear un conducto ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/create-a-pipeline){:new_window}

  * [Cree y utilice su primera cadena de herramientas utilizando la cadena de herramientas "Desarrollar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## Adición de DevOps Insights
{: #dra}

{{site.data.keyword.DRA_full}} recopila y analiza los resultados de las pruebas de unidad, de las pruebas funcionales y de las herramientas de cobertura de código para determinar si el código cumple los criterios predefinidos en las puertas especificadas del proceso de despliegue. Si el código no cumple o excede los criterios, el despliegue se detiene para evitar la exposición a riesgos. Puede utilizar {{site.data.keyword.DRA_short}} como red de seguridad para el entorno de entrega continuada o como método para implementar y mejorar los estándares de calidad.

 Esta integración de herramientas solo está disponible en {{site.data.keyword.Bluemix_notm}} público. Está preconfigurada y no requiere ningún parámetro de configuración. No puede volver a configurar esta integración de herramientas.
 {: tip}

Añada {{site.data.keyword.DRA_short}} para mantener y mejorar la calidad de su código en {{site.data.keyword.Bluemix_notm}} supervisando las implementaciones para identificar los riesgos antes de distribuir la app.

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **{{site.data.keyword.DRA_short}}**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **{{site.data.keyword.DRA_short}}**.

1. Pulse **Crear integración**.
1. Pulse **{{site.data.keyword.DRA_short}}** y, a continuación, complete los primeros pasos: crear criterios, conectar los criterios al conducto y ejecutar el conducto.

### Más información sobre DevOps Insights

Para obtener más información sobre {{site.data.keyword.DRA_short}}, consulte el [artículo de {{site.data.keyword.DRA_short}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/learn/tool_devops_insights/){: new_window} en el IBM Cloud Garage Method o realice estas guías de aprendizaje:

  * [Utilice la cadena de herramientas "Desarrollar y probar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [Garantice la calidad de los despliegues mediante la cadena de herramientas "Deployment Risk Analytics con GitHub y Jenkins" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}


## Adición del IDE Eclipse Orion Web
{: #webide}

Eclipse Orion {{site.data.keyword.webide}} es un entorno integrado basado en web en el que puede crear, editar, ejecutar, depurar y controlar las tareas de control del código fuente. Puede pasar sin problemas de editar a ejecutar, enviar y desplegar.

 Esta integración de herramientas está preconfigurada. No es necesario configurar ningún parámetro y tampoco es posible modificar la configuración existente.
 {: tip}

Para completar las tareas de control del código fuente, añada la integración de herramientas Eclipse Orion {{site.data.keyword.webide}}:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Eclipse Orion {{site.data.keyword.webide}}**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Eclipse Orion {{site.data.keyword.webide}}**.

1. Pulse **Crear integración**.
1. Pulse **Eclipse Orion {{site.data.keyword.webide}}**. El espacio de trabajo ya contiene los repositorios de GitHub o {{site.data.keyword.ghe_short}}. Los repositorios que están asociados a la cadena de herramientas actual aparecen resaltados.

### Más información sobre el Eclipse Orion Web IDE

Para obtener más información sobre el {{site.data.keyword.webide}} de Eclipse Orión, consulte [Edición de código con Eclipse Orion {{site.data.keyword.webide}}](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-web_ide). También puede leer el artículo [Eclipse Orion {{site.data.keyword.webide}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_eclipse_orion_web_ide/){: new_window} en IBM Cloud Garage Method. Realice estas guías de aprendizaje para probar el uso de Eclipse Orion {{site.data.keyword.webide}}:

  * [Cree y utilice su primera cadena de herramientas utilizando la cadena de herramientas "Desarrollar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}


## Configuración de Git Repos and Issue Tracking
{: #gitbluemix}

La integración de la herramienta {{site.data.keyword.gitrepos}} se basa en GitLab Community Edition, que es un servicio de alojamiento basado en web para repositorios Git. Puede tener copias locales y remotas de sus repositorios. Para obtener más información, consulte [{{site.data.keyword.gitrepos}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://git.ng.bluemix.net/help){:new_window}.

Si configura {{site.data.keyword.gitrepos}} mientras crea la cadena de herramientas, siga estos pasos:    

1. En la sección Integraciones configurables, pulse **Git Repos and Issue Tracking**.
1. Revise las ubicaciones de destino predeterminadas para el repositorio Git. Dichos repositorios se clonan a partir del repositorio de ejemplo. Si es necesario, cambie el nombre de los repositorios de destino.

Si tiene una cadena de herramientas y desea migrar un repositorio Git de la cadena de herramientas a {{site.data.keyword.gitrepos}}, siga estos pasos:

Estas instrucciones se aplican a las cadenas de herramientas que ya contienen el repositorio Git que desea migrar a {{site.data.keyword.gitrepos}}. Para obtener información sobre la adición de distintos tipos de repositorios Git a la cadena de herramientas, consulte las secciones [Configuración de](#github), [Configuración de GitHub Enterprise and Issues en {{site.data.keyword.Bluemix_notm}} dedicado](#configghe) y [Configuración de GitLab](#gitlab).
{: tip}

1. En el panel de control de DevOps, en la página Cadenas de herramientas, pulse sobre la cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.
1. Pulse **Añadir una herramienta**.
1. En la sección Integraciones de herramientas, pulse **Git Repos and Issue Tracking**.
1. Para crear una copia del repositorio Git, para el tipo de repositorio, pulse **Clonar**. Escriba un nuevo nombre de repositorio y el URL del repositorio de origen.
1. Si desea utilizar la aplicación Issues para realizar un seguimiento de los problemas, marque el recuadro de selección **Habilitar Issues**.
1. Si desea realizar un seguimiento del despliegue de cambios en el código mediante la creación de etiquetas y comentarios en las confirmaciones, y etiquetas y comentarios en los problemas a los que hacen referencia las confirmaciones, marque el recuadro de selección **Hacer un seguimiento del despliegue cambios de código**. Para obtener más información, consulte [Seguimiento de dónde se despliega el código con cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}.
1. Pulse **Crear integración**.

Después de clonar el repositorio Git, puede eliminarlo de la cadena de herramientas.
{: tip}

Si tiene una cadena de herramientas y le está añadiendo {{site.data.keyword.gitrepos}}, siga estos pasos:    

1. En el panel de control de DevOps, en la página Cadenas de herramientas, pulse sobre la cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.
1. Pulse **Añadir una herramienta**.
1. En la sección Integraciones de herramientas, pulse **Git Repos and Issue Tracking**.
1. Seleccione un tipo de repositorio:     

  a. Para crear un repositorio vacío, para el tipo de repositorio, pulse **Nuevo** y escriba un nombre de repositorio.    
  b. Para bifurcar un repositorio Git para que pueda aportar cambios a través de solicitudes de fusión, para el tipo de repositorio, pulse **Bifurcar**. Escriba el URL del repositorio de origen.    
  c. Para crear una copia de un repositorio Git, para el tipo de repositorio, pulse **Clonar**. Escriba un nuevo nombre de repositorio y el URL del repositorio de origen.     
  d. Si tiene un repositorio Git y desea utilizarlo, para el tipo de repositorio, pulse **Existente**. Escriba el URL.    

1. Si desea utilizar la aplicación Issues para realizar un seguimiento de los problemas, marque el recuadro de selección **Habilitar Issues**.
1. Si desea realizar un seguimiento del despliegue de cambios en el código mediante la creación de etiquetas y comentarios en las confirmaciones, y etiquetas y comentarios en los problemas a los que hacen referencia las confirmaciones, marque el recuadro de selección **Hacer un seguimiento del despliegue cambios de código**. Para obtener más información, consulte [Seguimiento de dónde se despliega el código con cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}.
1. Pulse **Crear integración**.
1. Pulse la tarjeta correspondiente al repositorio Git con el que desee trabajar. Se abrirá la página de visión general del proyecto.    

Si no tiene privilegios de Maestro o de Propietario sobre el repositorio con el que va a enlazar, la integración estará limitada porque no podrá utilizar un webhook. Los webhooks se necesitan para ejecutar automáticamente un conducto cuando se envía una confirmación al repositorio. Sin un webhook, debe iniciar los conductos manualmente.
{: tip}

### Más información sobre Git Repos and Issue Tracking

Para obtener más información sobre {{site.data.keyword.gitrepos}}, consulte el [artículo {{site.data.keyword.gitrepos}}: codificación social organizada por IBM ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_git_repos_and_issue_tracking/){: new_window} en IBM Cloud Garage Method o realice esta guía de aprendizaje:

  * [Cree y utilice su primera cadena de herramientas utilizando la cadena de herramientas "Desarrollar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## Configuración de GitHub
{: #github}

GitHub es un servicio de alojamiento basado en web para repositorios Git. Puede tener copias locales y remotas de sus repositorios, lo que facilita la colaboración.

{{site.data.keyword.ghe_short}} es un servicio de alojamiento basado en web para repositorios Git.

GitHub
Issues es una herramienta de seguimiento que mantiene todo su trabajo y sus planificaciones en un mismo lugar. Está integrado con el repositorio de desarrollo de modo que pueda centrarse en las tareas importantes.

Puede configurar GitHub como una integración de herramientas de la cadena de herramientas para que pueda gestionar el código fuente en un repositorio nuevo o existente en GitHub.com o en la instancia de {{site.data.keyword.ghe_short}} de su empresa. Entre en la codificación social a través de wikis, seguimiento de problemas y solicitudes de extracción.

Si configura la integración de esta herramienta mientras crea la cadena de herramientas, siga estos pasos:

1. Si está almacenando el código fuente en un repositorio GitHub, en la sección Integraciones configurables, pulse **GitHub**. Si está configurando esta integración de herramientas en {{site.data.keyword.Bluemix_notm}} Público y no ha autorizado a {{site.data.keyword.Bluemix_notm}} para que acceda a GitHub, pulse **Autorizar** para ir al sitio web de GitHub. Si no tiene ninguna sesión de GitHub activa, se le solicitará que inicie sesión. Pulse **Autorizar aplicación** para permitir que {{site.data.keyword.Bluemix_notm}} acceda a su cuenta de GitHub. Si tiene una sesión de GitHub activa pero no ha especificado la contraseña recientemente, es posible que se le solicite que especifique su contraseña de GitHub para confirmar.
1. Si está utilizando un repositorio en su propio servidor de {{site.data.keyword.ghe_short}}, en la sección Integraciones configurables, pulse **Añadir servidor personalizado**.

 La red debe poder acceder al servidor Git de destino desde un entorno de {{site.data.keyword.Bluemix_notm}} dedicado. Si el servidor de GitHub no está disponible en Internet público o el nombre de host no se resuelve en el Servidor de nombres de dominio (DNS) público, [abra una incidencia de soporte](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-cd_support#support-ticket){: new_window}. Puede utilizar la incidencia de soporte para enviar una solicitud para abrir las rutas de red o actualizar los valores de DNS.
 {: important}

 Escriba un título para el servidor de GitHub personalizado y especifique el URL raíz para el servidor. Escriba su señal de acceso personal y pulse **Guardar integración personalizada**.

  Si no tiene una señal de acceso personal, puede crear una:

     a. En cualquier página de GitHub, pulse en el icono de su perfil y, a continuación, pulse **Valores**.

     b. En la barra lateral, pulse **Señales de acceso personales**.

     c. Pulse **Generar señal nueva**.

     d. Añada una descripción para la señal.

     e. Seleccione los recuadros de selección **repo** y **user** para definir el acceso para la señal personal.

     f. Pulse **Generar señal**.

     g. Copie la señal en una ubicación segura o en una app de gestión de contraseñas. Por motivos de seguridad, una vez que abandone la página ya no podrá volver a ver la señal.

1. Revise las ubicaciones de repositorio de destino predeterminadas para los repositorios GitHub. Dichos repositorios se clonan a partir del repositorio de ejemplo. Si es necesario, cambie el nombre de los repositorios de destino.
 ![Ubicaciones de repositorio de destino predeterminadas](images/toolchain_github_config.png)

Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, siga estos pasos:

1. En el panel de control de DevOps, en la página Cadenas de herramientas, pulse sobre la cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.
1. Pulse **Añadir una herramienta**.
1. En la sección Integraciones de herramientas, pulse **GitHub**.
1. Pulse el servidor GitHub que desea utilizar.
1. Si tiene un repositorio GitHub o {{site.data.keyword.ghe_short}} y desea utilizarlo, para el tipo de repositorio, pulse **Existente** y escriba el URL.
1. Si desea utilizar un nuevo repositorio GitHub o {{site.data.keyword.ghe_short}}, escriba un nombre para el repositorio, escriba el URL para el repositorio que está clonando o bifurcando, y seleccione el tipo de repositorio:

 a. Para crear un repositorio vacío, pulse **Nuevo**.

 b. Para crear una copia de un repositorio GitHub o {{site.data.keyword.ghe_short}}, pulse **Clonar**.

 c. Para bifurcar un repositorio GitHub o {{site.data.keyword.ghe_short}} de modo que pueda aportar cambios a través de solicitudes de extracción, pulse **Bifurcar**.

1. Si es un usuario de GitHub.com con una cuenta actualizada, o si ha seleccionado un servidor de {{site.data.keyword.ghe_short}} y desea crear un nuevo repositorio privado en el servidor, marque el recuadro de selección **Convertir este repositorio en privado**.
1. Si desea utilizar GitHub Issues para realizar un seguimiento de los problemas, seleccione el recuadro de selección **Habilitar GitHub Issues**.
1. Si desea realizar un seguimiento del despliegue de cambios en el código mediante la creación de etiquetas y comentarios en las confirmaciones, y etiquetas y comentarios en los problemas a los que hacen referencia las confirmaciones, marque el recuadro de selección **Hacer un seguimiento del despliegue cambios de código**. Para obtener más información, consulte [Seguimiento de dónde se despliega el código con cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}.
1. Pulse **Crear integración**.
1. Pulse la tarjeta correspondiente al repositorio GitHub o {{site.data.keyword.ghe_short}} con el que desea trabajar. En función del repositorio seleccionado, se abrirá el sitio web de GitHub o el repositorio de {{site.data.keyword.ghe_short}} de su empresa, donde puede ver el contenido del repositorio.

  Puede utilizar estas herramientas integradas de gestión del código fuente en Eclipse Orion {{site.data.keyword.webide}} para editar el repositorio de GitHub y desplegar una app desde su espacio de trabajo.
  {: tip}

1. Si ha habilitado GitHub Issues, pulse **GitHub Issues** para abrirlo. Puede utilizar esta instancia de GitHub Issues para toda la cadena de herramientas, aunque la cadena de herramientas contenga varios repositorios GitHub o {{site.data.keyword.ghe_short}}.    

Si no tiene privilegios de administrador sobre el repositorio con el que va a enlazar, la integración se verá limitada porque no podrá utilizar un webhook. Los webhooks se necesitan para ejecutar automáticamente un conducto cuando se envía una confirmación al repositorio. Sin un webhook, debe iniciar los conductos manualmente.
{: tip}

### Más información sobre GitHub

Para obtener más información acerca de GitHub, consulte el [artículo de GitHub ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_github/){: new_window} y el [artículo de GitHub Issues ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window} en el IBM Cloud Garage Method o realice estas guías de aprendizaje:

 * [Utilice la cadena de herramientas "Desarrollar y probar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

 * [Garantice la calidad de los despliegues mediante la cadena de herramientas "Deployment Risk Analytics con GitHub y Jenkins" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

 * [Cree una cadena de herramientas personalizada ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/create-a-custom-toolchain){:new_window}


## Configuración de GitHub Enterprise and Issues en {{site.data.keyword.Bluemix_notm}} dedicado
{: #configghe}

 Estas instrucciones se aplican a {{site.data.keyword.Bluemix_notm}} dedicado para {{site.data.keyword.ghe_short}}. Si utiliza su propia versión gestionada de {{site.data.keyword.ghe_short}}, algunos pasos pueden diferir en función de sus procedimientos internos.
 {: important}

{{site.data.keyword.ghe_long}} es un servicio de alojamiento basado en web para repositorios Git. {{site.data.keyword.ghe_short}} dedicado es únicamente para clientes de {{site.data.keyword.Bluemix_notm}} dedicado. GitHub Issues es una herramienta de seguimiento que mantiene todo su trabajo y sus planificaciones en un mismo lugar. Está integrado con el repositorio de desarrollo de modo que pueda centrarse en las tareas importantes. Para obtener más información sobre {{site.data.keyword.ghe_short}} dedicado y GitHub Issues, consulte [Iniciación a {{site.data.keyword.ghe_long}}](/docs/services/ghededicated?topic=ghededicated-gheded_getting_started){: new_window} y el [artículo GitHub Issues ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window} en IBM Cloud Garage Method.

Puede configurar {{site.data.keyword.ghe_short}} como una integración de herramientas de la cadena de herramientas para que pueda gestionar el código fuente en la instancia de [{{site.data.keyword.Bluemix_notm}} Dedicado](/docs/dedicated?topic=dedicated-dedicated#dedicated){: new_window} de la empresa.

1. Si configura la integración de esta herramienta mientras crea la cadena de herramientas, siga estos pasos:

 a. Antes de iniciar sesión en Dedicated {{site.data.keyword.ghe_short}} por primera vez, solicite al administrador de la zona de su empresa que añada el ID de usuario a la instancia de {{site.data.keyword.Bluemix_notm}} Dedicated desde el registro de usuarios de su empresa utilizando LDAP. Para obtener información sobre cómo configurar la cuenta de {{site.data.keyword.ghe_short}}, consulte [Iniciación a {{site.data.keyword.ghe_long}}](/docs/services/ghededicated?topic=ghededicated-gheded_getting_started){: new_window}.

 b. En la sección Integraciones configurables, pulse **{{site.data.keyword.ghe_short}}**.    

 c. Revise el nombre predeterminado para el nuevo repositorio de {{site.data.keyword.ghe_short}}. Si es necesario, cambie el nombre del repositorio nuevo. La siguiente imagen muestra un ejemplo de un repositorio clonado desde un repositorio de ejemplo. Puede utilizar un repositorio existente o uno nuevo. Para utilizar un repositorio nuevo, puede crear un repositorio vacío, clonarlo o bifurcarlo.
 ![Ubicaciones de repositorio predeterminado](images/toolchain_ghe_config.png)

1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **{{site.data.keyword.ghe_short}}**.

1. Si tiene un repositorio de {{site.data.keyword.ghe_short}} que desea utilizar, escriba el URL para el repositorio. Para el tipo de repositorio, pulse **Existente**.
1. Si desea utilizar un repositorio nuevo de {{site.data.keyword.ghe_short}}, escriba un nombre para el repositorio, escriba el URL del repositorio que está clonando o bifurcando y seleccione el tipo de repositorio:

 a. Para crear un repositorio vacío, pulse **Nuevo**.

 b. Para crear una copia de un repositorio, pulse **Clonar**.

 c. Para bifurcar un repositorio para que pueda aportar cambios a través de solicitudes de extracción, pulse **Bifurcar**.

1. Para utilizar GitHub Issues para realizar un seguimiento de los problemas, seleccione el recuadro de selección **Habilitar GitHub Issues**.
1. Pulse **Crear integración**.
1. Pulse la tarjeta correspondiente al repositorio {{site.data.keyword.ghe_short}} con el que desee trabajar. Se abrirá el repositorio de {{site.data.keyword.ghe_short}} de la empresa.

  Puede utilizar estas herramientas integradas de gestión del código fuente en Eclipse Orion {{site.data.keyword.webide}} para editar el repositorio de {{site.data.keyword.ghe_short}} y desplegar una app desde su espacio de trabajo.
  {: tip}

1. Si ha habilitado GitHub Issues, pulse **GitHub Issues**. Puede utilizar esta instancia de GitHub Issues para toda la cadena de herramientas, aunque la cadena de herramientas contenga varios repositorios GitHub.    

Si no tiene privilegios de administrador sobre el repositorio con el que va a enlazar, la integración se verá limitada porque no podrá utilizar un webhook. Los webhooks se necesitan para ejecutar automáticamente un conducto cuando se envía una confirmación al repositorio. Sin un webhook, debe iniciar los conductos manualmente.
{: tip}


## Configuración de GitLab
{: #gitlab}

GitLab es un servicio de alojamiento basado en web para repositorios Git. Puede tener copias locales y remotas de sus repositorios, lo que facilita la colaboración.

Puede configurar GitLab como una integración de herramientas de la cadena de herramientas para que pueda gestionar el código fuente en un repositorio nuevo o existente en GitLab.com o en la instancia GitLab de su empresa. Participe en la codificación social mediante wikis, seguimiento de problemas y solicitudes de fusión.

Si configura la integración de esta herramienta mientras crea la cadena de herramientas, siga estos pasos:

1. Si está almacenando el código fuente en un repositorio GitLab, en la sección Integraciones configurables, pulse **GitLab**. Si está configurando esta integración de herramientas en {{site.data.keyword.Bluemix_notm}} Público y no ha autorizado a {{site.data.keyword.Bluemix_notm}} para que acceda a GitLab, pulse **Autorizar** para ir al sitio web de GitLab. Si no tiene ninguna sesión de GitLab activa, se le solicitará que inicie sesión. Pulse **Autorizar aplicación** para permitir que {{site.data.keyword.Bluemix_notm}} acceda a su cuenta de GitLab. Si tiene una sesión de GitLab activa pero no ha especificado la contraseña recientemente, es posible que se le solicite que especifique su contraseña de GitLab para confirmar.
1. Si está utilizando un repositorio en su propio servidor de GitLab, en la sección Integraciones configurables, pulse **Añadir servidor personalizado**.

 La red debe poder acceder al servidor GitLab de destino desde un entorno de {{site.data.keyword.Bluemix_notm}} dedicado.
 {: tip}

 Escriba un título para el servidor de GitLab personalizado y especifique el URL raíz para el servidor. Escriba su señal de acceso personal y pulse **Guardar integración personalizada**.

  Si no tiene una señal de acceso personal, puede crear una:

     a. En cualquier página de GitLab, pulse el icono de su perfil y, a continuación, pulse **Valores**.

     b. En la página Señales de acceso, escriba el nombre de la aplicación para la que desee crear una señal de acceso personal.

     c. Opcional. Elija una fecha de caducidad para la señal de acceso.

     d. Seleccione el recuadro de selección **api** para definir el acceso para la señal personal.

     e. Pulse **Crear señal de acceso personal**.

     f. Copie la señal en una ubicación segura o en una app de gestión de contraseñas. Por motivos de seguridad, una vez que abandone la página ya no podrá volver a ver la señal.

1. Revise las ubicaciones de repositorio de destino predeterminadas para los repositorios de GitLab. Dichos repositorios se clonan a partir del repositorio de ejemplo. Si es necesario, cambie el nombre de los repositorios de destino.

Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, siga estos pasos:

1. En el panel de control de DevOps, en la página Cadenas de herramientas, pulse sobre la cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.
1. Pulse **Añadir una herramienta**.
1. En la sección Integraciones de herramientas, pulse **GitLab**.
1. Pulse el servidor de GitLab que desee utilizar.
1. Si tiene un repositorio de GitLab y desea utilizarlo, para el tipo de repositorio, pulse **Existente** y escriba el URL.
1. Si desea utilizar un repositorio de GitLab nuevo, escriba un nombre para el repositorio, escriba el URL para el repositorio que esté colando o bifurcando, y seleccione el tipo de repositorio:

 a. Para crear un repositorio vacío, pulse **Nuevo**.

 b. Para crear una copia de un repositorio de GitLab, pulse **Clonar**.

 c. Para bifurcar un repositorio de GitLab para que pueda aportar cambios a través de solicitudes de fusión, pulse **Bifurcar**.

1. Si desea crear un repositorio público en el servidor, desmarque el recuadro de selección **Convertir este repositorio en privado**.
1. Si desea utilizar los problemas de GitLab para el seguimiento de problemas, marque el recuadro de selección **Habilitar problemas de GitLab**.
1. Si desea realizar un seguimiento del despliegue de cambios en el código mediante la creación de etiquetas y comentarios en las confirmaciones, y etiquetas y comentarios en los problemas a los que hacen referencia las confirmaciones, marque el recuadro de selección **Hacer un seguimiento del despliegue cambios de código**. Para obtener más información, consulte [Seguimiento de dónde se despliega el código con cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}.
1. Pulse **Crear integración**.
1. Pulse la tarjeta correspondiente al repositorio de GitLab con el que desee trabajar. En función del repositorio que haya seleccionado, ya sea que se abra el sitio web de GitLab o el repositorio de GitLab de la empresa, donde pueda visualizar el contenido del repositorio.

  Puede utilizar estas herramientas integradas de gestión del código fuente en Eclipse Orion {{site.data.keyword.webide}} para editar el repositorio de GitLab y desplegar una app desde su espacio de trabajo.
  {: tip}

1. Si ha habilitado Problemas de GitLab, pulse **Problemas de GitLab** para abrirla. Puede utilizar esta instancia de Problemas de GitLab para toda la cadena de herramientas, incluso si la cadena de herramientas contiene varios repositorios de GitLab.    

Si no tiene privilegios de propietario o maestro para el repositorio al que está enlazando, la integración estará limitada porque no puede utilizar un webhook. Los webhooks se necesitan para ejecutar automáticamente un conducto cuando se envía una confirmación al repositorio. Sin un webhook, debe iniciar los conductos manualmente.
{: tip}

### Más información sobre GitLab

Para obtener más información sobre GitLab, consulte el [artículo de GitLab ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_gitlab/){: new_window} en el IBM Cloud Garage Method.


## Configuración de Jenkins
{: #jenkins}

Jenkins es una herramienta de código abierto basada en la web que compila y prueba software continuamente, dando soporte a prácticas de integración continua y de entrega continua.

Antes de crear una integración de herramientas Jenkins, debe tener un servidor Jenkins.
{: important}

Con la integración de herramientas Jenkins, puede enviar notificaciones de trabajos Jenkins a otras herramientas de la cadena de herramientas, como por ejemplo Slack y PagerDuty. Para realizar un seguimiento del código en los despliegues, puede añadir mensajes de despliegue a sus confirmaciones Git y a los problemas de Git o JIRA relacionados. También puede ver los despliegues en la página Conexiones de cadena de herramientas. Puede enviar los resultados de las pruebas a {{site.data.keyword.DRA_short}}, añadir objetivos de calidad automatizados y realizar un seguimiento del riesgo del despliegue.

Configure Jenkins para automatizar la creación, las pruebas y el despliegue automáticos de sus apps:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Jenkins**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Jenkins**.

1. Escriba el nombre que desea visualizar para esta integración de herramientas en la tarjeta de Jenkins de la cadena de herramientas.
1. Escriba el URL correspondiente al servidor Jenkins que desea abrir cuando pulse la tarjeta de Jenkins en la cadena de herramientas.
1. Copie el webhook de la cadena de herramientas generado.
1. En el servidor Jenkins, siga estos pasos:

 a. [Instale el plug-in de IBM Cloud DevOps ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Installingtheplugin){: new_window}.

 b. [Configure Jenkins para notificar a las cadenas de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Notifyingtoolchains){: new_window}.

 c. Vuelva a la página Configurar la integración para la integración de herramientas de Jenkins.

1. Pulse **Crear integración**.
1. En la cadena de herramientas, pulse **Jenkins** para ver el servidor Jenkins.  

### Más información sobre Jenkins

Para obtener más información sobre Jenkins, consulte el [artículo de Jenkins ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/deliver/tool_jenkins/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje:

  * [Garantice la calidad de los despliegues mediante la cadena de herramientas "Deployment Risk Analytics con GitHub y Jenkins" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

## Configuración de JIRA
{: #jira}

JIRA es una herramienta que realiza un seguimiento de problemas y errores relacionados con el software. La integración de herramientas JIRA actualiza los problemas del proyecto cuando Jenkins o {{site.data.keyword.deliverypipeline}} ejecutan un despliegue. Para que la integración de herramientas JIRA realice el seguimiento de los problemas, debe utilizar JIRA Smart Commits en los mensajes de confirmación. Para obtener más información sobre JIRA Smart Commits, consulte [Utilización de Smart Commits ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://confluence.atlassian.com/fisheye/using-smart-commits-298976812.html){: new_window}.

Configure JIRA de modo que planifique, realice un seguimiento y distribuya código de calidad:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **JIRA**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **JIRA**.

1. Si tiene un proyecto JIRA y desea conectar con el mismo, para el tipo de JIRA pulse **Existente**:

 a. Escriba la clave del proyecto JIRA para el proyecto JIRA. Encontrará la clave del proyecto en el URL del proyecto JIRA.

 b. Escriba el URL de API base de su instancia de JIRA. Encontrará el URL de la API en la cabecera de la instancia de JIRA. Pulse el icono **Administración** y pulse **Sistema**.

 c. Si se está conectando a una instancia de JIRA privada, o si desea recibir información de rastreabilidad desde una instancia de JIRA pública, especifique el nombre de usuario y la contraseña de JIRA.

 d. Para realizar un seguimiento del despliegue de cambios en el código para el proyecto mediante la creación de etiquetas y comentarios para problemas a los que se hace referencia, marque el recuadro de selección **Hacer un seguimiento del despliegue de cambios de código**. Asegúrese de utilizar JIRA Smart Commit para hacer referencia a los problemas de JIRA en las confirmaciones de GitHub. Si no selecciona esta opción, la integración de herramientas JIRA pasa por alto las confirmaciones.

1. Si desea crear un proyecto JIRA, para el tipo de JIRA pulse **Nuevo**:

 a. Escriba una clave de proyecto de JIRA que se utilizará para el proyecto nuevo. Esta clave se utiliza como identificador exclusivo en el URL del proyecto.

 b. Escriba un nombre para el proyecto JIRA.

 c. Escriba el URL de API base de su instancia de JIRA. Encontrará el URL de la API en la cabecera de la instancia de JIRA. Pulse el icono **Administración** y pulse **Sistema**.

 d. Escriba el nombre de usuario para el responsable del proyecto JIRA que desee utilizar para este proyecto. Para especificar alguien como responsable de proyecto JIRA, dicha persona debe tener permiso de responsable del proyecto en JIRA.

 e. Escriba el nombre de usuario administrador para esta instancia de JIRA.

 f. Escriba la contraseña del administrador para esta instancia de JIRA.

 g. Para realizar un seguimiento del despliegue de cambios en el código para el proyecto mediante la creación de etiquetas y comentarios para problemas a los que se hace referencia, marque el recuadro de selección **Hacer un seguimiento del despliegue de cambios de código**. Asegúrese de utilizar JIRA Smart Commit para hacer referencia a los problemas de JIRA en las confirmaciones de GitHub. Si no selecciona esta opción, la integración de herramientas JIRA pasa por alto las confirmaciones.

1. Pulse **Crear integración**.
1. Desde la cadena de herramientas, pulse **JIRA** para ver el panel de control del proyecto JIRA al que se ha conectado.

### Más información sobre JIRA

Para obtener más información sobre JIRA, consulte el [artículo de JIRA ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/code/tool_jira/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje:

  * [Obtenga información mediante la cadena de herramientas "Developer Insights y Team Dynamics con GitHub y JIRA" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/gain-insights-developer-insights-and-team-dynamics-with-github-and-jira-toolchain){:new_window}


## Configuración de Nexus
{: #nexus}

Configure el gestor de repositorios Nexus para que guarde los artefactos de compilación en el repositorio de Nexus (repo):

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Nexus**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Nexus**.

1. Escriba un nombre para esta instancia de la integración de herramientas Nexus.
1. Escriba el URL correspondiente al repositorio Nexus que desea abrir cuando pulse la tarjeta de Nexus en la cadena de herramientas.
1. Seleccione el tipo de repositorio con el que desea conectar.
1. Si ha seleccionado **Registro de npm**, siga estos pasos:

 a. Escriba la dirección de correo electrónico asociada con el registro.

 b. Escriba la señal de autenticación asociada con el registro.

 c. Escriba el URL del repositorio de release de Nexus, que es el registro privado del servidor de Nexus.

 d. Escriba el URL para el registro de duplicación o público que utiliza para combinar varios registros npm públicos y privados. Por ejemplo, este URL podría ser el URL del registro virtual en el servidor de Nexus que puede acceder tanto al registro privado como a la memoria caché del registro global de npm.

1. Si ha seleccionado **Repositorio de Maven**, siga estos pasos:

 a. Escriba el ID de usuario asociado con el repositorio.

 b. Escriba la contraseña asociada con el repositorio.

 c. Escriba el URL del repositorio de release de Nexus, que es el repositorio del release privado del servidor de Nexus.

 d. Escriba el URL del repositorio de instantáneas de Nexus, que es el repositorio de instantáneas privado del servidor de Nexus.

 e. Escriba el URL del repositorio de duplicación o público que utilice para combinar varios repositorios Maven públicos y privados. Por ejemplo, este URL podría ser el URL del repositorio virtual en el servidor de Nexus que puede acceder tanto al repositorio privado como a la memoria caché del repositorio central de Maven.

1. Pulse **Crear integración**.
1. En la cadena de herramientas, pulse la tarjeta correspondiente al repositorio Nexus con el que desee trabajar. Se abrirá el sitio web de Nexus, donde puede ver el contenido del repositorio.
1. Opcional: si utiliza una cadena de herramientas en {{site.data.keyword.Bluemix_notm}} Público y desea crear la app utilizando Nexus con npm, configure el conducto para añadir un trabajo de compilación de npm. Para obtener instrucciones sobre cómo configurar el trabajo de creación, consulte [Configuración de un trabajo de compilación de npm de Nexus en el conducto](#config_nexus_npm).
1. Opcional: si utiliza una cadena de herramientas en {{site.data.keyword.Bluemix_notm}} Público y desea crear la app utilizando Nexus con Maven, configure el conducto para añadir un trabajo de compilación de Maven. Para obtener instrucciones sobre cómo configurar el trabajo de creación, consulte [Configuración de un trabajo de compilación de Maven de Nexus en el conducto](#config_nexus_maven).

### Configuración de un trabajo de compilación de npm de Nexus en el conducto
{: #config_nexus_npm}

Antes de configurar un trabajo de compilación de npm en el conducto, necesita un conducto en funcionamiento que pueda utilizar para crear el repositorio SCM como entrada y debe configurar Nexus para su cadena de herramientas. Para obtener instrucciones sobre cómo configurar Nexus, consulte la sección [Nexus](#nexus).

Configure {{site.data.keyword.deliverypipeline}} para añadir un trabajo de compilación de npm:

1. Cree una etapa y establezca la entrada al repositorio SCM adecuado.
1. En la etapa, añada un trabajo de trabajo de compilación.
1. Configure el trabajo de compilación: ![Trabajo de compilación de npm](images/nexus_npm_job.png)

  a. Para el tipo de constructor, seleccione **Compilación de NPM**.

  b. Si ha configurado varias instancias de la integración de herramientas de Nexus, escriba el nombre de la integración de herramientas de Nexus para la que desea configurar el trabajo de compilación.

  c. Para el tipo de integración de herramientas, seleccione **Nexus**.

  d. Para el mandato de compilación, especifique los mandatos para crear el módulo npm o publicarlo en el registro. En este ejemplo se muestran los mandatos para crear el módulo o publicarlo.
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  **Consejo:** encontrará el URL y las credenciales de usuario que ha utilizado para conectar con el registro en los valores de configuración correspondientes a la integración de herramientas de Nexus.

  e. Si el trabajo de compilación se publica en el registro de Nexus y el formato de su versión del módulo de nodo es `x.y.z-SNAPSHOT.w`, marque el recuadro de selección **Incrementar versión del módulo de instantáneas**. El trabajo de compilación actualiza automáticamente la versión del módulo antes de que publique en el registro de Nexus. El trabajo de compilación selecciona la versión más alta del módulo a partir del registro de npm y el archivo `package.json` local e incrementa la versión del módulo utilizando semver. El trabajo de compilación no envía los cambios al repositorio SCM.

1. Pulse **GUARDAR**. Siempre que se ejecute el conducto, este trabajo de compilación utilizará la información de configuración de la integración de herramientas de Nexus para conectar con el registro de npm.

### Configuración de un trabajo de compilación de Maven de Nexus en el conducto
{: #config_nexus_maven}

Antes de configurar un trabajo de compilación de Maven en el conducto, necesita un conducto en funcionamiento que pueda utilizar para crear el repositorio SCM como entrada y debe configurar Nexus para su cadena de herramientas. Para obtener instrucciones sobre cómo configurar Nexus, consulte la sección [Nexus](#nexus).

Configure {{site.data.keyword.deliverypipeline}} para añadir un trabajo de compilación de Maven:

1. Cree una etapa y establezca la entrada al repositorio SCM adecuado.
1. En la etapa, añada un trabajo de trabajo de compilación.
1. Configure el trabajo de compilación: ![Trabajo de compilación de Maven](images/nexus_maven_job.png)

  a. Para el tipo de constructor, seleccione **Compilación de Maven**.

  b. Si ha configurado varias instancias de la integración de herramientas de Nexus, escriba el nombre de la integración de herramientas de Nexus para la que desea configurar el trabajo de compilación de Maven.

  c. Para el tipo de integración de herramientas, seleccione **Nexus**.

  d. Para el mandato de compilación, escriba los mandatos para crear el módulo de Maven o publicarlo en el registro de instantáneas. En este ejemplo se muestran los mandatos para crear el módulo o publicarlo.
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  Encontrará el URL y las credenciales de usuario que ha utilizado para conectar con el registro en los valores de configuración correspondientes a la integración de herramientas de Nexus.
  {: tip}

1. Pulse **GUARDAR**. Siempre que se ejecute el conducto, este trabajo de compilación utilizará la información de configuración de la integración de herramientas de Nexus para conectar con el registro de Maven.

### Más información sobre Nexus

Para obtener más información sobre Nexus, consulte el [artículo de Nexus ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/deliver/tool_nexus/){: new_window} en el IBM Cloud Garage Method.


## Configuración de una herramienta personalizada (Otras herramientas)
{: #othertool}

Si el equipo utiliza una herramienta no incluida en la lista de integraciones de las cadenas de herramientas, puede integrar una herramienta personalizada.

Configure una herramienta personalizada para que funcione con otras herramientas de la cadena de herramientas y que esté disponible para el equipo:

1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Otra herramienta**.

1. Escriba el nombre de la herramienta.
1. Seleccione la fase del ciclo de vida que esté asociada de forma más cercana con la herramienta. Esta selección determina la categoría en la que se lista la herramienta en la página Visión general.
1. Añada un URL de icono. El icono se muestra en la tarjeta de la integración de herramientas.
1. Añada un URL de documentación.
1. Especifique un nombre de instancia de la herramienta. Por ejemplo, My Team Tool.
1. Añada un URL de instancia de herramienta. Este URL se abre siempre que se pulsa en la tarjeta de la integración de herramientas.
1. Añada una descripción de la herramienta.
1. (Avanzado) Añada propiedades adicionales si es necesario. Por ejemplo, liste cualquier información o atributos necesarios para que la herramienta se integre con otras herramientas en la cadena de herramientas.  
1. Pulse **Crear integración**.

### Más información sobre la herramienta personalizada

Para obtener más información sobre la herramienta personalizada, consulte [Introducción a la integración de herramientas personalizadas para cadenas de herramientas de {{site.data.keyword.Bluemix_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2016/10/custom-tool-integration-with-bluemix-toolchains/){: new_window} o realice esta guía de aprendizaje:

  * [Añadir una integración de herramientas personalizadas para una cadena de herramientas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/add-a-custom-tool-integration-to-a-toolchain){:new_window}


## Configuración de PagerDuty
{: #pagerduty}

PagerDuty integra datos de varios sistemas de supervisión en una única vista. Cuando se produce un problema, PagerDuty se asegura de que el miembro del equipo más adecuado para corregirlo reciba una notificación. Si el miembro del equipo no responde al problema, pueden configurarse sistemas de escalado para pasar el problema a representantes o gestores de operaciones secundarios.

Configure PagerDuty para enviar notificaciones cuando se producen errores en la fase de conducto para que pueda corregir los problemas con mayor celeridad y reducir el tiempo de inactividad:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **PagerDuty**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **PagerDuty**.

1. Si desea integrar PagerDuty en el nivel de cuenta utilizando una clave de API, pulse **Cuenta**:

 a. Escriba la clave de acceso de API para su cuenta de PagerDuty. Si no dispone de una cuenta de PagerDuty, [regístrese para obtener una ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://signup.pagerduty.com/accounts/new){: new_window}. Para ver instrucciones para localizar la clave, consulte [Generación de una clave de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://support.pagerduty.com/hc/en-us/articles/202829310-Generating-an-API-Key){: new_window}.

 b. Escriba el nombre del servicio PagerDuty.

 c. Escriba la dirección de correo electrónico del contacto principal de PagerDuty.

 d. Escriba el número de teléfono del contacto principal de PagerDuty.

1. Si desea integrar PagerDuty en el nivel de servicio mediante una clave de integración, pulse **Servicio**:

 a. Escriba el URL para el servicio de PagerDuty en el que desee publicar alertas.

 b. Escriba su clave de integración de PagerDuty. Puede encontrar la clave o crear una en la sección Integraciones de la página de servicio de PagerDuty.

1. Pulse **Crear integración**.
1. Pulse **PagerDuty** para ir a pagerduty.com. Puede ver los sucesos asociados con el servicio PagerDuty que ha especificado al configurar la integración de esta herramienta para su cadena de herramientas.

### Más información sobre PagerDuty

Para obtener más información sobre PagerDuty, consulte el [artículo de PagerDuty ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/manage/tool_pagerduty/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje y el curso de defensor de Garage Method:

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [Conviértase en un defensor de Garage Method ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## Configuración de Rational Team Concert
{: #rationalteamconcert}

IBM Rational Team Concert es una herramienta de colaboración en equipo que integra, entre otras, tareas de desarrollo, planificación de iteraciones, gestión de cambios, seguimiento de defectos, control de origen, automatización de compilaciones y creación de informes.

Configure Rational Team Concert para la entrega continua y seguir la aproximación que DevOps ofrece en su entorno de desarrollo:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Rational Team Concert**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Rational Team Concert**.

1. Escriba el URL correspondiente al servidor Rational Team Concert que desea abrir cuando pulse la tarjeta de Rational Team Concert en la cadena de herramientas.
1. Escriba el ID de usuario que utiliza para acceder al servidor de Rational Team Concert.
1. Escriba la contraseña que utiliza para acceder al servidor de Rational Team Concert.
1. Si tiene un área de proyecto de Rational Team Concert que desea añadir a su cadena de herramientas, siga estos pasos:

 a. Desde la lista **Escribir área de proyecto**, seleccione **Área de proyecto existente**.

 b. Escriba el nombre del área de proyecto que desea añadir a la cadena de herramientas.

1. Si desea crear un área de proyecto de Rational Team Concert a su cadena de herramientas, siga estos pasos:

 a. Desde la lista **Escribir área de proyecto**, seleccione **Nueva área de proyecto**.

 b. Escriba un nombre para la nueva área de proyecto que va añadir a su cadena de herramientas.

 c. Escriba el nombre de la plantilla de proceso de Rational Team Concert que utilizará para crear el proyecto.

1. Para realizar un seguimiento del despliegue de cambios en el código para el proyecto mediante la creación de etiquetas y comentarios en elementos de trabajo, marque el recuadro de selección **Hacer un seguimiento del despliegue de cambios de código**.
1. Pulse **Crear integración**.
1. Desde su cadena de herramientas, pulse **Rational Team Concert** para abrir el panel de control de Rational Team Concert configurado.

### Más información sobre Rational Team Concert

Para obtener más información sobre Rational Team Concert, consulte el [artículo de IBM Rational Team Concert ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/think/tool_rtc/){: new_window} en el IBM Cloud Garage Method.


## Configuración de Sauce Labs
{: #saucelabs}

Sauce Labs ejecuta pruebas de unidad funcionales. Cuando se configura una suite de pruebas de Sauce Labs como trabajo de pruebas en {{site.data.keyword.deliverypipeline}}, la suite de pruebas puede ejecutar pruebas para la app web o móvil como parte del proceso de entrega continuo. Estas pruebas pueden proporcionar un control de flujo muy valioso para los proyectos, y actuar como pasarelas para evitar el despliegue de código defectuoso.

 Esta integración de herramientas solo está disponible en {{site.data.keyword.Bluemix_notm}} público.
 {: tip}

Configure Sauce Labs para ejecutar pruebas funcionales automatizadas en varios sistemas operativos y navegadores a fin de poder emular el modo en que el usuario puede utilizar un sitio web o una aplicación:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Sauce Labs**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Sauce Labs**.

1. Escriba el nombre de usuario asociado con su cuenta de Sauce Labs. Puede [encontrar su nombre de usuario en el mensaje de bienvenida en la página de la cuenta de Sauce Labs ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://saucelabs.com/account){: new_window}.
1. Escriba la clave de acceso para su cuenta de Sauce Labs. Puede [encontrar la clave en la página de la cuenta de Sauce Labs ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://saucelabs.com/account){: new_window}.
1. Pulse **Crear integración**.
1. Pulse **Sauce Labs** para ir a saucelabs.com y ver la actividad de pruebas de la cadena de herramientas.

 Si ha añadido un trabajo de pruebas de Sauce Labs al {{site.data.keyword.deliverypipeline}}, puede seleccionar la instancia del servicio. Para obtener instrucciones sobre cómo configurar un trabajo de prueba en su conducto, consulte [Configuración de un trabajo de pruebas Sauce Labs en el conducto](#config_saucelabs).
 {: tip}

### Más información sobre Sauce Labs

Para obtener más información sobre Sauce Labs, consulte el [artículo de Sauce Labs ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/deliver/tool_sauce_labs/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje:

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}



## Configuración de Slack
{: #slack}

Las notificaciones que se publican en canales Slack públicos son visibles para todas las personas del equipo. El usuario es responsable del contenido que publique.
{: important}

Slack es un sistema de notificaciones y mensajería en tiempo real y basado en la nube. Slack proporciona una función de chat permanente, que es una alternativa más interactiva que el correo electrónico para facilitar la colaboración del equipo. Puede comunicarse con su equipo en un canal dedicado o en un conjunto de canales directamente relacionados con su trabajo. Asimismo, puede compartir archivos e imágenes a través de los canales o a través de mensajes directos entre dos o más personas. Las comunicaciones en los mensajes directos y en los canales se conservan para poder realizar búsquedas.

Configure Slack para recibir notificaciones acerca de su cadena de herramientas desde las integraciones de herramientas, como actividades de prueba y de despliegue:

1. Si configura la integración de esta herramienta al crear la cadena de herramientas, en la sección Integraciones configurables, pulse **Slack**.
1. Si tiene una cadena de herramientas y le está añadiendo esta integración de herramientas, en el panel de instrumentos de DevOps, en la página Cadenas de herramientas, pulse la cadena de herramientas para abrir su página Visión general. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego **Visión general**.

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **Slack**.

1. Escriba el URL del webhook de Slack, que genera Slack en forma de webhook de entrada. Necesita un URL de webhook de Slack para recibir notificaciones acerca de su cadena de herramientas desde las integraciones de herramientas. Para ver instrucciones sobre cómo crear o encontrar su webhook, consulte [Webhooks de entrada ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://api.slack.com/incoming-webhooks){: new_window}.

 Si utiliza una clave de API para el canal de Slack para recibir notificaciones acerca de la cadena de herramientas desde las integraciones de herramientas, debe actualizar la configuración para que utilice un webhook en su lugar.
 {: tip}

1. Escriba el nombre del canal Slack al que desea enviar las notificaciones. El canal debe existir y debe estar activo en el equipo de Slack.
1. Escriba el nombre de host del URL para el equipo de Slack, que es la palabra o frase que precede a `.slack.com` en el URL del equipo. Por ejemplo, si el URL del equipo es `https://team.slack.com`, el nombre de host es `team`.
1. Pulse **Crear integración**.

 Si no se puede acceder al canal ni al equipo de Slack que ha especificado, se muestra el error `Error de configuración` en la tarjeta de Slack. Mueva el cursor sobre el mensaje `Error de configuración` y pulse **Reconfigurar**. Asegúrese de utilizar parámetros de configuración válidos para el URL del webhook de Slack, el canal de Slack y el nombre de host del URL del equipo de Slack. Actualice los valores según sus necesidades y pulse **Guardar integración**.
 {: tip}

1. Pulse **Slack**. Puede ver toda la actividad de su cadena de herramientas en el canal Slack configurado.

### Más información sobre Slack

Para obtener más información sobre Slack, consulte el [artículo de Slack ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/culture/tool_slack/){: new_window} en el IBM Cloud Garage Method o realice esta guía de aprendizaje y el curso de defensor de Garage Method:

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [Conviértase en un defensor de Garage Method ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## Configuración de SonarQube
{: #sonarqube}

SonarQube ofrece una visión general del estado general y de la calidad del código fuente e identifica los problemas del nuevo código. Los analizadores de código detectan errores complicados, como referencias a punteros nulos, errores de lógica y falta de recursos, para más de 20 lenguajes de codificación.

Configure SonarQube de modo que analice y evalúe continuamente la calidad del código fuente:

1. En el panel de control de DevOps, pulse **Cadenas de herramientas**. Pulse la página Cadenas de herramientas a la que desea añadir SonarQube. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**. A continuación, pulse **Visión general**.  

 a. Pulse **Añadir una herramienta**.

 b. En la sección Integraciones de herramientas, pulse **SonarQube**.

1. Escriba un nombre para esta instancia de la integración de herramientas SonarQube.
1. Escriba el URL correspondiente a la instancia de SonarQube que desea abrir cuando pulse la tarjeta de SonarQube en la cadena de herramientas.
1. Opcional: escriba el nombre de usuario que utiliza para conectarse al servidor de SonarQube.

 Solo es necesario especificar un nombre de usuario si utiliza una contraseña para conectar con el servidor de SonarQube. Si utiliza una señal de autenticación para conectar, deje este campo vacío.
 {: tip}

1. Escriba la contraseña o la señal de autenticación que utiliza para conectarse al servidor de SonarQube.
1. Pulse **Crear integración**.
1. Desde la cadena de herramientas, pulse **SonarQube** para ver el panel de control de la instancia de SonarQube al que se ha conectado.

### Más información sobre SonarQube

Para obtener más información sobre SonarQube, consulte el [artículo de SonarQube ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/content/learn/tool_sonarqube/){: new_window} en el IBM Cloud Garage Method.
