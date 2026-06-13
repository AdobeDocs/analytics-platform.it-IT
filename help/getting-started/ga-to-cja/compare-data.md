---
title: Perché differiscono i dati di GA4 e Customer Journey Analytics
description: Scopri perché i dati tra GA4 e Customer Journey Analytics possono differire e come controllare le discrepanze.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# Perché differiscono i dati di GA4 e Customer Journey Analytics

È normale che GA4 e Customer Journey Analytics riporti numeri diversi per lo stesso periodo di tempo e la stessa metrica apparente. Diversi metodi di raccolta dei dati, definizioni delle metriche, modelli di identità e regole di sessione contribuiscono alle discrepanze. Questa pagina illustra le fonti di differenza più comuni e fornisce indicazioni per il controllo di lacune non spiegate.

## Sessioni impegnate

GA4 considera una sessione come **innestata** se è durata 10 o più secondi, include almeno un evento chiave o include 2 o più visualizzazioni di pagina. Questa singola definizione supporta diverse metriche GA4, tra cui il tasso di coinvolgimento, il tasso di rimbalzo e la soglia di coinvolgimento dietro gli utenti attivi.

Customer Journey Analytics non dispone di una metrica o dimensione di sessione integrata; puoi definire il coinvolgimento in base al tuo business. Adobe consiglia di creare un segmento che acquisisca i criteri di coinvolgimento e di riutilizzare tale segmento laddove il coinvolgimento è importante. L’amministratore può anche promuovere questa definizione in una metrica nella visualizzazione dati in modo che sia disponibile per tutti.

Quando formuli i tuoi criteri, scegli i segnali che indicano realmente il valore del tuo sito. Tre elementi costitutivi comuni per il coinvolgimento includono:

* **Durata**: durata minima della sessione, ad esempio 10 o più secondi
* **Profondità**: un numero minimo di eventi o visualizzazioni di pagina, ad esempio 2 o più
* **Azione**: presenza di un evento di conversione o chiave, ad esempio un abbonamento o un acquisto

È possibile combinarle con `OR` in modo che una sessione sia considerata come attiva se soddisfa una condizione (come fa GA4) o combinarle con `AND` per un requisito più rigoroso. Se l’obiettivo è la parità con GA4, inizia dalle impostazioni predefinite e sintonizza da lì.

### Tasso di coinvolgimento

Una volta definita una sessione attiva, il tasso di coinvolgimento è la percentuale di sessioni attive. Per generarlo come metrica calcolata:

1. In Analysis Workspace, seleziona l&#39;icona **[!UICONTROL +]** accanto all&#39;elenco delle metriche per aprire il Generatore di metriche calcolate.
2. Denominalo &quot;Livello di coinvolgimento&quot; e imposta il formato su **[!UICONTROL Percentuale]**.
3. Definisci la formula come segmento di sessioni impegnate diviso per **[!UICONTROL Sessioni]**.
4. Seleziona **[!UICONTROL Salva]**.

### Percentuale mancati recapiti

In GA4, un mancato recapito è l&#39;inverso di una sessione attiva, quindi la frequenza di mancato recapito di GA4 è uguale a `1 - Engagement Rate`. Generalo in Customer Journey Analytics come seconda metrica calcolata utilizzando tale formula.

Customer Journey Analytics fornisce anche una metrica incorporata **[!UICONTROL Bounce Rate]**, ma la sua definizione predefinita è diversa: conta le sessioni in cui è stato registrato un solo evento, che è direzionalmente opposto alla definizione di GA4 per molti siti. Confrontando la percentuale di mancato recapito di GA4 con la metrica predefinita [!UICONTROL Percentuale di mancato recapito], anziché con il calcolo di `1 - Engagement Rate`, si ottengono numeri sostanzialmente diversi.

>[!TIP]
>
>La definizione della sessione in Customer Journey Analytics è configurabile in base alla visualizzazione dati. Le definizioni di mancato recapito e coinvolgimento possono essere regolate in base ai criteri di GA4 (durata 10 secondi, più di 2 visualizzazioni di pagina o un evento chiave) se tale parità è un requisito di reporting per la tua organizzazione.

## Sessioni

Per impostazione predefinita, sia GA4 che Customer Journey Analytics hanno un timeout di inattività di 30 minuti ed entrambi mantengono una sessione per tutta la mezzanotte e per una modifica alla campagna di metà sessione. (Le sessioni di ripristino di Universal Analytics in entrambi i casi sono quindi una fonte comune di confusione, ma non rappresentano differenze tra GA4 e Customer Journey Analytics.) Le regole che differiscono sono:

| Regola | GA4 | Customer Journey Analytics |
|---|---|---|
| Timeout di inattività | Regolabile a livello di proprietà (impostazione predefinita di 30 minuti, fino a 7 ore e 55 minuti) | Configurabile per visualizzazione dati |
| Eventi di avvio della sessione | Solo `session_start` (automatico) | Configurabile; qualsiasi evento può avviare una sessione |
| Eventi di fine sessione | Nessuno | Configurabile; qualsiasi evento può terminare una sessione |

Poiché la definizione della sessione di Customer Journey Analytics è configurabile, i conteggi delle sessioni dipendono da come è impostata la visualizzazione dati. La corrispondenza tra il timeout di una visualizzazione dati e gli eventi di avvio della sessione e la proprietà GA4 avvicina i conteggi delle sessioni tra le piattaforme.

## Persone e utenti attivi

