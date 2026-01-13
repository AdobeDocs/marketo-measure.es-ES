---
description: 'Configurar la conexión de Marketo:  [!DNL Marketo Measure]'
title: Configuración de la conexión de Marketo
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---


# Configuración de la conexión de Marketo {#set-up-marketo-connection}

A continuación se indica cómo configurar la conexión con Marketo.

>[!PREREQUISITES]
>
>[Cree un rol de usuario solo API](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html?lang=es){target="_blank"} para la conexión [!DNL Marketo Measure]/Marketo Engage.

1. En [!DNL Marketo Measure], haga clic en la lista desplegable **[!UICONTROL Mi cuenta]** y seleccione **[!UICONTROL Configuración]**.

   ![Menú desplegable Mi cuenta de Marketo Measure con la opción Configuración](assets/set-up-marketo-connection-1.png)

1. En [!UICONTROL Integraciones], haga clic en **[!UICONTROL Conexiones]**.

   ![Menú de integraciones con la opción Conexiones](assets/set-up-marketo-connection-2.png)

1. Haga clic en **[!UICONTROL Configurar nueva conexión de CRM]**.

   ![Botón Configurar nueva conexión de CRM](assets/set-up-marketo-connection-3.png)

1. Haga clic en el botón **[!UICONTROL Conectar]** que está junto a Marketo.

   ![Botón de conexión junto a la opción de integración de Marketo](assets/set-up-marketo-connection-4.png)

1. En una pestaña nueva, inicie sesión en su cuenta de Marketo Engage. Vaya a **Administración** > **Servicios web**. Desplácese hacia abajo hasta API de REST. Resalte y guarde el punto de conexión y la URL del servicio de identidad. Los necesita en los siguientes pasos.

   ![Página de servicios web de Marketo que muestra el extremo de la API REST y las direcciones URL de identidad](assets/set-up-marketo-connection-5.png)

1. En Marketo Engage, seleccione **LaunchPoint** en el árbol de la izquierda. Busque el servicio personalizado que desea conectar con Marketo Measure y haga clic en **Ver detalles**.

   ![Menú LaunchPoint con servicio personalizado y opción Ver detalles](assets/set-up-marketo-connection-6.png)

1. Resalte y guarde el ID de cliente y el secreto de cliente. Haga clic en **Cerrar**.

   ![Detalles del servicio LaunchPoint que muestran el ID de cliente y el secreto de cliente](assets/set-up-marketo-connection-7.png)

1. En [!DNL Marketo Measure], rellene los campos con los datos que ha recopilado.

   ![Formulario de conexión de Marketo con campos de extremo y credenciales](assets/set-up-marketo-connection-8.png)

1. Después de escribir los valores, haga clic en **[!UICONTROL Autenticar]**. Su cuenta de Marketo Engage está conectada a [!DNL Marketo Measure].

   ![Mensaje de confirmación de conexión de Marketo correcto](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >[!DNL Marketo Measure] hace llamadas a la API de Marketo en tu nombre sin consumir ninguno de tus límites de API de Marketo, por lo que no hay necesidad de preocuparse por los límites y la asignación de crédito con otras integraciones.
