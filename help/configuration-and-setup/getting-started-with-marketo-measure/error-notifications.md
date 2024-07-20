---
description: Notificaciones de error - [!DNL Marketo Measure]
title: Notificaciones de errores
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 20f886a0c6f448956ad2fda2d21a25f8d9a5a6af
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 30%

---

# Notificaciones de errores {#error-notifications}

A continuación se muestra una lista de errores que puede recibir mediante una notificación en la aplicación o por correo electrónico. Si recibe alguno de estos, siga los pasos correspondientes para la resolución de problemas. Si estos pasos no resuelven el problema, póngase en contacto con el [equipo de soporte de Marketo](https://nation.marketo.com/t5/support/ct-p/Support).

Para ver el mensaje de notificación completo en [!DNL Marketo Measure], haga clic en **Ver todo** en la parte inferior de la ficha Notificaciones.

![](assets/error-notifications-1.png)

<table>
  <tbody>
    <tr>
      <th style="width:31%">Código de error</th>
      <th style="width:23%">Ejemplo de notificación</th>
      <th style="width:23%">Descripción</th>
      <th style="width:23%">Pasos para la solución de problemas</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Se ha producido un error durante la importación de CRM: API_DISABLED: Se han deshabilitado las llamadas de la API para este usuario</td>
      <td>Se ha deshabilitado el permiso de la API para el usuario de Marketo Measure.</td>
      <td>Consulte la siguiente documentación de Salesforce sobre <a href="https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.branded_apps_commun_api_permset.htm&amp;type=5">cómo habilitar el acceso a la API</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Error durante la exportación de CRM: PI_LIMIT_EXCEEDED</td>
      <td>Se ha superado el límite de la API de CRM (24 horas).</td>
      <td>Consulte la siguiente documentación de su CRM para obtener ayuda sobre el ajuste de las asignaciones de crédito de la API:</p>
          <ul>
            <li><a href="https://learn.microsoft.com/es-es/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm?lang=es">Salesforce</a>
            </li>
          </ul>
          <p>También puede ajustar los créditos CRM que utiliza Marketo Measure con los siguientes pasos:</p>
          <ul>
            <li>Vaya a <b>Configuración</b> &gt; <b>CRM</b> &gt; <b>General</b></li>
            <li>Actualización del límite diario de la API de CRM<br/>
              <ul>
                <li><b>Nota: El valor predeterminado es 100 000</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-2.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_DÉCLENCHEUR</td>
      <td>Se ha producido un error durante la exportación de Crm: CANNOT_EXECUTE_FLOW_DÉCLENCHEUR : Tipo de entidad 'Contacto'. Proporcione estos detalles al administrador de Salesforce.
Límite superado
Usted o su organización han superado el límite máximo de esta función. ID de error: 123456</td>
      <td>El registro no se puede guardar porque no cumple una regla de flujo de déclencheur configurada en la organización de Salesforce.</td>
      <td>Revise todos los detalles del mensaje de notificación y los déclencheur de flujo en la organización de Salesforce.
La documentación de Salesforce sobre los déclencheur de flujo <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated"> se encuentra aquí</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>Error durante la exportación de Crm: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Tipo de entidad 'Posible cliente': Código de error de CRM: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, Mensaje de error de CRM: System.LimitException: Se ha superado el límite de tiempo de CPU Apex, RecordId: 0123456
      <p>
      Error durante la exportación de Crm: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Tipo de entidad 'Cuenta': Código de error de CRM: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, Mensaje de error de CRM: el tipo de entidad no se puede actualizar: Cuenta, RecordId: 0123456</td>
      <td>Los déclencheur impiden actualizar o insertar un objeto.
      <p>
      O
      <p>
      Faltan permisos en el objeto.</td>
      <td>Revise el código de déclencheur que provoca que la inserción/actualización falle. Consulte la siguiente documentación de Salesforce para obtener más información sobre los déclencheur:
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&amp;type=5">déclencheur Apex</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">déclencheur de flujo</a>
          </li>
        </ul>
        <p>
        Proporcione todos los permisos necesarios al <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">usuario de Marketo Measure</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>Error durante la exportación de Crm: DUPLICATES_DETECTED : Tipo de entidad 'Contacto': Código de error de CRM: DUPLICATES_DETECTED, Mensaje de error de CRM: Está creando un registro duplicado. Se recomienda usar un registro existente en su lugar., RecordId: 0123456</td>
      <td>El registro que se está importando a la organización de Salesforce ya existe.</td>
      <td><a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">Deshabilite la configuración "Duplicar regla"</a> para permitir duplicados.
          <p>
          Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.</td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>Error durante la exportación de Crm: DUPLICATE_VALUE : Tipo de entidad 'Posible cliente': Código de error de CRM: DUPLICATE_VALUE, Mensaje de error de CRM: valor duplicado encontrado: Email_Unique__c duplica el valor en el registro con ID: 123, RecordId: 456</td>
      <td>El campo que se está importando a la organización de Salesforce no permite valores duplicados.</td>
      <td>Desmarque la <a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">"Casilla de verificación única"</a> en Salesforce.
          <p>
          Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.</td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKED</td>
      <td>Error durante la exportación de Crm: ENTITY_IS_LOCKED : Tipo de entidad "Cuenta": Código de error de CRM: ENTITY_IS_LOCKED, Mensaje de error de CRM: Este registro está bloqueado. Si necesita editarlo, póngase en contacto con el administrador., RecordId: 0123456</td>
      <td>Cuando un registro se encuentra en un proceso de aprobación y un usuario que no es el aprobador actual o el administrador del sistema intenta editar el registro.</td>
      <td>
        <ul>
          <li>Resuelva el proceso de aprobación pendiente para ese registro en la organización de Salesforce.</li>
          <li>Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>Error durante la exportación de Crm: FIELD_FILTER_VALIDATION_EXCEPTION : Tipo de entidad 'Posible cliente': Código de error de CRM: FIELD_FILTER_VALIDATION_EXCEPTION, Campos: Usuario__C, Mensaje de error de CRM: El valor no existe o no coincide con los criterios de filtro. Seleccione un usuario con la función "Ejecutivo de cuenta, ventas internas"; RecordId: 0123456</td>
      <td>El registro modificado ya no satisface los filtros de búsqueda definidos en el objeto.</td>
      <td>Compruebe si hay filtros en el objeto que Marketo Measure está intentando modificar. Consulte <a href="https://help.salesforce.com/s/articleView?id=000384756&amp;type=1">este artículo de Salesforce</a> para obtener información sobre cómo buscar filtros en un objeto.</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>Error durante la exportación de Crm: FIELD_INTEGRITY_EXCEPTION : Tipo de entidad 'Posible cliente': Código de error de CRM: FIELD_INTEGRITY_EXCEPTION, Campo(s): País, Mensaje de error de CRM: Hay un problema con este país, aunque pueda parecer correcto. Seleccione un país o territorio de la lista de países válidos.: País, ID de registro: 0123456</td>
      <td>El tipo esperado de registro no coincide.</td>
      <td>El caso más común de esto no es seguir las normas de nomenclatura de estado/país establecidas en la organización de Salesforce, porque los campos Estado/país se han estandarizado para aceptar solo ciertos valores de la lista de selección. Para solucionar este problema, puede:
        <ul>
          <li>Actualice el registro para seguir los valores aceptados de la organización para ese campo. Póngase en contacto con el administrador de SFDC para obtener la lista de valores aceptados.</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&amp;type=5">Deshabilitar las listas de selección de estado/país</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>Error durante la exportación de Crm: INACTIVE_OWNER_OR_USER : Tipo de entidad 'Contacto': Código de error de CRM: INACTIVE_OWNER_OR_USER, Mensaje de error de CRM: operación realizada con el usuario inactivo [1234] como propietario del contacto, RecordId: 0123456</td>
      <td>A Marketo Measure le falta el permiso "Actualizar registros con propietarios inactivos".</td>
      <td>Conceder a Marketo Measure el permiso "<a href="https://help.salesforce.com/s/articleView?id=000386699&amp;type=1">Actualizar registros con propietarios inactivos</a>".</td>
    </tr>
    <tr>
      <td>INSUFFICIENT_ACCESS_OR_READONLY</td>
      <td>Error durante la exportación de Crm: INSUFFICIENT_ACCESS_OR_READONLY : Tipo de entidad 'Cuenta': Código de error de CRM: INSUFFICIENT_ACCESS_OR_READONLY, Mensaje de error de CRM: derechos de acceso insuficientes en el ID de objeto: [123], RecordId: 456</td>
      <td>A Marketo Measure le faltan permisos en un objeto/ campo o el objeto es de solo lectura.</td>
      <td>Consulte el siguiente <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">artículo del Experience League</a> para obtener instrucciones sobre los permisos que Marketo Measure requiere.</td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Se ha producido un error durante la exportación de Adobe Analytics: INVALID_ADOBE_ANALYTICS_CONFIGURATION : Error: No se permite la carga. Confirme el esquema de la fuente de datos antes de cargar. ID de fuente de datos:1234</td>
      <td>La integración de Adobe Analytics no está configurada correctamente.</td>
      <td>Consulte los siguientes artículos de ayuda para garantizar una configuración correcta:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Integraciones de Marketo Measure con Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=es">Creación de un origen de atributo del cliente y carga del archivo de datos</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>Se ha producido un error durante la importación del anuncio: INVALID_CURRENCY_ISO_CODE: Marketo Measure no admite la moneda XXX.
      <p>
      Se ha producido un error durante la importación del anuncio: INVALID_CURRENCY_ISO_CODE: Marketo Measure no admite la moneda XXX en la cuenta para 1234.</td>
      <td>Se ha encontrado una moneda no compatible.</td>
      <td>En el sistema de origen indicado en la notificación (Ad, Crm, Marketo) se garantiza que la moneda asociada al registro tenga una moneda válida y compatible. Las monedas admitidas derivan de las normas de moneda ISO.</td>
    </tr>
    <tr>
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>Error durante la exportación de Crm: MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS : Tipo de entidad "Campaña": Código de error de CRM: INVALID_FIELD_FOR_INSERT_UPDATE, Campos: bizible2__UniqueId__c, Mensaje de error de CRM: No se pueden crear/actualizar campos: bizible2__UniqueId__c. Compruebe la configuración de seguridad de este campo y compruebe que es de lectura y escritura para su perfil o conjunto de permisos.</td>
      <td>A Marketo Measure le faltan permisos en los campos bizbibles.</td>
      <td>Se requieren permisos de lectura y escritura en todos los campos con el prefijo "bizible2__". Se puede encontrar una lista completa de estos campos <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">en este artículo</a>.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Se ha producido un error durante la exportación de CRM: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure no tiene el permiso para ver/editar posibles clientes convertidos</td>
      <td>Consulte el siguiente documento de Experience League para obtener ayuda sobre cómo habilitar este permiso en su CRM<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">Habilitación del permiso para editar posibles clientes convertidos</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Se ha producido un error durante la importación de CRM: MISSING_FIELD_READ_PERMISSION: Tipo de entidad 'Event': INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure carece de permisos de lectura en un campo obligatorio.</td>
      <td>Consulte los siguientes artículos de ayuda para obtener ayuda sobre los permisos que requiere Marketo Measure:
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
      <td>Se ha producido un error durante la importación de CRM: MISSING_ISREPLICATEABLE_PERMISSION : Falta el permiso IsReplicateable en Campaign</td>
      <td>Este permiso es necesario en los objetos de Salesforce para que podamos mantener su Marketo Measure y Salesforce sincronizados.</td>
      <td>Póngase en contacto con el servicio de soporte técnico de Salesforce para obtener ayuda sobre el establecimiento del permiso replicable en objetos.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Se ha producido un error durante la importación de CRM: MISSING_OBJECT_READ_PERMISSION: Tipo de entidad 'Campaign': Código de error de CRM: MISSING_PERMISSION</td>
      <td>Marketo Measure carece de permisos de lectura para un objeto necesario.</td>
      <td rowspan="2">Consulte los siguientes artículos de ayuda para obtener ayuda sobre los permisos que requiere Marketo Measure:
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
      <td>Se ha producido un error durante la exportación de CRM: MISSING_OBJECT_WRITE_PERMISSION: Tipo de entidad 'bizible2_Bizible_Attribution_Touchpoint': Código de error de CRM: MISSING_PERMISSION</td>
      <td>Marketo Measure carece de permisos de escritura en un objeto necesario.</td>
    </tr>
    <tr>
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>Error durante la exportación de Crm: MISSING_RECORD_OBJECT_PERMISSIONS : Tipo de entidad 'bizible2__Bizible_Touchpoint__c': Código de error de CRM: INSUFFICIENT_ACCESS_ON_CROSS_REFERENCE_ENTITY, Campos: Cuenta, Mensaje de error de CRM: derechos de acceso insuficientes en el ID de referencia cruzada: 0123456</td>
      <td>Faltan permisos en Marketo Measure.</td>
      <td>Existen varias razones para este error que son específicas de la organización de Salesforce. A continuación se indican algunos pasos comunes de solución de problemas que pueden resolver el problema:
        <ul>
          <li>Revise todos los permisos que necesitamos para cada <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">objeto y campo</a>.</li>
          <li>Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.</li>
          <li>Conceder permisos de "<a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">Modificar todos</a>" a Marketo Measure.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Se ha producido un error durante la importación de CRM: NULL_EMPTY_CURRENCY_ISO_CODE: El código ISO de moneda es NULL o está vacío cuando MultiCurrency está habilitado para RecordId 1234
      </td>
      <td>La moneda debe ser un código de moneda ISO compatible.</td>
      <td>En el sistema de origen indicado en la notificación (Ad, Crm, Marketo) se garantiza que la moneda asociada al registro tenga una moneda válida y compatible. Las monedas admitidas derivan de las normas de moneda ISO.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Se ha producido un error durante la importación de CRM: OPERATION_TOO_LARGE: Se necesita el permiso "Ver todos los datos" para consultar las actividades correctamente.</td>
      <td>La configuración de CRM no permite a Marketo Measure consultar un conjunto de datos lo suficientemente grande</td>
      <td>Conceda permisos para "Ver todos los datos" a Marketo Measure en el objeto designado.
      <p>
       <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">Aquí puede encontrar</a> más información sobre el permiso "Ver todos los datos".</td>
    </tr>
    <tr>
      <td>RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES</td>
      <td>Error durante la exportación de Crm: RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES : Tipo de entidad 'Posible cliente': CRM Código de error: FIELD_CUSTOM_VALIDATION_EXCEPTION, Campos: Lead_Status_Reason__c, CRM Mensaje de error: Debe seleccionar el Motivo del estado del posible cliente, RecordId: 0123456</td>
      <td>El registro que se está actualizando no cumple una regla de validación establecida en la organización de Salesforce.</td>
      <td>Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.
      <p>
      Actualice sus <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&amp;type=5">reglas de validación</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>Error durante la exportación de Crm: RESTRICT_PICKLIST_VALUES_ENABLED : Tipo de entidad "Campaña": Código de error de CRM: INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST, Campos: Areas_of_Interest__c, Mensaje de error de CRM: valor incorrecto para el campo de lista de selección restringido: Desconocido</td>
      <td>Cuando "Restringir la lista de selección a los valores definidos en el conjunto de valores" está habilitado en la configuración del campo de lista de selección o el valor que se está insertando en el campo no está disponible en el tipo de registro del objeto.</td>
      <td>Deshabilite la configuración restringir lista de selección en la organización de Salesforce.
          <p>
          Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>Error durante la exportación de Crm: MISSING_REQUIRED_FIELD : Tipo de entidad 'Posible cliente': Código de error de CRM: REQUIRED_FIELD_MISSING, Campos: Product_Type__c, Mensaje de error de CRM: Faltan campos obligatorios: [Product_Type__c], RecordId: 0123456</td>
      <td>Cuando una regla de validación especifica campos obligatorios en objetos.</td>
      <td>Excluir al usuario dedicado de Marketo Measure de <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">reglas de validación personalizadas</a>.
      </td>
    </tr>
    <tr>
      <td>UNKNOWN_EXCEPTION</td>
      <td>Error durante la exportación de Crm: UNKNOWN_EXCEPTION : Tipo de entidad 'Contacto': Código de error de CRM: UNKNOWN_EXCEPTION, Mensaje de error de CRM: los usuarios del portal no pueden ser propietarios de cuentas de socios, RecordId: 0123456</td>
      <td>Se ha producido una excepción no controlada en Salesforce.</td>
      <td>Si el problema persiste, presente un caso con Salesforce y copie los valores numéricos en el mensaje de error.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Error durante la importación de Crm: UNSUPPORTED_CRM_PACKAGE_VERSION : Actualice el paquete de crm</td>
      <td>El paquete actual detectado ya no es compatible.</td>
      <td>Actualice el paquete a la versión más reciente:
        <ul>
          <li> <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">Prácticas recomendadas</a>
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
