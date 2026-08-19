---
title: Creare un feed dati
description: Scopri come creare un feed di dati e le informazioni sui file da fornire ad Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e7c2598015d3ee271bb7e0f64937fd1c457b5433
workflow-type: tm+mt
source-wordcount: 4033
ht-degree: 17%

---

# Creare un feed di dati

{{release-limited-testing}}

Durante la creazione di un feed di dati, fornisci ad Adobe:

* Informazioni sulla destinazione in cui si desidera inviare i file di dati non elaborati

* Dati da includere in ciascun file

* Frequenza con cui vengono inviati i dati (incluso il ritardo di elaborazione per acquisire gli eventi in ritardo)

Prima di creare un feed di dati, è importante avere una conoscenza di base dei feed di dati e assicurarsi di soddisfare tutti i prerequisiti. Per ulteriori informazioni, consulta [Panoramica sui feed di dati](data-feed-overview.md).

## Creare e configurare un feed di dati {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifesto"
>abstract="Scegli se includere un file manifesto con ogni consegna di feed di dati. I file manifesto contengono informazioni per ciascun file incluso nel feed di dati. Quando invii i dati di un feed di dati in un singolo pacchetto, puoi scegliere di includere un file finale (.fin), ma è consigliabile utilizzare i file manifest. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Notifica dei problemi, al completamento e alla scadenza"
>abstract="Specifica uno o più indirizzi e-mail a cui inviare una notifica quando il feed di dati viene completato, è in scadenza o riscontra problemi. Separa più indirizzi e-mail con una virgola."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Ritardo elaborazione"
>abstract="Il tempo di attesa per gli eventi in ritardo prima dell’elaborazione di un file di feed dati. Eventuali hit in ritardo che arrivano durante il periodo di ritardo dell’elaborazione sono inclusi nel feed di dati. <p>I ritardi di elaborazione sono utili per vari motivi, ad esempio per dare alle implementazioni mobili l’opportunità di connettere e inviare dati ai dispositivi offline o per adattarsi ai processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza.</p><p>Per poter essere incluse, le sessioni devono iniziare dopo il cut-off del ritardo di elaborazione; le sessioni che iniziano prima del cut-off e terminano entro il ritardo di elaborazione non sono incluse.</p><p>Customer Journey Analytics determina in modo dinamico il ritardo ottimale in base a quanto tempo richiedono in genere gli eventi in ritardo per il feed, ma puoi impostarlo manualmente per un ritardo di 2, 3, 4 o 8 ore.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="I dati dell’agente utente e i dati di ricerca del dispositivo non possono esistere nella stessa configurazione di feed dati."

<!-- markdownlint-enable MD034 -->

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.

1. Seleziona [!UICONTROL **Customer Journey Analytics**] dal selettore di app ![App](/help/assets/icons/Apps.svg) in alto a destra nell’interfaccia.

1. Nella barra di navigazione superiore, vai a [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Feed dati**].

1. Seleziona [!UICONTROL **Crea**] nell&#39;angolo superiore destro dello schermo.

   In alternativa, se in precedenza non è stato creato alcun feed di dati, selezionare [!UICONTROL **Crea feed di dati**] all&#39;interno della tabella vuota.

   Viene visualizzata una pagina con le seguenti schede: [!UICONTROL **Dettagli**], [!UICONTROL **Struttura dati**] e [!UICONTROL **Consegna**].

   ![Nuova pagina feed dati](assets/data-feed-new.png)

1. Nella scheda [!UICONTROL **Dettagli**], completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome**] | Nome del feed dati. I nomi devono essere univoci all’interno della visualizzazione dati selezionata e possono contenere fino a 255 caratteri. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tag**] | Applica eventuali tag al feed dati per facilitarne la classificazione. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descrizione**] | Specifica una descrizione per il feed di dati (fino a 500 caratteri). La descrizione aggiunta è visibile quando si modifica il feed dati. |
   | [!UICONTROL **Visualizzazione dati**] | Selezionare la visualizzazione dati contenente i dati che si desidera esportare.<p>Quando selezioni una visualizzazione dati, tieni presente quanto segue:</p> <ul><li>Se vengono creati più feed di dati per la stessa visualizzazione dati, ogni feed di dati deve avere definizioni di colonne diverse.</li><li>L’elenco delle colonne disponibili dipende dalla società di accesso a cui appartiene la visualizzazione dati selezionata. Se modifichi la visualizzazione dati, l’elenco delle colonne disponibili può cambiare. </li></ul> |

