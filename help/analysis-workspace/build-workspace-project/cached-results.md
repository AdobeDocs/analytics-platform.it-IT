---
title: Utilizzare i risultati nella cache per un caricamento più rapido in Analysis Workspace
description: Abilita un’impostazione di progetto in Analysis Workspace che memorizza nella cache i risultati per 12 ore in modo che i progetti vengano caricati all’istante. Aggiorna in qualsiasi momento per visualizzare i dati più recenti.
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
source-git-commit: 32dfb7790f57293ea297bdcb8319c3d3b187a2ae
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 5%
---

# Utilizza i risultati memorizzati nella cache nei progetti di Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Utilizza i risultati memorizzati nella cache per un caricamento più rapido"
>abstract="Quando questa opzione è abilitata, i risultati vengono caricati all’istante per 12 ore a quando un utente apre il progetto per la prima volta o da quando viene consegnato tramite pianificazione. Chiunque apra il progetto in quel periodo di tempo visualizzerà gli stessi risultati, anche se i dati continueranno ad affluire in background. Per caricare i risultati più recenti, aggiorna i singoli pannelli o l’intero progetto."

{{release-limited-testing}}

Puoi configurare i progetti Analysis Workspace in modo da mostrare i risultati memorizzati nella cache per una finestra di 12 ore, che consente di caricare i risultati immediatamente per chiunque apra il progetto dopo averlo caricato inizialmente.

I progetti possono essere caricati inizialmente da un utente che apre il progetto o da una consegna pianificata del progetto.

## Comprendere i risultati memorizzati in cache in un progetto

### Quando i risultati vengono memorizzati in cache

La prima volta che il progetto viene caricato, i risultati vengono caricati a velocità normale e Analysis Workspace li memorizza nella cache per una finestra di 12 ore. Ciò si verifica quando:

* Qualcuno apre il progetto

* Il progetto viene eseguito per una consegna pianificata

Ad esempio, se la consegna di un progetto è pianificata per le 06:00, i risultati vengono memorizzati nella cache fino alle 18:00. Chiunque apra il progetto tra le 6:00 e le 18:00 vede i risultati caricarsi all’istante, inclusa la prima persona ad aprirlo.

Dopo 12 ore, i risultati memorizzati in cache scadono. Al successivo caricamento del progetto, che si tratti dell’apertura di un utente o dell’esecuzione di una consegna pianificata, i risultati vengono caricati alla velocità normale e inizia una nuova finestra di 12 ore.

### Quali risultati vengono memorizzati nella cache

#### Il progetto viene inizialmente memorizzato nella cache con la relativa configurazione originale

Analysis Workspace memorizza nella cache i risultati del progetto così come è stato configurato originariamente, con le visualizzazioni dati selezionate, i segmenti applicati, gli intervalli di date, le selezioni a discesa del pannello e così via. Tutti coloro che aprono il progetto visualizzano questi risultati memorizzati nella cache.

