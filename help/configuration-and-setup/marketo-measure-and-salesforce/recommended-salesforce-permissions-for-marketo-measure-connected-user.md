---
unique-page-id: 18874696
description: ' [!DNL Salesforce] Permisos recomendados para [!DNL Marketo Measure] usuario conectado - [!DNL Marketo Measure]'
title: 'Permisos de  [!DNL Salesforce]  recomendados para un usuario conectado de  [!DNL Marketo Measure] '
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 23%

---

# Permisos recomendados de [!DNL Salesforce] para [!DNL Marketo Measure] usuario conectado {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] envía y recibe datos a través de un usuario conectado de [!DNL Salesforce] dentro de la aplicación [!DNL Marketo Measure].

Para insertar datos de punto de contacto en la instancia [!DNL Salesforce], el usuario conectado debe tener acceso a [!DNL Marketo Measure] objetos personalizados (es decir, Buyer Touchpoint y Buyer Attribution Touchpoint), así como a objetos estándar [!DNL Salesforce] como posibles clientes y contactos. Ver [[!DNL Marketo Measure] en Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

Las licencias de usuario de administrador de [!DNL Salesforce] pueden servir como usuario conectado, ya que a menudo tienen los privilegios de datos necesarios de forma predeterminada. Sin embargo, es posible que su equipo prefiera usar un usuario de integración o una licencia de usuario de [!DNL Salesforce] dedicada para rastrear el impacto de [!DNL Marketo Measure] en su instancia.

Recomendamos los siguientes permisos para garantizar que los datos de [!DNL Marketo Measure] fluyen con precisión:

* Conjunto De Permisos De Administrador De [!DNL Marketo Measure] Para Usuario Dedicado

El conjunto de permisos administrados permite a un administrador de SFDC crear, leer, escribir y eliminar registros de objetos de [!DNL Marketo Measure].

* Ver y editar conjunto de permisos de posibles clientes convertidos

Esto permite a [!DNL Marketo Measure] decorar posibles clientes después de convertirlos en contactos. Si este conjunto de permisos no está habilitado, puede haber brechas significativas en el seguimiento de datos. Encontrará más información en [[!DNL Salesforce Trailblazer] la comunidad](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5).

* Casilla de verificación de usuario de marketing [!DNL Salesforce]

La casilla de verificación [!UICONTROL Usuario de marketing] permite al usuario crear campañas y utilizar el asistente para importación de campañas. Si no se selecciona esta opción, el usuario solo puede ver las campañas y la configuración avanzada de la campaña, editar el historial de campañas para un único posible cliente o contacto y ejecutar informes de campaña. [!DNL Marketo Measure] necesita poder leer y escribir en el objeto de campaña.

**Solución de problemas adicional**

Si [!DNL Marketo Measure] sigue teniendo problemas al leer o escribir datos, puede resultar útil investigar lo siguiente:

* Acceso a [!DNL Salesforce] colas

Si el usuario dedicado no tiene acceso a los posibles clientes en las colas, no podrá modificar los posibles clientes con datos de [!DNL Marketo Measure]. Puede hacerlo teniendo un rol en la jerarquía que permita el acceso a las colas o concediendo acceso a los usuarios de forma individual.

* Seguridad y accesibilidad de nivel de campo

La seguridad y la accesibilidad de los campos están relacionadas, pero tienen algunas diferencias clave. La seguridad de nivel de campo define la visibilidad del campo para un perfil determinado, mientras que la accesibilidad del campo determina si un campo es editable en función de la seguridad de nivel de campo y la configuración del diseño de página. Al usar los conjuntos de permisos del paquete [!DNL Marketo Measure], recibirá la configuración de seguridad de objetos de campo necesaria. A veces, para tener la accesibilidad de campo correcta, el usuario conectado necesita tener los campos [!DNL Marketo Measure] en los diseños de página. [!DNL Marketo Measure] campos del diseño permiten que los datos de [!DNL Marketo Measure] se asignen a [!DNL Salesforce]. Esto depende de su entorno [!DNL Salesforce] en particular.

[!DNL Salesforce] de cada organización tiene necesidades individuales, pero le proporcionamos nuestros requisitos para equilibrar las necesidades de acceso de [!DNL Marketo Measure] con sus protocolos de seguridad. No dude en ponerse en contacto con [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
