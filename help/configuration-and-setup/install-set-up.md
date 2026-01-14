---
description: Instalación y configuración del paquete Salesforce - [!DNL Marketo Measure]
title: Instalación y configuración del paquete [!DNL Salesforce]
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 92%

---

# Instalación de paquetes de Salesforce{#marketo-measure-salesforce-package-installation}

Antes de instalar el paquete base de [!DNL Marketo Measure] [!DNL Salesforce], debe determinar si lo va a instalar primero en una zona protegida de [!DNL Salesforce] antes de pasar a la instancia de producción de Salesforce.

>[!NOTE]
>
>Una vez que su cuenta de [!DNL Marketo Measure] esté conectada a una instancia de producción de [!DNL Salesforce], no podrá retroceder y conectarse a una zona protegida. Además, una cuenta de [!DNL Marketo Measure] solo puede conectarse a una instancia de producción de [!DNL Salesforce].

El paquete base de [!DNL Marketo Measure] contiene:

* 7 objetos personalizados de [!DNL Marketo Measure]
* Campos personalizados de [!DNL Marketo Measure]
* 25 informes de [!DNL Stock]

[!DNL Marketo Measure] es capaz de leer objetos, campos y registros estándar de [!DNL Salesforce]; sin embargo, [!DNL Marketo Measure] nunca actualizará ni insertará datos en ellos. Todos los datos recopilados por el JavaScript de [!DNL Marketo Measure] se mostrarán en los objetos y campos personalizados de [!DNL Marketo Measure].

Siga los pasos a continuación para instalar el paquete base de [!DNL Marketo Measure Salesforce].

1. Con un navegador de incógnito, ve a [Salesforce AppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} e inicia sesión.

1. Instale el paquete de [!DNL Marketo Measure] en zona protegida o en producción.

1. Inicie sesión en [!DNL Salesforce] como administrador.

1. Seleccione **[!UICONTROL Instalar] para todos los usuarios**.

   ![1. Seleccione Instalar para todos los usuarios.](assets/bizible-full-1.png)

1. Una vez finalizada la instalación, podrá verla.

   ![1. Una vez completada la instalación, puede verlo.](assets/bizible-taxonomy-1.png)

Una vez finalizada la instalación, podrá actualizar sus [[!DNL Salesforce] diseños de página](/help/configuration-and-setup/page-layout-instructions.md){target="_blank"} con los campos de [!DNL Marketo Measure] si lo desea.

>[!NOTE]
>
>Obtenga información sobre los conjuntos de permisos creados de [!DNL Marketo Measure] y [cómo se utilizan](/help/configuration-and-setup/marketo-measure-permission-sets.md){target="_blank"}.

## Creación de un perfil y un usuario de [!DNL Marketo Measure] {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] envía y recibe datos a través de un usuario conectado de [!DNL Salesforce] dentro de la aplicación [!DNL Marketo Measure].

Para insertar datos de Touchpoint en su instancia de [!DNL Salesforce], el usuario conectado debe tener acceso a los objetos personalizados de [!DNL Marketo Measure] (p. ej., Buyer Touchpoint y Buyer Attribution Touchpoint), así como a objetos de [!DNL Salesforce] estándar como posibles clientes y contactos.

Cree un perfil de [!DNL Marketo Measure] para garantizar que no se producirá ningún error de validación al enviar datos a Salesforce.

Paso 1: cree un perfil de [!DNL Marketo Measure] específico

1. Asigne los siguientes permisos:

* “[!DNL Marketo Measure] Conjunto de permisos de administrador”
   * El conjunto de permisos administrados permite a un administrador de SFDC crear, leer, escribir y eliminar registros de objetos de [!DNL Marketo Measure].
* “Ver y editar conjunto de permisos de posibles clientes convertidos”
   * Esto permite a [!DNL Marketo Measure] decorar posibles clientes después de convertirlos en contactos. Si este conjunto de permisos no está habilitado, puede haber brechas significativas en el seguimiento de datos.

>[!NOTE]
>
>Este perfil puede ser un clon de un perfil de administrador del sistema.

Paso 2: cree un usuario de [!DNL Marketo Measure] específico para que pueda realizar un seguimiento del impacto de [!DNL Marketo Measure] en su instancia de [!DNL Salesforce]

1. Asigne el nuevo perfil de [!DNL Marketo Measure] a ese usuario.

1. Habilite “Usuario de marketing” como permiso a nivel de usuario.

* La casilla de verificación [!UICONTROL Usuario de marketing] permite al usuario crear campañas y utilizar el asistente para importación de campañas. Si no se selecciona esta opción, el usuario solo puede ver las campañas y la configuración avanzada de la campaña, editar el historial de campañas para un único posible cliente o contacto y ejecutar informes de campaña. [!DNL Marketo Measure] necesita poder leer y escribir en el objeto de campaña.

Paso 3: Excluya este perfil de todos los activadores, flujos de trabajo y procesos

Paso 4: inicie sesión en su cuenta de [!DNL Marketo Measure] y vuelva a autorizar la conexión de [!DNL Salesforce] con el nuevo usuario

1. Vaya a apps.bizible.com e inicie sesión con las nuevas credenciales de [!DNL Salesforce] de producción de usuario.

1. Seleccione **[!UICONTROL Configuración]** en el menú desplegable **[!UICONTROL Mi cuenta]**.

1. Seleccione **[!UICONTROL Conexiones]** en la agrupación **[!UICONTROL Integraciones]**.

1. Haga clic en el icono de clave a la derecha de la conexión actual de [!DNL Salesforce] y seleccione **Volver a autorizar con producción**. Inicie sesión otra vez con las nuevas credenciales de usuario (si se le solicita).

>[!MORELIKETHIS]
>
>* [Información general sobre permisos de integración](/help/api-connections/integration-permissions-overview.md){target="_blank"}
>
>* [Configuración de Adobe Admin Console](/help/configuration-and-setup/adobe-admin-console-setup.md){target="_blank"}
