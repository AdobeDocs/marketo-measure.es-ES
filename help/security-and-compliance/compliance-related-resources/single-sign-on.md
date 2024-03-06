---
unique-page-id: 18874761
description: Inicio de sesión único - [!DNL Marketo Measure]
title: Inicio de sesión único
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---

# Inicio de sesión único {#single-sign-on}

SAML (lenguaje de marcado de aserciones de seguridad) para SSO (inicio de sesión único) permite a los usuarios autenticarse a través del proveedor de identidad de una empresa cuando inician sesión en [!DNL Marketo Measure] aplicación. SSO permite que un usuario se autentique una vez, sin necesidad de autenticar aplicaciones independientes. SAML es una necesidad para los clientes empresariales, ya que no todos los usuarios tienen un [!DNL Salesforce] o [!DNL Google] cuenta dentro de su organización. Para escalar, [!DNL Marketo Measure] ha desarrollado una solución SAML compatible con los proveedores de identidad de la empresa.

>[!CAUTION]
>
>Este artículo describe el inicio de sesión único (SSO) y la administración de usuarios de CRM avanzada. Si su cuenta estaba aprovisionada **después del 10/9/2020**, ignore este artículo, ya que el SSO y Identity Management se configurarán dentro de la [Adobe Admin Console para su [!DNL Marketo Measure] integración](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>Es probable que las empresas utilicen diferentes proveedores de identidad (por ejemplo, Ping Identity, Okta). Es posible que los términos utilizados en las siguientes instrucciones de configuración y en la interfaz de usuario no coincidan directamente con los utilizados por su proveedor de identidad.

## Requisitos {#requirements}

* Usuario con permisos de administrador de cuentas en [!DNL Marketo Measure] Aplicación
* Usuario con acceso administrativo al proveedor de identidad del cliente

## Introducción {#getting-started}

Para empezar, vaya a la página Configuración > Seguridad > Autenticación en [!DNL Marketo Measure] aplicación. A continuación, cambie el Tipo de inicio de sesión a SSO personalizado para ver las opciones de configuración. Los cambios no surtirán efecto hasta que pruebe la autenticación y haga clic en **[!UICONTROL Guardar]** en la parte inferior de la página.

![](assets/single-sign-on-1.png)

## Procesar {#process}

[!DNL Marketo Measure] El inicio de sesión único requiere configurar los ajustes de autenticación en una serie de pasos para que no se arriesgue a quedar bloqueado en su [!DNL Marketo Measure] cuenta.

Configure las variables [!DNL Marketo Measure] Aplicación en su proveedor de identidad. Consulte la documentación externa que se muestra a continuación para ver tutoriales.

    a. Cuando se le solicite la URL de inicio de sesión único, la URL del destinatario o la URL de destino, la URL del servicio de atención al cliente de aserción de SAML (ACS), utilice [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b. Cuando se le pida la URL de restricción de audiencia o el identificador único definido por la aplicación, utilice [https://BizibleLPM](https://biziblelpm/)

Cambie a SSO personalizado en [!DNL Marketo Measure] Aplicación

    a. Una vez que el grupo de facturación se haya habilitado para su cuenta, ahora puede navegar a [!UICONTROL Configuración] >>[!UICONTROL Seguridad] >> [!UICONTROL Autenticación]
    
    b. De forma predeterminada, el tipo de inicio de sesión se establecerá en &quot;Usuarios de CRM&quot;.
    
    c. Cambie el tipo de inicio de sesión a &quot;SSO personalizado&quot; para iniciar el proceso de configuración.

Rellene la configuración de conexión de la configuración del proveedor de identidad

    a. El proveedor de identidad puede proporcionar un documento .xml de metadatos de IdP que extraerá los campos de configuración requeridos. Cargue el contenido del documento .xml o rellene los tres campos siguientes a partir de la salida obtenida durante el proceso de configuración del proveedor de identidad. **No es necesario completar ambas operaciones.**
    
    i. Dirección URL de IdP: La dirección URL que [!DNL Marketo Measure] necesita apuntar a para autenticar a los usuarios en la [!DNL Marketo Measure] aplicación. A veces se denomina &quot;URL de redireccionamiento&quot;.
    ii. Emisor de IdP: Identificador único del proveedor de identidad. A veces se denomina &quot;Clave externa&quot;.
    iii. Certificado IdP: Una clave pública que permite [!DNL Marketo Measure] para comprobar y validar la firma de todas las respuestas del proveedor de identidad.

Establezca la caducidad del token para los usuarios en minutos.

    a. [!DNL Marketo Measure] permite un número entero entre 1 y 1440 minutos. Una vez que se haya superado el tiempo de sesión de un usuario, se cerrará la sesión del usuario una vez que navegue a una nueva página.

Configure y asigne la configuración de atributos del usuario a los campos Nombre, Apellidos y Dirección de correo electrónico correspondientes.

    a. Introduciendo los atributos SAML, [!DNL Marketo Measure] podrá reconocer a sus usuarios por la información que les ha pasado.
    
    i. Atributo de correo electrónico: proporcione el nombre de atributo que el proveedor de identidad utiliza para la dirección de correo electrónico del usuario.
    ii. Atributo de nombre: proporcione el nombre de atributo que el proveedor de identidad utiliza para el nombre del usuario.
    iii. Atributo de apellido: proporcione el nombre de atributo que el proveedor de identidad utiliza para el apellido del usuario.
    
    b. Sugerencia: si prueba la configuración de SAML ahora, analizaremos los atributos de correo electrónico, nombre y apellidos que puede utilizar para esta sección.

![](assets/single-sign-on-2.png)

Configure y asigne la configuración de la función de usuario a las funciones o grupos respectivos clasificados de su IdP.

    a. Los clientes tienen la opción de asignar [!DNL Marketo Measure] funciones de usuario basadas en grupos definidos en su proveedor de identidad. Al introducir sus atributos de SAML, [!DNL Marketo Measure] podrá asignar los roles y grupos de su usuario a [!DNL Marketo Measure] permisos de usuario. Le recomendamos encarecidamente que configure estas funciones para que [!DNL Marketo Measure] el administrador tiene derechos suficientes para actualizar su cuenta.
    
    b. Si no se asignan roles ni grupos, la configuración predeterminada es que todos los empleados del proveedor de identidad tendrán acceso de usuario estándar.
    
    i. [!DNL Marketo Measure] Usuario estándar: proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso de solo lectura al [!DNL Marketo Measure] aplicación.
    ii. [!DNL Marketo Measure] Usuario administrador de cuenta: proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso administrativo al [!DNL Marketo Measure] aplicación. Esto significa que la función tiene acceso para cambiar las configuraciones y los ajustes relacionados con su cuenta.
    iii. Debe tener un atributo en su IdP con el nombre exacto de &quot;grupos&quot; que contenga los valores introducidos en los atributos &quot;Usuario estándar de Bizible&quot; o &quot;Usuario administrador de cuentas de Bizible&quot;.
    
    c. Si se deben asignar varios roles o grupos a un rol, introduzca cada valor separado por una coma.

![](assets/single-sign-on-3.png)

Prueba de la configuración de inicio de sesión único

    a. Antes de poder pulsar Guardar, deberá hacer clic en el botón [!UICONTROL Probar autenticación SAML] para comprobar que la configuración es correcta.
    
    b. Si ve un error de &quot;error&quot;, siga el mensaje e inténtelo de nuevo.

![](assets/single-sign-on-4.png)

Guarde la configuración e indique a sus compañeros que utilicen [!UICONTROL Inicio de sesión único] con la nueva URL de inicio de sesión personalizado.

    a. Importante: Una vez que guarde la nueva configuración de autenticación, es posible que la sesión termine una vez que navegue a una página nueva porque ha deshabilitado el inicio de sesión de los usuarios de CRM y ha habilitado el SSO personalizado.

![](assets/single-sign-on-5.png)

¡Pruébalo!

    a. Utilice la nueva URL de inicio de sesión personalizada e intente volver a iniciar sesión en [!DNL Marketo Measure] Aplicación con credenciales de proveedor de identidad.
    
    b. El formato será similar a https://apps.adobe.com/business/[accountName]
    
    c. ¡Felicitaciones! Ha configurado correctamente el inicio de sesión único en [!DNL Marketo Measure] Solicitud de su cuenta.

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>Después de configurar el SSO, ya no tendrá que agregar usuarios dentro de la variable [!DNL Marketo Measure] aplicación. El aprovisionamiento de usuarios debe gestionarse directamente dentro del proveedor de identidad.

## Usuarios de CRM (configuración avanzada) {#crm-users-advanced-setup}

De forma predeterminada, todas las cuentas pueden acceder a [!DNL Marketo Measure] aplicación con sus credenciales de CRM. A veces, los propietarios de cuentas deben limitar el acceso a determinadas funciones y no abrirlo a todos los usuarios con una licencia de CRM activa. La Configuración avanzada le permite asignar sus roles y grupos de CRM a [!DNL Marketo Measure] permisos de usuario.

Si no se asignan funciones ni grupos, la configuración predeterminada es que todas las licencias activas en su CRM tengan acceso de usuario estándar.

* [!DNL Marketo Measure] Usuario estándar: proporcione el valor de rol o grupo para los usuarios que deben tener acceso de solo lectura al [!DNL Marketo Measure] aplicación.
* [!DNL Marketo Measure] Usuario administrador de cuenta: proporcione el valor de rol o grupo para los usuarios que deben tener acceso administrativo al [!DNL Marketo Measure] aplicación. Esto significa que la función tiene acceso para cambiar las configuraciones y los ajustes relacionados con su cuenta.

Si se deben asignar varios roles o grupos a un rol, introduzca cada valor separado por una coma.

**Funciones de Salesforce**

Para [!DNL Salesforce] Roles, utilice el nombre de cada Rol. Todos los roles se encuentran en [!UICONTROL Configurar] >[!UICONTROL Administrar usuarios] >[!UICONTROL Funciones] menú.

![](assets/6.png)

**Funciones de Dynamics**

Para [!DNL Dynamics] Roles, utilice el nombre de cada Rol de seguridad. Todos los roles de seguridad se encuentran en [!UICONTROL Configuración] >[!UICONTROL Seguridad] >[!UICONTROL Funciones de seguridad] menú.

![](assets/7.png)

![](assets/8.png)

**Usuarios de Google**

Una vez configurado el SSO personalizado, la variable [!UICONTROL Usuarios] Esta página se actualiza para mostrar únicamente los usuarios externos que se han añadido con los inicios de sesión de Google. Dado que todos los usuarios con acceso a se definen mediante la configuración de SSO, aquí se enumeran los usuarios externos adicionales.

![](assets/9.png)

Solo válido [!DNL Google] Las cuentas de se pueden agregar y deben tener una función de usuario definida.

## Vínculos externos {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Identidad de ping](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
