---
description: 'Prácticas recomendadas para la asignación de etapas:  [!DNL Marketo Measure]'
title: Prácticas recomendadas para la asignación de fases
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 4%

---


# Prácticas recomendadas para la asignación de fases {#best-practices-for-stage-mapping}

## Información general {#overview}

La sección Asignación de etapas de su cuenta de [!DNL Marketo Measure] describe las etapas que [!DNL Marketo Measure] extrae automáticamente de su CRM y cualquier etapa personalizada que haya definido si utiliza el modelo de atribución personalizado. La validez de los datos de [!DNL Marketo Measure] depende de que estas fases se ordenen correctamente para que [!DNL Marketo Measure] pueda comprender con precisión su funnel y la progresión de los registros a lo largo de dicho funnel.

En la sección Asignación de etapas de su instancia de [!DNL Marketo Measure], verá etapas activas e inactivas desde su CRM. Ordene todas las etapas lo mejor posible de acuerdo con la situación actual de su funnel.

Una función adicional que se administra en esta sección es Funnel Stages, que le permite agregar etapas al funnel sin aplicar atribución. Las etapas de funnel se rastrearán como puntos de contacto y se rellenarán en el campo Posiciones de punto de contacto de su CRM. Estas fases de Funnel también se representarán en varios tableros de recorrido de [!DNL Marketo Measure] Discover.

## Mejores prácticas {#best-practices}

Tanto si está evaluando la asignación de etapas por primera vez como si simplemente está revisando su pedido de funnel, es importante tener en cuenta las siguientes prácticas recomendadas.

* ¡El orden lo es todo!
   * Teniendo en cuenta que [!DNL Marketo Measure] extrae las etapas activa e inactiva de su CRM, confirme que todas las etapas que se puedan utilizar en un posible cliente/contacto o una oportunidad se agrupen y se ordenen en consecuencia
* Al definir una fase personalizada, asegúrese de que el seguimiento del historial de campos esté habilitado para cualquier campo utilizado para definir la fase
* No utilice un campo de fórmula para definir una fase personalizada
   * Un campo booleano es la recomendación de prácticas recomendadas
* Tenga en cuenta que la sección de la fase Posible cliente o Contacto se divide en Perdido, Abierto y Convertido; compruebe que las fases se encuentran en la sección de fase adecuada
   * Tener una fase en la sección de fase incorrecta puede generar datos [!DNL Marketo Measure] muy incorrectos
   * Si es cliente de Marketo Measure Ultimate y ha establecido su objeto de panel predeterminado como contacto, no utilice los dos campos siguientes específicos para posible cliente ([obtener más información](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Tenga en cuenta que la sección Fase de oportunidad se divide en Perdidas, Abiertas y Ganadas; valide que las fases se encuentren en la sección de fase adecuada
   * Tener una fase en la sección de fase incorrecta puede generar datos de ingresos de [!DNL Marketo Measure] o canalización altamente incorrectos
* Evite utilizar nombres de fase duplicados (nuestro sistema los detectará y eliminará uno automáticamente).
* Para establecer una regla que compruebe valores NULL, deje en blanco el cuadro de texto del valor.

## Prácticas recomendadas para mantenimiento {#best-practices-for-maintenance}

Revisar la asignación de fase una vez al año garantizará que los datos de oportunidad de [!DNL Marketo Measure] sean precisos y estén actualizados.

Otras razones que podrían déclencheur una revisión de su asignación de etapas incluyen...

* Rotación en su equipo de marketing
* Cualquier cambio en las fases de CRM
* Actualizaciones en el funnel de su organización
* Ver datos de ingresos incorrectos en su informe de [!DNL Marketo Measure]

>[!MORELIKETHIS]
>[Diferencia entre las fases de Funnel y las fases de modelo personalizadas](/help/advanced-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
