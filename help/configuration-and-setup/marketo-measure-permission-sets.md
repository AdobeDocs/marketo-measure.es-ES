---
description: '[!DNL Marketo Measure] conjuntos de permisos - [!DNL Marketo Measure]'
title: Conjuntos de permisos de [!DNL Marketo Measure]
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 4%

---

# Conjuntos de permisos de [!DNL Marketo Measure] {#marketo-measure-permission-sets}

Obtenga información sobre cómo acceder y asignar conjuntos de permisos de [!DNL Marketo Measure] en Salesforce.

## Conjuntos de permisos de [!DNL Marketo Measure] {#marketo-measure-permission-sets-1}

Se incluyen tres conjuntos de permisos con el paquete Salesforce [!DNL Marketo Measure]. Estos conjuntos de permisos proporcionan acceso a [!DNL Marketo Measure] para administradores, especialistas en marketing y usuarios estándar.

Para acceder y asignar conjuntos de permisos en Salesforce:

1. Haga clic en **[!UICONTROL Configuración]**.
1. En el margen izquierdo, haga clic en **[!UICONTROL Usuarios]** y luego en **[!UICONTROL Conjuntos de permisos]**.
1. Seleccione el conjunto de permisos [!DNL Marketo Measure] que desee asignar.
1. Haga clic en **[!UICONTROL Administrar asignaciones]** y luego en **[!UICONTROL Agregar asignaciones]**.
1. Seleccione a los usuarios para el conjunto de permisos y haga clic en **[!UICONTROL Asignar]**.

   ![1. Seleccione los usuarios para el conjunto de permisos y haga clic en Asignar.](assets/bizible-full-1.png)

## Conjuntos de permisos de [!DNL Marketo Measure] explicados {#marketo-measure-permission-sets-explained}

<table>
 <tbody>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Administrador</strong></span></td>
   <td><span>Permite a un administrador de SFDC crear, leer, escribir y eliminar registros de [!DNL Marketo Measure] objetos. La licencia bajo la cual [!DNL Marketo Measure] envía datos a SFDC debe tener habilitado este conjunto de permisos. Además, se recomienda que esta licencia tenga la capacidad de editar posibles clientes convertidos en los casos en que el posible cliente se convierta antes de que [!DNL Marketo Measure] aplique los datos al registro. Esto garantiza la precisión en los informes entre Salesforce y [!DNL Marketo Measure]. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Más información aquí</a>.</span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Usuario de marketing</strong></span></td>
   <td><span>Permite al usuario de marketing leer y escribir registros de [!DNL Marketo Measure] objetos. Todos los miembros del equipo de marketing deben tener habilitado el conjunto de permisos [!DNL Marketo Measure] usuario de marketing. <br></span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Usuario estándar</strong></span></td>
   <td><span>Permite al usuario leer registros de [!DNL Marketo Measure] objetos.</span></td>
  </tr>
 </tbody>
</table>

Los equipos de desarrollo de ventas entrantes y los ejecutivos de cuentas pueden beneficiarse de los datos de [!DNL Marketo Measure]. Si estos roles desean usar los datos de [!DNL Marketo Measure] en los informes, habilite el conjunto de permisos de usuario estándar de [!DNL Marketo Measure].

>[!NOTE]
>
>Además, el usuario al que estamos conectados debe tener habilitado el perfil de &quot;usuario de marketing&quot; [!DNL Salesforce] en el nivel de usuario para que podamos acceder al objeto de Campaign. Para comprobarlo, haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Administrar usuarios]** > **[!UICONTROL Perfiles]** > **[!UICONTROL Usuario de marketing]** > **Usuarios asignados**.
