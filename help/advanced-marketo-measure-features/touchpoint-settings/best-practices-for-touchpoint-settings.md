---
description: 'Prácticas recomendadas para la configuración de Touchpoint: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la configuración de puntos de contacto
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 5%

---

# Prácticas recomendadas para la configuración de puntos de contacto {#best-practices-for-touchpoint-settings}

## Información general {#overview}

La sección Configuración de punto de contacto de su [!DNL Marketo Measure] La aplicación de le permite establecer reglas que suprimirán o eliminarán los puntos de contacto de su [!DNL Marketo Measure] datos y sistemas relacionados. Estas reglas pueden ayudarle a aislar ciertos conjuntos de datos que no necesitan representarse en los datos de punto de contacto del comprador o que no desea recibir crédito de atribución sin perturbar el seguimiento y la recopilación de datos.

**Eliminación de Touchpoint** recursos [!DNL Marketo Measure] depurará (es decir, eliminará) cualquier punto de contacto de su CRM que se ajuste a los criterios de la regla. Los datos se pueden registrar en el [!DNL Marketo Measure] Tablero de ROI (Discover), pero no aparece en CRM. Normalmente se utiliza para aliviar el estrés en los límites de almacenamiento de datos dentro de su CRM

**Supresión de Touchpoint** es similar a la eliminación de puntos de contacto, pero los datos NO se PUEDEN registrar dentro del panel de ROI. Los puntos de contacto suprimidos no serán accesibles en CRM ni en Discover. La supresión garantizará que los datos de CRM y de Discover coincidan. Se utiliza comúnmente para ajustar y especificar aún más qué datos de punto de contacto desea recibir crédito de atribución.

En su [!DNL Marketo Measure] de la aplicación, la sección Configuración de punto de contacto se dividirá en cuatro secciones clave. Cada sección suprime o elimina un conjunto diferente de datos. Utilice la siguiente tecla para asegurarse de que las reglas supriman o eliminen los puntos de contacto deseados.

* Suprimir Buyer Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Datos de Touchpoint del comprador** (los puntos de contacto asociados al individuo, no la oportunidad) desde su **CRM**
* Suprimir los Buyer Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Datos de Touchpoint del comprador** (los puntos de contacto asociados al individuo, no la oportunidad) desde su **CRM** y **Discover**
* Suprimir los Buyer Attribution Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Punto de contacto de atribución del comprador** datos (los puntos de contacto asociados a la oportunidad y los ingresos) de su **CRM**
* Suprimir los Buyer Attribution Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Punto de contacto de atribución del comprador** datos (los puntos de contacto asociados a la oportunidad y los ingresos) de su **CRM** y **Discover**

## Práctica recomendada {#best-practice}

Tanto si establece las reglas de Configuración de puntos de contacto por primera vez como si solo las revisa para comprobar la precisión, tenga en cuenta las siguientes prácticas recomendadas.

* Establezca la lista de datos que desea suprimir o eliminar antes de crear las reglas
* Identifique exactamente qué campos denotarán claramente la regla o reglas que está configurando
* Asegúrese de haber especificado el operador correcto para la regla
* Utilizando la clave anterior, asegúrese de que la regla se especifica en la sección correcta de la Configuración de punto de contacto
* Pruebe las reglas antes de implementarlas replicando la lógica de regla en un informe de punto de contacto del comprador en CRM para asegurarse de que suprime o elimina los datos deseados

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Es importante revisar la configuración de Touchpoint, ya que puede cambiar drásticamente los datos cuando no se define correctamente. Como práctica recomendada, le recomendamos que revise la configuración de Touchpoint al menos dos veces al año. Esta es una sencilla revisión visual de las reglas configuradas en la sección Configuración de punto de contacto de su [!DNL Marketo Measure] aplicación. Esta revisión le permitirá sentirse seguro de que la Configuración de Touchpoint está actualizada y que se pueden realizar los cambios correspondientes.

Los motivos para revisar la configuración de Touchpoint incluyen...

* Facturación en su equipo de marketing
* Principales actualizaciones de la estructura del sitio web
* Identificación de datos de punto de contacto que ya no son útiles
   * Cada vez que encuentra datos de punto de contacto que cree que no deberían recibir crédito de atribución, las reglas de supresión de puntos de contacto son la funcionalidad para garantizar que los datos sean lo más limpios y precisos posible.
* Cambios en los campos utilizados para definir las reglas de supresión o eliminación

>[!MORELIKETHIS]
>
>* [Información general sobre eliminación y supresión de Touchpoint](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [Por qué los puntos de contacto nunca deben eliminarse](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [Puntos de contacto del comprador (BT) frente a puntos de contacto de atribución del comprador (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)
