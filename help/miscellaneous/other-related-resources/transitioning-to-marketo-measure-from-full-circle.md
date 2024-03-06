---
unique-page-id: 18874535
description: 'Transición a [!DNL Marketo Measure] de Círculo completo: [!DNL Marketo Measure]'
title: Transición a  [!DNL Marketo Measure]  desde “Full Circle”
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Transición a [!DNL Marketo Measure] desde círculo completo {#transitioning-to-marketo-measure-from-full-circle}

Cambio de Círculo completo a [!DNL Marketo Measure]? No estás solo... Estas son las consideraciones más importantes que debe tener en cuenta y las lecciones que hemos aprendido de otros clientes que han realizado el cambio.

## Seguimiento basado en campañas frente a seguimiento de varias fuentes {#campaign-based-tracking-vs-multi-source-tracking}

Todas las interacciones en [!UICONTROL Círculo completo] se rastrean mediante la pertenencia a campañas CRM. Con [!DNL Marketo Measure], el recorrido de compra se compila mediante una combinación de nuestros registros de JavaScript, pertenencia a campañas CRM y actividad CRM. Puede ser difícil hacer el cambio mental de &quot;toda interacción debe rastrearse en una campaña de CRM para que nuestros informes de atribución funcionen&quot; a &quot;solo este subconjunto de interacciones debe rastrearse en una campaña de CRM para que nuestros informes de atribución funcionen&quot;.

En términos generales, así es como [!DNL Marketo Measure] crea registros de puntos de contacto para los principales tipos de interacciones:

* Rellenos de formularios en sus sitios: [!DNL Marketo Measure] JavaScript
* Vistas de página en los sitios: creado por [!DNL Marketo Measure] JavaScript solo si esta vista de página ha impulsado un hito CRM designado (como la creación de clientes potenciales o de oportunidades)
* Interacciones sin conexión, como conferencias o ferias comerciales: suscripción a la campaña de CRM
* Interacciones digitales que se producen en cualquier lugar de Internet que no sea el sitio (como un seminario web alojado en un sitio de terceros que genera una carga de lista): suscripción a una campaña de CRM
* Interacciones con el equipo de ventas: registros de actividad de CRM

Si se siente cómodo con la administración de campañas de CRM y prefiere mantener los procesos existentes en su lugar, está bien. No me duele. [!DNL Marketo Measure] para continuar rastreando todas las interacciones en campañas de CRM. Puede diseñar una lógica que solo cree puntos de contacto a partir de un subconjunto deseado de campañas para evitar la duplicación de puntos de contacto.

## Visibilidad vs. Atribución {#visibility-vs-attribution}

Con la mayoría de las configuraciones de Círculo completo, puede ver cada interacción que una persona tiene con sus esfuerzos de marketing o ventas. Vistas de página, visitas de página repetidas, pertenencia a campañas triplicadas: todas ellas aparecen en Círculo completo. Si ve una página 300 veces, Full Circle crea 300 campañas duplicadas y le da una membresía en cada una de ellas. [!DNL Marketo Measure] no, y eso fue una decisión de diseño consciente por nuestra parte.

[!DNL Marketo Measure] tiene como objetivo proporcionarle una historia de atribución que muestre interacciones significativas y distribuya adecuadamente el peso entre los puntos de contacto más impactantes. Por ejemplo, la variable [!DNL Marketo Measure] el marco de trabajo no muestra las vistas de página (sin rellenos de formulario) como puntos de contacto habituales. No es probable que una vista de página independiente afecte al avance de un recorrido de compra, pero creamos un punto de contacto si es la interacción más reciente antes de un hito de CRM designado (como la creación de clientes potenciales o de oportunidades). No queremos mostrarte todo. - ¿Qué? Queremos mostrarles lo que importa, desde el punto de vista de la atribución.

Trabaje con su [!DNL Marketo Measure] un representante de para establecer las expectativas adecuadas sobre qué datos ya no estarán disponibles para su equipo.

## Pre-[!DNL Marketo Measure] Datos {#pre-marketo-measure-data}

La recomendación estándar es comenzar con la creación de informes y la recopilación de datos desde el día en que se implementó el [!DNL Marketo Measure] JavaScript hacia adelante, y eso es el doble para los antiguos clientes de Full Circle. Piense en las dos secciones anteriores: Está acostumbrado a ver una mayor cantidad de datos y está acostumbrado a todos esos datos procedentes de la pertenencia a la campaña de CRM. Si decide incluir algunos o todos los datos anteriores a la [!DNL Marketo Measure] , no comparará manzanas con manzanas en la fecha de implementación de JavaScript.

Dicho esto, sin duda entendemos que muchos clientes necesitan estos datos históricos; especialmente si tiene un ciclo de ventas más largo (más de 90 días), es posible que desee dar [!DNL Marketo Measure] visibilidad sobre la pre-[!DNL Marketo Measure] datos. Analice esto detenidamente con su [!DNL Marketo Measure] repita y tenga siempre en cuenta que el sesgo en la fecha de implementación puede provocar la aparición de mejoras o caídas en el rendimiento o la participación del canal, así como otras deducciones potencialmente incorrectas.

## En resumen {#in-summary}

Está en buena compañía y hemos ayudado a muchos otros clientes a gestionar estos cambios. Trabaje con su [!DNL Marketo Measure] rep para comprender los impactos anteriores y cualquier otra preocupación que pueda tener.
