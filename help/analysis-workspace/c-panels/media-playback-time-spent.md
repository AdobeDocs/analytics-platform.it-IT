---
title: Pannello Tempo trascorso su contenuti multimediali
description: Scopri come utilizzare e interpretare il pannello Tempo di riproduzione multimediale trascorso in Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 96%

---

# Pannello Tempo trascorso per la riproduzione di file multimediali {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="Tempo trascorso su contenuti multimediali"
>abstract="Crea un pannello per analizzare il consumo video nel tempo, con vari livelli di granularità e con la possibilità di suddividerli e confrontarli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="Tempo trascorso su contenuti multimediali"
>abstract="Analizza il consumo video nel tempo, seleziona varie granularità e, facoltativamente, suddividi e confronta utilizzando segmenti, dimensioni, elementi dimensionali o intervalli di date."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello Tempo trascorso su contenuti multimediali in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulta [Pannello Tempo trascorso su contenuti multimediali](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Il pannello Pubblico medio per minuto è disponibile solo per i clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection per Customer Journey Analytics.
>&#x200B;>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

Il pannello **[!UICONTROL Media playback time spent]** consente di analizzare le riproduzioni nel tempo, con dettagli sul picco di concorrenza e la possibilità di suddividere e confrontare i dati.

In Analysis Workspace il Tempo di riproduzione trascorso corrisponde alla quantità di tempo utilizzato per visualizzare i flussi multimediali in un determinato momento. Include pausa, buffer e tempo di avvio.

I clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection possono analizzare il tempo di riproduzione trascorso per ottenere informazioni approfondite sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori. E per contribuire a risolvere problemi o pianificare volumi o scala.

Il Tempo di riproduzione trascorso può aiutarti a comprendere:

* Dove si è verificato il picco di concorrenza.

* Dove si sono verificati cali.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tempo di riproduzione trascorso](https://video.tv.adobe.com/v/338699){target="_blank"} per un video demo.

{{videoaa}}

>[!ENDSHADEBOX]


## Utilizzo

Per usare un pannello **[!UICONTROL Media playback time spent]**:

1. Crea un pannello **[!UICONTROL Media playback time spent]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello i cui componenti sono configurati da Streaming Media Collection.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.


### Input del pannello

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date. |
| Granularità | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| Raggruppamento per serie | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.</p><p>- Quando viene trascinata una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel segmento di raggruppamento di serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione trascorso in `Hours:Minutes:Seconds` (impostazione predefinita) o in `Minutes` (visualizzati in numeri interi, arrotondati a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due segmenti di intervallo di date come raggruppamenti di serie, visualizzerai l’opzione per selezionare tra sovrapposizione, (predefinita) o sequenziale. La sovrapposizione mostra le linee con un inizio comune dell’asse X, in modo che siano parallele, mentre la sequenziale mostra le linee con il proprio inizio specifico dell’asse X. Se i dati sono allineati (ad esempio, il segmento 1 termina alle 20:44 e il segmento 2 inizia alle 20:45), le righe vengono visualizzate in sequenza. |


![Visualizzazione predefinita del tempo trascorso sul playbook dei contenuti multimediali.](assets/mpts_default_view.png)

### Output del pannello

Il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, seleziona ![Modifica pannello Tempo di riproduzione trascorso sui contenuti multimediali](/help/assets/icons/Edit.svg) per modificare e ricreare il pannello.

Se hai selezionato il raggruppamento per serie, per ciascun raggruppamento viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output del Tempo di riproduzione trascorso sui contenuti multimediali che mostra un grafico a linee e un riepilogo.](assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale `hours:minutes:seconds` (o `minutes`) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | <p></p><p>La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, dal menu di scelta rapida nel grafico a linee seleziona l’opzione per scaricare il file CSV.</p> |
| <p>Perché la granularità è cambiata?</p> | <p>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date.</p><p></p><p>Quando modifchi un intervallo di date più ampio in uno più ridotto, la granularità viene aggiornata al dettaglio minimo consentito una volta che l’intervallo di date è stato modificato. Per visualizzare una granularità maggiore, modifica il pannello e crealo nuovamente.</p> |
| <p></p><p>Come posso confrontare nomi video, segmenti, tipi di contenuto, ecc.?</p> | <p>Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel segmento di raggruppamento di serie.</p><p></p><p>La visualizzazione è limitata a 10 raggruppamenti. Per visualizzarne più di 10, è necessario utilizzare più pannelli.</p> |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date. Questi intervalli di date sovrascrivono l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | <p></p><p>Questo pannello consente solo la visualizzazione a linee per le serie temporali.</p> |
| Posso eseguire il rilevamento delle anomalie? | <p></p><p>No. Il rilevamento delle anomalie non è disponibile per questo pannello.</p> |


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Pannello Pubblico medio per minuto di contenuti multimediale](average-minute-audience-panel.md)
>&#x200B;>[Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md)
>
