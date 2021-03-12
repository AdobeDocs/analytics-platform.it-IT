---
title: Panoramica dei componenti
description: Scopri i componenti offerti da CJA e come utilizzarli nel reporting.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 46%

---


# Panoramica dei componenti

I componenti sono funzionalità di Customer Journey Analytics che possono essere utilizzate nei rapporti o che integrano le funzioni di reporting. Puoi gestire questi componenti procedendo come segue:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le tue credenziali Adobe ID.
2. Passa a [!UICONTROL Components] > [!UICONTROL Components] nel menu intestazione.

Puoi gestire i seguenti componenti:

* [**Filtri**](filters/filters-overview.md): Escludere parti dei dati per concentrarsi su elementi dimensionali comuni
* [**Metriche calcolate:**](calc-metrics/calc-metr-overview.md) utilizza metriche e formule come nuovi componenti da utilizzare nel reporting
* [**Intervalli di date:**](date-ranges/overview.md) personalizza e perfeziona gli intervalli di date offerti da Analysis Workspace
* [**Progetti:**](/help/analysis-workspace/home.md) organizza e gestisci i progetti in Analysis Workspace

## Componenti Analysis Workspace

I componenti in Analysis Workspace sono metriche, dimensioni, segmenti e granularità temporali da trascinare su un progetto. I componenti creati, come ad esempio gli intervalli di date personalizzati, vengono aggiunti a questi pannelli.

Per accedere al pannello Componenti, fai clic su **[!UICONTROL Components]** nella barra a sinistra. Puoi passare da un pannello all’altro (pannello vuoto, pannello [Pannello a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Informazioni rapide](/help/analysis-workspace/c-panels/quickinsight.md) o pannello [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e Componenti utilizzando le icone della barra a sinistra o i [tasti di scelta rapida](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Consulta [Creare un progetto](/help/analysis-workspace/home.md) per informazioni sull&#39;utilizzo dei componenti in un progetto.

## Azioni dei componenti

Sono disponibili diversi metodi di gestione dei componenti (singolarmente o selezionandone più di uno). Fai clic con il pulsante destro del mouse su un componente oppure fai clic su **[!UICONTROL Actions]** in alto nell’elenco dei componenti.

>[!NOTE]
>
>Queste azioni non si applicano ai componenti Time.

| Azione del componente | Descrizione |
|--- |--- |
| Tag | Organizzare o gestire i componenti tramite l’applicazione di tag. Questa azione si riflette nel rispettivo Component Manager (Gestione componenti), ad esempio Analytics > Componenti > Segmenti o Analytics > Componenti > Progetti |
| Preferito | Aggiungere il componente all’elenco dei preferiti. Questa azione si riflette nel rispettivo Component Manager (Gestione componenti), ad esempio Analytics > Componenti > Segmenti o Analytics > Componenti > Progetti. |
| Approva | Approvare il componente per renderlo canonico. Questa azione si riflette nel rispettivo Component Manager (Gestione componenti), ad esempio Analytics > Componenti > Segmenti o Analytics > Componenti > Progetti |
| Condividi | Applicabile solo ai segmenti. |
| Elimina | Applicabile solo ai segmenti. |

Guarda il video su Creazione di metriche, segmenti e date:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Autorizzazioni di accesso ai componenti

Gli amministratori possono curare (tramite [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) i componenti esposti agli utenti nel reporting. La tabella seguente mostra il funzionamento di queste autorizzazioni di accesso ai componenti:

| Tipo di cura | L&#39;amministratore può visualizzare | Il proprietario del progetto non amministratore (o il ruolo di modifica) può visualizzare | Ruolo duplicato non amministratore |
| --- | --- | --- | --- |
| **Componenti &quot;nascosti&quot; da una visualizzazione dati** | Tutti i componenti della visualizzazione dati disponibili per il reporting (i componenti nascosti richiedono di fare clic su &quot;Mostra tutto&quot;) | Non disponibile per la generazione di rapporti | Non disponibile per la generazione di rapporti |
| **Componenti aggiunti o rimossi da una visualizzazione dati** | Solo i componenti aggiunti alla visualizzazione dati (nascosti o non nascosti). Gli amministratori non possono creare rapporti su campi o componenti non definiti dalla visualizzazione dati. | Solo i componenti aggiunti alla visualizzazione dati o i componenti di proprietà o condivisi con l’utente. I componenti nascosti non sono disponibili (come la cura delle VRS). | Solo i componenti aggiunti al DV non sono nascosti e sono stati inclusi nella cura del progetto. |
| **Componenti curati in un progetto** | Tutti i componenti della visualizzazione dati disponibili per il reporting (i componenti nascosti richiedono di fare clic su &quot;Mostra tutto&quot;) | Tutti i componenti della visualizzazione dati non nascosti (è necessario fare clic su &quot;mostra tutto&quot;) | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
| **Progetto curato utilizzando una visualizzazione dati con componenti nascosti** | Tutti i componenti dati disponibili per il reporting (i componenti nascosti e non curati richiedono di fare clic su &quot;Mostra tutto&quot;) | Tutti i componenti di progetto non curati, tutti i componenti di visualizzazione dati non nascosti e tutti i componenti di proprietà o condivisi con l’utente | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |

