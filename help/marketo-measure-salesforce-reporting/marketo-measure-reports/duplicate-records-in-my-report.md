---
unique-page-id: 18874634
description: Duplicar registros en mi informe - [!DNL Marketo Measure] - Documentación del producto
title: Duplicar registros en mi informe
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# Duplicar registros en mi informe {#duplicate-records-in-my-report}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

A medida que se sumerge en el [!DNL Marketo Measure] Informes en [!DNL Salesforce], es posible que empiece a encontrar registros &quot;duplicados&quot; en los informes. Es probable que experimente esta sensación al revisar [!DNL Marketo Measure] informes predeterminados.

Al realizar informes con el objeto Touchpoints del comprador o el objeto Touchpoint de atribución del comprador, es importante comprender que ya no realiza informes sobre el recuento de posibles clientes, contactos u oportunidades, sino que informará sobre el número de touchpoints del comprador o de puntos de contacto de atribución del comprador asociados a dichos objetos estándar (posibles clientes, contactos, oportunidades).

Veamos el siguiente informe como ejemplo:

Esto es un **Contactos con puntos de contacto del comprador** informe. De nuevo, esto significa que estamos viendo el número de puntos de contacto asociados a un contacto individual.

![](assets/1.gif)

Como pueden ver, parece que hay tres contactos de James Williams en el informe, y por lo tanto puede estar pensando, &quot;¡duplicados!&quot;

Sin embargo, este informe muestra el número de puntos de contacto relacionados con James. Dentro del informe, puede ver que James tiene un FT individual (primer toque), una LC individual, un Formulario (contacto de creación de posibles clientes) y un punto de contacto PostLC (un envío de formulario que tiene lugar después del punto de contacto LC).

Si desea comprender el &quot;recuento de contactos&quot;, puede utilizar los campos &quot;Recuento: primer toque&quot;, &quot;Recuento: contacto para la creación de posibles clientes&quot; o &quot;Recuento: Forma de U&quot; para comprender cuántos contactos han tenido interacciones de marketing.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Informes de SFDC de existencias](https://universityonline.marketo.com/courses/bizible-fundamentals-bizible-102/#/page/5c5cb68dfb384d0c9fb96cc4)