Se qualcuno modifica la configurazione del progetto durante la visualizzazione del progetto memorizzato in cache, i risultati vengono caricati normalmente (non immediatamente) e [viene memorizzata nella cache una nuova variante di progetto](#project-variations-are-cached-as-the-project-is-modified).

#### Le varianti di progetto vengono memorizzate nella cache quando il progetto viene modificato

Una nuova variante del progetto viene creata quando qualcuno ne modifica la configurazione originale, ad esempio selezionando un elemento dal menu a discesa di un pannello, applicando un segmento, modificando un intervallo di date o modificando la visualizzazione dati selezionata.

La prima volta viene caricata una nuova variante alla velocità normale. Dopodiché, anche i suoi risultati vengono memorizzati in cache, così chiunque carichi la stessa variante vede i risultati immediatamente.

Considera i seguenti aspetti:

* Analysis Workspace memorizza nella cache ogni variante di un progetto che viene caricata da un utente. Non memorizza in cache tutte le possibili varianti di un progetto.

* La memorizzazione nella cache di una nuova variante non sovrascrive o invalida i risultati già memorizzati nella cache. Il progetto originale viene memorizzato nella cache insieme ad altre varianti caricate dagli utenti.

>[!BEGINSHADEBOX]

**Scenario di esempio**

Supponiamo che un progetto di prestazioni globali della campagna includa segmenti per diverse aree geografiche e sia pianificato per la consegna alle 06:00:

| Tempo | Azione | Velocità di carico |
| --- | --- | --- |
| 06:00 | Consegna pianificata del progetto | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 07:06 | L’utente A apre il progetto | Istantanea |
| 07:07 | L&#39;utente A applica il segmento delle Americhe | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 08:01 | L&#39;utente B apre il progetto | Istantanea |
| 08:05 | L&#39;utente B applica il segmento delle Americhe | Istantanea |
| 08:12 | L’utente B applica il segmento EMEA | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |

>[!ENDSHADEBOX]

### Modifiche che causano l’aggiornamento dei risultati memorizzati nella cache con il successivo caricamento del progetto

Le seguenti modifiche alla configurazione sottostante di un progetto inducono Analysis Workspace ad aggiornare i risultati alla successiva apertura del progetto, anche se la finestra di 12 ore non è scaduta:

* Modifiche a un componente nella visualizzazione dati, ad esempio la modifica delle [impostazioni del componente](/help/data-views/component-settings/overview.md) di una dimensione o di una metrica

* Modifiche a un [campo derivato](/help/data-views/derived-fields/derived-fields.md)

* Modifiche a una definizione di segmento utilizzata nel progetto

I risultati vengono caricati a velocità normale e quindi memorizzati nella cache, che inizia una nuova finestra di 12 ore.

### Chi visualizza i risultati memorizzati nella cache

I risultati memorizzati in cache vengono visualizzati per impostazione predefinita per tutti coloro che:

* Ha accesso al progetto

* Ha accesso alle visualizzazioni dati utilizzate nel progetto

* Caricamento di una variante del progetto già memorizzata nella cache, ad esempio un progetto con gli stessi segmenti o le stesse selezioni a discesa del pannello (per ulteriori informazioni, vedere [Quali risultati vengono memorizzati nella cache](#what-results-are-cached))

Durante la visualizzazione dei risultati memorizzati nella cache, puoi visualizzare i dati più recenti [aggiornando manualmente i risultati](#manually-refresh-results-on-cached-projects).

### Quando lasciare i risultati memorizzati nella cache disattivati in un progetto

Alcuni progetti dipendono dai risultati per riflettere i dati più recenti ogni volta che qualcuno li apre. Ciò è comune per i progetti che si basano fortemente su dati dello stesso giorno, dati in arrivo o [set di dati di ricerca](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) che vengono aggiornati frequentemente.

Lascia disabilitati i risultati memorizzati nella cache nel progetto se la maggior parte degli utenti che accedono al progetto deve visualizzare:

* **Dati del giorno corrente**

  Se un progetto viene memorizzato nella cache alle 07:00, i risultati non includono i dati che arrivano dopo le 07:00, fino alla scadenza dei risultati memorizzati nella cache alle 19:00.

* **Dati in arrivo ritardato**

  I dati in arrivo tardivo hanno marche temporali da un periodo di tempo precedente, ma arrivano dopo che tale periodo è passato. Ad esempio, [dati batch](/help/data-ingestion/batch.md) da un call center potrebbero essere caricati il giorno successivo, oppure un&#39;app mobile potrebbe inviare eventi archiviati mentre è offline. I risultati memorizzati nella cache non includono questi dati fino alla scadenza.

* **Valori di ricerca aggiornati**

  I risultati memorizzati nella cache continuano a mostrare i valori di ricerca precedenti, ad esempio i nomi dei prodotti precedenti, fino alla scadenza.

>[!NOTE]
>
>Se queste esigenze si presentano solo occasionalmente, abilita i risultati memorizzati nella cache e [aggiorna il progetto manualmente](#manually-refresh-results-on-cached-projects) quando hai bisogno dei dati più recenti.

## Abilitare i risultati memorizzati nella cache per un progetto

Chiunque possa aggiornare le impostazioni del progetto può abilitare i risultati memorizzati nella cache. Questo include il proprietario del progetto e chiunque abbia il ruolo **[!UICONTROL Modifica originale]** per il progetto. Per ulteriori informazioni sui ruoli di progetto, vedere [Condividere un ruolo di progetto specifico](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>I risultati memorizzati nella cache potrebbero non essere adatti se devi visualizzare immediatamente i dati del giorno corrente, quelli in arrivo o i valori di ricerca aggiornati. Prima di abilitare questa impostazione, controllare [Quando lasciare disabilitati i risultati memorizzati nella cache in un progetto](#when-to-leave-cached-results-disabled-on-a-project).

Nel progetto Workspace in cui desideri abilitare i risultati memorizzati nella cache per un caricamento più rapido:

1. Vai a **[!UICONTROL Progetti]** > **[!UICONTROL Informazioni e impostazioni progetto]**.

1. Seleziona **[!UICONTROL Utilizza i risultati memorizzati nella cache per un caricamento più rapido]**.

1. Seleziona **[!UICONTROL Salva]**.

## Visualizza quando i risultati memorizzati in cache vengono visualizzati in un progetto

Quando vengono visualizzati i risultati memorizzati nella cache, nella parte superiore del progetto viene visualizzata una marca temporale. La marca temporale specifica se tutti i risultati sono memorizzati in cache o solo alcuni risultati:

* **[!UICONTROL Visualizzazione dei risultati da] [_data e ora_]**: tutti i pannelli del progetto mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.

* **[!UICONTROL Visualizzazione di alcuni risultati da] [_data e ora_]**: alcuni pannelli mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora mostrate, mentre altri sono stati aggiornati più di recente.

![Timestamp sul progetto memorizzato nella cache](assets/project-cache-timestamp.png)

I pannelli visualizzano anche una marca temporale che indica quando i risultati sono stati memorizzati in cache:

* **[!UICONTROL Visualizzazione dei risultati da] [_data e ora_]**: il pannello mostra i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.

  >[!NOTE]
  >
  >Questa opzione non è disponibile durante la fase alfa del rilascio.

## Aggiorna manualmente i risultati nei progetti memorizzati in cache

Solo i risultati mostrati nel progetto vengono memorizzati in cache. I dati dell’evento sottostante continuano a fluire in Customer Journey Analytics come di consueto.

Per visualizzare i dati più recenti prima della scadenza dei risultati memorizzati nella cache, puoi aggiornare manualmente i risultati di un progetto in qualsiasi momento durante la finestra delle 12 ore. Quando aggiorni l’intero progetto, inizia una nuova finestra di 12 ore e tutti coloro che aprono il progetto durante tale finestra visualizzano i risultati aggiornati.

Nel progetto Workspace in cui desideri visualizzare i dati più recenti, puoi aggiornare i risultati per l’intero progetto o per un singolo pannello.

### Aggiorna i risultati per l&#39;intero progetto

Per caricare i risultati più recenti per tutti i pannelli e iniziare una nuova finestra di 12 ore:

1. Seleziona l&#39;icona **[!UICONTROL Aggiorna]** ![Aggiorna](/help/assets/icons/Refresh.svg) nella parte superiore del progetto accanto alla marca temporale del progetto.

### Aggiorna i risultati per un singolo pannello

>[!NOTE]
>
>Questa opzione non è disponibile durante la fase alfa del rilascio.

Per caricare i risultati più recenti solo per un singolo pannello:

1. Seleziona l&#39;icona **[!UICONTROL Aggiorna]** ![Aggiorna](/help/assets/icons/Refresh.svg) accanto al timestamp di un pannello.

