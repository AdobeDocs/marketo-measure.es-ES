---
description: '[!DNL Marketo Measure] Guía de implementación definitiva: [!DNL Marketo Measure] - Documentación del producto'
title: '[!DNL Marketo Measure] Guía de implementación definitiva'
hide: true
hidefromtoc: true
feature: Integration, Tracking, Attribution
source-git-commit: d8c1962aaf1830970c4cbde4385d05ca4ad3139e
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 6%

---

# [!DNL Marketo Measure] Guía de implementación de Ultimate {#marketo-measure-ultimate-implementation-guide}

FRASE INTRODUCTORIA

## Diferencias principales al utilizar Ultimate con respecto a los niveles estándar {#main-differences-when-using-ultimate-over-standard-tiers}

Importar datos B2B a través de AEP: Se espera que los especialistas en marketing traigan sus datos B2B (por ejemplo: cuenta, oportunidad, contacto, posible cliente, campaña, miembro de la campaña, actividad) a través de AEP. Realiza la ingesta desde casi cualquier fuente de datos y desde varias fuentes de datos del mismo tipo para incorporar todos los datos para la atribución.

* Se utiliza con casi cualquier CRM, no solo con Salesforce y Dynamics.
* Conectar varias instancias de CRM o instancias de MAP a una instancia de Marketo Measure.
* Incluya datos de participación y registro de seminarios web de terceros.

Las conexiones directas de CRM y Marketo Engage ya no están disponibles para Ultimate.

* Ultimate no devuelve los datos al CRM. Los clientes pueden consumir datos del almacén de datos.
* Los especialistas en marketing seguirán trayendo datos de Ad Platform a través de conexiones directas y rastreando actividades web a través de Marketo Measure javascript.

Los usuarios finales se aprovisionarán en AEP. Si ya tienen AEP, no volveremos a aprovisionar una nueva instancia.

* La versión de AEP aprovisionada incluirá todos los conectores de origen, el modelado de datos de esquema, los conjuntos de datos, el servicio de consultas ad hoc y un destino solo para Marketo Measure.

Más información sobre [Marketo Measure Ultimate](/help/marketo-measure-ultimate/marketo-measure-ultimate-overview.md).

## Esquemas y conjuntos de datos {#schemas-and-datasets}

