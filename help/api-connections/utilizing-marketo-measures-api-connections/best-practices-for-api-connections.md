---
description: Prácticas recomendadas para conexiones de API - [!DNL Marketo Measure]
title: Prácticas recomendadas para conexiones de API
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: ht
source-wordcount: '737'
ht-degree: 100%

---

# Prácticas recomendadas para conexiones de API {#best-practices-for-api-connections}

## Información general {#overview}

[!DNL Marketo Measure] ofrece conexiones API con [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]y LinkedIn. Estas conexiones de API habilitan [!DNL Marketo Measure] para extraer una variedad de datos de las plataformas publicitarias y registrarlos en los datos de Buyer Touchpoint. Una característica principal de estas conexiones de API es su capacidad para extraer datos de gasto automáticamente, lo que le ahorra a usted y a su equipo el tiempo y el esfuerzo que se tardan en cargar manualmente datos para la creación de informes de ROI. La configuración de estas conexiones de API no es obligatoria para [!DNL Marketo Measure] para realizar un seguimiento de esos canales, pero proporcionan detalles granulares valiosos que mejoran la creación de informes.

Las conexiones de API de [!DNL Marketo Measure] son un aspecto inestimable de su cuenta y nuestras recomendaciones de prácticas recomendadas le ayudarán a usted y a su equipo a utilizar nuestras conexiones al máximo.

## Práctica recomendada {#best-practice}

Independientemente de la plataforma publicitaria que se conecte, es importante tener en cuenta las siguientes directrices.

* Usar un administrador para conectarse
* Puede conectar varias cuentas de anuncios para una plataforma
* Conecte todas las cuentas de publicidad posibles para automatizar al máximo la creación de informes de gasto
* Si está disponible, implemente siempre una plantilla de seguimiento. La plantilla garantiza que, incluso si la cuenta de publicidad se desconecta, [!DNL Marketo Measure] sigue pudiendo extraer detalles de anuncios granulares

Para optimizar cada API de [!DNL Marketo Measure], siga las siguientes prácticas recomendadas.

**[!DNL Facebook]**: Conectar con el etiquetado automático

Antes de habilitar el etiquetado automático, exporte el historial de anuncios a un csv. Al habilitar el etiquetado automático, se restablecerá el historial de conversión y la prueba social de todos los anuncios etiquetados por [!DNL Marketo Measure].

Siguiendo nuestra recomendación de prácticas recomendadas, la API [!DNL Marketo Measure] [!DNL Facebook] podrá:

* Etiquetar automáticamente todos los Anuncios de [!DNL Facebook] con los parámetros de [!DNL Marketo Measure] necesarios `_bf ={creative}`
* Descargar información de coste de publicidad en todos los anuncios de [!DNL Facebook] activos

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL Facebook], la API se basa en el parámetro de etiquetado automático (_bf) para recopilar los detalles del anuncio.

**AdWord**: implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

[!DNL Marketo Measure] recomienda utilizar una Plantilla de seguimiento del nivel de la cuenta, nivel de campaña o nivel de grupo de anuncios, ya que esta permite añadir o eliminar parámetros para todos los anuncios sin el riesgo de provocar interrupciones o eliminación en el Historial de anuncios.

Siguiendo nuestra recomendación de prácticas recomendadas, la API de AdWords de [!DNL Marketo Measure] podrá:

* Etiquetar automáticamente todos los anuncios de AdWords con parámetros [!DNL Marketo Measure] de `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Descargar información de coste de anuncio en todos los anuncios activos de AdWords

**Bing**: implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

No hay riesgo de perder el historial de anuncios al configurar su conexión de API de [!DNL Bing], a diferencia de algunas de nuestras otras conexiones de API.

Siguiendo nuestra recomendación de prácticas recomendadas, la API de Bing de [!DNL Marketo Measure] podrá:
* Etiquetar automáticamente todos los anuncios de Bing con los siguientes parámetros de `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Descargar información de coste de anuncio en todos los anuncios activos de Bing

**LinkedIn**: conectar con el etiquetado automático

Al habilitar el etiquetado automático, se vuelve a crear un Recurso compartido y se coloca en un nuevo Creativo, y se archiva el antiguo.

Siguiendo nuestra recomendación de prácticas recomendadas, la API de LinkedIn de [!DNL Marketo Measure] podrá:

* Etiquete automáticamente todos los anuncios de LinkedIn que sean del tipo de anuncio Contenido patrocinado con el parámetro de [!DNL Marketo Measure] _bl={creativeId} necesario. Este parámetro extrae el ID creativo y permite a [!DNL Marketo Measure] resolver la campaña y la información creativa.
* Descargar información de coste de publicidad en todos los anuncios de [!DNL LinkedIn] activos y admitidos

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL LinkedIn], la API se basa en el parámetro de etiquetado automático (_bl) para recopilar todos los detalles posibles del anuncio.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Aunque seguir nuestras prácticas recomendadas le protegerá de la pérdida de datos si está desconectado, le recomendamos que revise su conexión de forma regular, mensualmente si es posible. Esta es una comprobación visual simple de la sección [!UICONTROL Conexiones] en su aplicación [!DNL Marketo Measure] para asegurarse de que no haya iconos de llave roja presentes que indiquen una cuenta desconectada.

Cuando se desconecta una cuenta conectada a la API, [!DNL Marketo Measure] no puede extraer los datos de gasto en anuncios nuevos ni etiquetarlos. Por este motivo, siempre recomendamos implementar una plantilla de seguimiento si es posible. La plantilla garantiza que, incluso si la cuenta de publicidad se desconecta, [!DNL Marketo Measure] aún puede etiquetar los anuncios y extraer detalles granulares de los anuncios. Una vez que se haya vuelto a conectar, los datos de gasto se rellenarán de nuevo y la interrupción de la creación de informes del canal de pago será mínima.

Las razones para la desconexión y reautorización incluyen...

* Cambio de la contraseña de la cuenta de persona que está conectada
* Esa persona ya no está en la compañía
* Actualizaciones de las API

Si su equipo ha experimentado cualquiera de los casos anteriores, compruebe las conexiones de API en la aplicación de [!DNL Marketo Measure] para asegurarse de que no necesitan volver a autorizarse.

>[!MORELIKETHIS]
>
>* [Plataformas de anuncios integradas (API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [Cómo afectan las herramientas de administración de ofertas [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] Parámetros de API explicados](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Información general de API de Facebook](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Información general de integración](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Información general de integración de AdWords](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Volver a autorizar cuentas de API conectadas](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
