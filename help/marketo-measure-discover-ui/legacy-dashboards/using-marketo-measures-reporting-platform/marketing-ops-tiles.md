---
unique-page-id: 34406495
description: 'Mosaicos de operaciones de marketing: [!DNL Marketo Measure]'
title: Mosaicos de operaciones de marketing
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 4%

---

# Mosaicos de operaciones de marketing {#marketing-ops-tiles}

Las operaciones de marketing le permiten validar y diagnosticar [!DNL Marketo Measure] datos con una visibilidad completa de los puntos de contacto individuales por posibles clientes, contactos, cuentas, campañas y oportunidades.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><br></td> 
   <td><p><strong>ID de cuenta</strong></p></td> 
   <td><p><strong>Nombre de la cuenta</strong></p></td> 
   <td><p><strong>ID de Opp</strong></p></td> 
   <td><p><strong>Nombre de Opp</strong></p></td> 
   <td><p><strong>Cliente potencial o identificación del contacto</strong></p></td> 
   <td><p><strong>Cliente potencial o correo electrónico del contacto</strong></p></td> 
   <td><p><strong>ID de campaña</strong></p></td> 
   <td><p><strong>Oportunidad ganada</strong></p></td> 
   <td><p><strong>Fecha de creación de Opp</strong></p></td> 
   <td><p><strong>Cerrar fecha de apertura</strong></p></td> 
   <td><p><strong>Fecha de Touchpoint</strong></p></td> 
   <td><p><strong>Modelo de atribución</strong></p></td> 
  </tr> 
  <tr> 
   <td><p><strong>Cuentas</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Oportunidad</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Contactos</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Clientes potenciales</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Campañas</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
 </tbody> 
</table>

## Mosaico de cuenta {#account-tile}

![](assets/one-1.png)

Muestra los siguientes datos relacionados con las cuentas especificadas.

**Las cuentas deben tener datos de Touchpoint (solo aplicable si tiene habilitado ABM)**

-Account ID: ID de cuenta en CRM

-Account Name: Nombre de cuenta en CRM

Fecha de creación: Fecha de creación de la cuenta en CRM

* Desglose: Consulte Fecha de creación por hora, minuto, hora

-Sitio web: valor encontrado en el campo Sitio web de la cuenta

-Clasificación de participación: puntuación de participación predictiva (PES) rellenada por [!DNL Marketo Measure]^1

-Oportunidades: Número de oportunidades conectadas a la cuenta

* Profundizar: Ver los detalles de las oportunidades asociadas

-Contacts: número de contactos enumerados en esta cuenta

* Profundizar: Ver los detalles de los contactos asociados

-Posibles clientes: número de posibles clientes asignados a esta cuenta mediante la asignación de posibles clientes a cuenta^1

* Profundizar: vea los detalles de los posibles clientes asignados a la cuenta

-Puntos de contacto de atribución: Número de puntos de contacto de atribución del comprador de la cuenta

* Desglose: Consulte Detalles del punto de contacto de atribución del comprador (ID, correo electrónico, fecha del punto de contacto, nombre de cuenta, campaña, canal, subcanal, tipo de contacto de marketing, modelo de atribución)

-Touchpoints: número de puntos de contacto que tienen los contactos de esta cuenta^2

* Profundizar: consulte Puntos de contacto en los detalles del punto de contacto de la cuenta (ID, correo electrónico, fecha del punto de contacto, nombre de la cuenta, campaña, canal, subcanal, tipo de contacto de marketing)

>[!NOTE]
>
>Si tiene ABM, se mostrarán los puntos de contacto relacionados con los posibles clientes que se han asignado a través de la asignación de posibles clientes a cuentas.

## Mosaico de oportunidad {#opportunity-tile}

![](assets/two-1.png)

Muestra los siguientes datos relacionados con las oportunidades especificadas.

-ID de oportunidad: ID de oportunidad en CRM

-Nombre de oportunidad: Nombre de oportunidad en CRM

