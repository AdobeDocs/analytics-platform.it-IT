---
title: Pannello Tempo trascorso su contenuti multimediali
description: Come utilizzare e interpretare il pannello Media Playback time speso (Tempo di riproduzione dei contenuti multimediali) in Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 54%

---

# Pannello Tempo di riproduzione dei contenuti multimediali {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_button"
>title="Tempo trascorso per la riproduzione di file multimediali"
>abstract="Crea un pannello per analizzare il consumo video nel tempo, con vari livelli di granularità e con la possibilità di suddividerli e confrontarli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_panel"
>title="Tempo trascorso per la riproduzione di file multimediali"
>abstract="Analizza il consumo video nel tempo, seleziona varie granularità, suddividi e confronta.<br/><br/>**Granularità**: seleziona il periodo di tempo in base al quale osservare i visualizzatori simultanei.<br/>**Numeri di riepilogo pannello (facoltativo)**: opzione per visualizzare i numeri di riepilogo con dettagli di data o ora per ogni riga. Il valore massimo mostra i dettagli del picco del tempo di riproduzione trascorso. Il valore minimo mostra i dettagli del punto inferiore. Somma mostra i dettagli della somma totale del tempo di riproduzione trascorso.<br/>**Suddivisione serie (facoltativo)**: puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date. Visualizza fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.<br/>**Formato ora**: opzione per la visualizzazione del formato ora, in ore o minuti."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Il pannello Pubblico medio per minuto è disponibile solo per i clienti che hanno acquistato per il Customer Journey Analytics il componente aggiuntivo Streaming Media Collection.
>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

Il pannello **[!UICONTROL Media playback time spent]** consente di analizzare le riproduzioni nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli.

In Analysis Workspace, il tempo di riproduzione trascorso è la quantità di tempo impiegata per visualizzare i flussi multimediali in un determinato momento. Include pausa, buffer e tempo di avvio.

I clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection possono analizzare il tempo di riproduzione trascorso per ottenere informazioni approfondite sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori. e per risolvere problemi o pianificare volumi o scala.

Il tempo di riproduzione trascorso può aiutarti a comprendere:

* Dove si è verificato il picco di concorrenza.

* Dove si è verificato il calo.

+++ Guarda una dimostrazione video di questa funzionalità.

>[!VIDEO](https://video.tv.adobe.com/v/338699)

+++

## Seleziona

Per utilizzare un pannello **[!UICONTROL Media playback time spent]**:

1. Crea un pannello **[!UICONTROL Media playback time spent]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello con componenti configurati dal componente aggiuntivo Streaming Media Collection.

1. Specifica [input](#panel-input) per il pannello.

1. Osserva [output](#panel-output) per il pannello.


### Input del pannello

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| Raggruppamento per serie | Facoltativamente, puoi suddividere la visualizzazione per filtri, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di raggruppamento per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione trascorso in `Hours:Minutes:Seconds` (impostazione predefinita) o in `Minutes` (visualizzato in numeri interi, arrotondato a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due filtri di intervallo di date come raggruppamenti di serie, puoi selezionare l’opzione per sovrapporre (impostazione predefinita) o sequenziale. Sovrapponi visualizza le linee con un inizio comune dell&#39;asse X in modo che vengano eseguite in parallelo, mentre sequenziale visualizza le linee con il loro inizio specifico dell&#39;asse X. Se i dati sono allineati (ad esempio, il filtro 1 termina alle 20:44 e il filtro 2 inizia alle 20:45), le linee vengono visualizzate in sequenza. |


![Tempo predefinito trascorso dal playbook multimediale.](assets/mpts_default_view.png)

### Output del pannello

Il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, seleziona ![Modifica pannello Tempo di riproduzione dei contenuti multimediali](/help/assets/icons/Edit.svg) per modificare e ricreare il pannello.

Se selezioni la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![L&#39;output del tempo di riproduzione dei contenuti multimediali mostra un grafico a linee e un riepilogo.](assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale `hours:minutes:seconds` (o `minutes`) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | <p></p><p>La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, dal menu di scelta rapida nel grafico a linee seleziona l’opzione per scaricare il file CSV.</p> |
| <p>Perché la granularità è cambiata?</p> | <p>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.</p><p></p><p>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila.</p> |
| <p></p><p>Come si confrontano nomi video, filtri, tipi di contenuto e altro ancora?</p> | <p>Per confrontare questi elementi in una singola visualizzazione, trascina filtri, dimensioni o elementi dimensionali specifici nel filtro di raggruppamento per serie.</p><p></p><p>La visualizzazione è limitata a 10 raggruppamenti. Per visualizzarne più di 10, è necessario utilizzare più pannelli.</p> |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date. Questi intervalli di date hanno la precedenza sull’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | <p></p><p>Questo pannello consente solo la visualizzazione a linee per le serie temporali.</p> |
| Posso eseguire il rilevamento delle anomalie? | <p></p><p>No. Il rilevamento delle anomalie non è disponibile per questo pannello.</p> |


>[!MORELIKETHIS]
>
>[Crea un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Pannello del pubblico medio per minuto del file multimediale](average-minute-audience-panel.md)
>[Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md)
>