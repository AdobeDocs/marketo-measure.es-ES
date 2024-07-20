---
unique-page-id: 18874584
description: "[!DNL Marketo Measure] Taxonomía de objetos y campos - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Taxonomía de objetos y campos"
exl-id: 67f1cac8-e2b4-45cc-b1c9-58bf4e1a760d
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# Taxonomía de objetos y campos de [!DNL Marketo Measure] {#marketo-measure-object-and-field-taxonomy}

A continuación se muestra un diagrama de flujo que representa cómo se relacionan [!DNL Marketo Measure] objetos personalizados con [!DNL Salesforce] objetos estándar.

![](assets/1-2.png)

Para la imagen de tamaño completo, [haga clic aquí](assets/bizible-object-and-field-taxonomy-graph-full.png).

Las definiciones de los campos [!DNL Marketo Measure] que residen en cada objeto [se encuentran aquí](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md).

## Preguntas frecuentes {#faq}

**¿Cuál es la lógica en las flechas?**

Cada flecha describe la relación entre un objeto y el otro. Por ejemplo, verá que la persona [!DNL Marketo Measure] rellena campos en el objeto de posible cliente estándar [!DNL Salesforce]. Si está apuntando a él, entonces significa que está rellenando el extremo receptor de la flecha.

**¿Qué es la persona [!DNL Marketo Measure]?**

Es un objeto [!DNL Marketo Measure] personalizado de [!DNL Salesforce] que vincula los puntos de contacto del comprador con los posibles clientes y contactos.

**¿Qué es [!DNL Bizible].JS?**

Es nuestro JavaScript personalizado el que utilizamos para rastrear la información web que una persona tiene en un sitio específico.

**¿Qué es el panel de ROI de marketing?**

Es un panel de canales de marketing personalizados que se encuentra en la aplicación [!DNL Marketo Measure]. Se puede acceder a ella desde la ficha [!DNL Marketo Measure] en [!DNL Salesforce].
