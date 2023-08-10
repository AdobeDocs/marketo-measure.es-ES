---
unique-page-id: 18874600
description: 'Sincronización de campañas sin conexión: [!DNL Marketo Measure] - Documentación del producto'
title: Sincronización de campañas sin conexión
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: e01738222e8845112892c0258cb084a4f0ebb257
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# Sincronización de campañas sin conexión {#syncing-offline-campaigns}

Puede resultar difícil rastrear con precisión las campañas sin conexión y comprender cómo se comparan con sus esfuerzos de marketing digital. [!DNL Marketo Measure] le permite rastrear y atribuir puntos de contacto a sus campañas sin conexión en [!DNL Salesforce], incluso en situaciones en las que [!DNL Salesforce] la campaña no se crea hasta unas semanas después del evento.

>[!NOTE]
>
>Este artículo trata sobre un proceso obsoleto. Recomendamos a los usuarios que utilicen [proceso en la aplicación nuevo y mejorado](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## Antes de sincronizar {#before-you-sync}

A continuación se ofrecen algunas sugerencias para lograr un proceso de sincronización eficaz:

* Las campañas sin conexión hacen referencia a interacciones de marketing que no se producen en línea. Estos incluyen canales de marketing como eventos, seminarios web y ferias comerciales. Incluya solo campañas de marketing sin conexión.
* Si desea incluir campañas que hayan rastreado la actividad en línea antes de la instalación de [!DNL Marketo Measure], asegúrese de establecer la fecha de finalización del punto de contacto como la fecha en la que se implementó el JavaScript en el sitio.
* Es útil mantener la variable [!DNL Marketo Measure] La aplicación se abre en la página Canales sin conexión para que sea fácil identificar los diferentes tipos de campaña, junto con en qué canal de marketing se agrupan los puntos de contacto.

* Compruebe todo antes de pulsar el botón &quot;[!UICONTROL Guardar]&quot; botón!

## Fecha de punto de contacto de actualización masiva {#bulk-update-touchpoint-date}

Entrada [!DNL Salesforce], el campo Fecha de creación en el objeto de miembro de campaña indica la fecha en la que se añadió el miembro de campaña a la campaña. Para que el proceso de sincronización transcurra sin problemas, asegúrese de que el campo Fecha de punto de contacto del comprador tenga la misma fecha que la del objeto de miembro de la campaña de Salesforce. Este paso se realiza con el &quot;[!UICONTROL Botón Fecha de punto de contacto de actualización masiva],&quot; _antes_ si selecciona la [!UICONTROL lista desplegable] en el campo Habilitar puntos de contacto del comprador.

¿Por qué es esto importante? Imagine por un momento que su empresa patrocina un stand en una conferencia en enero. En la conferencia, 100 personas mostraron interés en su producto y proporcionaron su información de contacto para recibir actualizaciones por correo electrónico. Tres semanas después, finalmente creó una campaña en [!DNL Salesforce] para hacer un seguimiento de los resultados de la conferencia.

La fecha de carga sería tres semanas después de la fecha de la conferencia. Para solucionar esta diferencia, la variable [!UICONTROL Fecha de punto de contacto de actualización masiva] se puede utilizar para establecer la fecha adecuada. El botón se muestra en la siguiente imagen.

![](assets/1-3.png)

En este caso, rellenaría la fecha de carga en tres semanas. Este paso debe realizarse antes de configurar &quot;[!UICONTROL Activar puntos de contacto del comprador]Campo &quot;.

En resumen, si utiliza la variable [!UICONTROL Fecha de punto de contacto de actualización masiva] y cambie la fecha del punto de contacto a la fecha del evento, [!DNL Marketo Measure] generará puntos de contacto para la fecha real del evento, no para la fecha de la carga.

También puede actualizar las fechas de todos los miembros de una campaña existente. Al hacerlo, asegúrese de que la fecha del punto de contacto sea la fecha de interacción del miembro. Simplemente haga clic en la Fecha de contacto del comprador de actualización masiva, filtre la lista de miembros de la campaña según corresponda y en el icono &quot;[!UICONTROL Seleccionar fecha]&quot; encima de la lista de miembros de la campaña, añada la misma fecha que la fecha en la que se produjo el evento.

>[!CAUTION]
>
>Asegúrese de actualizar la fecha de Touchpoint _antes_ Si activa los puntos de contacto para todos los miembros de la campaña.

![](assets/2-3.png)

## Cómo crear una campaña y sincronizar los puntos de contacto del comprador {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

Para crear una campaña en [!DNL Salesforce], vaya al [!UICONTROL Campañas] y seleccione &#39;[!UICONTROL Nuevo]&#39; como se muestra en la siguiente imagen. En función de su [!DNL Salesforce] Para configurar, es posible que tenga que agregar Campañas a la barra superior haciendo clic en el icono de signo más (+).

![](assets/3-3.png)

Cuando esté creando esta campaña, haga clic en el icono &quot;[!UICONTROL Activar puntos de contacto del comprador]&quot; y seleccione una de las siguientes opciones de la lista de selección:

![](assets/4-3.png)

* **Incluir todos los miembros de la campaña**
   * Esta opción habilita [!DNL Marketo Measure] para atribuir un Touchpoint a cada miembro de la campaña.

* **Incluir miembros de la campaña &quot;Respondidos&quot;**
   * Esta opción aplica puntos de contacto a los miembros de la campaña que tienen el estado Respondido.

* **Excluir todos los miembros de la campaña.**
   * Esta opción no atribuye puntos de contacto a ningún miembro de la campaña y actúa como un indicador del que se excluyó deliberadamente la campaña [!DNL Marketo Measure]. Si alguna vez sincronizas una campaña con puntos de contacto del comprador en caso de accidente, puedes cambiar el estado a &quot;Excluir todos los miembros de la campaña&quot; y se eliminarán los puntos de contacto.

Una vez elegida una de estas selecciones, [!DNL Marketo Measure] asignará a cada miembro de la campaña un punto de contacto, si corresponde. El posible cliente o contacto que se agrega a la campaña _debe_ tener una dirección de correo electrónico asociada a su registro para [!DNL Marketo Measure] para crear un punto de contacto. Sin una dirección de correo electrónico, [!DNL Marketo Measure] no asignará ningún punto de contacto al miembro de la campaña.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Asignación de canales sin conexión](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] University: Campos de objetos de campaña](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
