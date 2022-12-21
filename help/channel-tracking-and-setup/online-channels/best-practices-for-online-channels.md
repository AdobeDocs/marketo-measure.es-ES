---
description: 'Prácticas recomendadas para canales en línea: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para canales en línea
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Prácticas recomendadas para canales en línea {#best-practices-for-online-channels}

## Resumen {#overview}

Para tener precisión [!DNL Marketo Measure] informes, los canales de marketing deben estar correctamente configurados. El campo Canal de marketing muestra el grupo de nivel más alto de actividades de marketing al que puede pertenecer un punto de contacto (por ejemplo, Búsqueda paga, Directa, Social, etc.).

Existen dos aspectos para configurar los canales de marketing: en línea y sin conexión. Este documento se centrará en el [!DNL Marketo Measure] recomendaciones de prácticas recomendadas para configurar y mantener sus canales en línea.

Las reglas de canal en línea son las directrices para [!DNL Marketo Measure] asigna los puntos de contacto digitales, es decir, todos los puntos de contacto que se rastrean y crean mediante la variable [!DNL Marketo Measure] JS en su sitio. Si estas reglas no son completas o no están ordenadas correctamente, los puntos de contacto se pueden atribuir al canal incorrecto, por lo que se reduce la precisión de los informes. Garantizar que las reglas del canal en línea sean precisas y estén actualizadas garantizará que los datos digitales se atribuyan al canal y los subcanales correctos del canal en línea [!DNL Marketo Measure] Informes.

## Práctica recomendada {#best-practice}

Tanto si está configurando sus reglas por primera vez como si solo está revisándolas para comprobar la precisión, tenga en cuenta las siguientes prácticas recomendadas.

Tómese un tiempo para pensar en la organización de sus campañas de marketing y en cómo encajan en el [!DNL Marketo Measure] marco. Determine qué canales y subcanales deben representarse en sus canales en línea, así como qué campañas, parámetros de UTM o sitios web de referencia diferencian esos canales entre sí.

Cosas que hay que tener en cuenta:

* Todos los canales digitales y subcanales deben representarse con al menos una regla
   * Si el canal no lleva a las personas a su sitio, no es un canal en línea
* Está bien tener múltiples reglas para un canal/subcanal
   * Se pueden considerar varias reglas como &quot;colar una red más amplia&quot; para garantizar que cada punto de contacto se asigne correctamente. A menudo, los parámetros se pueden agregar o perder por completo de forma incorrecta, por lo que es aconsejable tener varias reglas para capturar un canal o subcanal para garantizar la precisión de la asignación.
* [!DNL Marketo Measure] la lógica prioriza la asignación de puntos de contacto en orden descendente empezando por la fila superior de la hoja de cálculo y bajando
   * [!DNL Marketo Measure] lee cada regla (fila), buscando el verdadero y el primer ajuste. A continuación, el punto de contacto se asigna a ese canal/subcanal
   * No ordene la hoja en orden alfabético, ya que esto interferirá con las reglas lógicas.
* Mantener las reglas entre corchetes, no editar ni agregar a las reglas entre corchetes (ejemplo; [Búsqueda de pago de AdWords] o [Facebook de pago] )
   * Están fuera de la caja [!DNL Marketo Measure] reglas que han incorporado lógica, que están vinculadas a la variable [!DNL Marketo Measure] integraciones. Asigne prioridad superior a estas reglas para esa sección de canal/subcanal para garantizar que la variable [!DNL Marketo Measure] las integraciones pueden funcionar tal como están diseñadas.
* Una vez cargado el archivo, no se puede cambiar ninguna de las reglas durante siete días
   * [!DNL Marketo Measure] utiliza este tiempo para procesar y actualizar los touchpoints, por lo que asegúrese de comprobar las reglas antes de cargar.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenace}

Una vez guardadas y procesadas, las reglas de canal en línea funcionan continuamente para incluir sus puntos de contacto digitales. Sin embargo, algunos cambios o escenarios hacen que desee revisar la configuración del canal en línea. [!DNL Marketo Measure] recomienda revisar las reglas del canal en línea una vez cada seis meses. Esto garantizará que su [!DNL Marketo Measure] Los datos de se alinean con las definiciones internas de canales/subcanales en línea y el uso de UTM.

Otros artículos que podrían déclencheur a su equipo para realizar el mantenimiento del canal en línea incluyen:.

* Se inicia el nuevo canal/subcanal digital
* Los parámetros de UTM se actualizan o cambian
* Cambios en la organización del canal o convenciones de nomenclatura
* Volumen de negocio en su equipo de marketing

Si su equipo ha experimentado cualquiera de los cambios anteriores recientemente [!DNL Marketo Measure] recomienda revisar las reglas de los canales en línea y realizar los cambios correspondientes.

>[!MORELIKETHIS]
>
>* [Configuración del canal en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Parámetros de UTM](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Canal de marketing y subcanal](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Prácticas recomendadas de UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)

