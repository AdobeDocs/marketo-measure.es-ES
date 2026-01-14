---
description: Guías para configurar el acceso a Marketo Measure a través de perfiles de Adobe Admin Console e iniciar sesión
title: Configuración de Adobe Admin Console
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 75%

---

# Configuración de Adobe Admin Console {#adobe-admin-console-setup}

El primer paso para utilizar [!DNL Marketo Measure] es crear su Adobe Admin Console aprovisionada e iniciar sesión. Si no ha recibido el correo electrónico con las instrucciones de inicio de sesión, póngase en contacto con el representante de cuentas de [!DNL Marketo Measure].

## Configuración de Adobe Admin Console y el proveedor de identidad {#set-up-your-adobe-admin-console-and-identity-provider}

Como producto que forma parte de Adobe Suite, [!DNL Marketo Measure] aprovecha todas las funciones de Adobe Admin Console para Identity Management. Puede obtener más información sobre recursos [aquí](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

Se recomienda revisar todos los recursos, las prácticas recomendadas y las opciones disponibles para usted en [Identity Management](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).

Para obtener instrucciones sobre la configuración de Identity Management en Adobe Admin Console, póngase en contacto con el representante de cuentas de [!DNL Marketo Measure].

Para facilitar la autenticación y autorización de los usuarios con sus instancias de [!DNL Marketo Measure], se requiere seguir estos pasos en Adobe Admin Console:

**Configuración de la tarjeta de producto de [!DNL Marketo Measure]**

Al acceder a Adobe Admin Console, verá sus instancias de producto de [!DNL Marketo Measure] en la sección Información general.

![Al acceder a Adobe Admin Console, verá su Marketo Measure](assets/adobe-setup-1.png)

Si hace clic en la tarjeta de producto de [!DNL Marketo Measure], puede ver todas sus instancias de [!DNL Marketo Measure]. De forma predeterminada, cada instancia de [!DNL Marketo Measure] tiene su propio perfil con el prefijo “[!DNL Marketo Measure]”. Todos los administradores o usuarios añadidos a este u otro perfil dentro de esta instancia podrán iniciar sesión en [!DNL Marketo Measure].

![Al hacer clic en la tarjeta de producto de Marketo Measure, se muestran todos los elementos](assets/adobe-setup-2.png)

No se requiere ninguna acción para crear un nuevo perfil en las instancias de producto de [!DNL Marketo Measure].

Para empezar a añadir usuarios que puedan acceder a [!DNL Marketo Measure], consulte la sección [Agregar administradores de  [!DNL Marketo Measure]  y usuarios de  [!DNL Marketo Measure] &#x200B;](#adding-marketo-measure-admins-and-marketo-measure-users) a continuación.

## Agregar administradores de [!DNL Marketo Measure] y usuarios de [!DNL Marketo Measure] {#adding-marketo-measure-admins-and-marketo-measure-users}

El siguiente paso es conceder acceso a la aplicación de [!DNL Marketo Measure] añadiendo usuarios. Esto se puede hacer en el directorio de administradores y usuarios de la tarjeta de producto de [!DNL Marketo Measure].

| Tipo de usuario | Descripción |
|---|---|
| Administradores | son administradores y usuarios avanzados de la aplicación de [!DNL Marketo Measure] con capacidad total para actualizar y gestionar opciones de configuración específicas de [!DNL Marketo Measure] |
| Usuarios | Estos son usuarios estándares de la aplicación de [!DNL Marketo Measure] con permisos de solo lectura dentro de la aplicación de [!DNL Marketo Measure] |

Al añadir un usuario a su grupo respectivo, verá su [tipo de identidad en la lista](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).

>[!NOTE]
>
>Para ser administrador de [!DNL Marketo Measure] (en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), se debe agregar un usuario como usuario _y_ como administrador a cualquier perfil de producto de [!DNL Marketo Measure] dentro de la tarjeta de producto de [!DNL Marketo Measure].

**Iniciar sesión en [!DNL Marketo Measure]**

Una vez agregado un usuario a un perfil de producto, podrá obtener acceso a sus [!DNL Marketo Measure] instancias eligiendo la opción **Iniciar sesión con Adobe ID** en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![Después de agregar un usuario a un perfil de producto, puede](assets/adobe-setup-3.png)
