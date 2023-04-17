---
unique-page-id: 35586140
description: Esquema de Data Warehouse - Marketo Measure - Documentación del producto
title: Esquema de Data Warehouse
exl-id: f1895eb1-a32d-4c43-93fb-0aa838527946
source-git-commit: d1f1a3d1d0dd3111b984fbe9d0a8e8d3ed9289d2
workflow-type: tm+mt
source-wordcount: '22622'
ht-degree: 99%

---

# Esquema de Data Warehouse {#data-warehouse-schema}

Data Warehouse le permite rastrear todo lo que desee, informar sobre los datos de atribución donde quiera y conectarlos a otros conjuntos de datos.

>[!IMPORTANT]
>
>* Las filas con un valor para _DELETED_DATE se conservarán durante 7 días y, a continuación, se eliminarán de Snowflake.
>* Los husos horarios utilizados en el Snowflake se adhieren a la Hora Universal Coordinada (UTC).


>[!NOTE]
>
>[Haga clic aquí](#sample-queries) para ver consultas de ejemplo en la parte inferior de este artículo.

## Diagramas de relación de entidades {#entity-relationship-diagrams}

El ERD del _Modelo de datos de Data Warehouse_ muestra cómo se pretende que los datos de Data Warehouse fluyan y se vinculen entre sí. Este diagrama no incluye todas las tablas disponibles en Data Warehouse porque algunas de ellas representan tablas de asignación, vistas de otras tablas ya presentes o tablas obsoletas que ya no se recomienda utilizar. Consulte las descripciones detalladas de las tablas y columnas presentes en Data Warehouse a continuación. Muchas de estas tablas contienen campos no normalizados, sin embargo, este diagrama es el modelo de datos recomendado, aprovechando los datos de las tablas dimensionales en su lugar.

El ERD adicional del _Modelo de datos dimensional de anuncios_ presenta una vista de cómo las tablas para dimensiones específicas de anuncios se pueden vincular mejor a las tablas en el modelo de datos principal. Aunque las dimensiones de los anuncios también están desnormalizadas en otras tablas, esto representa el modelo recomendado para unir estas dimensiones.

_Haga clic en una imagen para obtener su versión de tamaño completo_

<table style="table-layout:auto"> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>Modelo de datos de Data Warehouse</strong></td> 
   <td><strong>Modelo de datos dimensional de anuncios</strong></td> 
  </tr> 
  <tr> 
   <td> 
    <div> 
     <p><a href="assets/data-warehouse-data-model.pdf"><img src="assets/data-warehouse-data-model-thumb.png"></a></p> 
    </div></td>
   <td> 
    <div> 
     <p><a href="assets/ads-dimensional-data-model.pdf"><img src="assets/ads-dimensional-data-model-thumb.png"></a></p>
    </div></td> 
  </tr> 
 </tbody> 
</table>

## Vistas {#views}

### BIZ_ACCOUNTS {#biz-accounts}

Cuentas importadas desde el sistema de origen.

<table>
  <tbody>
    <tr>
      <th><strong>Columna</strong></th>
      <th><strong>Tipo de datos</strong></th>
      <th><strong>Descripción</strong></th>
      <th><strong>Datos de muestra</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>El id. de cuenta, desde el sistema de origen.</td>
      <td>0013100001kpAZxAAM</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de creación de la cuenta, desde el sistema de origen.</td>
      <td>28/08/2016 00:32:55,000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de la última modificación de la cuenta, desde el sistema de origen.</td>
      <td>01/08/2018 17:38:30,000</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>El nombre de la cuenta, desde el sistema de origen.</td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>WEB_SITE</td>
      <td>varchar</td>
      <td>El sitio web de la cuenta, tal como se registra en el sistema de origen, utilizado para la asignación de posibles clientes a cuentas.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_RATING</td>
      <td>varchar</td>
      <td>Una calificación por letra (A, B, C, D, N/A) generada a partir del modelo de aprendizaje automático de [!DNL Marketo Measure]. Este será nulo si ABM está deshabilitado.</td>
      <td>B</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_SCORE</td>
      <td>number(38,19)</td>
      <td>Una puntuación numérica calculada mediante el aprendizaje automático de [!DNL Marketo Measure] para generar la puntuación de participación predictiva (Engagement_Rating). Este será nulo si ABM está deshabilitado.</td>
      <td>0.1417350147058800000</td>
    </tr>
    <tr>
      <td>DOMAIN</td>
      <td>varchar</td>
      <td>La versión analizada del sitio web que solo almacena el dominio.</td>
      <td>adobe</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Indica si el registro se elimina o no en el sistema de origen.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Account_Type__c": "Security", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_ACCOUNT_TO_EMAILS {#biz-account-to-emails}

La tabla de asignación entre direcciones de correo electrónico de posibles clientes/contactos y cuentas conocidas. Esta tabla estará vacía si ABM está deshabilitado.

<table>
  <tbody>
    <tr>
    <th><strong>Columna</strong></th>
      <th><strong>Tipo de datos</strong></th>
      <th><strong>Descripción</strong></th>
      <th><strong>Datos de muestra</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Un id. único para el registro.</td>
      <td>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13.000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cuenta, desde el sistema de origen.</p>
      </td>
      <td>
        <p>0013100001phrBAAAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico asignada a la cuenta, ya sea a través de relaciones de contacto o de la asignación de posibles clientes a cuentas.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la cuenta, desde el sistema de origen.</p>
      </td>
      <td>
        <p>31/08/2018 23:53:39,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de creación de la cuenta, desde el sistema de origen.</p>
      </td>
      <td>
        <p>18/08/2018 22:01:32,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se considera o no eliminado.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_ACTIVITIES {#biz-activities}

Actividades importadas desde un sistema de origen o una cuenta de anuncios conectada.

<table>
  <tbody>
  <tr>
    <th><strong>Columna</strong></th>
    <th><strong>Tipo de datos</strong></th>
    <th><strong>Descripción</strong></th>
    <th><strong>Datos de muestra</strong></th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de actividad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>1678625515</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. del posible cliente asociado a la actividad.</td>
      <td>
        <p>15530482</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado a la actividad.</p>
      </td>
      <td>
        <p>13792552</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del tipo de actividad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>104</p>
      </td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_NAME</td>
      <td>varchar</td>
      <td>El nombre de la actividad, desde el sistema de origen.</td>
      <td>
        <p>cambiar estado en progresión</p>
      </td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de inicio de la actividad, desde el sistema de origen.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestapm_ntz</td>
      <td>La fecha de finalización de la actividad, desde el sistema de origen.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>CAMPAIGN_ID</td>
      <td>varchar</td>
      <td>El id. de la campaña de la que forma parte la actividad, desde el sistema de origen.</td>
      <td>
        <p>li.508038570.147643566</p>
      </td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Identifica el tipo de sistema de origen.</td>
      <td>Marketo</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó la fila en el sistema de origen.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó por última vez la fila en el sistema de origen.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>IS_DELETD</td>
      <td>boolean</td>
      <td>Indica si el registro se considera o no eliminado en el sistema de origen.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>AD_FORM_ID</td>
      <td>varchar</td>
      <td>El id. del formulario de anuncios del que forma parte la actividad, desde el sistema de origen.</td>
      <td>li.507063119.3757704</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADS {#biz-ads}

Anuncios importados desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p><strong>Columna</strong></p>
      </th>
      <th>
        <p><strong>Tipo de datos</strong></p>
      </th>
      <th>
        <p><strong>Descripción</strong></p>
      </th>
      <th>
        <p><strong>Datos de muestra</strong></p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el anuncio.</p>
      </td>
      <td>
        <p>fb.106851586409075.6052044288804.6052044290004.6053457066804</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de anuncio, desde el sistema de origen.</p>
      </td>
      <td>
        <p>6053457066804</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el anuncio.</p>
      </td>
      <td>
        <p>fb.106851586409075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el anuncio.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Cuenta</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para el anuncio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante del anuncio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios para el anuncio.</p>
      </td>
      <td>
        <p>fb.106851586409075.6052044288804.6052044290004</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios para el anuncio.</p>
      </td>
      <td>
        <p>Conjunto de anuncios para el anuncio B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña para el anuncio.</p>
      </td>
      <td>
        <p>fb.106851586409075.6052044288804</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña del anuncio.</p>
      </td>
      <td>
        <p>Campaña de generación de posibles clientes</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anuncio sigue activo o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anuncio se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:59,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:59,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio, desde el sistema de origen.</p>
      </td>
      <td>
        <p>Anuncio 2</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anuncio debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td>
        <p>fb.106851586409075.6052044288804.6052044290004</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Anuncio”.</p>
      </td>
      <td>
        <p>Anuncio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el anuncio.</p>
      </td>
      <td>
        <p>Facebook</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la página de destino.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Valor anterior para URL_CURRENT.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Decoración de la dirección URL con los parámetros de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_ALTENATIVES</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Importado desde el sistema de origen.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADVERTISERS {#biz-advertisers}

Anunciantes importados desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el anunciante.</p>
      </td>
      <td>
        <p>dc.6114.9143143</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de anunciante, desde el sistema de origen.</td>
      <td>9143143</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el anuncio.</p>
      </td>
      <td>
        <p>fb.106851586409075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el anuncio.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Cuenta</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima del anunciante en ninguna jerarquía de anuncios.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima del anunciante en ninguna jerarquía de anuncios.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna campaña de anuncios por encima del anunciante en ninguna jerarquía de anuncios.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna campaña por encima del anunciante de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anunciante sigue activo o no en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anunciante se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:59,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:59,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante, desde el sistema de origen.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anunciante debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Anunciante”.</p>
      </td>
      <td>
        <p>Anunciante</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El proveedor de anuncios para el anunciante.</p>
      </td>
      <td>
        <p>DoubleClick</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_ACCOUNTS {#biz-ad-accounts}

Cuentas de anuncios importadas desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la cuenta de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de cuenta de anuncios, desde el sistema de origen.</td>
      <td>
        <p>6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se espera que sea nulo, ya que este es el registro de las cuentas de anuncios en la jerarquía de anuncios.</td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se espera que sea nulo, ya que este es el registro de las cuentas de anuncios en la jerarquía de anuncios.</td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún anunciante por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún anunciante por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna campaña de anuncios por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna campaña de anuncios por encima de las cuentas de anuncios en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la cuenta de anuncios sigue o no activa en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la cuenta de anuncios se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>06/09/2018 12:54:37,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:58,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El nombre de la cuenta de anuncios, desde el sistema de origen.</td>
      <td>
        <p>[!DNL Marketo Measure] Cuenta de anuncios</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anunciante debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Cuenta”.</p>
      </td>
      <td>
        <p>Cuenta</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para la cuenta de anuncios.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_CURRENCY_UNIT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El código de divisa utilizado para la cuenta de anuncios, desde el sistema de origen.</p>
      </td>
      <td>
        <p>USD</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se utiliza para el procesamiento interno.</td>
      <td>1933789</td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Analizado desde la dirección URL de utm_source.</td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Analizado desde la dirección URL de utm_medium.</td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_COST</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>La cantidad de gastos importada durante los últimos 30 días, solo aplicable a AdWords.</p>
      </td>
      <td>
        <p>17260.000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_IMPRESSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>El número de impresiones de los últimos 30 días, solo aplicable a AdWords.</p>
      </td>
      <td>
        <p>730060</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CLICKS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>El número de clics de los últimos 30 días, solo aplicable a AdWords.</p>
      </td>
      <td>
        <p>3400</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CONVERSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>El número de conversiones notificadas de los últimos 30 días, solo aplicable a AdWords.</p>
      </td>
      <td>
        <p>180</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plantilla de seguimiento agregada en el nivel de cuenta de anuncios para AdWords o Bing para etiquetar páginas de destino.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_CAMPAIGNS {#biz-ad-campaigns}

Campañas importadas desde cuentas de anuncios conectadas, sistemas de origen, UTM y autoinformes.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Id. único para la campaña.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de campaña, desde el sistema de origen.</td>
      <td>
        <p>285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó la campaña.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó la campaña.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para la campaña, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para la campaña, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de la campaña en ninguna jerarquía de anuncios.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de la campaña en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Id. único para la campaña, utilice el campo Id. en su lugar.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña, utilice el campo Nombre en su lugar.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la campaña sigue o no activa en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la campaña se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:58,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:58,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña.</p>
      </td>
      <td>
        <p>Redireccionamiento de socios</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la campaña debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Campaña”.</p>
      </td>
      <td>
        <p>Campaña</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para la campaña.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DAILY_BUDGET</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>El presupuesto diario que se establece en la plataforma de anuncios para la campaña.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plantilla de seguimiento agregada en el nivel de campaña para AdWords o Bing para etiquetar páginas de destino.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_FORMS {#biz-ad-forms}

Formularios de anuncios importados desde cualquier cuenta de anuncios conectada.

<table>
  <tr>
    <th>
      <p>Columna</p>
    </th>
    <th>
      <p>Tipo de datos</p>
    </th>
    <th>
      <p>Descripción</p>
    </th>
    <th>
      <p>Datos de muestra</p>
    </th>
  </tr>
  <tbody>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el formulario de anuncios.</p>
      </td>
      <td>
        <p>li.507063119.3757704</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el formulario de anuncios.</p>
      </td>
      <td>
        <p>li.507063119</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el formulario de nuncios.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Estado Eliminado, desde el sistema de origen. Se establece como Eliminado si el estado es Borrador, Archivado o Cancelado.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:58,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:35:58,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del formulario de anuncios.</p>
      </td>
      <td>
        <p>NSPA Ebook LGF (mayo de 2020)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “AdForm”.</p>
      </td>
      <td>
        <p>AdForm</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el formulario de anuncios.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La descripción del formulario de anuncios.</p>
      </td>
      <td>
        <p>Aprenda cómo la automatización inteligente puede aumentar la eficacia del proceso en las solicitudes de préstamos de refinanciación hipotecaria.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El encabezado del formulario de anuncios.</td>
      <td>
        <p>Es hora de automatizar el proceso de solicitud de refinanciación</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección URL de la página de destino del formulario de anuncios.</td>
      <td>
        <p>https://adobe.com/blog/refinancing-application-process/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>QUESTIONS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La lista de preguntas para el formulario de anuncios.</td>
      <td>
        <p>Nombre:Apellido:Dirección de correo electrónico:País/Región:Puesto de trabajo:Nombre de la empresa</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El estado del formulario de anuncios.</p>
      </td>
      <td>
        <p>enviado</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>El id. del origen desde el que se originó el registro.</td>
      <td>aw.3284209</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_GROUPS {#biz-ad-groups}

Grupos de anuncios importados desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el grupo de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955.23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de grupo de anuncios, desde el sistema de origen.</td>
      <td>
        <p>23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el grupo de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el grupo de anuncios.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios en la jerarquía de anuncios de DoubleClick.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios en la jerarquía de anuncios de DoubleClick.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que este es el registro del grupo de anuncios en la jerarquía.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que este es el registro del grupo de anuncios en la jerarquía.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña para el grupo de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña para el grupo de anuncios.</p>
      </td>
      <td>
        <p>Atribución de ingresos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la cuenta de anuncios sigue o no activa en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la cuenta de anuncios se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:36:14,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:36:14,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios.</p>
      </td>
      <td>
        <p>Atribución de ingresos: basada en cuentas</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el anunciante debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “AdGroup”.</p>
      </td>
      <td>
        <p>Grupo de anuncios</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el grupo de anuncios.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NETWORK_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Los medios en los que se ejecuta el grupo de anuncios.</p>
      </td>
      <td>
        <p>Búsqueda, Visualización, YouTube_Search, YouTube_Watch</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plantilla de seguimiento agregada en el nivel de cuenta de anuncios para AdWords o Bing para etiquetar páginas de destino.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-5594512713562690000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_PROVIDERS

<p>Proveedores de anuncios de cualquier cuenta de anuncios conectada, incluida una entrada para que se informe usted mismo, si corresponde.</p>

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el proveedor de anuncios.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>4783788151269206864</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_TOUCHPOINTS {#biz-attribution-touchpoints}

<p>Puntos de contacto de atribución de comprador, todos los puntos de contacto asociados a una oportunidad.</p>
<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el punto de contacto de atribución de comprador (BAT).</p>
      </td>
      <td>
        <p>BAT2_0060Z00000lFHtOQAW_</p>
        <p>0030Z00003K5bpKQAR_2017-06-20:01-05-20-6193330.0b5c5678807c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>01/09/2018 04:53:53,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la oportunidad a la que se atribuye el BAT.</p>
      </td>
      <td>
        <p>0060Z00000lFHtOQAW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado al BAT.</p>
      </td>
      <td>
        <p>0030Z00003K5bpKQAR</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>La dirección de correo electrónico asociada al BAT.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta a la que se atribuye el BAT.</p>
      </td>
      <td>
        <p>0013100001otbIAAAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del punto de contacto del usuario que generó el BAT.</p>
      </td>
      <td>
        <p>person@adobe.com_00v1B00003ZbWzHQAV</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha del punto de contacto.</p>
      </td>
      <td>
        <p>20/06/2017 01:05:20,000</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>El id. del visitante asociado al BAT.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de actividad, visita web, formulario web, chat en web, llamada telefónica, campaña [CRM] o actividad [CRM]. En CRM, se denomina “Tipo de punto de contacto”.</p>
      </td>
      <td>
        <p>Formulario web</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El canal al que corresponde el punto de contacto, tal como se especifica en las definiciones de canales personalizados en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Canal de marketing - Ruta”.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la primera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>ABC</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la segunda categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>Sí</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY3</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la tercera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>SMB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY4</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la cuarta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td>
        <p>Nuevo negocio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY5</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la quinta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY6</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la sexta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la séptima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la octava categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la novena categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY10</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la décima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY11</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la undécima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY12</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la duodécima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY13</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la decimotercera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY14</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la decimocuarta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY15</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la decimoquinta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el explorador detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada del explorador en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la plataforma detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada de la plataforma en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. En CRM, se denomina “Página de destino”.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover- truth-behind-cost-per-lead</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. Una página de destino sin procesar contendrá todos los parámetros de consulta en la dirección URL. En CRM, se denomina “Página de destino - Sin procesar”.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover-truth -behind-cost-per-lead?utm_content=27322869&amp;utm_ medium=social&amp;utm_source=linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. En CRM, se denomina “Página del referente”.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. Una página de referente sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “Página de referente - Sin procesar”.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Attribution_Touchpoints, sino en la tabla Form_Submits. En CRM, se denomina “URL del formulario”.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Attribution_Touchpoints, sino en la tabla Form_Submits. Una página de formulario sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “URL del formulario - Sin procesar”.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se realizó el envío del formulario.</p>
      </td>
      <td>
        <p>20/06/2017 01:06:41,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la ciudad detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>San Francisco</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la región detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>California</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el país detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Estados Unidos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el medio que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_medium. O bien, si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “cpc” o “visualización”.</p>
      </td>
      <td>
        <p>social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el origen que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_source, establecida genéricamente como “Campaña de CRM” si se sincronizó desde CRM, o si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “Google AdWords” o “Facebook”. En CRM, se denomina “Origen del punto de contacto”.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor que el usuario introdujo en el explorador para su búsqueda y acabó en el sitio web. Dependiendo de las compras de palabras clave, esto puede o no coincidir con las palabras clave compradas en la plataforma Búsqueda de pago.</p>
      </td>
      <td>
        <p>Google [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plataforma de anuncios [!DNL Marketo Measure] pudo resolverlo, por lo general, uno de nuestros socios de integración.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>Atribución de marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>Atribución de marketing: general</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>
        <p>dc.6114.8882972.25272734.492579576</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>
        <p>Seminario web sobre presupuesto: barra lateral</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.182716179597</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Atribución de marketing B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Descargar la guía de CMO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La segunda línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Descubra cómo la atribución mide el ROI conectando las actividades de marketing con los ingresos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La página de destino en la que se hace clic desde el anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre descriptivo de la dirección URL que se muestra en el anuncio de búsqueda, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>http://info.adobe.com/CMOs-Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.4838421670</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda)</p>
      </td>
      <td>
        <p>“atribución de marketing”</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de coincidencia encontrada entre la frase de búsqueda y la palabra clave comprada.</p>
      </td>
      <td>
        <p>Exacto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el primer contacto del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto de creación de posibles clientes del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto de creación de oportunidades del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto cerrado del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGES_TOUCHED</p>
      </td>
      <td>varchar</td>
      <td>Este campo está en desuso. Utilice las tablas Stage_Transitions para obtener información sobre la fase.</td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto rellenó o no un formulario durante la sesión.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el primer contacto de impresiones del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un primer contacto (consulte Is_First_Touch).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un contacto de creación de posibles clientes (consulte Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de U (consulte Is_First_Touch e Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de W (consulte Is_First_Touch, Is_Lead_Creation_Touch e Is_Opp_Creation_Touch).</p>
      </td>
      <td>
        <p>0.0153374234214425</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo de ruta completa (consulte See Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch e Is_Closed_Touch).</p>
      </td>
      <td>
        <p>0.0143061513081193</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>number(22,19)</td>
      <td>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo personalizado (consulte Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch e Is_Closed_Touch).</td>
      <td>0.0143061513081193</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se elimina este punto de contacto.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_ROW_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CAMPAIGN_MEMBERS {#biz-campaign-members}

Miembros de campaña importados desde el sistema de origen. Esta tabla estará vacía si la sincronización de campaña está deshabilitada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de miembro de campaña, desde el sistema de origen.</p>
      </td>
      <td>
        <p>00v0Z00001VVzdLQAT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación del miembro de campaña, desde el sistema de origen.</p>
      </td>
      <td>
        <p>31/08/2018 20:49:54,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de creación del miembro de campaña, desde el sistema de origen.</p>
      </td>
      <td>
        <p>31/08/2018 20:49:54,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_TOUCH_POINT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha y la hora que el cliente establece para anular la fecha de campaña, utilice este valor para la fecha del punto de contacto en su lugar.</p>
      </td>
      <td>
        <p>30/08/2018 18:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente al que está vinculado el miembro de campaña.</p>
      </td>
      <td>
        <p>00Q0Z000013dw4GUAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del posible cliente al que está vinculado el miembro de campaña.</p>
      </td>
      <td>
        <p>persona@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto al que está vinculado el miembro de campaña.</p>
      </td>
      <td>
        <p>00331000032hMxRAAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del contacto al que está vinculado el miembro de campaña.</p>
      </td>
      <td>
        <p>persona@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El estado del miembro de campaña, normalmente establecido en Enviado o Respondido u otro valor personalizado. Este estado está vinculado a Campaign_Sync_Type para determinar para qué miembros de campaña se crearán puntos de contacto.</p>
      </td>
      <td>
        <p>Enviado</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_RESPONDED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el miembro de campaña se marcó como “Respondido” en el selector Estado.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_RESPONDED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que el miembro de campaña respondió por primera vez.</p>
      </td>
      <td>
        <p>30/08/2018 07:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña relacionada de la que forma parte el miembro de campaña.</p>
      </td>
      <td>
        <p>Entrevistas rápidas de CMO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña relacionada de la que forma parte el miembro de campaña.</p>
      </td>
      <td>
        <p>7010Z000001TcKlQAK</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo seleccionado en la campaña relacionada de la que forma parte el miembro de campaña. El tipo se utiliza para asignar el canal de marketing.</p>
      </td>
      <td>
        <p>Sin conexión</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_SYNC_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Determina para qué miembros de campaña se crearán puntos de contacto. Los valores posibles son: Include_All, Include_Responded y Exclude_All.</p>
      </td>
      <td>
        <p>Include_All</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SYNC_STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Campo de auditoría, indica si se generó o no un punto de contacto de comprador para el posible cliente. Si no se creó ningún punto de contacto, se indica la razón por la que no reunió las condiciones necesarias.</p>
      </td>
      <td>
        <p>Sin punto de contacto: modelo de fecha exterior</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_SYNC_STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Campo de auditoría, indica si se generó o no un punto de contacto de comprador para el contacto. Si no se creó ningún punto de contacto, se indica la razón por la que no reunió las condiciones necesarias.</p>
      </td>
      <td>
        <p>Punto de contacto creado</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_SYNC_STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Campo de auditoría, indica si se generó o no un punto de contacto de atribución de comprador para la oportunidad. Si no se creó ningún punto de contacto, se indica la razón por la que no reunió las condiciones necesarias.</p>
      </td>
      <td>
        <p>Punto de contacto creado</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se considera o no eliminado en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Campaign_Type__c":"Dinners","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CHANNELS {#biz-channels}

Canales de marketing, tal como se crearon en la aplicación [!DNL Marketo Measure].

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el canal.</p>
      </td>
      <td>
        <p>Búsqueda orgánica.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del canal.</p>
      </td>
      <td>
        <p>Búsqueda orgánica.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CONTACTS {#biz-contacts}

Contactos importados desde el sistema de origen.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de contacto, desde el sistema de origen.</p>
      </td>
      <td>
        <p>0030Z00003OzioeQAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó por última vez el registro de contacto, desde el sistema de origen.</p>
      </td>
      <td>
        <p>05/09/2018 05:17:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó el registro de contacto, desde el sistema de origen.</p>
      </td>
      <td>
        <p>05/09/2018 05:17:51,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico del contacto, desde el sistema de origen.</p>
      </td>
      <td>
        <p>persona@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta relacionada con el contacto.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El origen en el que se creó el posible cliente.</p>
      </td>
      <td>
        <p>Anuncio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Fase actual del contacto, reconocida como una fase personalizada que se puede crear en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Demostración programada</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Todas las fases anteriores del contacto, reconocidas como fases personalizadas que se pueden crear en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Abrir: contacto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>El algoritmo de estimación de [!DNL Marketo Measure] que indica si un contacto ayudará a cerrar una oportunidad en función de la edad y la fase</p>
      </td>
      <td>
        <p>.290034</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies de [!DNL Marketo Measure] utilizado para rellenar desde un socio de integración con el fin de asignar un evento sin conexión a una sesión web. Requisito: Habilitar seguimiento de llamadas: Verdadero</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se elimina o no en el sistema de origen.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Se utiliza para eliminar registros duplicados si se ha configurado una integración de CRM y Marketo. Si hay duplicados, el contacto de Marketo se marca como verdadero.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Indica si el registro procede de una integración de CRM o Marketo.</td>
      <td>CRM</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Asigna a una persona de una integración de Marketo con un contacto de una integración de CRM. Si existe una integración de CRM y Marketo, el valor es el id. correspondiente.</td>
      <td>1234 / 00Q0Z00001OohgTUAR</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>3263982503087870000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CONVERSION_RATES {#biz-conversion-rates}

Tasas de conversión de divisa importadas desde el sistema de origen.

<table>
  <tbody>
    <tr>
      <th>Columna</th>
      <th>Tipo de datos</th>
      <th>Descripción</th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>number(38,0)</td>
      <td>Un id. único para el registro.</td>
      <td>-5942345438803054604</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>El valor de id. para la divisa.</td>
      <td>7493833133899044458</td>
    </tr>
    <tr>
      <td>SOURCE_ISO_CODE</td>
      <td>varchar</td>
      <td>El código ISO de divisa, desde el sistema de origen.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de inicio de la tasa de conversión.</td>
      <td>01/11/2018 00:00:00,000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de inicio siguiente para la tasa de conversión. (La fecha de finalización de la tasa de conversión es end_date menos un día).</td>
      <td>01/09/2018 00:00:00,000</td>
    </tr>
    <tr>
      <td>CONVERSION_RATE</td>
      <td>number(38,0)</td>
      <td>La tasa utilizada para convertir la divisa en la divisa corporativa.</td>
      <td>0.76728300</td>
    </tr>
    <tr>
      <td>IS_CURRENT</td>
      <td>boolean</td>
      <td>La semántica de este campo se ha dañado. No usar.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en el sistema de origen.</td>
      <td>30/03/2019 00:54:50,000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó por última vez el registro en el sistema de origen.</td>
      <td>30/03/2019 00:54:50,000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Indica si el registro se considera o no eliminado en el sistema de origen.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_COSTS {#biz-costs}

Datos de costes importados desde cuentas de anuncios conectadas o gasto de marketing notificado personalmente.

<table>
  <tbody>
    <tr>
      <th>Columna</th>
      <th>Tipo de datos</th>
      <th>Descripción</th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Un id. único para el registro de costes.</td>
      <td>aw.6601259029.285114995.21703163075.[AdWords Display]_2018-09-06</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez.</td>
      <td>06/09/2018 12:22:45,000</td>
    </tr>
    <tr>
      <td>COST_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se incurrió (o se atribuyó) el coste.</td>
      <td>06/09/2018 00:00:00,000</td>
    </tr>
    <tr>
      <td>SOURCE</td>
      <td>varchar</td>
      <td>El origen del coste registrado.</td>
      <td>[Pantalla de AdWords]</td>
    </tr>
    <tr>
      <td>COST_IN_MICRO</td>
      <td>number(38,0)</td>
      <td>La cantidad de costes en millones. El usuario tendrá que dividir el valor por 1 000 000.</td>
      <td>1410000</td>
    </tr>
    <tr>
      <td>CLICKS</td>
      <td>number(38,0)</td>
      <td>El número de clics registrados para el grupo durante el día.</td>
      <td>4</td>
    </tr>
    <tr>
      <td>IMPRESSIONS</td>
      <td>number(38,0)</td>
      <td>El número de impresiones registradas para el grupo durante el día.</td>
      <td>4187</td>
    </tr>
    <tr>
      <td>ESTIMATED_TOTAL_POSSIBLE_IMPRESSIONS</td>
      <td>number(38,0)</td>
      <td>El número total de impresiones estimadas de DCM para el grupo durante el día.</td>
      <td>5024</td>
    </tr>
    <tr>
      <td>AD_PROVIDER</td>
      <td>varchar</td>
      <td>El proveedor para el cual se extrajo el coste.</td>
      <td>Google</td>
    </tr>
    <tr>
      <td>CHANNEL_UNIQUE_ID</td>
      <td>varchar</td>
      <td>El id. del canal de marketing, creado por [!DNL Marketo Measure].</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_NAME</td>
      <td>varchar</td>
      <td>El nombre del canal de marketing, creado por el cliente en la aplicación [!DNL Marketo Measure].</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Indica si la fila contiene coste que se puede sumar por canal (es decir, para obtener coste de canal, sume filas donde esta columna sea igual a verdadero).</td>
      <td>false</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>El id. del anunciante extraído de la conexión de anuncios, específicamente para conexiones DoubleClick.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>El nombre del anunciante extraído de la conexión de anuncios, específicamente para conexiones DoubleClick.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>ADVERTISER_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Indica si la fila contiene coste que se puede sumar por anunciante (es decir, para obtener coste de anunciante, sume filas donde esta columna sea igual a verdadero).</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por cuenta (es decir, para obtener coste de cuenta, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de campaña extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de campaña extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>Redireccionamiento de socios</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por campaña (es decir, para obtener coste de campaña, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.21703163075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>Software de administración de atribuciones | Frase</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por grupo de anuncios (es decir, para obtener coste de grupo de anuncios, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>dc.6114.9131003.24149929.467969200</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>Nombre del anuncio: Ad3-320x50.gif; 320 x 50</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por anuncio (es decir, para obtener coste de anuncio, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del creativo extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.51749608028.266050115160</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>Cuadrante Mágico de Gartner de 2019</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por creativo (es decir, para obtener coste de creativo, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la palabra clave extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>aw.6601259029.669328935.39419128772.99608705795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>atribución de marketing sfdc</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PALABRA CLAVE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por palabra clave (es decir, para obtener coste de palabra clave, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por ubicación (es decir, para obtener coste de ubicación, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio extraído de la conexión de anuncios.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por sitio (es decir, para obtener coste de sitio, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se considera o no eliminado en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ISO_CURRENCY_CODE</td>
      <td>varchar</td>
      <td>El código ISO para la divisa, importado desde el sistema de origen.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>El id. del origen desde el que se originó el registro.</td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ROW_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>El valor de id. de la divisa para el registro.</td>
      <td>
        <p>-3253183181619994799</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CREATIVES {#biz-creatives}

Creativos importados desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el creativo.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de creativo, desde el sistema de origen.</td>
      <td>
        <p>10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el creativo.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el creativo.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para el creativo, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para el creativo, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios para el creativo.</p>
      </td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios para el creativo.</p>
      </td>
      <td>Conjunto de anuncios para el anuncio B</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña para el creativo.</p>
      </td>
      <td>
        <p>ba.3284209.132855866</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña para el creativo.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el creativo sigue o no activo en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el creativo se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>02/08/2018 06:36:25,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:36:25,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo, desde el sistema de origen.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el creativo debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Creativo”.</p>
      </td>
      <td>
        <p>Creativo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el creativo.</p>
      </td>
      <td>
        <p>Bing Ads</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La versión actual de la dirección URL, incluidas todas las etiquetas.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td>
        <p>cdn.adobe.com/redir?lp=http%3a%2f%2fwww.pipelinemarketing.com%2f&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}&amp;utm_content={adid}&amp;utm_term={keyword}&amp;utm_campaign=PipelineMarketing.com&amp;utm_source=bing&amp;utm_medium=cpc</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_DISPLAY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL abreviada y descriptiva que se muestra en el creativo.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Valor anterior para URL_CURRENT.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Decoración de la dirección URL con los parámetros de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_SHORTENED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección URL abreviada y descriptiva que se muestra en el creativo. (Solo se usa para LinkedIn Ads).</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de creativo, que puede ser texto o visualización</p>
      </td>
      <td>
        <p>Texto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el creativo está usando o no direcciones URL actualizadas.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La línea superior (encabezado) del creativo</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La copia de la primera línea del creativo</p>
      </td>
      <td>
        <p>Conéctese y aprenda de los expertos en marketing B2B impulsados por los ingresos. Únase a la comunidad.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La copia de la segunda línea del creativo</p>
      </td>
      <td>
        <p>¿Ha utilizado Analytics? ¡Deje hoy una reseña!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Campo de diagnóstico, para procesamiento interno.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SHARE_URN</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del recurso compartido. (Solo se usa para LinkedIn Ads).</p>
      </td>
      <td>
        <p>urn:li:share:6376987561897848832</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_EVENTS {#biz-crm-events}

Eventos importados desde el sistema de origen. Esta tabla estará vacía si la sincronización de actividad está deshabilitada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de evento, desde el sistema de origen.</p>
      </td>
      <td>
        <p>00U3100000VLUnEEAX</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó el evento, desde el sistema de origen.</p>
      </td>
      <td>
        <p>12/12/2016 19:32:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó por última vez el evento, desde el sistema de origen.</p>
      </td>
      <td>
        <p>03/09/2018 08:39:51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente asociado al evento.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del posible cliente asociado al evento.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado al evento.</p>
      </td>
      <td>
        <p>0030Z00003OyjbOQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del contacto asociado al evento.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies de [!DNL Marketo Measure] utilizado para rellenar desde un socio de integración con el fin de asignar un evento sin conexión a una sesión web. Requisito: Habilitar seguimiento de llamadas: Verdadero</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del tipo de actividad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>Correo electrónico</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_START_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de inicio del evento, una de las opciones utilizadas para determinar la fecha del punto de contacto.</p>
      </td>
      <td>
        <p>16/12/2016 19:30:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_END_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de finalización del evento, una de las opciones utilizadas para determinar la fecha del punto de contacto.</p>
      </td>
      <td>
        <p>16/12/2016 21:30:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si el registro se considera o no eliminado en el sistema de origen.</td>
      <td>
        <p>Falso</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Contact_Type__c":"CMO","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_TASKS {#biz-crm-tasks}

Tareas importadas desde el sistema de origen. Esta tabla se rellenará si están habilitadas la sincronización de actividades o el seguimiento de llamadas.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de tarea, desde el sistema de origen.</p>
      </td>
      <td>
        <p>00T0Z00004Rf62rUAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó la tarea, desde el sistema de origen.</p>
      </td>
      <td>
        <p>27/08/2018 18:30:25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó por última vez la tarea, desde el sistema de origen.</p>
      </td>
      <td>
        <p>27/08/2018 18:31:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente asociado a la tarea.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del posible cliente asociado a la tarea.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado a la tarea.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del contacto asociado a la tarea.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies de [!DNL Marketo Measure] utilizado para rellenar desde un socio de integración con el fin de asignar un evento sin conexión a una sesión web. Requisito: Habilitar seguimiento de llamadas: Verdadero</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del tipo de actividad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>Llamar a un</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se realizó la tarea, una de las opciones utilizadas para determinar la fecha del punto de contacto.</p>
      </td>
      <td>
        <p>27/08/2018 07:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si el registro se considera o no eliminado en el sistema de origen.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CURRENCIES {#biz-currencies}

La tabla de todas las divisas ISO.

<table>
  <tbody>
    <tr>
      <th>Columna</th>
      <th>Tipo de datos</th>
      <th>Descripción</th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>number(38,0)</td>
      <td>Un id. único para el registro de divisa.</td>
      <td>139474809945095870</td>
    </tr>
    <tr>
      <td>ISO_CODE</td>
      <td>varchar</td>
      <td>El código ISO para la divisa.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>IS_CORPORATE</td>
      <td>boolean</td>
      <td>Designa si la divisa es la divisa corporativa.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_ENABLED</td>
      <td>boolean</td>
      <td>Designa si la divisa está habilitada en el sistema de origen.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó por última vez el registro en [!DNL Marketo Measure].</td>
      <td>27/08/2018 18:30:25.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó por última vez el registro en el sistema de origen.</td>
      <td>27/08/2018 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro [!DNL Marketo Measure]</td>
      <td>27/08/2018 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en el sistema de origen.</td>
      <td>27/08/2018 18:30:25.000</td>
    </tr>
    <tr>
      <td>ISO_NUMERIC</td>
      <td>number(38,0)</td>
      <td>El código numérico estándar ISO.</td>
      <td>048</td>
    </tr>
    <tr>
      <td>EXPONENT</td>
      <td>number(38,0)</td>
      <td>El número de decimales entre la unidad de divisa definida más pequeña y una unidad de divisa entera.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>El nombre de la divisa.</td>
      <td>Peso argentino</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_AB_TESTS {#biz-customer-ab-tests}

Pruebas A/B registradas. Esta tabla estará vacía si las pruebas A/B no están habilitadas.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer id. de cookies del id. de visitante relacionado.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookie registrado en el momento en que se registró el evento.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se registró el chat.</p>
      </td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento en que se registró el experimento.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del experimento extraído de la plataforma de pruebas A/B.</p>
      </td>
      <td>123</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del experimento extraído de la plataforma de pruebas A/B.</p>
      </td>
      <td>Experimento A</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de variación del experimento extraído de la plataforma de pruebas A/B.</p>
      </td>
      <td>456</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de variación del experimento extraído de la plataforma de pruebas A/B.</p>
      </td>
      <td>Prueba azul</td>
    </tr>
    <tr>
      <td>
        <p>ABTEST_USER_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del usuario que recibió el experimento extraído de la plataforma de pruebas A/B.</p>
      </td>
      <td>584d64et</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se eliminó o no el registro, se utiliza para el diagnóstico y la auditoría.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_EVENTS {#biz-customer-events}

Eventos web que se han registrado utilizando eventos personalizados en el JavaScript. Esta tabla estará vacía si los eventos de [!DNL Marketo Measure] no están habilitados.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer id. de cookies del id. de visitante relacionado.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies registrado en el momento en que se activó el evento desde el JavaScript personalizado.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se activó el evento desde el JavaScript personalizado.</p>
      </td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento en que se activó el evento desde el JavaScript personalizado.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre proporcionado al evento que se activó desde el JavaScript personalizado.</p>
      </td>
      <td>Vista de vídeo</td>
    </tr>
    <tr>
      <td>
        <p>VALUE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor proporcionado al evento que se activó desde el JavaScript personalizado.</p>
      </td>
      <td>75 % visitado</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se eliminó o no el registro, se utiliza para el diagnóstico y la auditoría.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOM_LANDING_PAGES {#biz-custom-landing-pages}

Páginas de destino descargadas desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el registro.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de la cuenta de anuncios desde la que se importó la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El nombre de la cuenta de anuncios desde la que se importó la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para la página de destino, específicamente para DoubleClick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para la página de destino, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. del grupo de anuncios para la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios para la página de destino.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de campaña para la página de destino.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de campaña para la página de destino.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la fila</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_EMAIL_TO_VISITOR_IDS {#biz-email-to-visitor-ids}

La tabla de asignación para direcciones de correo electrónico e id. de visitante.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Un id. único para el registro.</td>
      <td>
        <p>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Una dirección de correo electrónico conocida vinculada a un id. de visitante determinado de una sesión.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera cookie del id. de visitante relacionado.</p>
      </td>
      <td>
        <p>v_36ec805b4db344d6e92c972c86aee34a</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la fila</p>
      </td>
      <td>
        <p>14/08/2018 23:55:03,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de creación de la fila.</p>
      </td>
      <td>
        <p>14/08/2018 23:55:03,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se considera o no eliminado el registro, se utiliza para el diagnóstico y la auditoría.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_IGNORE</td>
      <td>boolean</td>
      <td>Indica si el correo electrónico o el id. de visitante se consideran ruido o correo no deseado, se utiliza para el procesamiento interno.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_FACTS {#biz-facts}

Agrupa Impresiones, Vistas de página, Visitas, Envíos de formularios, Puntos de contacto del usuario, Punto de contacto (BT), Puntos de contacto de atribución (BAT) y Datos de costes. Se utiliza internamente para admitir informes de [!DNL Marketo Measure].

<table>
  <tbody>
    <tr>
      <th>Columna</th>
      <th>Tipo de datos</th>
      <th>Descripción</th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>COST_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Costes.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>ATP_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Puntos de contacto de atribución.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>TP_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a las tablas Puntos de contacto o Puntos de contacto del usuario.</td>
      <td>5028390208679093800</td>
    </tr>
    <tr>
      <td>PAGE_VIEW_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Vistas de página.</td>
      <td>-8044063242541720607</td>
    </tr>
    <tr>
      <td>SESSION_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Sesiones.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>El primer id. de cookies del id. de visitante relacionado.</td>
      <td>v_530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>COOKIE_ID</td>
      <td>varchar</td>
      <td>El id. de cookie registrado en el momento en que se registró el evento.</td>
      <td>530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>FORM_SUBMIT_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Envíos de formulario.</td>
      <td>-8659572802702769670</td>
    </tr>
    <tr>
      <td>IMPRESSION_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Impresiones.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Direcciones URL.</td>
      <td>4079876040770132443</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Direcciones URL.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Direcciones URL.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>AD_PROVIDER_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Proveedores de anuncios.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Canales.</p>
      </td>
      <td>
        <p>-1921844114032355934</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Campañas de anuncios.</p>
      </td>
      <td>
        <p>252687814634577606</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Palabras clave.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Anuncios.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Grupos de anuncios.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Creativos.</p>
      </td>
      <td>
        <p>-2333871387956621113</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Sitios.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Anunciantes.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Cuentas de anuncios.</p>
      </td>
      <td>
        <p>1825012532740770032</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Se utiliza para unirse a la tabla Ubicaciones.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>CATEGORY_01_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_02_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_03_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_04_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_05_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_06_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_07_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_08_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_09_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_10_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_11_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_12_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_13_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_14_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_15_KEY</td>
      <td>number(38,0)</td>
      <td>Se utiliza para unirse a la tabla Segmentos.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>number(38,0)</td>
      <td>Indica el tipo de hecho de la fila. 1 = Punto de contacto de atribución de comprador 2 = Coste 3 = Punto de contacto de comprador 4 = Punto de contacto del usuario 5 = Vista de página 6 = Sesión 7 = Envío de formulario 8 = Impresión</td>
      <td>3</td>
    </tr>
    <tr>
      <td>DATE</td>
      <td>fecha</td>
      <td>La fecha en la que se produjo el evento.</td>
      <td>28/08/2018</td>
    </tr>
    <tr>
      <td>TIMESTAMP</td>
      <td>timestamp_ntz</td>
      <td>La fecha y la hora en las que se produjo el evento.</td>
      <td>28/08/2018 19:39:15,000</td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó la fila por última vez.</p>
      </td>
      <td>
        <p>29/08/2018 00:46:47,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COST_IN_MICRO</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>La cantidad de costes en millones. El usuario tendrá que dividir el valor por 1 000 000.</p>
      </td>
      <td>
        <p>27370000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>El número de impresiones registradas para el grupo durante el día.</p>
      </td>
      <td>
        <p>340</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLICKS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>El número de clics registrados para el grupo durante el día.</p>
      </td>
      <td>4</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un primer contacto.</p>
      </td>
      <td>0.0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un contacto de creación de posibles clientes.</p>
      </td>
      <td>100,0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de U.</p>
      </td>
      <td>
        <p>100,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de W.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo de ruta completa.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo personalizado.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AMOUNT</p>
      </td>
      <td>
        <p>number(38,8)</p>
      </td>
      <td>
        <p>El importe de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>42000,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la oportunidad se ha movido a una fase clasificada como ganada.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la oportunidad se ha movido a una fase clasificada como cerrada.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>0060Z00000nFEfEQAW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de creación de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>31/08/2018 15:45:47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CLOSE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de cierre de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>31/12/2018 07:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó el registro de contacto, desde el sistema de origen.</p>
      </td>
      <td>28/04/2017 00:21:52,000</td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de contacto, desde el sistema de origen.</p>
      </td>
      <td>
        <p>0030Z00003ORVJmQAP</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>La dirección de correo electrónico del registro.</td>
      <td>personb@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>LEAD_CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó el registro de posible cliente, desde el sistema de origen.</p>
      </td>
      <td>
        <p>28/04/2017 00:21:52,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de posible cliente, desde el sistema de origen.</p>
      </td>
      <td>
        <p>00Q3100001GMPIsEAP</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por anuncio (es decir, para obtener coste de anuncio, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_ADVERTISER</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por anunciante (es decir, para obtener coste de anunciante, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_ACCOUNT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por cuenta (es decir, para obtener coste de cuenta, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_GROUP</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por grupo de anuncios (es decir, para obtener coste de grupo de anuncios, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CAMPAIGN</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por campaña (es decir, para obtener coste de campaña, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CHANNEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por canal (es decir, para obtener coste de canal, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CREATIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por creativo (es decir, para obtener coste de creativo, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_KEYWORD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por palabra clave (es decir, para obtener coste de palabra clave, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_PLACEMENT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por ubicación (es decir, para obtener coste de ubicación, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_SITE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila contiene coste que se puede sumar por sitio (es decir, para obtener coste de sitio, sume filas donde esta columna sea igual a verdadero).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se eliminó o no el registro, se usa como pista de auditoría.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>El valor de id. de la divisa para el registro.</td>
      <td>-3253183181619994799</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_FORM_SUBMITS {#biz-forms-submits}

Envíos de formulario capturados.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el envío de formularios.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-21-927280.9bc63c34482f4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies registrado en el momento en que se registró el envío de formularios.</p>
      </td>
      <td>
        <p>9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer id. de cookies del id. de visitante relacionado. Si el registro está marcado como is_duplicated = true, este campo será nulo.</p>
      </td>
      <td>
        <p>v_9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de sesión registrado en el momento en que se registró el envío del formulario. Si el registro está marcado como is_duplicated = true, este campo será nulo.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-24-1231230.9bc63c34482f</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de envío del formulario.</p>
      </td>
      <td>
        <p>06/08/2018 01:35:21,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>07/08/2018 23:09:52,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL donde se envió el formulario, sin parámetros de consulta.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL donde se envió el formulario, incluidos los parámetros de consulta.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento en que se envió el formulario.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el tipo de evento.</td>
      <td>
        <p>FormSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Dispositivo y navegador registrados en el momento del envío del formulario.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, como Gecko) versión/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el orden en que se produjo la vista de página en la sesión.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se utiliza para la auditoría y el procesamiento internos.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si el registro se considera un duplicado.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Se utiliza para el procesamiento interno.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico proporcionada en un formulario, tal y como se captura del JavaScript.</p>
      </td>
      <td>
        <p>personc@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el tipo de formulario enviado.</td>
      <td>
        <p>Chat</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Indica el método mediante el que se reconoció el formulario, como onSubmit o AjaxIntercept</p>
      </td>
      <td>
        <p>onSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_IDENTIFIER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor de id. del formulario.</td>
      <td>
        <p>-956012665</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Clave externa de la tabla URL.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_IMPRESSIONS {#biz-impressions}

Impresiones activadas y registradas. Esta tabla requiere una conexión DoubleClick y la opción Habilitar visualización establecida en Verdadero.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la impresión.</p>
      </td>
      <td>
        <p>6acd7b43290490fe5c53eed31281d09a|2020-05-18:22:20:59|0000|0|2869369052</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies registrado en el momento de la impresión.</p>
      </td>
      <td>08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer id. de cookies del id. de visitante relacionado.</p>
      </td>
      <td>v_08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de sesión registrado en el momento en que se registró la impresión.</p>
      </td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se realizó la impresión.</p>
      </td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL donde se realizó la impresión, sin parámetros de consulta.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL donde se realizó la impresión, incluidos los parámetros de consulta.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento de la impresión.</p>
      </td>
      <td>174.127.184.158</td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el tipo de evento.</td>
      <td>Impresión</td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Dispositivo y navegador registrados en el momento del envío del formulario.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, como Gecko) versión/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el orden en que se produjo la vista de página en la sesión.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se utiliza para la auditoría y el procesamiento internos.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si el registro se considera un duplicado.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Se utiliza para el procesamiento interno.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. En CRM, se denomina “Página del referente”.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE-RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. Una página de referente sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “Página de referente - Sin procesar”.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La ciudad resuelta desde la dirección IP.</p>
      </td>
      <td>
        <p>Seattle</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La región resuelta desde la dirección IP.</p>
      </td>
      <td>
        <p>Washington</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El país resuelto desde la dirección IP.</p>
      </td>
      <td>
        <p>Estados Unidos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de servicios de Internet, que utilizan los clientes con seguimiento de IP geográfica avanzado.</p>
      </td>
      <td>
        <p>AT&amp;T U-verse</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plataforma de anuncios [!DNL Marketo Measure] pudo resolverlo, por lo general, uno de nuestros socios de integración.</p>
      </td>
      <td>Google</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>aw.6601259029</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Market Measure Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>aw.6601259029.317738075</td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>Atribución de marketing</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>
        <p>68035923</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>
        <p>centurylink_banner_98121</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún creativo en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna palabra clave en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna palabra clave en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna palabra clave en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el explorador detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada del explorador en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la plataforma detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada de la plataforma en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista BIZ_FACTS.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_KEYWORDS {#biz-keywords}

Palabras clave importadas desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la palabra clave.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365.39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de la palabra clave, desde el sistema de origen.</td>
      <td>
        <p>39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó la palabra clave.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó la palabra clave.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna palabra clave en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ninguna palabra clave en la jerarquía de DoubleClick para las impresiones.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios para la palabra clave.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios para la palabra clave.</p>
      </td>
      <td>
        <p>Atribución de ingresos: B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña para la palabra clave.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña para la palabra clave.</p>
      </td>
      <td>
        <p>Atribución de ingresos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la palabra clave sigue o no activa en el sistema de origen.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la palabra clave se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>02/08/2018 06:37:29,000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>
        <p>02/08/2018 06:37:29,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave, desde el sistema de origen.</p>
      </td>
      <td>
        <p>[atribución de ingresos b2b]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la palabra clave debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Palabra clave”.</p>
      </td>
      <td>
        <p>Palabra clave</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para la palabra clave.</p>
      </td>
      <td>
        <p>Bing Ads</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la página de destino.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Valor anterior para URL_CURRENT.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>
        <p>La dirección URL de la página de destino con parámetros de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WORD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La frase de búsqueda que el usuario ha introducido.</td>
      <td>
        <p>atribución de ingresos b2b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de coincidencia que se encontró entre la frase de búsqueda y la palabra clave.</p>
      </td>
      <td>
        <p>Exacto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Utilizado para diagnósticos internos.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La plantilla de seguimiento de URL que [!DNL Marketo Measure] añadió a la palabra clave.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>-2712935512233520000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_LANDING_PAGES {#biz-landing-pages}

Páginas de destino importadas desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la página de destino.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de la cuenta de anuncios desde la que se importó la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El nombre de la cuenta de anuncios desde la que se importó la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para la página de destino, específicamente para DoubleClick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para la página de destino, específicamente para DoubleClick.</p>
      </td>
      <td>Marketing Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. del grupo de anuncios para la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El nombre del grupo de anuncios para la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de campaña para la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El nombre de campaña para la página de destino.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la fila.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEADS {#biz-leads}

Posibles clientes importados desde el sistema de origen.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de posible cliente, desde el sistema de origen.</p>
      </td>
      <td>
        <p>00Q0Z00001MZcj8UAD</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó por última vez el registro de posible cliente, desde el sistema de origen.</p>
      </td>
      <td>
        <p>27/08/2018 21:52:10,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se creó el registro de posible cliente, desde el sistema de origen.</p>
      </td>
      <td>27/08/2018 21:52:10,000</td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico del posible cliente, desde el sistema de origen.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>WEB_SITE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Sitio web introducido para el posible cliente, desde el sistema de origen, utilizado para la asignación de Lead2Account.</p>
      </td>
      <td>
        <p>adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Nombre de empresa introducido para el posible cliente, desde el sistema de origen, utilizado para la asignación de Lead2Account.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El origen en el que se creó el posible cliente.</p>
      </td>
      <td>
        <p>Anuncio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CONVERTED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el posible cliente se ha convertido o no en un contacto.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_OPPORTUNITY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la oportunidad relacionada una vez que el posible cliente se ha convertido.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que el posible cliente se convirtió en un contacto.</p>
      </td>
      <td>
        <p>27/08/2018 07:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto relacionado una vez que el posible cliente se ha convertido.</p>
      </td>
      <td>
        <p>0030Z00003Oyp25QAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta asignada. Requisitos: habilitar ABM</p>
      </td>
      <td>
        <p>0010Z0000236F9GQAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Fase actual del posible cliente, reconocida como una fase personalizada que se puede crear en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Demostración programada</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Todas las fases anteriores del posible cliente, reconocidas como fases personalizadas que se pueden crear en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>MQL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>El algoritmo de estimación de [!DNL Marketo Measure] que indica si un posible cliente se convertirá en función de la edad y la fase</p>
      </td>
      <td>
        <p>.290034</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_MODEL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>(obsoleto)</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_RESULTS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>(obsoleto)</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies de [!DNL Marketo Measure] utilizado para rellenar desde un socio de integración con el fin de asignar un evento sin conexión a una sesión web. Requisito: Habilitar seguimiento de llamadas: Verdadero</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se elimina o no en el sistema de origen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Lead_Type__c":"Sales Created", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Se utiliza para eliminar registros duplicados si se ha configurado una integración de CRM y Marketo. Si hay duplicados, el posible cliente de Marketo se marca como verdadero.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Indica si el registro procede de una integración de CRM o Marketo.</td>
      <td>CRM</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Asigna a una persona de una integración de Marketo con un posible cliente de una integración de CRM. Si existe una integración de CRM y Marketo, el valor es el id. correspondiente.</td>
      <td>1234</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEAD_STAGE_TRANSITIONS {#biz-lead-stage-transitions}

Transiciones de fase para posibles clientes o contactos.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la transición.</p>
      </td>
      <td>
        <p>ST_0030Z00003FhkRXQAZ__FT-1_TP2_Person_0030Z00003FhkRXQAZ_2018-08-27:17-05-45-9474800.0d5c18c29d7b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico proporcionada para el posible cliente o contacto relacionado.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente asociado a la transición.</p>
      </td>
      <td>
        <p>00Q3100001Fx6AlEAJ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado a la transición.</p>
      </td>
      <td>
        <p>0033100003Aq9grAAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del punto de contacto de comprador vinculado a la transición.</p>
      </td>
      <td>
        <p>TP2_Person_00Q3100001Fx6AlEAJ_2018-08-28:14-41-06-1674260.d00ceb09fbd3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que el registro realizó la transición a la fase.</p>
      </td>
      <td>
        <p>27/08/2018 16:05:34,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor de id. de la fase para la transición.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la fase para la transición.</p>
      </td>
      <td>
        <p>FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>La clasificación numérica de la fase, tal como se ordenó en la configuración de la asignación de fase de [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>5</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Se utiliza en el procesamiento interno para la indexación y ordenación de las fases de boomerang.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>Se utiliza en el procesamiento interno para la indexación y ordenación de las fases de boomerang.</td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el punto de contacto se considera pendiente y aún no se ha cerrado. Esto solo aparece para clientes con modelo de atribución de ruta completa.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila está vinculada a una transición de fase de hito. Por ejemplo, si hay 3 fases/entradas (FT, LC, MQL) y 4 puntos de contacto, el punto de contacto 1 sin una fase se considera “no transitorio”, por lo que el valor sería igual a verdadero.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de transición para la fase anterior, según la clasificación de la fase.</p>
      </td>
      <td>
        <p>28/11/2017 21:26:44,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de transición para la fase siguiente, según la clasificación de la fase.</p>
      </td>
      <td>
        <p>11/12/2017 22:39:17,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación del registro.</p>
      </td>
      <td>
        <p>28/08/2018 15:31:10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro de transición se considera o no eliminado.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_OPPORTUNITIES {#biz-opportunities}

Oportunidades importadas desde el sistema de origen.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>0060Z00000o89I4QAI</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>28/11/2017 21:26:44,000</td>
    </tr>
    <tr>
      <td>
        <p>CREATED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de creación de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>28/11/2017 21:26:44,000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta relacionada.</p>
      </td>
      <td>
        <p>001i000000qbyeoAAA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>Renovación de Marketo Measure</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la oportunidad se ha movido a una fase que se considera ganada.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la oportunidad se ha movido a una fase que se considera cerrada.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLOSE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de cierre prevista o real de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>28/08/2019 07:00:00,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_CUSTOM_MODEL_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>(obsoleto)</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AMOUNT</p>
      </td>
      <td>
        <p>number(38,8)</p>
      </td>
      <td>
        <p>Importe del acuerdo que se espera o se cierra de la oportunidad, desde el sistema de origen.</p>
      </td>
      <td>
        <p>8988,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente relacionado que se ha convertido en esta oportunidad.</p>
        <p>Tenga en cuenta que este campo no está establecido y devuelve nulo en Snowflake para todos los clientes.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El correo electrónico del posible cliente relacionado que se ha convertido en esta oportunidad.</p>
        <p>Tenga en cuenta que este campo no está establecido y devuelve nulo en Snowflake para todos los clientes.</p>
      </td>
      <td>
        <p>nulo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Si se utiliza la función de contacto principal, el id. del contacto relacionado aparece como la función de contacto principal.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Si se utiliza la función de contacto principal, el correo electrónico del contacto relacionado aparece como la función de contacto principal.</p>
      </td>
      <td>
        <p>personb@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>El algoritmo de estimación de [!DNL Marketo Measure] que indica si una oportunidad se cerrará en función de la edad y la fase</p>
      </td>
      <td>
        <p>0.8225108385086060000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La fase actual de la oportunidad, tal como se define en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Demostración de DM</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Una cadena de todas las fases por las que ha pasado la oportunidad, tal como se define en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Descubrimiento cualificado, Demostración programada</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro se elimina o no en el sistema de origen.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ISO_CODE</td>
      <td>varchar</td>
      <td>El código ISO para la divisa, importado desde el sistema de origen.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>El valor de id. de la divisa para el registro.</td>
      <td>4609512587744160000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Propiedades personalizadas que [!DNL Marketo Measure] ha importado desde el sistema de origen, en formato JSON.</td>
      <td>{"Opportunity_Location__c":"Seattle", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_OPP_STAGE_TRANSITIONS {#biz-opp-stage-transitions}

Transiciones de fase para oportunidades.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la transición.</p>
      </td>
      <td>
        <p>ST_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_Demo Scheduled-1_BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta asociada a la oportunidad.</p>
      </td>
      <td>
        <p>0013100001b44nTAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la oportunidad asociada a la transición.</p>
      </td>
      <td>
        <p>0060Z00000nEgjlQAC</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado a la transición.</p>
      </td>
      <td>
        <p>0030Z00003IjojKQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico proporcionada para el contacto relacionado.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del punto de contacto de atribución de comprador vinculado a la transición.</p>
      </td>
      <td>
        <p>BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que el registro realizó la transición a la fase.</p>
      </td>
      <td>
        <p>26/05/2018 07:29:43,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la fase para la transición.</p>
      </td>
      <td>
        <p>Demostración programada</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor de id. de la fase para la transición.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>La clasificación numérica de la fase, tal como se ordenó en la configuración de la asignación de fase de [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Se utiliza en el procesamiento interno para la indexación y ordenación de las fases de boomerang.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Se utiliza en el procesamiento interno para la indexación y ordenación de las fases de boomerang.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el punto de contacto se considera pendiente y aún no se ha cerrado. Esto solo aparece para clientes con modelo de atribución de ruta completa.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fila está vinculada a una transición de fase de hito. Por ejemplo, si hay 3 fases/entradas (FT, LC, MQL) y 4 puntos de contacto, el punto de contacto 1 sin una fase se considera “no transitorio”, por lo que el valor sería igual a verdadero.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de transición para la fase anterior, según la clasificación de la fase.</p>
      </td>
      <td>
        <p>16/07/2015 17:41:49,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de transición para la fase siguiente, según la clasificación de la fase.</p>
      </td>
      <td>
        <p>27/08/2018 19:40:52,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación del registro.</p>
      </td>
      <td>
        <p>28/08/2018 03:53:33,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el registro de transición se considera o no eliminado.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_PAGE_VIEWS {#biz-page-views}

Vistas de página recopiladas de las visitas web. Varias vistas de página pueden componer una sola sesión.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la vista de página.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies registrado en el momento en que se registró la vista de página.</p>
      </td>
      <td>
        <p>277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera cookie del id. de visitante relacionado.</p>
      </td>
      <td>
        <p>v_277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de sesión correlacionado con la vista de página.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se produjo la vista de página.</p>
      </td>
      <td>
        <p>19/08/2018 16:49:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>19/08/2018 16:55:37,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la vista de página, sin parámetros de consulta.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la vista de página, incluidos los parámetros de consulta.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo?hsCtaTracking=207219e9-87b6-4105-8f4b-0a3b62ae1af8%7C48060522-3aeb-4c72-8ce5-fd4b1017f069</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento en que se envió el formulario.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el tipo de evento.</td>
      <td>
        <p>Vista de página</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Dispositivo y navegador registrados en el momento del envío del formulario.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (X11; Linux x86_64; rv:52.0) Gecko/20100101 Firefox/52.0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Indica el orden en que se produjo la vista de página en la sesión.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Se utiliza para la auditoría y el procesamiento internos.</td>
      <td>
        <p>103532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si el registro se considera un duplicado.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Se utiliza para el procesamiento interno.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL desde donde se originó la vista de página, sin parámetros de consulta.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL desde donde se originó la vista de página, incluidos los parámetros de consulta.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU%20-%20CMO%20JT&amp;utm_content=CMOs%20Guide&amp;utm_term=lisu05091601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_TITLE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El título de la página.</p>
      </td>
      <td>
        <p>Guía de CMO para la descarga de atribución de marketing B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico proporcionada en un formulario, tal y como se captura del JavaScript.</p>
      </td>
      <td>personc@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Clave externa de la tabla URL.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Clave externa de la tabla URL.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>HAS_USER_CONSENT</td>
      <td>boolean</td>
      <td>Indica si el usuario ha aceptado el seguimiento. Falso significa que la vista de página se ha recopilado porque no se requiere el consentimiento del usuario. Verdadero significa que la vista de página se ha recopilado y que el usuario ha dado su consentimiento para que se le realice un seguimiento.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_PLACEMENTS {#biz-placements}

Tabla que almacena todas las ubicaciones descargadas de cualquier cuenta de anuncios conectada, un objeto de la integración de DoubleClick.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la ubicación.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de ubicación, desde el sistema de origen.</td>
      <td>10426699711</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó la ubicación.</p>
      </td>
      <td>fb. 106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó la ubicación.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para la ubicación, específicamente para DoubleClick.</p>
      </td>
      <td>300184624</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para la ubicación, específicamente para DoubleClick.</p>
      </td>
      <td>[!DNL Marketo Measure] Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de la ubicación en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima de la ubicación en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña para la ubicación.</p>
      </td>
      <td>ba.3284209.132855866</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña para la ubicación.</p>
      </td>
      <td>Marketing de canal</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la ubicación sigue o no activa en el sistema de origen.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la ubicación se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>02/08/2018 06:36:25,000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>02/08/2018 06:36:25,000</td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación, desde el sistema de origen.</p>
      </td>
      <td>Marketo</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la ubicación debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, para procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Ubicación”.</p>
      </td>
      <td>Publicación</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para la ubicación.</p>
      </td>
      <td>Bing Ads</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de creación del registro de Snowflake</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de modificación del registro de Snowflake</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de eliminación del registro de Snowflake si se ha eliminado</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENTS {#biz-segments}

Los valores de los segmentos tal como se define en la aplicación [!DNL Marketo Measure].

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el segmento.</p>
      </td>
      <td>
        <p>Nuevo negocio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del segmento.</p>
      </td>
      <td>
        <p>Nuevo negocio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENT_NAMES {#biz-segment-names}

Asigna el nombre del segmento personalizado a su valor de categoría. (Esto asigna los nombres de columna a los encabezados de columna Categoría 1-15 que se encuentran en las tablas de puntos de contacto).

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>CATEGORY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Indica la categoría a la que está asignada el nombre del segmento.</p>
      </td>
      <td>
        <p>CategoryOne</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>28/02/2022 18:12:35,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEGMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del segmento asignado a la categoría.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Indica si la categoría está en uso.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Indica si se elimina el registro.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_SESSIONS {#biz-sessions}

Sesiones procesadas desde las vistas de página. Varias vistas de página pueden conformar una sesión, y un solo id. de visitante se puede asociar a varias sesiones.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la sesión.</p>
      </td>
      <td>
        <p>2016-08-01:14-24-21-9079480.33163948f0a3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera cookie del id. de visitante relacionado.</p>
      </td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de cookies registrado de la sesión.</p>
      </td>
      <td>277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la sesión.</p>
      </td>
      <td>
        <p>01/08/2016 14:24:21,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>01/09/2018 03:49:10,000</p>
      </td>
    </tr>
    <tr>
      <td>IS_FIRST_SESSION</td>
      <td>boolean</td>
      <td>Indica si esta es la primera sesión del id. de visitante.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Canal atribuido a la sesión, tal como se especifica en las definiciones de canal establecidas en la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Búsqueda de pago.AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_TITLE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la página web.</p>
      </td>
      <td>
        <p>Salesforce Google Analytics | [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la primera vista de página de la sesión, sin parámetros de consulta.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la primera vista de página de la sesión, incluidos los parámetros de consulta.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics?_bt=83558988035&amp;_bk=google%20analytics%20salesforce&amp;_bm= p&amp;gclid=CMvd5YTLo84CFUI9gQodd-kLEQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL desde donde se originó la sesión, sin parámetros de consulta.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL desde donde se originó la sesión, incluidos los parámetros de consulta.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la página del referente.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor que el usuario introdujo en el explorador para su búsqueda y acabó en el sitio web.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Google Salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el origen que dio como resultado la sesión. Esto se puede analizar desde la dirección URL de utm_source o establecer en un proveedor de anuncios si [!DNL Marketo Measure] puede resolver un anuncio.</p>
      </td>
      <td>
        <p>Google AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_FORM</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la sesión contenía o no un relleno de formulario.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CHAT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la sesión contenía o no un chat en web.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_EMAIL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la sesión contenía o no una dirección de correo electrónico.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CRM_ACTIVITY</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la sesión provino o no de un registro de actividad de CRM.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DEVICE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El explorador y el sistema operativo del usuario durante la sesión.</p>
      </td>
      <td>
        <p>Chrome (65.0), Windows (6.1)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plataforma de anuncios [!DNL Marketo Measure] pudo resolverlo, por lo general, uno de nuestros socios de integración.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante desde el que se resolvió el anuncio, específicamente desde la conexión DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante desde el que se resolvió el anuncio, específicamente desde la conexión DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio desde el que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio desde el que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>Seminario web sobre planificación del presupuesto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios desde el que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios desde el que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>Salesforce - Google Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. desde el que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>aw.6601259029.321586235.23182235435</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre desde el que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>Promoción de invierno: verde</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del creativo desde el que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.83558988035</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo desde el que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Integrar GA y Salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Integrar Salesforce y Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La segunda línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Optimice para ingresos. Aprenda cómo.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La página de destino en la que se hace clic desde el anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre descriptivo de la dirección URL que se muestra en el anuncio de búsqueda, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>adobe.com/Salesforce-for-GA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la palabra clave desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.35934468937</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>google analytics salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de coincidencia encontrada entre la frase de búsqueda y la palabra clave comprada.</p>
      </td>
      <td>
        <p>Frase</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Analizado desde la dirección URL de utm_campaign.</p>
      </td>
      <td>
        <p>SU - Cuentas ABC - Capacidades de medios de pago</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Analizado desde la dirección URL de utm_source.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Analizado desde la dirección URL de utm_medium.</p>
      </td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TERM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Analizado desde la dirección URL de utm_term.</p>
      </td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Analizado desde la dirección URL de utm_content.</p>
      </td>
      <td>
        <p>Informe de referencia de AdWords de 2016</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La ciudad resuelta desde la dirección IP.</p>
      </td>
      <td>Vancouver</td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La región resuelta desde la dirección IP.</p>
      </td>
      <td>Columbia Británica</td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El país resuelto desde la dirección IP.</p>
      </td>
      <td>Canadá</td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El proveedor de servicios de Internet del usuario</p>
      </td>
      <td>
        <p>AT&amp;T U-verse</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección IP registrada en el momento de la sesión.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Determina si esta sesión se combinó con otra y debe eliminarse.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITES {#biz-sites}

Sitios importados desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el sitio.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. del sitio, desde el sistema de origen.</td>
      <td>39464932147</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se importó el sitio.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se importó el sitio.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para el sitio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para el sitio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima del sitio en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se espera que sea nulo, ya que no hay ningún grupo de anuncios por encima del sitio en ninguna jerarquía de anuncios.</p>
      </td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Id. de la campaña para el sitio.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña para el sitio.</p>
      </td>
      <td>Atribución de ingresos</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el sitio sigue o no activo en el sistema de origen.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el sitio se ha eliminado o no en el sistema de origen.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>02/08/2018 06:37:29,000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se importó por primera vez el registro desde el sistema de origen.</p>
      </td>
      <td>02/08/2018 06:37:29,000</td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio, desde el sistema de origen.</p>
      </td>
      <td>Ingresos</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el sitio debe actualizarse o no para el etiquetado de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, utilizado para el procesamiento interno).</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Campo de diagnóstico, utilizado para el procesamiento interno.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Sitio”.</p>
      </td>
      <td>Sitio</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el sitio.</p>
      </td>
      <td>AdWords</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITE_LINKS {#biz-site-links}

Vínculos de sitios desde cualquier cuenta de anuncios conectada.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el vínculo del sitio</p>
      </td>
      <td>
        <p>aw.6601259029.285077795.1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td>
        <p>1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios conectada para el vínculo del sitio</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios conectada para el vínculo del sitio</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante para el vínculo del sitio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante para el vínculo del sitio, específicamente para DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios para el vínculo del sitio</p>
      </td>
      <td>aw.6601259029.208548635.16750166675</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios para el vínculo del sitio</p>
      </td>
      <td>Marca - Principal</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de campaña para el vínculo del sitio</p>
      </td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de campaña para el vínculo del sitio</p>
      </td>
      <td>
        <p>Marca</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el vínculo del sitio sigue o no activo en la cuenta de anuncios</p>
      </td>
      <td>
        <p>TRUE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el vínculo del sitio se ha eliminado o no en la cuenta de anuncios</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha de la última modificación de la fila</p>
      </td>
      <td>
        <p>02/08/2018 06:36:50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que Marketo Measure descargó por primera vez el vínculo del sitio [!DNL Marketo Measure]</p>
      </td>
      <td>
        <p>02/08/2018 06:36:50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del vínculo del sitio</p>
      </td>
      <td>Vínculo A</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si el vínculo del sitio debe actualizarse o no para obtener el etiquetado de Marketo Measure</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td></td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El objeto o entidad principal de esta tabla. En este caso, “Vínculo del sitio”.</p>
      </td>
      <td>
        <p>Vínculo del sitio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del proveedor de anuncios para el vínculo del sitio</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL de la página de destino.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td>
        <p>http://adobe.com/b2b-marketing-attribution?_bt =</p>
        <p>{creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Valor anterior para URL_CURRENT.</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Decoración de la dirección URL con los parámetros de [!DNL Marketo Measure].</p>
        <p>(Campo de diagnóstico, para procesamiento interno).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de creación del registro de Snowflake</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de modificación del registro de Snowflake</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha de eliminación del registro de Snowflake si se ha eliminado</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_STAGE_DEFINITIONS {#biz-stage-definitions}

La lista de fases tal como se importan o definen en la aplicación [!DNL Marketo Measure].

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para la fase.</p>
      </td>
      <td>
        <p>01J3100000QE753EAD</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>22/08/2018 17:27:27,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la fase.</p>
      </td>
      <td>
        <p>Verbal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_INACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si la fase se considera inactiva.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IN_CUSTOM_MODEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fase está seleccionada para rastrear en el modelo personalizado.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_BOOMERANG</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fase está seleccionada para rastrear como una fase de boomerang.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_TRANSITION_TRACKING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si la fase está seleccionada para rastrear transiciones.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_STATUS</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Estado de la fase, tal como se define en la asignación de fase de la aplicación [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>Abrir</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FROM_SALESFORCE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si la fase se importa desde un sistema de origen externo.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DEFAULT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Indica si la fase está definida como predeterminada.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clasificación numérica de la fase, utilizada para ordenar las fases en orden transitorio.</p>
      </td>
      <td>
        <p>53</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se ha eliminado o no la fase.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_TOUCHPOINTS {#biz-touchpoints}

Puntos de contacto de comprador, todos los puntos de contacto asociados a un posible cliente o contacto. Esta tabla estará vacía si los puntos de contacto de posible cliente o los puntos de contacto están deshabilitados.

<table>
  <tbody>
    <tr>
      <th>Columna</th>
      <th>Tipo de datos</th>
      <th>Descripción</th>
      <th>Datos de muestra</th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el punto de contacto de comprador (BT).</p>
      </td>
      <td>
        <p>TP2_Person_00Q0Z000013e2PYUAY_2018-08-27:20-04-40-5655690.1ee8567c175a</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>29/08/2018 22:29:30.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección de correo electrónico asociada al BT.</td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del contacto asociado al BT.</p>
      </td>
      <td>0030Z00003K5bpKQAR</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta asociada al BT.</p>
      </td>
      <td>
        <p>0013100001lSLScAAO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del posible cliente asociado al BT.</p>
      </td>
      <td>
        <p>00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>UNIQUE_ID_PERSON</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El registro de persona principal relacionado con un posible cliente o contacto.</p>
      </td>
      <td>
        <p>Person_00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del punto de contacto del usuario que generó el BT.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-08-29:18-14-53-8102030.10df92cbb414</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>El id. del visitante asociado al BT.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha del punto de contacto.</p>
      </td>
      <td>
        <p>27/08/2018 20:04:40,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de actividad, visita web, formulario web, chat en web, llamada telefónica, campaña [CRM] o actividad [CRM]. En CRM, se denomina “Tipo de punto de contacto”.</p>
      </td>
      <td>
        <p>Formulario web</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El canal al que corresponde el punto de contacto, tal como se especifica en las definiciones de canales personalizados en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Canal de marketing - Ruta”.</p>
      </td>
      <td>Social.LinkedIn</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la primera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>ABC</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la segunda categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>Sí</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY3</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la tercera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>Otro</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY4</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la cuarta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td>
        <p>Socio</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY5</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la quinta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY6</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la sexta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la séptima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la octava categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la novena categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY10</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la décima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY11</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la undécima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY12</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la duodécima categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY13</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El valor del segmento para la decimotercera categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY14</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la decimocuarta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY15</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor del segmento para la decimoquinta categoría a la que corresponde el punto de contacto, tal como se especifica en las definiciones de segmentos en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Segmentos”.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el explorador detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>Chrome</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada del explorador en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>68</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la plataforma detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Windows</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada de la plataforma en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>10_12</td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. En CRM, se denomina “Página de destino”.</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. Una página de destino sin procesar contendrá todos los parámetros de consulta en la dirección URL. En CRM, se denomina “Página de destino - Sin procesar”.</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU_COM_Demand_ Skills&amp;utm_content=DGPM&amp;utm_term=lisu03151846&amp;_bl=66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. En CRM, se denomina “Página del referente”.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. Una página de referente sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “Página de referente - Sin procesar”.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/feed</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Puntos de contacto, sino en la tabla Form_Submits. En CRM, se denomina “URL del formulario”.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>FORM_PAGE_RAW</td>
      <td>varchar</td>
      <td>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Puntos de contacto, sino en la tabla Form_Submits. Una página de formulario sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “URL del formulario - Sin procesar”.</td>
      <td>https://info.adobe.com/demo?hsCtaTracking=98adcc2f-afe2-40c4-9d79-40dcc41663ee%7C3cfaa909-39cb-4f5d-93eb-be05de6b0180</td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se realizó el envío del formulario.</p>
      </td>
      <td>
        <p>20/06/2017 01:06:41,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la ciudad detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Nueva York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la región detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Nueva York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el país detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Estados Unidos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el medio que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_medium. O bien, si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “cpc” o “visualización”.</p>
      </td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el origen que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_source, establecida genéricamente como “Campaña de CRM” si se sincronizó desde CRM, o si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “Google AdWords” o “Facebook”. En CRM, se denomina “Origen del punto de contacto”.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor que el usuario introdujo en el explorador para su búsqueda y acabó en el sitio web. Dependiendo de las compras de palabras clave, esto puede o no coincidir con las palabras clave compradas en la plataforma Búsqueda de pago.</p>
      </td>
      <td>
        <p>atribución de medida de marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plataforma de anuncios [!DNL Marketo Measure] pudo resolverlo, por lo general, uno de nuestros socios de integración.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>li.502664737</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>MM SC 2016_14605342_3/7-3/31/16</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Marketo Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>li.502664737.138949954</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>SU - Cuentas COM - Capacidades de demanda</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>aw.6601259029.317738075.23105327435</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>Atribución de marketing: general</td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>Seminario web sobre presupuesto: barra lateral</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>li.502664737.138949954.66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>La generación de posibles clientes se ha realizado</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La segunda línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Descargue la guía definitiva sobre marketing de canal: https://lnkd.in/e9xYj5M</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La página de destino en la que se hace clic desde el anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>https://image-store.slidesharecdn.com/d29165c0-1e0b-4ffc-a494-d2c77e7cd4a6-large.jpeg</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre descriptivo de la dirección URL que se muestra en el anuncio de búsqueda, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>marektomeasure.com/guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>__GAId__lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda)</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de coincidencia encontrada entre la frase de búsqueda y la palabra clave comprada.</p>
      </td>
      <td>
        <p>Amplia</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el primer contacto del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto de creación de posibles clientes del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto de creación de oportunidades del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el contacto cerrado del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>STAGES_TOUCHED</td>
      <td>varchar</td>
      <td>Este campo está en desuso. Utilice las tablas Stage_Transitions para obtener información sobre la fase.</td>
      <td>nulo</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto rellenó o no un formulario durante la sesión.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el primer contacto de impresiones del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un primer contacto (consulte Is_First_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque es un contacto de creación de posibles clientes (consulte Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de U (consulte Is_First_Touch e Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un contacto en forma de W (consulte Is_First_Touch, Is_Lead_Creation_Touch e Is_Opp_Creation_Touch). Se espera que sea 0, ya que se trata de un BT.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo de ruta completa (consulte See Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch e Is_Closed_Touch). Se espera que sea 0, ya que se trata de un BT.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_MODEL_PERCENTAGE</td>
      <td>number(22,19)</td>
      <td>El porcentaje calculado asignado a este punto de contacto porque forma parte de un modelo personalizado (consulte Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch e Is_Closed_Touch). Se espera que sea 0, ya que se trata de un BT.</p>
      </td>
      <td>0</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se elimina este punto de contacto.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>-9004910726709710000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_URLS {#biz-urls}

Adición de direcciones URL de páginas de destino, páginas de referente y vistas de página.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección URL completa.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/strategic-marketing-plangoals</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SCHEME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Comunicación segura de la página web a través de la red.</p>
      </td>
      <td>
        <p>https</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HOST</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El dominio de la dirección URL, con cualquier subdominio.</p>
      </td>
      <td>
        <p>www.adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PORT</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El puerto de un host de Internet, opcional en una URL.</p>
      </td>
      <td>
        <p>584</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PATH</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La parte de la dirección URL que señala a una ubicación específica del host.</p>
      </td>
      <td>
        <p>/blog/strategic-marketing-plangoals</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Clave externa de la vista Biz_Facts.</p>
      </td>
      <td>
        <p>5686109553536636820</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_USER_TOUCHPOINTS {#biz-user-touchpoints}

Todos los puntos de contacto creados a partir de cualquier evento vinculado a un correo electrónico.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Un id. único para el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>05/09/2018 23:30:53,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La dirección de correo electrónico asociada al punto de contacto del usuario.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la sesión que creó el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_MEMBER_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del miembro de campaña que creó el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>00v0Z00001VTgv1QAD</p>
      </td>
    </tr>
    <tr>
      <td>CRM_ACTIVITY_ID</td>
      <td>varchar</td>
      <td>El id. de la actividad que creó el punto de contacto del usuario.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>
        <p>CRM_EVENT_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del evento que creó el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>00U0Z00000pCZmyUAG</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CRM_TASK_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la tarea que creó el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>00T0Z00004Qbd1jUAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la impresión que creó el punto de contacto del usuario.</p>
      </td>
      <td>00T0Z00004Qbd1jUAB</td>
    </tr>
    <tr>
      <td>IS_FIRST_KNOWN_TOUCH</td>
      <td>boolean</td>
      <td>Indica si este punto de contacto se trata o no como el primer contacto del recorrido de oportunidad.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>El primer id. de cookies del id. de visitante relacionado.</td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se produjo el punto de contacto del usuario.</p>
      </td>
      <td>
        <p>05/01/2018 16:47:02,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de actividad, visita web, formulario web, chat en web, llamada telefónica, campaña [CRM] o actividad [CRM]. En CRM, se denomina “Tipo de punto de contacto”.</p>
      </td>
      <td>
        <p>Formulario web</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El canal al que corresponde el punto de contacto, tal como se especifica en las definiciones de canales personalizados en la aplicación [!DNL Marketo Measure]. En CRM, se denomina “Canal de marketing - Ruta”.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el explorador detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Firefox</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada del explorador en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>33</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la plataforma detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la versión detectada de la plataforma en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. En CRM, se denomina “Página de destino”.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera página de destino de la sesión que dio como resultado un punto de contacto. Una página de destino sin procesar contendrá todos los parámetros de consulta en la dirección URL. En CRM, se denomina “Página de destino - Sin procesar”.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+ marketo+%maeasure%27s+Pipeline+Marketing+Blog%29</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. En CRM, se denomina “Página del referente”.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Por lo general, la página de destino externa inmediatamente antes de que el usuario acceda al sitio web. Una página de referente sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “Página de referente - Sin procesar”.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Attribution_Touchpoints, sino en la tabla Form_Submits. En CRM, se denomina “URL del formulario”.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El primer formulario registrado en una sesión que dio como resultado un punto de contacto. Los envíos de formularios posteriores no aparecerán en la tabla Attribution_Touchpoints, sino en la tabla Form_Submits. Una página de formulario sin procesar puede contener parámetros de consulta en la dirección URL. En CRM, se denomina “URL del formulario - Sin procesar”.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation?utm_source=linkedin&amp;utm_medium=paid&amp;utm_content=sfskill&amp;utm _campaign=Content%20-%20AdWords%20Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>
        <p>timestamp_ntz</p>
      </td>
      <td>
        <p>La fecha en la que se realizó el envío del formulario.</p>
      </td>
      <td>
        <p>03/06/2015 17:49:10,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la ciudad detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Oakland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, la región detectada en la que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>California</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>A partir de la dirección IP y el JavaScript, el país detectado en el que se encontraba el usuario durante la sesión.</p>
      </td>
      <td>
        <p>Estados Unidos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el medio que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_medium. O bien, si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “cpc” o “visualización”.</p>
      </td>
      <td>
        <p>pago</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>Se utiliza para definir el origen que dio como resultado el punto de contacto. Esto se puede analizar desde la dirección URL de utm_source, establecida genéricamente como “Campaña de CRM” si se sincronizó desde CRM, o si [!DNL Marketo Measure] puede resolver un anuncio, pueden ser valores como “Google AdWords” o “Facebook”. En CRM, se denomina “Origen del punto de contacto”.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El valor que el usuario introdujo en el explorador para su búsqueda y acabó en el sitio web. Dependiendo de las compras de palabras clave, esto puede o no coincidir con las palabras clave compradas en la plataforma Búsqueda de pago.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La plataforma de anuncios [!DNL Marketo Measure] pudo resolverlo, por lo general, uno de nuestros socios de integración.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Cuenta</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anunciante de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del sitio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la ubicación de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica al administrador de campañas de DoubleClick.</p>
      </td>
      <td>
        <p>obstáculo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la campaña de la cuenta de anuncios desde la que se resolvió el anuncio.</p>
      </td>
      <td>
        <p>Marca</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del grupo de anuncios de la cuenta de anuncios desde la que se resolvió el anuncio. Esto solo se aplica a Google AdWords.</p>
      </td>
      <td>
        <p>Marca - Principal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del anuncio de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica al administrador de campañas de DoubleClick y Facebook (visualización).</p>
      </td>
      <td>Seminario web sobre presupuesto: barra lateral</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.195329631298</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre del creativo de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Sitio oficial</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La primera línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Planificación y atribución de ingresos</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La segunda línea del creativo del anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>Descubra por qué más de 250 empresas eligen [!DNL Marketo Measure] para la atribución de marketing. ¡Consiga una demostración!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>La página de destino en la que se hace clic desde el anuncio de búsqueda, extraída de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>http://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre descriptivo de la dirección URL que se muestra en el anuncio de búsqueda, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El id. de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.46267805426</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El nombre de la palabra clave adquirida en la compra de Búsqueda de pago, extraído de la cuenta de anuncios desde la que se resolvió el anuncio. Esto se aplica a Google AdWords y Bing Ads (búsqueda)</p>
      </td>
      <td>
        <p>[marketo]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>
        <p>El tipo de coincidencia encontrada entre la frase de búsqueda y la palabra clave comprada.</p>
      </td>
      <td>
        <p>Exacto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto rellenó o no un formulario durante la sesión.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si este punto de contacto se trata o no como el primer contacto de impresiones del recorrido de oportunidad.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Indica si se elimina o no el punto de contacto.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Clave externa de la vista Biz_Facts.</td>
      <td>-5269090762570690000</td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

### BIZ_WEB_HOST_MAPPINGS {#biz-web-host-mappings}

Tabla de asignación para asignar el id. de sesión de [!DNL Marketo Measure] al ECID de Adobe y al id. de Munckin.

<table>
  <tbody>
    <tr>
      <th>
        <p>Columna</p>
      </th>
      <th>
        <p>Tipo de datos</p>
      </th>
      <th>
        <p>Descripción</p>
      </th>
      <th>
        <p>Datos de muestra</p>
      </th>
    </tr>
    <tr>
      <td>
        <p>ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>Un id. único para el registro de asignación.</td>
      <td>
        <p>0d643578c0c74753eff91abe668ed328|2020-06-17:19:03:36|0002|0|568668</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de cookies registrado de [!DNL Marketo Measure].</td>
      <td>0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El primer id. de cookies del id. de visitante relacionado.</td>
      <td>v_0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>
        <p>varchar</p>
      </td>
      <td>El id. de sesión de [!DNL Marketo Measure].</td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se registró la asignación.</td>
      <td>
        <p>17/06/2020 19:03:36,000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>La fecha en la que se modificó el registro por última vez.</p>
      </td>
      <td>
        <p>17/06/2020 19:03:36,000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE</td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección URL de la vista de página, sin parámetros de consulta.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_RAW</td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección URL de la vista de página, incluidos los parámetros de consulta.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html?x=nGfrBF&amp;utm_medium=cpc&amp;utm_source=intensify</p>
      </td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>
        <p>varchar</p>
      </td>
      <td>La dirección IP registrada.</td>
      <td>
        <p>159.203.142.127</p>
      </td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>
        <p>varchar</p>
      </td>
      <td>Indica el tipo de evento.</td>
      <td>
        <p>HostMapping</p>
      </td>
    </tr>
    <tr>
      <td>USER_AGENT_STRING</td>
      <td>
        <p>varchar</p>
      </td>
      <td>Dispositivo y navegador registrados en el momento de la vista de página.</td>
      <td>
        <p>Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, como Gecko) Chrome/79.0.3945.130 Safari/537.36</p>
      </td>
    </tr>
    <tr>
      <td>CLIENT_SEQUENCE</td>
      <td>varchar</td>
      <td>Indica el orden en que se produjo la vista de página en la sesión.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>CLIENT_RANDOM</td>
      <td>varchar</td>
      <td>Se utiliza para la auditoría y el procesamiento internos.</td>
      <td>566868</td>
    </tr>
    <tr>
      <td>IS_DUPLICATED</td>
      <td>boolean</td>
      <td>Indica si el registro se considera un duplicado.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_PROCESSED</td>
      <td>boolean</td>
      <td>Se utiliza para el procesamiento interno.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>MAPPING_TYPE</td>
      <td>varchar</td>
      <td>El tipo de id. asignado al id. de cookies de [!DNL Marketo Measure].</td>
      <td>Adobe_OrgId_Ecid</td>
    </tr>
    <tr>
      <td>MAPPING_ORD_ID</td>
      <td>varchar</td>
      <td>Id. de la organización Adobe IMS.</td>
      <td>8CC867C25245ADC30A490D4C</td>
    </tr>
    <tr>
      <td>MAPPING_COOKIE_ID</td>
      <td>varchar</td>
      <td>ECID de Adobe para el id. de organización proporcionado.</td>
      <td>09860926390077352923264316157493772857</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se creó el registro en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se modificó el registro por última vez en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>La fecha en la que se marcó el registro como eliminado en Snowflake.</td>
      <td>01/01/2020 01:01:00,000</td>
    </tr>
  </tbody>
</table>

## Consultas de ejemplo {#sample-queries}

**¿Cuántos Buyer Touchpoints (BT) había para cada canal/subcanal el mes pasado?**

```
--Note: This query can quickly be modified to show Buyer Attribution Touchpoint (BAT) counts by switching the biz_touchpoints table to the biz_attribution_touchpoints table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,trim(split(ch.name,'.')[1])  as subchannel
      ,count(bt.id)                 as buyer_touchpoint_count
  from biz_user_touchpoints     ut
       left outer join
       biz_touchpoints          bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_channels             ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
   and ut.touchpoint_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
group by 1,2
```

**¿Cuántos ingresos atribuidos para cada canal se cerraron el mes pasado, para el modelo de atribución de ruta completa?**

```
--Note: This query does not perform any currency conversion.  If your data contains multiple currencies, you will need to add in logic to perform the conversion to the desired currency using the biz_conversion_rates table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,sum(opp.amount*(bat.full_path_percentage/100))   as attributed_revenue
  from biz_user_touchpoints         ut
       inner join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       inner join
       biz_opportunities            opp
        on bat.opportunity_id       = opp.id
       and opp._deleted_date        is null
       and opp.is_closed            = true
       and opp.is_won               = true
       and opp.close_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
       left outer join
       biz_channels                 ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
group by 1
```

**¿Cuál es el recorrido completo de una persona?  (Muestre todos los puntos de contacto de una sola dirección de correo electrónico).**

```
select ut.touchpoint_date
      ,ut.marketing_touch_type
      ,listagg(distinct ifnull(sdl.stage_name,sdo.stage_name),',')           as touchpoint_position
  from biz_user_touchpoints         ut
       left outer join
       biz_touchpoints              bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       left outer join
       biz_lead_stage_transitions   lst
        on lst.touchpoint_id        = bt.id
       and lst._deleted_date        is null
       and lst.is_pending           = false
       and lst.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdl
        on lst.stage_id             = sdl.id
       and sdl._deleted_date        is null
       left outer join
       biz_opp_stage_transitions    ost
        on ost.touchpoint_id        = bat.id
       and ost._deleted_date        is null
       and ost.is_pending           = false
       and ost.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdo
        on ost.stage_id             = sdo.id
       and sdo._deleted_date        is null
 where ut._deleted_date     is null
   and ut.email             = [email address]
group by 1,2
order by 1
```

**Muestre todos los Buyer Attribution Touchpoints(BAT) y sus ingresos atribuidos para una sola oportunidad.**

>[!NOTE]
>
>Esta consulta devuelve los ingresos atribuidos para el modelo de forma w. Cambie el modelo actualizando el campo en el cálculo de ingresos atribuidos.

```
select bat.id
      ,bat.touchpoint_date
      ,bat.email
      ,opp.amount*(bat.w_shape_percentage/100)             as attributed_revenue
      ,listagg(osd.stage_name,', ')                        as touchpoint_position
  from biz_opportunities               opp
       inner join
       biz_attribution_touchpoints     bat
        on bat.opportunity_id      = opp.id
       and bat._deleted_date       is null
       left outer join
       biz_opp_stage_transitions       ost
        on ost.touchpoint_id       = bat.id
       and ost._deleted_date       is null
       and ost.is_pending          = false
       and ost.is_non_transitional = false
       left outer join
       biz_stage_definitions            osd
        on ost.stage_id             = osd.id
       and osd._deleted_date        is null
 where opp._deleted_date    is null
   and opp.id               = [opportunity id]
group by 1,2,3,4
order by touchpoint_date
```

[Volver al inicio](#data-warehouse-schema)
