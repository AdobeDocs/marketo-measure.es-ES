---
description: 'Prácticas recomendadas para conexiones de API: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para conexiones de API
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---

# Prácticas recomendadas para conexiones de API {#best-practices-for-api-connections}

## Resumen {#overview}

[!DNL Marketo Measure] ofrece conexiones de API con [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]y LinkedIn. Estas conexiones de API habilitan [!DNL Marketo Measure] para extraer una variedad de datos de las plataformas de publicidad que se pueden registrar en los datos de Touchpoint de Comprador. Una característica clave de estas conexiones de API es su capacidad para extraer datos de gastos automáticamente, lo que le ahorra a usted y a su equipo el tiempo y esfuerzo que se necesitan para cargar datos manualmente para los informes de ROI. La configuración de estas conexiones de API no es obligatoria para [!DNL Marketo Measure] para rastrear esos canales, pero proporcionan detalles granulares valiosos que mejoran los informes.

La variable [!DNL Marketo Measure] Las conexiones API son un aspecto invalorable de su cuenta y nuestras recomendaciones de prácticas recomendadas le ayudarán a usted y a su equipo a utilizar nuestras conexiones en la mayor medida posible.

## Práctica recomendada {#best-practice}

Independientemente de la plataforma publicitaria que esté conectando, ¡es importante tener en cuenta las siguientes directrices!

* Usar un administrador para conectarse
* Puede conectar varias cuentas de anuncios para una plataforma
* Conecte todas las cuentas de publicidad posibles para automatizar los informes de gasto tanto como sea posible
* Si está disponible, implemente siempre una plantilla de seguimiento. La plantilla garantiza que, incluso si la cuenta publicitaria se desconecta, [!DNL Marketo Measure] sigue siendo capaz de extraer detalles de publicidad granulares

Para optimizar cada [!DNL Marketo Measure] , siga las siguientes prácticas recomendadas.

**[!DNL Facebook]**: Conexión con etiquetado automático

Antes de activar el etiquetado automático, exporte el historial de publicidad a un csv. Al habilitar el etiquetado automático, se restablecerá el historial de conversión y la prueba social de todos los anuncios etiquetados por [!DNL Marketo Measure].

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] [!DNL Facebook] La API podrá:

* Etiquetar automáticamente todo [!DNL Facebook] Anuncios con los necesarios [!DNL Marketo Measure] parameter `_bf ={creative}`
* Descargar información de costo de publicidad en todas las actividades activas [!DNL Facebook] anuncios

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL Facebook], la API se basa en el parámetro etiquetado automático (_bf) para recopilar los detalles de la publicidad.

**AdWords**: Implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, de nivel de campaña o de grupo de anuncios, ya que permite añadir y restar parámetros para todos los anuncios sin riesgo de interrupciones o eliminación del historial de anuncios.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de AdWords podrá:

* Etiquetar automáticamente todos los anuncios de AdWords con la variable [!DNL Marketo Measure] parámetros de `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Descargar información sobre los costos de publicidad en todas las publicidades activas de AdWords

**Bing**: Implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

No existe riesgo de perder el historial de anuncios al configurar su [!DNL Bing] Conexión de API, a diferencia de algunas de nuestras otras conexiones de API.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de Bing podrá:
* Etiquetar automáticamente todos los anuncios de Bing con los siguientes parámetros de `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Descargar información sobre el costo de la publicidad en todos los anuncios de Bing activos

**linkedIn**: Conexión con etiquetado automático

Al habilitar el etiquetado automático, se vuelve a crear un recurso compartido y se coloca en un nuevo elemento creativo, se archiva el elemento creativo antiguo.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de linkedIn podrá:

* Etiquete automáticamente todas las publicidades de LinkedIn que sean contenido patrocinado de tipo de anuncio con el contenido necesario [!DNL Marketo Measure] parámetro _bl={creativeId}. Este parámetro extrae el ID creativo que permite [!DNL Marketo Measure] para resolver la campaña y la información creativa.
* Descargar información sobre los costos de publicidad en todas las actividades activas y admitidas [!DNL LinkedIn] anuncios

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL LinkedIn], la API se basa en el parámetro etiquetado automático (_bl) para recopilar todos los detalles de publicidad posibles.

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Si bien las prácticas recomendadas le protegen de la pérdida de datos si se desconecta, le recomendamos que revise su conexión de forma regular, mensual si es posible. Esta es una simple comprobación visual de la variable [!UICONTROL Conexiones] en la sección [!DNL Marketo Measure] para asegurarse de que no haya iconos de clave roja presentes, señalando una cuenta desconectada.

Cuando se desconecta una cuenta conectada a la API, [!DNL Marketo Measure] no puede extraer datos de gastos ni etiquetar anuncios nuevos. Por este motivo siempre recomendamos implementar una plantilla de seguimiento si es posible. La plantilla garantiza que, incluso si la cuenta publicitaria se desconecta, [!DNL Marketo Measure] todavía puede etiquetar los anuncios y extraer detalles de los anuncios granulares. Una vez reconectados, los datos de gasto se rellenarán de nuevo y la interrupción en los informes de canal de pago será mínima.

Los motivos de desconexión y reautorización incluyen:

* Cambio de contraseña en la cuenta de persona que está conectada
* Esa persona ya no está en la compañía
* Actualizaciones en las API

Si su equipo ha experimentado cualquiera de los casos anteriores, compruebe las conexiones de API en la [!DNL Marketo Measure] para asegurarse de que no necesitan volver a autorizarse.

>[!MORELIKETHIS]
>
>* [Plataformas de publicidad integradas (API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [Cómo afectan las herramientas de administración de ofertas [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] Parámetros de API explicados](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Información general de la API de facebook](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Información general sobre la integración](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Información general sobre la integración de AdWords](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Volver a autorizar cuentas de API conectadas](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)

