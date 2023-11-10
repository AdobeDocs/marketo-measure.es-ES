---
description: 'Configuración de Adobe Admin Console, Marketo Measure: Documentación del producto'
title: Configuración de Adobe Admin Console
feature: Installation
source-git-commit: 68eb5bf83d589c9161490b1772551ed46a9ce444
workflow-type: ht
source-wordcount: '405'
ht-degree: 100%

---

# Configuración de Adobe Admin Console {#adobe-admin-console-setup}

El primer paso para utilizar [!DNL Marketo Measure] es crear su Adobe Admin Console aprovisionado e iniciar sesión. Si aún no ha recibido el correo electrónico con las instrucciones de inicio de sesión, póngase en contacto con el representante de cuentas de [!DNL Marketo Measure].

## Configuración de Adobe Admin Console y el proveedor de identidad {#set-up-your-adobe-admin-console-and-identity-provider}

Como producto que forma parte de Adobe Suite, [!DNL Marketo Measure] aprovecha todas las funciones de Adobe Admin Console para Identity Management. Puede obtener más información [aquí](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

Recomendamos revisar todos los recursos, las prácticas recomendadas y las opciones disponibles para usted en [Identity Management](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).

Para obtener instrucciones sobre la configuración de Identity Management en Adobe Admin Console, póngase en contacto con el representante de cuentas de [!DNL Marketo Measure].

Para facilitar la autenticación y autorización de los usuarios con sus instancias de [!DNL Marketo Measure], se requieren los siguientes pasos en Adobe Admin Console:

**Configuración de la tarjeta de producto de [!DNL Marketo Measure]**

Al acceder a Adobe Admin Console, verá sus instancias de producto de [!DNL Marketo Measure] presentes en la sección Información general.

![](assets/adobe-admin-console-setup-1.png)

Si hace clic en la tarjeta de producto de [!DNL Marketo Measure], podrá ver todas sus instancias de [!DNL Marketo Measure]. De forma predeterminada, cada instancia de [!DNL Marketo Measure] tiene su propio perfil con el prefijo “[!DNL Marketo Measure]”. Todos los administradores o usuarios añadidos a este u otro perfil dentro de esta instancia podrán iniciar sesión en [!DNL Marketo Measure].

![](assets/adobe-admin-console-setup-2.png)

No se requiere ninguna acción para crear un nuevo perfil en las instancias de producto de [!DNL Marketo Measure].

Para empezar a agregar usuarios que puedan acceder a [!DNL Marketo Measure], consulte la sección [Agregar administradores de  [!DNL Marketo Measure]  y usuarios de  [!DNL Marketo Measure] ](#adding-marketo-measure-admins-and-marketo-measure-users) a continuación.

## Agregar administradores de [!DNL Marketo Measure] y usuarios de [!DNL Marketo Measure] {#adding-marketo-measure-admins-and-marketo-measure-users}

El siguiente paso es conceder acceso a la aplicación de [!DNL Marketo Measure] añadiendo usuarios. Esto se puede hacer en el directorio de administradores y usuarios de la tarjeta de producto de [!DNL Marketo Measure].

| Tipo de usuario | Descripción |
|---|---|
| Administradores | son administradores y usuarios avanzados de la aplicación de [!DNL Marketo Measure] con capacidad total para actualizar y gestionar opciones de configuración específicas de [!DNL Marketo Measure] |
| Usuarios | son usuarios estándar de la aplicación de [!DNL Marketo Measure] con permisos de solo lectura dentro de la aplicación de [!DNL Marketo Measure] |

Al añadir un usuario a su grupo respectivo, verá su [tipo de identidad en la lista](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>Para poder ser un administrador de [!DNL Marketo Measure] (en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), se debe agregar un usuario como Usuario _y_ Administrador a cualquier perfil de producto de [!DNL Marketo Measure] en la tarjeta de producto de [!DNL Marketo Measure].

**Iniciar sesión en [!DNL Marketo Measure]**

Una vez que se añade un usuario a un perfil de producto, puede acceder a sus instancias de [!DNL Marketo Measure] seleccionando la opción **Iniciar sesión con Adobe ID** en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/adobe-admin-console-setup-3.png)

