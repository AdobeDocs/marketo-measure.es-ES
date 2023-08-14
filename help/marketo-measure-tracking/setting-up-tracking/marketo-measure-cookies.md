---
unique-page-id: 18874590
description: “Documentación del producto  [!DNL Marketo Measure] , cookies de [!DNL Marketo Measure]”
title: “Cookies de [!DNL Marketo Measure]”
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '205'
ht-degree: 100%

---

# Cookies de Marketo Measure {#marketo-measure-cookies}

Obtenga información sobre las distintas cookies de [!DNL Marketo Measure] que se cargan en el sitio al aplicar el JavaScript de [!DNL Marketo Measure] a las páginas de aterrizaje. Esta información puede resultar útil para el equipo de desarrollo web durante la implementación.

| **Nombre de la cookie** | **Tipo de cookie** | **Finalidad** |
|---|---|---|
| _BUID | Tercero, guardado en el dominio .bizible.com | ID de usuario universal para identificar el mismo usuario en los dominios de varios clientes. |
| _biz_uid | Origen | ID de usuario en el dominio actual. |
| _biz_sid | Origen | ID de sesión del usuario. |
| _biz_flagsA | Origen | Una sola cookie que almacena información múltiple, por ejemplo, si el usuario ha enviado o no un formulario, ha realizado una migración entre dominios, ha enviado una visualización a través de un píxel, se ha excluido del seguimiento, etc. |
| _biz_nA | Origen | Número de secuencia que [!DNL Marketo Measure] incluye para todas las solicitudes, con fines de diagnóstico interno |
| _biz_dfsA | Origen | Almacena temporalmente los datos de envío de formularios que se producen antes de que [!DNL bizible.js] reciba un JS de configuración para determinar si el formulario de seguimiento en HTTPS está habilitado o no. |
| _biz_pendingA | Origen | Almacena temporalmente datos de análisis que todavía no se han enviado correctamente a un servidor de [!DNL Marketo Measure]. |

Si se activa una advertencia de firewall de aplicaciones web (Web Application Firewall, WAF) durante la configuración de JavaScript. Los usuarios pueden deshabilitar esa regla de WAF o incluir las cookies en la lista de permitidos, como en el siguiente ejemplo:

![](assets/marketo-measure-cookies-1.png)
