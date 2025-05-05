---
unique-page-id: 18874708
description: Atribución de actividades de Salesforce - [!DNL Marketo Measure]
title: Atribución de actividades de Salesforce
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 1%

---

# Atribución de actividades de Salesforce {#salesforce-activities-attribution}

La integración de actividades de Salesforce [!DNL Marketo Measure] incorpora registros de tareas y eventos específicos en el modelo de atribución. Empiece a realizar el seguimiento de elementos como correos electrónicos de ventas o llamadas telefónicas de ventas que no recibían el crédito debido. Para configurar la regla de actividades, ve a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Desde allí, ve a la ficha **[!UICONTROL Configuración]** y haz clic en la ficha **[!UICONTROL Actividades]**.

![](assets/1.png)

>[!AVAILABILITY]
>
>Esta función solo está habilitada para clientes de nivel 2. Para solicitar un nivel de cuenta superior, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas).

Para empezar, presentamos un nuevo concepto llamado Campaña [!DNL Marketo Measure]. Para cada regla que defina, va a agrupar los registros en una [!DNL Marketo Measure] campaña a la que pueda asignar un nombre. Añada varias campañas según sea necesario. Imagine medir la eficacia de una campaña de ventas salientes junto a una campaña de medios de pago.

Va a usar este nombre de campaña de [!DNL Marketo Measure] para indicarnos a qué canal debe asignarse. Si todavía está pensando en las ventas salientes, quizás todas las campañas de ventas salientes deban sentarse en un canal BDR.

Familiarícese con esta jerarquía:

* Canal
   * Subcanal
      * Campaña
      * Campaña
   * Subcanal
      * Campaña

>[!TIP]
>
>Si desea establecer una campaña única para cada representante de ventas, por ejemplo, use parámetros de reemplazo dinámico para rellenar el nombre de campaña [!DNL Marketo Measure]. En el mismo ejemplo, puede escribir `"Outbound Sales - {AssignedTo}"` y lo cambia a algo así como `"Outbound Sales - Jill"` o `"Outbound Sales - Jack."`

![](assets/2.png)

Una vez establecido el nombre de campaña de [!DNL Marketo Measure], es hora de configurar las reglas de actividad.

Las reglas actúan como un filtro para decirnos qué registros son aptos para la atribución. Imagine que está creando un informe en su CRM con una lógica similar para generar ese informe. Tiene la flexibilidad de usar una combinación de instrucciones y/o y varios operadores como `matches any`, `contains`, `starts with`, `ends with`, `is equal to`. Defina `and` instrucciones dentro de una regla con caja o instrucciones de capa `or` fuera de la caja.

![](assets/3.png)

>[!NOTE]
>
>Los campos de fórmula no se pueden utilizar dentro de las reglas y no aparecerán en la lista de selección. Dado que las fórmulas calculan en segundo plano y no modifican un registro, [!DNL Marketo Measure] no puede detectar si un registro se ajusta o no a una regla.
>
>Asegúrese de utilizar valores correctos para campos de ID como CrmEvent.CreatedById. [!DNL Salesforce IDs] tiene 18 caracteres ( 0054H000007WmrfQAC).

Por último, elija uno de los campos de fecha y hora para utilizarlo como Buyer Touchpoint Date. Se pueden seleccionar los campos estándar y personalizados.

>[!TIP]
>
>Con la instalación del paquete, [!DNL Marketo Measure] incluye un campo Fecha de Buyer Touchpoint personalizado en el registro de actividad. Si desea utilizar una fecha dinámica, como la fecha en la que cambia el estado, es posible utilizar un flujo de trabajo de CRM para establecer la &quot;Fecha de Buyer Touchpoint&quot; y, a continuación, seleccionar la Fecha de Buyer Touchpoint aquí en este paso.

![](assets/4.png)

No olvide establecer reglas diferentes para Tareas o Eventos. Debe saber qué objeto utiliza su equipo de ventas para registrar sus actividades.

![](assets/5.png)

Probablemente quiera colocar estos nuevos puntos de contacto en su [canal de mercadotecnia](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target="_blank"} correspondiente. Para ello, defina el Canal con su nueva asignación de Campaña que acaba de crear.

>[!TIP]
>
>Al añadir una definición de canal, utilice valores comodín, una forma más sencilla de indicar a operadores como:
>
>empieza por ( saliente&#42; )
>
>contiene ( &#42;saliente&#42; )
>
>termina por ( &#42;saliente )
>
>Ningún comodín significa básicamente &quot;es igual a&quot;, por lo que asegúrese de utilizarlos según sea necesario.

| **Operador** | **Caso de uso** |
|---|---|
| Is Equal To | Valor único: coincidencia exacta |
| Contains | Valor único: contiene un valor |
| Coincide con Cualquiera | Varios valores: coincidencia exacta |
| Coincide Con Cualquiera (Contiene) | Varios valores: &#42;value&#42;, &#42;value, &#42;value&#42; |

![](assets/6.png)

Y por último, pero no menos importante, tiene la opción de ingresar costos para sus nuevos canales. La [carga de gasto en mercadotecnia](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} le permite ingresar su gasto a nivel de canal, subcanal o campaña. Con sus nuevas [!DNL Marketo Measure] campañas, puede agregar esos costos relacionados por mes y luego ver el ROI de cada campaña.

![](assets/7.png)

>[!MORELIKETHIS]
>
>[Preguntas frecuentes sobre la atribución de actividades](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
