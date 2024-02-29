---
description: 'Configuración de Adobe Admin Console, Marketo Measure: Documentación del producto'
title: Configuración de Adobe Admin Console
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 39%

---

# Configuración de Adobe Admin Console {#adobe-admin-console-setup}

El primer paso para utilizar [!DNL Marketo Measure] es crear e iniciar sesión en el Adobe Admin Console aprovisionado. Si aún no ha recibido el correo electrónico con las instrucciones de inicio de sesión, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

## Configuración de Adobe Admin Console y el proveedor de identidad {#set-up-your-adobe-admin-console-and-identity-provider}

Como producto dentro de la suite de Adobe, [!DNL Marketo Measure] utiliza todas las funciones de Adobe Admin Console para Identity Management. Puede obtener más información [aquí](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

Recomendamos revisar todos los recursos, las prácticas recomendadas y las opciones disponibles para usted en [Identity Management](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).

Para obtener instrucciones y revisar la configuración de Identity Management en Adobe Admin Console, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

Para facilitar la autenticación y autorización de usuarios con su [!DNL Marketo Measure] En las instancias de, se requieren los siguientes pasos en Adobe Admin Console:

**Configuración de la tarjeta de producto de [!DNL Marketo Measure]**

Al acceder a Adobe Admin Console, verá su [!DNL Marketo Measure] Instancias de producto presentes en la sección Información general.

![](assets/adobe-admin-console-setup-1.png)

Haciendo clic en [!DNL Marketo Measure] La tarjeta de producto le muestra todos sus [!DNL Marketo Measure] instancias. De forma predeterminada, cada instancia de [!DNL Marketo Measure] tiene su propio perfil con el prefijo “[!DNL Marketo Measure]”. Todos los administradores o usuarios añadidos a este u otro perfil dentro de esta instancia podrán iniciar sesión en [!DNL Marketo Measure].

![](assets/adobe-admin-console-setup-2.png)

No se requiere ninguna acción para crear un perfil dentro de [!DNL Marketo Measure] Instancia(s) de producto.

Para empezar a agregar usuarios que puedan acceder a [!DNL Marketo Measure], consulte la [Agregando [!DNL Marketo Measure] Administradores y [!DNL Marketo Measure] Usuarios](#adding-marketo-measure-admins-and-marketo-measure-users) más abajo.

## Agregar administradores de [!DNL Marketo Measure] y usuarios de [!DNL Marketo Measure] {#adding-marketo-measure-admins-and-marketo-measure-users}

El siguiente paso es conceder acceso a la aplicación de [!DNL Marketo Measure] añadiendo usuarios. Esto se puede hacer en el directorio de administradores y usuarios de la tarjeta de producto de [!DNL Marketo Measure].

| Tipo de usuario | Descripción |
|---|---|
| Administradores | son administradores y usuarios avanzados de la aplicación de [!DNL Marketo Measure] con capacidad total para actualizar y gestionar opciones de configuración específicas de [!DNL Marketo Measure] |
| Usuarios | son usuarios estándar de [!DNL Marketo Measure] Aplicación con permisos de solo lectura dentro de [!DNL Marketo Measure] aplicación |

Al agregar un usuario a su grupo respectivo, verá su [Tipo de identidad enumerado](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).

>[!NOTE]
>
>Para ser un [!DNL Marketo Measure] administrador (en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), se debe agregar un usuario como Usuario _y_ Añadir un administrador a cualquier [!DNL Marketo Measure] perfil de producto dentro de [!DNL Marketo Measure] tarjeta de producto.

**Iniciar sesión en [!DNL Marketo Measure]**

Una vez que se añade un usuario a un perfil de producto, puede acceder a su [!DNL Marketo Measure] al elegir la variable **Iniciar sesión con Adobe ID** opción en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/adobe-admin-console-setup-3.png)
