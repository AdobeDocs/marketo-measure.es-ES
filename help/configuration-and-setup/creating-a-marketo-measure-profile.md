---
description: Creando una guía de perfil [!DNL Marketo Measure] para usuarios de Marketo Measure
title: Creando un perfil [!DNL Marketo Measure]
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: c8f57308-7e33-4e41-a385-b55041c78939
    internal-label: Integrations
subfeature_v2:
  - id: e601da04-8de6-4fc3-8718-784749c3c41b
    internal-label: Salesforce integration
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 6%
---
# Creando un perfil [!DNL Marketo Measure] {#creating-a-marketo-measure-profile}

Obtenga información sobre cómo crear un perfil de [!DNL Marketo Measure]. La creación de un perfil [!DNL Marketo Measure] garantiza que no se produzcan errores de validación al insertar datos en su CRM.

1. Crear un perfil [!DNL Marketo Measure] específico:

   * Asignar el conjunto de permisos de administrador de [!DNL Marketo Measure]
   * Habilitar el permiso para ver y editar posibles clientes convertidos

   >[!NOTE]
   >
   >Este perfil puede ser un clon de un perfil [!DNL System Admin]

1. Se creó un usuario [!DNL Marketo Measure] dedicado:

   * Asignar el nuevo perfil [!DNL Marketo Measure] a ese usuario
   * Habilite &quot;Usuario de marketing&quot; como permiso de nivel de usuario

1. Excluya este perfil de todos los déclencheur, flujos de trabajo y procesos.
1. Inicie sesión en su cuenta de [!DNL Marketo Measure] y vuelva a autorizar la conexión de [!DNL Salesforce] con el nuevo usuario:

   * Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión con las nuevas credenciales de Salesforce de producción de usuario
   * Seleccione &quot;[!UICONTROL Configuración]&quot; en la lista desplegable &quot;[!UICONTROL Mi cuenta]&quot;
   * Seleccione &quot;[!UICONTROL Conexiones]&quot; en la agrupación &quot;[!UICONTROL Integraciones]&quot;
   * Haga clic en el icono de clave a la derecha de la conexión de [!DNL Salesforce] conectada actualmente y seleccione Volver a autorizar con producción. A continuación, vuelva a iniciar sesión con las nuevas credenciales de usuario si se le solicita

   ¡Listo!

   Si tiene alguna pregunta sobre cómo crear un perfil [!DNL Marketo Measure] específico, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