1. Seleziona [!UICONTROL **Avanti**].

1. Nella scheda [!UICONTROL **Data structure**], assicurati che nel campo **[!UICONTROL Data view]** sia selezionata la visualizzazione dati corretta.

   <!--add screenshot-->

1. Nel menu a discesa [!UICONTROL **Segmenti**], cerca e seleziona eventuali segmenti per filtrare i dati inclusi nel feed.

   Quando applichi più segmenti, questi vengono uniti insieme a un operatore AND. Per unire i segmenti con un operatore OR, devi prima creare un nuovo segmento nel generatore di segmenti, quindi applicare il nuovo segmento al feed di dati.

1. Aggiungi componenti alla configurazione del feed dati. La barra a sinistra mostra solo i componenti validi per i feed di dati.

   * **Trascina e rilascia**: trascina i componenti dalla barra a sinistra all&#39;area di lavoro. Tenere premuto **[!UICONTROL Maiusc]** oppure tenere premuto **[!UICONTROL Comando]** (macOS) o **[!UICONTROL Ctrl]** (Windows) per selezionare e trascinare più componenti contemporaneamente.
   * **Pulsante Plus**: seleziona l&#39;icona Più ![Aggiungi](/help/assets/icons/Add.svg) accanto a qualsiasi componente nella barra a sinistra per aggiungerlo all&#39;area di lavoro.
   * **[!UICONTROL Mostra tutto]**: seleziona **[!UICONTROL Mostra tutto]** nella parte inferiore dell&#39;elenco dei componenti per aprire una finestra di dialogo che mostra tutti i componenti disponibili. Selezionare la casella di controllo accanto a ogni componente che si desidera aggiungere, quindi selezionare **[!UICONTROL Aggiungi selezionati]**. Quando un termine di ricerca o un tag di filtro è attivo nella barra a sinistra, viene visualizzato anche un pulsante **[!UICONTROL Aggiungi tutto]** che consente di aggiungere tutti i risultati filtrati contemporaneamente.

   Quando aggiungi un componente che appartiene a un campo array XDM (ad esempio, un campo di proposta Adobe Journey Optimizer), questo viene visualizzato nell’area di lavoro come gruppo nidificato comprimibile anziché come elemento a comparsa. Il gruppo riflette la struttura di dati sottostante e restituisce come array nidificato nel file esportato.

   <!--add screenshot-->

   +++ Dimensioni sempre incluse nei feed di dati

   Le seguenti dimensioni sono incluse per impostazione predefinita in ogni feed di dati e non possono essere rimosse:

   | Nome dimensione | Note | Feed di dati | Altre attività di reporting |
   |---|---|---|---|
   | Marca temporale UTC | La data e l’ora in cui si è verificato l’evento, rappresentate nel fuso orario UTC. Supporta la granularità al secondo secondario (microsecondo). | Obbligatorio | Non disponibile |
   | ID riga | Identificatore univoco di ciascuna riga inclusa nel feed di dati. | Obbligatorio | Non disponibile |
   | ID sessione | Identificatore univoco di ciascuna sessione inclusa nel feed di dati. | Obbligatorio | Non disponibile |
   | ID persona | Identificatore della persona per la visualizzazione dati e la connessione | Obbligatorio | Standard opzionale |
   | ID account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID account quando si utilizza il contenitore Account | Obbligatorio | Standard opzionale |

   +++

   +++ Dimensioni che non possono essere incluse nei feed dati

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

   +++

   +++ Metriche che non possono essere incluse nei feed dati

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

   +++

   +++ Dimensioni che non possono essere utilizzate insieme nei feed di dati

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

   +++

   +++ Metriche che devono essere sostituite nei feed dati

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

   +++

   +++ Componenti standard opzionali

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

   +++