>[!NOTE]
>
>Desproteger [Bloques de creación de un esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#building-blocks-of-a-schema) para obtener una descripción general de esquemas, clases y grupos de campos.

**Esquema XDM = Clase + Grupo de campos de esquema&#42;**

* Los campos obligatorios no se pueden cambiar. Los clientes pueden crear y agregar campos personalizados según sea necesario.
* Ejemplo de nombre de campo basado en jerarquía: accountOrganization.annualRevenue.amount

&#42; _Un esquema consta de una clase y cero o más grupos de campos de esquema. Esto significa que puede componer un esquema de conjunto de datos sin utilizar grupos de campos._

![](assets/marketo-measure-ultimate-implementation-guide-1.png)

[Información general sobre conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html): todos los datos introducidos correctamente en AEP se conservan dentro del lago de datos como conjuntos de datos. Un conjunto de datos es una construcción de almacenamiento y administración para una colección de datos, normalmente una tabla, que contiene un esquema (columnas) y campos (filas).

## Creación de un esquema {#creating-a-schema}

Se recomienda utilizar una utilidad de generación automática para crear 10 esquemas B2B estándar.

* Pasos para descargar y configurar la utilidad [se puede encontrar aquí](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces.html#set-up-b2b-namespaces-and-schema-auto-generation-utility).

Para los que tengan un _**Derechos de CDP**_: Cree esquemas en la página Orígenes.

* Desde un origen, seleccione Añadir datos > Usar plantillas

![](assets/marketo-measure-ultimate-implementation-guide-2.png)

* Seleccione una cuenta y todas las plantillas B2B para crear 10 esquemas B2B estándar.

![](assets/marketo-measure-ultimate-implementation-guide-3.png)

## Flujos de datos {#dataflows}

[Resumen de flujos de datos](https://experienceleague.adobe.com/docs/experience-platform/dataflows/home.html)

**Pasos para crear un flujo de datos:**

1. Seleccione un origen.
1. Seleccione una cuenta existente o cree una cuenta.
1. Seleccione un tipo de datos de la lista de tipos disponibles para importar desde el origen.
1. Seleccione un conjunto de datos existente o cree uno nuevo.
1. Asigne los campos del origen al esquema.

   >[!NOTE]
   >
   >* Si asigna un tipo de esquema a otro idéntico, se realiza automáticamente.
   >* También puede importar la asignación desde otro flujo del sistema.
   >* Puede asignar un campo de origen a varios campos de destino, pero no puede hacer lo contrario.
   >* Puede crear campos calculados (por ejemplo, funciones de asignación de preparación de datos).

   >[!CAUTION]
   >
   >* Puede editar un flujo de datos, pero los datos no se rellenan cuando se cambia una asignación.
   >* Si un campo obligatorio es NULL, se rechazará todo el flujo.

   >[!NOTE]
   >
   >[Requisito de integridad de datos de Marketo Measure Ultimate](help/marketo-measure-ultimate/data-integrity-requirement.md)

1. Establezca una cadencia de carga de datos.
1. Revisar y completar.
1. Consulte la página &quot;Estado de la cuenta&quot; en la configuración de la IU de Measure para ver el estado del flujo de datos.

**Monitorización:**

Página Orígenes > Flujos de datos para comprobar el estado de los flujos de datos

* Para ver los detalles de actividad de un conjunto de datos, simplemente haga clic en él.
* Para ver los errores de flujo de datos, seleccione un flujo de datos, elija una ejecución de flujo de datos y haga clic en &quot;Previsualización de diagnósticos de error&quot;.

## Inspección de datos {#data-inspection}

Ejemplo: Requisito de integridad de datos de Marketo Measure Ultimate Este documento incluye campos obligatorios para cada XDM, así como consultas de inspección. Se publicará en ExL. - YA ESTÁ ETIQUETADO ARRIBA - POST DE NUEVO???

Opción 1: para ejecutar consultas directamente desde la interfaz de usuario, acceda a la pestaña Consultas en Administración de datos.

![](assets/marketo-measure-ultimate-implementation-guide-4.png)

Opción 2: [Descargar y utilizar PSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/psql.html) (más rápido y fiable)

## Activar conjunto de datos para Marketo Measure {#activate-dataset-for-marketo-measure}

Antes de empezar, vaya a la sección &quot;Experience Platform > Asignación de zona protegida&quot; en la configuración de la interfaz de usuario de Measure y asigne una zona protegida.

>[!CAUTION]
>
>Esto no se puede cambiar una vez seleccionado.

1. En AEP, vaya a &quot;Destinos > Página de Marketo Measure&quot; para exportar conjuntos de datos.
1. Configure el destino.
1. Activar conjunto de datos.
1. Consulte la página &quot;Estado de la cuenta&quot; en la configuración de la IU de Measure para ver el estado del flujo de datos.

>[!NOTE]
>
>* Los datos de una entidad determinada (por ejemplo, Account) de una fuente determinada solo pueden entrar en un conjunto de datos. Cada conjunto de datos solo puede incluirse en un flujo de datos. Las infracciones detendrán el flujo de datos en el tiempo de ejecución.
>* Elimine todo el destino en AEP para eliminar datos en Measure. Al deshabilitar solo se detendrán las nuevas exportaciones de datos y se conservarán los datos antiguos.
>* La configuración de la medida será básicamente la misma, pero algunas partes, como Asignación de etapas, tendrán un aspecto diferente.
>* Un nuevo flujo de datos tarda unas horas en generar una ejecución de flujo y, a continuación, se produce a intervalos regulares por hora.

En Measure, la moneda predeterminada debe configurarse en la sección &quot;Moneda&quot;

* Si utiliza varias monedas, el esquema de tasa de conversión de moneda debe rellenarse en AEP para que lo leamos y utilicemos para las conversiones.

**Asignación de fase:**

No importamos automáticamente las fases de los datos de usuario, por lo que todas las fases deben asignarse manualmente.

* Los usuarios pueden asignar etapas desde diferentes fuentes.

![](assets/marketo-measure-ultimate-implementation-guide-5.png)

Si las fases no están asignadas, el sistema no funcionará porque no habrá a dónde ir los datos.

**Reglas de miembro de campaña:**

Debe elegir un conjunto de datos y establecer reglas para cada uno.

**Reglas de eventos de experiencia:**

Debe elegir un conjunto de datos y seleccionar tipos de actividades.

* Todavía no se admiten actividades personalizadas.
* Si el cliente tiene actividades que no se ajustan a las opciones disponibles, sugerimos categorizarlas como &quot;Momentos interesantes&quot; y utilizar campos personalizados para distinguirlas.

**Canales sin conexión:**

* No aplicamos reglas de asignación de canales específicas para conjuntos de datos, por lo que sería global.
* Finalmente, tenemos que hacer coincidir tanto el tipo de campaña de CRM como el canal, pero por ahora, podemos asignar el nombre del canal a ambos campos como solución alternativa.
* **Reglas de canal: los datos rellenados no tendrán datos de transición de fase.**

La configuración del punto de contacto y del segmento sigue siendo la misma.
