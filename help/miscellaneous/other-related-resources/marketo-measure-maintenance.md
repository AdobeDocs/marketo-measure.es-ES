---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] Mantenimiento - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Mantenimiento"
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# [!DNL Marketo Measure] Mantenimiento {#marketo-measure-maintenance}

[!DNL Marketo Measure] extrae casi todo lo que necesita de su CRM diariamente, pero hay algunas tareas de mantenimiento que querrá programar regularmente para mantener [!DNL Marketo Measure] zumbando y obteniendo la información más precisa posible.

**Sincronizar puntos de contacto del comprador para nuevas campañas sin conexión (2 x/mes)**

Como aprendió durante la incorporación, [!DNL Marketo Measure] obtiene información sobre los esfuerzos de marketing sin conexión mediante la sincronización con las campañas de CRM. A medida que su organización inicie nuevas campañas, asegúrese de habilitar los puntos de contacto del comprador para cada campaña según corresponda. Consulte [este artículo](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)para obtener más información.

**Cargar gastos para todos los canales (1x/mes)**

Para aprovechar las capacidades completas de informes de ingresos y ROI para[!DNL Marketo Measure], debe decir [!DNL Marketo Measure] cuánto gasta en cada uno de sus canales y subcanales de marketing. Se recomienda designar el propietario de cada canal o subcanal y hacer que esas personas informen de gastos a una sola parte responsable de cargar la nueva información de coste mensualmente.

Actualice la memoria sobre cómo cargar la información de costes leyendo [este artículo](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**Actualizar lista de dominios para rastrear (1x/mes)**

Marketo Measure rastrea todas las páginas y subdominios donde nuestro Javascript está activo, pero solo para los dominios que conocemos. Si acaba de depurar un nuevo dominio, se ha expandido internacionalmente o ha cambiado su dominio principal, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;} para asegurarnos de actualizar su cuenta en consecuencia.

**Revisar la precisión de la asignación de canales personalizada (1x/mes)**

Durante la incorporación, se configura la asignación de canales personalizada para los esfuerzos de marketing en línea y sin conexión. A medida que evolucionen su estrategia de marketing y el uso de la medida de Marketo, debe prestar atención a esa lógica de asignación para garantizar que todos los puntos de contacto se clasifiquen adecuadamente.

Recuerde: [!DNL Marketo Measure] vuelve a procesar los datos al editar la lógica de asignación, por lo que no podrá cambiar estas reglas más de una vez cada 7 días.

Referencia [este artículo](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) para la configuración en línea, [este artículo](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) para la configuración sin conexión, y esta lista de prácticas recomendadas recopiladas por nuestros clientes:

* Revise los puntos de contacto que están cayendo actualmente en cualquier canal &quot;Otro&quot; o &quot;NULL&quot; que haya configurado. Si procede, actualice la lógica de asignación para volver a categorizar esos puntos de contacto en canales más precisos.
* Revise los puntos de contacto que están cayendo en sus canales directos. Si a algunas de sus campañas de marketing por correo electrónico u otras iniciativas les faltan parámetros de UTM, existe una buena posibilidad de que el tráfico se agrupe incorrectamente en un canal directo. Considere la posibilidad de actualizar los parámetros de la UTM para capturar el origen de referencia.

**Evaluar la configuración de supresión de puntos de contacto (1x/trimestre)**

Si está viendo muchos puntos de contacto que preferiría que no se tuvieran en cuenta en su artículo de atribución (de un [!DNL Login] o [!DNL Unsubscribe forms], una página de ofertas de empleo o una aplicación interna, por ejemplo), es posible que desee evaluar la configuración de supresión de puntos de contacto existente. Una vez al trimestre, localice cualquier grupo de puntos de contacto que esté creando ruido innecesario y actualice correctamente la lógica de supresión. [Aquí tiene un artículo útil](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  con el procedimiento.

**Revise la asignación de escenarios personalizada para comprobar la precisión (1x/trimestre) (si corresponde)**

Si está utilizando alguna [!UICONTROL Posible cliente], [!UICONTROL Contacto]o [!UICONTROL Oportunidades] , también puede haber personalizado a qué parte de la canalización se asignan esas etapas y si se incluyen o no en un modelo de atribución personalizado. Una vez al trimestre, visite [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) para actualizar la memoria en la asignación de escenario personalizada y asegurarse de que realiza un seguimiento preciso de sus etapas personalizadas.

**Comparar el modelo de aprendizaje automático con la ponderación del modelo personalizado (1x/trimestre) (si procede)**

Si tiene licencia para el [!DNL Marketo Measure] Modelo personalizado, también dispone de datos de nuestro Modelo de aprendizaje automático (MLM) en [!UICONTROL Configuración] > [!UICONTROL Configuración de atribución]. El MLM calcula la importancia de cada etapa mediante datos de punto de contacto de la cuenta y puede ayudarle a decidir cómo asignar el peso de atribución en el modelo personalizado. Se recomienda comparar el MLM con el modelo personalizado una vez al trimestre y analizar las implicaciones de los posibles cambios en el modelo personalizado con el SM.

Para obtener más información sobre la variable [!DNL Marketo Measure] Modelo de aprendizaje automático, salir [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
