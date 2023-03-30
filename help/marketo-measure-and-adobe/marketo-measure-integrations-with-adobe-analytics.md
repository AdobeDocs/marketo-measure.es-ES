---
description: "[!DNL Marketo Measure] Integraciones con Adobe Analytics: [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Integraciones con [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 0%

---

# Integraciones de [!DNL Marketo Measure] con Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

La integración de atributos del cliente B2B permite a los usuarios mutuos de [!DNL Marketo Measure] y Adobe Analytics para enriquecer su [!DNL Adobe Analytics] perfiles de usuario con metadatos valiosos derivados de [!DNL Marketo Measure] motor de atribución y a través de su capacidad de sincronización con CRM ([!DNL Microsoft Dynamics] y [!DNL Salesforce]). Está disponible de forma gratuita para todos los clientes que utilicen [!DNL Adobe Analytics] y [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>Debe tener suscripciones activas a ambos [!DNL Marketo Measure] y [!DNL Adobe Analytics].

## Configuración de la integración {#configuring-the-integration}

1. Comience creando una nueva fuente de datos de atributos del cliente en la consola del Experience Cloud. Instrucciones detalladas [se puede encontrar aquí](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   Tenga en cuenta la siguiente información, ya que la necesitará para algunos de los pasos posteriores del proceso:

   * El ID de alias, que puede ser cualquier valor que desee que sea. Recomendamos &quot;marketomeasure_id&quot;

   * El nombre de host y las credenciales del servidor FTP (nombre de usuario y contraseña)

1. Una vez creada la fuente de datos de atributos del cliente, continúe el proceso de configuración navegando hasta el **[!UICONTROL Integraciones]** > **[!UICONTROL Conexiones]** en la [!DNL Marketo Measure] menú de administración.

1. Haga clic en el **[!UICONTROL Configurar nueva conexión de atributos del cliente]** y siga las instrucciones para configurar la integración de Atributos del cliente. La interfaz de usuario le pedirá la información de ID de alias y conexión FTP que haya adquirido al crear el origen de atributos del cliente en la consola de servicios principales, así como que seleccione el conjunto de atributos de cuenta que desea sincronizar con su [!DNL Adobe Analytics] cuenta.

   También deberá introducir su ID de organización de Adobe IMS. Este ID se muestra en la esquina inferior derecha del Admin Console de Adobe Experience Cloud. Para obtener más ayuda con la búsqueda de este ID, consulte con el equipo de cuentas de Adobe (su administrador de cuentas).

1. Una vez que haya terminado de crear la conexión en su [!DNL Marketo Measure] cuenta, tendrá que volver a la consola del Experience Cloud para [validar el esquema](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). No es necesario preocuparse por la carga del archivo FTP, [!DNL Marketo Measure] ha automatizado esa parte para usted. Todo lo que debe hacer es ir a la pantalla de esquema &quot;Ver/Editar&quot; para el origen de atributos del cliente que creó en el paso 1 y decirle al Adobe cuáles son los tipos de datos para cada uno de los atributos que [!DNL Marketo Measure] ha subido en su nombre. También puede crear nuevos nombres descriptivos para la visualización de los atributos cargados, si lo desea.

   Si eligió sincronizar atributos del objeto de cuenta de CRM, es muy recomendable que elija nuevos nombres para mostrar, como [!DNL Marketo Measure] solo rellenará los nombres de nivel de API para estos atributos, que generalmente no son compatibles con los informes.

1. El último paso es configurar las Suscripciones de atributos para las aplicaciones de Experience Cloud en las que desea utilizar los atributos.  Puede configurar suscripciones para [!DNL Adobe Analytics] o [!DNL Adobe Target].  Más información sobre cómo hacerlo [se puede encontrar aquí](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## Descripciones de atributos {#attribute-descriptions}

Cuando crea una nueva conexión de atributos del cliente B2B, [!DNL Marketo Measure] creará automáticamente un conjunto estándar de atributos del cliente B2B. Estos atributos se describen en la siguiente tabla.

Además de los que se enumeran a continuación, también puede cargar cualquier atributo adjunto al objeto de cuenta en su CRM. Si hay más de una cuenta vinculada al usuario dado, [!DNL Marketo Measure] rellenará todos los valores de atributo de cuenta coincidentes en una lista delimitada por punto y coma.

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
   <td>Los nombres de cuenta asociados al visitante web dado. Si hay más de una cuenta vinculada al usuario dado, [!DNL Marketo Measure] rellenará todos los nombres de cuenta coincidentes en una lista delimitada por punto y coma.<br/>
   <strong>Nota:</strong> account.name es el nombre de nivel de API de Salesforce para el atributo name en el objeto account. Puede elegir un mejor nombre para mostrar (por ejemplo, "Empresa") para este atributo durante el paso Validación del esquema de la configuración de integración (paso 4).</td>
  </tr>
  <tr> 
   <td>Ingresos atribuidos - "MODEL" ›</td> 
   <td>Los ingresos atribuidos a este cliente en virtud de su asociación con oportunidades ganadas de forma cerrada en su CRM, calculados por la variable [!DNL Marketo Measure] motor de atribución.<br/>
   Habrá uno de estos atributos para cada modelo de atribución que su [!DNL Marketo Measure] las suscripciones permiten (por ejemplo, "Ingresos atribuidos - Ruta completa").</td>
  </tr>
  <tr> 
   <td>Etapa de canal más profunda</td> 
   <td>La etapa de canal más profunda de cualquier oportunidad abierta asociada con el usuario dado.</td>
  </tr>
  <tr> 
   <td>Abrir oportunidades</td> 
   <td>Una lista delimitada por punto y coma de los ID de oportunidad a los que está vinculado el usuario dado según sus datos CRM.</td>
  </tr> 
 </tbody> 
</table>

**Una nota sobre los límites de atributos**

Tenga en cuenta que los atributos mostrados a través de esta integración aún se contarán en sus límites de atributos contractuales en [!DNL Adobe Analytics] y [!DNL Adobe Target]. Solo los atributos que aparecen mediante una suscripción de atributos (paso 5 de [Configuración de la integración](#configuring-the-integration)) se contará con respecto a su límite para la aplicación suscrita.

## Preguntas frecuentes {#faqs}

**¿Cómo puedo cambiar el conjunto de atributos que quiero compartir a través de esta integración?**

Para que un atributo se comparta por [!DNL Marketo Measure] a su organización Adobe IMS mediante esta integración para que sea visible y se use en [!DNL Adobe Analytics], debe mostrarse mediante una suscripción de atributo configurada en la consola de servicios principales. Por lo tanto, si desea eliminar un atributo para que ya no aparezca en [!DNL Adobe Analytics], puede conseguirlo simplemente eliminando la suscripción de atributo.

También puede eliminar la conexión de Atributo del cliente B2B en [!DNL Marketo Measure] y vuelva a crearlo con el atributo que ya no desee compartir excluido de la configuración de conexión. Del mismo modo, para agregar atributos a la integración, deberá eliminar la conexión existente y crear una nueva con los atributos deseados agregados a la configuración.

En vista de lo anterior, se recomienda que, al configurar la conexión de atributos por primera vez, sea lo más inclusivo posible al seleccionar atributos.

**¿Cuáles son algunos ejemplos de casos de uso para esta integración?**

1. Métricas de tráfico basadas en cuentas: Con el atributo de nombre de cuenta, puede crear segmentos de una o varias cuentas de destino en Adobe Analytics y analizar las métricas de tráfico del sitio únicamente para el subconjunto de tráfico procedente de cuentas de destino.
1. Análisis de contenido: Utilice la métrica de ingresos para analizar qué contenido del sitio resulta más atractivo para los clientes que finalmente compran su producto o servicio, o para aquellos que llegan a una etapa de interés específica del canal.
1. Compatibilidad con el lanzamiento: Aplique a su equipo de ventas una perspectiva procesable analizando el comportamiento del sitio para los usuarios asociados con una oportunidad abierta específica en su CRM.
