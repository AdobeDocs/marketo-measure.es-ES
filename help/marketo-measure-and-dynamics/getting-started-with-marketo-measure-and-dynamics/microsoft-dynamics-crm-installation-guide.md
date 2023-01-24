---
unique-page-id: 18874763
description: "[!DNL Microsoft Dynamics] Guía de instalación de CRM - Medida de Marketo - Documentación del producto"
title: "[!DNL Microsoft Dynamics] Guía de instalación de CRM"
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
source-git-commit: 9de82556ca543aa8e6c53242eacae5c87019886c
workflow-type: tm+mt
source-wordcount: '1353'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] Guía de instalación de CRM {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

## Versiones admitidas {#supported-versions}

[!DNL Marketo Measure] admite lo siguiente [!DNL Microsoft Dynamics CRM] versiones:

* [!DNL Microsoft Dynamics 2016] (en línea y locales)
* [!DNL Microsoft Dynamics 365] (en línea y locales)

Para conexión y autenticación, [!DNL Marketo Measure] admite las siguientes versiones de Servicios Federados de Active Directory (ADFS):

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## Instalación de la solución administrada {#install-the-managed-solution}

[Descargar e instalar](assets/marketo-measure-dynamics-extension.zip) el archivo zip en Dynamics CRM.

**[!UICONTROL Configuración]** > **[!UICONTROL Personalizaciones]** > **[!UICONTROL Soluciones]** > **[!UICONTROL Importar]** (botón) > **[!UICONTROL Elegir archivo]**.

![](assets/1.png)

>[!NOTE]
>
>Las dos capturas de pantalla siguientes pueden variar ligeramente con respecto a las suyas, ya que se tomaron durante una actualización de la solución.

![](assets/2.png)

![](assets/3.png)

## [!DNL Marketo Measure] Permisos de usuario {#marketo-measure-user-permissions}

Se recomienda crear una [!DNL Marketo Measure] El usuario de Dynamics permite exportar e importar datos a través de para evitar problemas con otros usuarios de CRM. Tenga en cuenta el nombre de usuario y la contraseña, así como la dirección URL del extremo que se utilizará al crear la variable [!DNL Marketo Measure] cuenta.

## Funciones de seguridad {#security-roles}

Si su organización utiliza las funciones de seguridad de Dynamics, asegúrese de que el usuario conectado o la [!DNL Marketo Measure] El usuario tiene suficientes permisos de lectura y escritura para las entidades requeridas.

Las funciones de seguridad se encuentran aquí: **[!UICONTROL Configuración]** > **[!UICONTROL Seguridad]** > **[!UICONTROL Funciones de seguridad]**.

Para [!DNL Marketo Measure] entidades personalizadas, necesitaremos permisos completos en todas nuestras entidades.

>[!NOTE]
>
>Los usuarios que vayan a cerrar oportunidades también necesitarán los permisos completos.

![](assets/4.png)

Para las entidades estándar de Dynamics, consulte la [!DNL Marketo Measure] Documento de esquema de Dynamics. En un nivel superior, [!DNL Marketo Measure] solo necesita leer en ciertas entidades para recopilar los datos adecuados y escribir en los campos personalizados que se instalarán con la solución administrada. No crearemos nuevos registros estándar ni actualizaremos ningún campo estándar.

## Incluir puntos de contacto en los diseños de página: {#include-touchpoints-on-page-layouts}

1. Para cada entidad, vaya al Editor de formularios. Puede encontrar esto en **[!UICONTROL Configuración]** > **[!UICONTROL Personalizaciones]** > **[!UICONTROL Personalizar el sistema]** > `[Entity]` > **[!UICONTROL Forms]**. O puede encontrarlo en la configuración mientras está viendo un registro.

   * Las entidades que se van a configurar: Cuenta, oportunidad, contacto, posible cliente y campaña.

   * Para configurar Campañas, debe activar la opción &quot;Sincronización de campañas&quot; en **[!UICONTROL CRM]** > **[!UICONTROL Campañas]**.

   ![](assets/5.png)

1. Diseños de página: primero agregue un &quot;[!UICONTROL Una columna]&quot; en la sección en la que desea que se activen los puntos de contacto. En esa nueva columna, necesitamos una subcuadrícula agregada a cada formulario dentro de las entidades Cuenta, Oportunidad, Contacto y Poder.

   ![](assets/6.png)

   ![](assets/7.png)

1. Seleccione el objeto (puntos de contacto de atribución de comprador o puntos de contacto de comprador) que se debe procesar en la subcuadrícula, que depende de la relación de objeto. De forma opcional, cambie las columnas que se mostrarán haciendo clic en el botón Editar . La solución administrada ha establecido un diseño predeterminado.

   Subcuadrícula de puntos de contacto de atribución de comprador: cuentas, oportunidades y contacto\
   Subcuadrícula de puntos de contacto del comprador: posibles clientes y contactos

   ![](assets/8.png)

1. Una vez que haya terminado de actualizar el formulario, publique y guarde los cambios.

## Consideraciones relacionadas con el esquema {#schema-related-considerations}

**Ingresos**

[!DNL Marketo Measure] apunta al campo Ingresos reales estándar de forma predeterminada. Si no utiliza esto, explique cómo informar sobre los ingresos a su ingeniero de soluciones o a su gestor de éxito, ya que se necesitará un flujo de trabajo personalizado.

**Fecha de cierre**

[!DNL Marketo Measure] apunta al campo Fecha de cierre real fuera del cuadro. Si no utiliza esto o también utiliza el campo Fecha de cierre estimada , explique su proceso a su ingeniero de soluciones o a su gestor de éxito. Puede que sea necesario tener en cuenta ambos campos en un flujo de trabajo personalizado.

## Configuración de Adobe Admin Console y del proveedor de identidad {#set-up-your-adobe-admin-console-and-identity-provider}

El primer paso para utilizar [!DNL Marketo Measure] es crear e iniciar sesión en el Adobe Admin Console aprovisionado. Si todavía no ha recibido el correo electrónico con instrucciones de inicio de sesión, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

Como producto dentro de Adobe Suite, [!DNL Marketo Measure] aprovecha la funcionalidad completa de Adobe Admin Console para Identity Management. Se pueden usar más recursos [se encuentra aquí](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

Recomendamos revisar todos los recursos, las prácticas recomendadas y las opciones disponibles para [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Para obtener instrucciones y información sobre la configuración de Identity Management en Adobe Admin Console, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

Para facilitar la autenticación y autorización de los usuarios con su [!DNL Marketo Measure] instancias, se requieren los siguientes pasos en Adobe Admin Console:

**Configuración de [!DNL Marketo Measure] Tarjeta de producto**

Al acceder a Adobe Admin Console, verá su [!DNL Marketo Measure] Las instancias de producto presentes en la sección Información general .

![](assets/microsoft-dynamics-crm-installation-guide-8a.png)

Al hacer clic en [!DNL Marketo Measure] La tarjeta de producto le mostrará todas sus [!DNL Marketo Measure] instancias. De forma predeterminada, cada [!DNL Marketo Measure] La instancia tiene su propio perfil con el prefijo &#39;[!DNL Marketo Measure]&#39;. Cualquier administrador o usuario agregado a este o a otro perfil dentro de esta instancia podrá iniciar sesión en [!DNL Marketo Measure].

![](assets/microsoft-dynamics-crm-installation-guide-8b.png)

No es necesario realizar ninguna acción para crear un nuevo perfil dentro de la variable [!DNL Marketo Measure] Instancias de producto.

Para empezar a agregar usuarios que puedan acceder a [!DNL Marketo Measure], consulte la [Adición [!DNL Marketo Measure] Los administradores y [!DNL Marketo Measure] Usuarios](#adding-marketo-measure-admins-and-marketo-measure-users) a continuación.

## Adición [!DNL Marketo Measure] Los administradores y [!DNL Marketo Measure] Usuarios {#adding-marketo-measure-admins-and-marketo-measure-users}

El siguiente paso es conceder acceso al [!DNL Marketo Measure] al agregar usuarios. Esto se puede hacer en el directorio de administradores y usuarios del [!DNL Marketo Measure] tarjeta de producto.

| Tipo de usuario | Descripción |
|---|---|
| Administradores | son administradores y usuarios potentes del [!DNL Marketo Measure] Aplicación con plena capacidad de actualizar y administrar [!DNL Marketo Measure]-opciones de configuración específicas |
| Usuarios | son usuarios estándar de la variable [!DNL Marketo Measure] Aplicación con permisos de solo lectura dentro de [!DNL Marketo Measure] aplicación |

Al agregar un usuario a su grupo respectivo, verá sus [Tipo de identidad enumerado](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>Para que sea un [!DNL Marketo Measure] administrador (en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), se debe agregar un usuario como usuario _y_ un administrador para cualquier [!DNL Marketo Measure] perfil de producto dentro de la variable [!DNL Marketo Measure] tarjeta de producto.

**Iniciar sesión en[!DNL Marketo Measure]**

Una vez que un usuario ha sido agregado a un perfil de producto, puede acceder a su [!DNL Marketo Measure] para las instancias, elija el **Iniciar sesión con Adobe ID** opción en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/microsoft-dynamics-crm-installation-guide-15.png)

## Configuración de las conexiones y los proveedores de datos {#configuring-your-connections-and-data-providers}

Una vez que haya iniciado sesión en la [!DNL Marketo Measure] y se han configurado como usuario en Adobe Admin Console, el siguiente paso es configurar las distintas conexiones de datos.

**CRM como proveedor de datos**

1. En [!DNL Marketo Measure] haga clic en la **[!UICONTROL Mi cuenta]** y seleccione **[!UICONTROL Configuración]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. En [!UICONTROL Integraciones] en la navegación de la izquierda, haga clic en **[!UICONTROL Conexiones]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. Haga clic en el **[!UICONTROL Configurar nueva conexión CRM]** botón.

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. Junto a [!UICONTROL Microsoft Dynamics CRM], haga clic en **[!UICONTROL Connect]** botón.

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. Select [!UICONTROL Credenciales] o [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >Para obtener más información sobre OAuth, visite [este artículo](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). Si tiene alguna pregunta sobre el proceso, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

1. En este ejemplo, hemos elegido Credenciales. Introduzca sus credenciales y haga clic en **[!UICONTROL Siguiente]**.

Después de la conexión, verá los detalles de su conexión con Dynamics en la lista Conexiones CRM/MAP.

**Conexiones de la cuenta del anuncio**

Para conectar sus cuentas de publicidad con [!DNL Marketo Measure], comience por visitar [!UICONTROL Conexiones] dentro de la pestaña [!DNL Marketo Measure] aplicación.

1. Siga los pasos 1 y 2 desde arriba _CRM como proveedor de datos_ para obtener más información.

1. Haga clic en el **[!UICONTROL Configurar nueva conexión CRM]** botón.

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. Seleccione la plataforma que desee.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

Para [!DNL Marketo Measure] para realizar el seguimiento de las actividades web, existen varios pasos para la configuración.

1. Haga clic en el **[!UICONTROL Mi cuenta]** y seleccione **[!UICONTROL Configuración de la cuenta]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. Escriba su número de teléfono. Para el sitio web, introduzca el dominio raíz principal para el que se usará [!DNL Marketo Measure] seguimiento en el sitio web. Haga clic en **[!UICONTROL Guardar]** cuando haya terminado.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >Para agregar varios dominios raíz, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

1. La variable [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) luego debe colocarse en todo el sitio y en las páginas de aterrizaje. Se recomienda codificar el script dentro del encabezado de las páginas de aterrizaje o agregarlo a través de un sistema de Tag Management como [Administrador de etiquetas de Google](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >De forma predeterminada, [!DNL Marketo Measure] exporta 200 registros por crédito de API cada vez que un trabajo envía datos a su CRM. Para la mayoría de los clientes, esto proporciona el equilibrio óptimo entre los créditos de API que consume [!DNL Marketo Measure] y requisitos de recursos de CPU en CRM. Sin embargo, para los clientes con configuraciones de CRM complejas, como flujos de trabajo y déclencheur, un tamaño de lote más pequeño puede ser útil para mejorar el rendimiento de CRM. Con este fin, [!DNL Marketo Measure] permite a los clientes configurar el tamaño del lote de exportación de CRM. Esta configuración está disponible en la página Configuración > CRM > General de la página [!DNL Marketo Measure] la aplicación web y los clientes pueden elegir entre tamaños de lote de 200 (predeterminado), 100, 50 o 25.
   >
   >Al modificar esta configuración, tenga en cuenta que los tamaños de lote más pequeños consumirán más créditos API de su CRM. Es aconsejable reducir el tamaño del lote solo si está experimentando un tiempo de espera de CPU o una carga de CPU alta en su CRM.

   >[!NOTE]
   >
   >Cuando se deshabilita la exportación de datos de Marketo Measure a Dynamics, no se eliminarán los datos existentes. Para obtener ayuda con la eliminación de datos existentes, póngase en contacto con el soporte técnico de Dynamics.
