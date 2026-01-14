---
description: Guía de datos recopilados por JavaScript para usuarios de Marketo Measure
title: Datos recopilados por JavaScript
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 77%

---

# Datos recopilados por JavaScript {#data-collected-by-javascript}

Obtenga información sobre los datos recopilados por Marketo Measure JavaScript tras la implementación.

**Solicitud de ejemplo:**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure recopila los siguientes datos comunes para todos los tipos de solicitudes:

| Origen | Nombre | Tipo de datos | Finalidad |
| --- | --- | --- | --- |
| Encabezado de solicitud | Dirección IP | cadena | La ubicación del usuario se infiere mediante la búsqueda de GeoIP. Estos datos son temporales y no se almacenan de forma permanente. |
| Encabezado de solicitud | Cadena de agente de usuario | cadena | Determina qué dispositivo está utilizando el usuario. |
| Parámetro de consulta | `_biz_u` | cadena | ID de cookie de Bizible. |
| Parámetro de consulta | `_biz_l` | cadena | Dirección URL de la página actual. |
| Parámetro de consulta | `_biz_t` | long | Marca de tiempo de actividad. |
| Parámetro de consulta | `_biz_i` | cadena | Título de la página actual. |

Además de los datos comunes anteriores, bizible.js también adjunta datos adicionales en función de los tipos de solicitud, como se especifica a continuación:

| Tipo de solicitud | Ruta de solicitud | Parámetro de consulta adicional | Tipo de datos | Finalidad |
| --- | --- | --- | --- | --- |
| Vista de página | `/ipv` | `_biz_r` | cadena | Dirección URL de la página del referente. |
|  |  | `_biz_h` | cadena | Resolución de pantalla del cliente con hash. |
|  |  | `_biz_c` | cadena | Parámetro opcional. Si este parámetro está presente, indica que el inquilino configura `bizible.js` para esperar el consentimiento del usuario antes de realizar el seguimiento y que `bizible.js` ha recibido el consentimiento del usuario para realizar el seguimiento. |
| Envíos de formularios | `/frm` | `eMail` | cadena | Dirección de correo electrónico de texto sin formato. |
| Asignación de ID de usuario | `/u` | `mapType` | enum | Qué tipo de asignación de ID de usuario `bizible.js` detectó (Marketo Munchkin id y Adobe ECID) |
|  |  | `mapValue` | cadena | El valor real de ID de cookie de terceros de la integración anterior. |

>[!NOTE]
>
>Bizible es el antiguo nombre de Marketo Measure.
