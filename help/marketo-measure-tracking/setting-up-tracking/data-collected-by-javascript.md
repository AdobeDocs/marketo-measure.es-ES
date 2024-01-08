---
description: Datos recopilados por JavaScript - [!DNL Marketo Measure] - Documentación del producto
title: Datos recopilados por JavaScript
feature: Tracking
source-git-commit: 4953d6c51a87669ced0a13e2a54810d14976585c
workflow-type: ht
source-wordcount: '232'
ht-degree: 100%

---

# Datos recopilados por JavaScript {#data-collected-by-javascript}

Obtenga información sobre los datos recopilados por Marketo Measure JavaScript tras la implementación.

**Solicitud de ejemplo:**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure recopila los siguientes datos comunes para todos los tipos de solicitudes:

<table>
<thead>
  <tr>
    <th>Origen</th>
    <th>Nombre</th>
    <th>Tipo de datos</th>
    <th>Finalidad</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Encabezado de solicitud</td>
    <td>Dirección IP</td>
    <td>cadena</td>
    <td>La ubicación del usuario se infiere mediante la búsqueda de GeoIP. Estos datos son temporales y no se almacenan de forma permanente.</td>
  </tr>
  <tr>
    <td>Encabezado de solicitud</td>
    <td>Cadena de agente de usuario</td>
    <td>cadena</td>
    <td>Determina qué dispositivo está utilizando el usuario.</td>
  </tr>
  <tr>
    <td>Parámetro de consulta</td>
    <td>_biz_u</td>
    <td>cadena</td>
    <td>ID de cookie de Bizible.</td>
  </tr>
  <tr>
    <td>Parámetro de consulta</td>
    <td>_biz_l</td>
    <td>cadena</td>
    <td>Dirección URL de la página actual.</td>
  </tr>
  <tr>
    <td>Parámetro de consulta</td>
    <td>_biz_t</td>
    <td>long</td>
    <td>Marca de tiempo de actividad.</td>
  </tr>
  <tr>
    <td>Parámetro de consulta</td>
    <td>_biz_i</td>
    <td>cadena</td>
    <td>Título de la página actual.</td>
  </tr>
</tbody>
</table>

Además de los datos comunes anteriores, bizible.js también adjunta datos adicionales en función de los tipos de solicitud, como se especifica a continuación:

<table>
<thead>
  <tr>
    <th>Tipo de solicitud</th>
    <th>Ruta de solicitud</th>
    <th>Parámetro de consulta adicional</th>
    <th>Tipo de datos</th>
    <th>Finalidad</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Vista de página</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>cadena</td>
    <td>Dirección URL de la página del referente.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>cadena</td>
    <td>Resolución de pantalla del cliente con hash.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>cadena</td>
    <td>Parámetro opcional. Si este parámetro está presente, indica que el inquilino configura bizible.js para esperar el consentimiento del usuario antes de realizar el seguimiento y que bizsible.js ha recibido el consentimiento del usuario para realizar el seguimiento.</td>
  </tr>
  <tr>
    <td>Envíos de formularios</td>
    <td>/frm</td>
    <td>Correo electrónico</td>
    <td>cadena</td>
    <td>Dirección de correo electrónico de texto sin formato.</td>
  </tr>
  <tr>
    <td>Asignación de ID de usuario</td>
    <td>/u</td>
    <td>mapType</td>
    <td>enum</td>
    <td>Qué tipo de asignación de ID de usuario ha detectado bizible.js (ID de Marketo Munchkin y ECID de Adobe)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>mapValue</td>
    <td>cadena</td>
    <td>El valor real de ID de cookie de terceros de la integración anterior.</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible es el antiguo nombre de Marketo Measure.
