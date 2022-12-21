---
unique-page-id: 42762762
description: 'Configuración de la conexión de Marketo: [!DNL Marketo Measure] - Documentación del producto'
title: Configuración de la conexión de Marketo
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
source-git-commit: 391d2f42c0ee7e0b9e36c8257d23a6e942e4a9fa
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Configuración de la conexión de Marketo {#set-up-marketo-connection}

Así es como configurar la conexión a Marketo.

>[!PREREQUISITES]
>
>[Crear una función de usuario solo de API](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) para la conexión Medida/Marketo Engage de Marketo.

1. En [!DNL Marketo Measure], haga clic en **[!UICONTROL Mi cuenta]** y seleccione **[!UICONTROL Configuración]**.

   ![](assets/set-up-marketo-connection-1.png)

1. En [!UICONTROL Integraciones], haga clic en **[!UICONTROL Conexiones]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Haga clic en **[!UICONTROL Configurar nueva conexión CRM]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Haga clic en el **[!UICONTROL Connect]** situado junto a Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. En una pestaña nueva, inicie sesión en la cuenta de Marketo Engage. Vaya a **Administrador** > **Servicios Web**. Desplácese hacia abajo hasta la API de REST. Resalte y guarde la URL del extremo y del servicio de identidad. Los necesitarás en un poco.

   ![](assets/set-up-marketo-connection-5.png)

1. Todavía en el Marketo Engage, seleccione **LaunchPoint** en el árbol de la izquierda. Busque el servicio personalizado que desea conectar con Marketo Measure y haga clic en **Ver detalles**.

   ![](assets/set-up-marketo-connection-6.png)

1. Resalte y guarde el ID de cliente y el Secreto de cliente. Haga clic en **Cerrar**.

   ![](assets/set-up-marketo-connection-7.png)

1. Volver [!DNL Marketo Measure], rellene los campos con los datos que acaba de recopilar.

   ![](assets/set-up-marketo-connection-8.png)

1. Después de introducir los valores, haga clic en **[!UICONTROL Autenticar]**. La cuenta del Marketo Engage se conectará a [!DNL Marketo Measure].

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] realizará llamadas a la API de Marketo en su nombre sin consumir ninguno de los límites de la API de Marketo, por lo que no es necesario preocuparse por los límites de límite y la asignación de crédito con otras integraciones.
