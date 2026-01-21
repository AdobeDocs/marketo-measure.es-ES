---
unique-page-id: 27656745
description: Preguntas más frecuentes (multidivisa) - [!DNL Marketo Measure]
title: Preguntas frecuentes (multidivisa)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# Preguntas frecuentes (multidivisa) {#faq-multi-currency}

**¿Cómo sé qué bit de característica habilitar?**

Tenga en cuenta que hay dos bits de funciones diferentes para esta función. Ambos se encuentran en la ficha [!UICONTROL General] de la sección CRM en Configuración: Varias monedas y Monedas avanzadas. Se deben habilitar varias monedas si el cliente utiliza más de una sola moneda, mientras que la característica adicional bit Monedas avanzadas se puede habilitar si el cliente usa la característica &quot;Administración avanzada de monedas&quot; de [!DNL Salesforce], en la que el usuario puede establecer un intervalo basado en el tiempo para las tasas de conversión.

Marketo Measure extrae automáticamente la configuración de moneda del CRM del cliente. Ya no es necesaria la configuración manual en Marketo Measure para que coincida con el CRM. La configuración de moneda se puede encontrar en la página &quot;General&quot; en &quot;CRM&quot;.

**¿Por qué mi cuenta de anuncios me está enviando un mensaje de advertencia?**

Mostraremos un mensaje de advertencia junto a su cuenta de anuncios que pueden tener monedas procedentes de una moneda no admitida. Si esto sucede, los paneles contendrán mosaicos con un mensaje &quot;Divisas mixtas&quot;. Le recomendamos que trabaje con su administrador de CRM para asegurarse de que esta moneda desconocida contenga una conversión en su CRM.

**¿Qué significa &quot;Divisas mixtas&quot; en el mosaico de mi panel?**

Si tiene un mosaico con el mensaje &quot;Divisas mixtas&quot; en la parte inferior, significa que hemos importado algunos costes asignados a una moneda que no reconocemos. Dado que todas nuestras conversiones deben proceder de CRM con una tasa de conversión real, significa que a su CRM le falta esta moneda. Le recomendamos que trabaje con su administrador de CRM para asegurarse de que esta moneda desconocida contenga una conversión en su CRM.

**¿Cómo puedo corregir el error &quot;Divisas mixtas&quot; causado por monedas no válidas?**

Nuestro sistema actualiza las monedas no reconocidas a &quot;XXX&quot;. Para excluir oportunidades con monedas no válidas, cree una regla de supresión en la página Configuración de punto de contacto para evitar puntos de contacto para oportunidades con la moneda &quot;XXX&quot;. Una vez procesados, informaremos solo sobre monedas conocidas.

**¿Cómo puedo agregar una nueva moneda o tasa de conversión?**

La declaración de una nueva moneda o tasa de conversión sólo se puede realizar en [!DNL Salesforce] o [!DNL Dynamics], de modo que sólo haya una única fuente fiable para estos valores. Una vez que se detecte una nueva moneda o tasa de conversión, [!DNL Marketo Measure] descargará esa moneda y la pondrá a su disposición. No ofrecemos un área para ingresar estas tarifas.

**La moneda no se muestra en el formato correcto. ¿Cómo puedo cambiar esto?**

Entendemos que algunos países tienen una forma diferente de formatear los importes (por ejemplo, 1.234,00, 1,234, 1.234). Pero introducimos otro nivel de complejidad si no solo tenemos que determinar la moneda de un usuario, sino su país de origen, ya que diferentes países y monedas pueden manejarse de manera diferente. El formato coherente que hemos elegido es 1.234,00. Esto no se puede cambiar.

**¿Por qué no puede mostrar el símbolo de moneda de mi moneda seleccionada?**

[!DNL Salesforce] y [!DNL Dynamics] muestran sus importes con el código de conversión de 3 letras. Por lo tanto, para mantener la coherencia, las cantidades convertidas también se muestran con el código de conversión de 3 letras y no con el símbolo.

**¿Qué verá mi cliente si no tiene habilitada la opción de divisas múltiples?**

Si el cliente no tiene la función multidivisa, se usará de forma predeterminada su configuración regional de moneda del CRM y se cambiarán todos los códigos ISO que muestren su gasto e ingresos en la moneda corporativa. Si esto es incorrecto y el cliente tiene un uso mixto de la moneda, la solución sería actualizar para obtener la función de múltiples monedas.

**¿Cómo afecta esta característica a los informes basados en puntos de contacto en CRM?**

Para los clientes de [!DNL Dynamics] y [!DNL Salesforce] que solo usan la administración básica (no avanzada) de monedas, las cantidades de ingresos de los puntos de contacto deben convertirse correctamente, de modo que los informes de CRM deban funcionar según lo esperado.

Desafortunadamente, hay algunos matices en la forma en que esto funciona para los usuarios de [!DNL Salesforce] Advanced Currency Management, debido a una antigua limitación de [!DNL Salesforce]. La respuesta corta a &quot;qué hacemos en este caso&quot; es que convertimos los importes de los ingresos utilizando las tarifas planas definidas en la pestaña básica (es decir, no avanzada) &quot;Administrar monedas&quot;. En otras palabras, ignoramos por completo los tipos de cambio con fecha a pesar del hecho de que el cliente ha definido tipos de cambio con fecha.

Para el lector interesado, he aquí la razón por la que funciona de esta manera. Nuestros puntos de contacto utilizan campos de fórmula para calcular los ingresos (derivados de la cantidad de oportunidad asociada). [!DNL Salesforce] admite de forma nativa la conversión de moneda para estos cálculos de fórmula, pero solo por su sabor básico de compatibilidad con moneda. Es imposible para nosotros definir un campo de fórmula que haga referencia a los tipos de cambio antiguos. [!DNL Salesforce] simplemente no admite esa capacidad, por lo que no tenemos forma de hacer referencia a las tasas con fecha en nuestros cálculos de ingresos a pesar de que esas tasas con fecha existen en [!DNL Salesforce] (suena loco, pero así es como funciona).

**Si mi cliente utilizó un flujo de trabajo para rellenar un campo convertido, ¿cómo debería utilizarlo en adelante?**

Dado que nuestra oferta ahora gestiona las conversiones para el cliente, recomendamos que elimine los flujos de trabajo y el campo personalizado y nos permita importar su valor de cantidad sin procesar.

>[!MORELIKETHIS]
>
>[Notificaciones de errores](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