La metrica utente principale di GA4, **Utenti attivi**, conta gli utenti che hanno avuto almeno una sessione attiva nell&#39;intervallo di date. La metrica **[!UICONTROL Persone]** in Customer Journey Analytics conta ID persona univoci nell&#39;intervallo di date.

Ci si aspetta che queste metriche differiscano per diversi motivi:

* **Soglia di coinvolgimento**: gli utenti attivi di GA4 escludono i visitatori che non hanno avuto [sessione attiva](#engaged-sessions). La metrica [!UICONTROL Persone] in Customer Journey Analytics include tutti, indipendentemente dal livello di coinvolgimento.
* **[!UICONTROL Unione]**: se l&#39;unione è abilitata, una persona che ha visitato da un dispositivo mobile e da un desktop può essere conteggiata come una sola persona in Customer Journey Analytics ma due utenti in GA4. In genere, l&#39;unione rende la metrica [!UICONTROL Persone] inferiore agli utenti GA4 nei set di dati uniti.
* **Modello identità**: GA4 utilizza un modello identità a catena; Customer Journey Analytics utilizza qualsiasi ID persona definito nel set di dati. Queste differenze influiscono sui conteggi delle persone indipendentemente dall’unione.

## Identità e unione

GA4 utilizza un modello di identità a catena per identificare gli utenti:

1. User-ID (se impostato dall’implementazione)
2. Segnali Google (se l’utente ha effettuato l’accesso a un account Google con la personalizzazione abilitata)
3. ID dispositivo (ID client basato su cookie)

Nella maggior parte delle implementazioni, l’ID persona è un ECID (Experience Cloud ID). La funzione opzionale **[!UICONTROL Unione]** può quindi risolvere le identità tra dispositivi e canali utilizzando metodi basati sui campi o basati su grafico, consentendo l&#39;associazione di una sessione dell&#39;app mobile e di una sessione del browser desktop alla stessa persona.

Poiché la risoluzione delle identità varia tra le piattaforme, i conteggi a livello utente raramente corrispondono esattamente. Questa discrepanza è prevista e non indica un problema di qualità dei dati.

## Attribuzione

GA4 applica un modello di attribuzione per reporting configurato a livello di proprietà (in Amministratore), con l’attribuzione basata sui dati come impostazione predefinita. Come Customer Journey Analytics, GA4 valuta questo modello al momento della generazione del rapporto, quindi modificandolo aggiorna retroattivamente i rapporti storici e futuri. In GA4, tuttavia, il modello è a livello di proprietà e influisce solo sui rapporti chiave-evento che utilizzano dimensioni di traffico basate su eventi (come Source, Medium e Campaign).

Customer Journey Analytics applica anche l’attribuzione al momento della generazione del rapporto, ma con un controllo più granulare. Esistono due posizioni per configurarlo:

* **Impostazioni visualizzazione dati**: è possibile impostare un [modello di attribuzione](/help/data-views/component-settings/attribution.md) su qualsiasi componente di metrica nella visualizzazione dati, stabilendo il valore predefinito per tale metrica in tutti i report. Per impostazione predefinita, non viene applicato alcun modello di attribuzione. Puoi configurare una visualizzazione dati in modo che contenga più copie della stessa metrica, ciascuna delle quali utilizza un modello di attribuzione predefinito diverso.
* **Sostituzione a livello di componente**: dopo aver trascinato una metrica in una [!UICONTROL tabella a forma libera], fare clic con il pulsante destro del mouse sull&#39;intestazione di colonna e selezionare **[!UICONTROL Usa modello di attribuzione non predefinito]** per sostituirla per l&#39;istanza. Puoi anche trascinare la stessa metrica nella tabella più volte, ciascuna delle quali utilizza un modello di attribuzione diverso per un confronto diretto affiancato.

Poiché GA4 utilizza per impostazione predefinita l’attribuzione basata sui dati mentre Customer Journey Analytics non applica alcun modello, a meno che non ne configuri uno, è probabile che le metriche di conversione e di canale differiscano fino a quando non vengono allineate. L’impostazione di GA4 su un modello con ultimo clic e la configurazione di un modello con ultimo contatto corrispondente in Customer Journey Analytics è il modo più affidabile per stabilire una linea di base simile. Qualsiasi modifica del modello in Customer Journey Analytics si applica retroattivamente a tutti i dati storici senza nuova elaborazione.

## Discrepanze nell’audit

Quando i numeri differiscono più del previsto, sono disponibili tre percorsi di audit:

* **Assurance**: lo strumento di convalida interno al prodotto di Adobe conferma che gli eventi XDM si attivano correttamente, raggiungono Edge Network e vengono scritti nei set di dati della piattaforma. Utilizza questo strumento per verificare l’implementazione prima di confrontare i numeri dei rapporti.
* **Anteprime set di dati**: nell&#39;interfaccia utente di Platform è possibile visualizzare in anteprima le righe non elaborate in qualsiasi set di dati. Confrontali con l’esportazione DebugView o BigQuery di GA4 per verificare la precisione a livello di campo.
* **Adobe Consulting**: per discrepanze inspiegabili persistenti, il team del tuo account Adobe può organizzare un controllo formale dell&#39;implementazione con un consulente Adobe.
* **Revisione dell&#39;acquisizione**: se si sospetta che la discrepanza abbia origine dal modo in cui i dati GA sono stati introdotti in Platform, anziché nelle definizioni di reporting, rivedere la configurazione dell&#39;acquisizione in [Eseguire la migrazione dei dati da Google Analytics](/help/use-cases/third-party/ga/overview.md).
