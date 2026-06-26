---
title: Creare un feed dati
description: Scopri come creare un feed di dati e le informazioni sui file da fornire ad Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b31ae6194d30115f4d653addaf5efff5790e987c
workflow-type: tm+mt
source-wordcount: 2675
ht-degree: 24%

---

# Creare un feed di dati

Durante la creazione di un feed di dati, fornisci ad Adobe:

* Informazioni sulla destinazione in cui si desidera inviare i file di dati non elaborati

* Dati da includere in ciascun file

* Frequenza con cui vengono inviati i dati (incluso il ritardo di elaborazione per acquisire gli hit in arrivo)

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
>title="Notifica completamento"
>abstract="Specifica uno o più indirizzi e-mail a cui inviare una notifica dopo l’invio del feed di dati. È necessario separare più indirizzi e-mail con una virgola."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervallo di date di lookback"
>abstract="Controlla quanto Customer Journey Analytics deve risalire indietro nel tempo durante l’elaborazione della consegna del feed dati.<br/>Questa impostazione non modifica l’intervallo frequenza (ora o giorno). Tuttavia, l’intervallo di date di lookback può influire sui dati consegnati. La qualificazione segmento, il calcolo delle sessioni, alcune trasformazioni dei campi derivati e la persistenza delle dimensioni sono tutti influenzati dall’intervallo di date di lookback."

<!-- markdownlint-enable MD034 -->

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.

1. Seleziona [!UICONTROL **Customer Journey Analytics**] dal selettore di app ![App](/help/assets/icons/Apps.svg) in alto a destra nell’interfaccia.

1. Nella barra di navigazione superiore, vai a [!UICONTROL **Componenti**] > [!UICONTROL **Feed dati**].

1. Seleziona [!UICONTROL **Crea**] nell&#39;angolo superiore destro dello schermo.

   In alternativa, se in precedenza non è stato creato alcun feed di dati, selezionare [!UICONTROL **Crea feed di dati**] all&#39;interno della tabella vuota.

   Viene visualizzata una pagina con le seguenti schede: [!UICONTROL **Dettagli**], [!UICONTROL **Struttura dati**] e [!UICONTROL **Consegna**].

   ![Nuova pagina feed dati](assets/data-feed-new.png)

1. Nella scheda [!UICONTROL **Dettagli**], completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome**] | Nome del feed dati. I nomi devono essere univoci all’interno della visualizzazione dati selezionata e possono contenere fino a 255 caratteri. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tag**] | Applica eventuali tag al feed dati per facilitarne la classificazione. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descrizione**] | Specifica una descrizione per il feed dati. La descrizione aggiunta è visibile quando si modifica il feed dati. |
   | [!UICONTROL **Visualizzazione dati**] | Selezionare la visualizzazione dati contenente i dati che si desidera esportare.<p>Quando selezioni una visualizzazione dati, tieni presente quanto segue:</p> <ul><li>Se vengono creati più feed di dati per la stessa visualizzazione dati, ogni feed di dati deve avere definizioni di colonne diverse.</li><li>L’elenco delle colonne disponibili dipende dalla società di accesso a cui appartiene la visualizzazione dati selezionata. Se modifichi la visualizzazione dati, l’elenco delle colonne disponibili può cambiare. </li></ul> |

1. Seleziona [!UICONTROL **Avanti**].

1. Nella scheda [!UICONTROL **Data structure**], assicurati che nel campo **[!UICONTROL Data view]** sia selezionata la visualizzazione dati corretta.

1. Nel menu a discesa [!UICONTROL **Segmenti**], cerca e seleziona eventuali segmenti per filtrare i dati inclusi nel feed.

   Quando applichi più segmenti, questi vengono uniti insieme a un operatore AND. Per unire i segmenti con un operatore OR, devi prima creare un nuovo segmento nel generatore di segmenti, quindi applicare il nuovo segmento al feed di dati.

1. Aggiungi componenti alla configurazione del feed dati. Nella barra a sinistra, individua i componenti da includere, quindi trascinali nell’area di lavoro per creare la struttura dati. Per selezionare più componenti, tieni premuto **[!UICONTROL Maiusc]** oppure tieni premuto **[!UICONTROL Comando]** (su macOS) o **[!UICONTROL Ctrl]** (su Windows).

   Utilizza le seguenti informazioni per comprendere le dimensioni sempre incluse, le dimensioni che non possono essere incluse e le metriche che devono essere sostituite:

   +++ Dimensioni sempre incluse nei feed di dati

   Le seguenti dimensioni sono incluse per impostazione predefinita in ogni feed di dati e non possono essere rimosse:

   | Nome dimensione | Note | Feed di dati | Altre attività di reporting |
   |---|---|---|---|
   | Marca temporale | Timestamp del periodo dell’evento. Granularità al microsecondo. Rappresentata in UTC. | Obbligatorio | Non disponibile |
   | ID riga | Identificatore di riga univoco | Obbligatorio | Non disponibile |
   | ID sessione | Identificatore univoco per ogni sessione | Obbligatorio | Non disponibile |
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


