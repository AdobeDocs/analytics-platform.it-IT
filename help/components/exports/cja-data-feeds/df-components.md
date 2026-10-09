---
title: Componenti disponibili nei feed dati di Customer Journey Analytics
description: Scopri quali dimensioni e metriche sono necessarie, non supportate, soggette a restrizioni o devono essere sostituite durante la creazione di feed di dati di Customer Journey Analytics.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: d7614102d54af57a3a084c8550041f8e04f4bc37
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 42%
---
# Disponibilità dei componenti nei feed di dati

{{release-limited-testing}}

Non tutti i componenti Customer Journey Analytics possono essere utilizzati nei feed di dati. Alcune dimensioni sono incluse in ogni feed di dati, alcuni componenti non possono essere inclusi e alcune metriche devono essere sostituite con un sostituto.

Utilizzare le informazioni seguenti per capire quali componenti è possibile includere quando si [crea un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md).

## Dimensioni obbligatorie {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Dimensioni obbligatorie"
>abstract="Ogni feed di dati deve includere determinate dimensioni, identificate da un’etichetta **Obbligatorio** accanto al nome della dimensione. Queste dimensioni forniscono la struttura minima necessaria per l’analisi a livello di evento."

<!-- markdownlint-enable MD034 -->

Le seguenti dimensioni sono incluse per impostazione predefinita in ogni feed di dati e non possono essere rimosse:

| Nome dimensione | Note | Feed di dati | Altre attività di reporting |
|---|---|---|---|
| Marca temporale UTC | La data e l’ora in cui si è verificato l’evento, rappresentate nel fuso orario UTC. Supporta la granularità al secondo secondario (microsecondo). | Obbligatorio | Non disponibile |
| ID riga | Identificatore univoco di ciascuna riga inclusa nel feed di dati. | Obbligatorio | Non disponibile |
| ID sessione | Identificatore univoco di ciascuna sessione inclusa nel feed di dati. | Obbligatorio | Non disponibile |
| ID persona | Identificatore della persona per la visualizzazione dati e la connessione | Obbligatorio | Standard opzionale |
| ID account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID account quando si utilizza il contenitore Account | Obbligatorio | Standard opzionale |

## Dimensioni non supportate {#unsupported-dimensions}

Le dimensioni standard di Customer Journey Analytics non possono essere incluse nei feed di dati. Nella tabella seguente sono elencate queste dimensioni:

| Nome dimensione | Note | Feed di dati |
|---|---|---|
| 5 minuti | Intervalli di cinque minuti quando si sono verificati gli eventi (arrotondati per difetto) | Non disponibile |
| 15 minuti | Intervalli di quindici minuti quando si sono verificati gli eventi (arrotondati per difetto) | Non disponibile |
| 30 minuti | Intervalli di trenta minuti quando si sono verificati gli eventi (arrotondati per difetto) | Non disponibile |
| Giorno | Giorno in cui si è verificato un evento | Non disponibile |
| Giorno della settimana | Giorno della settimana in cui si è verificato un evento | Non disponibile |
| Giorno del mese | Giorno del mese in cui si è verificato un evento | Non disponibile |
| Ora | Ora in cui si è verificato un evento (arrotondata per difetto) | Non disponibile |
| Ora del giorno | Ora del giorno in cui si è verificato un evento (arrotondata per difetto) | Non disponibile |
| Minuto | Minuto di un evento (arrotondato per difetto) | Non disponibile |
| Minuto dell’ora | Minuto dell’ora in cui si è verificato un evento (arrotondato per difetto) | Non disponibile |
| Mese | Mese in cui si è verificato un evento | Non disponibile |
| Mese dell’anno | Mese dell’anno in cui si è verificato un evento | Non disponibile |
| Trimestre | Si è verificato un evento nel trimestre | Non disponibile |
| Trimestre dell’anno | Trimestre dell’anno in cui si è verificato un evento | Non disponibile |
| Second | Si è verificato un secondo evento (arrotondato per difetto) | Non disponibile |
| Settimana | Settimana in cui si è verificato un evento | Non disponibile |
| Settimana dell’anno | Settimana dell’anno in cui si è verificato un evento | Non disponibile |
| Anno | Anno in cui si è verificato un evento | Non disponibile |

