---
description: Guía de OAuth with [!DNL Azure Active Directory] for Dynamics CRM para usuarios de Marketo Measure
title: OAuth con [!DNL Azure Active Directory]  para Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# OAuth con [!DNL Azure Active Directory] para Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## Quién se ve afectado {#who-s-affected}

Esta configuración es para nuevos clientes de [!DNL Marketo Measure] que usan Dynamics CRM con una cuenta de [!DNL Azure Active Directory] (AAD), o para clientes que desean migrar de su nombre de usuario y contraseña heredados a [!DNL Azure Active Directory] con OAuth.

>[!NOTE]
>
>Para ambos casos, AAD está configurado aquí para facilitar la conexión de la instancia de Dynamics en [!DNL Marketo Measure] como proveedor de datos.

## Configurar nueva aplicación {#set-up-new-application}

1. Inicie sesión en [Azure Portal](https://portal.azure.com/#home).

1. Seleccione el inquilino de Azure AD haciendo clic en su cuenta en la esquina superior derecha de la página, luego en la opción de navegación Cambiar directorio y, a continuación, seleccione el inquilino adecuado. Omita este paso si solo tiene un inquilino de Azure AD en su cuenta o si ya ha seleccionado el inquilino de Azure AD adecuado.

   ![](assets/bizible-taxonomy-1.png)

1. Busque &quot;[!DNL Azure Active Directory]&quot; en la barra de búsqueda y haga clic en el nombre para abrir.

   ![](assets/creating-2e-1.png)

1. Haga clic en **[!UICONTROL Registros de aplicación]** en el menú de la izquierda.

   ![](assets/getting-dynamics-1.png)

1. Haga clic en **[!UICONTROL Nuevo registro]** en la parte superior.

   ![](assets/getting-dynamics-10.png)

1. Siga las indicaciones y cree una aplicación. No importa si es una aplicación web o una aplicación cliente pública (móvil y de escritorio), pero si desea ejemplos específicos para aplicaciones web o aplicaciones cliente públicas, consulte [quickstarts](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview).\
   a. Nombre es el nombre de la aplicación y describe la aplicación a los usuarios finales.\
   b. En Tipos de cuenta admitidos, seleccione Cuentas en cualquier directorio organizativo y cuentas personales de Microsoft.\
   c. Proporcione el URI de redireccionamiento. En las aplicaciones web, esta es la dirección URL base de la aplicación en la que los usuarios pueden iniciar sesión. Por ejemplo, `http://localhost:12345`. Para clientes públicos (móviles y de escritorio), Azure AD lo utiliza para devolver respuestas de token. Introduzca un valor específico para la aplicación. Por ejemplo, `http://MyFirstAADApp`.

1. Una vez completado el registro, Azure AD asigna a su aplicación un identificador de cliente único (el ID de aplicación). Necesita este valor en la siguiente sección, así que cópielo desde la página de la aplicación.

1. Para encontrar su aplicación en el portal de Azure, haga clic en **[!UICONTROL Registros de aplicación]** y, a continuación, haga clic en **[!UICONTROL Todas las aplicaciones]**. Abra la aplicación recién creada

1. Haga clic en **[!UICONTROL Autenticación]** en el menú de la izquierda.

   ![](assets/getting-dynamics-11.png)

1. Agregue las direcciones URL de redireccionamiento [!DNL Marketo Measure]: `https://apps.bizible.com/OAuth2` y `https://apps.bizible.com/OAuth2?identityOnly=true` a la lista de direcciones URL de redireccionamiento.

   ![](assets/getting-dynamics-2.png)

1. Vaya a la pestaña Permisos de API y asegúrese de que los permisos correctos están asignados a la aplicación.

   ![](assets/getting-dynamics-3.png)

1. Desde aquí, escriba &quot;[!UICONTROL enterprise]&quot; en el cuadro de búsqueda y haga clic en **[!UICONTROL Aplicaciones empresariales]**.

   ![](assets/getting-dynamics-4.png)

1. De nuevo, busque y abra la nueva aplicación en la lista de aplicaciones.

1. En la ficha Permisos, haga clic en **[!UICONTROL Conceder consentimiento de administrador para (nombre de instancia)]**.

   ![](assets/getting-dynamics-5.png)

1. Haga clic en **[!UICONTROL Aceptar]**.

   ![](assets/getting-dynamics-6.png)

1. En la ficha &quot;[!UICONTROL Usuarios y grupos]&quot;, asegúrese de que los &quot;Usuarios y grupos&quot; válidos estén asignados a la aplicación.

   ![](assets/getting-dynamics-7.png)

## Creación de un usuario de aplicación {#creating-an-application-user}

Una vez finalizado el registro de la aplicación, se puede crear un usuario de la aplicación.

1. Vaya al entorno de Common Data Service (`https://[org].crm.dynamics.com`).

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Seguridad]** > **[!UICONTROL Usuarios]**.

