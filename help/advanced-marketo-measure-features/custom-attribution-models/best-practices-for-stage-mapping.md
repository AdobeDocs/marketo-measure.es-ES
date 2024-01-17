---
description: 'Prácticas recomendadas para la asignación de etapas: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la asignación de fases
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 7bb458941e513b6155b834d27f76f0b5df4e0a09
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 3%

---

# Prácticas recomendadas para la asignación de fases {#best-practices-for-stage-mapping}

## Información general {#overview}

La sección Asignación de etapas de su [!DNL Marketo Measure] cuenta describe las etapas que [!DNL Marketo Measure] extrae automáticamente de su CRM y de cualquier fase personalizada que haya definido si utiliza el modelo de atribución personalizado. La validez de su [!DNL Marketo Measure] Los datos de dependen de que estas fases se ordenen correctamente para que [!DNL Marketo Measure] puede comprender con precisión su canal y la progresión de los registros a lo largo de dicho canal.

En la sección Asignación de etapas de su [!DNL Marketo Measure] Por ejemplo, verá las etapas activas e inactivas desde su CRM. Ordene todas las etapas lo mejor posible de acuerdo con la situación actual de su canal.

Una función adicional que se administra en esta sección es Etapas de canal, que le permite añadir etapas al canal sin aplicar atribución. Las etapas de canal se rastrearán como puntos de contacto y se rellenarán en el campo Posiciones de punto de contacto de su CRM. Estas fases de canal también se representarán en varios paneles de recorrido en [!DNL Marketo Measure] Descubrir.

## Prácticas recomendadas {#best-practices}

Tanto si está evaluando la asignación de etapas por primera vez como si está revisando el orden del canal, es importante tener en cuenta las siguientes prácticas recomendadas.

* ¡El orden lo es todo!
   * Consideración [!DNL Marketo Measure] obtiene etapas activas e inactivas de su CRM, confirme que cualquier etapa que se pueda utilizar en un cliente potencial/contacto o oportunidad se agrupen y se ordenen en consecuencia
* Al definir una fase personalizada, asegúrese de que el seguimiento del historial de campos esté habilitado para cualquier campo utilizado para definir la fase
* No utilice un campo de fórmula para definir una fase personalizada
   * Un campo booleano es la recomendación de prácticas recomendadas
* Tenga en cuenta que la sección de la fase Posible cliente o Contacto se divide en Perdido, Abierto y Convertido; compruebe que las fases se encuentran en la sección de fase adecuada
   * Tener una etapa en la sección de etapa incorrecta puede resultar en una etapa altamente incorrecta [!DNL Marketo Measure] datos
   * Si es cliente de Marketo Measure Ultimate y ha establecido su objeto de panel predeterminado como contacto, no utilice los dos campos siguientes específicos de posible cliente ([obtenga más información aquí](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Tenga en cuenta que la sección Fase de oportunidad se divide en Perdidas, Abiertas y Ganadas; valide que las fases se encuentren en la sección de fase adecuada
   * Tener una etapa en la sección de etapa incorrecta puede resultar en una etapa altamente incorrecta [!DNL Marketo Measure] datos de ingresos de ingresos o canalizaciones
* Evite utilizar nombres de fase duplicados (nuestro sistema los detectará y eliminará uno automáticamente).
* Para establecer una regla que compruebe valores NULL, deje en blanco el cuadro de texto del valor.

## Prácticas recomendadas para mantenimiento {#best-practices-for-maintenance}

Revisar la asignación de etapas una vez al año garantizará que los datos de oportunidad en [!DNL Marketo Measure] es precisa y está actualizada.

Otras razones que podrían déclencheur una revisión de su asignación de etapas incluyen...

* Rotación en su equipo de marketing
* Cualquier cambio en las fases de CRM
* Actualizaciones en el canal de su organización
* Ver datos de ingresos incorrectos en su [!DNL Marketo Measure] informe

>[!MORELIKETHIS]
>
>[La diferencia entre las fases de canal y las fases del modelo personalizado](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
