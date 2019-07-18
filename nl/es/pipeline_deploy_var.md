---

copyright:
  years: 2016, 2019
lastupdated: "2019-05-28"

keywords: Environment properties, IBM Java, pipeline environments

subcollection: ContinuousDelivery

---
<!-- Copyright info at top of file: REQUIRED
    The copyright info is YAML content that must occur at the top of the MD file, before attributes are listed.
    It must be surrounded by 3 dashes.
    The value "years" can contain just one year or a two years separated by a comma. (years: 2014, 2016)
    Indentation as per the previous template must be preserved.
-->

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Propiedades y recursos del entorno
{: #deliverypipeline_environment}

Las siguientes propiedades y recursos están disponibles de forma predeterminada en los entornos de conducto.

<!--##Contents
* [Environment properties](#env)
    * [General purpose properties](#gen)
    * [Runtime and tool properties](#runtime)
    * [Deployment properties](#deployment)
* [Pre-installed resources](#resources)
    * [Runtimes and tools](#tools)
    * [Node modules](#node)-->

## Propiedades de entorno
{: #deliverypipeline_envprop}

### Propiedades de finalidad general
En la tabla siguiente se listan y describen las propiedades de entorno de propósito general que están disponibles de forma predeterminada en entornos de conducto.

| Propiedad de entorno | Descripción |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| ARCHIVE_DIR | El directorio en el que archivar o descargar los archivados. |
| BUILD_ID | El ID exclusivo para la ejecución de trabajos actual.  |
| BUILD_DISPLAY_NAME | El valor BUILD_ID, prefijado con "#". |
| BUILD_NUMBER | El ID de etapa incremental que se muestra en la IU del conducto.  |
| GIT_BRANCH | La rama Git que utiliza el trabajo como entrada. Esta propiedad sólo está disponible en trabajos que utilizan un repositorio de Git como entrada. |
| GIT_COMMIT | La confirmación de Git que utiliza el trabajo como entrada. Esta propiedad sólo está disponible en trabajos que utilizan un repositorio de Git como entrada. |
| GIT_PREVIOUS_COMMIT | El valor de confirmación de Git de la última ejecución correcta del trabajo. Esta propiedad sólo está disponible en trabajos que utilizan un repositorio de Git como entrada. |
| GIT_URL | El URL de repositorio de Git que utiliza el trabajo como entrada. Esta propiedad sólo está disponible en trabajos que utilizan un repositorio de Git como entrada. |
| IDS_JOB_ID | El ID exclusivo de la configuración del trabajo. |
| IDS_JOB_NAME | El nombre de la configuración del trabajo. |
| IDS_OUTPUT_PROPS | Nombres separados por coma de las propiedades del entorno de transferencia. |
| IDS_PROJECT_NAME | El nombre del proyecto, por ejemplo, <code>Propietario - Nombre de proyecto</code>. |
| IDS_STAGE_NAME | El nombre de la etapa actual. |
| IDS_URL | El URL para el conducto actual. |
| IDS_VERSION | El número para la compilación que se está desplegando o el identificador de SCM. Esta propiedad sólo está disponible en trabajos desplegados.
| JOB_NAME | El ID de trabajo exclusivo en el contexto del conducto actual. |
| PIPELINE_ARTIFACT_URL | El URL que puede utilizar para descargar los artefactos del trabajo de compilación actual una vez que se completa el trabajo. Debe utilizar una señal portadora válida para acceder a los artefactos. |
| PIPELINE_INITIAL_STAGE_EXECUTION_ID | El ID exclusivo para la ejecución del conducto. |
| PIPELINE_KUBERNETES_CLUSTER_NAME | El nombre del clúster de Kubernetes seleccionado en el trabajo actual. |
| PIPELINE_LOG_URL | El URL que puede utilizar para descargar el archivo de registro del trabajo actual una vez que se completa el trabajo. Debe utilizar una señal portadora válida para acceder a los archivos de registro. |
| PIPELINE_STAGE_INPUT_JOB_ID | El ID del trabajo que se introduce para la etapa actual. |
| PIPELINE_STAGE_INPUT_REV | La revisión de la entrada para la etapa actual. |
| PIPELINE_TRIGGERING_USER | El usuario actual para el trabajo de conductos|
| TASK_ID | El ID exclusivo de la ejecución actual del trabajo. |
| TMPDIR | Una ubicación de directorio donde se almacenan los archivos temporales. |
| WORKSPACE | La vía de acceso para el directorio de trabajo actual. |
{: caption="Tabla 1. Propiedades de entorno de propósito general" caption-side="top"}

### Propiedades de tiempo de ejecución y de herramientas
En la tabla siguiente se listan y describen las propiedades de entorno de tiempo de ejecución y de herramientas que están disponibles de forma predeterminada en entornos de conducto.

| Propiedad de entorno | Descripción |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| ANT_HOME | La vía de acceso para Apache Ant 1.9.2. |
| ANT_JAVA8_HOME | La vía de acceso a una versión 1.10+ de Apache Ant que necesita Java 8. |
| GRADLE_HOME | La vía de acceso para Gradle 1.11. |
| JAVA_HOME | La vía de acceso para IBM&reg; Java&trade; 7. |
| JAVA7_HOME | La vía de acceso para IBM Java 7. |
| JAVA8_HOME | La vía de acceso para IBM Java 8. |
| MAVEN_HOME | La vía de acceso para Apache Maven 3.2.1. |
| NODE_HOME | La vía de acceso para Node.js 0.10.29. |
{: caption="Tabla 2. Propiedades de entorno de tiempo de ejecución y de herramientas" caption-side="top"}

Para utilizar Apache Ant 1.10+ en los scripts del conducto, establezca `ANT_HOME` en `$ANT_JAVA8_HOME` y `JAVA_HOME` en `$JAVA8_HOME`.
{: tip}

### Propiedades de despliegue
En la tabla siguiente se listan y describen las propiedades de entorno de despliegue que están disponibles de forma predeterminada en entornos de conducto.

| Propiedad de entorno | Descripción |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| CF_APP | Para despliegues, el nombre de la app a desplegar. Esta propiedad es necesaria para el despliegue y se puede especificar en el propio script, en la interfaz de configuración del trabajo de despliegue, o en el archivo `manifest.yml` del proyecto. |
| CF_ORG | Para despliegues, el nombre de la organización (org) en la que se desplegará. |
| CF_ORGANIZATION_ID | Para despliegues, el ID de la org en la que se desplegará. |
| CF_SPACE | Para despliegues, el nombre del espacio en el que se desplegará. |
| CF_SPACE_ID | Para despliegues, el ID del espacio en el que se desplegará.  |
| CF_TARGET_URL | Para despliegues, el URL de {{site.data.keyword.Bluemix_short}} o Cloud Foundry. |
| IDS_VERSION | Para despliegues, la versión de la app que se está desplegando o el identificador de origen. |
{: caption="Tabla 3. Propiedades de entorno de despliegue" caption-side="top"}

## Recursos preinstalados
{: #deliverypipeline_resources}

Varios tiempos de ejecución, herramientas y módulos de Nodos están preinstalados en cada conducto.

### Tiempos de ejecución y herramientas
En la tabla siguiente se listan los tiempos de ejecución y herramientas preinstalados que están disponibles en cada conducto.

Todos los enlaces están en el directorio de inicio.
{: tip}

| Recurso | Nombre de enlace | Vía de acceso |
|----------|-----------|-----------|
|Apache Ant 1.9.2|ant |/opt/IBM/ant |
|Cloud Foundry CLI 6.14 |cf | /opt/IBM/cf |
|Gradle 1.12|gradle |/opt/IBM/gradle |
|Gradle 2.9 |gradle2 |/opt/IBM/gradle2 |
|IBM Cloud CLI (bx) 0.13.0 |ibmcloud |/usr/local/ibmcloud/bin/ibmcloud |
|IBM Java (predeterminado)|java |/opt/IBM/java |
|IBM Java 7 x86_64-71 |java7 |/opt/IBM/java7 |
|IBM Java 8 x86_64-80|java8 |/opt/IBM/java8 |
|Apache Maven 3.2.1 |maven |/opt/IBM/maven |
|IBM Node |node |/opt/IBM/node |
|IBM Rational Team Concert&trade; SCM Tools |RTC-SCM-Tools |/opt/IBM/RTC-SCM-Tools |
{: caption="Tabla 4. Nombres y vías de acceso de enlace para tiempos de ejecución y herramientas" caption-side="top"}

El entorno de conducto ofrece versiones de 64 bits de IBM Node 0.10, 0.10.48, 0.12, 0.12.17, 4.2, 4.4.5, 4.6.0, 6.2.2 y 6.7.0. Para elegir una versión, utilice el mandato export.

Por ejemplo, para utilizar Node 0.12.7, especifique este mandato:
`export PATH=/opt/IBM/node-v0.12/bin:$PATH`

Para utilizar Node 4.2.2, especifique este mandato:
`export PATH=/opt/IBM/node-v4.2/bin:$PATH`

### Módulos de Node

Los siguientes módulos de Node se instalan de forma global en el entorno del conducto:

* grunt@0.4.5
* grunt-cli@0.1.13
* grunt-contrib-concat@0.4.0
* grunt-contrib-jshint@0.10.0
* grunt-contrib-nodeunit@0.4.1
* grunt-contrib-qunit@0.5.1
* grunt-contrib-uglify@0.5.0
* grunt-contrib-watch@0.6.1
* karma@0.12.23
* karma-cli@0.0.4
* karma-jasmine@0.1.5
* karma-phantomjs-launcher@0.1.4
* phantomjs@1.9.10
