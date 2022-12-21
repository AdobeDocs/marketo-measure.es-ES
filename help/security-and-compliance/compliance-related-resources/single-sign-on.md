---
unique-page-id: 18874761
description: Inicio de sesión único - [!DNL Marketo Measure] - Documentación del producto
title: Inicio de sesión único
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '1329'
ht-degree: 2%

---

# Inicio de sesión único {#single-sign-on}

SAML (lenguaje de marcado de afirmación de seguridad) para SSO (inicio de sesión único) permite a los usuarios autenticarse a través del proveedor de identidad de una empresa cuando inician sesión en el [!DNL Marketo Measure] aplicación. SSO permite que un usuario se autentique una sola vez, sin necesidad de autenticar aplicaciones independientes. SAML es una necesidad para los clientes empresariales, ya que no todos los usuarios tendrán un [!DNL Salesforce] o [!DNL Google] dentro de su organización. Para escalar, [!DNL Marketo Measure] ha desarrollado una solución SAML que puede ser compatible con los proveedores de identidad de la empresa.

>[!CAUTION]
>
>Este artículo describe el inicio de sesión único (SSO) y la administración avanzada de usuarios de CRM. Si su cuenta se aprovisionó **después del 10/9/2020**, no tenga en cuenta este artículo, ya que SSO y Identity Management se configurarán dentro de la función [Adobe Admin Console para su [!DNL Marketo Measure] integración](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>Es probable que las empresas utilicen diferentes proveedores de identidad (por ejemplo, Ping Identity, Okta). Es posible que los términos utilizados en las siguientes instrucciones de configuración y en la interfaz de usuario no coincidan directamente con los utilizados por su proveedor de identidad.

## Requisitos {#requirements}

* Usuario con permisos de AccountAdmin en el [!DNL Marketo Measure] Aplicación
* Usuario con acceso administrativo al proveedor de identidad del cliente

## Introducción {#getting-started}

Para empezar, vaya a Configuración > Seguridad > Autenticación en la página [!DNL Marketo Measure] aplicación. A continuación, cambie el Tipo de inicio de sesión a SSO personalizado para ver las opciones de configuración. Los cambios no surtirán efecto hasta que pruebe la autenticación y haga clic en el botón **[!UICONTROL Guardar]** en la parte inferior de la página.

![](assets/single-sign-on-1.png)

## Procesar {#process}

[!DNL Marketo Measure] El inicio de sesión único requiere la configuración de la autenticación en una serie de pasos que es importante seguir para que no corra el riesgo de quedar bloqueado [!DNL Marketo Measure] cuenta.

Configure el [!DNL Marketo Measure] Aplicación en su proveedor de identidad. Consulte la documentación externa que aparece a continuación para obtener tutoriales.

    a. Cuando se le pida la URL de inicio de sesión único o la URL de destinatario o la URL de destino, utilice la URL del servicio al cliente de aserción SAML (ACS) [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b. Cuando se le pida la URL de restricción de audiencias o el identificador único definido por la aplicación, utilice [https://BizibleLPM](https://biziblelpm/)

Cambie a SSO personalizado en el [!DNL Marketo Measure] Aplicación

    a. Una vez habilitado el grupo de facturación para su cuenta, ahora puede navegar a [!UICONTROL Configuración] >>[!UICONTROL Seguridad] >> [!UICONTROL Autenticación]
    
    b. De forma predeterminada, el tipo de inicio de sesión se establecerá en &quot;Usuarios de CRM&quot;.
    
    c. Cambie el Tipo de inicio de sesión a &quot;SSO personalizado&quot; para comenzar el proceso de configuración.

Complete los ajustes de conexión para la configuración de su proveedor de identidad

    a. Su proveedor de identidad puede proporcionar un documento .xml de metadatos de IdP que extraerá los campos de configuración necesarios. Cargue el contenido del documento .xml o complete los tres campos a continuación con el resultado obtenido durante el proceso de configuración del Proveedor de identidad. **No es necesario completar ambas opciones.**
    
    i. URL de IdP: La dirección URL que [!DNL Marketo Measure] debe apuntar a para autenticar a los usuarios en la variable [!DNL Marketo Measure] aplicación. A veces se denomina &quot;URL de redireccionamiento&quot;.
    ii. Emisor de IdP: Identificador único del proveedor de identidad. A veces se denomina &quot;Clave externa&quot;.
    iii. Certificado IdP: Una clave pública que permita [!DNL Marketo Measure] para verificar y validar la firma de todas las respuestas del proveedor de identidad.

Establezca la caducidad del token para los usuarios en minutos.

    a. [!DNL Marketo Measure] permite un número entero de 1 a 1440 minutos. Una vez que se haya superado el tiempo de sesión de un usuario, se cerrará la sesión del usuario una vez que navegue a una nueva página.

Configure y asigne la configuración de atributo de usuario al nombre, los apellidos y la dirección de correo electrónico correspondientes.

    a. Al introducir los atributos SAML, [!DNL Marketo Measure] podrá reconocer a sus usuarios por la información que pasan.
    
    i. Atributo de correo electrónico: Proporcione el nombre de atributo que su proveedor de identidad utiliza para la dirección de correo electrónico del usuario.
    ii. Atributo de nombre: Proporcione el nombre de atributo que su proveedor de identidad utiliza para el nombre del usuario.
    iii. Atributo de apellido: Proporcione el nombre de atributo que su proveedor de identidad usa para el apellido del usuario.
    
    b. Sugerencia: Si ahora prueba la configuración de SAML, analizaremos los atributos Correo electrónico, Nombre y Apellido que puede utilizar para esta sección.

![](assets/single-sign-on-2.png)

Configure y asigne la configuración de la función de usuario a las funciones o grupos respectivos clasificados desde su IdP.

    a. Los clientes tienen la opción de asignar [!DNL Marketo Measure] funciones de usuario basadas en grupos definidos en su proveedor de identidad. Al introducir sus atributos SAML, [!DNL Marketo Measure] podrán asignar las funciones y los grupos del usuario a [!DNL Marketo Measure] permisos de usuario. Le recomendamos encarecidamente que configure estas funciones para que su [!DNL Marketo Measure] El administrador tiene derechos suficientes para actualizar su cuenta.
    
    b. Si no se asignan roles ni grupos, la configuración predeterminada es que todos los empleados del proveedor de identidad tendrán acceso de usuario estándar.
    
    i. [!DNL Marketo Measure] Usuario estándar: Proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso de solo lectura al [!DNL Marketo Measure] aplicación.
    ii. [!DNL Marketo Measure] Usuario administrador de cuentas: Proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso administrativo al [!DNL Marketo Measure] aplicación. Esto significa que la función tiene acceso para cambiar configuraciones y configuraciones relacionadas con su cuenta.
    iii. Debe tener un atributo en su IdP con el nombre exacto de &quot;grupos&quot; que contenga los valores que ha introducido en los atributos &quot;Usuario estándar Bizible&quot; o &quot;Usuario administrador de cuenta Bizible&quot;.
    
    c. Si se deben asignar múltiples roles o grupos a una función, introduzca cada valor separado por una coma.

![](assets/single-sign-on-3.png)

Probar la configuración del inicio de sesión único

    a. Antes de pulsar Guardar, deberá hacer clic en el botón [!UICONTROL Probar la autenticación SAML] para comprobar que la configuración se ha configurado correctamente.
    
    b. Si ve un error de &quot;error&quot;, siga el mensaje y vuelva a intentarlo.

![](assets/single-sign-on-4.png)

Guarde la configuración y dirija a sus compañeros para que la utilicen [!UICONTROL Inicio de sesión único] con la nueva dirección URL de inicio de sesión personalizada.

    a. Importante: Una vez que guarde la nueva configuración de autenticación, es posible que la sesión termine cuando navegue a una nueva página porque ha deshabilitado el inicio de sesión por parte de los usuarios de CRM y ha habilitado el inicio de sesión único personalizado.

![](assets/single-sign-on-5.png)

¡Pruébelo!

    a. Use su nueva URL de inicio de sesión personalizada e intente iniciar sesión de nuevo en [!DNL Marketo Measure] Aplicación con credenciales de proveedor de identidad.
    
    b. El formato será como `https://apps.adobe.com/business/[accountName]`
    
    c. ¡Felicitaciones! Ha configurado correctamente el inicio de sesión único en la [!DNL Marketo Measure] ¡Solicite su cuenta!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>Después de configurar SSO, ya no tendrá que agregar usuarios dentro de [!DNL Marketo Measure] aplicación. El aprovisionamiento de usuarios debe gestionarse directamente dentro de su proveedor de identidad.

## Usuarios de CRM (Configuración avanzada) {#crm-users-advanced-setup}

De forma predeterminada, todas las cuentas pueden acceder al [!DNL Marketo Measure] con sus credenciales de CRM. A veces, los propietarios de cuentas deben limitar el acceso a ciertas funciones y no abrirlo a todos los usuarios con una licencia de CRM activa. La configuración avanzada le permitirá asignar sus roles y grupos de CRM a [!DNL Marketo Measure] permisos de usuario.

Si no hay roles ni grupos asignados, la configuración predeterminada es que todas las licencias activas en su CRM tendrán acceso de usuario estándar.

* [!DNL Marketo Measure] Usuario estándar: Proporcione el valor de rol o grupo a los usuarios que deben tener acceso de solo lectura al [!DNL Marketo Measure] aplicación.
* [!DNL Marketo Measure] Usuario administrador de cuentas: Proporcione el valor de rol o grupo a los usuarios que deben tener acceso administrativo al [!DNL Marketo Measure] aplicación. Esto significa que la función tiene acceso para cambiar configuraciones y configuraciones relacionadas con su cuenta.

Si se deben asignar múltiples roles o grupos a una función, introduzca cada valor separado por una coma.

**Funciones de Salesforce**

Para [!DNL Salesforce] Roles, utilice el nombre de cada Función. Todas las funciones se encuentran en la sección [!UICONTROL Configuración] >[!UICONTROL Administrar usuarios] >[!UICONTROL Funciones] para abrir el Navegador.

![](assets/6.png)

**Funciones de Dynamics**

Para [!DNL Dynamics] Roles, utilice el nombre de cada Función de seguridad. Todas las funciones de seguridad se encuentran en la sección [!UICONTROL Configuración] >[!UICONTROL Seguridad] >[!UICONTROL Funciones de seguridad] para abrir el Navegador.

![](assets/7.png)

![](assets/8.png)

**Usuarios de Google**

Una vez configurado el SSO personalizado, la variable [!UICONTROL Usuarios] se actualizará para mostrar solo los usuarios externos que se hayan agregado con los inicios de sesión de Google. Dado que todos los usuarios con acceso a se definen mediante la configuración de SSO, aquí se enumeran los usuarios externos adicionales.

![](assets/9.png)

Solo válido [!DNL Google] las cuentas se pueden agregar y deben tener una función de usuario definida.

## Vínculos externos {#external-links}

* [Okta](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Identidad de ping](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
