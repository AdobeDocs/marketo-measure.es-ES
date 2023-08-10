---
description: 'Prácticas recomendadas para canales en línea: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para canales en línea
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 8%

---

# Prácticas recomendadas para canales en línea {#best-practices-for-online-channels}

## Información general {#overview}

Para tener precisión [!DNL Marketo Measure] Para los informes de, los canales de marketing deben estar correctamente configurados. El campo de canal de marketing muestra el grupo de nivel superior de actividades de marketing a las que puede pertenecer un punto de contacto (por ejemplo, Búsqueda de pago, Directa, Social, etc.).

Existen dos aspectos para configurar los canales de marketing: en línea y sin conexión. Este documento se centrará en la [!DNL Marketo Measure] prácticas recomendadas para configurar y mantener sus canales en línea.

Las reglas de canal en línea son las directrices sobre cómo [!DNL Marketo Measure] asigna sus puntos de contacto digitales, es decir, cualquier punto de contacto que se rastree y cree mediante el [!DNL Marketo Measure] JS en el sitio. Si estas reglas no son completas o no se ordenan correctamente, los puntos de contacto se pueden atribuir al canal incorrecto, lo que reduce la precisión de los informes. Garantizar que las reglas del canal en línea sean precisas y estén actualizadas garantizará que los datos digitales se atribuyan al canal y a los subcanales correctos en su [!DNL Marketo Measure] Informes.

## Práctica recomendada {#best-practice}

Tanto si configura las reglas por primera vez como si simplemente las revisa para comprobar su precisión, tenga en cuenta las siguientes prácticas recomendadas.

Dedique un tiempo a pensar en la organización de sus campañas de marketing y en cómo encajan en la [!DNL Marketo Measure] marco. Determine qué canales y subcanales deben representarse en sus canales en línea, así como qué campañas, parámetros de UTM o sitios web de referencia diferencian esos canales entre sí.

Cosas que hay que tener en cuenta:

* Todos los canales digitales y subcanales deben representarse con al menos una regla
   * Si el canal no lleva personas a su sitio, no es un canal en línea
* Es aceptable tener varias reglas para un canal o subcanal
   * Se puede considerar que varias reglas &quot;proyectan una red más amplia&quot; para garantizar que cada punto de contacto se asigne correctamente. A menudo, los parámetros se pueden añadir incorrectamente o pasar por alto por completo, por lo que tener varias reglas para capturar un canal/subcanal es una buena idea para garantizar la precisión de la asignación.
* [!DNL Marketo Measure] La lógica prioriza la asignación de puntos de contacto en orden descendente, empezando por la fila superior de la hoja de cálculo y descendiendo
   * [!DNL Marketo Measure] lee cada regla (fila), buscando el verdadero y el primer ajuste. A continuación, el punto de contacto se asigna a ese canal/subcanal
   * No ordene la hoja en orden alfabético, ya que esto interferirá con las reglas lógicas.
* Mantener las reglas entre corchetes; no editar ni agregar a las reglas entre corchetes (ejemplo; [Búsqueda de pago de AdWords] o [Facebook de pago] )
   * Estas opciones están listas para usarse [!DNL Marketo Measure] reglas que tienen lógica integrada, que están vinculadas a [!DNL Marketo Measure] integraciones. Asigne a estas reglas la prioridad principal para esa sección de canal/subcanal para garantizar que [!DNL Marketo Measure] Las integraciones de pueden funcionar según lo diseñado.
* Una vez cargado el archivo, no se puede cambiar ninguna de las reglas durante siete días
   * [!DNL Marketo Measure] utiliza este tiempo para procesar y actualizar los puntos de contacto; por lo tanto, asegúrese de comprobar las reglas antes de cargar.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenace}

Una vez guardadas y procesadas, las reglas del canal en línea funcionan continuamente para agrupar los puntos de contacto digitales. Sin embargo, determinados cambios o escenarios hacen que desee revisar la configuración del canal en línea. [!DNL Marketo Measure] recomienda revisar las reglas del canal en línea una vez cada seis meses. Esto garantizará que su [!DNL Marketo Measure] Los datos de están alineados con las definiciones internas de canales/subcanales en línea y con el uso de UTM.

Otros elementos que podrían poner en déclencheur a su equipo para realizar el mantenimiento del canal en línea son....

* Se inicia un nuevo canal/subcanal digital
* Los parámetros de UTM se actualizan o cambian
* Cambios en la organización del canal o en las convenciones de nomenclatura
* Facturación en su equipo de marketing

Si su equipo ha experimentado cualquiera de los problemas anteriores recientemente [!DNL Marketo Measure] recomienda revisar las reglas de canales en línea y realizar los cambios correspondientes.

>[!MORELIKETHIS]
>
>* [Configuración de canal en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Parámetros UTM](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Canal y subcanal de marketing](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Prácticas recomendadas de UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
