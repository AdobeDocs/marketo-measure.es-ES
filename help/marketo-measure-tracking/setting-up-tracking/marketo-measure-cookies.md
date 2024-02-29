---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies: [!DNL Marketo Measure]"
title: “Cookies de [!DNL Marketo Measure]”
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 99%

---

# Cookies de Marketo Measure {#marketo-measure-cookies}

Obtenga información sobre las distintas cookies de [!DNL Marketo Measure] que se cargan en el sitio al aplicar el JavaScript de [!DNL Marketo Measure] a las páginas de aterrizaje. Esta información puede resultar útil para el equipo de desarrollo web durante la implementación.

>[!IMPORTANT]
>
>Debido a cuestiones de privacidad, las cookies de terceros están a punto de desaparecer. La obsolescencia de las cookies de terceros anunciada por Google Chrome en el tercer trimestre de 2024 marca el final de esta forma de seguimiento. Por consiguiente, Adobe dejará de utilizar las funciones de Marketo Measure que dependan de cookies de terceros; en concreto Seguimiento entre dominios y Atribución de visualización, que utilizan la cookie de impresión de Google/DoubleClick. Ninguna otra función de Marketo Measure se verá afectada. El uso de cookies de origen tampoco se verá afectado. En vista de la programación de Google, la fecha prevista de obsolescencia de las dos funciones anteriores es el 1/6/2024. Los datos relacionados recopilados antes de esta fecha permanecerán a disposición de los clientes de Adobe.

<table>
<thead>
  <tr>
    <th>Nombre de la cookie</th>
    <th>Tipo de cookie</th>
    <th>Finalidad</th>
    <th>Vencimiento</th>
    <th>¿Tiene establecido el indicador seguro?<br></th>
    <th>¿Tiene establecido el indicador solo HTTP?</th>
    <th>Configurador de cookies</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>Origen</td>
    <td>Identifique de forma exclusiva a un usuario en el dominio actual.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>Origen</td>
    <td>Un número de secuencia que Marketo Measure incluye para todas las solicitudes con fines de diagnóstico interno.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>Origen</td>
    <td>Una cookie que almacena información del usuario diversa, como el envío de formularios, la migración entre dominios, el píxel de visualización, el estado de exclusión de seguimiento, etc.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>Origen</td>
    <td>Almacena temporalmente los datos de análisis hasta que se envían correctamente al servidor de Marketo Measure.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>Origen</td>
    <td>Lista de sumas de comprobación de datos ABTests de Optimizely y Visual Web Optimizer que ya se han notificado, lo que impide que bizible.js vuelva a enviar los datos recopilados.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>Origen</td>
    <td>Lista de sumas de comprobación notificadas por eventos de Bizible para evitar que bizible.js vuelva a enviar los datos recopilados.</td>
    <td>1 año</td>
    <td>No</td>
    <td>No</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>Origen</td>
    <td>ID de usuario universal para identificar a un usuario en varios dominios, solo aplicable a los inquilinos con integración que omite las limitaciones de ITP.</td>
    <td>1 año</td>
    <td>Sí</td>
    <td>No</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Terceros, dominio=.<a href="http://bizible.com/">bizible.com</a></td>
    <td>ID de usuario universal para identificar a un usuario en varios dominios.</td>
    <td>1 año</td>
    <td>Sí</td>
    <td>No</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Terceros, dominio=.<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>Asignación entre el ID de cookie de Marketo Measure en el dominio del inquilino y su ID de cookie de impresión Doubleclick.</td>
    <td>1 año</td>
    <td>Sí</td>
    <td>No</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

Si se activa una advertencia de firewall de aplicaciones web (Web Application Firewall, WAF) durante la configuración de JavaScript. Los usuarios pueden deshabilitar esa regla de WAF o incluir las cookies en la lista de permitidos, como en el siguiente ejemplo:

![](assets/marketo-measure-cookies-1.png)
