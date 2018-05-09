---

copyright:
  years: 2015, 2018
lastupdated: "2018-3-21"

---


{:screen: .screen}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:shortdesc: .shortdesc}

# Cómo trabajar con conductos{: #pipeline-working}

Para automatizar las compilaciones y los despliegues en {{site.data.keyword.Bluemix}}, utilice los conductos de {{site.data.keyword.contdelivery_full}}.
{: shortdesc}

Con los conductos, puede elegir entre distintos tipos de compilación. Proporcione el script de compilación y {{site.data.keyword.contdelivery_short}} lo ejecutará; no es necesario configurar sistemas de compilación. A continuación, con un solo clic puede desplegar automáticamente su app en uno o más espacios de {{site.data.keyword.Bluemix_notm}}, servidores de Cloud Foundry públicos o contenedores Docker en IBM Containers for {{site.data.keyword.Bluemix_notm}}.

Los trabajos de compilación compilan y empaquetan el código fuente de su app desde repositorios Git. Los trabajos de compilación generan artefactos desplegables, como archivos WAR o contenedores Docker para IBM Containers. Además, puede ejecutar automáticamente pruebas de unidad en su compilación. Puede configurar sus trabajos de compilación de modo que cada vez que se envíe una confirmación se desencadene una compilación.

Un trabajo de despliegue toma la salida de un trabajo de compilación y lo despliega en IBM Containers o en servidores de Cloud Foundry como {{site.data.keyword.Bluemix_notm}}.

