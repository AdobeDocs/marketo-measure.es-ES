---
description: Información general sobre permisos de integración - [!DNL Marketo Measure] - Documentación del producto
title: Información general sobre permisos de integración
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: d7ded9075f7f5831314d59294327f1e4928baf8a
workflow-type: tm+mt
source-wordcount: '636'
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
    <td>Dynamics</td>
    <td>Datos del sistema B2B</td>
    <td>Marketo Measure está realizando un seguimiento:
    <p>
    <li>Cuenta
<li>ActivityParty
<li>ActivityPointer
<li>Campaña
<li>CampaignItem (CampaignList en nuestro sistema)
<li>CampaignResponse (miembro de Campaign en nuestro sistema)
<li>Contacto
<li>Posible cliente
<li>Lista (MarketingList en nuestro sistema)
<li>ListMember (MarketingListMember en nuestro sistema)
<li>Oportunidad
<li>Organización
<li>TransactionCurrency (CurrencyConversionRange y CurrencyStatus en nuestro sistema)
<li>Cita, Actividad de campaña, Correo electrónico, Fax, Resolución de incidentes, Carta, Llamada de teléfono, Cita recurrente, Maestro, Cita de servicio, Tarea
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
Los puntos de contacto creados y otros datos se escriben en campos bizbibles personalizados en Account, Campaign, CampaignResponse, Contact, Lead, List, Opportunity y PhoneCall</td>
    <td><b>Permisos de usuario de Marketo Measure</b>
<p>
Se recomienda crear un usuario de Marketo Measure específico dentro de Dynamics para exportar e importar datos a través de a fin de evitar problemas con otros usuarios en su CRM. Tome nota del nombre de usuario y la contraseña, así como de la dirección URL del extremo, ya que este se utilizará al crear la cuenta de Marketo Measure.
<p>
<b>Funciones de seguridad</b>
<p>
Si su organización utiliza funciones de seguridad de Dynamics, asegúrese de que el usuario conectado o el usuario de Marketo Measure específico tenga suficientes permisos de lectura y escritura para las entidades requeridas.
<br>
Aquí se encuentran las funciones de seguridad: Configuración &gt; Seguridad &gt; Funciones de seguridad
<br>
Para las entidades personalizadas de Marketo Measure, necesitaremos permisos completos en todas nuestras entidades.
<p>
<b>Permisos de campo de Dynamics Standard</b>
<br>
<a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Esquema de Marketo Measure Dynamics</a>
<p>
<b>Permisos de campo personalizado de Dynamics</b>
<br>
Necesitamos acceso de LECTURA para cualquier campo de la entidad de posible cliente o contacto que el cliente desee utilizar para las reglas personalizadas de Suprimir/Eliminar configuración de punto de contacto.
<br>
Necesitamos acceso de LECTURA para cualquier campo de la entidad de cliente potencial u oportunidad que el cliente desee utilizar para las reglas de segmentos o la asignación de etapas.
<br>
Necesitamos acceso de LECTURA para cualquier campo de las entidades Campaign, CampaignResponse y List que el cliente desee utilizar para sincronizar miembros de Campaign/MarketingList.
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>Datos de plataforma de publicidad</td>
    <td>Nos integramos con Facebook para lo siguiente:
<p>
<li>Importar datos de anuncios de clientes</li>
<li>Importar datos de coste de anuncios de clientes</li>
<li>Actualizar los anuncios del cliente añadiendo parámetros de URL</li>
<p>
Marketo Measure realiza un seguimiento de cuentas, campañas, grupos de publicidad, anuncios, ID de filtro y direcciones URL.</td>
    <td><li>El permiso ads_management es necesario para crear campañas, gestionar anuncios o recuperar métricas de publicidad.</li>
<li>Se requiere el permiso de correo electrónico para permitir que los usuarios inicien sesión en su correo electrónico de Facebook.</li>
<p>
<b>Ámbitos</b>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>Cree campañas mediante programación, administre anuncios y recupere métricas.</li>
<li>Cree herramientas de administración de anuncios que proporcionen soluciones innovadoras y un valor diferenciado para los anunciantes.</li>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/email">email</a>
<br>
<li>Comunicarse con las personas y permitirles iniciar sesión en la aplicación con la dirección de correo electrónico asociada a su perfil de Facebook.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Bing</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>