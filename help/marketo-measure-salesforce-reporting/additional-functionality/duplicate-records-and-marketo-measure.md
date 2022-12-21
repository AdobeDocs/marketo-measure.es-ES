---
unique-page-id: 18874572
description: Duplicar registros y [!DNL Marketo Measure] - [!DNL Marketo Measure] - Documentación del producto
title: Duplicar registros y [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Duplicar registros y [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

[!DNL Marketo Measure] aprovecha la dirección de correo electrónico como nuestro identificador único al hacer coincidir datos con un posible cliente o contacto relacionado en CRM. When [!DNL Marketo Measure] encuentra varios posibles clientes o contactos con la misma dirección de correo electrónico, mostraremos los mismos datos en todos los registros. El impacto de esto se produce cuando se realiza un informe sobre los posibles clientes o los contactos con [!DNL Marketo Measure] y puede aumentar incorrectamente la cantidad de personas únicas que tienen puntos de contacto de comprador.

¿Cómo se ve esto en [!DNL Marketo Measure] ¿Informar?

_Informe de ejemplo: [!DNL Marketo Measure] Personas con puntos de contacto de comprador._

![](assets/1-1.png)

Puede ver la [!DNL Marketo Measure] ID de persona de kelsey@adobe.com que existe un posible cliente y un contacto con esa dirección de correo electrónico. Verá que en este informe hay 2 primeros toques reportados, 2 toques de creación de posibles clientes y 2 interacciones postLC reportadas. Estos registros duplicados comparten la misma fecha de punto de contacto e información de punto de contacto que podría llevar a la conclusión de que son dos personas diferentes a pesar de ser la misma persona.

**Recomendación**

* Para maximizar el retorno de los informes, recomendamos aprovechar una herramienta de anulación de duplicación dentro de su CRM para asegurarse de que solo está creando registros únicos nuevos y netos. Esto se puede hacer con la herramienta de automatización de marketing o con un software independiente instalado dentro de su CRM. [!DNL Marketo Measure] no desduplica registros automáticamente y no ofrece este servicio a través de nuestro software.
* Una opción alternativa sería combinar manualmente los registros a medida que se identifican duplicados. Este proceso puede requerir mucho tiempo y ser tedioso, pero la producción de informes precisos vale la pena invertir tiempo.
