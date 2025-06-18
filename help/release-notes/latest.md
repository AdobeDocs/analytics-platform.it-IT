---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 216b44907c8af1194ee010ae830ccd4d21ccfbf4
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 27%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics di Adobe (luglio 2025)

**Ultimo aggiornamento**: giovedì 18 giugno 2025


Queste note sulla versione coprono il periodo di rilascio compreso tra il martedì 2 giugno 2025 e l’mercoledì 15 luglio 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Il pannello sinistro di Analysis Workspace non si apre più e si chiude al passaggio del mouse** | Il pannello a sinistra in Analysis Workspace viene utilizzato per aggiungere elementi come componenti, pannelli e visualizzazioni al progetto. L’opzione per aprire temporaneamente il pannello a sinistra passando il cursore su una delle icone all’estrema sinistra non è più disponibile. Al contrario, fai clic su una di queste icone per mantenere aperto il pannello, quindi fai clic sulla stessa icona per chiuderlo. |  | martedì 2 giugno 2025 <p>(Originariamente previsto per il rilascio il 29 maggio 2025)</p> |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition aiuta le aziende B2B ad allineare i team di marketing, vendita e prodotto fornendo informazioni fruibili sull’account che guidano la crescita dei ricavi. Con l’account posizionato al centro del modello dati, tutte le analisi si concentrano sul percorso dell’account. L’aggiunta di un nuovo livello di entità (account, opportunità e gruppi di acquisto) oltre a eventi basati su persona e tempo crea un quadro completo del ciclo di vita di marketing e ricavi B2B. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | giovedì 18 giugno 2025 |
| **Supporto per destinazioni sicure in Report Builder** | Sono state aggiunte nuove destinazioni di esportazione al componente aggiuntivo Report Builder. Sono supportate le seguenti destinazioni di archiviazione cloud: <ul><li>Amazon S3 con ruolo ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> Il link alla documentazione seguirà a breve. |  | Giugno 18,2025 |
| **Nuova esperienza di anteprima** | Il pannello Anteprima, utilizzato per visualizzare in anteprima segmenti, metriche calcolate e altro ancora, ora utilizza una visualizzazione a barre orizzontali invece di una ad anello. |  | giovedì 18 giugno 2025 |
| **Finestra di dialogo modello di attribuzione modificato** | Ora puoi definire separatamente il contenitore e il periodo di tempo nella finestra di dialogo del modello di attribuzione. |  | Giugno 18,2025 |
| **Mappa connessione** | È disponibile una nuova interfaccia [mappa di connessione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-connections/create-connection#connection-map) per visualizzare visivamente la configurazione della connessione. |  | giovedì 18 giugno 2025 |
| **Aggiungi e visualizza commenti nei progetti Analysis Workspace** | Una nuova funzione di [aggiunta di commenti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace consente di condividere informazioni e porre domande nel contesto di un progetto Analysis Workspace. Questo può semplificare le discussioni sui dati, mantenendo le conversazioni all’interno del contesto dei dati che vengono discussi. È possibile eseguire le seguenti azioni: <ul><li>Commento su qualsiasi progetto Analysis Workspace a cui hai accesso</li><li>Commento su un punto specifico di una visualizzazione o commenti generali su un progetto</li><li>Assegna tag ad altri utenti per notificare loro i tuoi commenti</li><li>Gestisci i commenti esistenti (modifica, fissaggio, risoluzione e così via)</li></ul>Gli amministratori di Customer Journey Analytics possono [disabilitare i commenti a livello di organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). I proprietari dei progetti possono [disabilitare i commenti a livello di progetto](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | giovedì 25 giugno 2025 <p>(Originariamente previsto per il rilascio il 29 maggio 2025)</p> |
| **Supporto per il pre-rendering di Chrome** | Controlla il comportamento delle librerie di raccolta dati quando Chrome esegue il pre-rendering di una pagina. Il link alla documentazione seguirà a breve. |  | martedì 30 giugno 2025 |

## Correzioni in Customer Journey Analytics

**Avvisi**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**Estensione BI per Tableau**: AN-377488
**Componenti**: AN-376174
**Visualizzazioni dati**: AN-379011
**Posizioni di esportazione**: AN-382191
**Esportazione tabella completa**: AN-375646; AN-376986; AN-380355; AN-381310
**Area di lavoro Percorsi**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Generazione rapporti**: AN-372615; AN-378578;


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