1. Nella scheda [!UICONTROL **Consegna**], specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Tipo di feed**] | Seleziona il tipo di feed da creare:<ul><li>[!UICONTROL **Feed live**]: esporta dati correnti e futuri.</li><li>[!UICONTROL **Feed di backfill**]: esporta dati storici tra due date precedenti.</li></ul> |
   | [!UICONTROL **Data di inizio**] | Specifica la data di inizio del feed di dati. Per iniziare immediatamente a elaborare i feed di dati per i dati storici, assicurati che sia selezionato [!UICONTROL **Feed di backfill**], quindi imposta questa data su una data nel passato in cui vengono raccolti i dati. La data di inizio è basata sul fuso orario della visualizzazione dati. |
   | [!UICONTROL **Data di fine**] | Specifica la data in cui desideri che termini il feed dati. La data di fine si basa sul fuso orario della visualizzazione dati. |
   | [!UICONTROL **Frequenza**] | Seleziona la frequenza con cui inviare il feed di dati. Gli eventi con marche temporali che rientrano nella finestra di frequenza sono inclusi nella consegna del feed di dati. I campi [!UICONTROL **Intervallo date di lookback**] e [!UICONTROL **Ritardo elaborazione**] possono anche influenzare gli eventi inclusi nei dati per la frequenza di consegna scelta.<p>Per i feed live, seleziona questa opzione per includere dati relativi a un’ora o a un giorno. I feed di backfill devono essere giornalieri.</p><ul><li>**Giornaliero**: i feed contengono dati relativi a un intero giorno, dalla mezzanotte alla mezzanotte nel fuso orario della visualizzazione dati. Utilizza questa opzione per i feed di backfill o per i feed live.</li><li>**Oraria**: i feed contengono dati relativi a una sola ora. Utilizza questa opzione per i feed live.</li></ul> |
   | [!UICONTROL **Intervallo date lookback**] | Controlla quanto Customer Journey Analytics deve risalire indietro nel tempo durante l’elaborazione della consegna del feed dati. <p>Questa impostazione non altera la finestra di frequenza (ora o giorno), che definisce l’intervallo di tempo degli eventi da includere nell’output del feed di dati. Tuttavia, l’intervallo di date di lookback può influenzare i dati consegnati nei seguenti modi: </p><ul><li>**Qualificazione del segmento**: quando un segmento viene applicato alla definizione del feed dati, tutti gli eventi all&#39;interno dell&#39;intervallo di date di lookback determinano se una persona è idonea. L’impostazione del contenitore del segmento determina l’ambito. (I contenitori possibili sono: Persona, Sessione o Evento. Il B2B ha i seguenti contenitori aggiuntivi: account globale, account, opportunità, gruppo di acquisto.)  <p>Ad esempio, se viene utilizzato un contenitore Persona e la persona risulta idonea durante l’intervallo di date del lookback, vengono qualificati anche tutti gli eventi di quella persona durante l’intervallo di frequenza.</p></li><li>**Calcolo sessione**: i limiti della sessione vengono calcolati utilizzando i dati all&#39;interno dell&#39;intervallo di date del lookback.</li><li>**Trasformazioni campo derivato**: tutte le funzioni campo derivato che fanno riferimento a contenitori utilizzano l&#39;intervallo di date del lookback nelle esportazioni di feed di dati.</li><li>**Persistenza Dimension**: se scegli di impostare la persistenza su una singola dimensione, scegli anche una scadenza per determinare per quanto tempo un elemento dimensione persiste oltre l&#39;evento su cui è impostato. <p>L’intervallo di date di lookback influisce sulla persistenza delle dimensioni quando la scadenza viene impostata su una delle seguenti opzioni nella visualizzazione dati:</p><ul><li>Per ogni dimensione nella definizione del feed dati che utilizza [!UICONTROL **Finestra di reporting**] come scadenza, l&#39;intervallo di date del lookback diventa il nuovo intervallo di reporting.</li><li>Per ogni dimensione nella definizione del feed dati che utilizza [!UICONTROL **Ora personalizzata**] come scadenza e se l&#39;ora personalizzata selezionata si estende oltre l&#39;intervallo di date del lookback, l&#39;ora personalizzata viene ignorata e l&#39;intervallo di date del lookback viene utilizzato per la scadenza della dimensione.<p>Per ulteriori informazioni sull&#39;impostazione della persistenza sulle dimensioni all&#39;interno della visualizzazione dati, vedere [Impostazioni dei componenti di persistenza](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Ritardo elaborazione**] | Scegli la quantità di tempo di attesa prima di elaborare un file di feed dati. Eventuali hit in ritardo che arrivano durante il ritardo di elaborazione sono inclusi nel feed di dati. <p>I ritardi di elaborazione sono utili per vari motivi, ad esempio per dare alle implementazioni mobili l’opportunità di connettere e inviare dati ai dispositivi offline o per adattarsi ai processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. </p><p>È possibile ritardare un feed di 2, 3, 4 o 8 ore.<p>Per poter essere incluse, le sessioni devono iniziare dopo il cut-off del ritardo di elaborazione; le sessioni che iniziano prima del cut-off e terminano entro il ritardo di elaborazione non sono incluse.</p> |
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
   | [!UICONTROL **Notifica quando completato**] | Specifica uno o più indirizzi e-mail a cui inviare una notifica dopo che il feed di dati è stato inviato correttamente o non è stato inviato. È necessario separare più indirizzi e-mail con una virgola. |
   | [!UICONTROL **Abilita manifesto**] | Scegli se includere un file manifesto con ogni consegna di feed di dati. Il file manifesto contiene informazioni per ciascun file incluso nel feed di dati. |

1. Seleziona **[!UICONTROL Salva]**.

