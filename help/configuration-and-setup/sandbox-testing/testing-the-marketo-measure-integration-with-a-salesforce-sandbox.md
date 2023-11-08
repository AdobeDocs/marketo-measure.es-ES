---
unique-page-id: 18874765
description: 'Prueba de la integración de Marketo Measure con una zona protegida de Salesforce: [!DNL Marketo Measure] - Documentación del producto'
title: Prueba de la integración de Marketo Measure con una zona protegida de Salesforce
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: b8ea008c594ed114323dedd3762d1265287193c7
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 9%

---

# Prueba de la integración de Marketo Measure con una zona protegida de Salesforce {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Uno de los [!DNL Marketo Measure] Las funcionalidades principales son su capacidad para rastrear los esfuerzos de marketing digital a través de acciones en el sitio web y luego transferir esos datos a la producción [!DNL Salesforce org] mediante posibles clientes y contactos. Sin embargo, normalmente no hay posibles clientes entrantes creados desde el sitio web dentro de una integración de zona protegida, por lo que el enfoque en los datos se centrará en ellos desde un punto de vista puramente sin conexión.

Estas son las dos fuentes a las que se hace referencia en ambas fases de la prueba. [Pasos 1-4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) y [Pasos 5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md). Se recomienda revisar estos documentos, ya que proporcionan más detalles en algunas áreas.

1. Debe crear algunos posibles clientes en un CSV para poder cargarlos en una campaña. La manera de hacerlo es exportar algunos posibles clientes a través de un informe en el Salesforce de producción. De lo contrario, puede crear manualmente posibles clientes en un archivo de Excel y, a continuación, guardarlo como CSV para su importación. Sólo necesita unos 20 registros. El archivo debe tener las siguientes columnas:

   1. Correo electrónico
   1. Compañía
   1. Apellido
   1. Nombre (opcional pero recomendado)

1. Inicie sesión en el entorno de espacio aislado.
1. Primero creará una campaña de prueba. Se recomienda utilizar un tipo de campaña como Evento o Newsletter.
1. Una vez creada la campaña, cargará posibles clientes como miembros de la campaña seleccionando **[!UICONTROL Administrar miembros]** > **[!UICONTROL Añadir miembros]** > **[!UICONTROL Importar archivos]**.
1. Una vez finalizado, vuelva al diseño de la página de Campaign y marque &quot;Habilitar puntos de contacto del comprador&quot;, que es un campo de lista de selección. Elija el valor: **[!UICONTROL Incluir todos los miembros de campaña]**.

Una vez hecho esto, se iniciará una sincronización entre [!DNL Marketo Measure] y [!DNL Salesforce] y aplicar puntos de contacto a los registros de posibles clientes. Se recomienda volver a consultar al día siguiente mediante un informe denominado &quot;Punto de contacto del comprador sobre posibles clientes&quot; que se encuentra en el [!UICONTROL Informes de puntos de contacto del comprador] dentro de la pestaña Informes. Si el informe rellena un punto de contacto para cada posible cliente, esto es una señal de éxito.
