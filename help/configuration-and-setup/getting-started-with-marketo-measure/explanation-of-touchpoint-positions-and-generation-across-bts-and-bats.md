---
description: Explicación de las posiciones de los puntos de contacto y de la generación entre los BT y las MTD - [!DNL Marketo Measure] - Documentación del producto
title: Explicación de las posiciones de Touchpoint y de la generación entre BT y [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 2%

---

# Explicación de las posiciones de Touchpoint y de la generación entre BT y [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Generación de posiciones y flujos de Touchpoint a través del Recorrido de Compradores**

Comprender las posiciones de los puntos de contacto del comprador y cómo se activan es crucial para generar informes correctamente con [!DNL Marketo Measure] datos. Usted querrá tener una clara comprensión de lo que sus prospectos hicieron a medida que avanzaban por el recorrido del comprador y a su vez cómo se verá en los datos de Touchpoint. Para obtener más contexto sobre este tema, le recomendamos que revise la [[!UICONTROL Generación y asignación de puntos de contacto]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) artículo.

[!DNL Marketo Measure] tiene una variedad de posiciones de Touchpoint activadas por varios pasos en el recorrido del comprador. Al informar sobre [!DNL Marketo Measure] existen dos conjuntos de datos de Touchpoint: puntos de contacto de comprador (BT) y puntos de contacto de atribución de comprador (BAT). Puede observar que estos conjuntos de datos tienen posiciones ligeramente diferentes, ya que están relacionados con distintos objetos. Para obtener más contexto sobre este tema, le recomendamos que revise la [Diferencia entre puntos de contacto de comprador (BT) y puntos de contacto de atribución de comprador (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) artículo.

**Puntos de contacto del comprador (BT)**: Estos son los puntos de contacto asociados a una persona individual y su recorrido y serán exclusivos de esa persona. Los siguientes informes predeterminados están creados a partir de datos de puntos de contacto del comprador.

* [!DNL Marketo Measure] 101: Posibles clientes por ID
* [!DNL Marketo Measure] 101: Posibles Clientes Por Canal
* [!DNL Marketo Measure] 101: Posible cliente/contacto por ID
* [!DNL Marketo Measure] 101: Posible Cliente/Contacto Por Canal

A continuación se describen las posiciones de Punto de contacto del comprador que describen dónde se encuentra un individuo en su recorrido y qué acciones tomó para obtener ese puesto.

<table> 
 <tbody>
  <tr>
   <th>Posición del punto de contacto del comprador (BT)</th> 
   <th>Tipo de punto de contacto (acción que puede almacenar en déclencheur el punto de contacto)</th> 
   <th>Descripción de Touchpoint</th> 
  </tr>
  <tr>
   <td>Primera instancia de interacción (FT)</td> 
   <td>Visita web</td> 
   <td>La primera interacción de marketing que un individuo tiene con su marca</td> 
  </tr>
  <tr>
   <td>Creación de cliente potencial (LC)</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>El primer relleno de formulario que tiene un individuo (normalmente un envío de formulario, pero también podría ser una inclusión de campaña/programa)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>Cualquier formulario que un individuo complete después de su LC (o una inclusión posterior de Campaign/Program)</td> 
  </tr>
 </tbody>
</table>

**Puntos de contacto de atribución de comprador (BATS)**: Estos son los puntos de contacto asociados a una Oportunidad y su recorrido. Estos puntos de contacto estarán conectados a los ingresos ya que están conectados a la oportunidad y a sus contactos. Los siguientes informes predeterminados están creados a partir de datos de puntos de contacto de atribución de comprador.

* [!DNL Marketo Measure] 101: Oportunidades por ID
* [!DNL Marketo Measure] 101: Oportunidades por canal de ID

<table> 
 <tbody>
  <tr>
   <th>Posición del punto de contacto de atribución de comprador (BAT)</th> 
   <th>Tipo de punto de contacto (acción que puede almacenar en déclencheur el punto de contacto)</th> 
   <th>Descripción de Touchpoint</th> 
  </tr>
  <tr>
   <td>Primera instancia de interacción (FT)</td> 
   <td>Visita web</td> 
   <td>La primera interacción de marketing que un contacto tuvo con su marca</td> 
  </tr>
  <tr>
   <td>Creación de cliente potencial (LC)</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>El primer relleno de formulario que tenía un contacto (normalmente un envío de formulario, pero también podría ser una inclusión de campaña/programa)</td> 
  </tr>
  <tr>
   <td>Creación de oportunidades</td> 
   <td>Relleno de formulario <strong>O</strong> Visita web <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>La interacción de marketing más cercana a cuando se crea la opción</td> 
  </tr> 
  <tr>
   <td>Ganados/perdidos cerrados</td> 
   <td>Relleno de formulario <strong>O</strong> Visita web <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>La interacción de marketing más cercana a cuando se cierra la opción Opp (Ganada o Perdida)</td> 
  </tr>
  <tr>
   <td>Contactos medios</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campaña/programa</td> 
   <td>Cuando un contacto rellena un formulario en línea y no coincide con un punto de contacto de hito</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] tiene estos dos conjuntos de datos de Touchpoint para crear una comprensión clara del recorrido de una persona y de las Oportunidades. Estos dos conjuntos de datos de Touchpoint le proporcionan un mapa claro de lo que ha sucedido desde la parte superior del canal hasta la parte inferior del canal.

En el siguiente ejemplo se muestra el flujo de datos de puntos de contacto de comprador (BT) a puntos de contacto de atribución de comprador (BAT). En este ejemplo, Persona A y Persona B forman parte de la misma oportunidad que tiene una fecha de creación del 7/3/2020 y una fecha de cierre del 6/5/2020.

**Persona A** Conjunto de datos de punto de contacto del comprador

* Primer toque (FT) - Búsqueda paga.AdWords - 1/9/2019
* Creación de posibles clientes (LC) - Búsqueda orgánica.Google - 20/11/2019
* Post LC (rellenado de formularios) - Seminario web - 04/03/2020

**Persona B** Conjunto de datos de punto de contacto del comprador

* Primer toque (FT) - Social de pago.Facebook - 26/8/2019
* Creación de posibles clientes (LC) - Búsqueda orgánica.Yahoo - 20/2/2020
* Post LC (rellenado de formularios) - Correo electrónico - 1/5/2020

**Oportunidades** Los datos de Touchpoint de atribución del comprador serían los siguientes:

* Primer toque (FT) - Social de pago.Facebook - 26/8/2019
   * (de **Persona B** porque tienen la verdad _Primer toque_ para la cuenta/Opp)
* Creación de posibles clientes (LC) - Búsqueda orgánica.Google - 20/11/2019
   * (de **Persona A** porque tienen la verdad _Creación de posibles clientes_ para la cuenta/Opp)
* Creación de oportunidades (OC) - Seminario web - 04/03/2020
   * (punto de contacto de Post LC desde **Persona A** sería el _Punto de contacto OC_ porque fue la interacción más reciente que tenemos con la oportunidad que estamos creando el 7/3/2020)
* Cerrado Won - Correo electrónico - 1/5/2020
   * (punto de contacto de Post LC desde **Persona B** sería el _Punto de contacto con Won cerrado_ porque fue la interacción más reciente que tenemos con la oportunidad que cerramos el 5/6/2020)
