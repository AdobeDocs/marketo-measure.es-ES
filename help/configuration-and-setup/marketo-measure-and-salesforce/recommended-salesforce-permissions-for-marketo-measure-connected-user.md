---
unique-page-id: 18874696
description: Recomendado [!DNL Salesforce] Permisos para [!DNL Marketo Measure] Usuario conectado - [!DNL Marketo Measure] - Documentación del producto
title: Recomendado [!DNL Salesforce] Permisos para [!DNL Marketo Measure] Usuario conectado
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Recomendado [!DNL Salesforce] Permisos para [!DNL Marketo Measure] Usuario conectado {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] envía y recibe datos a través de una [!DNL Salesforce] dentro del [!DNL Marketo Measure] aplicación.

Para insertar datos de puntos de contacto en el [!DNL Salesforce] , el usuario conectado debe tener acceso a [!DNL Marketo Measure] objetos personalizados (p. ej., Touchpoint de Comprador y Touchpoint de Atribución de Comprador), así como [!DNL Salesforce] objetos como posibles clientes y contactos (consulte [[!DNL Marketo Measure] en Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Las licencias de usuario administrador pueden servir como usuario conectado, ya que a menudo tienen los privilegios de datos necesarios de forma predeterminada. Sin embargo, es posible que su equipo prefiera utilizar un usuario de integraciones o una [!DNL Salesforce] licencia de usuario para realizar un seguimiento del impacto de [!DNL Marketo Measure] en su instancia.

Recomendamos los siguientes permisos para garantizar que [!DNL Marketo Measure] los datos fluyen con precisión:

* [!DNL Marketo Measure] Conjunto De Permisos De Administrador Para Usuario Dedicado

El conjunto de permisos administrados permite a un administrador de SFDC crear, leer, escribir y eliminar registros de [!DNL Marketo Measure] objetos.

* Ver y editar conjunto de permisos de posibles clientes convertidos

Esto permite que [!DNL Marketo Measure] para decorar posibles clientes después de convertirlos en contactos. Si este conjunto de permisos no está habilitado, puede haber lagunas de seguimiento de datos significativas. Puede encontrar más información en [[!DNL Salesforce Trailblazer] comunidad](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] Casilla de verificación de usuario de marketing

La variable [!UICONTROL Usuario de marketing] permite al usuario crear campañas y utilizar el Asistente para importación de campañas. Si no se selecciona esta opción, el usuario solo puede ver las campañas y la configuración avanzada de la campaña, editar el historial de campañas para un único posible cliente o contacto y ejecutar informes de campaña. [!DNL Marketo Measure] necesita poder leer y escribir en el objeto de campaña.

**Resolución de problemas adicionales**

If [!DNL Marketo Measure] sigue experimentando problemas al leer o escribir datos, puede resultar útil investigar lo siguiente:

* Acceso a [!DNL Salesforce] Colas

Si el usuario dedicado no tiene acceso a posibles clientes en colas, no puede modificar los posibles clientes con [!DNL Marketo Measure] datos. Esto se puede lograr teniendo una función en la jerarquía que permita el acceso a las colas o otorgando acceso a los usuarios de forma individual.

* Seguridad y accesibilidad en el nivel de campo

La seguridad a nivel de campo y la accesibilidad de los campos están relacionadas, pero tienen algunas diferencias clave. Seguridad de nivel de campo define la visibilidad de campo para un perfil determinado, mientras que Accesibilidad de campo determina si un campo es editable en función de la seguridad de nivel de campo y la configuración de la presentación de página. Al usar la variable [!DNL Marketo Measure] conjuntos de permisos del paquete recibirá la configuración de seguridad necesaria para los objetos de campo. En algunos casos, para tener la accesibilidad del campo correcta, el usuario conectado deberá tener la variable [!DNL Marketo Measure] en los diseños de página. [!DNL Marketo Measure] los campos de la presentación permiten el [!DNL Marketo Measure] datos a asignar [!DNL Salesforce]. Esto dependerá de su [!DNL Salesforce] entorno.

Todas las organizaciones [!DNL Salesforce] tiene necesidades individuales, pero le proporcionamos nuestros requisitos para equilibrar el [!DNL Marketo Measure] acceda a las necesidades con sus protocolos de seguridad. No dude en ponerse en contacto con [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