1. (Facoltativo) Riordina i componenti nell’area di lavoro trascinandoli. L’ordine definito viene mantenuto come ordine delle colonne nel file di feed dati esportato.

1. (Facoltativo) Modifica l’ID del componente visualizzato nell’output del feed dati.

   1. Passa il puntatore del mouse su un componente nell’area di lavoro, quindi seleziona l’icona delle informazioni.

   1. Nel campo ID componente specifica un nuovo ID componente.

      <!--add screenshot-->

1. (Facoltativo) Utilizza i pannelli **[!UICONTROL Riepilogo feed]** e **[!UICONTROL Anteprima schema]** sul lato destro della pagina per rivedere la struttura dei dati prima di procedere:

   * Il **[!UICONTROL riepilogo feed]** mostra un conteggio live dei componenti, delle colonne, delle dimensioni e delle metriche totali aggiunti.
   * L&#39;**[!UICONTROL Anteprima schema]** mostra una rappresentazione JSON dello schema del feed dati che viene aggiornata quando si aggiungono o si riordinano i componenti.
   * Il pulsante **[!UICONTROL Righe di esempio]** apre una finestra di dialogo in cui vengono visualizzate righe di output di esempio per verificare che la struttura sia corretta. Questa finestra di dialogo mostra solo i dati di esempio e non riflette i dati effettivi.

   <!--add screenshot-->

