---
description: Inicio de sesión único,  [!DNL Marketo Measure]
title: Inicio de sesión único
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 93%

---


# Inicio de sesión único {#single-sign-on}

El lenguaje de marcado para confirmaciones de seguridad (SAML) para el inicio de sesión único (SSO) permite autenticarse a través del proveedor de identidad de una compañía cuando se inicia sesión en la aplicación de [!DNL Marketo Measure]. SSO permite a un usuario autenticarse una vez, sin necesidad de autenticar aplicaciones independientes.  SAML es una necesidad para los clientes empresariales, ya que no todos los usuarios tienen una cuenta de [!DNL Salesforce] o [!DNL Google] en su organización. Para escalar, [!DNL Marketo Measure] ha desarrollado una solución SAML compatible con los proveedores de identidad de la empresa.

>[!NOTE]
>Es probable que las empresas utilicen diferentes proveedores de identidad (por ejemplo, Ping Identity, Okta). Es posible que los términos utilizados en las siguientes instrucciones de configuración y en la IU no coincidan directamente con los utilizados por su proveedor de identidad.

## Requisitos {#requirements}

* Usuario con permisos de administrador de cuentas en la aplicación de [!DNL Marketo Measure]
* Usuario con acceso administrativo al proveedor de identidad del cliente

## Introducción {#getting-started}

Para empezar, vaya a la página Configuración > Seguridad > Autenticación en la aplicación de [!DNL Marketo Measure]. A continuación, cambie el tipo de inicio de sesión a SSO personalizado para ver las opciones de configuración.  Los cambios no surtirán efecto hasta que pruebe la autenticación y haga clic en el botón **[!UICONTROL Guardar]** en la parte inferior de la página.

![Página de configuración de autenticación con la opción de tipo de inicio de sesión SSO personalizado](assets/single-sign-on-1.png)

## Procesar {#process}

El inicio de sesión único de [!DNL Marketo Measure] requiere configurar la configuración de la autenticación en una serie de pasos para que no se arriesgue a que le bloqueen la cuenta de [!DNL Marketo Measure].

