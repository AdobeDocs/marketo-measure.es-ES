---
unique-page-id: 18874600
description: Sincronización de campañas sin conexión - [!DNL Marketo Measure] - Documentación del producto
title: Sincronización de campañas sin conexión
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# Sincronización de campañas sin conexión {#syncing-offline-campaigns}

Puede resultar difícil rastrear con precisión las campañas sin conexión y comprender cómo se comparan con sus esfuerzos de marketing digital. [!DNL Marketo Measure] le permite rastrear y atribuir puntos de contacto a sus campañas sin conexión en [!DNL Salesforce], incluso en situaciones en las que [!DNL Salesforce] campaña no se crea hasta unas semanas después del evento.

## Antes de sincronizar {#before-you-sync}

A continuación se ofrecen algunas sugerencias para un proceso de sincronización eficaz:

* Las campañas sin conexión hacen referencia a interacciones de marketing que no se producen en línea. Estos incluyen canales de marketing como eventos, seminarios web y ferias. Incluya únicamente campañas de marketing sin conexión.
* Si desea incluir campañas que hayan realizado un seguimiento de la actividad en línea antes de la instalación [!DNL Marketo Measure], asegúrese de establecer la fecha de finalización de Touchpoint como la fecha en la que se implementó nuestro JavaScript en su sitio.
* Es útil mantener la variable [!DNL Marketo Measure] la aplicación se abre en la página Canales sin conexión para que sea fácil identificar los diferentes tipos de campaña, junto con el canal de marketing en el que se agruparán los puntos de contacto.

* Haga doble clic en todo antes de pulsar el botón &quot;[!UICONTROL Guardar]&quot; botón!

## Fecha de punto de contacto de actualización masiva {#bulk-update-touchpoint-date}

En [!DNL Salesforce], el campo Fecha de creación del objeto miembro de campaña indica la fecha en la que se agregó el miembro de campaña a la campaña. Para que el proceso de sincronización se realice sin problemas, asegúrese de que el campo Fecha de punto de contacto del comprador tenga la misma fecha que la del objeto miembro de la campaña de Salesforce. Este paso se realiza utilizando la variable &quot;[!UICONTROL Botón Actualización masiva de fecha de punto de contacto],&quot; _before_ seleccione el [!UICONTROL lista de selección] en el campo Habilitar puntos de contacto del comprador .

¿Por qué es importante? Imaginen por un momento que su compañía patrocinó un stand en una conferencia en enero. En la conferencia, 100 personas mostraron interés en su producto y proporcionaron su información de contacto para recibir actualizaciones por correo electrónico. Tres semanas después, finalmente creó una campaña en [!DNL Salesforce] para hacer un seguimiento de los resultados de la conferencia.

La fecha de carga sería tres semanas después de la fecha de la conferencia. Para corregir esta diferencia, la variable [!UICONTROL Fecha de punto de contacto de actualización masiva] para establecer la fecha adecuada. El botón se muestra en la imagen siguiente.

![](assets/1-3.png)

En este caso, rellenaría la fecha de carga tres semanas. Este paso debe realizarse antes de configurar la variable[!UICONTROL Habilitar puntos de contacto del comprador]&quot;.

En resumen, si usa la variable [!UICONTROL Fecha de punto de contacto de actualización masiva] y cambiar la fecha del punto de contacto a la fecha del evento, [!DNL Marketo Measure] generará Touchpoints para la fecha real del evento, no para la fecha de la carga.

También puede actualizar las fechas de todos los miembros de la campaña en una campaña existente. Al hacer esto, asegúrese de que la fecha del punto de contacto sea la fecha de la interacción del miembro. Simplemente haga clic en la Fecha del punto de contacto del comprador de la actualización masiva, filtre la lista de miembros de la campaña según corresponda y en el[!UICONTROL Seleccionar fecha]&quot; sobre la lista de miembros de la campaña, agregue la misma fecha que la fecha en que se produjo el evento.

>[!CAUTION]
>
>Asegúrese de actualizar la fecha de Touchpoint _before_ los touchpoints se habilitan para todos los miembros de la campaña.

![](assets/2-3.png)

## Cómo crear una campaña y sincronizar puntos de contacto del comprador {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

Para crear una campaña en [!DNL Salesforce], vaya a la [!UICONTROL Campañas] y seleccione[!UICONTROL Nuevo]&#39; como se muestra en la imagen siguiente. Según el [!DNL Salesforce] Para configurar, es posible que tenga que agregar Campañas a la barra superior haciendo clic en el icono de signo más (+).

![](assets/3-3.png)

Cuando esté creando esta campaña, haga clic en el botón[!UICONTROL Habilitar puntos de contacto del comprador]&quot; y seleccione una de las siguientes opciones en la lista de selección:

![](assets/4-3.png)

* **Incluir todos los miembros de la campaña**
   * Esta opción habilita [!DNL Marketo Measure] para atribuir un Touchpoint a cada miembro de la campaña.

* **Incluir miembros de campaña &quot;Respondidos&quot;.**
   * Esta opción aplica Touchpoints a los miembros de la campaña que tengan el estado &quot;Respondido&quot;.

* **Excluya todos los miembros de la campaña.**
   * Esta opción no atribuye Touchpoints a ningún miembro de la campaña y actúa como un indicador del que la campaña se haya excluido deliberadamente [!DNL Marketo Measure]. Si alguna vez sincroniza una campaña con puntos de contacto del comprador por accidente, puede cambiar el estado a &quot;Excluir todos los miembros de la campaña&quot; y se eliminarán los puntos de contacto.

Una vez elegida una de estas selecciones, [!DNL Marketo Measure] asignará a cada miembro de la campaña un Touchpoint, si corresponde. El posible cliente o contacto que se agrega a la campaña _must_ tener una dirección de correo electrónico asociada a su registro para [!DNL Marketo Measure] para crear un touchpoint. Sin una dirección de correo electrónico, [!DNL Marketo Measure] no asignará un touchpoint al miembro de la campaña.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Asignación de canales sin conexión](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] Universidad: Campos de objeto de campaña](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
