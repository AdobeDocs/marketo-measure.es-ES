---
description: Administración de dominios - [!DNL Marketo Measure] - Documentación del producto
title: Administración de dominios
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
source-git-commit: 148cc203f1fd2a3b90771f2223bbacacdcfad7b0
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Administración de dominios {#domain-management}

Para inquilinos habilitados para IMS en ejecución [!DNL Marketo Measure] en la interfaz del Experience Cloud, [!DNL Marketo Measure] proporciona una interfaz que permite a los usuarios administrar su propia lista de dominios. [!DNL Marketo Measure] los usuarios deben comprobar primero los dominios que desean rastrear en la variable [Adobe Admin Console](https://adminconsole.adobe.com/). Una vez verificados los dominios en el Admin Console, los usuarios pueden administrar si [!DNL Marketo Measure] utiliza estos dominios para rastrear el tráfico del sitio web.

## Adición de dominios en el Admin Console {#adding-domains-in-admin-console}

Los usuarios de IMS con acceso a Adobe Admin Console pueden agregar y validar dominios de su propiedad. La validación del dominio implica agregar un registro DNS para cada dominio y permitirle posteriormente al Admin Console comprobar ese registro.

![](assets/domain-management-1.png)

Las instrucciones para agregar dominios se encuentran en la sección [documentación del Admin Console](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). Una vez agregado un dominio, debe [vinculado a un directorio](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## Administración de dominios en [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Una vez agregado un dominio en el Admin Console, [!DNL Marketo Measure] sincronizará este registro con nuestra base de datos de forma regular. Esta sincronización se produce por la noche y también cada vez que un usuario visita el **[!UICONTROL Dominios]** en el [!DNL Marketo Measure] IU. De forma predeterminada, cualquier registro que [!DNL Marketo Measure] las importaciones se desactivarán y el inquilino debe habilitar manualmente cada dominio.

![](assets/domain-management-2.png)

En el **[!UICONTROL Integración]** > **[!UICONTROL Dominios]** , el usuario verá todos los dominios que haya registrado en el Admin Console, junto con su estado. Cada dominio puede habilitarse o deshabilitarse. Si un dominio está habilitado, [!DNL Marketo Measure] recopilará todo el tráfico que se vea en ese dominio. Si un dominio está deshabilitado, [!DNL Marketo Measure] ignorará cualquier tráfico que se vea desde ese dominio y no creará puntos de contacto u otros datos. [!DNL Marketo Measure] también confirmará la desactivación de un dominio y avisará de las ramificaciones:

![](assets/domain-management-3.png)

El impacto de alternar un dominio es inmediato y los cambios no son retroactivos. En el futuro, [!DNL Marketo Measure] depurará los datos de dominios deshabilitados después de un período de tiempo determinado.

## Estados {#statuses}

Los estados de los Admin Console se clasifican de la siguiente manera:

* **VALIDADO**: Este dominio se verifica en el Admin Console
* **NO VERIFICADO**: Este dominio no está completamente verificado en el Admin Console y no es apto para el seguimiento en [!DNL Marketo Measure]
* **NO VÁLIDO**: Es posible que este dominio haya caducado o se haya eliminado del Admin Console. Seguimiento de datos en [!DNL Marketo Measure] está marcado para su eliminación
* **HEREDADO**: Este dominio se creó en [!DNL Marketo Measure] y no existe en el Admin Console

Los estados de seguimiento pueden ser los siguientes:

* **ACTIVO**: [!DNL Marketo Measure] actualmente recibe datos de este dominio
* **DESHABILITADO**: Este dominio está disponible para seguimiento, pero está deshabilitado actualmente
* **NO DISPONIBLE**: Este dominio no está disponible para seguimiento porque no está verificado

Si pasa el ratón por encima de cualquier elemento de estado individual, se mostrará en déclencheur una información de objeto que explicará aún más ese estado.

## Preguntas frecuentes {#faq}

**¿Qué sucede cuando se elimina un dominio en el Admin Console?**

Cuando se elimina un dominio en el Admin Console, [!DNL Marketo Measure] marcará el dominio como eliminado. [!DNL Marketo Measure] detendrá inmediatamente el seguimiento del tráfico en este dominio, pero no eliminará los datos recopilados previamente.

**¿Por qué no puedo habilitar un dominio?**

Existen varias razones por las que un dominio puede no estar permitido para la selección en esta página. Si el dominio no se valida en el Admin Console, no estará disponible en [!DNL Marketo Measure]. Del mismo modo, si el dominio es propiedad de una organización de Adobe diferente de la actual [!DNL Marketo Measure] , puede que no esté disponible para la selección.

**¿Cómo elimino un dominio de esta lista?**

Si un dominio tiene el conmutador &quot;habilitado&quot; desactivado, [!DNL Marketo Measure] lo ignorará y se eliminará de forma efectiva [!DNL Marketo Measure]. Para quitar permanentemente un dominio de [!DNL Marketo Measure], debe deshabilitarlo en [!DNL Marketo Measure]y, a continuación, elimínelo del Admin Console.
