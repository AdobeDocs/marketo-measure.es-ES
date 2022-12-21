---
description: Métodos de administración de gastos - [!DNL Marketo Measure] - Documentación del producto
title: Métodos de administración de gastos
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Métodos de administración de gastos {#spend-management-methods}

Los datos de gasto son clave para el éxito de los informes de ROI con [!DNL Marketo Measure]. Para disponer de informes de ROI precisos y completos en todos sus canales y subcanales, debe asegurarse de que dispone de los datos de gasto adecuados en los que [!DNL Marketo Measure].

Existen tres maneras de obtener los datos de gasto en [!DNL Marketo Measure]. Cada método está diseñado para extraer datos de gastos de entradas de datos concretas.

**1) Cuentas conectadas a API**

Cualquier cuenta de publicidad a la que se haya conectado [!DNL Marketo Measure] a través de una API, se hará que se invierta automáticamente en [!DNL Marketo Measure] para informes de ROI. Para comprobar qué cuentas se han conectado y, por lo tanto, extraer gastos, vaya a [!DNL Marketo Measure] Aplicación y seleccione [!UICONTROL Conexiones] en la pestaña [!UICONTROL Integraciones] para obtener más información. Para obtener más información sobre cómo configurar las conexiones de API, consulte nuestra [Plataformas de publicidad integradas](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) artículo.

**2) Sincronización de costes de CRM Campaign**

Cada [!DNL Marketo Measure] la cuenta tiene acceso a una función denominada [Sincronizar los costes de campaña de CRM](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). De forma predeterminada, este bit de función está establecido en &quot;No&quot; pero se puede activar en cualquier momento.

![](assets/spend-management-methods-1.png)

Una vez habilitada, esta función extraerá automáticamente el gasto de cualquier campaña o programa de CRM que cumpla los siguientes criterios

i. [!DNL Marketo Measure] busca ver si la campaña/programa está creando puntos de contacto, ya sea a partir de una coincidencia [Regla de sincronización de campañas](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) que se creó o una coincidencia [Regla de sincronización de programas](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) que se creó, o bien la variable [Habilitar el valor de Touchpoints del comprador](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) es &quot;Incluir todos los miembros de campaña&quot; o &quot;Incluir los miembros de campaña &quot;Respondidos&quot;.&quot;

ii. Se debe rellenar una fecha de inicio en la campaña o el programa

iii. Las fechas de finalización también deben rellenarse en la campaña o el programa

iv. Por último, se debe especificar un Coste real (para campañas en SFDC) o un Coste de período (para programas en Marketo).

**3) Carga manual de costes**

Este método le permite [cargar manualmente los datos de gasto](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) para los canales y subcanales que no están cubiertos por las cuentas conectadas de API o la sincronización de costes de CRM Campaign. Vaya a la sección Gasto en marketing de su [!DNL Marketo Measure] , puede cargar datos de gastos a través de un archivo CSV para cualquiera de sus canales.

Los clientes pueden utilizar una combinación de estos tres métodos para administrar su gasto y dependerán de la configuración específica del [!DNL Marketo Measure]. Porque hay tres métodos para importar el gasto en [!DNL Marketo Measure], recomendamos encarecidamente que use su tablero de gasto de marketing ubicado en Discover para obtener una vista completa de todos los datos de gasto. Este tablero es el único lugar donde podrá ver todos sus canales y el gasto asociado. La tarjeta de gasto de marketing puede ayudarle a identificar rápidamente dónde pueden existir lagunas en los datos de gasto y cómo puede mejorar los informes de ROI.
