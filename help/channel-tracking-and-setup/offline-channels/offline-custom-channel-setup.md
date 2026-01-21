---
unique-page-id: 18874598
description: Configuración de canal personalizado sin conexión - [!DNL Marketo Measure]
title: Configuración de canales personalizados sin conexión
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 1%

---

# Configuración de canales personalizados sin conexión {#offline-custom-channel-setup}

## Introducción {#getting-started}

En comparación con el modo en que [!DNL Marketo Measure] gestiona las reglas de canal en línea, observará que las reglas de canal sin conexión no requieren el uso de una hoja de cálculo. Sin embargo, aún hay una hoja en el plan de implementación, ya que puede resultar útil para pensar en la forma en que desea organizar los canales sin conexión.

La hoja de cálculo tiene tres columnas:

![](assets/1-2.png)

**[!UICONTROL Salesforce] Tipo de campaña** - agregar tipos de campaña identificados en [!DNL Salesforce] aquí

* Por ejemplo, podría ser un correo electrónico, un seminario web, una conferencia o cualquier valor que haya creado para este campo al que desee atribuir puntos de contacto.

**[!UICONTROL Canal]**: agregue sus distintos canales de marketing aquí

**[!UICONTROL Subcanal]** - agregue aquí los subcanales correspondientes

## Lógica de canal sin conexión {#offline-channel-logic}

La lógica del canal sin conexión [!DNL Marketo Measure] está determinada por el objeto Campaign, específicamente el tipo de campaña [!DNL Salesforce]. Cada esfuerzo sin conexión debe tener un tipo de campaña [!DNL Salesforce], como una cena o una feria comercial, porque [!DNL Marketo Measure] se basa en este campo para comprender a qué canal y subcanal asignar.

Los tipos de campañas de SFDC aparecerán en la pestaña del canal sin conexión, enumerados en [!DNL Salesforce] Tipo de campaña. Tenga en cuenta que [!DNL Marketo Measure] solo puede importar tipos de campañas de SFDC para campañas que tengan puntos de contacto de comprador asociados a ellos.

![](assets/2-2.png)

Aquí es donde puede crear la asignación de canal/subcanal en la aplicación [!DNL Marketo Measure]. Es probable que esto implique la creación de nuevos canales y subcanales en la aplicación [!DNL Marketo Measure], lo cual se hace en la sección Crear canales de la aplicación, que se muestra en la siguiente imagen. Es necesario crear nuevos canales y subcanales para [!DNL Marketo Measure] a fin de saber dónde insertar los puntos de contacto. Puede decidir cómo desea que se asignen los tipos de campaña.

![](assets/3-2.png)

## Ejemplo de asignación de canal {#channel-mapping-example}

Por ejemplo, imagine que asiste a dos conferencias de [!DNL Salesforce] al año. Sin embargo, cada conferencia es muy diferente y tiene un público objetivo único. Desea saber cuál de los dos aporta más valor. En su entorno [!DNL Salesforce], puede asignar al evento de enero el tipo de campaña &quot;Conferencia&quot;, asignar un nombre al canal &quot;[!DNL Salesforce]&quot; y al subcanal &quot;Conferencia de enero&quot;.

Ahora desea hacer lo mismo para la conferencia de junio. Como también es una conferencia, se le puede dar el mismo Tipo de campaña, en este caso, &quot;Conferencia&quot;. El canal es el mismo, [!DNL Salesforce], y el subcanal para esta segunda conferencia es &quot;Conferencia de junio&quot;. Esto tiene sentido desde una perspectiva organizacional. Sin embargo, es muy confuso para la lógica [!DNL Marketo Measure] leer y aplicar estas reglas porque ambas campañas tienen el mismo tipo de campaña. El script [!DNL Marketo Measure] no puede asignar datos de un tipo a dos subcanales diferentes. Esto significa que debería crear un nuevo Tipo de campaña para cada subcanal, pero los subcanales pueden tener el mismo canal.

