---
description: Solicitudes de privacidad - [!DNL Marketo Measure]
title: Solicitudes de privacidad
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 25%

---

# Solicitudes de privacidad {#privacy-requests}

Este documento proporciona información general sobre la administración de solicitudes de privacidad de datos individuales que puede enviar a [!DNL Marketo Measure] a través de la interfaz de usuario de [!DNL Privacy Service] y la API de **[!DNL Privacy Service]**.

Puede enviar solicitudes individuales para acceder a los datos de consumidores y eliminarlos de [!DNL Marketo Measure] de dos maneras:

* A través de la [[!DNL Privacy Service] IU](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target="_blank"}.
* Mediante la API **[!DNL Privacy Service]**. Consulte la documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target="_blank"} y la referencia de la API [aquí](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es){target="_blank"} admite dos tipos de solicitudes: acceso a datos y eliminación de datos.

Veamos cómo se pueden crear solicitudes de acceso y eliminación.

## Configuración necesaria para enviar solicitudes para Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

Para realizar solicitudes de acceso y eliminación de datos para [!DNL Marketo Measure], debe:

1. Identificar lo siguiente:

   a. ID de organización de IMS

   b. Dirección de correo electrónico de la persona sobre la que desea actuar

   Un ID de organización de IMS es una cadena alfanumérica de 24 caracteres anexada a @AdobeOrg. Si el equipo de marketing o el administrador interno del sistema de Adobe no conocen el ID de organización de IMS de su organización, póngase en contacto con el servicio de atención al cliente de Adobe a la dirección gdprsupport@adobe.com. Necesita el ID de organización de IMS para enviar solicitudes a la API de privacidad.

1. En [!DNL Privacy Service], puede enviar solicitudes de Acceso y Eliminación a [!DNL Marketo Measure] y comprobar el estado de las solicitudes existentes.

## Valores de campo requeridos en solicitudes JSON de [!DNL Marketo Measure] {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContext&quot;:

* &quot;espacio de nombres&quot;: **imsOrgID**
* &quot;valor&quot;: `<Your IMS Org ID Value>`

&quot;usuarios&quot;:

* &quot;acción&quot;: [!UICONTROL acceder] o eliminar
* &quot;userID&quot;:
   * &quot;namespace&quot;: email
   * &quot;tipo&quot;: estándar
   * &quot;valor&quot;: `<Data Subject's Email Address>`

&quot;incluir&quot;:

* **marketoMeasure** (que es el producto de Adobe que se aplica a la solicitud)

&quot;regulación&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra** o **nzpa_nzl** (que es la norma de privacidad que se aplica a la solicitud)

## Ejemplo 1: Solicitud de eliminación de RGPD {#gdpr-delete-request}

Solicitud JSON

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

Respuesta JSON

```text
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## Ejemplo 2: Solicitud de acceso a CCPA {#ccpa-access-request}

Solicitud JSON

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

Respuesta JSON

```text
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
