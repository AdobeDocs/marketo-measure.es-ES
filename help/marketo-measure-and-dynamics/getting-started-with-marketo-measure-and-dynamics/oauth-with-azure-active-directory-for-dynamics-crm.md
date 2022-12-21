---
unique-page-id: 37357059
description: OAuth con [!DNL Azure Active Directory] para Dynamics CRM - [!DNL Marketo Measure] - Documentación del producto
title: OAuth con [!DNL Azure Active Directory] para Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# OAuth con [!DNL Azure Active Directory] para Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## ¿Quién está afectado? {#who-s-affected}

Esta configuración es para [!DNL Marketo Measure] clientes que utilizan Dynamics CRM con un [!DNL Azure Active Directory] (AAD) o para clientes que desean migrar de su nombre de usuario y contraseña heredados a [!DNL Azure Active Directory] con OAuth.

>[!NOTE]
>
>Para ambos casos, AAD está configurado aquí para facilitar la conexión de la instancia de Dynamics en [!DNL Marketo Measure] como proveedor de datos.

## Configurar nueva aplicación {#set-up-new-application}

1. Inicie sesión en su [Azure Portal](https://portal.azure.com/#home).

1. Para elegir su inquilino de Azure AD, haga clic en su cuenta en la esquina superior derecha de la página, luego haga clic en el navegador Switch Directory y seleccione el inquilino apropiado (omita este paso si solo tiene un inquilino de Azure AD en su cuenta o si ya ha seleccionado el inquilino de Azure AD adecuado).

   ![](assets/setup-2.png)

1. Buscar &quot;[!DNL Azure Active Directory]&quot; en la barra de búsqueda y haga clic en el nombre para abrirlo.

   ![](assets/setup-3.png)

1. Haga clic en **[!UICONTROL Registros de aplicaciones]** en el menú de la izquierda.

   ![](assets/setup-4.png)

1. Haga clic en **[!UICONTROL Nuevo registro]** en la parte superior.

   ![](assets/setup-5.png)

1. Siga las indicaciones y cree una nueva aplicación. No importa si se trata de una aplicación web o una aplicación cliente pública (móvil y escritorio), pero si desea ejemplos específicos para aplicaciones web o aplicaciones cliente públicas, consulte nuestra [inicio rápido](https://docs.microsoft.com/en-us/azure/active-directory/develop/v1-overview).\
   a. Nombre es el nombre de la aplicación y describe su aplicación para los usuarios finales.\
   b. En Tipos de cuentas compatibles, seleccione Cuentas en cualquier directorio organizativo y cuentas personales de Microsoft.\
   c. Proporcione el URI de redirección. En el caso de las aplicaciones web, esta es la URL base de la aplicación en la que los usuarios pueden iniciar sesión. Por ejemplo, `http://localhost:12345`. Para el cliente público (móvil y escritorio), Azure AD lo utiliza para devolver respuestas de token. Introduzca un valor específico para la aplicación. Por ejemplo, `http://MyFirstAADApp`.

1. Una vez que haya completado el registro, Azure AD asignará a su aplicación un identificador de cliente único (el ID de aplicación). Necesita este valor en la siguiente sección, así que cópielo desde la página de la aplicación.

1. Para encontrar la aplicación en el portal de Azure, haga clic en **[!UICONTROL Registros de aplicaciones]** y haga clic en **[!UICONTROL Todas las aplicaciones]**. Abra la aplicación recién creada

1. Haga clic en **[!UICONTROL Autenticación]** en el menú de la izquierda.

   ![](assets/setup-9.png)

1. Agregue la variable [!DNL Marketo Measure] direcciones URL de redireccionamiento: `https://apps.bizible.com/OAuth2` y `https://apps.bizible.com/OAuth2?identityOnly=true` a la lista de direcciones URL de redireccionamiento.

   ![](assets/setup-10.png)

1. Vaya a la pestaña Permisos de API y asegúrese de que se han asignado los permisos correctos a la aplicación.

   ![](assets/setup-10a.png)

1. Desde aquí, introduzca &quot;[!UICONTROL enterprise]&quot; en el cuadro de búsqueda y haga clic en **[!UICONTROL Aplicaciones empresariales]**.

   ![](assets/setup-11.png)

1. De nuevo, busque y abra la nueva aplicación en la lista de aplicaciones.

1. En la ficha Permisos, haga clic en **[!UICONTROL Conceder consentimiento de administrador para (nombre de instancia)]**.

   ![](assets/setup-13a.png)

1. Haga clic en **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. Desde el &quot;[!UICONTROL Usuarios y grupos]&quot;, asegúrese de que los &quot;Usuarios y grupos&quot; válidos estén asignados a la aplicación.

   ![](assets/setup-14.png)

## Creación de un usuario de aplicación {#creating-an-application-user}

Una vez que se haya realizado el registro de la aplicación, se puede crear un usuario de la aplicación.

1. Vaya al entorno del Servicio de datos común (`https://[org].crm.dynamics.com`).

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Seguridad]** > **[!UICONTROL Usuarios]**.

1. Choose **[!UICONTROL Usuarios de aplicaciones]** en el filtro de vista.

1. Select **[!UICONTROL + Nuevo]**.

1. En el formulario Usuario de aplicación, introduzca la información requerida.

   >[!NOTE]
   >
   >* La información del nombre de usuario no debe coincidir con un usuario que exista en la variable [!DNL Azure Active Directory].
   >
   >* En el campo ID de aplicación , introduzca el ID de aplicación de la aplicación que registró anteriormente en Azure AD.


1. Si la configuración es correcta, después de seleccionar **[!UICONTROL Guardar]**, el **[!UICONTROL URI de ID de aplicación]** y **[!UICONTROL Azure AD Object Id]** se rellenarán automáticamente con los valores correctos.

1. Antes de salir del formulario de usuario, elija **[!UICONTROL Administrar funciones]** y asignar una función de seguridad a este usuario de aplicación para que el usuario de la aplicación pueda acceder a los datos de organización deseados.

## Conexión de la instancia de Dynamics mediante OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Al configurar la conexión de Dynamics por primera vez, siga los pasos 1-5 de la sección &quot;CRM as a Data Provider&quot; en [este artículo](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. Cuando se le soliciten las credenciales de OAuth, rellene el ID de cliente, el Secreto del cliente y el URI del ID de aplicación que se configuraron en la sección anterior.

a. El ID de cliente es el ID del paso 7 de la sección anterior. Si no lo escribió, el ID de la aplicación se muestra en la Configuración del registro de la aplicación.

b. Secreto del cliente es el secreto de aplicación creado en Azure Portal para su aplicación en Certificados y secretos.

![](assets/creating-2e.png)

c. El URI del ID de aplicación es la URL de la API web de destino (recurso seguro). Para buscar la URL del ID de aplicación, en Azure Portal, haga clic en [!DNL Azure Active Directory], haga clic en Registros de aplicación, abra la página Configuración de la aplicación y, a continuación, haga clic en Propiedades. También puede ser un recurso externo como `https://graph.microsoft.com`. Normalmente es la URL de la instancia de Dynamics.

1. Después de hacer clic en **[!UICONTROL Submit]**, se le pedirá que inicie sesión con [!DNL Azure Active Directory]. Cuando la autenticación se realice correctamente, la cuenta de Dynamics se conectará como proveedor de datos dentro de [!DNL Marketo Measure].

## Volver a autenticar su cuenta de Dynamics {#re-authenticating-your-dynamics-account}

1. Cuando esté en el [!DNL Marketo Measure] aplicación, vaya a **[!UICONTROL Mis ajustes]** > **[!UICONTROL Configuración]** > **[!UICONTROL Conexiones]**.

1. Haga clic en el icono de la clave en la sección CRM junto a la conexión con Dynamics.

1. Una vez que haga clic en la clave, aparecerá una ventana emergente y se le pedirá que introduzca el ID de cliente, el Secreto del cliente y el URI del ID de la aplicación, de forma similar al flujo de suscripción.

   ![](assets/re-authenticating-3.png)

1. Después de hacer clic en **[!UICONTROL Submit]**, se le pedirá que inicie sesión con [!DNL Azure Active Directory]. Cuando la autenticación se realice correctamente, la cuenta de Dynamics se volverá a autorizar en [!DNL Marketo Measure].
