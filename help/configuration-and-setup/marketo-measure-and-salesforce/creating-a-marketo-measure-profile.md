---
description: Creando un  [!DNL Marketo Measure] perfil - [!DNL Marketo Measure]
title: 'Creación de un perfil de  [!DNL Marketo Measure] '
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 3%

---


# Creando un perfil [!DNL Marketo Measure] {#creating-a-marketo-measure-profile}

Obtenga información sobre cómo crear un perfil de [!DNL Marketo Measure]. La creación de un perfil [!DNL Marketo Measure] garantiza que no se produzcan errores de validación al insertar datos en su CRM.

1. Crear un perfil [!DNL Marketo Measure] específico:

   * Asignar el conjunto de permisos de administrador de [!DNL Marketo Measure]
   * Habilitar el permiso para ver y editar posibles clientes convertidos

   >[!NOTE]
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
