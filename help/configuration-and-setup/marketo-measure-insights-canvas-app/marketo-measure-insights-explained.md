---
unique-page-id: 18874676
description: "[!DNL Marketo Measure] Información explicada - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Perspectivas explicadas"
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Información explicada de [!DNL Marketo Measure] {#marketo-measure-insights-explained}

Obtenga información acerca de [!DNL Marketo Measure] Vista de perspectivas en [!DNL Salesforce], incluidos los distintos iconos que representan y cómo utilizar la función. Esta función es muy útil para ver las primeras 20 sesiones de un posible cliente, contacto o cuenta.

Una vez que el usuario ha rastreado a alguien, [!DNL Marketo Measure] JavaScript y rellena un formulario en su sitio web, la persona se convierte en un posible cliente de su sistema y sus datos de marketing digital se envían a su organización de Salesforce (SFDC). Cuando esto sucede, se ven los datos de punto de contacto rellenados dentro de la variable [!DNL Marketo Measure] Sección de perspectivas del posible cliente (una aplicación de lienzo) sobre los objetos de cliente potencial/contacto/oportunidad/cuenta.

En primer lugar, verá en la parte central de sus perspectivas, el número de sesiones que la persona ha tenido en su sitio web. Puede desplazarse por estas sesiones y navegar a su antojo.

![](assets/1.png)

Puede ver el resumen de todas las sesiones si hace clic en &quot;Todas&quot; en la parte superior central de sus perspectivas. Aquí puede comprender las fechas de las sesiones individuales, qué canal o fuente las impulsó y un conjunto de iconos que especifican más información.

Lo primero que se ve son los iconos FT o LC. Representan la posición del punto de contacto de las sesiones de la lista. Específicamente, FT significa Primer toque y LC significa Creación de plomo. Puede tener varias sesiones, pero solo un Touchpoint puede ser la FT o la LC. Nunca encontrará varias FT o LC asociadas a una persona.

Los iconos que parecen papel indican que se produjo una vista de página dentro de la sesión. Es probable que todas las sesiones incluyan este icono.

![](assets/2.png)

El icono que parece un vaso de precipitados indica que se ha producido un experimento de prueba A/B. Nos integramos con Optimizely y VWO en este punto. Con esta integración, podemos impulsar el experimento y la variación que vio el usuario en su sesión específica.

![](assets/3.png)

Si hace clic en cualquier sesión específica (puede hacerlo haciendo clic en la fecha real de la sesión o en la parte media superior de las sesiones agrupadas), podrá ver los detalles de la sesión. En cada sesión, puede ver todas las páginas específicas que vio el usuario ordenadas por fecha y hora.

![](assets/4.png)

En el lado derecho de cada sesión, puede ver más datos de marketing granulares que impulsan la [!DNL Marketo Measure] en el SFDC. En este ejemplo, puede ver Grupo de publicidad, Contenido de publicidad, Campaña, Palabra clave, Medio. También puede desplazarse hacia abajo para ver más de las [!DNL Marketo Measure] datos que proporcionamos.

Por último, una vez que alguien tiene una miríada de sesiones, puede utilizar algunos filtros dentro de [!UICONTROL Insights] para buscar partes específicas de su participación en el sitio. Puede filtrar por [!UICONTROL Posición del punto de contacto] por ejemplo.

También puede buscar por Vistas de página, Pruebas AB o Forms.
