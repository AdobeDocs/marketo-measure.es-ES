---
description: 'Prácticas recomendadas para la asignación de escenarios: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la asignación de escenarios
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Prácticas recomendadas para la asignación de escenarios {#best-practices-for-stage-mapping}

## Resumen {#overview}

La sección Asignación de escenario de su [!DNL Marketo Measure] la cuenta describe las etapas que [!DNL Marketo Measure] extrae automáticamente de su CRM y de cualquier fase personalizada que haya definido si utiliza el modelo de atribución personalizado. La validez de su [!DNL Marketo Measure] los datos dependen de que estas etapas estén ordenadas correctamente para que [!DNL Marketo Measure] puede comprender con precisión su embudo y la progresión de registros a través de dicho canal.

En la sección Asignación de ensayo de su [!DNL Marketo Measure] por ejemplo, verá etapas activas e inactivas de su CRM. Ordene todas las etapas de la mejor manera posible en consonancia con la situación actual de su embudo.

Una característica adicional que se administra en esta sección son las etapas de canal, que le permiten agregar etapas al canal sin aplicar atribución. Los escenarios de canal se rastrearán como puntos de contacto y se rellenarán en el campo Posiciones de punto de contacto de su CRM. Estas etapas de canal también se representarán dentro de varios tableros de recorrido en [!DNL Marketo Measure] Discover.

## Prácticas recomendadas {#best-practices}

Tanto si está evaluando la asignación de escenarios por primera vez como si solo está revisando el orden de los canales, es importante tener en cuenta las siguientes prácticas recomendadas.

* ¡El orden es todo!
   * Consideración [!DNL Marketo Measure] extrae de su CRM las etapas activas e inactivas, confirme que cualquier etapa que se pueda usar en un posible cliente/contacto u oportunidad se agrupa y se ordena en consecuencia
* Al definir un escenario personalizado, asegúrese de que el seguimiento del historial de campos esté habilitado para cualquier campo utilizado para definir el escenario
* No utilice un campo de fórmula para definir un escenario personalizado
   * Un campo booleano es la mejor recomendación
* Tenga en cuenta que la sección Plomo o Contacto se divide en Perdido, Abierto y Convertido; valide que las fases se encuentran en la sección de escenario adecuada
   * Tener un escenario en la sección de etapa incorrecta puede resultar en un estado muy incorrecto [!DNL Marketo Measure] data
* Tenga en cuenta que la sección Etapa de oportunidad se divide en Perdido, Abierto y Ganado; valide que las fases se encuentran en la sección de escenario adecuada
   * Tener un escenario en la sección de etapa incorrecta puede resultar en un estado muy incorrecto [!DNL Marketo Measure] datos de ingresos de canalización
* Evite utilizar nombres de escenario duplicados (nuestro sistema los detectará y quitará uno automáticamente).

## Prácticas recomendadas para el mantenimiento {#best-practices-for-maintenance}

Al revisar la asignación de fases una vez al año, se asegurará de que los datos de oportunidad se encuentran en [!DNL Marketo Measure] es preciso y está actualizado.

Otras razones que pueden déclencheur una revisión de la asignación de escenarios son:

* Volumen de negocio en su equipo de marketing
* Cualquier cambio en las etapas de CRM
* Actualizaciones en el canal de su organización
* Visualización de datos de ingresos incorrectos en su [!DNL Marketo Measure] creación de informes

>[!MORELIKETHIS]
>
>[La diferencia entre las etapas del canal y las etapas del modelo personalizado](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
