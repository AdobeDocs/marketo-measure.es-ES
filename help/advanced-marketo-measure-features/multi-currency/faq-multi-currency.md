---
unique-page-id: 27656745
description: 'Preguntas más frecuentes (varias monedas): [!DNL Marketo Measure] - Documentación del producto'
title: Preguntas más frecuentes (en varias monedas)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# Preguntas más frecuentes (en varias monedas) {#faq-multi-currency}

**¿Cómo sé qué bit de funciones habilitar?**

Tenga en cuenta que hay dos bits de función diferentes para esta función. Ambas se encuentran en la pestaña General de la sección CRM en Configuración: Monedas Múltiples y Monedas Avanzadas. Si el cliente utiliza más de una moneda única, se deben habilitar múltiples monedas, mientras que la función adicional bit Advanced Currencies se puede habilitar si el cliente utiliza [!DNL Salesforce]La función &quot;Administración avanzada de divisas&quot; de permite al usuario establecer un intervalo basado en el tiempo para las tasas de conversión.

Desafortunadamente, no sabemos cuándo un cliente cambia entre Simple o Advanced si Advanced ya está activado. Debido a ello, el cliente debe mantener la configuración de monedas avanzadas alineada manualmente con su configuración de CRM. Esto debería ser evidente para el cliente si las conversiones son incorrectas, lo que significa que no sabíamos qué nivel de conversión aplicar.

**¿Por qué mi cuenta de anuncios me da un mensaje de advertencia?**

Mostraremos un mensaje de advertencia junto a la cuenta de la publicidad que pueda tener monedas que vengan de una moneda no compatible. Si esto sucede, los tableros contendrán mosaicos con un mensaje &quot;Monedas mixtas&quot;. Le recomendamos que trabaje con su administrador de CRM para asegurarse de que esta moneda desconocida contenga una conversión en su CRM.

**¿Qué significa &quot;Monedas mixtas&quot; en mi mosaico de tablero?**

Si tiene un mosaico que tiene un mensaje &quot;Monedas mixtas&quot; en la parte inferior, significa que hemos importado algunos costes que están asignados a una moneda que no reconocemos. Como todas nuestras conversiones deben proceder de CRM con una tasa de conversión real, significa que su CRM no tiene esta moneda. Le recomendamos que trabaje con su administrador de CRM para asegurarse de que esta moneda desconocida contenga una conversión en su CRM.

**¿Cómo puedo agregar una nueva moneda o tasa de conversión?**

La declaración de una nueva moneda o tasa de conversión solo se puede realizar en [!DNL Salesforce] o [!DNL Dynamics] de modo que estos valores solo tengan una única fuente de verdad. Una vez que se detecta una nueva moneda o tasa de conversión, [!DNL Marketo Measure] descargaré eso y lo pondremos a tu disposición. No ofrecemos un área para introducir estas tarifas.

**La moneda no se muestra en el formato correcto. ¿Cómo puedo cambiar esto?**

Entendemos que algunos países tienen una forma diferente de aplicar formato a las cantidades (por ejemplo, 1.234,00, 1.234, 1.234). Pero introducimos otro nivel de complejidad si tenemos que determinar no sólo la moneda de un usuario, sino su país de origen, ya que los diferentes países y monedas pueden manejarse de manera diferente. El formato coherente que hemos elegido es 1.234,00. Esto no se puede cambiar.

**¿Por qué no puede mostrar el símbolo de moneda de mi moneda seleccionada?**

[!DNL Salesforce] y [!DNL Dynamics] muestre sus cantidades con el código de conversión de 3 letras. Por lo tanto, para mantener la coherencia, las cantidades convertidas también se muestran con el código de conversión de 3 letras y no con el símbolo .

**¿Qué verá mi cliente si no tiene habilitada la multimoneda?**

Si el cliente no tiene la función multimoneda, se usará de forma predeterminada la configuración regional de moneda de CRM y se cambiarán todos los códigos ISO que muestran su gasto e ingresos en la moneda corporativa. Si esto es incorrecto y el cliente tiene un uso mixto de la moneda, la solución sería actualizar para obtener la función multimoneda.

**¿Cómo afecta esta función a los informes basados en puntos de contacto en CRM?**

Para [!DNL Dynamics] y [!DNL Salesforce] los clientes que solo utilizan la administración de moneda básica (no avanzada), las cantidades de ingresos de touchpoint deben convertirse correctamente, de modo que los informes de CRM deberían funcionar según lo esperado.

Desafortunadamente, hay algunos matices en cómo esto funciona para los usuarios de [!DNL Salesforce] Gestión de divisas avanzada, debido a una limitación de larga data de [!DNL Salesforce]. La respuesta corta a &quot;qué hacemos en este caso&quot; es que convertimos importes de ingresos utilizando las tasas fijas definidas en la pestaña básica (es decir, no avanzada) &quot;Administrar monedas&quot;. En otras palabras, ignoramos por completo los tipos de cambio con fecha a pesar de que el cliente ha definido tipos de cambio con fecha.

Para el lector interesado, por eso funciona de esta manera. Nuestros puntos de contacto utilizan campos de fórmula para calcular los ingresos (derivados de la cantidad de oportunidad asociada). [!DNL Salesforce] nativamente admite la conversión de moneda para estos cálculos de fórmula, pero solo para su sabor básico de compatibilidad con monedas. Para nosotros es imposible definir un campo de fórmula que haga referencia a los tipos de cambio con fecha. [!DNL Salesforce] simplemente no admite esa capacidad, por lo que no tenemos forma de hacer referencia a las tasas con fecha en nuestros cálculos de ingresos a pesar de que esas tasas con fecha de vencimiento existen en [!DNL Salesforce] (parece una locura, pero así es como funciona).

**Si mi cliente ha utilizado un flujo de trabajo para rellenar un campo convertido, ¿cómo debe utilizar este campo para avanzar?**

Dado que nuestra oferta ahora gestiona las conversiones para el cliente, recomendamos que elimine los flujos de trabajo y el campo personalizado y nos permita importar su valor de Importe sin procesar.
