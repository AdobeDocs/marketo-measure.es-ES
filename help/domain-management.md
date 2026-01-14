---
description: Directrices de administración de dominios para usuarios de Marketo Measure
title: Administración de dominios
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Administración de dominios {#domain-management}

Para los inquilinos habilitados para IMS que ejecutan [!DNL Marketo Measure] en la interfaz de Experience Cloud, [!DNL Marketo Measure] proporciona una interfaz que permite a los usuarios administrar su propia lista de dominios. [!DNL Marketo Measure] usuarios deben comprobar primero los dominios que desean rastrear en [Adobe Admin Console](https://adminconsole.adobe.com/). Una vez verificados los dominios en Admin Console, los usuarios podrán administrar si [!DNL Marketo Measure] utiliza estos dominios para rastrear el tráfico del sitio web.

## Adición de dominios en Admin Console {#adding-domains-in-admin-console}

Los usuarios de IMS con acceso a Adobe Admin Console pueden agregar y validar los dominios que poseen. La validación del dominio implica agregar un registro DNS para cada dominio y, a continuación, permitir que Admin Console compruebe ese registro.

![Los usuarios de IMS con acceso a Adobe Admin Console pueden agregar y](assets/domain-management-4.png)

Encontrará instrucciones para agregar dominios en la [documentación de Admin Console](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). Una vez agregado el dominio, debe estar [enlazado a un directorio](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies).

## Administrar dominios en [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Después de agregar un dominio en Admin Console, [!DNL Marketo Measure] sincroniza este registro con regularidad en la base de datos. Esta sincronización se produce todas las noches, y también cada vez que un usuario visita la página **[!UICONTROL Dominios]** en la interfaz de usuario de [!DNL Marketo Measure]. De manera predeterminada, los registros que [!DNL Marketo Measure] importa están deshabilitados y el inquilino debe habilitar manualmente cada dominio.

![Después de agregar un dominio en Admin Console, Marketo Measure](assets/domain-management-2.png)

En la página **[!UICONTROL Integración]** > **[!UICONTROL Dominios]**, el usuario ve todos los dominios que ha registrado en Admin Console, junto con su estado. Cada dominio puede habilitarse o deshabilitarse. Si un dominio está habilitado, el seguimiento de [!DNL Marketo Measure] recopila el tráfico que se ve en ese dominio. Si un dominio está deshabilitado, [!DNL Marketo Measure] omitirá el tráfico proveniente de ese dominio y no creará puntos de contacto u otros datos. [!DNL Marketo Measure] confirma la deshabilitación de un dominio y advierte de cualquier ramificación:

![En la página Dominios de integración, el usuario ve todos los dominios](assets/domain-management-3.png)

El impacto de cambiar un dominio es inmediato y los cambios no son retroactivos. En el futuro, [!DNL Marketo Measure] purgará los datos de los dominios deshabilitados después de un período establecido.

## Estados {#statuses}

Los estados de Admin Console se clasifican de la siguiente manera:

* **VALIDADO**: este dominio está verificado en Admin Console
* **SIN VERIFICAR**: este dominio no está completamente verificado en Admin Console y no es apto para seguimiento en [!DNL Marketo Measure]
* **NO VÁLIDO**: Es posible que este dominio haya caducado o se haya eliminado de Admin Console. Se ha marcado la eliminación de los datos de seguimiento en [!DNL Marketo Measure]
* **HEREDADO**: este dominio se creó en [!DNL Marketo Measure] y no existe en Admin Console

Los estados de seguimiento pueden ser los siguientes:

* **ACTIVO**: [!DNL Marketo Measure] está recibiendo datos de este dominio
* **DESHABILITADO**: este dominio está disponible para seguimiento, pero está deshabilitado
* **NO DISPONIBLE**: este dominio no está disponible para seguimiento porque no está verificado

Al pasar el ratón por encima de cualquier elemento de estado individual, aparece una información sobre herramientas que déclencheur aún más ese estado.

## Preguntas frecuentes {#faq}

**¿Qué sucede cuando se elimina un dominio en Admin Console?**

Cuando se quita un dominio en Admin Console, [!DNL Marketo Measure] marca el dominio como eliminado. [!DNL Marketo Measure] detiene inmediatamente el seguimiento del tráfico en este dominio, pero no eliminará ningún dato recopilado anteriormente.

**¿Por qué no puedo habilitar un dominio?**

Existen varias razones por las que un dominio puede no estar permitido para la selección en esta página. Si el dominio no se valida en Admin Console, no estará disponible en [!DNL Marketo Measure]. Del mismo modo, si el dominio es propiedad de una organización de Adobe diferente del inquilino actual de [!DNL Marketo Measure], es posible que no esté disponible para su selección.

**¿Cómo quito un dominio de esta lista?**

Si un dominio tiene el conmutador &quot;habilitado&quot; desactivado, [!DNL Marketo Measure] lo ignora y se elimina de [!DNL Marketo Measure]. Para quitar permanentemente un dominio de [!DNL Marketo Measure], debe deshabilitarlo en [!DNL Marketo Measure] y después quitarlo de Admin Console.
