---
title: Integrare la gestione delle decisioni di Adobe Journey Optimizer con Adobe Customer Journey Analytics
description: Inserire i dati generati da,la gestione delle decisioni di Adobe Journey Optimizer e analizzali utilizzando Analysis Workspace all’interno di Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '698'
ht-degree: 100%

---

# Integrare la gestione delle decisioni con Adobe Customer Journey Analytics


La funzione [Gestione delle decisioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=it) di Adobe Journey Optimizer semplifica la personalizzazione con una libreria centrale di offerte di marketing e un motore decisionale che applica regole e vincoli ai profili avanzati e in tempo reale creati da Adobe Experience Platform, per aiutarti a inviare ai tuoi clienti l’offerta giusta al momento giusto.

La gestione delle decisioni fa parte di Adobe Journey Optimizer ed è integrata con essa. Può essere utilizzata anche indipendentemente dai percorsi e dalle campagne definiti in Adobe Journey Optimizer, utilizzando il suo ricco supporto [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=it).

Puoi importare i dati generati dalla gestione delle decisioni per eseguire analisi avanzate in Customer Journey Analytics attraverso i seguenti passaggi:

## Inviare dati dalla gestione delle decisioni ad Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra la gestione delle decisioni e Customer Journey Analytics. I dati provenienti dalla gestione delle decisioni sono raccolti in Experience Platform **automaticamente** o come parte di **eventi di esperienza inviati in modo esplicito** (ad esempio impression o clic). Per ulteriori informazioni, consulta la [Guida introduttiva sulla raccolta dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=it).

## Creare una connessione

Una volta che i dati della gestione delle decisioni sono in Adobe Experience Platform, puoi creare una [connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) in base al set di dati della gestione delle decisioni. Oppure puoi aggiungere set di dati della gestione delle decisioni a una connessione esistente.

Seleziona e configura i seguenti set di dati:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| ODE DecisonEvents - decisioning della _sandbox_ | Evento | ID persona: `IdentityMap` | Contiene dati generati automaticamente per gli eventi di decisione della gestione delle decisioni. _Sandbox_ fa riferimento al nome specifico della sandbox. |
| Set di dati evento feedback messaggio Adobe Journey Optimizer | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna dei messaggi. |
| Set di dati evento esperienza tracciamento e-mail di Adobe Journey Optimizer | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail. |
| Set di dati evento esperienza tracciamento push di Adobe Journey Optimizer | Evento | ID Persona: `IdentityMap` | Contiene eventi di tracciamento push. |
| Set di dati di entità di Adobe Journey Optimizer | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano i metadati di percorso e campagna a tutti i dati evento Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Creare una visualizzazione dati

Dopo aver creato una connessione, puoi creare una o più [Viste dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>[!NOTE]
>
>Le discrepanze di dati tra Adobe Journey Optimizer e Customer Journey Analytics sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.

### Configurare le dimensioni

Per ottenere una parità approssimativa con dimensioni simili nella gestione delle decisioni, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione della dimensione.

| Dimensione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- |
| Nome attività | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo di componente: dimensione |
| Identificatore contenitore | `_experience.decisioning.containerID` | Tipo di componente: dimensione |
| Identificatore di correlazione | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo di componente: dimensione |
| Nome opzione di decisione | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo di componente: dimensione |
| Nome opzione decisione di fallback | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo di componente: dimensione |
| Nome posizionamento | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo di componente: dimensione |

{style="table-layout:auto"}


### Configurare le metriche

Per ottenere una parità approssimativa con metriche simili nella gestione delle decisioni, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- |
| Tipo di evento (rinomina per fare riferimento a un evento specifico, ad esempio `Feedback` per `message.feedback`) [1] | Quantità di un tipo specifico di evento | `eventType` | Tipo di componente: metrica <br/>**[!UICONTROL Set Include Exclude Values]**: attivato<br/>**[!UICONTROL Match]**: [!UICONTROL If all criteria are met]<br/>**[!UICONTROL Criteria]**:**[!UICONTROL Equals]**`message.feedback` |
| Punteggio opzione di decisione | Valore calcolato per un’opzione di decisione nel contesto di un singolo ambito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo di componente: metrica |
| Punteggio opzione decisione di fallback | Valore calcolato per un’opzione di decisione di fallback nel contesto di un singolo ambito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo di componente: metrica |
| Offerte ignorate | Il numero di offerte ignorate o rifiutate senza altre interazioni dirette. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: metrica |
| Offerte visualizzate | Il numero di offerte visualizzate nel profilo. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: metrica |
| Offerte interattive | Il numero di offerte visualizzate nel profilo. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo di componente: metrica |
| Offerte inviate | Il numero di offerte inviate al profilo. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo di componente: metrica |
| Trigger offerte | Il numero di offerte scelte per essere visualizzate dall’SDK client. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: metrica |
| Annullamento dell’abbonamento alle offerte | Numero di offerte richieste dal profilo da non mostrare in futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: metrica |

{style="table-layout:auto"}

[1] Puoi definire più metriche per i vari tipi di evento disponibili. Per ulteriori informazioni, consulta le [impostazioni dei componenti - Valori da includere/escludere](/help/data-views/component-settings/include-exclude-values.md).
