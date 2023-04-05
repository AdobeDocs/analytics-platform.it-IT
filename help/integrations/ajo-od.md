---
title: Integrare Adobe Journey Optimizer Decision Management con il Customer Journey Analytics (CJA)
description: Inserisci i dati generati da Adobe Journey Optimizer Decision Management e analizzali utilizzando Analysis Workspace all’interno del Customer Journey Analytics.
source-git-commit: 00a87f5f370310672ca37ab9df08350d14fc6a91
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 18%

---

# Integrare la gestione delle decisioni con il Customer Journey Analytics


Adobe Journey Optimizer [Gestione delle decisioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) semplifica la personalizzazione grazie a una libreria centrale di offerte di marketing e a un motore decisionale che applica regole e vincoli ai profili avanzati e in tempo reale creati da Adobe Experience Platform per aiutarti a inviare ai clienti l’offerta giusta al momento giusto.

La gestione delle decisioni fa parte di Adobe Journey Optimizer (AJO) e la sua integrazione. Può essere utilizzato anche indipendentemente dai percorsi e dalle campagne definiti in AJO, utilizzando la sua ricchezza [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) supporto.

Puoi importare i dati generati da Gestione decisioni per eseguire analisi avanzate in Customer Journey Analytics (CJA) eseguendo le seguenti operazioni:

## Inviare dati da Gestione decisioni a Adobe Experience Platform

Adobe Experience Platform funge da fonte di dati centrale e da collegamento tra la gestione delle decisioni e il Customer Journey Analytics. I dati della gestione delle decisioni sono raccolti in Experience Platform **automaticamente** o come parte di **eventi esperienza inviati esplicitamente** (ad esempio impression o clic). Vedi [Guida introduttiva alla raccolta dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) per ulteriori dettagli.

## Creare una connessione

Una volta che i dati di Gestione delle decisioni sono in Adobe Experience Platform, puoi creare un [Connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) in base ai set di dati di Gestione delle decisioni. Oppure puoi aggiungere i set di dati di Gestione decisioni a una connessione esistente.

Seleziona e configura i set di dati seguenti:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandbox_ decisione | Evento | ID persona: `IdentityMap` | Contiene dati generati automaticamente per gli eventi decisionali della Gestione delle decisioni. _Sandbox_ fa riferimento al nome specifico della sandbox. |
| Set di dati evento feedback messaggio AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna messaggi. |
| Set di dati evento esperienza di tracciamento e-mail AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail. |
| Set di dati evento esperienza di tracciamento push AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento push. |
| Set di dati di entità AJO | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano metadati di Percorso e campagna a tutti i dati evento AJO. |

{style="table-layout:auto"}

## Creare una visualizzazione dati

Dopo la creazione di una connessione, puoi crearne una o più [Visualizzazioni dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it) per configurare le dimensioni e le metriche desiderate disponibili in CJA.

>[!NOTE]
>
>Le discrepanze di dati tra AJO e CJA sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.

### Configurare le dimensioni

È possibile creare le dimensioni seguenti in una visualizzazione dati per ottenere una parità approssimativa con dimensioni simili in Gestione decisioni. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione della dimensione.

| Dimensione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- |
| Nome attività | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo di componente: dimensione |
| Identificatore contenitore | `_experience.decisioning.containerID` | Tipo di componente: dimensione |
| Identificatore di correlazione | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo di componente: dimensione |
| Nome opzione decisione | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo di componente: dimensione |
| Nome opzione della decisione di fallback | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo di componente: dimensione |
| Nome posizionamento | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo di componente: dimensione |

{style="table-layout:auto"}


### Configurare le metriche

È possibile creare le metriche seguenti in una visualizzazione dati per ottenere la parità approssimativa con metriche simili in Gestione decisioni. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- |
| Tipo evento (rinominare per fare riferimento a un evento specifico, ad esempio `Feedback` per `message.feedback`) [1] | Importo di un tipo specifico di evento | `eventType` | Tipo di componente: Metrica <br/>**[!UICONTROL Set Include Exclude Values]**: On<br/>**[!UICONTROL Match]**: [!UICONTROL If all criteria are met]<br/>**[!UICONTROL Criteria]**:**[!UICONTROL Equals]**`message.feedback` |
| Punteggio opzione decisione | Valore calcolato per un’opzione di decisione nel contesto di un unico ambito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo di componente: Metrica |
| Punteggio opzione per la decisione di fallback | Valore calcolato per un’opzione di decisione di fallback nel contesto di un singolo ambito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo di componente: Metrica |
| Offerte ignorate | Il numero di offerte scartate o rifiutate senza alcuna altra interazione diretta. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: Metrica |
| Visualizzazione delle offerte | Il numero di offerte visualizzate al profilo. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: Metrica |
| Offerte interattive | Il numero di offerte visualizzate al profilo. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo di componente: Metrica |
| Offerte Invia | Il numero di offerte inviate al profilo. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo di componente: Metrica |
| Trigger delle offerte | Il numero di offerte scelte per la visualizzazione dall’SDK client. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: Metrica |
| Offerte Annulla sottoscrizione | Il numero di offerte richieste dal profilo da non visualizzare in futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: Metrica |

{style="table-layout:auto"}

[1] Puoi definire più metriche per i vari tipi di evento disponibili. Vedi [Includi impostazioni del componente Valori di esclusione](/help/data-views/component-settings/include-exclude-values.md) per ulteriori informazioni.
