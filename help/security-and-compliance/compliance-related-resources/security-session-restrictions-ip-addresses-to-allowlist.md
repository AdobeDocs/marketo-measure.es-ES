---
unique-page-id: 18874706
description: Restricciones de sesión de seguridad - Direcciones IP a Lista de permitidos - Marketo Measure - Documentación del producto
title: 'Restricciones de sesión de seguridad: direcciones IP a Lista de permitidos'
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
source-git-commit: b9d9e3110e87be0d6311c17b0ef76dfad8735a00
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 3%

---

# Restricciones de sesión de seguridad: Direcciones IP a Lista de permitidos {#security-session-restrictions-ip-addresses-to-allowlist}

Si hay [Configuración de seguridad de sesión](https://help.salesforce.com/articleView?id=admin_sessions.htm&amp;type=0){target="_blank"} en su lugar para evitar que direcciones IP específicas introduzcan o extraigan datos en su [!DNL Salesforce] por ejemplo, necesitamos los siguientes rangos de IP incluidos en la lista de permitidos para permitir [!DNL Marketo Measure] para insertar datos en [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Para agregar [!DNL Marketo Measure] IP a los intervalos de IP de confianza en Salesforce, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de administración]** > **[!UICONTROL Controles de seguridad]** > **[!UICONTROL Acceso a la red]** > **[!UICONTROL Nuevo]**.

![](assets/1.png)
