---
unique-page-id: 37356395
description: "[!DNL Marketo Engage] Integración de personas - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Engage] Integración de personas"
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integración de personas {#marketo-engage-people-integration}

La integración de personas de Marketo permite [!DNL Marketo Measure] para empezar a descargar personas de Marketo y a enlazar sus sesiones rastreadas con el individuo y asignar puntos de contacto a sus participaciones. Históricamente, [!DNL Marketo Measure] solo se pudieron asignar puntos de contacto a una persona desde CRM, por lo que esto ayuda a los especialistas en marketing a medir sus esfuerzos de marketing antes que esperar a que un escenario o déclencheur los sincronice con CRM.

## Requisitos {#requirements}

* Instancia de Marketo de producción
* Producción [!DNL Salesforce] o [!DNL Microsoft Dynamics] instancia
* Cualquier pago [!DNL Marketo Measure] suscripción
* SOLR habilitado (póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/Support/ct-p/Support) para tener esto habilitado)

## Cómo funciona {#how-it-works}

Como cliente actual, [!DNL Marketo Measure] ya está descargando personas de su CRM. El proceso estándar es que [!DNL Marketo Measure] descarga las personas y asigna la dirección de correo electrónico a una sesión web que hemos rastreado a través de bizible.js.

Con la introducción de la descarga de usuarios de Marketo, [!DNL Marketo Measure] ahora puede asignar sesiones web a un grupo mayor de individuos, los que no se han sincronizado con CRM. Normalmente esto se debe a procesos internos que esperan hasta que las personas alcancen un estado determinado antes de enviarse al CRM.

When [!DNL Marketo Measure] asignando correctamente a la persona de Marketo a una sesión web, nuestro procesamiento generará todos los puntos de contacto relevantes para ella, que finalmente se pueden registrar en [!DNL Marketo Measure Discover]. Si se envía a esa persona de Marketo a CRM, [!DNL Marketo Measure] gestionará el escenario duplicado y recrearemos el punto de contacto para la persona de CRM y marcaremos el conjunto inicial como &quot;duplicado&quot;.

Para que podamos detectar estos duplicados, asegúrese de que su [!DNL Marketo-Salesforce] o [!DNL Marketo-Dynamics] sync está rellenando los ID de posible cliente y de contacto en Marketo Person. Si el Id. se está sincronizando correctamente, debería poder ver el Id. de CRM en el registro de persona, de esta manera:

![](assets/5a.png)

![](assets/5b.png)

Los clientes tienen la opción de informar del conjunto completo de personas de Marketo y de CRM dentro de [!DNL Marketo Measure] Discover. Si solo le interesa informar sobre personas de CRM, le recomendamos que cree un segmento para filtrarlos.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Al informar sobre posibles clientes (personas) en [!DNL Marketo Measure Discover], verá el total de posibles clientes de Marketo y CRM. Para informar solo sobre las personas de Marketo o solo sobre los posibles clientes de CRM, debe crear una categoría de segmento para el origen y, a continuación, crear reglas de segmento para Marketo y CRM utilizando el campo &quot;Sistema de origen&quot; para definir la regla. Una vez creados los segmentos, verá la categoría Fuente disponible para filtrar por su [!DNL Marketo Measure Discover] tableros.

![](assets/bizible-discover-1.png)

![](assets/bizible-discover-2.png)

