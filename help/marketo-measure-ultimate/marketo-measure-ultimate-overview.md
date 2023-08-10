---
description: '[!DNL Marketo Measure] Información general definitiva: [!DNL Marketo Measure] - Documentación del producto'
title: '[!DNL Marketo Measure] Información general definitiva'
exl-id: fada9479-0671-4698-8043-c67d7977577b
feature: Integration, Tracking, Attribution
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 1%

---

# Información general sobre [!DNL Marketo Measure] Ultimate {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (anteriormente Bizible) ofrece a los especialistas en marketing una perspectiva detallada de las medidas de marketing más eficaces para generar ingresos y maximizar el retorno de la inversión para su compañía. [!DNL Marketo Measure] es una solución de atribución de marketing que realiza automáticamente un seguimiento e informa sobre el rendimiento del canal, lo que proporciona visibilidad sobre los canales que generan la mayor participación de los clientes y le permite optimizar el gasto de marketing en consecuencia.

[!DNL Marketo Measure Ultimate] contiene las funciones adicionales:

* Realice la ingesta desde casi cualquier fuente de datos y desde varias fuentes de datos del mismo tipo para incorporar todos los datos para la atribución.
   * Se utiliza con casi cualquier CRM, no solo con Salesforce y Dynamics.
   * Conectar varias instancias de CRM o instancias de MAP a una [!DNL Marketo Measure] ejemplo.
   * Incluya datos de participación y registro de seminarios web de terceros.

* Transforme sus datos con buena flexibilidad a través de las capacidades de asignación de campos y transformación para garantizar la forma de datos correcta.

* Ponga perspectivas de atribución a disposición de aplicaciones externas a través del almacén de datos incluido para integrar las perspectivas en su flujo de trabajo. Datos de resultados más granulares e informes basados en BI, incluida la Data Warehouse del Snowflake, que proporciona acceso a datos de resultados granulares y la capacidad de usar cualquier herramienta de BI para análisis e informes.

* Integración con RTCDP (edición B2B o B2P), que proporciona una solución de atribución B2B integrada para clientes de RTCDP como RTCDP y [!DNL Marketo Measure] ambos funcionan desde datos centralizados de Adobe Experience Platform (AEP).

**[!DNL Marketo Measure]Niveles 1-3**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## Novedades de la versión de [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**Importación de datos B2B mediante AEP**

Se espera que los especialistas en marketing traigan sus datos B2B (por ejemplo: cuenta, oportunidad, contacto, posible cliente, campaña, miembro de la campaña, actividad) a través de AEP. Las conexiones directas de CRM y Marketo Engage ya no están disponibles para Ultimate. Los especialistas en marketing seguirán trayendo datos de Ad Platform a través de conexiones directas y rastreando actividades web a través de [!DNL Marketo Measure] javascript.

![](assets/marketo-measure-ultimate-overview-3.png)

**Configuración de moneda predeterminada**

[!DNL Marketo Measure Ultimate] establecerá la moneda predeterminada en USD hasta que el usuario la cambie. Si se establece una nueva moneda predeterminada, los datos se actualizarán sin necesidad de volver a procesarlos. Siempre que la moneda seleccionada esté presente como código ISO de destino, no es necesario enviar las tasas de conversión.

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]Sandbox**

[!DNL Marketo Measure Ultimate] La instancia debe asignarse a una zona protegida de AEP antes de crear la instancia de [!DNL Marketo Measure] Los datos de destino fluyen en AEP.

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] La instancia de producción debe asignarse a una zona protegida de producción de AEP, una [!DNL Marketo Measure Ultimate] La instancia de desarrolladores debe asignarse a una zona protegida de desarrolladores de AEP.

Una vez guardada la selección de la asignación de la zona protegida, no puede cambiarla en la aplicación en este momento. Para cambiarlo, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Los datos de una entidad determinada (por ejemplo, Cuenta) de una fuente de datos determinada solo pueden entrar en un conjunto de datos. Cada conjunto de datos solo se puede incluir en un flujo de datos. Las infracciones detendrán el flujo de datos en tiempo de ejecución.

![](assets/marketo-measure-ultimate-overview-5.png)

**Asignación de etapa**

Todo [!DNL Marketo Measure Ultimate] las reglas son específicas del conjunto de datos. Las reglas de asignación de etapas deben crearse para todos los conjuntos de datos y todas las etapas seleccionadas.

Hay seis etapas integradas:

* Posible cliente perdido
* Apertura de posible cliente
* Posible cliente convertido
* Oportunidad perdida
* Oportunidad abierta
* Oportunidad ganada

Las secciones Perdida, Ganada y Convertida no permiten fases personalizadas. Sin embargo, los datos de origen se pueden asignar a las fases integradas de pérdida/ganancia/conversión actualizando la regla de asignación.

Las fases personalizadas solo se pueden definir para secciones abiertas.
Ya no se incluyen automáticamente las fases CRM en la asignación de etapas.

Se deben asignar cuatro fases integradas con reglas (las reglas de asignación para las otras dos, plomo perdido y plomo convertido, son opcionales):

* Apertura de posible cliente
* Oportunidad perdida
* Oportunidad abierta
* Oportunidad ganada

Las condiciones de regla son específicas del conjunto de datos. Las reglas de asignación de etapas deben crearse para todos los conjuntos de datos y todas las etapas, excepto para la pérdida de posibles clientes y la conversión de posibles clientes.

No hay selección para el modelo de embudo frente a búmeran o personalizado. Todas las fases se seleccionan para el embudo, el bumerán y el modelo personalizado. Hay un límite de cuántas etapas admitimos: 15 etapas personalizadas más 6 etapas integradas.

![](assets/marketo-measure-ultimate-overview-6.png)

Las reglas de punto de contacto de miembro de campaña y las reglas de punto de contacto de actividad son específicas del conjunto de datos.

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

Los puntos de contacto de atribución no se escriben en CRM porque Ultimate no tiene una conexión CRM directa.

[!DNL Marketo Measure] Los servicios ABM ML (coincidencia de cliente potencial con cuenta y puntuación de participación predictiva) no están disponibles para [!DNL Marketo Measure Ultimate]. En la edición RT-CDP B2B se incluyen gratuitamente estos servicios.

## Limitaciones {#limitations}

* Hay campos limitados disponibles para las reglas de transformación de datos en este momento.
* No hay ninguna ruta de migración para los usuarios de nivel 1/2/3 existentes. Requiere una nueva implementación, pero le ayudaremos a migrar los datos de actividad web rastreados desde la instancia existente.

>[!MORELIKETHIS]
>
>[Destino de Marketo Measure Ultimate](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/marketo-measure-ultimate.html?lang=en){target="_blank"}