1. Elija **[!UICONTROL Usuarios de la aplicación]** en el filtro de vista.

1. Seleccione **[!UICONTROL + Nuevo]**.

1. En el formulario Usuario de aplicación, introduzca la información necesaria.

   >[!NOTE]
   >
   >* La información del nombre de usuario no debe coincidir con un usuario que exista en [!DNL Azure Active Directory].
   >
   >* En el campo ID de aplicación, introduzca el ID de aplicación de la aplicación que registró anteriormente en Azure AD.

1. Si la configuración es correcta, después de seleccionar **[!UICONTROL Guardar]**, los campos **[!UICONTROL ID de aplicación URI]** y **[!UICONTROL ID de objeto de Azure AD]** se rellenarán automáticamente con los valores correctos.

1. Antes de salir del formulario de usuario, elija **[!UICONTROL Administrar funciones]** y asigne una función de seguridad a este usuario de la aplicación para que el usuario de la aplicación pueda acceder a los datos de organización deseados.

## Conexión de la instancia de Dynamics mediante OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Al configurar la conexión de Dynamics por primera vez, siga los pasos del 1 al 5 de la sección &quot;CRM como proveedor de datos&quot; en [este artículo](/help/marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. Cuando se le soliciten credenciales de OAuth, rellene los campos ID de cliente, Secreto de cliente y URI de ID de aplicación que se configuraron en la sección anterior.

a. El ID de cliente es el ID del paso #7 de la sección anterior. Si no lo ha anotado, el ID de aplicación se muestra en la Configuración del registro de la aplicación.

b. Secreto de cliente es el secreto de aplicación creado en Azure Portal para su aplicación en Certificados y secretos.

![](assets/getting-dynamics-8.png)

c. El URI del ID de aplicación es la dirección URL de la API web de destino (recurso protegido). Para encontrar la dirección URL del id. de aplicación, en Azure Portal, haga clic en [!DNL Azure Active Directory], luego en Registros de aplicaciones, abra la página Configuración de la aplicación y haga clic en Propiedades. También puede ser un recurso externo como `https://graph.microsoft.com`. Normalmente, es la dirección URL de la instancia de Dynamics.

1. Después de hacer clic en **[!UICONTROL Enviar]**, se le pedirá que inicie sesión con [!DNL Azure Active Directory]. Si la autenticación se realiza correctamente, su cuenta de Dynamics se conectará como proveedor de datos en [!DNL Marketo Measure].

## Volver a autenticar su cuenta de Dynamics {#re-authenticating-your-dynamics-account}

1. Cuando esté en la aplicación [!DNL Marketo Measure], vaya a **[!UICONTROL Mi configuración]** > **[!UICONTROL Configuración]** > **[!UICONTROL Conexiones]**.

1. Haga clic en el icono de clave en la sección CRM junto a la conexión de Dynamics.

1. Cuando se hace clic en la tecla, aparece una ventana emergente y se le solicita que introduzca el ID de cliente, el secreto de cliente y el URI de ID de aplicación, de forma similar al flujo de suscripción.

   ![](assets/getting-dynamics-9.png)

1. Después de hacer clic en **[!UICONTROL Enviar]**, se le pedirá que inicie sesión con [!DNL Azure Active Directory]. Si la autenticación se realiza correctamente, la cuenta de Dynamics se vuelve a autorizar en [!DNL Marketo Measure].
