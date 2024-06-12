---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 484ec8c32a8da4c33bb3236b9c7a8e1de83ead76
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 16%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (giugno 2024)

**Ultimo aggiornamento**: giovedì 12 giugno 2024

Queste note sulla versione coprono il periodo dal 6 giugno 2024 a luglio 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Assistente AI per Customer Journey Analytics** | Consente di porre domande in lingua naturale nell’interfaccia utente del Customer Journey Analytics e di ottenere risposte in base alla documentazione del Customer Journey Analytics. [Ulteriori informazioni](/help/ai-assistant.md) | | venerdì 6 giugno 2024 |
| **Unione basata su grafico: unione utilizzando l’esportazione di grafici UIS** | Tramite l’unione basata su grafico, puoi utilizzare il grafico Identità per ottenere una visualizzazione migliore del percorso di clienti:<ul><li>Unire i set di dati con identificatori diversi senza dover estrarre, trasformare e caricare dati aggiuntivi per riflettere un singolo identificatore.</li><li>Miglioramento della copertura dell’identità preferita o d’oro per un singolo set di dati mediante la condivisione di identità tra set di dati diversi.</li><li>Allineamento dei profili creati in Real-time Customer Data Platform e Journey Optimizer alle persone nel Customer Journey Analytics.</li></ul>(Segui il link alla documentazione) |  | sabato 28 giugno 2024 |
| **Trasformazione dello schema B2B per la persona all’account** | Per supportare le ricerche basate su persone sui dati B2B (inclusi account, opportunità, elenchi di marketing e campagne), puoi trasformare i set di dati di ricerca B2B. Questa trasformazione è disponibile solo per i set di dati con dati per schemi di ricerca B2B, in base alle classi seguenti:<ul><li>Relazione della persona dell’account aziendale XDM</li><li>Relazione della persona dell’opportunità di business XDM</li><li>Membri dell’elenco di marketing aziendale XDM</li><li>Membri della campagna aziendale XDM</li></ul>[Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | giovedì 5 giugno 2024 |
| **Campi derivati - Funzione matematica** | Consente di eseguire semplici operatori matematici all’interno delle visualizzazioni dati per rispondere a domande sugli utenti. Ad esempio, puoi combinare i ricavi da prodotti, garanzia e spedizione. <p>[Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | giovedì 5 giugno 2024 |
| **Campi derivati - Funzione Successivo o Precedente** | Consente di esaminare il valore successivo o precedente. Ad esempio, con quali canali di marketing precedenti si è interagito prima del canale di marketing selezionato? Oppure, con cosa hanno interagito gli utenti della pagina prima o dopo la pagina selezionata? Quali sono i canali più diffusi con cui gli utenti interagiscono prima di recarsi in negozio? <p>[Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12 giugno 2024 |
| **Campi derivati - Funzione di riepilogo** | Consente di applicare funzioni di tipo aggregazione a metriche o dimensioni a livello di evento, sessione e utente. (Segui il link alla documentazione) | | giovedì 26 giugno 2024 |
| **Campi derivati - Funzione di deduplicazione** | Consente di evitare il conteggio ripetuto di un valore. Può essere applicata a livello di utente o di sessione oppure in base al valore univoco di una dimensione. (Segui il link alla documentazione) |  | giovedì 26 giugno 2024 |
| **Priorità di acquisizione e latenza** | Ora è possibile acquisire i dati degli eventi in Customer Journey Analytics entro 90 minuti (SLT), indipendentemente dal fatto che i dati abbiano 24 ore, 48 ore o 7 giorni. Tieni presente che questa funzionalità varia in base al pacchetto SKU acquistato dalla tua azienda:<ul><li>CJA Priority Ingestion Basic: dati di 24 ore entro l’elaborazione SLT di 90 minuti (disponibile per CJA Foundation e CJA Select)</li><li>Acquisizione prioritaria di CJA Intermedia: dati di 72 ore entro l’elaborazione SLT di 90 minuti (disponibile per CJA Prime)</li><li>Priority Ingestion Advanced di CJA: dati di 1 settimana entro l’elaborazione SLT di 90 minuti (disponibile per CJA Ultimate)</li></ul> |  | 12 giugno 2024 |
| **Condividere account e posizioni utilizzati per l’esportazione e l’importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificare ed eliminare gli account e le posizioni. In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati. Queste impostazioni sono disponibili quando [configurare account di esportazione cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) e [configurare i percorsi di esportazione cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 giugno 2024 | mercoledì 18 giugno 2024 |
| **Selezionare più campi in un filtro a discesa** | Quando a un filtro a discesa sono stati aggiunti più campi, gli utenti possono ora selezionare più campi alla volta. Il pannello viene filtrato per includere uno qualsiasi dei campi selezionati. <p>In precedenza, gli utenti potevano selezionare un solo campo alla volta in un filtro a discesa.</p><p>(Link alla documentazione da seguire.)</p> |  | giovedì 19 giugno 2024 |
| **Sommario per i progetti Workspace** | È ora disponibile un nuovo sommario per i progetti. Il sommario fornisce collegamenti che consentono agli utenti di passare rapidamente a pannelli e visualizzazioni all’interno del progetto. <p>Il sommario può essere abilitato per singoli progetti o per tutti i progetti di un determinato utente.</p><p>(Link alla documentazione da seguire.)<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | giovedì 19 giugno 2024 |
| **Creare collegamenti ipertestuali per gli elementi dimensionali in una tabella a forma libera** | Puoi creare collegamenti ipertestuali per uno o più elementi dimensionali per renderli cliccabili all’interno di una tabella a forma libera in Analysis Workspace. <p>Puoi creare collegamenti ipertestuali per gli elementi dimensione che hanno valori URL, oppure puoi creare URL personalizzati per gli elementi dimensione che hanno valori non URL.</p><p>Puoi creare URL dinamici personalizzati per più elementi di dimensione utilizzando le variabili. Le variabili possono fare riferimento al valore di un elemento dimensione o alla dimensione di raggruppamento.</p><p>(Link alla documentazione da seguire.)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | giovedì 19 giugno 2024 |
| **I tipi di pubblico vengono pubblicati in una nuova sezione &quot;Tipi di pubblico&quot; nell’Experience Platform** | I tipi di pubblico pubblicati da Customer Journey Analytics sono ora disponibili nella nuova sezione &quot;Tipi di pubblico&quot; in Adobe Experience Platform.<p>In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Experienci Platform nella sezione &quot;Segmenti&quot;.</p><p>Questo miglioramento offre i seguenti vantaggi:</p><ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Experienci Platform; sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Experienci Platform utilizzando la colonna &quot;Origine&quot;, che mostra l’applicazione da cui il pubblico è stato pubblicato originariamente.</li><li>Le opzioni di filtro e ordinamento in Experienci Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul> <p>(Segui il link alla documentazione)</p> |  | lunedì 14 luglio 2024 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2024](/help/release-notes/2024.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