1. Nella scheda [!UICONTROL **Consegna**], nella sezione [!UICONTROL **Pianifica**], scegli il tipo di feed da creare (live o backfill), quindi specifica l&#39;intervallo di reporting, la frequenza e altre opzioni di configurazione:

   <!--add screenshot-->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Tipo di feed**] | Seleziona il tipo di feed da creare:<ul><li>[!UICONTROL **Feed live**]: esporta dati correnti e futuri.</li><li>[!UICONTROL **Feed di backfill**]: esporta dati storici. </li></ul> |
   | [!UICONTROL **Data di inizio**] | La data di inizio del feed di dati. Per i feed live, deve essere nella data odierna o in una data futura. Per i feed di backfill, deve essere una data passata all’interno della finestra di conservazione dei dati della visualizzazione dati. La data di inizio è basata sul fuso orario della visualizzazione dati. |
   | [!UICONTROL **Data di scadenza**] <br/>Disponibile solo per i feed attivi | La data in cui il feed dati scade e non viene più eseguito. La data è basata sul fuso orario della visualizzazione dati. |
   | [!UICONTROL **Data di fine**]<br/> Disponibile solo per i feed di backfill | La data in cui termina il feed di dati. La data di fine non può essere nel futuro. La data è basata sul fuso orario della visualizzazione dati. |
   | [!UICONTROL **Frequenza**] | Seleziona la frequenza con cui inviare il feed di dati. Gli eventi con marche temporali che rientrano nella finestra di frequenza sono inclusi nella consegna del feed di dati. I campi [!UICONTROL **Intervallo date di lookback**] e [!UICONTROL **Ritardo elaborazione**] possono anche influenzare gli eventi inclusi nei dati per la frequenza di consegna scelta.<p>Per i feed live, seleziona questa opzione per includere dati relativi a un’ora o a un giorno. Per i feed di backfill, questo campo è bloccato su **Giornaliero** e non può essere modificato.</p><ul><li>**Giornaliero**: i feed contengono dati relativi a un intero giorno, dalla mezzanotte alla mezzanotte nel fuso orario della visualizzazione dati. <p>Questa opzione è obbligatoria per i feed di backfill ed è facoltativa per i feed live.</p></li><li>**Oraria**: i feed contengono dati relativi a una sola ora. <p>Questa opzione è disponibile solo per i feed live.</p></li></ul> |
   | [!UICONTROL **Intervallo date lookback**] | Controlla quanto Customer Journey Analytics deve risalire indietro nel tempo durante l’elaborazione della consegna del feed dati. Il valore predefinito è 30 giorni. <p>L’intervallo di date del lookback influisce sulla qualificazione dei segmenti, sul calcolo della sessione, sulle trasformazioni dei campi derivati e sulla persistenza delle dimensioni. <p>Prima di configurare questa opzione, consulta i dettagli e gli esempi descritti nella sezione seguente, [Comprendere l&#39;intervallo di date del lookback](#understand-the-lookback-date-range).</p> |
   | [!UICONTROL **Ritardo elaborazione**] | Scegli la quantità di tempo di attesa prima di elaborare un file di feed dati. Il valore predefinito è 2 ore. Eventuali eventi in ritardo che arrivano durante il ritardo di elaborazione sono inclusi nel feed di dati. <p>I ritardi di elaborazione sono utili per vari motivi, ad esempio per dare alle implementazioni mobili l’opportunità di connettere e inviare dati ai dispositivi offline o per adattarsi ai processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. </p><p>Per poter essere incluse, le sessioni devono iniziare dopo il cut-off del ritardo di elaborazione; le sessioni che iniziano prima del cut-off e terminano entro il ritardo di elaborazione non sono incluse.</p><p>Customer Journey Analytics determina in modo dinamico il ritardo ottimale in base a quanto tempo richiedono in genere gli eventi in ritardo per il feed, ma puoi impostarlo manualmente per un ritardo di 2, 3, 4 o 8 ore.</p> |
   | [!UICONTROL **Formato di compressione**] | Seleziona il formato di compressione per i file di output Parquet consegnati alla destinazione cloud. Scegli uno dei seguenti formati:<ul><li>[!UICONTROL **Snappy**]: compressione e decompressione veloci con dimensioni file moderate. Ampiamente supportato da piattaforme di dati moderne come BigQuery, Snowflake e Apache Spark.</li><li>[!UICONTROL **GZip**]: ampiamente compatibile, anche con strumenti che non supportano Snappy in modalità nativa. Consigliato se la pipeline a valle richiede uno standard di compressione ampiamente riconosciuto.</li><li>[!UICONTROL **Z Standard (Zstd)**]: elevata efficienza di compressione con decompressione rapida. Adatto se la riduzione delle dimensioni del file è una priorità e i tuoi strumenti supportano Zstd.</li></ul> |

1. Nella scheda [!UICONTROL **Consegna**], nella sezione [!UICONTROL **Destinazione**], configura la destinazione in cui desideri inviare i dati.

   >[!NOTE]
   >
   >Quando configuri la destinazione di rapporto, tieni presente quanto segue:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Tutti gli account cloud configurati in precedenza sono disponibili per l’utilizzo con i feed di dati. Puoi configurare gli account cloud da Gestione posizioni in [Componenti > Esportazioni > Account posizione](/help/components/exports/cloud-export-accounts.md).
   >
   >* Gli account cloud sono associati al tuo account utente Customer Journey Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud configurati, a meno che non vengano resi disponibili a tutti gli utenti dell’organizzazione.
   >
   >* È possibile modificare qualsiasi percorso creato dal gestore Percorsi in [Componenti > Esportazioni > Percorsi](/help/components/exports/cloud-export-locations.md).

   Completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Visualizza destinazioni per tutti gli utenti**] | Se sei un amministratore di sistema, puoi abilitare questa opzione per visualizzare le destinazioni create da tutti gli utenti dell’organizzazione. Se questa opzione è disabilitata, vengono visualizzate solo le destinazioni create dall’utente. |
   | [!UICONTROL **Account**] | Esegui una delle operazioni seguenti:<ul><li>**Utilizza un account esistente:** Seleziona il menu a discesa accanto al campo **[!UICONTROL Account]**. In alternativa, inizia a digitare il nome dell’account, quindi selezionalo dal menu a discesa. <p>Gli account sono disponibili solo se sono stati configurati o se sono condivisi con un&#39;organizzazione di cui fai parte.</p></li><li>**Crea un nuovo account:** Seleziona **[!UICONTROL Aggiungi account]** nel menu a discesa **[!UICONTROL Account]**. Per informazioni su come configurare l&#39;account, vedere [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Posizione**] | Esegui una delle operazioni seguenti:<ul><li>**Usa una posizione esistente:** Seleziona il menu a discesa accanto al campo **[!UICONTROL Posizione]**. In alternativa, inizia a digitare il nome della posizione, quindi selezionalo dal menu a discesa.</li><li>**Crea un nuovo percorso:** Seleziona **[!UICONTROL Aggiungi percorso]** nel menu a discesa **[!UICONTROL Percorso]**. Per informazioni su come configurare il percorso, vedere [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Notifica via e-mail quando completato**] | Specifica uno o più indirizzi e-mail a cui inviare una notifica dopo che il feed di dati è stato inviato correttamente o non è stato inviato. È necessario separare più indirizzi e-mail con una virgola. |
   | [!UICONTROL **Abilita manifesto**] | Scegli se includere un file manifesto con ogni consegna di feed di dati. Il file manifesto contiene informazioni per ciascun file incluso nel feed di dati. |

