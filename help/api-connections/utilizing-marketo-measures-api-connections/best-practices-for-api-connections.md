---
description: 'Prácticas recomendadas para conexiones de API: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para conexiones de API
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 2%

---

# Prácticas recomendadas para conexiones de API {#best-practices-for-api-connections}

## Información general {#overview}

[!DNL Marketo Measure] ofrece conexiones API con [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]y LinkedIn. Estas conexiones de API habilitan [!DNL Marketo Measure] para extraer una variedad de datos de las plataformas publicitarias y registrarlos en los datos de Touchpoint del comprador. Una característica clave de estas conexiones de API es su capacidad para extraer datos de gasto automáticamente, lo que le ahorra a usted y a su equipo el tiempo y el esfuerzo que se tardan en cargar manualmente datos para la creación de informes de ROI. La configuración de estas conexiones de API no es obligatoria para [!DNL Marketo Measure] para realizar un seguimiento de esos canales, pero proporcionan detalles granulares valiosos que mejoran los informes.

El [!DNL Marketo Measure] Las conexiones de API son un aspecto inestimable de su cuenta y nuestras recomendaciones de prácticas recomendadas le ayudarán a usted y a su equipo a utilizar nuestras conexiones al máximo.

## Práctica recomendada {#best-practice}

Independientemente de la plataforma publicitaria que esté conectando, es importante tener en cuenta las siguientes directrices.

* Usar un administrador para conectarse
* Puede conectar varias cuentas de anuncios para una plataforma
* Conecte todas las cuentas de publicidad posibles para automatizar al máximo la creación de informes de gasto
* Si está disponible, implemente siempre una plantilla de seguimiento. La plantilla garantiza que, incluso si la cuenta de publicidad se desconecta, [!DNL Marketo Measure] sigue pudiendo extraer detalles de anuncios granulares

Para optimizar cada [!DNL Marketo Measure] API, siga las siguientes prácticas recomendadas.

**[!DNL Facebook]**: conectar con el etiquetado automático

Antes de habilitar el etiquetado automático, exporte el historial de anuncios a un csv. Al habilitar el etiquetado automático, se restablecerá el historial de conversión y la prueba social de todos los anuncios etiquetados por [!DNL Marketo Measure].

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] [!DNL Facebook] La API podrá:

* Etiquetar automáticamente todo [!DNL Facebook] Anuncios con los necesarios [!DNL Marketo Measure] parámetro `_bf ={creative}`
* Descargar información de coste de publicidad en todos los anuncios activos [!DNL Facebook] anuncios

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL Facebook]Sin embargo, la API se basa en el parámetro de etiquetado automático (_bf) para recopilar los detalles del anuncio.

**AdWord**: Implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, de nivel de campaña o de nivel de grupo de publicidad, ya que permite añadir y restar parámetros para todos los anuncios sin el riesgo de interrupciones o eliminación del historial de anuncios.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de AdWords podrá:

* Etiquetar automáticamente todos los anuncios de AdWords con [!DNL Marketo Measure] parámetros de `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Descargar información de coste de anuncio en todos los anuncios activos de AdWords

**Bing**: Implemente una plantilla de seguimiento en el nivel de cuenta y habilite el etiquetado automático

No hay riesgo de perder el historial de anuncios al configurar su [!DNL Bing] Conexión API, a diferencia de algunas de nuestras otras conexiones API.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de Bing podrá:
* Etiquete automáticamente todos los anuncios de Bing con los siguientes parámetros de `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Descargar información de coste de anuncio en todos los anuncios activos de Bing

**LinkedIn**: conectar con el etiquetado automático

Al habilitar el etiquetado automático, se vuelve a crear un recurso compartido y se coloca en un nuevo creativo, y se archiva el antiguo.

Siguiendo nuestra recomendación de prácticas recomendadas, la variable [!DNL Marketo Measure] La API de linkedIn podrá:

* Etiquete automáticamente todos los anuncios de LinkedIn que sean de tipo Contenido patrocinado con el necesario [!DNL Marketo Measure] parámetro _bl={creativeId}. Este parámetro extrae el ID creativo y permite lo siguiente [!DNL Marketo Measure] para resolver la campaña y la información creativa.
* Descargar información de coste de publicidad en todos los recursos activos y admitidos [!DNL LinkedIn] anuncios

>[!NOTE]
>
>No hay ninguna plantilla de seguimiento para [!DNL LinkedIn]Sin embargo, la API se basa en el parámetro de etiquetado automático (_bl) para recopilar todos los detalles posibles del anuncio.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Aunque seguir nuestras prácticas recomendadas le protegerá de la pérdida de datos si está desconectado, le recomendamos que revise su conexión de forma regular, mensualmente si es posible. Esta es una comprobación visual simple del [!UICONTROL Conexiones] en su sección [!DNL Marketo Measure] aplicación para asegurarse de que no haya iconos de llave roja presentes que indiquen una cuenta desconectada.

Cuando se desconecta una cuenta conectada a la API, [!DNL Marketo Measure] no puede extraer los datos de gasto en anuncios nuevos ni etiquetarlos. Por este motivo, siempre recomendamos implementar una plantilla de seguimiento si es posible. La plantilla garantiza que, incluso si la cuenta de publicidad se desconecta, [!DNL Marketo Measure] aún puede etiquetar los anuncios y extraer detalles granulares de los anuncios. Una vez que se haya vuelto a conectar, los datos de gasto se rellenarán de nuevo y la interrupción de los informes del canal de pago será mínima.

Las razones para la desconexión y reautorización incluyen...

* Cambio de la contraseña de la cuenta de persona que está conectada
* Esa persona ya no está en la compañía
* Actualizaciones de las API de

Si su equipo ha experimentado cualquiera de los casos anteriores, compruebe las conexiones de API en la [!DNL Marketo Measure] para asegurarse de que no necesitan volver a autorizarse.

>[!MORELIKETHIS]
>
>* [Plataformas de publicidad integradas (API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [Cómo afectan a  [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md) las herramientas de administración de ofertas
>* [[!DNL Marketo Measure] Parámetros de API explicados](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Información general de API de facebook](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Resumen de integración](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Resumen de integración de AdWords](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Reautorización de cuentas de API conectadas](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
