---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] Conjuntos de permisos - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Conjuntos de permisos"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# Conjuntos de permisos de [!DNL Marketo Measure] {#marketo-measure-permission-sets}

Obtenga información sobre cómo acceder a y asignar [!DNL Marketo Measure] Conjuntos de permisos en Salesforce.

## Conjuntos de permisos de [!DNL Marketo Measure] {#marketo-measure-permission-sets-1}

Se incluyen tres conjuntos de permisos con [!DNL Marketo Measure] Paquete de Salesforce. Estos conjuntos de permisos proporcionan acceso a [!DNL Marketo Measure] para administradores, especialistas en marketing y usuarios estándar.

Para acceder y asignar conjuntos de permisos en Salesforce:

1. Clic **[!UICONTROL Configurar]**.
1. En el margen izquierdo, haga clic en **[!UICONTROL Usuarios]**, entonces **[!UICONTROL Conjuntos de permisos]**.
1. Seleccione el [!DNL Marketo Measure] Conjunto de permisos que desea asignar.
1. Clic **[!UICONTROL Administrar asignaciones]**, entonces **[!UICONTROL Agregar asignaciones]**.
1. Seleccione los usuarios del conjunto de permisos y haga clic en **[!UICONTROL Asignar]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Conjuntos de permisos explicados {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Administrador</strong></span></td> 
   <td><span>Permite a un administrador de SFDC crear, leer, escribir y eliminar registros de [!DNL Marketo Measure] objetos. La licencia con la que [!DNL Marketo Measure] los datos enviados a SFDC deben tener este conjunto de permisos habilitado. Además, se recomienda que esta licencia tenga la capacidad de editar posibles clientes convertidos en los casos en que el posible cliente se convierta antes que [!DNL Marketo Measure] aplicación de datos al registro. Esto garantiza la precisión en los informes entre Salesforce y [!DNL Marketo Measure]. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Puede obtener más información aquí</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Usuario de marketing</strong></span></td> 
   <td><span>Permite al usuario de marketing leer y escribir registros de [!DNL Marketo Measure] objetos. Todos los miembros del equipo de marketing deben tener el [!DNL Marketo Measure] Conjunto de permisos de usuario de marketing habilitado. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Usuario estándar</strong></span></td> 
   <td><span>Permite al usuario leer registros de [!DNL Marketo Measure] objetos.</span></td> 
  </tr> 
 </tbody> 
</table>

Los equipos de desarrollo de ventas entrantes y los ejecutivos de cuentas pueden beneficiarse de [!DNL Marketo Measure] datos. Si estas funciones desean utilizar [!DNL Marketo Measure] en los informes, habilite la opción [!DNL Marketo Measure] Conjunto de permisos de usuario estándar.

>[!NOTE]
>
>Además, el usuario al que estamos conectados debe tener el &quot;Usuario de marketing&quot; [!DNL Salesforce] Perfil habilitado a nivel de usuario para que podamos acceder al objeto de Campaign. Para comprobarlo, haga clic en **[!UICONTROL Configurar]** > **[!UICONTROL Administrar usuarios]** > **[!UICONTROL Perfiles]** > **[!UICONTROL Usuario de marketing]** > **Usuarios asignados**.
