---
unique-page-id: 18874660
description: 'Preguntas más frecuentes: [!DNL Marketo Measure] - Documentación del producto'
title: Preguntas frecuentes
exl-id: f1896bf8-2216-427e-ac3e-98d87efede76
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 0%

---

# Preguntas frecuentes {#faq}

[!DNL Marketo Measure Discover]: Preguntas más frecuentes.

**¿Cómo se guardan los filtros en un informe?**

Como hoy, los resultados de la consulta se guardan en la dirección URL y se pueden guardar o compartir con la dirección URL copiada.

**¿Cómo utilizo intervalos de fechas preconfigurados como Último año o Trimestre actual?**

Ahora, en lugar de usar intervalos de fechas preconfigurados, se ha añadido la flexibilidad de fechas. Puede establecer Último año, pero tiene la opción de seleccionar Último año, que es el último 365 días desde hoy o Último año completo, que es el último año completo del 1/1 al 31/12. Otros usos buenos del nuevo selector de fechas es establecer un intervalo de fechas relativo, que tenderá a proporcionar un intervalo de tiempo móvil para una fecha móvil.

**¿Cómo obtengo datos de CPL o CPC?**

Estas métricas solo se encuentran en el panel de medios de pago.

**¿Por qué no muestra Vistas de página en el panel Crecimiento?**

Una de las características del panel Crecimiento es que no puede agrupar los gráficos de tendencias por una dimensión, como Canal o Campaña. No tenemos esos datos disponibles en el nivel de vista de página porque las vistas de página no siempre tienen una fuente como Canal o Campaña porque se producen en mitad de las visitas web. Utilice los medios de pago o el tráfico web para ver los datos de vistas de página.

**Cuando cambio la agrupación, los totales no siempre equivalen a la misma cantidad. ¿Por qué?**

Los valores no existen para cada jerarquía de datos porque la jerarquía no siempre es un flujo de corte claro. Por ejemplo, tanto si los costes se están autonotificando como si se están importando desde un proveedor de anuncios, el coste total para el Canal 1 podría ser de 10 000 dólares, pero por campaña individual, solo se notificó un total de 5 500 dólares, por lo que cuando la agrupación cambie entre Canal y Campaña, los totales variarán.

**¿Qué es &quot;coincide con un atributo del usuario&quot; en los operadores de filtro?**

Los atributos de usuario se aplican a usuarios como el ID empresarial, el nombre o los apellidos, pero como los usuarios son usted (nuestros clientes) y no sus clientes, los atributos de usuario no se pueden usar en la variable [!DNL Marketo Measure Discover] experiencia. Por favor, siéntase libre de ignorar esta opción. Estamos trabajando en una mejor experiencia de filtro personalizado que eliminará los filtros que no se aplican a nuestros clientes.

**¿Cómo es que algunos intervalos de fechas predeterminados pasan por el primero del mes siguiente?**

Aunque el intervalo de fechas no siempre es intuitivo, la interfaz de usuario del filtro predeterminado tiene el texto &quot;antes&quot; que corresponde a la fecha de finalización, por lo que esto debería ayudarle a recordar que la fecha de finalización que utilice debe estar 1 día fuera del intervalo deseado.

**¿Qué modelo de atribución se utiliza para posibles clientes y contactos?**

Los puntos de contacto del comprador asignados a Posibles clientes y contactos se miden hasta el contacto de Creación de posibles clientes, por lo que se recomiendan el modelo de Primer toque, Creación de posibles clientes y Forma de U. Si cambia el Modelo de atribución a Forma W o Ruta completa, automáticamente aplicamos un modelo en Forma de U para Posibles clientes y contactos.

**¿Por qué mis mosaicos Visitas, Visitas únicas y Forms están en blanco en el panel Crecimiento?**

Si estos mosaicos aparecen como 0 o en blanco en la vista, significa que los mosaicos no se aprovisionan en la cuenta. Póngase en contacto con el administrador de éxito si tiene alguna pregunta al respecto.

**En el caso de los posibles clientes a lo largo del tiempo y los contactos a lo largo del tiempo, ¿cuál es el recuento al que se hace referencia?**

