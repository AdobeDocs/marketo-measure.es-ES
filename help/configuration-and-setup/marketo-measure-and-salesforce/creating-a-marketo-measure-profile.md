---
unique-page-id: 18874698
description: Creación de un [!DNL Marketo Measure] Perfil - [!DNL Marketo Measure] - Documentación del producto
title: Creación de un perfil de  [!DNL Marketo Measure]
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 20%

---

# Creación de un perfil de [!DNL Marketo Measure] {#creating-a-marketo-measure-profile}

Obtenga información sobre cómo crear un [!DNL Marketo Measure] perfil. Creación de un [!DNL Marketo Measure] Este perfil garantiza que no se produzcan errores de validación al transferir datos a su CRM.

1. Crear un específico [!DNL Marketo Measure] perfil:

   * Asigne el [!DNL Marketo Measure] Conjunto de permisos de administrador
   * Habilitar el permiso para ver y editar posibles clientes convertidos

   >[!NOTE]
   >
   >Este perfil puede ser un clon de un [!DNL System Admin] perfil

1. Se ha creado un [!DNL Marketo Measure] usuario:

   * Asigne el nuevo perfil de [!DNL Marketo Measure] a ese usuario
   * Habilite “Usuario de marketing” como permiso a nivel de usuario

1. Excluya este perfil de todos los déclencheur, flujos de trabajo y procesos.
1. Inicie sesión en su [!DNL Marketo Measure] Cuenta y volver a autorizar la [!DNL Salesforce] conexión con el nuevo usuario:

   * Ir a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión con las nuevas credenciales de Salesforce de producción de usuario
   * Seleccione &quot;[!UICONTROL Configuración]&quot; dentro de &quot;[!UICONTROL Mi cuenta]&quot; lista desplegable
   * Seleccione &quot;[!UICONTROL Conexiones]&quot; dentro de &quot;[!UICONTROL Integraciones]&quot; agrupación
   * Haga clic en el icono de clave a la derecha de la conexión actual de [!DNL Salesforce] y seleccione Volver a autorizar con producción. A continuación, vuelva a iniciar sesión con las nuevas credenciales de usuario si se le solicita

   Listo!

   Si tiene alguna pregunta acerca de la creación de una [!DNL Marketo Measure] perfil, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
