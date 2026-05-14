---
unique-page-id: 18874769
description: Configuración de [!DNL Marketo Measure] perspectivas - [!DNL Marketo Measure]
title: Configuración de información de [!DNL Marketo Measure]
exl-id: f6fe296b-d22a-43f2-b124-5d4b2f74d67a
feature: Reporting
TQID: https://experienceleague.adobe.com/5i-eUsazdk6Ahr91VhW31gynWc42FF-TMOs-3PDIZs0
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 116
ht-degree: 3%

---

# Configuración de información de [!DNL Marketo Measure] {#marketo-measure-insights-configuration}

La aplicación de lienzo de perspectivas [!DNL Marketo Measure] debe agregarse al diseño de página de posible cliente, pero requiere una configuración adicional en la sección Aplicaciones conectadas de la configuración de [!DNL Salesforce]. Siga estas instrucciones para asegurarse de que la aplicación de lienzo tenga los permisos adecuados.

1. Vaya al programa de instalación de [!DNL Salesforce] y haga clic en **[!UICONTROL Aplicaciones conectadas]** en la ficha [!UICONTROL Administrar aplicaciones].

1. Seleccione [!DNL Marketo Measure Insights] de la lista que se rellena.

1. En la sección de directivas de [!UICONTROL OAuth], cambie la opción Usuarios permitidos a &quot;Los usuarios aprobados por el administrador están preautorizados&quot;. Aparece una ventana emergente, haz clic en **[!UICONTROL Aceptar]** y luego **[!UICONTROL Guardar]**.

   ![](assets/1-1.png)

1. Una vez guardada la página, puede hacer clic en el botón **[!UICONTROL Administrar perfiles]**.

   ![](assets/2-1.png)

1. Seleccione todos los perfiles que deberían tener acceso a [!DNL Marketo Measure] Insights y haga clic en **[!UICONTROL Guardar]**.