Utiliza los recuentos de puntos de contacto, distribuidos por el Modelo de atribución que seleccione. Será el total de posibles clientes y recuentos distribuidos a lo largo del tiempo. No es un recuento único.

**¿El gráfico de direcciones URL de formulario por canal en Marketing de contenido muestra visitas web o rellenos de formulario?**

Solo se rastrean rellenos de formulario.

**¿Cuál es el beneficio de Discover sobre Measure?**

[!DNL Marketo Measure Discover] proporciona una mejor funcionalidad, como obtención de detalles y un mejor filtrado, como subcanales y canales. También estamos poniendo fin a la medida en algún momento en 2019.

**En la medida, pude filtrar por grupo de anuncios y cuenta cuando se filtraba a cuentas de publicidad, ¿cómo puedo ver esto en Discover?**

Esto solo estará disponible con el Media Board de pago.

**¿En qué se diferencia el canal de cohorte del canal de pasaporte?**

El embudo de cohorte le permite observar la tasa de conversión del canal de ventas, midiendo el impacto entre etapas. Puede seleccionar la fase que desea medir desde los filtros, lo que le permitirá ver la tasa de conversión desde esa fase a todas las etapas posteriores. La tarjeta de Pasaporte muestra todos los posibles clientes/contactos y oportunidades que han pasado por cada etapa de la canalización en un plazo determinado.

**¿Cómo se determina el contenido del tablero Medios pagados?**

En cada uno de los mosaicos del tablero, hemos agregado un filtro para incluir solo datos donde tenemos un proveedor de publicidad conocido de Facebook, Google, Bing, LinkedIn o Doubleclick, ya que nuestra integración nos permite extraer los datos de la publicidad de esas fuentes. Además, agregamos una coincidencia de nombres confusos a Canales y Subcanales para visualización, Búsqueda paga, Social pagado, PPC, SEM, Móvil pagado, Twitter pagado, Anuncio, Terminus, Lógica de Madison, Madisonlogic y Demandbase.

**¿Cuál es la diferencia entre visitas y visitas únicas?**

Las visitas únicas son un subconjunto de visitas. Mientras que las visitas son un recuento de cada visita al sitio, las visitas únicas son cookies únicas de esas visitas al sitio. Una persona puede contabilizar varias visitas únicas si regresa con un identificador de cookie diferente.

**¿Son los touchpoint contables el recuento de Touchpoints del comprador o de puntos de contacto de atribución del comprador?**

Es un recuento de lo que consideramos puntos de contacto &quot;sin procesar&quot;, o &quot;puntos de contacto del usuario&quot;, donde es un agregado de ambos, además de los toques que no resultaron en un punto de contacto en el posible cliente/contacto u oportunidad.

**Cuando filtro por dirección URL, ¿por qué los mosaicos Costo por solo muestran 0,00 dólares?**

Este es el comportamiento esperado debido al hecho de que no tenemos los costes segmentados por dirección URL, por lo que no es aplicable en ese escenario.

**¿Por qué no aparecen todas las opciones de Segmento para mis filtros de Categoría?**

En el filtro Segmentos solo se mostrarán los segmentos que tengan registros válidos asignados a ellos. Por ejemplo, si no hay registros con el segmento &quot;Otro&quot;, entonces &quot;Otro&quot; no aparecerá como opción.

**Does [!DNL Marketo Measure Discover] ¿admite el conjunto de caracteres GB18030?**

Discover utiliza herramientas de terceros y no admite el conjunto de caracteres GB18030 en este momento.

**Al cargar Discover, ¿por qué veo un error 401 que indica &quot;No está autenticado para ver esta página&quot;?**

[!DNL Marketo Measure Discover] requiere cookies de terceros para que se muestren correctamente. Para usar Discover, habilite las cookies de terceros en el explorador y actualice la página.

>[!NOTE]
>
>Algunos exploradores, incluido Chrome en Incognito, deshabilitan las cookies de terceros de forma predeterminada.

![](assets/faq-1.png)