---
unique-page-id: 18874572
description: Registros duplicados y [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Duplicar registros y  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 6%

---

# Registros duplicados y [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

[!DNL Marketo Measure] utiliza la dirección de correo electrónico como identificador único cuando se comparan datos con un posible cliente o contacto relacionado en CRM. Cuándo [!DNL Marketo Measure] Si encuentra varios posibles clientes o contactos con la misma dirección de correo electrónico, se mostrarán los mismos datos en todos los registros. El impacto de esto se produce cuando se crea un informe sobre los posibles clientes o los contactos con [!DNL Marketo Measure] y pueden inflar incorrectamente la cantidad de personas únicas que tienen puntos de contacto de comprador.

¿Qué aspecto tiene esto en [!DNL Marketo Measure] ¿Reportando?

_Informe de ejemplo: [!DNL Marketo Measure] Personas con puntos de contacto de comprador._

![](assets/1-1.png)

Se puede ver para. [!DNL Marketo Measure] ID de persona de kelsey@adobe.com que indica que existe un posible cliente y un contacto con esa dirección de correo electrónico. Verá que en este informe hay 2 primeros toques notificados, 2 toques de creación de posibles clientes y 2 interacciones PostLC notificadas. Estos registros duplicados comparten la misma fecha de punto de contacto y la misma información de punto de contacto, lo que podría llevar a la conclusión de que son dos personas diferentes a pesar de ser la misma persona.

**Recomendación**

* Para maximizar el retorno de sus informes, recomendamos aprovechar una herramienta de desduplicación dentro de su CRM para garantizar que solo está creando registros nuevos y únicos. Esto se puede hacer con la herramienta de automatización de marketing o con un software independiente instalado dentro de su CRM. [!DNL Marketo Measure] no desduplica registros automáticamente y no ofrece este servicio a través de nuestro software.
* Una opción alternativa sería combinar manualmente los registros a medida que identifique duplicados. Este proceso puede llevar mucho tiempo y ser tedioso, pero el resultado de generar informes precisos merece la pena invertir tiempo.
