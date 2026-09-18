---
title: Customer Journey Analytics Report Builder
description: Descrive come utilizzare Report Builder per richiamare i dati di Customer Journey Analytics in Excel per la generazione di rapporti ricorrenti.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

Questo articolo illustra come utilizzare [!DNL Report Builder] per implementare il seguente [caso d&#39;uso per l&#39;esportazione dei dati](overview.md):

* Generazione di rapporti ad hoc e ricorrenti

## Introduzione

[!DNL Report Builder] [!DNL Report Builder] è un componente aggiuntivo di Microsoft Excel che richiama i dati di Customer Journey Analytics in blocchi di dati in una cartella di lavoro. Gli utenti aziendali che hanno già familiarità con Excel possono creare report ricorrenti senza imparare a utilizzare Analysis Workspace o SQL.

## Ulteriori informazioni

Ogni blocco di dati in [!DNL Report Builder] restituisce fino a 50.000 righe. Per recuperare altre righe, utilizza le opzioni **[!UICONTROL Pagina]** e **[!UICONTROL Righe]** per estrarre i dati in pagine sequenziali oltre il limite di 50.000 righe. Per ulteriori informazioni, vedere [Dimensioni filtro](/help/report-builder/filter-dimensions.md).

Puoi pianificare la consegna di una cartella di lavoro tramite e-mail o esportarla in una destinazione cloud, ad esempio Amazon S3, Google Cloud Platform o Azure. Consulta [Pianificare le cartelle di lavoro condividendo tramite e-mail](/help/report-builder/schedule-reportbuilder.md) e [Pianificare le cartelle di lavoro esportando in destinazioni cloud](/help/report-builder/report-builder-export.md) per ulteriori informazioni.

Per un&#39;introduzione alla configurazione e all&#39;utilizzo di [!DNL Report Builder], vedere [Panoramica di Report Builder](/help/report-builder/rb-overview.md).
