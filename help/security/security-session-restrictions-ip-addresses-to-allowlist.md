---
description: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos'
title: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos'
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 8%

---


# Restricciones de sesión de seguridad: Direcciones IP a lista de permitidos {#security-session-restrictions-ip-addresses-to-allowlist}

Si hay [Configuración de seguridad de sesión](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"} que impide que direcciones IP específicas inserten o extraigan datos en su instancia de [!DNL Salesforce], necesitaremos los siguientes intervalos de IP incluidos en la lista de permitidos para permitir que [!DNL Marketo Measure] inserte datos en [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Para agregar [!DNL Marketo Measure] IP a los intervalos de IP fiables en Salesforce, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de administración]** > **[!UICONTROL Controles de seguridad]** > **[!UICONTROL Acceso a la red]** > **[!UICONTROL Nuevo]**.

![Página de acceso a la red de Salesforce para agregar intervalos de IP de confianza](assets/1.png)
