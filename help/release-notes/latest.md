---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2929a8034fe7ef1602a2a04eb76dbb9e7c4a9b81
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 18%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (agosto 2025)

**Ultimo aggiornamento**: venerdì 14 agosto 2025


Queste note sulla versione coprono il periodo dal 13 agosto al 16 settembre 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizzazione mappa** | La visualizzazione mappa in Analysis Workspace consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate). È utile per identificare e confrontare i dati delle metriche tra diverse aree geografiche.<p>In precedenza, la visualizzazione mappa era disponibile solo in Adobe Analytics.</p><p>La visualizzazione mappa in Customer Journey Analytics contiene i seguenti miglioramenti dalla visualizzazione mappa in Adobe Analytics:</p><ul><li>Utilizza qualsiasi segmento della visualizzazione dati come origine dati.</li><li>Precisione fino a un singolo metro configurando la dimensione nella visualizzazione dati.</li><li>Un nuovo strumento di selezione consente di creare un segmento, un pubblico, una tendenza o un raggruppamento da qualsiasi area selezionata nella visualizzazione.</li></ul><p>Per ulteriori informazioni, vedere [Mappa](/help/analysis-workspace/visualizations/map.md).</p> | giovedì 13 agosto 2025 | 25 agosto 2025 |
| **Reporting in tempo reale** | Il reporting in tempo reale in Customer Journey Analytics mostra e aggiorna dati e visualizzazioni in uno o più pannelli in Analysis Workspace in tempo reale. | | 17 settembre 2025 (originariamente previsto per il rilascio il 15 agosto 2025) |
| **Modelli B2B** | Se utilizzi in licenza Customer Journey Analytics B2B edition, i seguenti modelli B2B aggiuntivi sono ora disponibili dall’interfaccia utente dei modelli di Adobe: <ul><li>Panoramica sul coinvolgimento dell’account B2B</li><li>Panoramica del coinvolgimento dell’opportunità B2B</li><li>Attività del gruppo di acquisto B2B</li></ul><p>(Il link alla documentazione seguirà a breve.)</p> |  | sabato 15 agosto 2025 |
| **I progetti scaricati come file PDF vengono scaricati nella workstation** | Quando si scarica un progetto come PDF, il PDF viene scaricato nella cartella dei download sulla workstation. <p>In precedenza, il download di un progetto come PDF avviava PDF in una nuova scheda del browser con un URL univoco.</p><p>Per ulteriori informazioni, vedere [Scaricare progetti e dati](/help/analysis-workspace/export/download-send.md).</p> |  | 25 agosto 2025 |
| **Supporto per schemi ad hoc** | [Gli schemi ad hoc](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/ad-hoc) vengono utilizzati in vari flussi di lavoro di acquisizione dati per Experience Platform, inclusa l&#39;acquisizione di file CSV e la creazione di alcuni tipi di connessioni di origine. <p>Questa funzione abilita il supporto per l’utilizzo di schemi ad hoc in Customer Journey Analytics. Come parte della definizione di una connessione, ora puoi selezionare un set di dati basato su uno schema ad hoc e utilizzare i dati nei progetti di visualizzazione dati e area di lavoro.</p> <p>(Il link alla documentazione seguirà a breve.)</p> |  | venerdì 28 agosto 2025 |
| **Unione nelle connessioni** | Semplifica la combinazione di Customer Journey Analytics. Invece di duplicare un set di dati e applicare l’unione al set di dati duplicato, l’unione viene ora eseguita al momento dell’acquisizione dei dati in Customer Journey Analytics, eliminando il requisito di set di dati e schemi duplicati. <p>Inoltre, invece di dover richiedere l’unione tramite l’assistenza clienti, ora puoi iniziare a eseguire l’unione da un’interfaccia utente Connessioni aggiornata.</p><p> *Le date di rilascio comunicate in precedenza vengono inviate a causa di sforzi aggiuntivi richiesti. Le nuove date di rilascio si sovrappongono alle feste, introducendo ulteriori vincoli di rilascio. È ora pianificato un rollout graduale per garantire la stabilità e ridurre al minimo le interruzioni durante il periodo festivo.*</p> | Fine ottobre 2025 | Fine di gennaio 2026 |
| **Estensione del limite delle chiavi di ricerca** | A seconda del pacchetto Customer Journey Analytics, ora puoi avere fino a un massimo di 1 miliardo di chiavi univoche in un set di dati di ricerca. <p>Per ulteriori informazioni, vedere [Limiti di trasferimento dei dati](/help/technotes/guardrails.md#data-transfer-limits) nella documentazione di Customer Journey Analytics [Guardrail](/help/technotes/guardrails.md).</p> |  | sabato 29 agosto 2025 |
| **Creare metriche e dimensioni in base ai campi mappa definiti dall&#39;utente dallo schema di Platform** | I campi mappa definiti dall’utente che definisci nello schema di Experience Platform ora possono essere utilizzati in Customer Journey Analytics.<p>Durante la creazione di metriche e dimensioni in Customer Journey Analytics, puoi utilizzare i seguenti campi mappa:</p><ul><li>Stringa a stringa</li><li>Stringa a numero intero</li></ul><p>(Il link alla documentazione seguirà a breve.)</p><p>Per ulteriori informazioni sui campi mappa in Experience Platform, vedi [Definire i campi mappa nell&#39;interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/map).</p> |  | Fine di agosto 2025 |
| **I progetti eliminati non sono immediatamente disponibili tramite URL e vengono eliminati dalle consegne pianificate** | I progetti eliminati vengono eliminati immediatamente dalle consegne pianificate e non sono più accessibili dal relativo URL.<p>In precedenza, i progetti venivano inclusi nelle consegne pianificate e potevano essere accessibili con il loro URL per 60 giorni dopo l’eliminazione.</p><p>Per ulteriori informazioni sull&#39;eliminazione dei progetti, vedere [Panoramica progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fine di agosto 2025 |
| **Streaming Media: sono stati aggiornati i campi XDM per la raccolta dei dati di Streaming Media in Adobe Experience Platform** | Durante la raccolta di dati di contenuti in streaming in Adobe Experience Platform, i percorsi dei campi XDM mostrati sotto l’intestazione “Percorso dei campi XDM” nella documentazione sui parametri per contenuti in streaming non devono più essere utilizzati. Al contrario, i clienti che hanno implementato il connettore di origine di Analytics per raccogliere i dati di Streaming Media in Platform prima del 9 maggio 2025 devono migrare le configurazioni esistenti ai percorsi dei campi mediaReporting, come mostrato nell’intestazione &quot;Percorso campo XDM per reporting&quot; della documentazione sui parametri di Streaming Media.<p> I percorsi dei campi sono disponibili nelle pagine seguenti e sono contrassegnati come &quot;Obsoleti&quot;: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). (Non è richiesta alcuna azione per i clienti che implementano il connettore di origine di Analytics dopo il 9 maggio 2025 e utilizzano già solo i percorsi XDM mediaReporting).</p><p>L’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà fino alla fine di ottobre 2025. Dopo tale periodo, i percorsi dei campi obsoleti verranno completamente rimossi e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi mediaReporting.</p><p>Per ulteriori informazioni, consulta [Migrare un&#39;implementazione del connettore Source di Analytics ai campi XDM Streaming Media aggiornati](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contatta i servizi Adobe Consulting o il team dell’account per il supporto alla migrazione. </p> |  | 2025 ottobre |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Componenti**:
**Content Analytics**:
**Analisi guidata**: AN-384426
**Piattaforma**: AN-384410
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
