---
unique-page-id: 18874646
description: Diferencia entre puntos de contacto del comprador y puntos de contacto de atribución del comprador - [!DNL Marketo Measure] - Documentación del producto
title: Diferencia entre puntos de contacto del comprador y puntos de contacto de atribución del comprador
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Diferencia entre puntos de contacto del comprador y puntos de contacto de atribución del comprador {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Conozca lo que define un punto de contacto de comprador (BT) y un punto de contacto de atribución de comprador (BAT), las diferencias entre ambos, y responda a las preguntas más frecuentes.

El distintivo clave entre puntos de contacto del comprador y puntos de contacto de atribución del comprador es su relación con [!DNL Salesforce] Objetos. Los BT están relacionados con los objetos Posible cliente, Contacto y Caso, pero no con el objeto Oportunidad. Lo que significa que nunca habrá ingresos asociados a puntos de contacto del comprador.

Mientras que el objeto Touchpoint de atribución de comprador está relacionado con los objetos Contacto, Cuenta y Oportunidad, pero no con el objeto Lead. Lo que significa que nunca habrá puntos de contacto de atribución de Comprador vinculados a posibles clientes. El objeto BAT es donde verá ingresos vinculados a interacciones de marketing específicas.

Diferencia entre BT y BAT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Punto de contacto del comprador (BT)</td> 
   <td>Punto de contacto de atribución de comprador (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Se refiere a los objetos Posible cliente, Contacto y Caso</li> 
     <li>No se relaciona con el objeto de oportunidad</li> 
     <li>Los ingresos no están asociados a un punto de contacto del comprador</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Se refiere a los objetos Contacto, Cuenta y Oportunidad</li> 
     <li>No se relaciona con el objeto Lead</li> 
     <li>Dado que un punto de contacto de atribución de comprador está asociado a una oportunidad, todas las MTD tienen ingresos asociados a ellos</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Preguntas frecuentes {#faq}

**¿Cuándo un punto de contacto del comprador se convierte en un punto de contacto de atribución del comprador?**

Un BT se convierte en un BAT una vez que este BT está asociado a un Contacto que tiene una oportunidad asociada. Una cosa muy importante para comprender es que una interacción de marketing específica puede ser un BT y un BAT.

**¿Puede un punto de contacto del comprador tener una posición de punto de contacto de creación de oportunidades (OC)?**

Un punto de contacto del comprador solo tendrá una posición de punto de contacto de primer contacto (FT), de creación de posibles clientes (LC) o de envío de formulario (puntos de contacto intermedios). Dado que los BT no están relacionados con Oportunidades, no es posible que un BT tenga una Posición de Touchpoint de Creación de Oportunidades o Cerrada.

**¿Cómo se aprovechan los datos de punto de contacto del comprador?**

Normalmente, los clientes aprovechan los datos de punto de contacto del comprador para comprender la participación de la parte superior del canal y el centro del canal. Significado [!DNL Marketo Measure] los usuarios saben quién envía los formularios, quién está viendo su sitio, qué publicación de blog está teniendo un buen rendimiento, qué publicidad de AdWords está impulsando lleva a la conversión, etc. Los datos de puntos de contacto del comprador son buenos para comprender la participación de sus posibles clientes y contactos.

**¿Cómo se ve un punto de contacto del comprador en Salesforce?**

Esta es una captura de pantalla de un BT en [!DNL Salesforce]:

![](assets/1.png)

**¿Cómo se ve un punto de contacto de atribución de comprador en Salesforce?**

Esta es una captura de pantalla de un BAT en [!DNL Salesforce]:

![](assets/2.png)
