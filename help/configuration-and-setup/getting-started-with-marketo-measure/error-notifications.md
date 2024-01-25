---
description: Notificaciones de error - [!DNL Marketo Measure] - Documentación del producto
title: Notificaciones de error
feature: Fundamentals
source-git-commit: 969cb2b4fb85aeb5c3a3aa21ead3eb5f4ff15ad9
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Notificaciones de error {#error-notifications}

A continuación se muestra una lista de errores que puede recibir mediante una notificación en la aplicación o por correo electrónico. Si recibe alguno de estos, siga los pasos correspondientes para la resolución de problemas. Si estos pasos no resuelven el problema, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th>Código de error</th>
      <th>Ejemplo de notificación</th>
      <th>Descripción</th>
      <th>Pasos para solucionar problemas</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Se ha producido un error durante la importación de CRM: API_DISABLED: Se han deshabilitado las llamadas de API para este usuario</td>
      <td>Se ha deshabilitado el permiso API para el usuario de Marketo Measure.</td>
      <td>Consulte la siguiente documentación de Salesforce sobre <a href="https://help.salesforce.com/s/articleView?id=sf.branded_apps_commun_api_permset.htm&amp;type=5">Cómo habilitar el acceso a la API</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Error durante la exportación de Crm: PI_LIMIT_EXCEEDED</td>
      <td>Se ha superado el límite de API de CRM (24 horas).</td>
      <td>Consulte la siguiente documentación de su CRM para obtener ayuda sobre el ajuste de las asignaciones de crédito de la API:</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>También puede ajustar los créditos CRM que utiliza Marketo Measure siguiendo los siguientes pasos:</p>
          <ul>
            <li>Vaya a Configuración → CRM → General</li>
            <li>Actualización del límite diario de la API de CRM<br/>
              <ul>
                <li><b>Nota</b>: El valor predeterminado es 100 000</li>
              </ul>
            </li>
          </ul>
          <p>
            CAPTURA DE PANTALLA
          </p>
      </td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Se ha producido un error durante la exportación de Adobe Analytics: INVALID_ADOBE_ANALYTICS_CONFIGURATION : Error: no se permite la carga. Confirme el esquema de la fuente de datos antes de cargar. Id De Fuente De Datos:1234</td>
      <td>La integración de Adobe Analytics no está configurada correctamente.</td>
      <td>Consulte los siguientes artículos de ayuda para garantizar una configuración correcta:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Integraciones de Marketo Measure con Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">Crear un origen de Atributo del cliente y cargar el archivo de datos</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>Error durante la importación del anuncio: INVALID_CURRENCY_ISO_CODE: Marketo Measure no admite la divisa XXX.
      <p>
      Error durante la importación del anuncio: INVALID_CURRENCY_ISO_CODE : Marketo Measure no admite la divisa XXX en la cuenta para 1234.</td>
      <td>Se ha encontrado una moneda no compatible.</td>
      <td>En el sistema de origen indicado en la notificación (Ad, Crm, Marketo), asegúrese de que la moneda asociada al registro tenga una moneda compatible y válida. Las monedas admitidas derivan de las normas de moneda ISO.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Error durante la exportación de Crm: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure no tiene el permiso Ver/Editar posibles clientes convertidos</td>
      <td>Consulte el siguiente documento del Experience League para obtener ayuda sobre cómo habilitar este permiso en su CRM<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">Activación del permiso para editar posibles clientes convertidos</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Error durante la importación de Crm: MISSING_FIELD_READ_PERMISSION : Tipo de entidad 'Evento': INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>A Marketo Measure le faltan permisos de lectura en un campo obligatorio.</td>
      <td>Consulte los siguientes artículos de ayuda para obtener instrucciones sobre los permisos que requiere Marketo Measure:
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATEABLE_PERMISSION</td>
      <td>Error durante la importación de Crm: MISSING_ISREPLICATEABLE_PERMISSION : Falta el permiso IsReplicateable en Campaign</td>
      <td>Este permiso es necesario en los objetos de Salesforce para que podamos mantener su Marketo Measure y Salesforce sincronizados.</td>
      <td>Póngase en contacto con el servicio de soporte técnico de Salesforce para obtener ayuda sobre el establecimiento del permiso replicable en objetos.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Error durante la importación de Crm: MISSING_OBJECT_READ_PERMISSION : Tipo de entidad 'Campaña': Código de error de CRM: MISSING_PERMISSION</td>
      <td>A Marketo Measure le faltan permisos de lectura para un objeto requerido.</td>
      <td rowspan="2">Consulte los siguientes artículos de ayuda para obtener instrucciones sobre los permisos que requiere Marketo Measure:
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>Error durante la exportación de Crm: MISSING_OBJECT_WRITE_PERMISSION : Tipo de entidad 'bizible2_Bizible_Attribution_Touchpoint': Código de error de CRM: MISSING_PERMISSION</td>
      <td>A Marketo Measure le faltan permisos de escritura en un objeto requerido.</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Error durante la importación de Crm: NULL_EMPTY_CURRENCY_ISO_CODE: El código ISO de divisa es NULL o Empty cuando MultiCurrency está habilitado para RecordId 1234
      </td>
      <td>La divisa debe ser un código de divisa ISO compatible.</td>
      <td>En el sistema de origen indicado en la notificación (Ad, Crm, Marketo), asegúrese de que la moneda asociada al registro tenga una moneda compatible y válida. Las monedas admitidas derivan de las normas de moneda ISO.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Se ha producido un error durante la importación de Crm: OPERATION_TOO_LARGE : Se necesita el permiso "Ver todos los datos" para consultar las actividades correctamente.</td>
      <td>La configuración de CRM no permite a Marketo Measure consultar un conjunto de datos lo suficientemente grande</td>
      <td>Conceda permisos de "Ver todos los datos" a Marketo Measure en el objeto designado.
      <p>
      Más información sobre el permiso "Ver todos los datos" <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">se puede encontrar aquí</a>.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Error durante la importación de Crm: UNSUPPORTED_CRM_PACKAGE_VERSION : Actualice el paquete de crm</td>
      <td>El paquete actual detectado ya no es compatible.</td>
      <td>Actualice el paquete a la versión más reciente:
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">Prácticas recomendadas</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
