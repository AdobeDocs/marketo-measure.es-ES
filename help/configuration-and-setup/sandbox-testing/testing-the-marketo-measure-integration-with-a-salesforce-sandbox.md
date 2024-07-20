---
unique-page-id: 18874765
description: 'Prueba de la integración de Marketo Measure con una zona protegida de Salesforce:  [!DNL Marketo Measure]'
title: Prueba de la integración de Marketo Measure con una zona protegida de Salesforce
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 10%

---

# Prueba de la integración de Marketo Measure con una zona protegida de Salesforce {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Una de las funcionalidades principales de [!DNL Marketo Measure] es su capacidad para rastrear los esfuerzos de marketing digital a través de acciones en el sitio web y luego enviar esos datos a su producción [!DNL Salesforce org] a través de posibles clientes y contactos. Sin embargo, normalmente no hay posibles clientes entrantes creados desde el sitio web dentro de una integración de zona protegida, por lo que el enfoque en los datos se centrará en ellos desde un punto de vista puramente sin conexión.

Estas son las dos fuentes a las que se hace referencia en ambas fases de la prueba. [Pasos 1-4](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&amp;language=en_US&amp;type=5) y [Pasos 5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md). Se recomienda revisar estos documentos a medida que proporcionan más detalles en algunas áreas.

1. Debe crear algunos posibles clientes en un CSV para poder cargarlos en una campaña. La manera de hacerlo es exportar algunos posibles clientes a través de un informe en el Salesforce de producción. De lo contrario, puede crear manualmente posibles clientes en un archivo de Excel y, a continuación, guardarlo como CSV para su importación. Sólo necesita unos 20 registros. El archivo debe tener las columnas siguientes:

   1. Correo electrónico
   1. Compañía
   1. Apellido
   1. Nombre (opcional pero recomendado)

1. Inicie sesión en el entorno de espacio aislado.
1. Cree una campaña de prueba. Utilice un tipo de campaña como Evento o Newsletter.
1. Una vez creada la campaña, cargue posibles clientes como miembros de la campaña seleccionando **[!UICONTROL Administrar miembros]** > **[!UICONTROL Agregar miembros]** > **[!UICONTROL Importar archivos]**.
1. Una vez finalizado, vuelva al diseño de la página de Campaign y marque &quot;Habilitar puntos de contacto del comprador&quot;, que es un campo de lista de selección. Elija el valor: **[!UICONTROL Incluir todos los miembros de la campaña]**.

Una vez hecho esto, inicia una sincronización entre [!DNL Marketo Measure] y [!DNL Salesforce] y aplica puntos de contacto a los registros de posibles clientes. Se recomienda consultar al día siguiente mediante un informe llamado: &quot;Buyer Touchpoint sobre posibles clientes&quot; que se encuentra en la carpeta [!UICONTROL Informes de puntos de contacto del comprador] dentro de la pestaña Informes. Si el informe rellena un punto de contacto para cada posible cliente, esto es una señal de éxito.
