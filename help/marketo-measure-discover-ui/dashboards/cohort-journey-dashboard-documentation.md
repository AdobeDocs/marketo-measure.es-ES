---
unique-page-id: 42762648
description: 'Documentación del tablero Recorrido de cohorte: [!DNL Marketo Measure] - Documentación del producto'
title: Documentación del panel Recorrido de cohorte
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
source-git-commit: 28f1400e8e13c091e8ea2a3bef115a0db810c2e0
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Documentación del panel Recorrido de cohorte {#cohort-journey-dashboard-documentation}

Los paneles Impacto de cohorte y Canal permiten a los especialistas en marketing ver la progresión desde una etapa de cohorte de inicio durante un lapso de tiempo seleccionado y medir la tasa de conversión.

La principal diferencia es cómo contamos cada entidad desde la fase de cohorte.

* Canal de cohorte: El resultado de cada etapa se deriva directamente de la etapa anterior.

   * Solo se cuentan los registros que han pasado por cada fase del canal después de la hora de inicio de la cohorte establecida.

![](assets/cohort-journey-dashboard-documentation-1.png)

* Impacto de cohorte: El resultado de cada etapa se deriva de la etapa de cohorte, no de la anterior.

   * Todos los registros de cada etapa se cuentan siempre que se hayan producido después de la hora de inicio de la cohorte establecida. Naturalmente, este tablero tendrá más registros que el tablero Embudo, ya que estamos viendo cómo las entidades se vieron afectadas desde la etapa de cohorte, no solo el movimiento a través del canal.

![](assets/cohort-journey-dashboard-documentation-2.png)

Cada tablero tiene dos mosaicos:

* Ingresos de cohorte: Cantidad total de oportunidades de todas las oportunidades de la fase Ofertas del mosaico Recorrido de cohorte.
* Recorrido de cohorte: La progresión a cada fase de recorrido desde la fase de cohorte de inicio para un lapso de tiempo seleccionado.

>[!NOTE]
>
>En todos los tableros de Discover, solo se puede informar de un objeto de persona, ya sea posible Cliente o Contacto. Esto se configura en [!UICONTROL Configuración] > [!UICONTROL Informes] > [!UICONTROL Configuración de atribución] > [!UICONTROL Objeto de tablero predeterminado].

Los tableros admiten los siguientes filtros:

* Etapa de cohorte: seleccione la etapa de cohorte de inicio. Los registros de todas las etapas siguientes evolucionan a partir de los registros de la etapa de cohorte.
* Intervalo de fechas de cohorte: seleccione el lapso de tiempo para la etapa de cohorte seleccionada. Junto con Fase de cohorte, define el conjunto de datos de inicio.
* Fecha de corte: seleccione la fecha en la que debe producirse la progresión del registro en todas las etapas siguientes. El valor predeterminado es hoy. Tenga en cuenta que esto se aplica a todas las etapas que no sean la fase de cohorte.
* Canal: filtre los registros por canales. Un registro está asociado a un canal si alguno de sus puntos de contacto está asociado al canal.
* Subcanal: filtre los registros por subcanales. Un registro está asociado a un subcanal si alguno de sus puntos de contacto está asociado al subcanal.
* Campaña: filtrar los registros por campañas. Un registro está asociado a una campaña si alguno de sus puntos de contacto está asociado a ella.
* Fuente de campaña: filtre los registros por fuentes de campaña. Ejemplo de fuentes de campaña: [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], etc. Un registro está asociado a un origen de campaña si alguno de sus puntos de contacto está asociado al origen de la campaña.
* Filtros de segmento: filtre los registros por segmentos personalizados. Un registro está asociado a un segmento si alguno de sus puntos de contacto está asociado a él.

En todos los filtros se utiliza la lógica &quot;Y&quot;.

>[!NOTE]
>
>Los filtros de segmento solo se aplican al escenario LC y después. Si la etapa de cohorte es Desconocida o Conocida y uno de los filtros de segmento tiene un valor, el panel no devolverá ningún resultado.

Los escenarios incluyen Desconocido, Conocido, LC, etapas de Embudo seleccionadas en Fases de Cliente/Contacto Abiertos (Configuración > CRM > Asignación de Fases), OC, etapas de Embudo seleccionadas en Fases de Oportunidad Abierta (Configuración > CRM > Asignación de Fases) y Ofertas (Oportunidades Ganadas Cerradas).

>[!NOTE]
>
>El recuento de los registros de una fase de recorrido, definida como cualquier fase distinta de la fase de cohorte, incluye todos los registros nuevos, relacionados con los registros de cohorte, que se crean después de la fecha de inicio del lapso de tiempo seleccionado y antes de la fecha de corte. Esto es causalidad inferida.

Puede explorar en profundidad desde cada barra para ver los registros de cada etapa.

* Para Desconocido, muestra detalles de visitantes anónimos.
* Para Conocido, muestra los detalles conocidos del visitante.
* Para las fases LC y Abrir posible cliente/contacto, muestra los detalles de posible cliente/contacto.
* Para OC, etapas de Oportunidad Abierta y Ofertas, muestra detalles de Oportunidad.
