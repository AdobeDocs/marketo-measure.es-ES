---
unique-page-id: 18874646
description: Diferencia entre Buyer Touchpoints y Buyer Attribution Touchpoints - [!DNL Marketo Measure]
title: Diferencia entre Buyer Touchpoints y Buyer Attribution Touchpoints
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 100%

---

# Diferencia entre Buyer Touchpoints y Buyer Attribution Touchpoints {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Conozca lo que define un punto de contacto de comprador (BT) y un punto de contacto de atribución de comprador (BAT), las diferencias entre ambos y responda a las preguntas frecuentes.

La diferencia clave entre Buyer Touchpoints y Buyer Attribution Touchpoints es su relación con objetos de [!DNL Salesforce]. Los BT están relacionados con los objetos Posible cliente, Contacto y Caso, pero no con el objeto Oportunidad. Lo que significa que nunca habrá ingresos asociados a Buyer Touchpoints.

Mientras que el objeto Buyer Attribution Touchpoint está relacionado con los objetos Contacto, Cuenta y Oportunidad, pero no con el objeto Posible cliente, los Buyer Attribution Touchpoints no están vinculados a posibles clientes. El objeto BAT es donde se verán ingresos vinculados a interacciones de marketing específicas.

Diferencia entre BT y BAT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Punto de contacto de comprador (BT)</td> 
   <td>Punto de contacto de atribución de comprador (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Se relaciona con los objetos Posible cliente, Contacto y Caso</li> 
     <li>No se relaciona con el objeto Oportunidad</li> 
     <li>Los ingresos no están asociados a un punto de contacto de comprador</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Se relaciona con los objetos Contacto, Cuenta y Oportunidad</li> 
     <li>No se relaciona con el objeto Posible cliente</li> 
     <li>Dado que un punto de contacto de atribución de comprador está asociado a una oportunidad, todos los BAT tienen ingresos asociados a ellos</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Preguntas frecuentes {#faq}

**¿Cuándo un punto de contacto de comprador se convierte en un punto de contacto de atribución de comprador?**

Un BT se convierte en un BAT una vez que este BT está asociado a un contacto que tiene una oportunidad asociada. Una cuestión importante que hay que comprender es que una interacción de marketing específica puede ser un BT y BAT.

**¿Puede un punto de contacto de comprador tener una posición de punto de contacto de creación de oportunidades (OC)?**

Un punto de contacto de comprador solo tendrá una posición de punto de contacto de primer contacto (FT), de creación de posibles clientes (LC) o de envío de formulario (puntos de contacto intermedios). Dado que los BT no están relacionados con las oportunidades, no es posible que un BT tenga una posición de Touchpoint de Creación de oportunidad o Cerrado.

**¿Cómo se emplean los datos de Buyer Touchpoint?**

Por lo general, los clientes emplean los datos de Buyer Touchpoing para comprender la participación de la parte superior y el centro del canal. Lo que significa que los usuarios de [!DNL Marketo Measure] saben quién envía formularios, quién está viendo su sitio, qué publicación de blog está funcionando bien, qué anuncio de AdWords está ocasionando la conversión de posibles clientes, etc. Los datos de Buyer Touchpoints son ideales para comprender la participación de sus posibles clientes y contactos.

**¿Qué aspecto tiene un punto de contacto de comprador en Salesforce?**

Esta es una captura de pantalla de un BT en [!DNL Salesforce]:

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-1.png){width="600" zoomable="yes"}

**¿Qué aspecto tiene un punto de contacto de atribución de comprador en Salesforce?**

Esta es una captura de pantalla de un BAT en [!DNL Salesforce]:

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-2.png){width="600" zoomable="yes"}
