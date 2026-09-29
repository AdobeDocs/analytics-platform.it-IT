---
title: Utilizzare i risultati nella cache per un caricamento più rapido in Analysis Workspace
description: Abilita un’impostazione di progetto in Analysis Workspace che memorizza nella cache i risultati delle query per 12 ore, in modo che i progetti vengano caricati all’istante. Aggiorna in qualsiasi momento per visualizzare i dati più recenti.
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 6bcbf10e6bff660f57f598f6cf75b43eb75c7db3
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%
---

# Utilizzare i risultati memorizzati nella cache nei progetti Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Utilizza i risultati memorizzati nella cache per un caricamento più rapido"
>abstract="Quando questa opzione è abilitata, i risultati vengono caricati più rapidamente per 12 ore dopo la prima apertura di un progetto da parte di un utente o dopo che un progetto è stato consegnato da una pianificazione. Chiunque apra il progetto in quel periodo di tempo vede gli stessi risultati, anche se i dati continuano a scorrere in background. Per caricare i risultati più recenti, aggiorna i singoli pannelli o l’intero progetto."

Puoi configurare i progetti Analysis Workspace in modo da mostrare i risultati memorizzati nella cache per una finestra di 12 ore, che consente di caricare i risultati immediatamente per chiunque apra il progetto dopo averlo caricato inizialmente.

I progetti possono essere caricati inizialmente da un utente che apre il progetto o da una consegna pianificata del progetto.

>[!NOTE]
>
>Solo i risultati della query vengono memorizzati in cache. I dati dell’evento sottostante continuano a fluire in Customer Journey Analytics come di consueto.
>
>Per visualizzare i dati più recenti prima della scadenza dei risultati memorizzati nella cache, è possibile [aggiornare manualmente i risultati](#manually-refresh-results-on-cached-projects).

## Comprendere i risultati memorizzati in cache in un progetto

### Quando i risultati vengono memorizzati in cache

La prima volta che il progetto viene eseguito, Analysis Workspace esegue la query come di consueto e memorizza nella cache i risultati per una finestra di 12 ore. Questo accade quando qualcuno apre il progetto o quando il progetto viene eseguito per una consegna pianificata. Ad esempio, se la consegna di un progetto è pianificata per le 06:00, i risultati vengono memorizzati nella cache fino alle 18:00. Chiunque apra il progetto tra le 6:00 e le 18:00 vede i risultati caricarsi all’istante, inclusa la prima persona ad aprirlo.

Dopo 12 ore, i risultati memorizzati in cache scadono. La query successiva sul progetto, che sia aperta da un utente o eseguita da una consegna pianificata, viene caricata alla velocità normale e viene avviata una nuova finestra di 12 ore.

### Chi può visualizzare i risultati memorizzati nella cache

I risultati memorizzati in cache vengono condivisi con tutti coloro che hanno accesso al progetto e alle visualizzazioni dati utilizzate nel progetto.

### Quali risultati vengono memorizzati nella cache

Analysis Workspace memorizza nella cache ogni query in esecuzione, non tutte le versioni possibili di un progetto. Quando qualcuno modifica la query, ad esempio selezionando un elemento da un menu a discesa del pannello o applicando un segmento, Analysis Workspace esegue una nuova query. La nuova query viene caricata la prima volta a velocità normale. Dopodiché, vengono memorizzati in cache anche i relativi risultati.

La memorizzazione nella cache di una nuova query non sovrascrive né annulla la validità dei risultati già memorizzati nella cache. La vista del progetto originale viene memorizzata nella cache insieme ad altre varianti eseguite dagli utenti.

>[!BEGINSHADEBOX]

**Scenario di esempio**

Supponiamo che un progetto di prestazioni globali della campagna includa segmenti per diverse aree geografiche e sia pianificato per la consegna alle 06:00:

| Tempo | Azione | Velocità di carico |
| --- | --- | --- |
| 06:00 | Consegna pianificata del progetto | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 07:06 | L’utente A apre il progetto | Veloce |
| 07:06 | L&#39;utente A applica il segmento delle Americhe | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 08:01 | L&#39;utente B apre il progetto | Veloce |
| 08:01 | L&#39;utente B applica il segmento delle Americhe | Veloce |
| 08:01 | L’utente B applica il segmento EMEA | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |

>[!ENDSHADEBOX]

## Abilitare i risultati memorizzati nella cache per un progetto

Chiunque possa aggiornare le impostazioni del progetto può abilitare i risultati memorizzati nella cache. Questo include il proprietario del progetto e chiunque abbia il ruolo **[!UICONTROL Modifica originale]** per il progetto. Per ulteriori informazioni sui ruoli di progetto, vedere [Condividere un ruolo di progetto specifico](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

Nel progetto Workspace in cui desideri abilitare i risultati memorizzati nella cache per un caricamento più rapido:

1. Vai a **[!UICONTROL Progetti]** > **[!UICONTROL Informazioni e impostazioni progetto]**.
1. Seleziona **[!UICONTROL Utilizza i risultati memorizzati nella cache per un caricamento più rapido]**.
1. Seleziona **[!UICONTROL Salva]**.

## Visualizzare i timestamp dei dati nei progetti memorizzati in cache

Quando un progetto è configurato per l’utilizzo dei risultati memorizzati nella cache, nella parte superiore del progetto viene visualizzata una marca temporale che indica quando i risultati sono stati memorizzati nella cache:

* **[!UICONTROL Visualizzazione dei dati da] [_data e ora_]**: tutti i pannelli del progetto mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.
* **[!UICONTROL Visualizzazione di alcuni dati da] [_data e ora_]**: alcuni pannelli mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora mostrate, mentre altri sono stati aggiornati più di recente.

I pannelli visualizzano anche una marca temporale che indica quando i risultati sono stati memorizzati in cache:

* **[!UICONTROL Visualizzazione dei dati da] [_data e ora_]**: il pannello mostra i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.

## Aggiorna manualmente i risultati nei progetti memorizzati in cache

Per visualizzare i dati più recenti, è possibile aggiornare manualmente i risultati di un progetto in qualsiasi momento durante la finestra delle 12 ore. Quando aggiorni l’intero progetto, inizia una nuova finestra di 12 ore e tutti coloro che aprono il progetto durante tale finestra visualizzano i risultati aggiornati.

Nel progetto Workspace in cui desideri visualizzare i dati più recenti, puoi aggiornare i risultati per l’intero progetto o per un singolo pannello.

### Aggiorna i risultati per l&#39;intero progetto

Per caricare i risultati più recenti per tutti i pannelli e iniziare una nuova finestra di 12 ore:

1. Seleziona **[!UICONTROL Aggiorna]** nella parte superiore del progetto accanto alla marca temporale del progetto.

### Aggiorna i risultati per un singolo pannello

>[!NOTE]
>
>Questa opzione non è disponibile durante la fase alfa del rilascio.

Per caricare i risultati più recenti solo per un singolo pannello:

1. Seleziona **[!UICONTROL Aggiorna]** accanto alla marca temporale di un pannello.