1. Seleziona **[!UICONTROL Salva]**.

## Comprendere l’intervallo di date del lookback {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervallo di date di lookback"
>abstract="Controlla la distanza di Customer Journey Analytics nell’elaborazione di ogni consegna.<p>La finestra di frequenza (ora o giorno) determina quali eventi sono inclusi nel feed di dati, mentre l&#39;**intervallo di date di lookback** fornisce il contesto storico necessario per classificare correttamente tali eventi.</p><p>Qualificazione del segmento, persistenza delle dimensioni, calcolo della sessione e trasformazioni di campo derivate possono influenzare tutti gli eventi inclusi.</p><p>Un lookback più lungo migliora la precisione; un lookback più breve migliora le prestazioni.</p>"

<!-- markdownlint-enable MD034 -->

L’intervallo di date del lookback controlla l’aspetto indietro di Customer Journey Analytics durante l’elaborazione di ogni consegna di feed dati.

Per poter essere inclusi nella consegna, gli eventi devono ancora avere marche temporali che rientrano nell&#39;intervallo di frequenza (ora o giorno), ma i dati che rientrano nell&#39;**intervallo di date di lookback** forniscono il contesto storico necessario per classificare correttamente tali eventi.

Durante la configurazione di questa opzione, considera i seguenti concetti importanti:

* Un intervallo di date di lookback più lungo in genere consente di ottenere dati più precisi; un intervallo più breve determina prestazioni di consegna migliori.
* L’intervallo di date del lookback, insieme all’intervallo di frequenza, funziona in modo simile all’intervallo di date del reporting di Analysis Workspace. Tuttavia, sono presenti [differenze chiave](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). Tali differenze possono causare discrepanze di dati tra i rapporti di Workspace e le consegne di feed di dati.

La qualificazione dei segmenti, il calcolo della sessione, la persistenza delle dimensioni e le trasformazioni dei campi derivati vengono presi in considerazione durante l’elaborazione dei dati all’interno dell’intervallo di date del lookback:

### Qualificazione segmento

Quando un segmento viene applicato alla definizione del feed dati, i dati all’interno dell’intervallo di date del lookback determinano quali eventi, sessioni o persone sono idonee per il segmento. L’impostazione del contenitore del segmento determina l’ambito. (I contenitori possibili sono: Persona, Sessione o Evento. B2B include i seguenti contenitori aggiuntivi: account globale, account, opportunità, gruppo di acquisto.)

>[!BEGINSHADEBOX]

**Esempio:**

Supponiamo di voler creare un feed di dati per comprendere il comportamento degli utenti che fanno parte di una specifica campagna di marketing, la Campagna B.

A questo scopo, applichi un segmento al feed di dati denominato _Utenti nella campagna B_, indicando che solo gli eventi associati agli utenti in questo segmento devono essere inclusi nel feed di dati.

