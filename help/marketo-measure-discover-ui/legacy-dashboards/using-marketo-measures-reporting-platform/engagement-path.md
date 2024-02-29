---
unique-page-id: 35586105
description: Ruta de participación - [!DNL Marketo Measure]
title: Ruta de participación
exl-id: 104d803f-9f40-4ab6-872d-6432f8c087e9
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 4%

---

# Ruta de participación {#engagement-path}

La ruta de participación le permite ver una vista completa de las participaciones de posibles clientes, contactos, cuentas y oportunidades desde el primer contacto hasta el cierre.

![](assets/one-2.png)

## Descripción del mosaico {#tile-description}

**Tipo de evento:** El tipo de punto de contacto (sesión, campaña de CRM, evento de CRM, tarea de CRM, impresión)

**Posición de Touchpoint del comprador:** Posición del punto de contacto del posible cliente/contacto

**Posición de Touchpoint de Atribución del Comprador:** Posición del punto de contacto de atribución del comprador de la oportunidad

**Fecha de Touchpoint:** Para fuentes en línea: fecha y hora en que se produjo la participación. Para eventos sin conexión: fecha y hora establecidas en Salesforce Campaign. Para actividades touchpoint: se hace referencia al campo de fecha del punto de contacto en la configuración de actividades

**Correo electrónico:** El correo electrónico asociado al compromiso

**Tipo de contacto de marketing:** Tipo de participación (visita web, formulario web, chat web, CRM, tipos de actividad)

**Canal:** Canal de marketing que propició la participación

**Medio:** Medio de participación

* Si la participación procede de una plataforma conectada a la API (AdWords/BingAds), el medio será CPC
* Si la página de aterrizaje de la participación contiene utm_medium, analizaremos
* Si la participación procede de una campaña de CRM, el medio procede del campo &quot;Tipo&quot; de la campaña de CRM

**Origen web:** Esta columna muestra el origen de la participación

* Si la participación procede de una plataforma conectada a la API, el origen web mostrará el nombre de la plataforma de publicidad
* Si el punto de contacto procede de una búsqueda orgánica, este campo mostrará el nombre del motor de búsqueda
* Si no es #1 o #2 y el valor utm_source está presente en la dirección URL de la página de aterrizaje del punto de contacto, ese valor se mostrará aquí
* Si no es #1 o #2 y no hay ningún valor utm_source presente, el dominio raíz de la dirección URL de referencia se mostrará aquí.
* Si nada de lo anterior, esto mostrará Web Direct o Web

**Primera interacción con la persona:** Esta columna muestra Sí o No si ese punto de contacto fue la primera interacción individual

**Ingresos atribuidos:** Esta columna muestra los ingresos atribuidos a ese punto de contacto en función del modelo de atribución seleccionado

