---
unique-page-id: 18874708
description: Atribución de actividades de Salesforce - [!DNL Marketo Measure] - Documentación del producto
title: Atribución de actividades de Salesforce
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 1%

---

# Atribución de actividades de Salesforce {#salesforce-activities-attribution}

El [!DNL Marketo Measure] La integración de actividades de Salesforce traerá registros de tareas y eventos específicos al modelo de atribución. Empiece a rastrear cosas como correos electrónicos de ventas o llamadas telefónicas de ventas que no recibían el crédito debido. Para configurar la regla de actividades, debe ir a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. A partir de ahí, vaya al **[!UICONTROL Configuración]** y haga clic en la pestaña **[!UICONTROL Actividades]** pestaña.

¡Está a punto de hacer muy feliz a su equipo de ventas! Permítanos guiarle a través de un tutorial rápido.

![](assets/1.png)

Para empezar, estamos introduciendo un nuevo concepto llamado [!DNL Marketo Measure] Campaña. Para cada regla que defina, va a agrupar los registros en una [!DNL Marketo Measure] Campaña que puede nombrar. Añada varias campañas según sea necesario. Imagine medir la eficacia de una campaña de ventas salientes junto a una campaña de medios de pago.

Vas a usar esto. [!DNL Marketo Measure] Nombre de la campaña para decirnos a qué canal debe asignarse. Si todavía está pensando en las ventas salientes, quizás todas las campañas de ventas salientes deban sentarse en un canal BDR.

Familiarícese con esta jerarquía:

* Canal
   * Subcanal
      * Campaña
      * Campaña
   * Subcanal
      * Campaña

>[!TIP]
>
>Si desea establecer una campaña única para cada representante de ventas, por ejemplo, utilice nuestros parámetros de reemplazo dinámico para rellenar el [!DNL Marketo Measure] Nombre de campaña. En el mismo ejemplo, puede introducir `"Outbound Sales - {AssignedTo}"` y lo transformaremos en algo como... `"Outbound Sales - Jill"` o `"Outbound Sales - Jack."` ¡No tienes idea de cuánto tiempo te acabamos de salvar!

![](assets/2.png)

Una vez que [!DNL Marketo Measure] El nombre de la campaña está establecido, es hora de configurar las reglas de actividad.

Las reglas actúan como un filtro para decirnos qué registros son aptos para la atribución. Imagine que está creando un informe en su CRM con una lógica similar para generar ese informe. Tiene la flexibilidad de utilizar una combinación de instrucciones y/o y varios operadores como coincide con cualquiera, contiene, comienza con, termina con, es igual a, etc. Defina las instrucciones &quot;y&quot; dentro de una regla con caja o las instrucciones &quot;o&quot; de capa fuera de la caja.

![](assets/3.png)

>[!NOTE]
>
>Los campos de fórmula no se pueden utilizar dentro de las reglas y no aparecerán en la lista de selección. Como las fórmulas calculan en segundo plano y no modifican un registro, [!DNL Marketo Measure] no puede detectar si un registro se ajusta o no a una regla.
>
>Asegúrese de utilizar valores correctos para campos de ID como CrmEvent.CreatedById. [!DNL Salesforce IDs] tienen 18 caracteres (por ejemplo, 0054H000007WmrfQAC).

Por último, vamos a elegir uno de los campos de fecha y hora para utilizarlo como Fecha de contacto del comprador. Se pueden seleccionar los campos estándar y personalizados.

>[!TIP]
>
>Con la instalación del paquete, [!DNL Marketo Measure] incluye un campo Fecha del punto de contacto del comprador personalizado en el registro de actividad. Si desea utilizar una fecha dinámica, como la fecha en la que cambia el estado, es posible utilizar un flujo de trabajo de CRM para establecer la &quot;Fecha de punto de contacto del comprador&quot; y, a continuación, seleccionar la Fecha de punto de contacto del comprador aquí en este paso.

![](assets/4.png)

No olvide establecer reglas diferentes para las Tareas o los Eventos. Necesitará saber qué objeto utiliza su equipo de ventas para registrar sus actividades.

![](assets/5.png)

Probablemente quiera colocar estos nuevos puntos de contacto en su ubicación apropiada [Canal de marketing](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target="_blank"}. Puede hacerlo definiendo el canal con su nueva asignación de campaña que acaba de crear. Tal vez cree una nueva fila para el canal BDR en la que la campaña comience por Saliente.

>[!TIP]
>
>Al añadir una definición de canal, utilice valores de comodines, una forma más sencilla de indicar a operadores como:
>
>empieza por ( saliente&#42; )
>
>contiene ( &#42;Saliente&#42; )
>
>termina por ( &#42;Saliente )
>
>Ningún comodín significa básicamente &quot;es igual a&quot;, por lo que asegúrese de utilizarlos según sea necesario.

| **Operador** | **Caso de uso** |
|---|---|
| Is Equal To | Valor único: coincidencia exacta |
| Contiene | Valor único: contiene un valor |
| Coincide con Cualquiera | Varios valores: coincidencia exacta |
| Coincide Con Cualquiera (Contiene) | Varios valores: &#42;valor&#42;, &#42;valor, &#42;valor&#42; |

![](assets/6.png)

Y por último, pero no menos importante, tiene la opción de ingresar costos para sus nuevos canales. Nuestro [Carga de gasto de marketing](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} permite introducir el gasto en los niveles de canal, subcanal o campaña. Con su nuevo [!DNL Marketo Measure] Campañas, puede añadir esos costes relacionados por mes y luego ver el ROI de cada campaña.

![](assets/7.png)

>[!MORELIKETHIS]
>
>[Preguntas frecuentes sobre Attribution de actividad](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