In questo caso, gli utenti vengono inclusi nel feed di dati solo se soddisfano **entrambe** le seguenti condizioni:

* L’utente aveva un evento con una marca temporale all’interno della finestra della frequenza del feed dati (l’ora o il giorno specificato del feed dati).
* L&#39;utente si è qualificato per il segmento **Campaign B _entro l&#39;intervallo di date del lookback**._

  Per un evento idoneo che si è verificato 9 giorni fa, ciò significa che l&#39;utente **verrebbe incluso** nel feed di dati se l&#39;intervallo di date del lookback fosse impostato su 30 giorni, ma l&#39;utente **non verrebbe incluso** nel feed di dati se l&#39;intervallo di date del lookback fosse impostato su 7 giorni.

>[!ENDSHADEBOX]

### Calcolo della sessione

I limiti di sessione vengono calcolati utilizzando i dati all’interno dell’intervallo di date del lookback. <!--Maybe this matters more regarding what the session ID is? Could it impact the Session ID? This could impact several factors, such as session-based persistence.-->

### Persistenza Dimension

Quando imposti la persistenza su una singola dimensione, imposti anche una scadenza per determinare per quanto tempo l’elemento dimensione persiste oltre l’evento su cui è impostato.

L’intervallo di date di lookback influisce sulla persistenza delle dimensioni quando la scadenza viene impostata su una delle seguenti opzioni nella visualizzazione dati:

* [!UICONTROL **Finestra di reporting per persona**]: l&#39;intervallo di date del lookback diventa il nuovo intervallo di reporting per ogni dimensione nella definizione del feed di dati che utilizza [!UICONTROL **Finestra di reporting per persona**] come scadenza.
* [!UICONTROL **Ora personalizzata**]: se l&#39;ora personalizzata selezionata si estende oltre l&#39;intervallo di date del lookback, l&#39;ora personalizzata viene ignorata e l&#39;intervallo di date del lookback viene utilizzato per la scadenza della dimensione per ogni dimensione nella definizione del feed di dati che utilizza [!UICONTROL **Ora personalizzata**] come scadenza. I valori che si sono verificati prima dell’intervallo di date del lookback non vengono considerati.

  Per ulteriori informazioni sull&#39;impostazione della persistenza sulle dimensioni all&#39;interno della visualizzazione dati, vedere [Impostazioni dei componenti di persistenza](/help/data-views/component-settings/persistence.md).

Per ottenere dati più precisi, puoi impostare l’intervallo di date del lookback su un valore uguale o superiore al set di persistenza impostato sulle dimensioni nei dati. Tuttavia, ricorda che un intervallo di date di lookback più breve determina prestazioni migliori per le consegne di feed di dati.

>[!BEGINSHADEBOX]

**Esempio:**

Supponiamo che nel tuo feed di dati desideri sapere quali utenti della campagna di marketing hanno visto originariamente prima di visitare il tuo sito.

A questo scopo, imposta la persistenza sulla dimensione Campagne con Originale come modello di allocazione.

In questo caso, la campagna originale viene visualizzata nell&#39;output del feed dati solo se gli utenti soddisfano **entrambi** delle seguenti condizioni:

* L’utente aveva un evento con una marca temporale all’interno della finestra della frequenza del feed dati (l’ora o il giorno specificato del feed dati).

* L&#39;utente si è qualificato per la campagna originale **entro l&#39;intervallo di date del lookback**.

  Se l&#39;utente è qualificato per la campagna originale 9 giorni fa, la campagna originale **è inclusa** nel feed di dati se l&#39;intervallo di date del lookback è impostato su 30 giorni, ma la campagna originale **non è inclusa** nel feed di dati se l&#39;intervallo di date del lookback è impostato su 7 giorni.

>[!ENDSHADEBOX]

### Trasformazioni di campo derivate

Qualsiasi funzione di campo derivata che fa riferimento a contenitori utilizza l’intervallo di date di lookback nelle esportazioni di feed di dati. Quali funzionalità di data sono disponibili nei campi derivati? <!--Not sure how this applies.-->



