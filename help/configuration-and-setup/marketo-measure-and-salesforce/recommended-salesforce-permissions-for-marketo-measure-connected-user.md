---
unique-page-id: 18874696
description: Recomendado [!DNL Salesforce] Permisos para [!DNL Marketo Measure] Usuario conectado - [!DNL Marketo Measure] - Documentación del producto
title: Permisos de  [!DNL Salesforce]  recomendados para un usuario conectado de  [!DNL Marketo Measure]
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 26%

---

# Permisos de [!DNL Salesforce] recomendados para un usuario conectado de [!DNL Marketo Measure] {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] envía y recibe datos a través de un usuario conectado de [!DNL Salesforce] dentro de la aplicación [!DNL Marketo Measure].

Para insertar los datos de punto de contacto en su [!DNL Salesforce] Por ejemplo, el usuario conectado debe tener acceso a [!DNL Marketo Measure] objetos personalizados (es decir, Buyer Touchpoint y Buyer Attribution Touchpoint), así como [!DNL Salesforce] como posibles clientes y contactos (consulte [[!DNL Marketo Measure] en Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Las licencias de usuario de administrador pueden servir como el usuario conectado, ya que a menudo tienen los privilegios de datos necesarios de forma predeterminada. Sin embargo, es posible que su equipo prefiera utilizar un usuario de integraciones o un dedicado [!DNL Salesforce] licencia de usuario para realizar un seguimiento del impacto de [!DNL Marketo Measure] en su instancia.

Recomendamos los siguientes permisos para garantizar que [!DNL Marketo Measure] Los datos fluyen con precisión:

* [!DNL Marketo Measure] Conjunto De Permisos Del Administrador Para Usuario Dedicado

El conjunto de permisos administrados permite a un administrador de SFDC crear, leer, escribir y eliminar registros de objetos de [!DNL Marketo Measure].

* Ver y editar conjunto de permisos de posibles clientes convertidos

Esto permite a [!DNL Marketo Measure] decorar posibles clientes después de convertirlos en contactos. Si este conjunto de permisos no está habilitado, puede haber brechas significativas en el seguimiento de datos. Puede encontrar más información en [[!DNL Salesforce Trailblazer] comunidad](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] Casilla de verificación de usuario de marketing

La casilla de verificación [!UICONTROL Usuario de marketing] permite al usuario crear campañas y utilizar el asistente para importación de campañas. Si no se selecciona esta opción, el usuario solo podrá ver las campañas y la configuración avanzada de la campaña, editar el historial de campañas para un único posible cliente o contacto y ejecutar informes de campaña. [!DNL Marketo Measure] necesita poder leer y escribir en el objeto de campaña.

**Solución de problemas adicional**

If [!DNL Marketo Measure] sigue teniendo problemas al leer o escribir datos. puede resultar útil investigar lo siguiente:

* Acceso a [!DNL Salesforce] Colas

Si el usuario dedicado no tiene acceso a los posibles clientes en las colas, no puede modificar los posibles clientes con [!DNL Marketo Measure] datos. Puede hacerlo teniendo un rol en la jerarquía que permita el acceso a las colas o concediendo acceso a los usuarios de forma individual.

* Seguridad y accesibilidad de nivel de campo

La seguridad y la accesibilidad de los campos están relacionadas, pero tienen algunas diferencias clave. La seguridad de nivel de campo define la visibilidad del campo para un perfil determinado, mientras que la accesibilidad del campo determina si un campo es editable en función de la seguridad de nivel de campo y la configuración del diseño de página. Uso del [!DNL Marketo Measure] conjuntos de permisos del paquete recibirá la configuración de seguridad de objeto de campo necesaria. En algunos casos, para tener la accesibilidad de campo correcta, el usuario conectado deberá tener la variable [!DNL Marketo Measure] campos en los diseños de página. [!DNL Marketo Measure] Los campos del diseño permiten el [!DNL Marketo Measure] datos para asignar a [!DNL Salesforce]. Esto dependerá de su [!DNL Salesforce] entorno.

El de cada organización [!DNL Salesforce] tiene necesidades individuales, pero le proporcionamos nuestros requisitos para equilibrar las [!DNL Marketo Measure] acceso necesario con los protocolos de seguridad. No dude en ponerse en contacto con [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
