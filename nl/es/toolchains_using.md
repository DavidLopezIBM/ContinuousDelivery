---

copyright:
  years: 2015, 2018
lastupdated: "2018-2-26"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Utilización de cadenas de herramientas
{: #toolchains-using}

Las cadenas de herramientas abiertas están disponibles en los entornos Público y Dedicado en {{site.data.keyword.Bluemix}}. Puede utilizar una cadena de herramientas para que sea productiva en su trabajo diario de desarrollo, despliegue y operaciones. Una vez que se ha configurado una cadena de herramientas, es posible añadir, eliminar o configurar integraciones de herramientas y gestionar el acceso a la cadena de herramientas.
{: shortdesc}

## Configuración de una integración de herramienta
{: #configuring_a_tool_integration}

Si ha aplazado la configuración de una integración de herramientas al crear una cadena de herramientas, se mostrará un botón **Configurar** en su tarjeta. Si ha configurado una integración de herramientas al crear una cadena de herramientas, puede actualizar los valores de configuración.

1. En el panel de control de DevOps, en la página **Cadenas de herramientas**, pulse una cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, tarjeta Entrega continua, pulse **Ver cadena de herramientas** y, a continuación, **Visión general**.
1. Si necesita configurar una integración de herramienta por primera vez, en su tarjeta, pulse **Configurar**.

  ![Botón de configuración](images/toolchain_tile_configure.png)

 Cuando haya terminado de configurar la integración de la herramienta, pulse **Guardar integración**.

1. Si necesita actualizar la configuración de una integración de herramienta, en su tarjeta, pulse el menú para acceder a las opciones de configuración.

  ![Menú de configuración](images/toolchain_tile_menu.png)

 **Consejo**: Algunos de las integraciones de herramientas están preconfiguradas y no requieren ningún parámetro de configuración. Puede actualizar los valores de configuración sólo para las integraciones de herramientas que ha configurado.

 Cuando haya terminado de configurar los ajustes, pulse **Guardar integración**. Para obtener más información sobre cómo configurar las integraciones de herramientas específicas, consulte [Configurar integraciones de herramientas](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.

## Adición de una integración de herramienta
{: #adding_a_tool_integration}

Puede añadir y configurar integraciones de herramientas para su cadena de herramientas. Las integraciones de herramientas disponibles difieren en función de si utiliza {{site.data.keyword.Bluemix_notm}} público o {{site.data.keyword.Bluemix_notm}} dedicado.

1. En el panel de control de DevOps, en la página **Cadenas de herramientas**, pulse una cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, tarjeta Entrega continua, pulse **Ver cadena de herramientas** y, a continuación, **Visión general**.
1. Para ver una lista de integraciones de herramientas que añadir, pulse **Añadir una herramienta**.
1. Pulse en la integración de herramientas que desee añadir.
1. Introduzca la información necesaria para configurar la integración de la herramienta.
1. Pulse **Crear integración** para añadir la integración de la herramienta en su cadena de herramientas.

## Eliminación de una integración de herramienta
{: #deleting_a_tool_integration}

Si suprime una integración de herramientas desde su cadena de herramientas, la supresión no se podrá deshacer.

1. En el panel de control de DevOps, en la página **Cadenas de herramientas**, pulse una cadena de herramientas para abrir la página Visión general correspondiente. Si lo prefiere, en la página Visión general de la app, tarjeta Entrega continua, pulse **Ver cadena de herramientas** y, a continuación, **Visión general**.
1. En la tarjeta de la integración de herramientas que desea eliminar, pulse el menú para acceder a las opciones de configuración.
1. Para eliminar la integración de herramienta de su cadena de herramientas, pulse **Suprimir**.
1. Confirme la acción pulsando **Suprimir**.  

## Gestión del acceso
{: #managing_access}

Puede conceder acceso a los usuarios a una cadena de herramientas si los añade a la organización con la que está asociada la cadena de herramientas y a la lista de control de accesos de la cadena de herramientas. Cada cadena de herramientas está asociada con una organización específica y cualquier usuario que sea miembro de la organización se puede añadir a la lista de control de accesos correspondiente a las cadenas de herramientas asociadas. La organización en la que está trabajando actualmente se muestra en la barra de menús. Para acceder a un conjunto distinto de cadenas de herramientas, cambie a una organización distinta.

**Sugerencia:** Debe añadir usuarios a la organización de la cadena de herramientas en la región donde está alojada la cadena de herramientas. Como las cadenas de herramientas están actualmente alojadas sólo en la región EE.UU. Sur, debe añadir usuarios a la organización en la región EE.UU. Sur. Si la cadena de herramientas está configurada para desplegar apps en una región distinta, seguirá desplegando apps en dicha región.

Si utiliza {{site.data.keyword.Bluemix_notm}} dedicado para {{site.data.keyword.ghe_short}}, cuando añada usuarios a la organización y a los espacios de {{site.data.keyword.Bluemix_notm}}, los usuarios podrán iniciar una sesión en {{site.data.keyword.ghe_short}} con su ID y contraseña de {{site.data.keyword.Bluemix_notm}}. Cuando los usuarios inician sesión, se les crearán cuentas. Al añadir usuarios a la organización y a los espacios de {{site.data.keyword.Bluemix_notm}}, no se añadirán automáticamente al repositorio de {{site.data.keyword.ghe_short}}. Debe añadirlos alguien que tenga privilegios de administración para el repositorio. Para obtener más información, consulte [Utilización de GitHub Enterprise dedicado](/docs/services/ghededicated/index.html){: new_window}. Si utiliza su propia versión gestionada de {{site.data.keyword.ghe_short}}, siga los procedimientos internos.

###Consejos para gestionar el acceso a una cadena de herramientas

* Para gestionar el acceso a una cadena de herramientas, en el panel de control de DevOps, en la página **Cadenas de herramientas**, pulse la cadena de herramientas que desee gestionar y pulse **Gestionar**. Si lo prefiere, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas** y luego pulse **Gestionar**.

* Para otorgar acceso a todos los miembros de la organización de la cadena de herramientas, pulse **Añadir org**. Todos los miembros de dicha org podrán ver la cadena de herramientas.

* Puede otorgar privilegios de administrador a una org o a un usuario. Los administradores pueden modificar y suprimir la cadena de herramientas. Para otorgar privilegios de administrador, marque el recuadro de selección **ADMIN** para la organización o para el usuario.

* Si marca el recuadro de selección **ADMIN** para una organización, todos los miembros de dicha organización se convierten en administradores. Si añade miembros a la organización después de otorgar privilegios de administrador a la organización, dichos miembros reciben el mismo acceso que el resto de la organización.

* Para otorgar acceso a un usuario que es miembro de la organización de la cadena de herramientas, escriba el ID del usuario y pulse **Añadir usuario**. El usuario puede ver la cadena de herramientas.

* Para otorgar acceso a un usuario que no es miembro de la organización de la cadena de herramientas, siga estos pasos:

   a. En la barra de menús, pulse **Gestionar > Seguridad > Identidad y acceso**.

   b. En la fila del usuario al que desea asignar acceso, seleccione el menú **Acciones** y pulse **Asignar acceso**.

   c. Seleccione **Asignar acceso utilizando Cloud Foundry**.

   d. Seleccione **Asignar organización**.

   e. Asigne el acceso de usuario:

     * Seleccione una organización a la que añadir el usuario.

     * Asigne un rol de organización.

     * Seleccione una región.

     * Seleccione un espacio.

     * Asigne un rol para el espacio seleccionado en la organización.

     **Nota:** De forma predeterminada, los gestores de una organización tienen privilegios completos de administrador sobre todas las cadenas de herramientas asociadas a la organización. Para otorgar privilegios completos de administrador al usuario, seleccione el rol **Gestor**. Los roles Gestor de facturación y Auditor no afectan al acceso a la cadena de herramientas. Puede cambiar los roles más adelante en la página Directorio del equipo. Para obtener más información, consulte [Roles de Cloud Foundry](/docs/iam/cfaccess.html#cfaccess){: new_window}.

   Una vez que el usuario sea miembro de la organización, vuelva a la página Gestionar de la cadena de herramientas y añada el usuario a la cadena de herramientas.  


## Eliminación de una cadena de herramientas
{: #deleting_a_toolchain}

Puede eliminar una cadena de herramientas y especificar qué integraciones de herramienta asociadas desea eliminar. Al suprimir una cadena de herramientas, la supresión no se podrá deshacer.

1. En el panel de control de DevOps, en la página **Cadenas de herramientas**, pulse sobre la cadena de herramientas que desea suprimir. Como alternativa, en la página Visión general de la app, en la tarjeta de Entrega continua, pulse **Ver cadena de herramientas**.
1. Pulse el menú **Más acciones**, que se encuentra junto a **Ver app**.
1. Pulse **Suprimir**. Cuando se suprime una cadena de herramientas, también se suprimen todas sus integraciones de herramienta, lo que podría dar lugar a la supresión de los recursos que dichas integraciones gestionan.
1. Para confirmar la eliminación, escriba el nombre de la cadena de herramientas y pulse **Suprimir**.  

 **Sugerencia**: Cuando suprime GitHub, {{site.data.keyword.ghe_short}} o las herramientas de integración de {{site.data.keyword.gitrepos}}, el repositorio asociado no se suprime de GitHub, {{site.data.keyword.ghe_short}} ni {{site.data.keyword.gitrepos}}. Debe eliminar manualmente el repositorio.

##Realice una guía de aprendizaje: Uso de las cadenas de herramientas
{: #toolchain-tutorial}

Consulte estas guías en [IBM&reg; Cloud Garage Method ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage){:new_window}:

  * [Cree y utilice su primera cadena de herramientas utilizando la cadena de herramientas "Desarrollar una app de Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}.

  * [Añada una cadena de herramientas para una app ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/add-a-toolchain-to-an-app?task=2){:new_window}. 

  * [Utilice la cadena de herramientas "Desarrollar y probar microservicios en Cloud Foundry" ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}.
