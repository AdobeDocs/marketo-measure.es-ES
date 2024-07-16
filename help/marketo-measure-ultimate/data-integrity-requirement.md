---
description: '[!DNL Marketo Measure] requisito de integridad de datos definitivo - [!DNL Marketo Measure]'
title: '''[!DNL Marketo Measure] Requisito sobre la integridad de datos de Ultimate'
feature: Integration, Tracking, Attribution
exl-id: 8ad001d0-e9fe-46f5-b808-d6203a55a229
source-git-commit: 54695bd795fe9bdb58d97b6b0762b9e9fe8f17cf
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 86%

---

# [!DNL Marketo Measure] Requisito sobre la integridad de datos de Ultimate {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure] valida los conjuntos de datos de AEP entrantes para asegurarse de que los datos sean suficientes y coherentes para la atribución. Si no se cumple el requisito de integridad de datos, el sistema [!DNL Marketo Measure] rechaza el conjunto de datos. Este artículo detalla el requisito de integridad de los datos, proporciona ejemplos de consultas para la inspección de datos y recomienda una solución para los campos obligatorios con un valor nulo.

## Objeto de entidad {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>Clase XDM</th>
    <th>Grupo de campos XDM</th>
    <th>Ruta XDM</th>
    <th>Tipo de XDM</th>
    <th>Campo de fuente de datos</th>
    <th>¿Es esto obligatorio?</th>
    <th>Notas</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>Cuenta</strong> (cuenta de Salesforce, compañía y/o cuenta con nombre para Marketo)</td>
    </tr>
    <tr>
      <td rowspan="6">Cuenta empresarial de XDM</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>P. ej., 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>Detalles de la cuenta empresarial de XDM</td>
      <td>accountName</td>
      <td>cadena</td>
      <td>Nombre</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Campaña</strong> (campaña para Salesforce, programa para Marketo)</td>
    </tr>
    <tr>
      <td rowspan="8">Campaña empresarial de XDM</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>P. ej., 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignName</td>
      <td>cadena</td>
      <td>Nombre</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignType</td>
      <td>cadena</td>
      <td>CampaignType</td>
      <td>No</td>
      <td>Para la asignación de canales</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">Detalles de la campaña empresarial de XDM</td>
      <td>channelName</td>
      <td>cadena</td>
      <td>ChannelName</td>
      <td>No</td>
      <td>Para la asignación de canales</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignStartDate</td>
      <td>fecha-hora</td>
      <td>StartDate</td>
      <td>No</td>
      <td>Para el coste de campaña</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignEndDate</td>
      <td>fecha-hora</td>
      <td>EndDate</td>
      <td>No</td>
      <td>Para el coste de campaña</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>número</td>
      <td>Coste</td>
      <td>No</td>
      <td>Para el coste de campaña</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>cadena</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>No</td>
      <td>Para el coste de campaña</td>
    </tr>
    <tr>
      <td colspan="7"><strong>Miembro de campaña</strong> (miembro de la campaña para Salesforce, miembros del programa para Marketo)</td>
    </tr>
    <tr>
      <td rowspan="14">Miembros de la campaña empresarial de XDM</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>P. ej., 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>cadena</td>
      <td>ID de posible cliente o ID de contacto</td>
      <td>Sí</td>
      <td>
        <p>Por ejemplo: 333, según la tabla de fuente de datos, es el ID de posible cliente o el ID de contacto.</p>
        <p>Clave externa del posible cliente o contacto</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>cadena</td>
      <td>ID de campaña</td>
      <td>Sí</td>
      <td>
        <p>P. ej., 55555.</p>
        <p>Clave externa de la campaña</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">Detalles del miembro de la campaña empresarial de XDM</td>
      <td>b2b.personType</td>
      <td>cadena</td>
      <td>"Posible cliente" o "Contacto"</td>
      <td>Sí</td>
      <td>Según la tabla de fuente de datos, se debe configurar como “Posible cliente” o “Contacto”. Se recomienda configurarlo como "Contacto" en la mayoría de los casos de uso</td>
    </tr>
    <tr>
      <td></td>
      <td>memberStatus</td>
      <td>cadena</td>
      <td>Estado</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>HasResponded</td>
      <td>booleano</td>
      <td>HasResponded</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>FirstRespondedDate</td>
      <td>fecha-hora</td>
      <td>FirstRespondedDate</td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Persona</strong> (contacto o posible cliente de Salesforce, personas para Marketo)</td>
    </tr>
    <tr>
      <td>Perfil individual de XDM</td>
      <td rowspan="11">Detalles de la persona empresaria de XDM</td>
      <td>b2b.personKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>Por ejemplo: 333, según la tabla de fuente de datos, es el ID del posible cliente o el ID del contacto</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>cadena</p>
        <p>correo electrónico</p>
      </td>
      <td>Correo electrónico</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>cadena</td>
      <td>Estado</td>
      <td><b><i>Sí, solo para la personType del posible cliente</i></b></td>
      <td>Solo es necesario si b2b.personType es "Posible cliente"</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>booleano</td>
      <td>IsConverted</td>
      <td><b><i>Sí, solo para la personType del posible cliente</i></b></td>
      <td>Solo es necesario si b2b.personType es "Posible cliente"</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>cadena</td>
      <td>"Posible cliente" o "Contacto"</td>
      <td>Sí</td>
      <td>Según la tabla de fuente de datos, se debe configurar como “Posible cliente” o “Contacto”. Se recomienda configurarlo como "Contacto" en la mayoría de los casos de uso</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>cadena</td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">Componentes de la persona empresaria de XDM</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>No</td>
      <td>
        <p>Por ejemplo: 123@999-abc-888.Marketo.</p>
        <p>El conjunto de campos sourceAccountKey solo es “obligatorio” para registros de contacto verdaderos, definidos como registros de persona vinculados a la cuenta. S se omite, el conjunto de datos no se rechaza, pero los resultados de atribución se desactivan.</p>
        <p>personComponents es una matriz, pero Marketo Measure solo toma el primer elemento personComponents[0]</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>cadena</td>
      <td>ID de cuenta</td>
      <td>No</td>
      <td>
        <p>P. ej., 123.</p>
        <p>Clave externa de la cuenta</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>No</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>No</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong>Oportunidad</strong> (oportunidad para Salesforce, oportunidades para Marketo)</td>
    </tr>
    <tr>
      <td rowspan="13">Oportunidad de negocio de XDM</td>
      <td></td>
      <td>oportunidadKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>p. ej.: 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>P. ej., 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>cadena</td>
      <td>ID de cuenta</td>
      <td>Sí</td>
      <td>
        <p>P. ej., 123.</p>
        <p>Clave externa de la cuenta</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityName</td>
      <td>cadena</td>
      <td>Nombre</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityStage</td>
      <td>cadena</td>
      <td>Fase</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityType</td>
      <td>cadena</td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">Detalles de oportunidad de negocio de XDM</td>
      <td>isWon</td>
      <td>booleano</td>
      <td>IsWon</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isClosed</td>
      <td>booleano</td>
      <td>IsClosed</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>expectedCloseDate</td>
      <td>fecha</td>
      <td>CloseDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.amount</td>
      <td>número</td>
      <td>Monto</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.currencyCode</td>
      <td>
        <p>cadena</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Función de contacto de oportunidad (solo es necesario si piensa utilizar la función de contacto de oportunidad como grupo comprador para la atribución)</strong></td>
    </tr>
    <tr>
      <td rowspan="16">Relación de persona de oportunidad de negocio de XDM</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>cadena</td>
      <td>Identificación del contacto</td>
      <td>Sí</td>
      <td>
        <p>p. ej., 333.</p>
        <p>Clave externa del contacto</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>booleano</td>
      <td>IsPrimary</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>oportunidadKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>p. ej.: 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>cadena</td>
      <td>Identificación de oportunidad</td>
      <td>Sí</td>
      <td>
        <p>p. ej., 77777.</p>
        <p>Clave externa de oportunidad</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>p. ej.: 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceID</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>p. ej., 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personRole</td>
      <td>cadena</td>
      <td>Función</td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Tasa de conversión (solo es necesaria si utiliza varias monedas; solo se puede activar un conjunto de datos de tasa de conversión en Marketo Measure)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">Conversión</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>p. ej.: 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>p. ej., 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>fecha-hora</td>
      <td>CreatedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>fecha-hora</td>
      <td>ModifiedDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>IsDeleted</td>
      <td>booleano</td>
      <td></td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">Detalles de la tasa de conversión de moneda</td>
      <td>conversionRate</td>
      <td>número</td>
      <td>ConversionRate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>fecha</td>
      <td>NextStartDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startDate</td>
      <td>fecha</td>
      <td>StartDate</td>
      <td>Sí</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOCode</td>
      <td>cadena</td>
      <td>ISOCode</td>
      <td>Sí</td>
      <td>Por ejemplo, EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetISOCode</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>El código de moneda predeterminado establecido en Marketo Measure, por ejemplo, está en USD.</td>
    </tr>
  </tbody>
</table>

## Requisitos de datos de conversión de moneda {#currency-conversion-data-requirements}

**Moneda predeterminada**: en Marketo Measure, todos los ingresos y costos se convierten a una moneda predeterminada en el momento de generar los informes. Debe haber un registro con la misma cobertura de fechas para la propia moneda de destino (por ejemplo, USD a USD) con una tasa de conversión de 1.

**Tasas de conversión**: Cada par (moneda de origen, moneda de destino) puede tener múltiples tasas de conversión para diferentes períodos de fecha. Las tasas deben cubrir todo el lapso de tiempo desde 0001-01-01 hasta 9999-12-31, según el objeto DatedConversionRate de Salesforce.

**Intervalo de fecha**:
* No se superponen intervalos de fechas dentro de un conjunto de tasas (moneda de origen, moneda de destino) (por ejemplo, 2023-01-01 a 2023-02-01 y 2023-01-01 a 2024-01-01).
* No hay espacios entre intervalos de fechas. La fecha de inicio es inclusiva y la fecha de finalización es exclusiva.

<p>

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>Clase XDM</th>
    <th>Grupo de campos XDM</th>
    <th>Ruta XDM</th>
    <th>Tipo de XDM</th>
    <th>Campo de fuente de datos</th>
    <th>¿Es esto obligatorio?</th>
    <th>Notas</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>Actividad</strong></td>
    </tr>
    <tr>
      <td rowspan="3">ExperienceEvent de XDM</td>
      <td></td>
      <td>_id</td>
      <td>cadena</td>
      <td>ID</td>
      <td>Sí</td>
      <td>Sí</td>
    </tr>
    <tr>
      <td></td>
      <td>eventType</td>
      <td>cadena</td>
      <td>Tipo de actividad</td>
      <td>Sí</td>
      <td>Sí</td>
    </tr>
    <tr>
      <td></td>
      <td>marca de tiempo</td>
      <td>fecha-hora</td>
      <td>Fecha de la actividad</td>
      <td>Sí</td>
      <td>Sí</td>
    </tr>
    <tr>
      <td></td>
      <td>Identificador de persona</td>
      <td>personKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>cadena</td>
      <td>ID de posible cliente o ID de contacto</td>
      <td>Sí</td>
      <td>
        <p>Por ejemplo: 333, según la tabla de fuente de datos, es el ID de posible cliente o el ID de contacto.</p>
        <p>Clave externa del posible cliente o contacto</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Añadir a la campaña</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.addToCampaign</td>
      <td>Por ejemplo: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>cadena</td>
      <td>ID de campaña</td>
      <td>Sí, solo para el tipo leadOperation.addToCampaign</td>
      <td>
        <p>P. ej., 55555.</p>
        <p>Clave externa de la campaña</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.addToCampaign</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.addToCampaign</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>El estado en progresión de la campaña ha cambiado</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.campaignProgression</td>
      <td>Por ejemplo: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>cadena</td>
      <td>ID de campaña</td>
      <td>Sí, solo para el tipo leadOperation.campaignProgression</td>
      <td>
        <p>P. ej., 55555.</p>
        <p>Clave externa de la campaña</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.campaignProgression</td>
      <td>Por ejemplo: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>cadena</td>
      <td></td>
      <td>Sí, solo para el tipo leadOperation.campaignProgression</td>
      <td>Por ejemplo: Marketo</td>
    </tr>
  </tbody>
</table>

## Tipo de ExperienceEvent admitido {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>Tipo de evento</th>
    <th>Tipo de evento XDM</th>
    <th>Descripción</th>
  </tr>
  <tbody>
    <tr>
      <td>Nuevo posible cliente</td>
      <td>leadOperation.newLead</td>
      <td>Se utiliza para registrar la creación y los detalles de un nuevo posible cliente de marketing</td>
    </tr>
    <tr>
      <td>Convertir posible cliente</td>
      <td>leadOperation.convertLead</td>
      <td>Se utiliza cuando un posible cliente de marketing se convierte en un contacto calificado de ventas que se asigna a un usuario de ventas</td>
    </tr>
    <tr>
      <td>Momento interesante</td>
      <td>leadOperation.interestMoment</td>
      <td>Se utiliza para realizar el seguimiento de actividades de alto valor de clientes potenciales</td>
    </tr>
    <tr>
      <td>Completar formulario</td>
      <td>web.formFilledOut</td>
      <td>Se utiliza para capturar datos cuando una persona rellena un formulario en una página web</td>
    </tr>
    <tr>
      <td>Cancelar suscripción a los correos electrónicos</td>
      <td>directMarketing.emailUnsuscribed</td>
      <td>Se utiliza para capturar datos cuando una persona cancela la suscripción de un correo electrónico</td>
    </tr>
    <tr>
      <td>Abrir correo electrónico</td>
      <td>directMarketing.emailOpened</td>
      <td>Se utiliza para capturar datos cuando una persona abre un correo electrónico de marketing</td>
    </tr>
    <tr>
      <td>Hacer clic en el correo electrónico</td>
      <td>directMarketing.emailClicked</td>
      <td>Se utiliza para capturar datos cuando una persona hace clic en un vínculo en un correo electrónico de marketing</td>
    </tr>
    <tr>
      <td>Cambio de estado en progreso</td>
      <td>leadOperation.statusInCampaignProgressChanged</td>
      <td>Se utiliza para capturar datos cuando cambia el estado de un posible cliente en una campaña</td>
    </tr>
    <tr>
      <td>Añadir al programa de participación (añadir a Nurture)</td>
      <td>leadOperation.addToCampaign</td>
      <td>Se utiliza para añadir una persona a la campaña específica.</td>
    </tr>
  </tbody>
</table>

Utilice el tipo de evento &quot;Momento interesante&quot; para los tipos de evento no admitidos en la tabla anterior. Agregue un campo personalizado para indicar el subtipo &quot;Momento interesante&quot;.

## Ejemplos de consultas para la inspección de datos {#query-examples-for-data-inspection}

A continuación, se muestra una lista de ejemplos de consultas para inspeccionar conjuntos de datos ingeridos en el lago de datos de AEP. Para utilizarlos con sus conjuntos de datos, reemplace el nombre de tabla de los ejemplos de consulta siguientes por el nombre real de la tabla del conjunto de datos.

Esperamos que todos los recuentos sean 0.

Para el campo personType, se espera que solo haya valores “Posible cliente” o “Contacto” y que no haya ningún valor nulo.

Para todos los registros de personas de &quot;Contacto&quot;, se espera que haya una clave externa de cuenta.

Para los registros de personas “Posibles clientes”, no existe una clave externa de cuenta y tampoco es necesaria. Si decide introducir registros de persona &quot;Posible cliente&quot; como registros de persona de &quot;contacto&quot; (se recomienda), no se requiere una clave externa de cuenta en esos registros de persona.

### Cuenta empresarial de XDM {#xdm-business-account}

```
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### Campaña empresarial de XDM {#xdm-business-campaign}

```
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### Miembro de campaña empresarial de XDM {#xdm-business-campaign-member}

```
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### Persona empresaria de XDM {#xdm-business-person}

```
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### Oportunidad de negocio de XDM {#xdm-business-opportunity}

```
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### ExperienceEvent de XDM {#xdm-experienceevent}

```
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### Conversión {#conversion}

```
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from currency_conversion_rate where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from currency_conversion_rate where extSourceSystemAudit.lastUpdatedDate is null;
```

## Solución recomendada para los campos obligatorios con valor NULL {#recommended-solution-for-required-fields-with-a-null-value}

Se recomienda utilizar un campo calculado en la asignación de campos para establecer el campo de forma predeterminada en un valor no NULL. A continuación, se muestran dos ejemplos:

* Si el OpportunityName de algunos registros de oportunidad es nulo, cree y utilice el siguiente campo calculado en la asignación de campos
   * `iif(name != null && trim(name) != "", name, "Unknown")`

* Si el leadOperation.campaignProgression.campaignID de algunos registros experienceevent es nulo, cree y utilice el siguiente campo calculado en la asignación de campos
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`
