---
unique-page-id: 18874698
description: Creación de [!DNL Marketo Measure] Perfil - [!DNL Marketo Measure] - Documentación del producto
title: Creación de [!DNL Marketo Measure] Perfil
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Creación de [!DNL Marketo Measure] Perfil {#creating-a-marketo-measure-profile}

Obtenga información sobre cómo crear una [!DNL Marketo Measure] perfil. Creación de [!DNL Marketo Measure] garantiza que no se encuentren errores de validación al enviar datos a su CRM.

1. Cree un [!DNL Marketo Measure] perfil:

   * Asigne la variable [!DNL Marketo Measure] Conjunto de permisos de administrador
   * Habilite el permiso para ver y editar posibles clientes convertidos

   >[!NOTE]
   >
   >Este perfil puede ser un clon de un [!DNL System Admin] perfil

1. Creación de una [!DNL Marketo Measure] usuario:

   * Asigne el nuevo [!DNL Marketo Measure] Perfil a ese usuario
   * Habilitar &quot;Usuario de marketing&quot; como permiso de nivel de usuario

1. Excluya este perfil de todos los déclencheur, flujos de trabajo y procesos.
1. Inicie sesión en su [!DNL Marketo Measure] Cuenta y vuelva a autorizar la variable [!DNL Salesforce] conexión con el nuevo usuario:

   * Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} e inicie sesión con las nuevas credenciales de Salesforce de producción de usuario
   * Seleccione &quot;[!UICONTROL Configuración]&quot; dentro de la &quot;[!UICONTROL Mi cuenta]&quot; desplegable
   * Seleccione &quot;[!UICONTROL Conexiones]&quot; dentro de la &quot;[!UICONTROL Integraciones]&quot; agrupación
   * Haga clic en el icono Clave a la derecha del conectado actual [!DNL Salesforce] y seleccione Volver a autorizar con Producción. A continuación, vuelva a iniciar sesión con las nuevas credenciales de usuario si se le solicita

   Listo!

   Si tiene alguna duda sobre la creación de una [!DNL Marketo Measure] perfil, póngase en contacto con su gestor de éxito del cliente o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.
