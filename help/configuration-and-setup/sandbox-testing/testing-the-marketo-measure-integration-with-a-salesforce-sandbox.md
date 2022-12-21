---
unique-page-id: 18874765
description: 'Prueba de la integración de medidas de Marketo con un Simulador para pruebas de Salesforce: [!DNL Marketo Measure] - Documentación del producto'
title: Prueba de la integración de medidas de Marketo con un Simulador para pruebas de Salesforce
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Prueba de la integración de medidas de Marketo con un Simulador para pruebas de Salesforce {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

Uno de los [!DNL Marketo Measure] las funcionalidades principales son su capacidad para rastrear los esfuerzos de marketing digital a través de acciones en el sitio web y luego llevar esos datos a su producción [!DNL Salesforce org] a través de posibles clientes y contactos. Sin embargo, normalmente no hay posibles clientes entrantes creados desde el sitio web dentro de una integración de espacio aislado, por lo que el enfoque en los datos se centrará exclusivamente en los datos sin conexión.

Estas son las dos fuentes a las que se hace referencia en ambas fases de la prueba. [Pasos 1 a 4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) y [Pasos 5 a 6](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md). Recomendamos revisar estos documentos, ya que proporcionan más detalles en algunas áreas.

1. Deberá crear algunos posibles clientes en un CSV para poder cargarlos en una campaña. La forma de hacerlo es exportar algunos posibles clientes a través de un informe en Salesforce de producción. De lo contrario, puede crear manualmente Posibles clientes en un archivo de Excel y, a continuación, guardarlo como CSV para su importación. Solo se necesitan unos 20 registros. El archivo debe tener las siguientes columnas:

   1. Email
   1. Compañía
   1. Apellido
   1. Nombre (opcional, pero recomendado)

1. Inicie sesión en el entorno de espacio aislado.
1. Primero creará una campaña de prueba. Se recomienda utilizar un tipo de campaña, como Evento o Newsletter.
1. Una vez creada la campaña, cargará Posibles clientes como miembros de la campaña seleccionando **[!UICONTROL Administrar miembros]** > **[!UICONTROL Agregar miembros]** > **[!UICONTROL Importar archivos]**.
1. Una vez completado, en el diseño de la página de Campaign, debe activar los puntos de contacto del comprador, que es un campo de la lista de selección. Elija el valor: **[!UICONTROL Incluir todos los miembros de la campaña]**.

Una vez hecho esto, iniciará una sincronización entre [!DNL Marketo Measure] y [!DNL Salesforce] y aplicar puntos de contacto a los registros de posibles clientes. Se recomienda volver a consultar el día siguiente mediante un informe llamado: &quot;Punto de contacto del comprador sobre posibles clientes&quot; se encuentra en la sección [!UICONTROL Informes de puntos de contacto del comprador] dentro de la ficha Informes . Si el informe rellena un punto de contacto para cada posible cliente, esto es una señal de éxito.
