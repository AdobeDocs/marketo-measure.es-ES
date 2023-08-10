---
unique-page-id: 30082018
description: 'Sincronización de cookies retrasada: [!DNL Marketo Measure] - Documentación del producto'
title: Sincronización de cookies retrasada
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Sincronización de cookies retrasada {#delayed-cookie-sync}

Esta modificación a la predeterminada [!DNL Marketo Measure] Javascript sirve para proporcionar [!DNL bizible.js] Compatibilidad con API, de modo que puede configurar el JS para almacenar temporalmente las actividades de usuario de los visitantes, pero no para enviar la información a [!DNL Marketo Measure] hasta que el usuario dé su consentimiento para hacerlo.

## Procedimientos {#how-to}

Reemplazar el predeterminado [!DNL bizible.js] etiqueta de script con lo siguiente:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

El atributo data-permission-button-id=&quot;ConsentButtonId&quot; indica [!DNL bizible.js] para no enviar datos analíticos hasta que se haga clic en un elemento HTML con ese id.

Alternativamente, los clientes pueden configurar la variable [!UICONTROL data-permission-button-id] sea algo inexistente (por ejemplo, &quot;foobar&quot;) y utilice la siguiente API para indicarlo [!DNL bizible.js] que el usuario ha dado su consentimiento:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>El consentimiento del usuario se guarda en la cookie, lo que significa que, una vez que el usuario ha dado su consentimiento, no es necesario realizar esta llamada en ninguna página posterior.

## Limitación {#limitation}

Porque [!DNL bizible.js] guarda temporalmente las actividades web no enviadas en las cookies de origen de los clientes. el tamaño de las cookies de origen es limitado y solo se pueden guardar tres solicitudes no enviadas en un momento determinado.

Si ya hay tres solicitudes pendientes, se ignorarán las actividades posteriores; esto es para conservar la primera vista de página, que contiene información valiosa del referente.
