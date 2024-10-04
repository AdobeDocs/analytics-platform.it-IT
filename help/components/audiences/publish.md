---
title: Creare e pubblicare tipi di pubblico su Real-Time Customer Profile
description: Scopri come pubblicare tipi di pubblico da Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: e131fd78ceee67a05a1ea7256e58b4b34ce44ae5
workflow-type: tm+mt
source-wordcount: '1865'
ht-degree: 14%

---

# Creare e pubblicare tipi di pubblico {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_refreshfrequency"
>title="Refresh frequency (Frequenza di aggiornamento)"
>abstract="Scopri con quale frequenza viene rivalutata l’iscrizione di un pubblico.<br/>I tipi di pubblico occasionali vengono valutati una sola volta."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_audiencelimit"
>title="Limite di pubblico"
>abstract="I tipi di pubblico di aggiornamento sono limitati in base alla frequenza con cui vengono aggiornati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_refreshlookbackwindow"
>title="Finestra di lookback di aggiornamento"
>abstract="Definisci il numero di giorni di lookback a partire da oggi da cui viene valutato un pubblico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_audiencesizelimit"
>title="Limite dimensione pubblico"
>abstract="Il pubblico non può superare i 20 milioni di membri."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_namespacesincluded"
>title="Namespace inclusi"
>abstract="Le identità in questo pubblico sono composte dagli spazi dei nomi seguenti."

<!-- markdownlint-enable MD034 -->




Questo argomento illustra come creare e pubblicare i tipi di pubblico identificati nel Customer Journey Analytics in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) in Adobe Experience Platform per la personalizzazione e il targeting dei clienti.

Leggi questa [panoramica](/help/components/audiences/audiences-overview.md) per acquisire familiarità con il concetto di pubblico di Customer Journey Analytics.

## Creare e pubblicare un pubblico {#create}

1. Per creare e pubblicare un pubblico, effettua una delle seguenti operazioni:

   | Metodo di creazione | Dettagli |
   | --- | --- |
   | Dall&#39;interfaccia **[!UICONTROL Audiences]**. | Selezionare **[!UICONTROL Components]** > **[!UICONTROL Audiences]** dal menu principale del Customer Journey Analytics. Viene visualizzata l’interfaccia Tipi di pubblico. Selezionare **[!UICONTROL Create audience]** creazione e verrà aperto [!UICONTROL Audience builder]. |
   | Da una visualizzazione in Analysis Workspace | Molte visualizzazioni in Analysis Workspace consentono di creare un pubblico utilizzando il menu di scelta rapida. È ad esempio possibile selezionare **[!UICONTROL Create audience]** dal menu di scelta rapida di un elemento in una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) o un nodo nell&#39;[area di lavoro Percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>L’utilizzo di questo metodo precompila il filtro nel generatore di tipi di pubblico con la dimensione o l’elemento dimensione selezionato.</p><p>Le seguenti visualizzazioni ti consentono di creare un pubblico utilizzando il menu di scelta rapida:</p><ul><li>[Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Nota:** i tipi di pubblico non possono includere metriche calcolate. Se tenti di creare un pubblico che contiene una metrica calcolata, questa non viene inclusa nella definizione del pubblico.</p> |
   | Dall’interfaccia utente di creazione/modifica del filtro | Seleziona la casella che riporta **[!UICONTROL Create an audience from this filter]**. L’utilizzo di questo metodo precompila il filtro. Per ulteriori informazioni, vedere [Creare filtri](/help/components/filters/create-filters.md). |

   {style="table-layout:auto"}