## Descripción del filtro {#filter-description}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Nombre del filtro</th> 
   <th>Descripción</th> 
  </tr> 
  <tr> 
   <td><p>Nombre/ID de la cuenta</p></td> 
   <td><p>Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. Los valores de varios filtros tendrán una relación "o", lo que significa que el mosaico mostrará los resultados de ambos valores de filtro. Si alguno de los valores de filtro no es válido, el panel no producirá resultados para el valor no válido, pero seguirá filtrando a los valores de filtro válidos. No distingue mayúsculas de minúsculas.</p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre/ID de oportunidad</p></td> 
   <td><p>Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. Los valores de varios filtros tendrán una relación "o", lo que significa que el mosaico mostrará los resultados de ambos valores de filtro. Si alguno de los valores de filtro no es válido, el panel no producirá resultados para el valor no válido, pero seguirá filtrando a los valores de filtro válidos. No distingue mayúsculas de minúsculas.</p></td> 
  </tr> 
  <tr> 
   <td><p>Identificación/email del cliente potencial</p></td> 
   <td><p>Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. Los valores de varios filtros tendrán una relación "o", lo que significa que el mosaico mostrará los resultados de ambos valores de filtro. Si alguno de los valores de filtro no es válido, el panel no producirá resultados para el valor no válido, pero seguirá filtrando a los valores de filtro válidos. No distingue mayúsculas de minúsculas.</p></td> 
  </tr> 
  <tr> 
   <td><p>Identificación/email del contacto</p></td> 
   <td><p>Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. Los valores de varios filtros tendrán una relación "o", lo que significa que el mosaico mostrará los resultados de ambos valores de filtro. Si alguno de los valores de filtro no es válido, el panel no producirá resultados para el valor no válido, pero seguirá filtrando a los valores de filtro válidos. No distingue mayúsculas de minúsculas.</p><p>El nombre/ID de cuenta, el ID/correo electrónico del posible cliente, el ID de contacto/el filtro de correo electrónico son una relación "o", lo que significa que si tanto el filtro de posible cliente como el filtro de contacto tienen valor, se mostrarán todos los registros para cualquiera de los ID.</p></td> 
  </tr> 
  <tr> 
   <td><p>Modelo de atribución</p></td> 
   <td><p>Especifique con qué modelo se deben calcular los ingresos atribuidos. Valores permitidos: "Atribución de ruta completa", "Atribución de primer contacto", "Atribución de modelo personalizado", "Atribución de creación de posibles clientes", "Atribución de forma de U", "Atribución de forma de W".</p></td> 
  </tr> 
  <tr> 
   <td><p>Tipo de evento</p></td> 
   <td><p>Filtre el recorrido por tipo de evento en el que se basa el punto de contacto del usuario. Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. Valores permitidos: "Session", "CRM Campaign", "CRM Event", "CRM Task", "Impression".</p></td> 
  </tr> 
  <tr> 
   <td><p>Etapas de clientes potenciales</p></td> 
   <td><p>Filtre el recorrido por fase de posible cliente en la que se basa el punto de contacto del usuario. Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. El filtro predeterminado de "es igual a" mostrará sugerencias para elegir, pero se recomienda utilizar "contiene" como criterio de filtro para varios filtros en las fases.</p></td> 
  </tr> 
  <tr> 
   <td><p>Etapas de oportunidad</p></td> 
   <td><p>Filtre los recorridos por fase de oportunidad en la que se basa el punto de contacto del usuario. Permite varios valores añadiendo filtros a través del signo más "+" a la derecha. El filtro predeterminado de "es igual a" mostrará sugerencias para elegir, pero se recomienda utilizar "contiene" como criterio de filtro para varios filtros en las fases.</p></td> 
  </tr> 
  <tr> 
   <td><p>Fecha de Touchpoint</p></td> 
   <td><p>Filtrar el recorrido por fecha/hora de punto de contacto.</p></td> 
  </tr> 
  <tr> 
   <td><p>Correo electrónico de Touchpoint del usuario</p></td> 
   <td><p>Filtrar el recorrido por correo electrónico en el punto de contacto del usuario. Esto permite filtrar los correos electrónicos que no están asociados a un posible cliente/contacto/cuenta.</p></td> 
  </tr> 
  <tr> 
   <td><p>Tipo de instancia de interacción de marketing</p></td> 
   <td><p>Filtre los recorridos por tipo de contacto de marketing.</p></td> 
  </tr> 
  <tr> 
   <td><p>Canal</p></td> 
   <td><p>Filtrar el recorrido por canal.</p></td> 
  </tr> 
  <tr> 
   <td><p>Medio</p></td> 
   <td><p>Filtrar recorrido por medio.</p></td> 
  </tr> 
  <tr> 
   <td><p>Fuente web</p></td> 
   <td><p>Filtrar recorrido por origen web.</p></td> 
  </tr> 
  <tr> 
   <td><p>Primera interacción con la persona</p></td> 
   <td><p>Filtre el recorrido por la columna "Primer contacto" en la tabla de puntos de contacto del usuario.</p></td> 
  </tr> 
  <tr> 
   <td><p>Ingresos atribuidos</p></td> 
   <td><p>Filtre los recorridos por valor de ingresos atribuido.</p></td> 
  </tr> 
 </tbody> 
</table>
