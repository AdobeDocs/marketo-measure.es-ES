---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Cookies"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
source-git-commit: 3a13ab3e497652d1975e69280a3d224ac95504aa
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Cookies de medida de Marketo {#marketo-measure-cookies}

Obtenga información sobre las distintas [!DNL Marketo Measure] Las cookies que se cargan en el sitio al aplicar la variable [!DNL Marketo Measure] JavaScript a las páginas de aterrizaje. Esta información puede ser útil para el equipo de desarrollo web durante la implementación.

| **Nombre de la cookie** | **Tipo de cookie** | **Objetivo** |
|---|---|---|
| _BUID | Terceros, guardados en dominio .bizible.com | ID de usuario universal para identificar al mismo usuario en los dominios de varios clientes. |
| _biz_uid | Origen | ID de usuario en el dominio actual. |
| _biz_sid | Origen | ID de sesión del usuario. |
| _biz_flagA | Origen | Una sola cookie que almacena información múltiple, como si el usuario ha enviado o no un formulario, ha realizado una migración entre dominios, ha enviado un píxel de visualización, ha excluido el seguimiento, etc. |
| _biz_nA | Origen | Número de secuencia que [!DNL Marketo Measure] incluye para todas las solicitudes, con fines de diagnóstico interno |
| _biz_dfsA | Origen | Almacena temporalmente los datos de envío de formularios que se producen antes de [!DNL bizible.js] recibe un JS de configuración para determinar si el formulario de seguimiento en HTTPS está habilitado o no. |
| _biz_pendingA | Origen | Almacena temporalmente datos de análisis que no se han enviado correctamente a [!DNL Marketo Measure] servidor aún. |

Si se activa una advertencia de Firewall de aplicación web (WAF) durante la configuración de JavaScript, los usuarios pueden deshabilitar esa regla WAF o incluir en la lista de permitidos las cookies, como se muestra a continuación:

![](assets/marketo-measure-cookies-1.png)