Configure la aplicación de [!DNL Marketo Measure] en su proveedor de identidad. Consulte la documentación externa que se muestra a continuación para ver tutoriales.

    a. Cuando se le solicite la URL de inicio de sesión único, la URL del destinatario, la URL de destino o la URL del servicio de atención al cliente de confirmación de SAML (ACS), utilice [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest] (https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b. Cuando se le pida la URL de restricción de público o el identificador único definido por la aplicación, utilice [https://BizibleLPM](https://biziblelpm/)

Cambie a SSO personalizado en la aplicación de [!DNL Marketo Measure]

    a. Una vez que el grupo de facturación se haya habilitado para su cuenta, puede navegar a [!UICONTROL Configuración] >>[!UICONTROL Seguridad] >> [!UICONTROL Autenticación]
    
    b. De forma predeterminada, el tipo de inicio de sesión se establecerá en “Usuarios de CRM”.
    
    c. Cambie el tipo de inicio de sesión a “SSO personalizado” para iniciar el proceso de configuración.

Rellene la configuración de conexión de la configuración del proveedor de identidad

    a. El proveedor de identidad puede proporcionar un documento .xml de metadatos de IdP que extraerá los campos de configuración requeridos.  Cargue el contenido del documento .xml o complete los tres campos a continuación con el resultado obtenido durante el proceso de configuración del proveedor de identidad. **&#x200B; No es necesario completar ambas operaciones.** 
    
    i. URL de IdP: la URL a la que  [!DNL Marketo Measure]  debe apuntar para autenticar a los usuarios en la aplicación de  [!DNL Marketo Measure] .  A veces se denomina “URL de redireccionamiento”.
    ii. Emisor de IdP: identificador único del proveedor de identidad.  A veces se denomina “Clave externa”.
    iii. Certificado IdP: una clave pública que permite a  [!DNL Marketo Measure]  comprobar y validar la firma de todas las respuestas del proveedor de identidad.

Establezca la caducidad del token para los usuarios en minutos.

    a. [!DNL Marketo Measure]  permite introducir un número entero entre 1 y 1440 minutos.  Una vez que se haya superado el tiempo de sesión del usuario, se cerrará su sesión una vez que navegue a una nueva página.

Configure y asigne la configuración de atributos del usuario a los campos Nombre, Apellidos y Dirección de correo electrónico correspondientes.

    a. Al introducir los atributos de SAML,  [!DNL Marketo Measure]  podrá reconocer a sus usuarios por la información facilitada.
    
    i. Atributo de correo electrónico: proporcione el nombre de atributo que el proveedor de identidad utiliza para la dirección de correo electrónico del usuario.
    ii.  Atributo de nombre: proporcione el nombre de atributo que el proveedor de identidad utiliza para el nombre del usuario.
    iii.  Atributo de apellido: proporcione el nombre de atributo que el proveedor de identidad utiliza para el apellido del usuario.
    
    b. Sugerencia: Si prueba la configuración de SAML ahora, se analizan los atributos de correo electrónico, nombre y apellidos que puede utilizar para esta sección.

![Formulario de configuración de SAML con campos de asignación de atributos de usuario](assets/single-sign-on-2.png)

Configure y asigne la configuración de la función de usuario a las funciones o grupos respectivos clasificados de su IdP.

    a. Los clientes tienen la opción de asignar [!DNL Marketo Measure]  funciones de usuario basadas en grupos definidos en su proveedor de identidad. Al introducir sus atributos de SAML, [!DNL Marketo Measure]  podrá asignar los roles y grupos de su usuario a los permisos de usuario de  [!DNL Marketo Measure] . Se recomienda que configure estas funciones para que el administrador de  [!DNL Marketo Measure]  tenga derechos suficientes para actualizar su cuenta.
    
    b. Si no se asignan roles ni grupos, la configuración predeterminada es que todos los empleados del proveedor de identidad tengan acceso de usuario estándar.
    
    i. Usuario estándar de  [!DNL Marketo Measure] : proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso de solo lectura a la aplicación de  [!DNL Marketo Measure] .
    ii.Usuario administrador de cuenta de  [!DNL Marketo Measure] : proporcione el valor de rol o grupo (de su proveedor de SSO) para los usuarios que deben tener acceso administrativo a la aplicación de  [!DNL Marketo Measure] . Esto significa que la función tiene acceso para cambiar las configuraciones y los ajustes relacionados con su cuenta.
    iii. Debe tener un atributo en su IdP con el nombre exacto de “grupos” que contenga los valores introducidos en los atributos “Usuario estándar de Bizible” o “Usuario administrador de cuentas de Bizible”.
    
    c. Si se deben asignar varios roles o grupos a un rol, introduzca cada valor separado por una coma.

![Configuración de asignación de funciones de usuario con opciones de usuario y administrador estándar](assets/single-sign-on-3.png)

Prueba de la configuración de inicio de sesión único

    a. Antes de poder pulsar Guardar, deberá hacer clic en el botón [!UICONTROL Probar autenticación SAML] para comprobar que la configuración sea correcta.
    
    b. Si ve un error de “failure”, siga el mensaje e inténtelo de nuevo.

![Botón Probar autenticación SAML y mensaje de estado de validación](assets/single-sign-on-4.png)

Guarde la configuración e indique a sus compañeros que utilicen [!UICONTROL Inicio de sesión único] con la nueva URL de inicio de sesión personalizado.

    a. Importante: Una vez que guarde la nueva configuración de autenticación, es posible que la sesión termine una vez que navegue a una página nueva porque ha deshabilitado el inicio de sesión de los usuarios de CRM y ha habilitado el SSO personalizado.

![Botón Guardar para la configuración de autenticación y el mensaje de confirmación](assets/single-sign-on-5.png)

Pruébelo.

    a. Utilice la nueva URL de inicio de sesión personalizada e intente volver a iniciar sesión en la aplicación de  [!DNL Marketo Measure]  con las credenciales del proveedor de identidad.
    
    b. El formato será similar a https://apps.adobe.com/business/[accountName]
    
    c. ¡Felicitaciones! Ha configurado correctamente el inicio de sesión único en la Solicitud de su cuenta de  [!DNL Marketo Measure] .

![Pantalla de confirmación de inicio de sesión SSO correcta](assets/single-sign-on-6.png)

>[!NOTE]
>Después de configurar el SSO, ya no tendrá que agregar usuarios dentro de la aplicación de [!DNL Marketo Measure]. El aprovisionamiento de usuarios debe gestionarse directamente dentro del proveedor de identidad.

## Usuarios de CRM (configuración avanzada) {#crm-users-advanced-setup}

De forma predeterminada, todas las cuentas pueden acceder a la aplicación de [!DNL Marketo Measure] con sus credenciales de CRM. A veces, los propietarios de cuentas deben limitar el acceso a determinadas funciones y no abrirlo a todos los usuarios con una licencia de CRM activa. La configuración avanzada permite asignar sus funciones y grupos de CRM a permisos de usuario de [!DNL Marketo Measure].

Si no se asignan funciones ni grupos, la configuración predeterminada es que todas las licencias activas en su CRM tengan acceso de usuario estándar.

* Usuario estándar de [!DNL Marketo Measure]: proporcione el valor de función o grupo para los usuarios que deben tener acceso de solo lectura a la aplicación de [!DNL Marketo Measure].
* Usuario administrador de cuenta de [!DNL Marketo Measure]: proporcione el valor de función o grupo para los usuarios que deben tener acceso administrativo a la aplicación de [!DNL Marketo Measure]. Esto significa que la función tiene acceso para cambiar las configuraciones y los ajustes relacionados con su cuenta.

Si se deben asignar varias funciones o grupos a una función, introduzca cada valor separado por una coma.

**Funciones de Salesforce**

Para las funciones de [!DNL Salesforce], utilice el nombre de cada función. Todas las funciones se encuentran en el menú [!UICONTROL Configuración] >[!UICONTROL Administrar usuarios] > [!UICONTROL Funciones].

![Menú de configuración de Salesforce que muestra los roles bajo Administrar usuarios](assets/6.png)

**Funciones de Dynamics**

Para las funciones de [!DNL Dynamics], utilice el nombre de cada función de seguridad. Todas las funciones de seguridad se encuentran en el menú [!UICONTROL Configuración] > [!UICONTROL Seguridad] > [!UICONTROL Funciones de seguridad].

![Navegación del menú de configuración de Dynamics a los roles de seguridad](assets/7.png)

![Lista de roles de seguridad de Dynamics que muestra las opciones de rol disponibles](assets/8.png)

**Usuarios de Google**

Una vez configurado el SSO personalizado, la página [!UICONTROL Usuarios] se actualiza para mostrar únicamente los usuarios externos que se han añadido con los inicios de sesión de Google. Dado que todos los usuarios con acceso a se definen mediante la configuración de SSO, aquí se enumeran los usuarios externos adicionales.

![Página de usuarios que muestra usuarios de inicio de sesión de Google externos](assets/9.png)

Solo pueden agregarse cuentas de [!DNL Google] válidas y deben tener una función de usuario definida.

## Vínculos externos {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Identidad del ping](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/es-es/azure/active-directory/active-directory-saas-custom-apps)
