---
description: Configuración de Adobe Admin Console - Marketo Measure - Documentación del producto
title: Configuración de Adobe Admin Console
feature: Installation
source-git-commit: 68eb5bf83d589c9161490b1772551ed46a9ce444
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Configuración de Adobe Admin Console {#adobe-admin-console-setup}

El primer paso para utilizar [!DNL Marketo Measure] es crear e iniciar sesión en el Adobe Admin Console aprovisionado. Si aún no ha recibido el correo electrónico con las instrucciones de inicio de sesión, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

## Configuración de Adobe Admin Console y el proveedor de identidad {#set-up-your-adobe-admin-console-and-identity-provider}

Como producto dentro de la suite de Adobe, [!DNL Marketo Measure] aprovecha todas las funciones de Adobe Admin Console para Identity Management. Se pueden añadir más recursos [encontrado aquí](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

Recomendamos revisar todos los recursos, las prácticas recomendadas y las opciones disponibles para usted en [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Para obtener instrucciones y revisar la configuración de Identity Management en Adobe Admin Console, póngase en contacto con su [!DNL Marketo Measure] Representante de cuentas.

Para facilitar la autenticación y autorización de los usuarios con su [!DNL Marketo Measure] En las instancias de, se requieren los siguientes pasos en Adobe Admin Console:

**Configuración de la variable [!DNL Marketo Measure] Tarjeta del producto**

Al acceder a Adobe Admin Console, verá su [!DNL Marketo Measure] Las instancias de producto presentes en la sección Información general.

![](assets/adobe-admin-console-setup-1.png)

Haciendo clic en [!DNL Marketo Measure] La tarjeta de producto le mostrará todos sus [!DNL Marketo Measure] instancia(s). De forma predeterminada, cada [!DNL Marketo Measure] La instancia tiene su propio perfil con el prefijo &quot;[!DNL Marketo Measure]&#39;. Cualquier administrador o usuario agregado a este perfil o a cualquier otro dentro de esta instancia podrá iniciar sesión en [!DNL Marketo Measure].

![](assets/adobe-admin-console-setup-2.png)

No se requiere ninguna acción para crear un nuevo perfil dentro de [!DNL Marketo Measure] Instancia(s) de producto.

Para empezar a agregar usuarios que puedan acceder a [!DNL Marketo Measure], consulte la [Agregando [!DNL Marketo Measure] Administradores y [!DNL Marketo Measure] Usuarios](#adding-marketo-measure-admins-and-marketo-measure-users) más abajo.

## Agregando [!DNL Marketo Measure] Administradores y [!DNL Marketo Measure] Usuarios {#adding-marketo-measure-admins-and-marketo-measure-users}

El siguiente paso es conceder acceso a [!DNL Marketo Measure] mediante la adición de usuarios. Esto se puede hacer en el directorio de administradores y usuarios de [!DNL Marketo Measure] tarjeta de producto.

| Tipo de usuario | Descripción |
|---|---|
| Administradores | son administradores y usuarios avanzados de [!DNL Marketo Measure] Aplicación con capacidad total para actualizar y gestionar [!DNL Marketo Measure]Opciones de configuración específicas de |
| Usuarios | son usuarios estándar de [!DNL Marketo Measure] Aplicación con permisos de solo lectura dentro de [!DNL Marketo Measure] aplicación |

Al agregar un usuario a su grupo respectivo, verá su [Tipo de identidad enumerado](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>Para poder ser un [!DNL Marketo Measure] administrador (en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), se debe agregar un usuario como Usuario _y_ Añadir un administrador a cualquier [!DNL Marketo Measure] perfil de producto dentro de [!DNL Marketo Measure] tarjeta de producto.

**Iniciando sesión en[!DNL Marketo Measure]**

Una vez que se añade un usuario a un perfil de producto, puede acceder a su [!DNL Marketo Measure] instancia(s) seleccionando la variable **Iniciar sesión con Adobe ID** opción en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/adobe-admin-console-setup-3.png)

