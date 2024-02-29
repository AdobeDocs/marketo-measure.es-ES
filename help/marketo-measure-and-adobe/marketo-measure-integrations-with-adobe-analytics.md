---
description: "[!DNL Marketo Measure] Integraciones con Adobe Analytics: [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Integraciones con [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 0%

---

# Integraciones de [!DNL Marketo Measure] con Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

La integración de Atributos del cliente B2B permite a los usuarios mutuos de [!DNL Marketo Measure] y Adobe Analytics para enriquecer su [!DNL Adobe Analytics] perfiles de usuario con valiosos metadatos derivados de [!DNL Marketo Measure] y a través de su capacidad de sincronización con CRM ([!DNL Microsoft Dynamics] y [!DNL Salesforce]). Está disponible de forma gratuita para todos los clientes que utilicen [!DNL Adobe Analytics] y [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>Debe tener suscripciones activas a ambos [!DNL Marketo Measure] y [!DNL Adobe Analytics].

## Configuración de la integración {#configuring-the-integration}

1. Cree una nueva fuente de datos de atributos del cliente en la consola del Experience Cloud. Instrucciones detalladas [se puede encontrar aquí](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=es).

   Tome nota de la siguiente información, necesaria en los pasos posteriores:

   * El ID de alias, que puede ser cualquier valor que desee que sea. Recomendamos &quot;marketomeasure_id&quot;

   * El nombre de host y las credenciales del servidor FTP (nombre de usuario y contraseña)

1. Una vez creada la fuente de datos de atributos del cliente, continúe con el proceso de configuración navegando hasta **[!UICONTROL Integraciones]** > **[!UICONTROL Conexiones]** pantalla en el [!DNL Marketo Measure] menú de administración.

1. Haga clic en **[!UICONTROL Configurar nueva conexión de Atributos del cliente]** y siga las instrucciones para configurar la integración de Atributos del cliente. La interfaz de usuario le solicita la información de ID de alias y conexión FTP que adquirió al crear el origen de atributos del cliente en la consola de servicios principales y al seleccionar el conjunto de atributos de cuenta que desea sincronizar con su [!DNL Adobe Analytics] cuenta.

   también deberá introducir su ID de organización de IMS de Adobe. Este ID se muestra en la esquina inferior derecha del Admin Console de Adobe Experience Cloud. Para obtener más ayuda para encontrar este ID, consulte con el equipo de cuenta de Adobe (su administrador de cuentas).

1. Una vez que haya terminado de crear la conexión en su [!DNL Marketo Measure] cuenta, debe volver a la consola de Experience Cloud para [validación del esquema](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en). No es necesario preocuparse por la carga del archivo FTP, [!DNL Marketo Measure] ha automatizado esa parte para usted. Todo lo que debe hacer es ir a la pantalla de esquema &quot;Ver/Editar&quot; del origen de atributos del cliente que creó en el paso 1 y decirle al Adobe cuáles son los tipos de datos para cada uno de los atributos que [!DNL Marketo Measure] ha cargado en su nombre. También puede crear nuevos nombres descriptivos para mostrar para los atributos cargados, si lo desea.

   Si ha seleccionado sincronizar atributos del objeto de cuenta de CRM, se recomienda encarecidamente que elija nuevos nombres para mostrar para ellos, como [!DNL Marketo Measure] solo rellenará los nombres de nivel de API para estos atributos, que generalmente no son compatibles con la creación de informes.

1. El último paso es configurar las Suscripciones de atributos para las aplicaciones Experience Cloud en las que desea utilizar los atributos. Puede configurar suscripciones para [!DNL Adobe Analytics] o [!DNL Adobe Target].  Más información sobre cómo hacerlo [se puede encontrar aquí](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html).

## Descripciones de atributos {#attribute-descriptions}

Al crear una nueva conexión de atributo del cliente B2B, [!DNL Marketo Measure] creará automáticamente un conjunto estándar de Atributos del cliente B2B. Estos atributos se describen en la tabla siguiente.

Además de los que se enumeran a continuación, también puede cargar cualquier atributo adjunto al objeto de cuenta en su CRM. Si hay más de una cuenta vinculada al usuario determinado, [!DNL Marketo Measure] rellena todos los valores de atributo de cuenta coincidentes en una lista delimitada por punto y coma.

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>Nombre de atributo</b></td> 
   <td><b>Descripción</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>Los nombres de cuenta asociados con el visitante web determinado. Si hay más de una cuenta vinculada al usuario determinado, [!DNL Marketo Measure] rellena todos los nombres de cuenta coincidentes en una lista delimitada por punto y coma.<br/>
   <strong>Nota:</strong> account.name es el nombre de nivel de API de Salesforce para el atributo name del objeto de cuenta. Puede elegir un nombre para mostrar mejor (por ejemplo, "Empresa") para este atributo durante el paso Validación de esquema de la configuración de integración (paso 4).</td>
  </tr>
  <tr> 
   <td>Ingresos atribuidos: ‹MODELO›</td> 
   <td>Los ingresos atribuidos a este cliente en virtud de su asociación con oportunidades ganadas cerradas en su CRM, calculados por el [!DNL Marketo Measure] motor de atribución.<br/>
   Hay uno de estos atributos para cada modelo de atribución que su [!DNL Marketo Measure] Las suscripciones de permiten (por ejemplo, "Ingresos atribuidos - Ruta completa").</td>
  </tr>
  <tr> 
   <td>Fase de canal más profunda</td> 
   <td>La fase de canal más profunda de cualquier oportunidad abierta asociada con el usuario determinado.</td>
  </tr>
  <tr> 
   <td>Abrir oportunidades</td> 
   <td>Una lista delimitada por punto y coma de los ID de oportunidad a los que está vinculado el usuario según sus datos de CRM.</td>
  </tr> 
 </tbody> 
</table>

**Una nota sobre los límites de atributos**

Los atributos que aparezcan a través de esta integración aún contarán en los límites de atributos contractuales en [!DNL Adobe Analytics] y [!DNL Adobe Target]. Solo los atributos que aparecen mediante una suscripción de atributo (paso 5 en [Configuración de la integración](#configuring-the-integration)) se descontará del límite de la aplicación suscrita.

## Preguntas frecuentes {#faqs}

**¿Cómo cambio el conjunto de atributos que deseo compartir mediante esta integración?**

Para un atributo compartido por [!DNL Marketo Measure] a su organización IMS de Adobe a través de esta integración para que sea visible y se utilice en [!DNL Adobe Analytics], debe aparecer mediante una suscripción de atributo configurada en la consola de servicios principales. Por lo tanto, si desea quitar un atributo para que ya no aparezca en [!DNL Adobe Analytics], puede conseguirlo simplemente eliminando la suscripción del atributo.

También puede eliminar la conexión de atributos del cliente B2B en [!DNL Marketo Measure] y vuelva a crearlo con el atributo que ya no desee compartir excluido de la configuración de conexión. Del mismo modo, para agregar atributos a la integración, debe eliminar la conexión existente y crear una nueva con los atributos deseados agregados a la configuración.

Teniendo en cuenta lo anterior, es muy recomendable que al configurar la conexión de atributos por primera vez, sea lo más inclusivo posible al seleccionar atributos.

**¿Cuáles son algunos casos de uso de ejemplo para esta integración?**

1. Métricas de tráfico basadas en cuentas: con el atributo de nombre de cuenta, puede crear segmentos de una o más cuentas de destino en Adobe Analytics y analizar las métricas de tráfico del sitio únicamente para el subconjunto de tráfico procedente de cuentas de destino.
1. Análisis de contenido: utilice la métrica de ingresos para analizar qué contenido del sitio resulta más atractivo para los clientes que, en última instancia, compran su producto o servicio, o para aquellos que alcanzan una fase de interés específica del canal.
1. Asistencia técnica en vivo: Proporcione a su equipo de ventas una perspectiva procesable mediante el análisis del comportamiento del sitio para los usuarios asociados con una oportunidad abierta específica en su CRM.
