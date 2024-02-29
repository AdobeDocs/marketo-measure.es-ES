---
unique-page-id: 18874646
description: Diferencia entre los puntos de contacto del comprador y los puntos de contacto de atribución del comprador - [!DNL Marketo Measure]
title: Diferencia entre Buyer Touchpoints y Buyer Attribution Touchpoints
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 61%

---

# Diferencia entre Buyer Touchpoints y Buyer Attribution Touchpoints {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Conozca lo que define un punto de contacto de comprador (BT) y un punto de contacto de atribución de comprador (BAT), las diferencias entre ambos y responda a las preguntas frecuentes.

La diferencia clave entre Buyer Touchpoints y Buyer Attribution Touchpoints es su relación con objetos de [!DNL Salesforce]. Los BT están relacionados con los objetos Posible cliente, Contacto y Caso, pero no con el objeto Oportunidad. Esto significa que nunca hay ingresos asociados a los puntos de contacto del comprador.

Mientras que el objeto de contacto de atribución del comprador está relacionado con los objetos de contacto, cuenta y oportunidad, pero no con el objeto del posible cliente; los puntos de contacto de atribución del comprador no están vinculados a posibles clientes. El objeto MTD es donde verá los ingresos vinculados a interacciones de marketing específicas.

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

Un BT se convierte en un BAT una vez que este BT está asociado a un contacto que tiene una oportunidad asociada. Una cosa importante a entender es que una interacción de marketing específica puede ser un BT y BAT.

**¿Puede un punto de contacto de comprador tener una posición de punto de contacto de creación de oportunidades (OC)?**

Un punto de contacto de comprador solo tendrá una posición de punto de contacto de primer contacto (FT), de creación de posibles clientes (LC) o de envío de formulario (puntos de contacto intermedios). Debido a que los BT no están relacionados con Oportunidades, no es posible que un BT tenga una Posición de Touchpoint de Creación de Oportunidades o Cerrado.

**¿Cómo se utilizan los datos de Touchpoint del comprador?**

Normalmente, los clientes utilizan los datos del punto de contacto del comprador para comprender la parte superior del canal y la parte media del canal. Significado [!DNL Marketo Measure] Los usuarios de saben quién envía formularios, quién está viendo su sitio, qué publicación de blog tiene un buen rendimiento, qué anuncios de AdWords generan conversiones, etc. Los datos de Buyer Touchpoints son ideales para comprender la participación de sus posibles clientes y contactos.

**¿Qué aspecto tiene un punto de contacto de comprador en Salesforce?**

Esta es una captura de pantalla de un BT en [!DNL Salesforce]:

![](assets/1.png)

**¿Qué aspecto tiene un punto de contacto de atribución de comprador en Salesforce?**

Esta es una captura de pantalla de un BAT en [!DNL Salesforce]:

![](assets/2.png)
