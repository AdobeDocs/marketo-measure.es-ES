---
description: Configuración de la guía de conexión de Marketo para usuarios de Marketo Measure
title: Configuración de la conexión de Marketo
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---

# Configuración de la conexión de Marketo {#set-up-marketo-connection}

A continuación se indica cómo configurar la conexión con Marketo.

>[!PREREQUISITES]
>
>[Cree un rol de usuario solo API](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) para la conexión [!DNL Marketo Measure]/Marketo Engage.

1. En [!DNL Marketo Measure], haga clic en la lista desplegable **[!UICONTROL Mi cuenta]** y seleccione **[!UICONTROL Configuración]**.

   ![1. En Marketo Measure, haga clic en la lista desplegable Mi cuenta y &#x200B;](assets/set-connection-7.png)

1. En [!UICONTROL Integraciones], haga clic en **[!UICONTROL Conexiones]**.

   ![1. En Integraciones, haga clic en Conexiones.](assets/set-connection-8.png)

1. Haga clic en **[!UICONTROL Configurar nueva conexión de CRM]**.

   ![1. Haga clic en Configurar nueva conexión de CRM.](assets/set-connection-9.png)

1. Haga clic en el botón **[!UICONTROL Conectar]** que está junto a Marketo.

   ![1. Haga clic en el botón Conectar situado junto a Marketo.](assets/set-connection-5.png)

1. En una pestaña nueva, inicie sesión en su cuenta de Marketo Engage. Vaya a **Administración** > **Servicios web**. Desplácese hacia abajo hasta API de REST. Resalte y guarde el punto de conexión y la URL del servicio de identidad. Los necesita en los siguientes pasos.

   ![1. En una ficha nueva, inicie sesión en su cuenta de Marketo Engage.](assets/set-connection-6.png)

1. En Marketo Engage, seleccione **LaunchPoint** en el árbol de la izquierda. Busque el servicio personalizado que desea conectar con Marketo Measure y haga clic en **Ver detalles**.

   ![1. En Marketo Engage, seleccione LaunchPoint en el árbol del &#x200B;](assets/set-connection-4.png)

1. Resalte y guarde el ID de cliente y el secreto de cliente. Haga clic en **Cerrar**.

   ![1. Resalte y guarde el ID de cliente y el secreto de cliente. Haga clic en Cerrar.](assets/set-connection-3.png)

1. En [!DNL Marketo Measure], rellene los campos con los datos que ha recopilado.

   ![1. En Marketo Measure, rellene los campos con los datos &#x200B;](assets/set-connection-1.png)

1. Después de escribir los valores, haga clic en **[!UICONTROL Autenticar]**. Su cuenta de Marketo Engage está conectada a [!DNL Marketo Measure].

   ![1. Una vez introducidos los valores, haga clic en Autenticar. Su Marketo Engage](assets/set-connection-2.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] hace llamadas a la API de Marketo en tu nombre sin consumir ninguno de tus límites de API de Marketo, por lo que no hay necesidad de preocuparse por los límites y la asignación de crédito con otras integraciones.