A continuación se muestra un ejemplo de lógica que [!DNL Marketo Measure] no podría leer:

![](assets/4-2.png)

En el escenario anterior, se desea crear un tipo de campaña único porque no se puede asignar el mismo tipo de campaña a dos subcanales diferentes. En su lugar, le recomendamos configurar tipos únicos como los siguientes:

![](assets/5-2.png)

Cualquier tipo de campaña existente debe incluirse en el mapa de canal y se debe agregar &quot;NULL&quot; como canal.

Dedique tiempo a [!DNL Salesforce] para determinar el número y la naturaleza de los tipos de registro existentes que desea incluir y si necesita crear campañas adicionales basadas en la información anterior. Una vez que haya rellenado toda la información necesaria, estará listo para cargar.

Más información sobre [sincronización de campañas sin conexión [!DNL Salesforce] con [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## Gestión de campañas de SFDC para esfuerzos de marketing en línea {#handling-sfdc-campaigns-for-online-marketing-efforts}

Es habitual que los equipos de marketing creen [!DNL Salesforce] campañas para realizar el seguimiento de varios esfuerzos de marketing digital. No hay problema con esta práctica; sin embargo, es importante tratar estas campañas de forma diferente a las verdaderas campañas sin conexión, como el correo directo o las conferencias, por ejemplo. Las campañas relacionadas con eventos digitales (las interacciones que se producen en el sitio web) no se deben sincronizar con [!DNL Marketo Measure]. La sincronización de estas campañas resultaría en la duplicación de puntos de contacto porque el JavaScript [!DNL Marketo Measure] ya está realizando el seguimiento de los esfuerzos en línea.

Otra sugerencia para administrar campañas para actividades en línea es asignar el tipo de campaña [!DNL Salesforce] a NULL. Para ello, cree primero un canal en la aplicación [!DNL Marketo Measure] con el título NULL, como se muestra en la siguiente imagen. Esto se encuentra en la aplicación [!DNL Marketo Measure] en la sección **Crear canales**. Esto resulta útil en caso de que una campaña que no debería sincronizarse se sincronice accidentalmente. Es fácil encontrar la campaña y corregir el estado de sincronización mirando todo lo agrupado en NULL.

![](assets/6-2.png)

## Introducción de las reglas de canal sin conexión en la aplicación {#entering-your-offline-channel-rules-to-the-app}

Una vez que haya editado y actualizado la hoja de cálculo con sus reglas personalizadas, el siguiente paso es volver a crear esta asignación de canal en la aplicación [!DNL Marketo Measure]; en realidad, no cargará una hoja de cálculo para canales sin conexión. En su lugar, debe introducir la información en los cuadros de la lista de selección tal como se muestra en la imagen siguiente. Se encuentra haciendo clic en **[!UICONTROL Canales sin conexión]** en la sección **[!UICONTROL Canales]**.

![](assets/7-2.png)

>[!TIP]
>
>¿Quiere determinar _cuándo_ se extrae un tipo de campaña [!DNL Salesforce] en la asignación de canal [!DNL Marketo Measure]? Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Campañas]** > **[!UICONTROL Campos]** > **[!UICONTROL Tipo]**. A continuación, puede ver qué valores se encuentran en la lista de selección y cuáles están inactivos. Los inactivos no aparecerán como un tipo seleccionable en nuestra sección &quot;[!UICONTROL Canales sin conexión]&quot;. Tenga en cuenta que este proceso puede tardar entre unos minutos y 48 horas.

Haga clic en **[!UICONTROL Guardar]** cuando haya terminado y [!DNL Marketo Measure] cargará los cambios y volverá a procesar los datos.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Tutoriales: Asignación de canales sin conexión](https://experienceleague.adobe.com/es/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>* [[!DNL Marketo Measure] Tutoriales: Sincronizando Campañas Sin Conexión](https://experienceleague.adobe.com/es/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/syncing-offline-campaigns){target="_blank"}
>
>* [Integración de programas de Marketo Engage](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}
