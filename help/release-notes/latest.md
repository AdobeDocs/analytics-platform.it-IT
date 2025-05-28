---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: df8a10c674ed64d0341209fbe0a700a5c94b3b75
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 28%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (maggio 2025)

**Ultimo aggiornamento**: venerdì 22 maggio 2025


Queste note sulla versione coprono il periodo di rilascio dal 22 aprile al 18 giugno 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Sono stati aggiornati i campi XDM per la raccolta dei dati di Streaming Media in Adobe Experience Platform** | Durante la raccolta di dati Streaming Media in Adobe Experience Platform, i percorsi dei campi XDM mostrati nell’intestazione &quot;Percorso campo XDM&quot; della documentazione sui parametri Streaming Media non devono più essere utilizzati. I percorsi dei campi sono disponibili nelle pagine seguenti e sono contrassegnati come &quot;Obsoleti&quot;: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). <p>I clienti devono invece migrare ai percorsi dei campi `mediaReporting`, come mostrato nell&#39;intestazione &quot;Percorso campo XDM per reporting&quot; della documentazione dei parametri di Streaming Media di cui sopra.<p>Durante un periodo transitorio di tre mesi, l’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà. Tuttavia, alla fine di luglio 2025, i percorsi dei campi obsoleti verranno completamente rimossi e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi `mediaReporting`.<p>I clienti che hanno implementato il connettore di origine di Analytics per raccogliere i dati di Streaming Media in Platform prima del 22 aprile 2025 devono migrare le configurazioni esistenti per utilizzare i nuovi percorsi dei campi. Questa migrazione deve essere completata entro la fine di luglio 2025. Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. Per la clientela che implementa il connettore di origine di Analytics dopo il 22 aprile 2025 non è richiesta alcuna azione.</p> |  | 22 aprile 2025 |
| **Unione: recupero di ID permanenti e transitori da IdentityMap XDM** | Questa funzione fornisce supporto per l’utilizzo di identità memorizzate in IdentityMap XDM nel processo di unione. IdentityMap può essere utilizzato per l’ID persistente o transitorio per l’unione basata sui campi e per l’ID persistente per l’unione basata sui grafici.  È possibile utilizzare uno spazio dei nomi specifico o un’identità primaria da identityMap. Ulteriori informazioni sono disponibili [qui](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/fbs#identitymap) e [qui](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/gbs#identitymap) |  | martedì 28 aprile 2025 |
| **Metriche e dimensioni condivise tra le visualizzazioni dati** | Consente di applicare impostazioni di dimensioni e metriche a più visualizzazioni dati. Le modifiche apportate a una dimensione o metrica condivisa si applicano a tutte le istanze di tale dimensione o metrica in tutte le visualizzazioni dati applicabili. Questa interfaccia consente agli amministratori di Customer Journey Analytics di gestire più facilmente i componenti quando vengono utilizzate più visualizzazioni dati. [Ulteriori informazioni](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 aprile 2025 |
| **Aumento dei limiti di esportazione della tabella completa** | Adobe ha aumentato il numero di colonne utilizzabili con [esportazione di tabelle completa](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) da 5 dimensioni e 5 metriche a 10 dimensioni e 10 metriche. Questo vale per tutti i livelli Customer Journey Analytics. I diritti per il numero di righe che è possibile esportare non vengono modificati. |  | 30 aprile 2025 |
| **Dimensione profondità evento** | Una nuova dimensione di profondità evento [&#128279;](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) è stata aggiunta all&#39;elenco dei componenti standard richiesti per una visualizzazione dati. |  | venerdì 8 maggio 2025 |
| **Disattiva il file manifesto durante l&#39;esportazione di tabelle complete** | Consente di disattivare il file manifesto incluso per impostazione predefinita durante l’esportazione di tabelle complete da Analysis Workspace. [Ulteriori informazioni](/help/analysis-workspace/export/export-cloud.md) |  | mercoledì 20 maggio 2025 |
| **Data Insights Agent** | Data Insights Agent, parte dell’assistente di intelligenza artificiale in Customer Journey Analytics, è un agente di conversazione di intelligenza artificiale generativo. Utilizza i componenti della visualizzazione dati e i dati effettivi per rispondere in modo rapido ed efficiente a domande incentrate sui dati creando visualizzazioni rilevanti in Analysis Workspace. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | giovedì 28 maggio 2025 |
| **Il valore predefinito per il formato Dimension è 2 per le dimensioni di tipo Double** | Per gli schemi con tipi di dati Double, il valore predefinito del formato della dimensione è 2 posizioni decimali. È possibile modificare questo numero da 0 a 5 cifre decimali.<p>In precedenza, il formato utilizzava 0 posizioni decimali come impostazione predefinita.</p><p>Ciò significa che se nei rapporti di Analysis Workspace utilizzi dimensioni di doppio tipo, per impostazione predefinita non sono state visualizzate cifre decimali. Questi stessi rapporti ora mostrano 2 posizioni decimali.</p><p>Per ulteriori informazioni su come aggiornare il numero di posizioni decimali visualizzate per le dimensioni a doppio tipo, vedere [Impostazioni del componente Formato](/help/data-views/component-settings/format.md).</p> | | venerdì 29 maggio 2025 |
| **Il pannello sinistro di Analysis Workspace non si apre più e si chiude al passaggio del mouse** | Il pannello a sinistra in Analysis Workspace viene utilizzato per aggiungere elementi come componenti, pannelli e visualizzazioni al progetto. L’opzione per aprire temporaneamente il pannello a sinistra passando il cursore su una delle icone all’estrema sinistra non è più disponibile. Al contrario, fai clic su una di queste icone per mantenere aperto il pannello, quindi fai clic sulla stessa icona per chiuderlo. |  | martedì 2 giugno 2025 <p>(Originariamente previsto per il rilascio il 29 maggio 2025)</p> |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition aiuta le aziende B2B ad allineare i team di marketing, vendita e prodotto fornendo informazioni fruibili sull’account che guidano la crescita dei ricavi. Con l’account posizionato al centro del modello dati, tutte le analisi si concentrano sul percorso dell’account. L’aggiunta di un nuovo livello di entità (account, opportunità e gruppi di acquisto) oltre a eventi basati su persona e tempo crea un quadro completo del ciclo di vita di marketing e ricavi B2B. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | giovedì 18 giugno 2025 |
| **Aggiungi e visualizza commenti nei progetti Analysis Workspace** | Una nuova funzione di [aggiunta di commenti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace consente di condividere informazioni e porre domande nel contesto di un progetto Analysis Workspace. Questo può semplificare le discussioni sui dati, mantenendo le conversazioni all’interno del contesto dei dati che vengono discussi. È possibile eseguire le seguenti azioni: <ul><li>Commento su qualsiasi progetto Analysis Workspace a cui hai accesso</li><li>Commento su un punto specifico di una visualizzazione o commenti generali su un progetto</li><li>Assegna tag ad altri utenti per notificare loro i tuoi commenti</li><li>Gestisci i commenti esistenti (modifica, fissaggio, risoluzione e così via)</li></ul>Gli amministratori di Customer Journey Analytics possono [disabilitare i commenti a livello di organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). I proprietari dei progetti possono [disabilitare i commenti a livello di progetto](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | giovedì 25 giugno 2025 <p>(Originariamente previsto per il rilascio il 29 maggio 2025)</p> |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Tipi di pubblico**: AN-372343
**Registro di controllo**: AN-378168
**Connessioni**: AN-373121; AN-372996
**Eliminazione dati**: AN-375450
**Campi derivati**: AN-373689; AN-377852
**Posizioni di esportazione**: AN-374167
**Area di lavoro Percorsi**: AN-373319
**Report Builder**: AN-369786
**Generazione rapporti**: AN-377326; AN-378051
**Gestione attività di reporting**: AN-377148


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
