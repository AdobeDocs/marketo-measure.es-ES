---
description: '''[!DNL Marketo Measure] Información general definitiva: [!DNL Marketo Measure] - Documentación del producto'
title: '''[!DNL Marketo Measure] Información general definitiva'
exl-id: fada9479-0671-4698-8043-c67d7977577b
source-git-commit: 4a5e720a91e8b229ad2f2889dbf87f5c43767411
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 1%

---

# Información general sobre [!DNL Marketo Measure] Ultimate {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (anteriormente Bizible) proporciona a los especialistas en marketing una perspectiva de cuáles son los esfuerzos de marketing más efectivos para generar ingresos y maximizar el retorno de la inversión para su empresa. [!DNL Marketo Measure] es una solución de atribución de marketing que rastrea automáticamente el rendimiento del canal y genera informes sobre él, lo que proporciona visibilidad sobre los canales que generan la mayor participación del cliente y le permite optimizar el gasto de marketing en consecuencia.

[!DNL Marketo Measure Ultimate] contiene las funciones adicionales:

* Ingeste desde casi cualquier fuente de datos, así como varias fuentes de datos del mismo tipo para incorporar todos los datos para la atribución.
   * Utilice con casi cualquier CRM, no solo Salesforce y Dynamics.
   * Conectar varias instancias CRM o instancias MAP a una [!DNL Marketo Measure] instancia.
   * Incorpore datos de registro y participación de seminarios web de terceros.

* Transforme sus datos con buena flexibilidad a través de las capacidades de asignación de campos y transformación para garantizar la forma de datos correcta.

* Haga que las perspectivas de atribución estén disponibles para aplicaciones externas a través del almacén de datos incluido para integrar las perspectivas en el flujo de trabajo. Datos de resultados más granulares e informes basados en BI, incluida la Data Warehouse de Snowflake, que proporciona acceso a datos de resultados granulares y la capacidad de usar cualquier herramienta de BI para análisis e informes.

* Integración con RTCDP (B2B o B2P Edition), proporcionando una solución de atribución integrada B2B para clientes RTCDP como RTCDP y [!DNL Marketo Measure] ambos funcionan a partir de datos centralizados de Adobe Experience Platform (AEP).

**[!DNL Marketo Measure]Neumáticos 1-3**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## Novedades de [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**Importar datos B2B a través de AEP**

Se espera que los especialistas en marketing aporten sus datos B2B (por ejemplo, cuenta, oportunidad, contacto, posible cliente, campaña, miembro de campaña, actividad) a través de AEP. Las conexiones directas de CRM y Marketo Engage ya no están disponibles para Ultimate. Los especialistas en marketing seguirán aportando datos de la plataforma de publicidad a través de conexiones directas y rastreando actividades web a través de [!DNL Marketo Measure] javascript.

![](assets/marketo-measure-ultimate-overview-3.png)

**Configuración de moneda predeterminada**

[!DNL Marketo Measure Ultimate] establecerá la moneda predeterminada en USD hasta que el usuario la cambie. Si se establece una nueva moneda predeterminada, se actualizarán los datos sin necesidad de volver a procesarlos. Siempre que la moneda seleccionada esté presente como código ISO de destino, no es necesario enviar tasas de conversión.

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]Sandbox**

[!DNL Marketo Measure Ultimate] La instancia de debe asignarse a un entorno limitado de AEP antes de crear el [!DNL Marketo Measure] flujos de datos de destino en AEP.

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] la instancia de producción debe asignarse a un entorno limitado de producción de AEP, un [!DNL Marketo Measure Ultimate] la instancia de desarrolladores debe asignarse a un entorno limitado de desarrolladores de AEP.

Una vez guardada la selección de asignación de entorno limitado, no se puede cambiar en la aplicación en este momento. Para cambiarlo, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Los datos de una entidad determinada (por ejemplo, Cuenta) de una fuente de datos determinada solo pueden entrar en un conjunto de datos. Cada conjunto de datos solo se puede incluir en un flujo de datos. Las infracciones detendrán el flujo de datos en tiempo de ejecución.

![](assets/marketo-measure-ultimate-overview-5.png)

**Asignación de etapa**

Todo [!DNL Marketo Measure Ultimate] las reglas son específicas del conjunto de datos. Se deben crear reglas de asignación de etapas para todos los conjuntos de datos y todas las etapas seleccionadas.

Hay seis etapas integradas:

* Posible cliente perdido
* Apertura de posible cliente
* Posible cliente convertido
* Oportunidad perdida
* Apertura de oportunidad
* Oportunidad ganada

Las secciones Perdido, Ganado y Convertido no permiten etapas personalizadas. Sin embargo, los datos de origen se pueden asignar a las etapas incorporadas Lost/Won/Converted actualizando la regla de asignación.

Los escenarios personalizados solo se pueden definir para las secciones Abiertas.
Ya no se incluyen automáticamente las fases CRM en la asignación de escenario.

Se deben asignar cuatro etapas integradas con reglas (las reglas de asignación para las otras dos, Lote de posibles clientes y Conversión de posibles clientes, son opcionales):

* Apertura de posible cliente
* Oportunidad perdida
* Apertura de oportunidad
* Oportunidad ganada

Las condiciones de las reglas son específicas del conjunto de datos. Las reglas de asignación de fase deben crearse para todos los conjuntos de datos y todas las etapas, excepto para Lead Lost y Lead Converted.

No hay selección de embudo frente a boomerang frente a modelo personalizado. Todas las etapas están seleccionadas para el canal, el boomerang y el modelo personalizado. Hay un límite en la cantidad de etapas que apoyamos: 15 etapas personalizadas más 6 etapas integradas.

![](assets/marketo-measure-ultimate-overview-6.png)

Las reglas de puntos de contacto de miembros de campaña y las reglas de puntos de contacto de actividad son específicas del conjunto de datos.

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

Los puntos de contacto de atribución no se escriben en CRM porque Ultimate no tiene una conexión CRM directa.

[!DNL Marketo Measure] Los servicios de ABM ML (coincidencia entre posibles clientes y puntuación de participación predictiva) no están disponibles para [!DNL Marketo Measure Ultimate]. Puede encontrar estos servicios incluidos de forma gratuita en la edición RT-CDP B2B.

## Limitaciones {#limitations}

* En este momento hay disponibles campos limitados para las reglas de transformación de datos.
* No hay una ruta de migración para los usuarios existentes de Nivel 1/2/3. Requiere una nueva implementación, pero ayudaremos a migrar los datos de actividad web rastreados desde la instancia existente.

>[!MORELIKETHIS]
>
>[Destino de Marketo Measure Ultimate](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/marketo-measure-ultimate.html?lang=en){target="_blank"}
