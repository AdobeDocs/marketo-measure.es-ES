---
unique-page-id: 42762762
description: 'Configuración de la conexión de Marketo: [!DNL Marketo Measure]'
title: Configuración de la conexión de Marketo
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 1%

---

# Configuración de la conexión de Marketo {#set-up-marketo-connection}

A continuación se indica cómo configurar la conexión con Marketo.

>[!PREREQUISITES]
>
>[Crear un rol de usuario solo de API](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) para el [!DNL Marketo Measure]/conexión de Marketo Engage.

1. Entrada [!DNL Marketo Measure], haga clic en **[!UICONTROL Mi cuenta]** y seleccione. **[!UICONTROL Configuración]**.

   ![](assets/set-up-marketo-connection-1.png)

1. En [!UICONTROL Integraciones], haga clic en **[!UICONTROL Conexiones]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Clic **[!UICONTROL Configurar nueva conexión CRM]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Haga clic en **[!UICONTROL Connect]** junto a Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. En una pestaña nueva, inicie sesión en su cuenta de Marketo Engage. Ir a **Administrador** > **Servicios web**. Desplácese hacia abajo hasta API de REST. Resalte y guarde el punto de conexión y la URL del servicio de identidad. Los necesita en los siguientes pasos.

   ![](assets/set-up-marketo-connection-5.png)

1. Aún en Marketo Engage, seleccione **LaunchPoint** en el árbol de la izquierda. Busque el servicio personalizado que desea conectar con Marketo Measure y haga clic en **Ver detalles**.

   ![](assets/set-up-marketo-connection-6.png)

1. Resalte y guarde el ID de cliente y el secreto de cliente. Haga clic en **Cerrar**.

   ![](assets/set-up-marketo-connection-7.png)

1. Volver a entrar [!DNL Marketo Measure], rellene los campos con los datos que ha recopilado.

   ![](assets/set-up-marketo-connection-8.png)

1. Una vez introducidos los valores, haga clic en **[!UICONTROL Autenticar]**. Su cuenta de Marketo Engage está conectada a [!DNL Marketo Measure].

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] realiza llamadas a la API de Marketo en su nombre sin consumir ninguno de los límites de la API de Marketo, por lo que no debe preocuparse por los límites y la asignación de crédito con otras integraciones.
