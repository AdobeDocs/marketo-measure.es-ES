---
unique-page-id: 18874706
description: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos, Marketo Measure, documentación del producto'
title: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos'
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 8%

---

# Restricciones de sesión de seguridad: Direcciones IP a lista de permitidos {#security-session-restrictions-ip-addresses-to-allowlist}

Si hay [Configuración de seguridad de sesión](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"} que impida que direcciones IP específicas inserten o extraigan datos en su instancia de [!DNL Salesforce], necesitaremos los siguientes intervalos de IP incluidos en la lista de permitidos para permitir que [!DNL Marketo Measure] inserte datos en [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0: 20.186.163.15

Para agregar [!DNL Marketo Measure] IP a los intervalos de IP fiables en Salesforce, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de administración]** > **[!UICONTROL Controles de seguridad]** > **[!UICONTROL Acceso a la red]** > **[!UICONTROL Nuevo]**.

![](assets/1.png)
