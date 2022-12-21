---
unique-page-id: 42762600
description: 'Documentación del tablero de instantáneas: [!DNL Marketo Measure] - Documentación del producto'
title: Documentación del tablero de instantáneas
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 1%

---

# Documentación del tablero de instantáneas {#snapshot-dashboard-documentation}

El tablero de instantáneas le permite ver el estado de su CRM en cualquier momento, con la distribución de registros en las etapas de posible cliente/contacto y oportunidad.

Este tablero tiene dos mosaicos:

* **Instantánea de posible cliente/contacto:** Número de registros de posible cliente o contacto en cada etapa de la fecha seleccionada.

>[!NOTE]
>
>En todos los tableros de Discover, solo se puede informar de un objeto de persona, ya sea posible Cliente o Contacto. Esto se configura en [!UICONTROL Configuración] > [!UICONTROL Informes] > [!UICONTROL Configuración de atribución] > [!UICONTROL Objeto de tablero predeterminado].

* **Instantánea de oportunidad:** Número de registros de oportunidad en cada etapa de la fecha seleccionada.

Este tablero admite los siguientes filtros (todos los filtros se aplican a ambos mosaicos):

* Fecha de instantánea: seleccione la fecha de la instantánea.
* Nombre/ID de cuenta de CRM: filtre los registros por ID de cuenta de CRM o nombres.

>[!NOTE]
>
>Las sugerencias solo muestran nombres.

* Canal: filtre los registros por canales. Un registro está asociado a un canal si alguno de sus puntos de contacto está asociado al canal.
* Subcanal: filtre los registros por subcanales. Un registro está asociado a un subcanal si alguno de sus puntos de contacto está asociado al subcanal.
* Campaña: filtrar los registros por campañas. Un registro está asociado a una campaña si alguno de sus puntos de contacto está asociado a ella.
* Fuente de campaña: filtre los registros por fuentes de campaña. Ejemplo de fuentes de campaña: [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], etc. Un registro está asociado a un origen de campaña si alguno de sus puntos de contacto está asociado al origen de la campaña.
* Nombre/ID de la cuenta del anuncio: filtre los registros por ID de cuenta de publicidad o nombres. Un registro está asociado a una cuenta de publicidad si alguno de sus puntos de contacto está asociado a una campaña de las cuentas de publicidad seleccionadas.

>[!NOTE]
>
>La sugerencia solo muestra nombres.

* Filtros de segmento: filtre los registros por segmentos personalizados. Un registro está asociado a un segmento si alguno de sus puntos de contacto está asociado a él.

En todos los filtros se utiliza la lógica &quot;Y&quot;.

>[!NOTE]
>
>Si un registro cambia de etapa en la fecha seleccionada, el registro se contabilizará para las etapas de y a y todas las etapas de paso.

## Cliente potencial/Instantánea de contacto {#lead-contact-snapshot}

![](assets/one.png)

Las etapas incluyen las fases FT, LC y Embudo seleccionado en las fases de apertura de posible cliente/contacto ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de fases]).

Puede explorar en profundidad desde cada barra para ver los registros de posible cliente/contacto de cada etapa.

## Instantánea de oportunidad {#opportunity-snapshot}

![](assets/two.png)

Las etapas incluyen FT, LC, etapas de canal seleccionadas en las etapas de posible cliente/contacto abiertos ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de fases]). Y OC y etapas de canal seleccionadas en las fases de oportunidad abierta ([!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL Asignación de fases]).

Puede explorar en profundidad desde cada barra para ver los registros de oportunidad de cada etapa.
