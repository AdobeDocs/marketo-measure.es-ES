---
description: '''[!DNL Marketo Measure]“Información general sobre Ultimate [!DNL Marketo Measure]”'
title: Información general sobre [!DNL Marketo Measure] Ultimate
exl-id: fada9479-0671-4698-8043-c67d7977577b
feature: Integration, Tracking, Attribution
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 87%

---

# Información general sobre [!DNL Marketo Measure] Ultimate {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (anteriormente Bizible) ofrece a los especialistas en marketing una perspectiva detallada de las medidas de marketing más eficaces para generar ingresos y maximizar el retorno de la inversión para su compañía. [!DNL Marketo Measure] es una solución de atribución de marketing que realiza automáticamente un seguimiento del rendimiento del canal y genera informes al respecto, lo que proporciona visibilidad sobre los canales que generan la mayor participación de los clientes y le permite optimizar el gasto de marketing en consecuencia.

[!DNL Marketo Measure Ultimate] contiene las siguientes funciones adicionales:

* Realiza la ingesta desde casi cualquier fuente de datos y desde varias fuentes de datos del mismo tipo para incorporar todos los datos para la atribución.
   * Se utiliza con casi cualquier CRM, no solo con Salesforce y Dynamics.
   * Conecta varias instancias de CRM y/o instancias de MAP a una instancia de [!DNL Marketo Measure].
   * Incluya datos de participación y registro de seminarios web de terceros.

* Transforme sus datos con gran flexibilidad a través de las capacidades de asignación de campos y transformación para garantizar la forma de datos correcta.

* Ponga perspectivas de atribución a disposición de aplicaciones externas a través de data warehouse incluido para integrar las perspectivas en su flujo de trabajo. Datos de resultados más granulares e informes basados en BI, incluido el Data Warehouse Snowflake, que proporciona acceso a datos de resultados granulares y la capacidad de usar cualquier herramienta de BI para el análisis y la creación de informes.

* Integración con RTCDP (edición B2B o B2P), que proporciona una solución de atribución B2B integrada para clientes de RTCDP, ya que tanto RTCDP como [!DNL Marketo Measure] funcionan a partir de datos centralizados de Adobe Experience Platform (AEP).

**[!DNL Marketo Measure]Niveles 1-3**

![Niveles de Marketo Measure 1-3](assets/marketo-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![Marketo Measure Ultimate](assets/marketo-overview-3.png)

## Novedades de [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**Importación de datos B2B mediante AEP**

Se espera que los especialistas en marketing traigan sus datos B2B (por ejemplo: cuenta, oportunidad, contacto, cliente potencial, campaña, miembro de la campaña, actividad) a través de AEP. Las conexiones directas de CRM y Marketo Engage ya no están disponibles para Ultimate. Los especialistas en marketing siguen trayendo datos de Ad Platform a través de conexiones directas y rastreando actividades web a través del JavaScript de [!DNL Marketo Measure].

Se espera que ![los especialistas en marketing traigan sus datos B2B (por ejemplo, Cuenta, Oportunidad,](assets/marketo-overview-2.png)

**Configuración de moneda predeterminada**

[!DNL Marketo Measure Ultimate] establece la moneda predeterminada en USD hasta que el usuario la cambie. Si se establece una nueva moneda predeterminada, los datos se actualizan sin necesidad de volver a procesarlos. Siempre que la moneda seleccionada esté presente como código ISO de destino, no es necesario enviar las tasas de conversión.

![Marketo Measure Ultimate establece la divisa predeterminada en USD hasta el ](assets/marketo-overview-7.png)

**[!DNL Marketo Measure Ultimate]zona protegida**

La instancia de [!DNL Marketo Measure Ultimate] debe asignarse a una zona protegida de AEP antes de crear los flujos de datos de destino de [!DNL Marketo Measure] en AEP.

>[!NOTE]
>
>Debe asignarse una instancia de producción de [!DNL Marketo Measure Ultimate] a una zona protegida de producción de AEP, debe asignarse una instancia de desarrolladores de [!DNL Marketo Measure Ultimate] a una zona protegida de desarrolladores de AEP.

Una vez guardada la selección de la asignación de la zona protegida, no puede cambiarla en la aplicación en este momento. Para cambiarlo, ponte en contacto con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Los datos de una entidad determinada (por ejemplo, cuenta) de una fuente de datos determinada solo pueden entrar en un conjunto de datos. Cada conjunto de datos solo puede incluirse en un flujo de datos. Las infracciones detendrán el flujo de datos en el tiempo de ejecución.

![Datos de una entidad determinada (por ejemplo, Cuenta) a partir de un dato determinado](assets/marketo-overview-6.png)

**Asignación de etapa**

Todas las reglas de [!DNL Marketo Measure Ultimate] son específicas del conjunto de datos. Las reglas de asignación de fases deben crearse para todos los conjuntos de datos y todas las etapas seleccionadas.

Hay seis fases integradas:

* Cliente potencial perdido
* Cliente potencial abierto
* Cliente potencial convertido
* Oportunidad perdida
* Oportunidad abierta
* Oportunidad ganada

Las secciones Perdido, Ganado y Convertido no permiten las fases personalizadas. Sin embargo, los datos de origen se pueden asignar a las fases integradas Perdido/Ganado/Convertido actualizando la regla de asignación.

Las fases personalizadas solo se pueden definir para las secciones Abiertas.
Ya no se incluyen automáticamente las fases CRM en la asignación de fases.

Se deben asignar cuatro fases integradas con reglas (las reglas de asignación para las otras dos, Cliente potencial perdido y Cliente potencial convertido, son opcionales):

* Cliente potencial abierto
* Oportunidad perdida
* Oportunidad abierta
* Oportunidad ganada

Las condiciones de la regla son específicas del conjunto de datos. Las reglas de asignación de fases deben crearse para todos los conjuntos de datos y todas las fases, excepto para los Clientes potenciales perdidos y los Clientes potenciales convertidos.

No hay selección para el modelo de canal frente a búmeran o personalizado. Todas las fases se seleccionan para el modelo de canal, búmeran y personalizado. Hay un límite de cuántas fases admitimos: 15 fases personalizadas más 6 fases integradas.

![No hay selección para funnel frente a boomerang frente a modelo personalizado. Todas las etapas son ](assets/marketo-overview-4.png)

Las reglas de punto de contacto de miembro de campaña y las reglas de punto de contacto de actividad son específicas del conjunto de datos.

![Las reglas de puntos de contacto de los miembros de Campaign y las reglas de puntos de contacto de actividad son específicas del conjunto de datos.](assets/marketo-overview-5.png)

![Las reglas de puntos de contacto de los miembros de Campaign y las reglas de puntos de contacto de actividad son específicas del conjunto de datos.](assets/marketo-overview-8.png)

Los puntos de contacto de atribución no se escriben en CRM porque Ultimate no tiene una conexión CRM directa.

Los servicios ABM ML de [!DNL Marketo Measure] (coincidencia de cliente potencial con cuenta y puntuación de participación predictiva) no están disponibles para [!DNL Marketo Measure Ultimate]. En la edición RT-CDP B2B se incluyen gratuitamente estos servicios.

## Limitaciones {#limitations}

* Hay campos limitados disponibles para las reglas de transformación de datos.
* No hay ninguna ruta de migración para los usuarios de nivel 1/2/3 existentes. Requiere una nueva implementación, pero le ayudaremos a migrar los datos de actividad web rastreados desde la instancia existente.

>[!MORELIKETHIS]
>
>* [Destino de Marketo Measure Ultimate](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/marketo-measure-ultimate.html?lang=es){target="_blank"}
>
>* [VÍDEO: Información general sobre Marketo Measure Ultimate](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/marketo-measure-ultimate/overview){target="_blank"}
