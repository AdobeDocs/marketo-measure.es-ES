---
description: Explicación de las posiciones de los puntos de contacto y la generación entre BT y MTD - [!DNL Marketo Measure]
title: Explicación de las posiciones y la generación de puntos de contacto entre BT y  [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 3%

---

# Explicación de las posiciones de los puntos de contacto y la generación entre BT y [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Generación de posiciones de Touchpoint y Flujo a través del Recorrido de Compradores**

Entender las posiciones de Touchpoint del comprador y cómo se activan es crucial para informar correctamente sobre con [!DNL Marketo Measure] datos. Desea tener una comprensión clara de lo que hicieron sus clientes potenciales a medida que se movían a través del recorrido del comprador y, a su vez, cómo se verá en los datos de Touchpoint. Para obtener más información contextual sobre este tema, se recomienda revisar la [[!UICONTROL Generación y asignación de puntos de contacto]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) artículo.

[!DNL Marketo Measure] tiene una variedad de posiciones de Touchpoint que se activan por varios pasos en el recorrido del comprador. Al informar sobre [!DNL Marketo Measure] Existen dos conjuntos de datos de Touchpoint: puntos de contacto del comprador (BT) y puntos de contacto de atribución del comprador (BAT). Puede observar que estos conjuntos de datos tienen posiciones ligeramente diferentes en relación con diferentes objetos. Para obtener más información contextual sobre este tema, se recomienda revisar la [Diferencia entre los puntos de contacto del comprador (BT) y los puntos de contacto de atribución del comprador (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) artículo.

**Puntos de contacto del comprador (BT)**: estos son los puntos de contacto asociados a una persona individual y su recorrido, y serán únicos para esa persona. Los siguientes informes predeterminados están basados en los datos de Buyer Touchpoint.

* [!DNL Marketo Measure] 101: Posibles clientes por identificador
* [!DNL Marketo Measure] 101: Posibles clientes por canal
* [!DNL Marketo Measure] 101: Posible cliente/Contacto por ID
* [!DNL Marketo Measure] 101: Posible cliente/Contacto Por Canal

A continuación se describen las posiciones de los puntos de contacto del comprador, que describen dónde se encuentra una persona en su recorrido y qué acciones ha realizado para conseguir esa posición.

<table> 
 <tbody>
  <tr>
   <th>Posición del punto de contacto del comprador (BT)</th> 
   <th>Tipo de punto de contacto (acción que puede almacenar en déclencheur el punto de contacto)</th> 
   <th>Descripción de Touchpoint</th> 
  </tr>
  <tr>
   <td>Primer contacto (FT)</td> 
   <td>Visita web</td> 
   <td>La primera interacción de marketing que un individuo tiene con su marca</td> 
  </tr>
  <tr>
   <td>Creación de posibles clientes (LC)</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>El primer formulario que rellena una persona tiene (normalmente un envío de formulario, pero también podría ser una inclusión de campaña/programa)</td> 
  </tr>
  <tr>
   <td>Publicar LC</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>Cualquier formulario que complete una persona después de su LC (o una inclusión posterior de campaña/programa).</td> 
  </tr>
 </tbody>
</table>

**Puntos de contacto de atribución del comprador (BATS)**: estos son los puntos de contacto asociados a una oportunidad y su recorrido. Estos puntos de contacto están conectados a los ingresos a medida que están conectados a la oportunidad y a sus contactos. Los siguientes informes predeterminados están basados en los datos de puntos de contacto de Atribución del comprador.

* [!DNL Marketo Measure] 101: Oportunidades por identificador
* [!DNL Marketo Measure] 101: Oportunidades por canal de ID

<table> 
 <tbody>
  <tr>
   <th>Posición del punto de contacto de atribución del comprador (BAT)</th> 
   <th>Tipo de punto de contacto (acción que puede almacenar en déclencheur el punto de contacto)</th> 
   <th>Descripción de Touchpoint</th> 
  </tr>
  <tr>
   <td>Primer contacto (FT)</td> 
   <td>Visita web</td> 
   <td>La primera interacción de marketing que un contacto tuvo con su marca</td> 
  </tr>
  <tr>
   <td>Creación de posibles clientes (LC)</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>El primer formulario que rellena un contacto tenía (normalmente un envío de formulario, pero también podría ser una inclusión de campaña/programa)</td> 
  </tr>
  <tr>
   <td>Creación de oportunidad</td> 
   <td>Relleno de formulario <strong>O</strong> Visita web <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>La interacción de marketing más cercana a cuando se crea la Opp</td> 
  </tr> 
  <tr>
   <td>Ganados/Perdidos cerrados</td> 
   <td>Relleno de formulario <strong>O</strong> Visita web <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>La interacción de marketing más cercana a cuando la opción está cerrada (ganada o perdida)</td> 
  </tr>
  <tr>
   <td>Contactos medios</td> 
   <td>Relleno de formulario <strong>O</strong> Inclusión de campañas/programas</td> 
   <td>Cuando un contacto rellena un formulario en línea y no coincide con un punto de contacto de Milestone</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] tiene estos dos conjuntos de datos de Touchpoint para crear una comprensión clara del recorrido y las oportunidades de una persona individual. Estos dos conjuntos de datos de Touchpoint le proporcionan un mapa claro de lo que ha sucedido desde la parte superior del embudo hasta la parte inferior del mismo.

El siguiente ejemplo muestra el flujo de datos desde los puntos de contacto del comprador (BT) hasta los puntos de contacto de atribución del comprador (BAT). En este ejemplo, la persona A y la persona B forman parte de la misma oportunidad que tiene una fecha de creación del 7/3/2020 y una fecha de cierre del 6/5/2020.

**Persona A** Conjunto de datos Touchpoint del comprador

* Primer contacto (FT) - Búsqueda de pago.AdWords - 1/9/2019
* Creación de clientes potenciales (LC) - Búsqueda orgánica.Google - 20/11/2019
* Post LC (rellenado de formulario) - Seminario web - 4/3/2020

**Persona B** Conjunto de datos Touchpoint del comprador

* Primer contacto (FT) - Social de pago.Facebook - 26/8/2019
* Creación de clientes potenciales (LC) - Búsqueda orgánica.Yahoo - 20/2/2020
* Post LC (rellenado de formulario) - Correo electrónico - 1/5/2020

**Oportunidades** Los datos del punto de contacto de atribución del comprador serían los siguientes:...

* Primer contacto (FT) - Social de pago.Facebook - 26/8/2019
   * (desde **Persona B** porque tienen la verdad _Primer contacto_ para la Cuenta/Opp)
* Creación de clientes potenciales (LC) - Búsqueda orgánica.Google - 20/11/2019
   * (desde **Persona A** porque tienen la verdad _Creación de posibles clientes_ para la Cuenta/Opp)
* Creación de oportunidades (OC) - Seminario web - 4/3/2020
   * (el punto de contacto Post LC desde **Persona A** sería el _OC Touchpoint_ porque fue la interacción más reciente que tenemos con la oportunidad que se está creando el 7/3/2020)
* Cerrado Won - Correo electrónico - 1/5/2020
   * (el punto de contacto Post LC desde **Persona B** sería el _Punto de contacto Won cerrado_ porque fue la interacción más reciente que tuvimos con la oportunidad que se cerró el 6/5/2020)
