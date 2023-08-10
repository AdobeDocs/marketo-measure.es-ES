---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies: [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Cookies"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Cookies de Marketo Measure {#marketo-measure-cookies}

Obtenga información sobre los distintos [!DNL Marketo Measure] Cookies que se cargan en el sitio al aplicar el [!DNL Marketo Measure] JavaScript a sus páginas de aterrizaje. Esta información puede resultar útil para el equipo de desarrollo web durante la implementación.

| **Nombre de cookie** | **Tipo de cookie** | **Finalidad** |
|---|---|---|
| _BUID | Terceros, guardados en el dominio .bizible.com | ID de usuario universal para identificar el mismo usuario en los dominios de varios clientes. |
| _biz_uid | Primera parte | ID de usuario en el dominio actual. |
| _biz_sid | Primera parte | ID de sesión del usuario. |
| _biz_flagsA | Primera parte | Una sola cookie que almacena información múltiple, como si el usuario ha enviado o no un formulario, ha realizado una migración entre dominios, ha enviado una vista a través de un píxel, se ha excluido del seguimiento, etc. |
| _biz_nA | Primera parte | Número de secuencia que [!DNL Marketo Measure] incluye para todas las solicitudes, con fines de diagnóstico interno |
| _biz_dfsA | Primera parte | Almacena temporalmente los datos de envío de formularios que se producen antes de [!DNL bizible.js] recibe un JS de configuración para determinar si el formulario de seguimiento en HTTPS está habilitado o no. |
| _biz_pendingA | Primera parte | Almacena temporalmente datos de análisis que no se han enviado correctamente a [!DNL Marketo Measure] servidor aún. |

Si se activa una advertencia de Firewall de aplicaciones web (WAF) durante la configuración de JavaScript, los usuarios pueden deshabilitar esa regla de WAF o incluir en la lista de permitidos las cookies, como en el siguiente ejemplo:

![](assets/marketo-measure-cookies-1.png)
