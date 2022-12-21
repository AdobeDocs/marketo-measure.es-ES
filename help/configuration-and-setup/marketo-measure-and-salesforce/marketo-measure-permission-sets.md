---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] Conjuntos de permisos: [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Conjuntos de permisos"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# [!DNL Marketo Measure] Conjuntos de permisos {#marketo-measure-permission-sets}

Obtenga información sobre cómo acceder y asignar [!DNL Marketo Measure] Conjuntos de permisos en Salesforce.

## [!DNL Marketo Measure] Conjuntos de permisos {#marketo-measure-permission-sets-1}

Se incluyen tres conjuntos de permisos con la variable [!DNL Marketo Measure] Paquete Salesforce. Estos conjuntos de permisos proporcionan acceso a [!DNL Marketo Measure] para administradores, especialistas en marketing y usuarios estándar.

Para acceder y asignar conjuntos de permisos en Salesforce:

1. Haga clic en **[!UICONTROL Configuración]**.
1. En el margen izquierdo, haga clic en **[!UICONTROL Usuarios]**, luego **[!UICONTROL Conjuntos de permisos]**.
1. Seleccione el [!DNL Marketo Measure] Conjunto de permisos que desea asignar.
1. Haga clic en **[!UICONTROL Administrar asignaciones]**, luego **[!UICONTROL Agregar asignaciones]**.
1. Seleccione los usuarios del conjunto de permisos y haga clic en **[!UICONTROL Asignar]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Conjuntos de permisos explicados {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Administrador</strong></span></td> 
   <td><span>Proporciona a un administrador de SFDC la capacidad de crear, leer, escribir y eliminar registros de [!DNL Marketo Measure] objetos. La licencia en virtud de la cual [!DNL Marketo Measure] inserta los datos en SFDC deben tener este conjunto de permisos habilitado. Además, se recomienda que esta licencia tenga la capacidad de editar posibles clientes convertidos en los casos en los que el posible cliente se convierta antes de [!DNL Marketo Measure] aplicar datos al registro. Esto garantizará la precisión en los informes entre Salesforce y [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">Lea más aquí</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Usuario de marketing</strong></span></td> 
   <td><span>Permite al usuario de marketing leer y escribir registros de [!DNL Marketo Measure] objetos. Todos los miembros del equipo de marketing deben tener la variable [!DNL Marketo Measure] Conjunto de permisos de usuario de marketing habilitado. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Usuario estándar</strong></span></td> 
   <td><span>Permite al usuario leer registros de [!DNL Marketo Measure] objetos.</span></td> 
  </tr> 
 </tbody> 
</table>

Los equipos de desarrollo de ventas entrantes y los ejecutivos de cuentas pueden beneficiarse de [!DNL Marketo Measure] datos. Si estas funciones desean utilizar [!DNL Marketo Measure] en los informes, habilite la variable [!DNL Marketo Measure] Conjunto de permisos de usuario estándar.

>[!NOTE]
>
>Además, el usuario al que estamos conectados debe tener el &quot;Usuario de marketing&quot; [!DNL Salesforce] Perfil habilitado a nivel de usuario para que podamos acceder al objeto de campaña. Para comprobar esto, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Administrar usuarios]** > **[!UICONTROL Perfiles]** > **[!UICONTROL Usuario de marketing]** > **Usuarios asignados**.