## Metriche non supportate {#unsupported-metrics}

Le metriche standard di Customer Journey Analytics seguenti non possono essere incluse nei feed di dati:

| Nome della metrica | Note | Feed di dati |
|---|---|---|
| Profilo dei visitatori di Adobe | | Non disponibile |
| Unione opportunità Adobe | | Non disponibile |
| Profilo opportunità Adobe | | Non disponibile |
| Unione account Adobe | | Non disponibile |
| Profilo account Adobe | | Non disponibile |
| Unione dei gruppi di acquisto Adobe | | Non disponibile |
| Profilo gruppi di acquisto Adobe | | Non disponibile |
| Unione degli account globali di Adobe | | Non disponibile |
| Profilo account globali Adobe | | Non disponibile |
| Unione persone Adobe | | Non disponibile |
| Profilo Persone Adobe | | Non disponibile |

## Dimensioni che non possono essere utilizzate insieme {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="I dati dell’agente utente e i dati di ricerca del dispositivo non possono esistere nella stessa configurazione di feed di dati."

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>Alcune dimensioni non possono essere utilizzate insieme nei set di dati di Experience Platform e pertanto non possono essere incluse nello stesso feed di dati.
>
>Se scegli di includere le dimensioni **Agente utente** o **ID dispositivo mobile** nel feed dati, le dimensioni elencate di seguito non possono essere aggiunte al feed dati.
>
>Se utilizzi il Web SDK, questa restrizione viene applicata nei flussi di dati prima che i dati arrivino in un set di dati di Experience Platform. Per ulteriori informazioni, vedere [Configurare la ricerca del dispositivo](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure#geolocation-device-lookup) in [Creare e configurare gli stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) nella guida alla raccolta dati.

Le dimensioni seguenti non possono essere utilizzate insieme alle dimensioni **Agente utente** o **ID dispositivo mobile**:

* Tipo di browser
* Browser
* Dispositivo mobile - Produttore
* Tipo di dispositivo mobile
* Supporto audio per dispositivi mobili
* DRM mobile
* VM Java mobile
* Mobile Information Services
* Supporto immagini per dispositivi mobili
* Profondità colore mobile
* Protocolli di rete mobile
* Numero dispositivo mobile
* Lunghezza massima e-mail mobile
* Decoration Mail mobile
* Push-to-talk per dispositivi mobili
* Larghezza schermo per dispositivi mobili
* Lunghezza massima URL browser mobile
* Sistema operativo mobile (obsoleto)
* Altezza schermo per dispositivi mobili
* Supporto video per dispositivi mobili
* Supporto per cookie mobili
* Lunghezza massima segnalibro mobile
* Dimensioni schermo per dispositivi mobili
* Nome dispositivo mobile
* Tipi di sistemi operativi
* Sistemi operativi

## Metriche che richiedono un sostituto {#substitute-metrics}

Le metriche di Customer Journey Analytics seguenti devono essere sostituite:

| Nome della metrica | Note | Feed di dati |
|---|---|---|
| Account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | In base all’ID account specificato nella connessione | Non disponibile. Utilizza il conteggio distinto dall’ID account. |
| Acquisto del gruppo [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Comprare gruppi in base all’ID gruppo di acquisto nella connessione | Non disponibile. Utilizza il conteggio distinto dall’ID del gruppo di acquisto. |
| Eventi | Numero di righe da tutti i set di dati evento in una connessione | Non disponibile. Utilizza il conteggio distinto dall’ID riga. |
| Account globali [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | In base all’ID account globale nella connessione | Non disponibile. Utilizza il conteggio distinto dall’ID account globale. |
| Opportunità [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunità basate sull’ID opportunità nella connessione | Non disponibile. Utilizza il conteggio distinto dall’ID opportunità. |
| Persone | In base all’ID persona specificato in una connessione | Non disponibile. Utilizza il conteggio distinto dall’ID persona. |
| Conversazioni | Numero di conversazioni | Non disponibile. Utilizza il conteggio distinto dall’ID conversazione. |
| Fine della sessione | Numero di eventi che sono stati l’ultimo evento di una sessione | Non disponibile |
| Inizio della sessione | Numero di eventi che sono stati il primo evento di una sessione | Non disponibile |
| Sessioni | In base alle impostazioni di sessione della visualizzazione dati | Non disponibile. Utilizza il conteggio distinto dall’ID sessione. |
| Tempo trascorso (secondi) | Somma il tempo tra due diversi valori di dimensione | Non disponibile |

## Componenti standard opzionali {#optional-standard-components}

| Nome componente | Tipo | Note | Feed di dati |
|---|---|---|---|
| AM/PM | Dimensione suddivisa in base al tempo | Mattina o pomeriggio | Non disponibile |
| ID batch | Dimensione | Identificatore per un batch di Experience Platform | Disponibile |
| ID set di dati | Dimensione | Identificatore per un set di dati di Experience Platform | Disponibile |
| Giorno del mese | Dimensione suddivisa in base al tempo | 1-31 | Non disponibile |
| Giorno della settimana | Dimensione suddivisa in base al tempo | Da lunedì a domenica | Non disponibile |
| Giorno dell’anno | Dimensione suddivisa in base al tempo | 1-366 | Non disponibile |
| Profondità evento | Dimensione | Valore numerico sequenziale (1, 2, 3, ecc.) assegnato a ogni interazione di evento all’interno di una sessione<p>Reimposta all&#39;inizio di ogni nuova sessione</p> | Disponibile |
| Ora del giorno | Dimensione suddivisa in base al tempo | 0-23 | Non disponibile |
| Mese dell’anno | Dimensione suddivisa in base al tempo | Gennaio-Dicembre | Non disponibile |
| Prime sessioni | Metrica | Prima sessione definita da una persona all’interno dell’intervallo di reporting | Non disponibile |
| Sessioni di ritorno | Metrica | Sessioni che non sono state la prima sessione di una persona | Non disponibile |
| Spazio dei nomi ID persona | Dimensione | Tipo di ID costituito dall’ID persona (ad esempio, e-mail o ID cookie) | Disponibile |
| ID account globale [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensione | ID account globale quando si utilizza il contenitore Account globale | Disponibile |
| ID opportunità [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensione | ID opportunità quando si utilizza il contenitore Opportunità | Disponibile |
| ID gruppo acquisti [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensione | ID gruppo di acquisto quando si utilizza il contenitore Gruppo di acquisto | Disponibile |
| Trimestre dell’anno | Dimensione suddivisa in base al tempo | Q1, Q2, Q3, Q4 | Non disponibile |
| Ripeti sessione | Metrica | Sessioni che non sono state le prime sessioni di una persona | Non disponibile |
| Tipo di sessione | Dimensione | Due valori: Primo tentativo o Restituzione | Non disponibile |
| Tempo trascorso per evento | Dimensione | Intervalli metrica Tempo trascorso nei bucket di eventi | Non disponibile |
| Tempo trascorso per sessione | Dimensione | Intervalli metrica Tempo trascorso nei bucket di sessione | Non disponibile |
| Tempo trascorso per persona | Dimensione | Intervalli metrica Tempo trascorso in intervalli di persone | Non disponibile |
| Fine settimana/Giorno feriale | Dimensione suddivisa in base al tempo | Fine settimana o giorno feriale | Non disponibile |
