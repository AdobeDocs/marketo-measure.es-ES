---
description: Registros duplicados en Mi informe - [!DNL Marketo Measure]
title: Duplicar registros en mi informe
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 9%

---


# Duplicar registros en mi informe {#duplicate-records-in-my-report}

>[!NOTE]
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero aún así ve &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

A medida que se sumerge en los informes de [!DNL Marketo Measure] en [!DNL Salesforce], es posible que empiece a encontrar registros &quot;duplicados&quot; en sus informes. Es probable que experimente esta sensación cuando revise [!DNL Marketo Measure] informes predeterminados.

Al realizar informes con los puntos de contacto del comprador o con el objeto Buyer Attribution Touchpoint, es importante entender que ya no realiza informes sobre el número de posibles clientes, contactos u oportunidades, sino sobre el número de puntos de contacto del comprador o de puntos de contacto de atribución del comprador asociados a dichos objetos estándar (posibles clientes, contactos, oportunidades).

Veamos el siguiente informe como ejemplo:

Este es un informe de **Contactos con puntos de contacto del comprador**. De nuevo, esto significa que estamos viendo el recuento de puntos de contacto asociados a un contacto individual.

![Informe de contactos con puntos de contacto del comprador que muestra varias entradas por contacto](assets/1.gif)

Como puede ver, parece que hay tres contactos de James Williams en el informe y, por lo tanto, podría estar pensando: &quot;¡duplicados!&quot;

Sin embargo, este informe muestra la cantidad de puntos de contacto relacionados con James. Dentro del informe, puede ver que James tiene una FT (primer contacto) individual, una LC individual, un formulario (contacto de creación de posibles clientes) y un punto de contacto PostLC (un envío de formulario que se produce después del punto de contacto LC).

Si desea comprender el &quot;recuento de contactos&quot;, puede utilizar los campos &quot;Recuento: primer contacto&quot;, &quot;Recuento: contacto de creación de posibles clientes&quot; o &quot;Recuento: forma&quot; para comprender cuántos contactos han tenido interacciones de marketing.

>[!MORELIKETHIS]
>[[!DNL Marketo Measure] Tutoriales: Informes de SFDC de Stock](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
