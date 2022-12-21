---
unique-page-id: 30082018
description: Sincronización de cookies retrasada - [!DNL Marketo Measure] - Documentación del producto
title: Sincronización de cookies retrasada
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Sincronización de cookies retrasada {#delayed-cookie-sync}

Esta modificación al valor predeterminado [!DNL Marketo Measure] Javascript sirve para proporcionar [!DNL bizible.js] Compatibilidad con API, para que pueda configurar el JS de modo que almacene temporalmente las actividades de usuario de los visitantes, pero no envíe la información al [!DNL Marketo Measure] hasta que el usuario da su consentimiento para hacerlo.

## Instrucciones {#how-to}

Reemplazar el valor predeterminado [!DNL bizible.js] etiqueta de script con lo siguiente:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

El atributo data-permission-button-id=&quot;ConsentButtonId&quot; indica [!DNL bizible.js] para no enviar datos analíticos hasta que se haga clic en un elemento HTML con ese id.

Como alternativa, los clientes pueden configurar la variable [!UICONTROL data-permission-button-id] no existe (por ejemplo, &quot;foobar&quot;) y utilice la siguiente API para indicar [!DNL bizible.js] que el usuario ha consentido:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>El consentimiento del usuario se guarda en la cookie , lo que significa que una vez que el usuario ha dado su consentimiento una vez que no hay necesidad de realizar esta llamada en ninguna página posterior.

## Limitación {#limitation}

Porque [!DNL bizible.js] guarda temporalmente las actividades web no enviadas en las cookies de origen de los clientes y el tamaño de las cookies de origen es limitado, solo se pueden guardar tres solicitudes no enviadas en un momento dado.

Si ya hay tres solicitudes pendientes, se ignorará cualquier actividad posterior; esto sirve para conservar la primera vista de página, que contiene información valiosa del referente.
