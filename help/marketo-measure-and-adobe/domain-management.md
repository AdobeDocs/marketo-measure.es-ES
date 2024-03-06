---
description: Administración de dominios - [!DNL Marketo Measure]
title: Administración de dominios
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Administración de dominios {#domain-management}

Para inquilinos habilitados para IMS que ejecutan [!DNL Marketo Measure] en la interfaz de Experience Cloud, [!DNL Marketo Measure] proporciona una interfaz que permite a los usuarios administrar su propia lista de dominios. [!DNL Marketo Measure] los usuarios deben comprobar primero los dominios que desean rastrear en la [Adobe Admin Console](https://adminconsole.adobe.com/). Una vez comprobados los dominios en el Admin Console, los usuarios pueden administrar si [!DNL Marketo Measure] utiliza estos dominios para rastrear el tráfico del sitio web.

## Añadir dominios en el Admin Console {#adding-domains-in-admin-console}

Los usuarios de IMS con acceso a Adobe Admin Console pueden agregar y validar los dominios que poseen. La validación del dominio implica agregar un registro DNS para cada dominio y, a continuación, permitir al Admin Console comprobar ese registro.

![](assets/domain-management-1.png)

Las instrucciones para agregar dominios se encuentran en [Documentación del Admin Console](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). Una vez agregado un dominio, debe ser [enlazado a un directorio](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## Administración de dominios en [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Después de agregar un dominio en el Admin Console, [!DNL Marketo Measure] sincroniza este registro con regularidad en la base de datos. Esta sincronización se produce todas las noches y también cada vez que un usuario visita el **[!UICONTROL Domains]** página en la [!DNL Marketo Measure] IU. De forma predeterminada, cualquier registro que [!DNL Marketo Measure] las importaciones están deshabilitadas y el inquilino debe habilitar manualmente cada dominio.

![](assets/domain-management-2.png)

En el **[!UICONTROL Integración]** > **[!UICONTROL Domains]** , el usuario ve todos los dominios que ha registrado en el Admin Console, junto con su estado. Cada dominio puede habilitarse o deshabilitarse. Si un dominio está habilitado, [!DNL Marketo Measure] El seguimiento de recopila cualquier tráfico que se ve en ese dominio. Si un dominio está deshabilitado, [!DNL Marketo Measure] ignora el tráfico proveniente de ese dominio y no crea puntos de contacto u otros datos. [!DNL Marketo Measure] confirma la deshabilitación de un dominio y advierte de cualquier ramificación:

![](assets/domain-management-3.png)

El impacto de cambiar un dominio es inmediato y los cambios no son retroactivos. En el futuro, [!DNL Marketo Measure] purgará los datos de los dominios deshabilitados después de un periodo establecido.

## Estados {#statuses}

Los estados de Admin Console se clasifican de la siguiente manera:

* **VALIDADO**: este dominio se verifica en el Admin Console
* **SIN VERIFICAR**: este dominio no está completamente verificado en el Admin Console y no es apto para el seguimiento en [!DNL Marketo Measure]
* **INVÁLIDO**: este dominio puede haber caducado o haberse eliminado del Admin Console. Seguimiento de datos en [!DNL Marketo Measure] está marcado para eliminación
* **HEREDADO**: Este dominio se creó en [!DNL Marketo Measure] y no existe en el Admin Console

Los estados de seguimiento pueden ser los siguientes:

* **ACTIVO**: [!DNL Marketo Measure] está recibiendo datos de este dominio
* **DESACTIVADO**: este dominio está disponible para seguimiento, pero está deshabilitado
* **NO DISPONIBLE**: este dominio no está disponible para seguimiento porque no está verificado

Al pasar el ratón por encima de cualquier elemento de estado individual, aparece una información sobre herramientas que déclencheur aún más ese estado.

## Preguntas frecuentes {#faq}

**¿Qué sucede cuando se elimina un dominio en el Admin Console?**

Cuando se elimina un dominio en el Admin Console, [!DNL Marketo Measure] marca el dominio como eliminado. [!DNL Marketo Measure] detiene inmediatamente el seguimiento del tráfico en este dominio, pero no eliminará ningún dato recopilado anteriormente.

**¿Por qué no puedo habilitar un dominio?**

Existen varias razones por las que un dominio puede no estar permitido para la selección en esta página. Si el dominio no se valida en el Admin Console, no estará disponible en [!DNL Marketo Measure]. Del mismo modo, si el dominio es propiedad de una organización de Adobe diferente de la actual [!DNL Marketo Measure] inquilino, puede no estar disponible para la selección.

**¿Cómo elimino un dominio de esta lista?**

Si un dominio tiene el conmutador &quot;habilitado&quot; desactivado, [!DNL Marketo Measure] lo ignora y se elimina de forma eficaz de [!DNL Marketo Measure]. Para quitar permanentemente un dominio de [!DNL Marketo Measure], debe desactivarlo en [!DNL Marketo Measure]y, a continuación, elimínelo del Admin Console.
