---
unique-page-id: 18874572
description: Registros duplicados y  [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Duplicar registros y  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 12%

---

# Registros duplicados y [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

[!DNL Marketo Measure] usa la dirección de correo electrónico como identificador único al hacer coincidir datos con un posible cliente o contacto relacionado en CRM. Cuando [!DNL Marketo Measure] encuentra varios posibles clientes o contactos con la misma dirección de correo electrónico, se muestran los mismos datos en todos los registros. El impacto de esto se produce cuando se generan informes sobre los posibles clientes o contactos con [!DNL Marketo Measure] y se puede aumentar incorrectamente el número de personas únicas que tienen puntos de contacto de comprador.

¿Qué aspecto tiene esto en los informes de [!DNL Marketo Measure]?

_Informe de ejemplo: [!DNL Marketo Measure] personas con puntos de contacto de comprador._

![](assets/1-1.png)

Puede ver para el ID de persona [!DNL Marketo Measure] de kelsey@adobe.com que existe un posible cliente y un contacto con esa dirección de correo electrónico. En este informe, se han notificado dos primeros toques, dos toques de creación de posibles clientes y dos interacciones PostLC. Estos registros duplicados comparten la fecha del punto de contacto y la información del punto de contacto, lo que podría llevar a la conclusión de que son dos personas diferentes a pesar de ser la misma persona.

**Recomendación**

* Para maximizar el retorno de los informes, se recomienda utilizar una herramienta de desduplicación dentro de su CRM para garantizar que solo está creando registros nuevos y únicos. Esto se puede hacer con la herramienta de automatización de marketing o con un software independiente instalado dentro de su CRM. [!DNL Marketo Measure] no desduplica registros automáticamente y no ofrece este servicio a través de nuestro software.
* Una opción alternativa sería combinar manualmente los registros a medida que identifique duplicados. Este proceso puede llevar mucho tiempo y ser tedioso, pero el resultado de generar informes precisos merece la pena invertir tiempo.
