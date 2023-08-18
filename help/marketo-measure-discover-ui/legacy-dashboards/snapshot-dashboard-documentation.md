---
unique-page-id: 42762600
description: Documentación del tablero de instantáneas - [!DNL Marketo Measure] - Documentación del producto
title: Documentación del tablero de instantáneas
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
feature: Reporting
source-git-commit: f8a37a996afefe78900e57e1eb166cdd50b5347f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---

# Documentación del tablero de instantáneas {#snapshot-dashboard-documentation}

El tablero de instantáneas le permite ver el estado de su CRM en cualquier momento dado, con la distribución de registros en las fases de cliente potencial/contacto y oportunidad.

Este tablero tiene dos mosaicos:

* **Instantánea de cliente potencial/contacto:** El número de registros de contacto o posible cliente de cada fase en la fecha seleccionada.

>[!NOTE]
>
>En todos los paneles de Discover, solo se puede crear un informe de un objeto de persona, ya sea un posible cliente o un contacto. Esto se establece en [!UICONTROL Configuración] > [!UICONTROL Informes] > [!UICONTROL Configuración de atribución] > [!UICONTROL Objeto de panel predeterminado].

* **Instantánea de oportunidad:** El número de registros de oportunidad en cada etapa de la fecha seleccionada.

Este panel admite los siguientes filtros (todos los filtros se aplican a ambos mosaicos):

* Fecha de Instantánea: seleccione la fecha de instantánea.
* CRM Account ID/Name: filtre los registros por nombres o ID de cuenta de CRM.

>[!NOTE]
>
>Las sugerencias solo muestran nombres.

* Channel: filtre los registros por canales. Un registro se asocia a un canal si alguno de sus puntos de contacto está asociado al canal.
* Subchannel: filtre los registros por subcanales. Un registro se asocia a un subcanal si alguno de sus puntos de contacto está asociado al subcanal.
* Campaign: filtre los registros por campañas. Un registro se asocia a una campaña si alguno de sus puntos de contacto está asociado a la campaña.
* Fuente de campaña: filtre los registros por fuentes de campaña. Las fuentes de campaña de ejemplo son [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], etc. Un registro está asociado a una fuente de campaña si alguno de sus puntos de contacto está asociado a la fuente de campaña.
* ID/nombre de cuenta de publicidad: filtre los registros por ID o nombres de cuenta de publicidad. Un registro está asociado a una cuenta de publicidad si alguno de sus puntos de contacto está asociado a una campaña desde las cuentas de publicidad seleccionadas.

>[!NOTE]
>
>Las sugerencias solo muestran nombres.

* Filtros de segmentos: filtre los registros por segmentos personalizados. Un registro se asocia a un segmento si alguno de sus puntos de contacto está asociado al segmento.

En todos los filtros se utiliza la lógica &quot;Y&quot;.

>[!NOTE]
>
>Si un registro cambia de fase en la fecha seleccionada, se contará el registro para las fases desde y hasta, y todas las fases de paso a través.

## Cliente potencial/Instantánea de contacto {#lead-contact-snapshot}

![](assets/one.png)

Las fases incluyen las fases FT, LC y las fases de canal seleccionadas en las fases de cliente potencial/contacto abiertas ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de etapas]).

Puede explorar en profundidad cada barra para ver los registros del posible cliente/contacto de cada etapa.

## Instantánea de oportunidad {#opportunity-snapshot}

![](assets/two.png)

Las fases incluyen FT, LC, fases de canal seleccionadas en las fases de cliente potencial/contacto abiertas ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de etapas]). Y CO y las fases de canal seleccionadas en las fases de oportunidad abierta ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de etapas]).

Puede explorar en profundidad cada barra para ver los registros de oportunidad de cada etapa.
