---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f09937e6babca5549b9b78e9c90462673750a4b3
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 96%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (agosto 2025)

**Ultimo aggiornamento**: venerdì 4 settembre 2025


Queste note sulla versione coprono il periodo dal 13 agosto al 16 settembre 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aggiornamenti all&#39;interfaccia di utilizzo** | L&#39;interfaccia [Usage](/help/connections/manage-connections.md#usage) ora aggiunge informazioni sul volume dei dati di base e sulle dimensioni medie delle righe. | | venerdì 4 settembre 2025 |
| **Visualizzazione mappa** | La visualizzazione mappa è una visualizzazione in Analysis Workspace che permette di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate). È utile per identificare e confrontare dati di metriche di diverse aree geografiche.<p>In precedenza, la visualizzazione mappa era disponibile solo in Adobe Analytics.</p><p>La visualizzazione mappa in Customer Journey Analytics rispetto a quella in Adobe Analytics contiene i seguenti miglioramenti:</p><ul><li>Utilizzo di qualsiasi segmento della visualizzazione dati come origine dati.</li><li>Precisione fino a un metro configurando la dimensione nella visualizzazione dati.</li><li>Un nuovo strumento di selezione consente di creare un segmento, un pubblico, una tendenza o un raggruppamento da qualsiasi area selezionata nella visualizzazione.</li></ul><p>Per ulteriori informazioni, consulta [Mappa](/help/analysis-workspace/visualizations/map.md).</p> | 13 agosto 2025 | 25 agosto 2025 |
| **Modelli B2B** | Se disponi della licenza Customer Journey Analytics B2B edition, i seguenti modelli B2B aggiuntivi sono ora disponibili dall’interfaccia utente dei modelli Adobe: <ul><li>Panoramica sul coinvolgimento dell’account B2B</li><li>Panoramica sul coinvolgimento dell’opportunità B2B</li><li>Attività del gruppo acquisti B2B</li></ul><p>Per ulteriori informazioni, consulta [Modelli B2B](/help/analysis-workspace/templates/use-templates.md#b2b-templates) in [Utilizzo dei modelli](/help/analysis-workspace/templates/use-templates.md).</p> |  | 15 agosto 2025 |
| **I progetti scaricati come file PDF vengono scaricati nella workstation** | Durante il download di un progetto come file PDF, il PDF viene scaricato nella cartella dei download sulla workstation. <p>In precedenza, il download di un progetto come file PDF avviava il PDF in una nuova scheda del browser con un URL univoco.</p><p>Per ulteriori informazioni, consulta [Scaricare progetti e dati](/help/analysis-workspace/export/download-send.md).</p> |  | 25 agosto 2025 |
| **Supporto per schemi ad hoc** | Gli [schemi ad hoc](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/ad-hoc) vengono utilizzati in vari flussi di lavoro di acquisizione dati per Experience Platform, inclusa l’acquisizione di file CSV e la creazione di alcuni tipi di connessioni di origine. <p>Questa funzione abilita il supporto per l’utilizzo di schemi ad hoc in Customer Journey Analytics. Come parte della definizione di una connessione, ora puoi selezionare un set di dati basato su uno schema ad hoc e utilizzare i dati nei progetti di visualizzazione dati e area di lavoro.</p> <p>Il collegamento alla documentazione seguirà a breve.</p> |  | 18 settembre 2025 (originariamente previsto per il rilascio il 28 agosto 2025) |
| **Estensione del limite delle chiavi di ricerca** | A seconda del pacchetto Customer Journey Analytics, ora puoi disporre fino a un massimo di 1 miliardo di chiavi univoche in un set di dati di ricerca. <p>Per ulteriori informazioni, consulta [Limiti di trasferimento dei dati](/help/technotes/guardrails.md#data-transfer-limits) nella documentazione [Guardrail](/help/technotes/guardrails.md) di Customer Journey Analytics.</p> |  | 29 agosto 2025 |
| **Creare metriche e dimensioni in base ai campi mappa definiti dall’utente dallo schema di Platform** | I campi mappa definiti dall’utente, che puoi stabilire nello schema di Experience Platform, ora sono disponibili per l’utilizzo in Customer Journey Analytics.<p>Durante la creazione di metriche e dimensioni in Customer Journey Analytics, puoi utilizzare i seguenti campi mappa:</p><ul><li>ds stringa a stringa</li><li>da stringa a numero intero</li></ul><p>Per ulteriori informazioni, consulta [Impostazioni dei componenti](/help/data-views/component-settings/overview.md).</p><p>Per ulteriori informazioni sui campi mappa in Experience Platform, consulta [Definire i campi mappa nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/map).</p> |  | Fine agosto 2025 |
| **I progetti eliminati non sono più immediatamente disponibili tramite URL e vengono rimossi dalle consegne pianificate** | I progetti eliminati vengono immediatamente rimossi dalle consegne pianificate e non sono più accessibili dal relativo URL.<p>In precedenza, i progetti venivano inclusi nelle consegne pianificate e potevano essere accessibili tramite il rispettivo URL per 60 giorni dopo l’eliminazione.</p><p>Per ulteriori informazioni sull’eliminazione dei progetti, consulta la sezione [Panoramica sui progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fine agosto 2025 |
| **Reporting in tempo reale** | Il reporting in tempo reale in Customer Journey Analytics mostra e aggiorna dati e visualizzazioni in uno o più pannelli di Analysis Workspace in tempo reale.<br/><br/>Il collegamento alla documentazione seguirà a breve. | | 18 settembre 2025 (originariamente previsto per il rilascio il 15 agosto 2025) |
| **Contenuti in streaming: sono stati aggiornati i campi XDM per la raccolta dati dei contenuti in streaming in Adobe Experience Platform** | Durante la raccolta dei dati dei contenuti in streaming in Adobe Experience Platform, i percorsi dei campi XDM mostrati sotto l’intestazione “Percorso dei campi XDM” nella documentazione sui parametri per contenuti in streaming non devono più essere utilizzati. La clientela che ha implementato il connettore di origine di Analytics per raccogliere i contenuti in streaming in Platform prima del 9 maggio 2025 deve effettuare la migrazione delle le configurazioni esistenti ai percorsi dei campi mediaReporting, come mostrato nell’intestazione “Percorso dei campi XDM per il reporting” della documentazione sui parametri dei contenuti multimediali in streaming.<p> Questi percorsi dei campi si trovano nelle pagine seguenti e sono contrassegnati come “Obsoleti”: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato del lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). Per la clientela che implementa il connettore di origine di Analytics dopo il 9 maggio 2025 e sta già utilizzando solo i percorsi XDM mediaReporting, non è richiesta alcuna azione.</p><p>L’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà fino alla fine di ottobre 2025. Successivamente, i percorsi dei campi obsoleti verranno rimossi del tutto e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi mediaReporting.</p><p>Per ulteriori informazioni, consulta [Effettuare la migrazione di un’implementazione del connettore di origine di Analytics ai campi XDM per contenuti multimediali in streaming aggiornati](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. </p> |  | Ottobre 2025 |
| **Unione nelle connessioni** | Semplifica l’unione in Customer Journey Analytics. Invece di duplicare un set di dati e applicare l’unione al set di dati duplicato, l’unione viene ora eseguita al momento dell’acquisizione dei dati in Customer Journey Analytics, eliminando il requisito di set di dati e schemi duplicati. <p>Inoltre, invece di dover richiedere l’unione tramite l’assistenza clienti, ora puoi iniziare a eseguire l’unione da un’interfaccia utente Connessioni aggiornata.</p><p> *Le date di rilascio comunicate in precedenza sono state posticipate a causa di ulteriori attività necessarie. Le nuove date di rilascio si sovrappongono al periodo delle festività, introducendo ulteriori vincoli per il rilascio. Per garantire la stabilità e ridurre al minimo le interruzioni durante tale periodo, è stato ora pianificato un rollout graduale.*</p> | Fine ottobre 2025 | Fine gennaio 2026 |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Componenti**:
**Content Analytics**:
**Analisi guidata**: AN-384426
**Platform**: AN-384410
**Report Builder**: AN-389336; AN-382775
**Generazione rapporti**:
**Segmentazione**:
**Metriche e dimensioni condivise**:
**Altro**: AN-388222; AN-384898; AN-387169


## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
