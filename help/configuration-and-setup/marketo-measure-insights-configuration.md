---
description: Configuración de [!DNL Marketo Measure] perspectivas - [!DNL Marketo Measure]
title: Configuración de información de [!DNL Marketo Measure]
exl-id: f6fe296b-d22a-43f2-b124-5d4b2f74d67a
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 4%

---

# Configuración de información de [!DNL Marketo Measure] {#marketo-measure-insights-configuration}

La aplicación de lienzo de perspectivas [!DNL Marketo Measure] debe agregarse al diseño de página de posible cliente, pero requiere una configuración adicional en la sección Aplicaciones conectadas de la configuración de [!DNL Salesforce]. Siga estas instrucciones para asegurarse de que la aplicación de lienzo tenga los permisos adecuados.

1. Vaya al programa de instalación de [!DNL Salesforce] y haga clic en **[!UICONTROL Aplicaciones conectadas]** en la ficha [!UICONTROL Administrar aplicaciones].

1. Seleccione [!DNL Marketo Measure Insights] de la lista que se rellena.

1. En la sección de directivas de [!UICONTROL OAuth], cambie la opción Usuarios permitidos a &quot;Los usuarios aprobados por el administrador están preautorizados&quot;. Aparece una ventana emergente, haz clic en **[!UICONTROL Aceptar]** y luego **[!UICONTROL Guardar]**.

   ![1. En la sección de directivas de OAuth, cambie el valor Usuarios permitidos &#x200B;](assets/marketo-app-1.png)

1. Una vez guardada la página, puede hacer clic en el botón **[!UICONTROL Administrar perfiles]**.

   ![1. Una vez guardada la página, puede hacer clic en &#x200B;](assets/marketo-app-2.png)

1. Seleccione todos los perfiles que deberían tener acceso a [!DNL Marketo Measure] Insights y haga clic en **[!UICONTROL Guardar]**.