## Asignaciones de campos {#field-mappings}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>biz_leads</strong></p></th> 
   <th><p><strong>Marketo</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>Identificación</p></td> 
   <td><p>Identificación</p></td> 
  </tr> 
  <tr> 
   <td><p>MODIFIED_DATE</p></td> 
   <td><p>updateAt<strong>*</strong></p></td> 
  </tr> 
  <tr> 
   <td><p>CREATED_DATE</p></td> 
   <td><p>createdAt</p></td> 
  </tr> 
  <tr> 
   <td><p>CORREO ELECTRÓNICO</p></td> 
   <td><p>email</p></td> 
  </tr> 
  <tr> 
   <td><p>WEB_SITE</p></td> 
   <td><p>sitio web</p></td> 
  </tr> 
  <tr> 
   <td><p>EMPRESA</p></td> 
   <td><p>empresa</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_CONVERTED</p></td> 
   <td><p>n/a</p></td> 
  </tr> 
  <tr> 
   <td><p>ACCOUNT_ID</p></td> 
   <td><p>Id De Cuenta (L2A)</p></td> 
  </tr> 
  <tr> 
   <td><p>BIZIBLE_STAGE</p></td> 
   <td><p>Estado</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_DELETED</p></td> 
   <td><p>true/false</p></td> 
  </tr> 
 </tbody> 
</table>

*Hay un problema de comportamiento conocido en el que los campos de la entidad Empresa de Marketo no afectan al valor actualizado de At de la Persona, por lo que si se actualizan los campos relevantes como Sitio web o Empresa, [!DNL Marketo Measure] no sabrá que esos valores se modifican porque el valor de date/time updateAt no se actualiza. Esto afecta a la función ABM, donde no tendríamos datos nuevos para resolver la Cuenta para el posible cliente. Por el momento no hay solución alternativa, pero hay planes para abordarlo en el futuro.

## Preguntas frecuentes {#faq}

**¿Por qué mis recuentos de posibles clientes difieren entre mi CRM y mi [!DNL Marketo Measure Discover]?**

Debido a que esta integración nos permite crear puntos de contacto para posibles clientes que hemos importado directamente de Marketo, puede haber posibles clientes que no se hayan sincronizado con CRM, por lo que el recuento dentro de Discover podría ser mayor que el CRM, ya que los puntos de contacto solo se insertan para los posibles clientes de CRM.

**¿Cómo reemplaza esto mis datos?**

Esta integración realmente combina los conjuntos de datos dentro de su [!DNL Marketo Measure] por lo que no se va a reemplazar nada. Lo que esperaríamos de sus posibles clientes actuales de CRM es que cuando descargamos los 2 años de posibles clientes de Marketo, simplemente actualizaríamos ese registro de posibles clientes para mostrar que también había una coincidencia con un posible cliente de Marketo. Que todo sucede en el servidor y se espera que los puntos de contacto sigan siendo los mismos. También esperaríamos ver más puntos de contacto debido a los posibles clientes de Marketo. Si logramos encontrar coincidencias de sesiones web con esas personas de Marketo, empezaremos a ver los puntos de contacto contabilizados en [!DNL Marketo Measure].

**¿Solo puedo hacer que mis personas se descarguen de Marketo y corten la conexión CRM?**

En este momento, no. Tendremos esta opción en el futuro, pero necesitamos desarrollar otras fases de esta integración de Marketo para que podamos conectar los programas, oportunidades y ofertas de Marketo a [!DNL Marketo Measure].

**¿Importar TODOS mis usuarios de Marketo?**

En este momento, lo más pronto que importaremos personas es a partir del 1/1/2018, de modo que tengamos un mínimo de 2 años de datos, que es el mismo comportamiento que aplicamos desde las descargas de CRM. Implementaremos un comportamiento mejorado para descargar una ventana móvil de 2 años una vez que se haya establecido la conexión con Marketo.

Tampoco se filtra para ningún tipo de persona, por lo que todas las personas dentro de la ventana de dos años se importarán y serán elegibles para puntos de contacto.

**¿Qué es SOLR y por qué necesito que esté habilitado para utilizar esta función?**

Habilitar SOLR para su instancia de Marketo es un paso trivial que abre espacio de hardware en Marketo para que su suscripción pueda utilizar el [!DNL Marketo Measure] integración. Sin SOLR habilitado, no tenemos acceso a ciertas llamadas que de otra manera nos permitirían descargar las personas adecuadas de su instancia de Marketo.
