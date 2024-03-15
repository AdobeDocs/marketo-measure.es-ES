---
unique-page-id: 18874634
description: Registros duplicados en Mi informe - [!DNL Marketo Measure]
title: Duplicar registros en mi informe
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 10%

---

# Duplicar registros en mi informe {#duplicate-records-in-my-report}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero sigue viendo &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

A medida que se sumerge en el [!DNL Marketo Measure] Informes en [!DNL Salesforce], es posible que empiece a buscar registros &quot;duplicados&quot; en los informes. Es probable que experimentes esta sensación cuando revises [!DNL Marketo Measure] informes listos para usar.

Al realizar informes con los puntos de contacto de comprador o con el objeto de punto de contacto de atribución de comprador, es importante comprender que ya no realiza informes sobre el recuento de posibles clientes, contactos u oportunidades, sino sobre el número de puntos de contacto de comprador o puntos de contacto de atribución de comprador asociados a dichos objetos estándar (posibles clientes, contactos, oportunidades).

Veamos el siguiente informe como ejemplo:

Este es un **Contactos con puntos de contacto del comprador** informe. De nuevo, esto significa que estamos viendo el recuento de puntos de contacto asociados a un contacto individual.

![](assets/1.gif)

Como puede ver, parece que hay tres contactos de James Williams en el informe y, por lo tanto, podría estar pensando: &quot;¡duplicados!&quot;

Sin embargo, este informe muestra la cantidad de puntos de contacto relacionados con James. Dentro del informe, puede ver que James tiene una FT (primer contacto) individual, una LC individual, un formulario (contacto de creación de posibles clientes) y un punto de contacto PostLC (un envío de formulario que se produce después del punto de contacto LC).

Si desea comprender el &quot;recuento de contactos&quot;, puede utilizar los campos &quot;Recuento: primer contacto&quot;, &quot;Recuento: contacto de creación de posibles clientes&quot; o &quot;Recuento: forma&quot; para comprender cuántos contactos han tenido interacciones de marketing.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Informes de SFDC de Stock](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
