---
unique-page-id: 18874781
description: 'Configuración de la vista del administrador de campañas de doble clic mediante atribución: [!DNL Marketo Measure] - Documentación del producto'
title: Configuración de la atribución de visualizaciones del administrador de campañas de DoubleClick
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 4%

---

# Configuración de la atribución de visualizaciones del administrador de campañas de DoubleClick {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Medición de la vista mediante atribución {#measuring-view-through-attribution}

>[!NOTE]
>
>Si está utilizando el [!DNL Marketo Measure] y DoubleClick Campaign Manager, se requiere un [Conexión de API](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) para que podamos descargar los detalles de las campañas y los elementos creativos para resolver los anuncios.

Para empezar a obtener una perspectiva más granular desde la vista hasta el seguimiento con el administrador de campañas de doble clic, es necesario configurar el píxel de seguimiento.

Por favor [haga clic aquí](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) para obtener más información sobre [!DNL Marketo Measure] Ver mediante la funcionalidad de atribución.

[!DNL Marketo Measure] se considera una etiqueta de &quot;piggyback&quot; porque es una llamada de terceros a través de la etiqueta de publicidad de DCM. Las etiquetas Piggyback no funcionan con etiquetas de imagen, solo con etiquetas de iframe o javascript. Según el Soporte de DCM, esto no ha cambiado recientemente y siempre ha sido así. Las etiquetas estándar quedaron obsoletas el 2 de octubre de 2017, pero no afectan a la capacidad de [!DNL Marketo Measure] para rastrear las impresiones.

En el caso de que aproveche una jerarquía principal y secundaria en DCM, necesitaremos que nuestra etiqueta se aplique a todos los niveles para el seguimiento de impresiones.

## Cómo añadir la etiqueta de imagen {#how-to-add-the-image-tag}

Agregará la etiqueta a Doubleclick bajo la configuración Anunciante y querrá crear una Etiqueta de evento de impresión.

1. Agregue el siguiente código como píxel de imagen 1x1.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Una vez agregado, confirme que los delimitadores se asignan de la siguiente manera. Debe ser automático una vez que se aplique la etiqueta:

   v = %eadv! Expandir ID del anunciante\
   a = %eaid! Expandir ID de anuncio\
   c = %ecid! Expandir ID de creativo\
   s = %esid! Expandir ID del sitio\
   p = %epid! Expandir ID de ubicación\
   m = %m Macro de código coincidente\
   n = Macro de número aleatorio %n

   ![](assets/1.png)

## Preguntas frecuentes {#faq}

**P: ¿La etiqueta de imagen es segura?**

R: Sí. No es una etiqueta JavaScript, es una etiqueta de imagen.

**P: ¿Qué permisos necesita el usuario conectado?**

A: dfattraffic, dfareporting, userinfo.email

**P: ¿Cuánto tiempo puede tardar la importación de datos de gasto?**

A: hasta 6 horas

**P: ¿Cuánto tiempo puede tardar la importación de datos de publicidad?**

A: hasta 6 horas
