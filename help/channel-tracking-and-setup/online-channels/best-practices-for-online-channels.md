---
description: Prácticas recomendadas para canales en línea de  [!DNL Marketo Measure]
title: Prácticas recomendadas para canales en línea
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 100%

---

# Prácticas recomendadas para canales en línea {#best-practices-for-online-channels}

## Información general {#overview}

Para una creación de informes de [!DNL Marketo Measure] precisa, los canales de marketing deben estar correctamente configurados. El campo de canal de marketing muestra el grupo de nivel superior de las actividades de marketing a las que puede pertenecer un punto de contacto (por ejemplo, búsqueda de pago, directa, social, etc.).

Existen dos aspectos para configurar los canales de marketing: en línea y sin conexión. Este documento se centra en las prácticas recomendadas de [!DNL Marketo Measure] para configurar y mantener sus canales en línea.

Las reglas del canal en línea son las directrices sobre cómo [!DNL Marketo Measure] asigna sus touchpoints digitales, es decir, cualquier touchpoint que se rastree y cree mediante el JS de [!DNL Marketo Measure] en el sitio. Si estas reglas no son completas o no se ordenan correctamente, los puntos de contacto se pueden atribuir al canal incorrecto, lo que reduce la precisión de los informes. Garantizar que las reglas del Canal en línea sean precisas y estén actualizadas, garantizará que sus datos digitales se atribuyan al canal y a los subcanales correctos en sus Informes de [!DNL Marketo Measure].

## Práctica recomendada {#best-practice}

Tanto si configura las reglas por primera vez como si simplemente las revisa para comprobar su precisión, tenga en cuenta las siguientes prácticas recomendadas.

Dedique un tiempo a pensar en la organización de sus campañas de marketing y en cómo encajan en el marco de trabajo de [!DNL Marketo Measure]. Determine qué canales y subcanales deben representarse en sus canales en línea, así como qué campañas, parámetros de UTM o sitios web de referencia diferencian esos canales entre sí.

Cosas que hay que tener en cuenta:

* Todos los canales digitales y subcanales deben representarse con al menos una regla
   * Si el canal no lleva personas a su sitio, no es un Canal en línea
* Es aceptable tener varias reglas para un canal o subcanal
   * Se pueden considerar que varias reglas “proyectan una red más amplia” para garantizar que cada punto de contacto se asigne correctamente. A menudo, los parámetros se pueden añadir incorrectamente o pasar por alto por completo, por lo que tener varias reglas para capturar un canal/subcanal es una buena idea para garantizar la precisión de la asignación.
* La lógica de [!DNL Marketo Measure] da prioridad a la asignación de puntos de contacto en orden descendente, empezando por la fila superior de la hoja de cálculo y bajando 
   * [!DNL Marketo Measure] lee cada regla (fila), buscando el primer ajuste verdadero. A continuación, el punto de contacto se asigna a ese canal/subcanal
   * No ordene la hoja en orden alfabético, ya que esto interfiere con las reglas lógicas.
* Mantener las reglas entre corchetes; no editar ni agregar a las reglas entre corchetes (ejemplo; [búsqueda de pago de AdWords] o [Facebook de pago])
   * Se trata de reglas de [!DNL Marketo Measure] listas para usarse, que tienen lógica integrada y están vinculadas a integraciones de [!DNL Marketo Measure]. Asigne a estas reglas la prioridad principal para esa sección de canal/subcanal para garantizar que las integraciones de [!DNL Marketo Measure] pueden funcionar según lo diseñado.
* Una vez cargado el archivo, no se puede cambiar ninguna de las reglas durante siete días
   * [!DNL Marketo Measure] utiliza este tiempo para procesar y actualizar los puntos de contacto; por lo tanto, asegúrese de comprobar las reglas antes de cargar.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenace}

Una vez guardadas y procesadas las reglas del canal en línea, funcionan continuamente para agrupar los touchpoints digitales. Sin embargo, determinados cambios o escenarios hacen que desee revisar la configuración del canal en línea. [!DNL Marketo Measure] recomienda revisar las reglas del canal en línea una vez cada seis meses. Esto garantiza que sus datos de [!DNL Marketo Measure] estén alineados con las definiciones internas de los canales/subcanales en línea y con el uso de UTM.

Otros elementos que podrían activar a su equipo para realizar el mantenimiento del canal en línea son los siguientes…

* Se inicia un nuevo canal/subcanal digital
* Los parámetros de UTM se actualizan o cambian
* Cambios en la organización del canal o en las convenciones de nomenclatura
* Rotación en su equipo de marketing

Si su equipo ha experimentado cualquiera de los problemas anteriores recientemente, [!DNL Marketo Measure] recomienda revisar las reglas de canales en línea y realizar los cambios correspondientes.

>[!MORELIKETHIS]
>
>* [Configuración del canal en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Parámetros UTM](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Subcanal y canal y de marketing](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Prácticas recomendadas de UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
