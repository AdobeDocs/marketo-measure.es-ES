---
description: 'Prácticas recomendadas para la configuración de puntos de contacto: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la configuración de Touchpoint
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Prácticas recomendadas para la configuración de Touchpoint {#best-practices-for-touchpoint-settings}

## Resumen {#overview}

La sección Configuración de puntos de contacto de su [!DNL Marketo Measure] aplicación le permite establecer reglas que suprimirán o eliminarán los puntos de contacto de su [!DNL Marketo Measure] datos y sistemas relacionados. Estas reglas pueden ayudarle a aislar ciertos conjuntos de datos que no necesitan estar representados en los datos de punto de contacto del comprador o que no desean recibir crédito de atribución sin que ello afecte al seguimiento y a la recopilación de datos.

**Eliminación de puntos de contacto** significa [!DNL Marketo Measure] depurará (es decir, eliminará) cualquier punto de contacto de su CRM que se ajuste a los criterios de la regla. Los datos se pueden registrar dentro de la variable [!DNL Marketo Measure] Tablero de ROI (Discover), pero no aparece en CRM. Normalmente se utiliza para aliviar el estrés en sus límites de almacenamiento de datos dentro de su CRM

**Eliminación de Touchpoint** es similar a la eliminación de Touchpoint, pero los datos NO se pueden registrar en el panel de ROI. No se podrá acceder a ningún punto de contacto suprimido en CRM o Discover. La supresión garantizará que sus datos CRM y Discover coincidan. Normalmente se utiliza para ajustar y especificar qué datos de puntos de contacto desea recibir crédito de atribución.

En [!DNL Marketo Measure] aplicación, la sección Configuración de puntos de contacto se dividirá en cuatro secciones clave. Cada sección suprime o elimina un conjunto diferente de datos. Utilice la clave siguiente para asegurarse de que las reglas suprimen o eliminan los puntos de contacto deseados.

* Suprimir Buyer Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Datos de puntos de contacto del comprador** (los puntos de contacto asociados al individuo, no la oportunidad) de su **CRM**
* Suprimir los Buyer Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Datos de puntos de contacto del comprador** (los puntos de contacto asociados al individuo, no la oportunidad) de su **CRM** y **Discover**
* Suprimir los Buyer Attribution Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Punto de contacto de atribución del comprador** datos (los puntos de contacto asociados a la oportunidad y los ingresos) de su **CRM**
* Suprimir los Buyer Attribution Touchpoints de CRM
   * Utilice esta sección cuando desee crear una regla que elimine **Punto de contacto de atribución del comprador** datos (los puntos de contacto asociados a la oportunidad y los ingresos) de su **CRM** y **Discover**

## Práctica recomendada {#best-practice}

Tanto si establece reglas de configuración de Touchpoint por primera vez como si solo las revisa para comprobar la precisión, tenga en cuenta las siguientes prácticas recomendadas.

* Establezca la lista de datos que desea suprimir o eliminar antes de crear las reglas
* Identifique exactamente qué campos denotarán claramente la regla o las reglas que está configurando
* Asegúrese de especificar el operador correcto para la regla
* Con la clave anterior, asegúrese de que la regla está especificada en la sección correcta de la Configuración de Touchpoint
* Pruebe las reglas antes de implementarlas replicando la lógica de reglas en un informe de puntos de contacto del comprador en CRM para asegurarse de que suprime o elimina los datos deseados

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

La revisión de la configuración de los puntos de contacto es importante, ya que pueden cambiar drásticamente los datos cuando no se definen correctamente. Como práctica recomendada, le recomendamos que revise su Configuración de Touchpoint al menos dos veces al año. Esta es una simple revisión visual de las reglas configuradas en la sección Configuración de puntos de contacto de su [!DNL Marketo Measure] aplicación. Esta revisión le permitirá sentirse seguro de que su configuración de Touchpoint está actualizada y de que se pueden realizar los cambios correspondientes.

Entre las razones para revisar la configuración de los puntos de contacto se incluyen...

* Volumen de negocio en su equipo de marketing
* Principales actualizaciones de la estructura del sitio web
* Identificación de datos de puntos de contacto que ya no son útiles
   * Cada vez que encuentra datos de puntos de contacto que cree que no deben recibir crédito de atribución, las reglas de supresión de puntos de contacto son la funcionalidad para garantizar que los datos sean lo más limpios y precisos posible.
* Cambios en los campos que se utilizan para definir las reglas de supresión o eliminación

>[!MORELIKETHIS]
>
>* [Información general sobre eliminación y supresión de puntos de contacto](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [Por qué los puntos de contacto no se deben eliminar nunca](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [Puntos de contacto de comprador (BT) frente a puntos de contacto de atribución de comprador (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