-Account Name: nombre de cuenta asociado a la oportunidad

Fecha de creación: Fecha de creación de la oportunidad en CRM

Desglose: Consulte Fecha de creación por hora, minuto, hora

-Cerrar fecha: fecha de cierre de la oportunidad en CRM

Desglosar: consulte Cerrar fecha por hora, minuto, hora

-Importe: El importe total de la oportunidad

-Contacts: número de contactos asociados a la oportunidad

Profundizar: Ver los detalles de los contactos asociados

-Puntos de contacto de atribución: Número de puntos de contacto de atribución del comprador relacionados

Desglose: Consulte Detalles del punto de contacto de atribución del comprador (ID, correo electrónico, fecha del punto de contacto, nombre de cuenta, campaña, canal, subcanal, tipo de contacto de marketing, modelo de atribución)

## Mosaico de contactos {#contacts-tile}

![](assets/three-1.png)

Muestra los siguientes datos relacionados con los contactos especificados.

-ID de contacto: ID de contacto en CRM

Correo electrónico: dirección de correo electrónico del registro de contacto

-Created Date: Fecha de creación del contacto en CRM

* Desglose: Consulte Fecha de creación por hora, minuto, hora

-Account Name: nombre de cuenta asociado al contacto

-Puntos de contacto de atribución: Número de puntos de contacto de atribución del comprador para el contacto

* Desglose: Consulte Detalles del punto de contacto de atribución del comprador (ID, correo electrónico, fecha del punto de contacto, nombre de cuenta, campaña, canal, subcanal, tipo de contacto de marketing, modelo de atribución)

-Touchpoints: número de puntos de contacto del comprador para el contacto

* Profundizar: consulte Contactos en los detalles de Touchpoint de la cuenta (ID, correo electrónico, fecha de Touchpoint, nombre de la cuenta, campaña, canal, subcanal, tipo de contacto de marketing)

## Mosaico de posibles clientes {#leads-tile}

![](assets/four-1.png)

Muestra los siguientes datos relacionados con los posibles clientes especificados.

-ID de posible cliente: ID de posible cliente en CRM

Correo electrónico: dirección de correo electrónico del registro de posibles clientes

Fecha de creación automática: cuando se creó el posible cliente en CRM

* Desglose: Consulte Fecha de creación por hora, minuto, hora

-Empresa (del posible cliente): la empresa que aparece en el registro en CRM rellenado por el cliente

-Account Name: nombre de la cuenta [!DNL Marketo Measure] se rellena en función de nuestra asignación de cliente potencial a cuenta

-Touchpoints: número de puntos de contacto asociados al posible cliente

* Profundizar: consulte Contactos en los detalles de Touchpoint de la cuenta (ID, correo electrónico, fecha de Touchpoint, nombre de la cuenta, campaña, canal, subcanal, tipo de contacto de marketing)

## Mosaico Campañas {#campaigns-tile}

![](assets/five-1.png)

Muestra los siguientes datos relacionados con las campañas especificadas.

-ID de campaña: ID de campaña en CRM

-Campaign Name: Nombre de la campaña en CRM

Gasto en campañas: el gasto [!DNL Marketo Measure] ha registrado asociado a la campaña

-Modelo de atribución: Esto mostrará la atribución adecuada en función del modelo seleccionado

Puntos de contacto de atribución: número de puntos de contacto de atribución del comprador asociados a la campaña o campañas

* Desglose: Consulte Detalles del punto de contacto de atribución del comprador (ID, correo electrónico, fecha del punto de contacto, nombre de cuenta, campaña, canal, subcanal, tipo de contacto de marketing, modelo de atribución)

-Touchpoints: el número de puntos de contacto asociados a las campañas

* Profundizar: consulte Contactos en los detalles de Touchpoint de la cuenta (ID, correo electrónico, fecha de Touchpoint, nombre de la cuenta, campaña, canal, subcanal, tipo de contacto de marketing)