1. Crea il pubblico utilizzando [Generatore di pubblico](#audience-builder).

1. Interpreta i dati utilizzando il pannello [Anteprima data](#data-preview).

1. Seleziona **[!UICONTROL [!UICONTROL View sample IDs]]** per visualizzare un esempio di ID in questo pubblico. Nella finestra di dialogo **[!UICONTROL Sample IDs]** puoi utilizzare ![Cerca](/help/assets/icons/Search.svg) [!UICONTROL *Cerca ID di esempio*] per cercare ID di esempio.

1. Controlla nuovamente la configurazione del pubblico e seleziona **[!UICONTROL Publish]**.
Ricevi un messaggio di conferma della pubblicazione del pubblico. La pubblicazione richiede solo un minuto o due per la visualizzazione di questo pubblico in Experience Platform.

1. Seleziona **[!UICONTROL View audience in AEP]** all&#39;interno dello stesso messaggio e accedi all&#39;[interfaccia utente segmento](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview) in Adobe Experience Platform. Per ulteriori informazioni, vedi di seguito.

## Generatore di pubblico

Configura queste impostazioni per definire o aggiornare il pubblico.

![Schermata di creazione di un pubblico con le impostazioni di sottomissione descritta nella sezione successiva.](assets/create-audience.png)

| Impostazione | Descrizione |
| --- | --- |
| ![Dati](/help/assets/icons/Data.svg) | Seleziona una visualizzazione dati da utilizzare per la creazione del pubblico. |
| **[!UICONTROL Name]** | Il nome del pubblico. Ad esempio: `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Tags]** | Qualsiasi tag che desideri assegnare al pubblico per scopi organizzativi. Puoi selezionare uno o più tag preesistenti o immetterne uno nuovo. |
| **[!UICONTROL Description]** | Una descrizione del pubblico, per distinguerlo dagli altri. Ad esempio: `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Refresh frequency]** | La frequenza con cui desideri aggiornare il pubblico.<p/>Puoi scegliere tra <ul><li>Pubblico **[!UICONTROL One time]**: un pubblico (predefinito) che non deve essere aggiornato. Ad esempio, questa opzione potrebbe essere utile per campagne una tantum specifiche.<br/>È necessario specificare **[!UICONTROL One time date range]**. È possibile utilizzare ![Calendario](/help/assets/icons/Calendar.svg) per immettere un intervallo di date.</li><li>Un pubblico che si aggiorna. Puoi scegliere una delle opzioni seguenti:<ul><li>**[!UICONTROL Every 4 hour]**: un pubblico che si aggiorna ogni 4 ore.</li><li>**[!UICONTROL Daily]**: un pubblico che si aggiorna ogni giorno</li><li>**[!UICONTROL Weekly]**: un pubblico che si aggiorna settimanalmente.</li><li>**[!UICONTROL Monthly]**: un pubblico che si aggiorna mensilmente</li></ul></li><br/>Per aggiornare i tipi di pubblico, è necessario specificare:<ul><li>**[!UICONTROL Refresh lookback window]** (Autenticazione): Definisci il numero di giorni di lookback a partire da oggi in cui viene valutato un pubblico. Puoi selezionare tra le opzioni o definire un’ora personalizzata. Il massimo è 90 giorni.</li><li>**[!UICONTROL Expiration date]**: definisci quando il pubblico smette di aggiornare. È possibile utilizzare ![Calendario](/help/assets/icons/Calendar.svg) per selezionare una data. Il valore predefinito è un anno dalla data di creazione. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza. L’amministratore riceve un’e-mail un mese prima della scadenza del pubblico.</li></ul> Tieni presente che esiste un limite di 75-150 aggiornamenti del pubblico, a seconda della adesione al Customer Journey Analytics.</li></ul> |
| **[!UICONTROL Filter]** | I filtri sono l’input principale per il pubblico. Trascina e rilascia uno o più filtri dal pannello ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** di sinistra nell&#39;area Filtro. Puoi usare ![Cerca](/help/assets/icons/Search.svg) [!UICONTROL *Cerca filtri*] per cercare i filtri. Puoi aggiungere fino a 20 filtri. È possibile unire i filtri con **[!UICONTROL And]** o **[!UICONTROL Or]** operatori.<p>Durante la creazione di un pubblico da una visualizzazione in Analysis Workspace (ad esempio, una tabella a forma libera o un’area di lavoro del Percorso), tutti i filtri applicati al pannello o alla colonna vengono mantenuti. Puoi rimuovere tutti i filtri applicati automaticamente.</p> |
| **[!UICONTROL Data preview]** | Seleziona ![Info](/help/assets/icons/Info.svg) per mostrare o nascondere la [Anteprima dati](#data-preview) per l&#39;intervallo date selezionato. |

## Anteprima dati

Il pannello Anteprima dati fornisce le seguenti informazioni.

| Elemento | Descrizione |
| --- | --- |
| **[!UICONTROL Total people]** | Un numero di riepilogo del numero totale di persone presenti nel pubblico. La dimensione massima è di 20 milioni di persone. Se il pubblico supera i 20 milioni di persone, devi ridurne la dimensione prima di poter pubblicare. |
| **[!UICONTROL Audience size limit]** | Visualizzazione per mostrare quanto è lontano il pubblico dal limite di 20 milioni. |
| **[!UICONTROL Estimated audience return]** | Puoi utilizzare questo valore per eseguire il retargeting delle persone nel pubblico che tornano al tuo sito, all’app mobile o a un altro canale.<p>È possibile selezionare l&#39;intervallo di tempo (**[!UICONTROL Next 7 days]**, **[!UICONTROL Next 2 weeks]** o **[!UICONTROL Next month]**) per il numero stimato di clienti che potrebbero tornare. |
| **[!UICONTROL Estimated to return]** | Questo numero fornisce una stima dei clienti fidelizzati nell’intervallo di tempo selezionato. Questo numero viene previsto utilizzando il tasso di abbandono storico per questo pubblico. |
| **[!UICONTROL Preview metrics]** | Puoi selezionare una metrica specifica per vedere in che modo i dati per quella metrica si basano sul pubblico definito.  Ogni metrica di anteprima mostra un totale per la metrica in base al pubblico. E una percentuale della metrica basata sul pubblico dal totale complessivo della metrica, come definito dalla visualizzazione dati. Ad esempio, 381 persone (la metrica selezionata) sono il risultato della definizione del pubblico, che è il 5% del totale delle persone disponibili nella visualizzazione dati. Puoi selezionare qualsiasi metrica disponibile nella visualizzazione dati. |
| **[!UICONTROL Namespaces included]** | Gli spazi dei nomi specifici associati alle persone nel pubblico. Alcuni esempi includono ECID, ID CRM, indirizzi e-mail e così via. |
| **[!UICONTROL Sandbox]** | La [sandbox di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) in cui risiede il pubblico. Quando pubblichi questo pubblico in Platform, puoi utilizzarlo solo entro i confini di questa sandbox. |

{style="table-layout:auto"}

## Cosa succede dopo la creazione e la pubblicazione di un pubblico? {#after-audience-created}

Dopo aver creato e pubblicato un pubblico in Customer Journey Analytics, il pubblico è disponibile in Experience Platform. Un segmento di streaming di Adobe Experience Platform viene creato solo se l’organizzazione è configurata per la segmentazione in streaming.

* Il pubblico in Platform condivide lo stesso nome e la stessa descrizione del pubblico Customer Journey Analytics. Al nome viene aggiunto l&#39;ID pubblico Customer Journey Analytics per garantire che il pubblico sia univoco.
* Eventuali modifiche apportate al nome o alla descrizione del pubblico nel Customer Journey Analytics vengono riportate in Experience Platform.
* Se un pubblico viene eliminato nel Customer Journey Analytics, il pubblico continua a essere disponibile in Experience Platform.

## Considerazioni sulla latenza {#latency}

In diversi punti prima, durante e dopo la pubblicazione del pubblico, possono verificarsi latenze. Ecco una panoramica delle latenze che possono verificarsi.

![Latenze nella pubblicazione del pubblico come descritto in questa sezione.](assets/latency-diagram.svg)

|  | Punto di latenza | Durata della latenza |
| --- | --- | --- |
| Non visualizzato | Connettore di origine da Adobe Analytics ad Analytics (A4T) | Fino a 30 minuti |
| 1 | Acquisizione dei dati nel Data Lake (dal connettore di origine di Analytics o da altre origini) | Fino a 90 minuti |
| 2 | Acquisizione dei dati da Experience Platform Data Lake a Customer Journey Analytics | Fino a 90 minuti |
| 3 | Pubblicazione di tipi di pubblico su Real-Time Customer Profile, inclusa la creazione automatica del segmento di streaming e la possibilità per il segmento di essere pronto a ricevere i dati. | Qualche secondo |
| 4 | Frequenza di aggiornamento per tipi di pubblico | <ul><li>Aggiornamento singolo (latenza inferiore a 5 minuti)</li><li>Aggiornamento ogni 4 ore, ogni giorno, ogni settimana, ogni mese (la latenza va di pari passo con la frequenza di aggiornamento) |
| 5 | Creazione di una destinazione in Adobe Experience Platform: attivazione del nuovo segmento | 1-2 ore |

{style="table-layout:auto"}

## Utilizzare i tipi di pubblico di Customer Journey Analytics in Experience Platform {#audiences-aep}

Customer Journey Analytics prende tutte le combinazioni di spazio dei nomi e ID dal pubblico pubblicato e le trasmette a Real-time Customer Data Platform. Il Customer Journey Analytics invia il pubblico all&#39;Experience Platform con l&#39;identità primaria impostata, in base a quella selezionata come [!UICONTROL Person ID] al momento della configurazione della connessione.

Real-time Customer Data Platform esamina quindi ogni combinazione di spazio dei nomi/ID e cerca un profilo di cui potrebbe far parte. Un profilo è fondamentalmente un cluster di spazi dei nomi, ID e dispositivi collegati. Se trova un profilo, aggiunge lo spazio dei nomi e l’ID agli altri ID in questo profilo come attributo di appartenenza al segmento. Ad esempio, è possibile eseguire il targeting di <user@adobe.com> su tutti i relativi dispositivi e canali. Se non viene trovato un profilo, ne viene creato uno nuovo.

Per visualizzare i tipi di pubblico di Customer Journey Analytics in Platform:

1. Espandi **[!UICONTROL Customer]** nel pannello a sinistra, quindi seleziona **[!UICONTROL Audiences]**. <!-- is there a folder called "Customer Journey Analytics? -->

1. Seleziona la scheda **[!UICONTROL Browse]**.

1. Per individuare il pubblico pubblicato da Customer Journey Analytics, effettua una delle seguenti operazioni:

   Opzione ![Tipi di pubblico nel pannello a sinistra](assets/aep-audiences.png)

   * Ordina la tabella in base alla colonna **[!UICONTROL Origin]** per visualizzare i tipi di pubblico che mostrano [!UICONTROL **Customer Journey Analytics**] come origine.

   * Filtra ![Filtra](/help/assets/icons/Filter.svg) su **[!UICONTROL Origin]** e seleziona **[!UICONTROL Customer Journey Analytics]**.

   * Utilizza il campo di ricerca ![Ricerca](/help/assets/icons/Search.svg).

Per ulteriori informazioni sull&#39;utilizzo dei tipi di pubblico in Platform, consulta la sezione [Tipi di pubblico](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) nella [guida dell&#39;interfaccia utente del Generatore di segmenti](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) nella documentazione di Experience Platform.


## Domande frequenti {#faq}

Domande frequenti sulla pubblicazione dei tipi di pubblico.

+++**Cosa succede se un utente non è più membro di un pubblico nel Customer Journey Analytics?**

In questo caso, viene inviato un evento di uscita all’Experience Platform dal Customer Journey Analytics.

+++

+++**Cosa succede se elimini un pubblico nel Customer Journey Analytics?**

Quando un pubblico di Customer Journey Analytics viene eliminato, non viene più visualizzato nell’interfaccia utente di Experience Platform. Tuttavia, i profili associati a tale pubblico non vengono eliminati in Experience Platform.

+++

+++**Se un profilo corrispondente non esiste in Real-time Customer Data Platform, viene creato un nuovo profilo?**

Sì.

+++

+++**Il Customer Journey Analytics invia i dati del pubblico come eventi pipeline o come file flat che viene inviato anche al data lake?**

Il Customer Journey Analytics invia i dati in Real-time Customer Data Platform tramite pipeline e questi dati vengono raccolti anche in un set di dati di sistema nel data lake.

+++

+++**Quali identità vengono inviate dal Customer Journey Analytics?**

Qualsiasi coppia identità/spazio dei nomi specificata nella [Configurazione della connessione](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection). In particolare, il passaggio in cui un utente seleziona il campo da utilizzare come ID persona.

+++

+++**Quale ID è scelto come identità primaria?**

Vedi sopra. Viene inviata una sola identità per persona del Customer Journey Analytics.

+++

+++**Real-time Customer Data Platform elabora anche i messaggi di Customer Journey Analytics? Il Customer Journey Analytics può aggiungere identità a un grafico delle identità di profilo tramite la condivisione del pubblico?**

No. Viene inviata una sola identità per persona, quindi non ci sarebbero margini di grafico da utilizzare per Real-time Customer Data Platform.

+++

+++**A che ora del giorno vengono eseguiti aggiornamenti giornalieri, settimanali e mensili? Quale giorno della settimana si verificano aggiornamenti settimanali?**

La tempistica dell’aggiornamento si basa su quando è stato pubblicato il pubblico originale ed è ancorata a tale ora del giorno (e al giorno della settimana o del mese).

+++

+++**È possibile configurare l&#39;ora dell&#39;aggiornamento giornaliera, settimanale e mensile?**

No, gli utenti non possono configurare l&#39;ora di aggiornamento.

+++


## Passaggi successivi

* Per gestire questo pubblico, vai all’[interfaccia utente di gestione](/help/components/audiences/manage.md).
