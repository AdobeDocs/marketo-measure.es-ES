---
unique-page-id: 42762648
description: 'Documentación del panel de Recorrido de cohorte: [!DNL Marketo Measure]'
title: Documentación del tablero de recorrido de cohorte
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Documentación del tablero de recorrido de cohorte {#cohort-journey-dashboard-documentation}

Los paneles Impacto de cohorte y Embudo permiten a los especialistas en marketing ver la progresión desde una fase de cohorte de inicio durante un periodo seleccionado y medir la tasa de conversión.

La principal diferencia es cómo contamos cada entidad desde la fase de cohorte.

* Canal de cohorte: el resultado de cada fase se deriva directamente de la fase anterior.

   * Solo se cuentan los registros que han pasado por cada fase del canal después de la hora de inicio de la cohorte establecida.

![](assets/cohort-journey-dashboard-documentation-1.png)

* Impacto de cohorte: el resultado de cada fase se deriva de la fase de cohorte, no de la fase anterior.

   * Todos los registros de cada fase se cuentan siempre y cuando se produjeron después de la hora de inicio de la cohorte establecida. Naturalmente, este panel tendrá más registros que el panel Embudo, ya que estamos viendo cómo se vieron afectadas las entidades desde la fase de cohorte, no solo el movimiento a través del canal.

![](assets/cohort-journey-dashboard-documentation-2.png)

Cada tablero tiene dos mosaicos:

* Ingresos de cohorte: cantidad de oportunidad total de todas las oportunidades en la fase Acuerdos del mosaico Recorrido de cohorte.
* Recorrido de cohorte: la progresión a cada fase de recorrido desde la fase de cohorte de inicio durante un periodo de tiempo seleccionado.

>[!NOTE]
>
>En todos los paneles de Discover, solo se puede crear un informe de un objeto de persona, ya sea un posible cliente o un contacto. Esto se establece en [!UICONTROL Configuración] > [!UICONTROL Informes] > [!UICONTROL Configuración de atribución] > [!UICONTROL Objeto de panel predeterminado].

Los paneles admiten los siguientes filtros:

* Fase de cohorte: seleccione la fase de cohorte inicial. Los registros de todas las fases siguientes evolucionan a partir de los registros de la fase de cohorte.
* Intervalo de fecha de cohorte: seleccione el lapso de tiempo para la etapa de cohorte seleccionada. Junto con la fase de cohorte, define el conjunto de datos inicial.
* Fecha de Corte: seleccione la fecha en la que debe producirse la progresión del registro en todas las fases siguientes. El valor predeterminado es hoy. Tenga en cuenta que esto se aplica a todas las etapas que no sean la de cohorte.
* Channel: filtre los registros por canales. Un registro se asocia a un canal si alguno de sus puntos de contacto está asociado al canal.
* Subchannel: filtre los registros por subcanales. Un registro se asocia a un subcanal si alguno de sus puntos de contacto está asociado al subcanal.
* Campaign: filtre los registros por campañas. Un registro se asocia a una campaña si alguno de sus puntos de contacto está asociado a la campaña.
* Fuente de campaña: filtre los registros por fuentes de campaña. Las fuentes de campaña de ejemplo son [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], etc. Un registro está asociado a una fuente de campaña si alguno de sus puntos de contacto está asociado a la fuente de campaña.
* Filtros de segmentos: filtre los registros por segmentos personalizados. Un registro se asocia a un segmento si alguno de sus puntos de contacto está asociado al segmento.

En todos los filtros se utiliza la lógica &quot;Y&quot;.

>[!NOTE]
>
>Los filtros de segmento solo se aplican a la fase LC y después. Si la fase de cohorte es Desconocida o Conocida y uno de los filtros de segmento tiene un valor, el panel no devolverá ningún resultado.

Las etapas incluyen Desconocido, Conocido, LC, etapas de canal seleccionadas en las etapas de cliente potencial/contacto abiertas (Configuración > CRM > Asignación de etapas), OC, etapas de canal seleccionadas en las etapas de oportunidad abiertas (Configuración > CRM > Asignación de etapas) y ofertas (oportunidades ganadas cerradas).

>[!NOTE]
>
>El recuento de registros de una etapa de recorrido, definido como cualquier etapa distinta de la etapa de cohorte, incluye todos los registros nuevos, relacionados con los registros de cohorte, que se crean después de la fecha de inicio del lapso de tiempo seleccionado y antes de la fecha de corte. Esto es causalidad inferida.

Puede explorar en profundidad cada barra para ver los registros de cada etapa.

* Para Desconocido, muestra detalles anónimos del visitante.
* Si se selecciona Conocido, muestra los detalles conocidos del visitante.
* Para las fases LC y Abrir cliente potencial/contacto, muestra los detalles del cliente potencial/contacto.
* Para las fases de oportunidad abierta y las ofertas, muestra detalles de oportunidad.
