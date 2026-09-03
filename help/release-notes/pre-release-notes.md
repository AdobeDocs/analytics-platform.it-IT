---
title: Note preliminari su Customer Journey Analytics
description: Ultime note sulla versione non definitiva di Customer Journey Analytics
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 74%

---

# Note pre-release di Adobe Customer Journey Analytics

>[!IMPORTANT]
>
>Questo documento è destinato ad essere **anteprima** delle note sulla versione per il mese corrente. Gli elementi da rilasciare sono soggetti a modifiche e possono essere aggiunti o rimossi nella versione finale.

Queste note sulla versione coprono il periodo di rilascio compreso tra il 2 giugno 2025 e il 15 luglio 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni.

Per le note sulla versione di Adobe Experience Platform e delle sue altre applicazioni, consulta la seguente documentazione:

* [Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [Composizione di pubblico federato](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Il pannello a sinistra di Analysis Workspace non si apre né si chiude più al passaggio del puntatore** | Il pannello a sinistra in Analysis Workspace viene utilizzato per aggiungere al progetto elementi come componenti, pannelli e visualizzazioni. L’opzione per aprire temporaneamente il pannello a sinistra passando il puntatore su una delle icone all’estrema sinistra non è più disponibile. Per mantenere aperto il pannello, fai clic su una di queste icone; per chiuderlo, fai clic sulla stessa icona. |  | 2 giugno 2025 <p>Rilascio originariamente pianificato per il 29 maggio 2025</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition aiuta le aziende B2B ad allineare i team di marketing, vendita e prodotto fornendo insight sugli account da utilizzare per stimolare la crescita dei ricavi. Collocando l’account al centro del modello dati, tutte le analisi si concentrano sul suo percorso. L’aggiunta di un nuovo livello di entità (account, opportunità e gruppi acquisti), oltre a eventi basati su persona e tempo, crea un quadro completo del ciclo di vita di marketing e ricavi B2B. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 giugno 2025 |
| **Supporto per destinazioni sicure in Report Builder** | Sono state aggiunte nuove destinazioni di esportazione al componente aggiuntivo Report Builder. Sono supportate le seguenti destinazioni di archiviazione cloud: <ul><li>Amazon S3 con ruolo ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | Giugno 18,2025 |
| **Nuova esperienza di anteprima** | Il pannello Anteprima, utilizzato per visualizzare in anteprima segmenti, metriche calcolate e altro ancora, ora utilizza una visualizzazione a barre orizzontali invece di una ad anello. |  | 18 giugno 2025 |
| **Finestra di dialogo del modello di attribuzione modificata** | Ora è possibile definire separatamente il contenitore e il periodo di tempo nella finestra di dialogo del modello di attribuzione. |  | Giugno 18,2025 |
| **Mappa connessione** | È disponibile una nuova [interfaccia della mappa di connessione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-connections/create-connection#connection-map) per visualizzare la configurazione della connessione. |  | 18 giugno 2025 |
| **Aggiungere e visualizzare commenti nei progetti Analysis Workspace** | Una nuova [funzione di commenti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace consente di condividere informazioni e porre domande nel contesto di un progetto Analysis Workspace. Questo può semplificare le discussioni sui dati, mantenendo le conversazioni nell’ambito del contesto dei dati che vengono discussi. È possibile eseguire le seguenti azioni: <ul><li>Commentare qualsiasi progetto Analysis Workspace a cui hai accesso</li><li>Commentare un punto specifico di una visualizzazione o in generale un progetto</li><li>Menzionare altri utenti per informarli dei tuoi commenti</li><li>Gestire i commenti esistenti (modificare, fissare, risolvere e così via)</li></ul>Gli amministratori di Customer Journey Analytics possono [disabilitare i commenti a livello di organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). I proprietari dei progetti possono [disabilitare i commenti a livello di progetto](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 25 giugno 2025 <p>Rilascio originariamente pianificato per il 29 maggio 2025</p> |
