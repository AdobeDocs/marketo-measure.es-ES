---
unique-page-id: 18874706
description: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos, Marketo Measure, documentación del producto'
title: 'Restricciones de sesión de seguridad: direcciones IP para Lista de permitidos'
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
TQID: https://experienceleague.adobe.com/Ka7ff5qarBVEm4JdSGCbaUM3Mrug0r3ZOPSKPrnc3Zo
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 84
ht-degree: 8%

---

# Restricciones de sesión de seguridad: Direcciones IP a lista de permitidos {#security-session-restrictions-ip-addresses-to-allowlist}

Si hay [Configuración de seguridad de sesión](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"} que impide que direcciones IP específicas inserten o extraigan datos en su instancia de [!DNL Salesforce], necesitaremos los siguientes intervalos de IP incluidos en la lista de permitidos para permitir que [!DNL Marketo Measure] inserte datos en [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Para agregar [!DNL Marketo Measure] IP a los intervalos de IP fiables en Salesforce, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de administración]** > **[!UICONTROL Controles de seguridad]** > **[!UICONTROL Acceso a la red]** > **[!UICONTROL Nuevo]**.

![](assets/1.png)
