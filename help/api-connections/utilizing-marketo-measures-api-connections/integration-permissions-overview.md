---
description: Información general sobre permisos de integración - [!DNL Marketo Measure] - Documentación del producto
title: Información general sobre permisos de integración
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 1c3cd5ac9999550003765a9e1ed8d538224fe8a9
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 4%

---

# Información general sobre permisos de integración {#integration-permissions-overview}

Esta guía describe los permisos necesarios para una integración perfecta con Marketo Measure, lo que garantiza que cada integración funcione de forma eficaz y sin problemas.

<table>
<thead>
  <tr>
    <th style="width:10%">Integración</th>
    <th style="width:20%">Tipo de datos
    <li>Datos de interacción web</li>
    <li>Datos del sistema B2B</li>
    <li>Datos de plataforma de publicidad</li></th>
    <th style="width:30%">Qué rastreamos</th>
    <th style="width:40%">Requisitos de permisos</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>Datos del sistema B2B    
</td>
    <td>Marketo Measure está realizando un seguimiento:
    <p>
    <li>Cuenta</li>
    <li>Campaña</li>
    <li>CampaignMember</li>
    <li>Contacto</li>
    <li>CurrencyConversionRange</li>
    <li>CurrencyStatus</li>
    <li>Eventos</li>
    <li>Historial de campos (posible cliente, contacto y oportunidad)</li>
    <li>Posible cliente</li>
    <li>Oportunidad</li>
    <li>OpportunityContactRole</li>
    <li>OpportunityHistory</li>
    <li>Tareas</li>
<p>
Los puntos de contacto creados y otros datos se escriben en campos bidimensionales personalizados de Cuenta, Campaña, Miembro de campaña, Caso, Contacto, Posible cliente y Oportunidad.</td>
    <td><b>Permisos de usuario de Salesforce Connected (obligatorio)</b>
    <p>
    <b>Conjunto De Permisos De Administrador De Marketo Measure Para Usuario Dedicado:</b> Permitir que el administrador de SFDC realice operaciones de CRUD en objetos de medida de marketing.
    <br>
    <b>Ver y editar conjunto de permisos de posibles clientes convertidos:</b> Esto permite a Marketo Measure decorar posibles clientes después de convertirlos en contactos.
    <br>
    <b>Casilla de verificación de usuario de marketing de Salesforce:</b> La casilla de verificación Usuario de marketing permite a los usuarios crear campañas y utilizar los asistentes de importación de campañas.
    <br>
    <b>Usuario estándar de Marketo Measure:</b> Permite al usuario leer registros de objetos de Marketo Measure.
    <p>
    <b>Permisos de campo estándar de Salesforce</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Objetos y acceso estándar de Salesforce</a>
    <p>
    <b>Permisos de campo personalizado de Salesforce</b>
    <br>
    Proporcionamos la configuración de funciones para albergar campos de fuerza de ventas personalizados que los clientes puedan utilizar. Si se definen estos ajustes de función, necesitamos acceso de LECTURA a cada uno de los campos de fuerza de ventas guardados en el ajuste de función (por ejemplo, si el valor de CustomLeadSourceField es igual a "LeadSource__c", se requiere acceso de LECTURA a este campo).
    </td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