Puede desplegar en una o más regiones y servicios. Por ejemplo, puede configurar {{site.data.keyword.deliverypipeline}} para que utilice uno o varios servicios, realice pruebas en una región y despliegue a producción en varias regiones. Para obtener más información, consulte [Regiones](/docs/overview/whatisbluemix.html#ov_intro_reg){: new_window}.

Si utiliza varios conductos en una cadena de herramientas abierta, puede crear un conducto compuesto para gestionar el despliegue de todos los conductos desde una sola ubicación.

Hay varias formas para crear un conducto, incluida la adición de un conducto a una aplicación existente y la creación de un conducto sin una aplicación existente. Si aún no tiene un servicio de {{site.data.keyword.deliverypipeline}} en la organización, puede ir al catálogo, pulsar {{site.data.keyword.deliverypipeline}} y pulsar Crear.

Complete estos pasos para configurar un {{site.data.keyword.deliverypipeline}} para una aplicación existente:

1. En el Panel de control de la app {{site.data.keyword.Bluemix_notm}}, pulse en la app.
1. En el menú de la barra de menús de {{site.data.keyword.Bluemix_notm}}, pulse **Servicios** y luego pulse **DevOps**.
1. Pulse **Conductos** y luego pulse **Crear un conducto**.

Para [crear un conducto ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.bluemix.net/devops/pipelines/dashboard/create){: new_window} configurado para desplegar una aplicación Cloud Foundry, siga estos pasos:

1. Pulse **Cloud Foundry**.
1. Si desea utilizar otro nombre para el conducto, cambie el nombre predeterminado.
1. Si desea utilizar otro nombre para la aplicación, cambie el nombre predeterminado. Este es el nombre de la aplicación en la que se despliega el conducto.
1. Si desea crear el conducto en una organización diferente (org), cambie la organización predeterminada. Puede crear conductos en organizaciones a las que pertenezca.
1. Si desea crear el conducto en un espacio diferente, cambie el espacio predeterminado. Puede crear el conducto en un espacio incluido en la organización.
1. Si no tiene una cadena de herramientas, se crea automáticamente una cadena de herramientas con un nombre predeterminado. Si desea utilizar otro nombre para la cadena de herramientas, cámbiele el nombre. Con la cadena de herramientas, puede ampliar las prestaciones del conducto integrándolo con otras herramientas y servicios. Para obtener más información sobre las cadenas de herramientas, consulte [Creación de cadenas de herramientas](/docs/services/ContinuousDelivery/toolchains_working.html){: new_window}.

 **Consejo**: Los conductos y las cadenas de herramientas pertenecen a las organizaciones (orgs). Si pertenece a una org que tiene cadenas de herramientas, se le puede añadir a la lista de control de accesos para cualquiera de sus cadenas de herramientas asociadas. Después de que se le haya añadido a la lista de control de accesos para una cadena de herramientas, puede visualizar dicha cadena de herramientas y los conductos asociados, aunque no los haya creado. Si se le han otorgado privilegios de administrador, también podrá modificar y suprimir cadenas de herramientas. Para obtener más información sobre el control de accesos para cadenas de herramientas, consulte [Gestión del acceso](/docs/services/ContinuousDelivery/toolchains_using.html#managing_access){: new_window}.

1. Seleccione la cadena de herramientas que desea utilizar o escriba un nombre para la nueva cadena de herramientas que desea crear.
1. Seleccione el proveedor de Git.

 **Sugerencia**: si no tiene autorización de {{site.data.keyword.Bluemix_notm}} para acceder a GitHub, se le solicitará que pulse **Autorizar** para ir al sitio web de GitHub. Si no tiene ninguna sesión de GitHub activa, se le solicitará que inicie sesión. Pulse **Autorizar aplicación** para permitir que {{site.data.keyword.Bluemix_notm}} acceda a su cuenta de GitHub. Si tiene una sesión activa de GitHub pero no ha introducido recientemente su contraseña, es posible que se le solicite que introduzca la contraseña de GitHub para confirmarla.

   * Si tiene un repositorio y desea utilizarlo, seleccione **Enlazar** para el tipo de repositorio. Busque la ubicación del repositorio o seleccione el repositorio en la lista de repositorios disponibles.

   * Si desea crear un repositorio vacío, seleccione **Nuevo** para el tipo de repositorio. Escriba un nombre para el repositorio.

   * Si desea crear un clon de un repositorio, seleccione **Copiar** para el tipo de repositorio. Busque la ubicación del repositorio o seleccione el repositorio en la lista de repositorios disponibles.

   * Si desea bifurcar un repositorio de forma que pueda aportar cambios a través de solicitudes de extracción, seleccione **Bifurcar**. Busque la ubicación del repositorio o seleccione el repositorio en la lista de repositorios disponibles.

1. Seleccione un repositorio o especifique un URL de repositorio.
1. Pulse **Crear**. El conducto se crea, se configura y se visualiza en la página Visión general de la cadena de herramientas.
 ![Tarjeta de conducto](images/cd_pipeline.png)
1. Si ha creado un conducto en una cadena de herramientas que contiene un conducto compuesto, el nuevo conducto se añade al conducto compuesto. Modifique el plan de despliegue para incluir tareas de despliegue para el nuevo conducto. Consulte [Creación de tareas de Delivery Pipeline](/docs/services/ContinuousDelivery/pipeline_deployment_plan.html#tasks_pipelineCD){: new_window}.

Para crear un [conducto vacío ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.bluemix.net/devops/pipelines/dashboard/create){: new_window} sin etapas preconfiguradas:

1. Pulse **Personalizado**.
1. Si desea utilizar otro nombre para el conducto, cambie el nombre predeterminado.
1. Si desea crear el conducto en una organización diferente, cambie la organización predeterminada. Puede crear conductos en organizaciones a las que pertenezca.
1. Si desea crear el conducto en un espacio diferente, cambie el espacio predeterminado. Puede crear el conducto en un espacio incluido en la organización.
1. Si no tiene una cadena de herramientas, se crea automáticamente una cadena de herramientas con un nombre predeterminado. Si desea utilizar otro nombre para la cadena de herramientas, cámbiele el nombre. Con la cadena de herramientas, puede ampliar las prestaciones del conducto integrándolo con otras herramientas y servicios.
1. Seleccione la cadena de herramientas que desea utilizar o escriba un nombre para la nueva cadena de herramientas que desea crear.
1. Pulse **Crear**. Se crea un conducto vacío y se representa como una tarjeta en la página Visión general de la cadena de herramientas.

En {{site.data.keyword.deliverypipeline}}, puede cambiar la configuración, comprobar el estado de las compilaciones, la app desplegada y los despliegues recientes, consultar los registros y detalles de despliegue más recientes o suprimir el conducto.

## Guía de aprendizaje: {{site.data.keyword.deliverypipeline}}
{: #pipeline-tutorial}

Consulte esta guía de aprendizaje en [IBM&reg; Cloud Garage Method ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage){:new_window}:
  * [Crear un conducto ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/tutorial_first_pipeline?task=1){:new_window}
