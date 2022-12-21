---
unique-page-id: 18874535
description: Transición a [!DNL Marketo Measure] desde círculo completo - [!DNL Marketo Measure] - Documentación del producto
title: Transición a [!DNL Marketo Measure] desde círculo completo
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Transición a [!DNL Marketo Measure] desde círculo completo {#transitioning-to-marketo-measure-from-full-circle}

Cómo hacer que el cambio de Círculo completo a [!DNL Marketo Measure]? No estás solo. Estas son las consideraciones más importantes que hay que tener en cuenta y las lecciones que hemos aprendido de otros clientes que han hecho el cambio.

## Seguimiento basado en campañas frente al seguimiento de varias fuentes {#campaign-based-tracking-vs-multi-source-tracking}

Todas las interacciones en [!UICONTROL Círculo completo] se rastrean mediante la pertenencia a campañas CRM. con [!DNL Marketo Measure], el recorrido de compra se compila mediante una combinación de nuestros registros de actividad de JavaScript, CRM campaign membership y CRM. El paso mental de &quot;todas las interacciones deben rastrearse en una campaña de CRM para que nuestros informes de atribución funcionen&quot; a &quot;solo es necesario rastrear este subconjunto de interacciones en una campaña de CRM para que nuestros informes de atribución funcionen&quot; puede ser complicado.

En términos generales, así es como [!DNL Marketo Measure] crea registros de punto de contacto para los principales tipos de interacciones:

* Rellenos de formularios en su sitio o sitios: [!DNL Marketo Measure] Javascript
* Vistas de página de su sitio: Creado por [!DNL Marketo Measure] Javascript solo si esta vista de página condujo a un hito de CRM designado (como Lead o Oportunity Creation)
* Interacciones sin conexión, como conferencias o ferias: abono a campañas CRM
* Interacciones digitales que se producen en cualquier lugar de Internet que no sea su sitio (como un seminario web alojado en un sitio de terceros que genera una carga de lista): abono a campañas CRM
* Interacciones con su equipo de ventas: Registros de actividad de CRM

Si se siente cómodo con la administración de campañas de CRM y prefiere mantener los procesos existentes en su sitio, eso está bien. No duele [!DNL Marketo Measure] para continuar rastreando todas las interacciones en campañas CRM. Puede diseñar una lógica que solo cree puntos de contacto a partir de un subconjunto de campañas deseado para evitar la duplicación de puntos de contacto.

## Visibilidad vs. Atribución {#visibility-vs-attribution}

Con la mayoría de las configuraciones de círculo completo, verá cada interacción que una persona tiene con sus esfuerzos de marketing o ventas. Vistas de página, visitas de página repetidas, pertenencia a campañas duplicadas y triplicadas: el círculo completo aparece en todas ellas. Si ve una página 300 veces, Círculo completo crea 300 campañas duplicadas y le ofrece una pertenencia en cada una de ellas. [!DNL Marketo Measure] no, y esa fue una decisión consciente de diseño por nuestra parte.

[!DNL Marketo Measure] Su objetivo es proporcionarle un artículo de atribución que aparezca interacciones significativas y distribuya el peso entre los puntos de contacto más impactantes de forma adecuada. Por ejemplo, la variable [!DNL Marketo Measure] el marco de trabajo no mostrará las vistas de página (sin rellenar el formulario) como puntos de contacto rutinarios. Es poco probable que una vista de página independiente tenga un impacto en la promoción de un recorrido de compra, pero crearemos un punto de contacto si es la interacción más reciente antes de un hito de CRM designado (como la creación de posibles clientes o de oportunidades). No queremos mostrarles todo. Queremos mostrarles lo que importa, desde el punto de vista de la atribución.

Trabaje con su [!DNL Marketo Measure] rep para establecer las expectativas adecuadas sobre qué datos ya no estarán disponibles para su equipo.

## Pre-[!DNL Marketo Measure] Datos {#pre-marketo-measure-data}

La recomendación estándar es comenzar a realizar informes y recopilar datos desde el día en que implementó el [!DNL Marketo Measure] JavaScript hacia adelante, que se duplica para los antiguos clientes de Full Circle. Considere las dos secciones anteriores: Está acostumbrado a ver una mayor cantidad de datos y a todos esos datos procedentes de la pertenencia a campañas CRM. Si decide incluir algunos o todos esos datos de antes de que [!DNL Marketo Measure] implementación, no comparará manzanas con manzanas en la fecha de implementación de JavaScript.

Dicho esto, sin duda entendemos que muchos clientes necesitan estos datos históricos; especialmente si tiene un ciclo de ventas más largo (bueno que 90 días), puede que desee dar [!DNL Marketo Measure] visibilidad de la[!DNL Marketo Measure] datos. Discuta esto cuidadosamente con su [!DNL Marketo Measure] rep, y tenga siempre en cuenta que la distorsión en la fecha de implementación puede provocar mejoras o caídas en el rendimiento o la participación del canal, así como otras inferencias potencialmente incorrectas.

## En resumen {#in-summary}

Está en buena compañía y hemos ayudado a muchos otros clientes a manejar estos cambios. Trabaje con su [!DNL Marketo Measure] rep para comprender los impactos anteriores, así como cualquier otra preocupación que pueda tener.
