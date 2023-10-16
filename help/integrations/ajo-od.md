---
title: Integrare la gestione delle decisioni di Adobe Journey Optimizer con Adobe Customer Journey Analytics
description: Importa i dati generati da Adobe Journey Optimizer Decision Management e analizzali utilizzando Analysis Workspace all’interno di Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
source-git-commit: 2429c60cab701017702e3312770232aa329e303c
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 20%

---

# Integrare la gestione delle decisioni con Adobe Customer Journey Analytics


Adobe Journey Optimizer [Gestione delle decisioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) semplifica la personalizzazione con una libreria centrale di offerte di marketing e un motore decisionale che applica regole e vincoli ai profili avanzati e in tempo reale creati da Adobe Experience Platform, per aiutarti a inviare ai tuoi clienti l’offerta giusta al momento giusto.

La gestione delle decisioni fa parte di Adobe Journey Optimizer ed è integrata con essa. Può essere utilizzato anche indipendentemente dai percorsi e dalle campagne definiti in Adobe Journey Optimizer, utilizzando il suo ricco [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) supporto.

È possibile importare i dati generati da Gestione delle decisioni per eseguire analisi avanzate in Customer Journey Analytics eseguendo i passi riportati di seguito.

## Inviare dati da Gestione decisioni a Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra la gestione delle decisioni e il Customer Journey Analytics. I dati provenienti dalla gestione delle decisioni sono raccolti in Experienci Platform **automaticamente** o come parte di **eventi di esperienza inviati in modo esplicito** ad esempio impression o clic. Consulta [Guida introduttiva alla raccolta dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) per ulteriori dettagli.

## Creare una connessione

Una volta che i dati di Gestione delle decisioni sono in Adobe Experience Platform, puoi creare una [Connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) in base ai set di dati di Gestione delle decisioni. Oppure puoi aggiungere set di dati di Gestione delle decisioni a una connessione esistente.

Seleziona e configura i seguenti set di dati:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandbox_ decisioning | Evento | ID persona: `IdentityMap` | Contiene dati generati automaticamente per gli eventi di decisione di Gestione delle decisioni. _Sandbox_ fa riferimento al nome specifico della sandbox. |
| Set di dati evento feedback messaggi Adobe Journey Optimizer | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna dei messaggi. |
| Set di dati evento di tracciamento e-mail Adobe Journey Optimizer | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail. |
| Set di dati evento di tracciamento push Adobe Journey Optimizer | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento push. |
| Set di dati di entità Adobe Journey Optimizer | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano i metadati di Percorsi e Campaign a tutti i dati evento Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Creare una visualizzazione dati

Dopo aver creato una connessione, puoi creare una o più [Viste dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>[!NOTE]
>
>Le discrepanze di dati tra Adobe Journey Optimizer e il Customer Journey Analytics sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.

### Configurare le dimensioni

Puoi creare le dimensioni seguenti in una visualizzazione dati per ottenere una parità approssimativa con dimensioni simili in Gestione delle decisioni. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione della dimensione.

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

Per ottenere una parità approssimativa con metriche simili in Gestione delle decisioni, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- |
| Tipo di evento (rinominare per fare riferimento a un evento specifico, ad esempio `Feedback` per `message.feedback`) [1] | Importo di un tipo specifico di evento | `eventType` | Tipo di componente: metrica <br/>**[!UICONTROL Set Include Exclude Values]**: attivato<br/>**[!UICONTROL Match]**: [!UICONTROL If all criteria are met]<br/>**[!UICONTROL Criteria]**:**[!UICONTROL Equals]**`message.feedback` |
| Punteggio opzione di decisione | Valore calcolato per un’opzione di decisione nel contesto di un singolo ambito. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo di componente: metrica |
| Punteggio opzione decisione di fallback | Valore calcolato per un’opzione di decisione di fallback nel contesto di un singolo ambito. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo di componente: metrica |
| Offerte ignorate | Il numero di offerte ignorate o rifiutate senza alcuna altra interazione diretta. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: metrica |
| Visualizzazione offerte | Il numero di offerte visualizzate nel profilo. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: metrica |
| Offerte interattive | Il numero di offerte visualizzate nel profilo. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo di componente: metrica |
| Invio offerte | Il numero di offerte inviate al profilo. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo di componente: metrica |
| Attivatore offerte | Il numero di offerte scelte per essere visualizzate dall’SDK client. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: metrica |
| Annullamento iscrizione offerte | Il numero di offerte richieste dal profilo da non mostrare in futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: metrica |

{style="table-layout:auto"}

[1] Puoi definire più metriche per i vari tipi di evento disponibili. Consulta [Includi impostazioni del componente Valori di esclusione](/help/data-views/component-settings/include-exclude-values.md) per ulteriori informazioni.
