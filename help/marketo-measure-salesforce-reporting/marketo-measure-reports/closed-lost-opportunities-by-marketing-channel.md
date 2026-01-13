---
description: Cerrar oportunidades perdidas por canal de mercadotecnia - [!DNL Marketo Measure]
title: Oportunidades perdidas cerradas por canal de marketing
exl-id: 010169fc-f7e7-4ab2-92fe-87e4250dd536
feature: Channels, Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 3%

---


# Oportunidades perdidas cerradas por canal de marketing {#closed-lost-opportunities-by-marketing-channel}

Aunque este informe puede depender de las fases de oportunidad, en este informe se mostrarán los canales de marketing que han contribuido a generar oportunidades que no se han cerrado.

1. Haga clic en la ficha **[!UICONTROL Informes]** de Salesforce y seleccione **[!UICONTROL Nuevo informe]**.

   ![Pestaña Informes de Salesforce con el botón Nuevo informe resaltado](assets/1-3.jpg)

1. En la búsqueda rápida, escriba &quot;Atribución Bizible&quot; y seleccione el tipo de informe **[!UICONTROL Atribución Bizible Touchpoint con oportunidad]**; a continuación, seleccione **[!UICONTROL Crear]**.

   ![Selección de tipo de informe que muestra el punto de contacto de atribución Bizible con la opción de oportunidad](assets/2-3.jpg)

1. Desde la parte superior del informe, muestre &quot;[!UICONTROL Todos los puntos de contacto de atribución de Bizible]&quot; y ajuste el campo de fecha según el periodo de tiempo sobre el que desee informar. En nuestro ejemplo, estamos mirando Todo el tiempo. Además, cambie el formato del informe de Tabular a Summary.

   ![Filtro de informe que muestra todos los puntos de contacto de atribución Bizible con selector de intervalo de fechas](assets/3-3.jpg)

   ![Opciones de formato de informe con formato de resumen seleccionado](assets/4-2.jpg)

1. Ahora, se agregarán campos al informe. En la búsqueda rápida de la izquierda, escriba &quot;Canal de marketing&quot; y agréguelo a la agrupación Resumen del informe.

   ![Report Builder que muestra el campo Canal de mercadotecnia que se está agregando a la agrupación de resumen](assets/5.jpg)

1. A continuación, agregaremos un filtro para ver solo las operaciones cerradas perdidas. En la búsqueda rápida de la izquierda, busque el campo &quot;Stage&quot; y arrástrelo al área de filtro.

   ![Área de filtro de informe con campo de fase arrastrado a la sección de filtro](assets/6.jpg)

1. A partir de ahí, seleccionará la lupa para elegir cualquier etapa que utilice para las oportunidades de &quot;Pérdida cerrada&quot;. En nuestro caso, utilizaremos el nombre estándar de &quot;Cerrado perdido&quot;.

   ![Selector de filtro de escenario que muestra la opción de selección de etapa Cerrada perdida](assets/7.jpg)

1. ¡Ahora, adelante y ejecute el informe!

   Este es un informe de oportunidades resumido por Canal de marketing que mide las oportunidades perdidas cerradas en sus canales. Este informe le permite comprender qué canales pueden tener un bajo rendimiento. No dude en agregar cualquier filtro o campo del que desee informar.

>[!MORELIKETHIS]
>[[!DNL Marketo Measure] Tutoriales: Informes adicionales de SFDC](https://experienceleague.adobe.com/es/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/addtional-salesforce-reports)
