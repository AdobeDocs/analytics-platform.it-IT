---
title: Pannello Visualizzatori simultanei di contenuti multimediali
description: Scopri come utilizzare e interpretare il pannello Visualizzatori simultanei di contenuti multimediali in Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 98%

---

# Pannello Visualizzatori simultanei di file multimediali {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visualizzatori simultanei di file multimediali"
>abstract="Crea un pannello per analizzare i visualizzatori simultanei in un determinato periodo di tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visualizzatori simultanei di file multimediali"
>abstract="Analizza i visualizzatori simultanei nel tempo, visualizza il picco di concorrenza e, facoltativamente, suddividi e confronta utilizzando segmenti, dimensioni, elementi dimensionali o intervalli di date."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello Visualizzatori simultanei di file multimediali in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulta [Pannello Visualizzatori simultanei di file multimediali](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Il pannello Pubblico medio per minuto è disponibile solo per i clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection per Customer Journey Analytics.
>
>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

Il pannello **[!UICONTROL Media concurrent viewers]** consente di analizzare i visualizzatori simultanei nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli. 

Puoi analizzare i visualizzatori simultanei per capire dove si è verificato il picco di concorrenza o dove si sono verificati abbandoni, così da fornire informazioni utili sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori. Questo aiuta anche nella risoluzione dei problemi o nella pianificazione per volumi o scala.

In Analysis Workspace, la metrica Visualizzatori simultanei rappresenta il numero di persone singole che visualizzano i flussi multimediali in un determinato momento, indipendentemente dal numero di sessioni.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pannello Visualizzatori simultanei di file multimediali](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]

## Utilizzo

Per usare un pannello **[!UICONTROL Media concurrent viewers]**:

1. Crea un pannello **[!UICONTROL Media concurrent viewers]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello i cui componenti sono configurati da Streaming Media Collection.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello Visualizzatori simultanei di file multimediali utilizzando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Panel date range]** | L’intervallo di date predefinito del pannello è Today (Oggi).  È possibile modificarlo per visualizzare uno o più mesi alla volta. <br> <br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date. |
| **[!UICONTROL Granularity]** | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date. |
| **[!UICONTROL Panel summary numbers]** | Per visualizzare i dettagli di data o ora per i visualizzatori simultanei, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il **[!UICONTROL Minimum]** mostra i dettagli del valore più basso.  Per impostazione predefinita il pannello mostra solo il valore massimo, ma puoi impostarlo sul valore minimo o su entrambi.<br><br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| **[!UICONTROL Series breakdown]** | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<br>È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.<br>Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.<br>Per confrontare intervalli di date, trascina 2 o più intervalli di date nel segmento di raggruppamento di serie. |

Ecco un esempio del pannello configurato per la granularità di **[!UICONTROL Minute]**, con **[!UICONTROL Maximum only]** numeri di riepilogo. Suddiviso inoltre per **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![La vista di raggruppamento per serie Visualizzatori simultanei di contenuti multimediali mostra 7 di 10 dimensioni, segmenti o intervalli di date.](assets/concurrent-viewers-series-breakdown.png)

### Output del pannello

Il pannello Visualizzatori simultanei di contenuti multimediali restituisce un grafico a linee e numeri di riepilogo che includono i dettagli del numero massimo e/o minimo di visualizzatori simultanei.  Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, seleziona ![Modifica pannello Visualizzatori simultanei di contenuti multimediali](/help/assets/icons/Edit.svg) per modificare e ricreare il pannello.

Se hai selezionato il raggruppamento per serie, per ciascun raggruppamento viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output Visualizzatori simultanei di contenuti multimediali.](assets/concurrent-viewers-output.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è **[!UICONTROL Concurrent viewers]**:

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Concurrent viewers]** | Numero di persone univoche che visualizzano i flussi di elementi multimediali in un determinato momento, indipendentemente dal numero di sessioni. |

In questa visualizzazione non è disponibile una tabella a forma libera.  Per visualizzare l’origine dati, scaricarla dal menu di scelta rapida della visualizzazione del grafico a linee e seleziona **[!UICONTROL Download data as CSV]**.  Sono inclusi i raggruppamenti per serie.

![Le opzioni di output Visualizzatori simultanei con &quot;Scarica dati come CSV&quot; evidenziato.](assets/concurrent-viewers-download-csv.png)

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | La tabella a forma libera non è disponibile in questa vista. È possibile scaricare l’origine dati dal menu di scelta rapida del grafico a linee e seleziona **[!UICONTROL Download data as CSV]**. |
| Perché la granularità è cambiata? | Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente per adattarsi all’intero intervallo di date.<br><br>Quando modifchi un intervallo di date più ampio in uno più ridotto, la granularità viene aggiornata al dettaglio minimo consentito una volta che l’intervallo di date è stato modificato. Per visualizzare una granularità maggiore, modifica il pannello e crealo nuovamente. |
| Come posso confrontare nomi video, segmenti, tipi di contenuto e altro? | Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel segmento di raggruppamento di serie.<br><br>La visualizzazione è limitata a 10 raggruppamenti. Per visualizzarne più di 10, è necessario utilizzare più pannelli. |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date. Gli intervalli di date sovrascriveranno l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | Questo pannello consente solo la visualizzazione a linee per le serie temporali. |
| Posso eseguire il rilevamento delle anomalie? | No.  Il rilevamento delle anomalie non è disponibile per questo pannello. |
| Perché utilizzare le persone univoche invece di sessioni attive? | L’utilizzo di persone univoche consente di rimuovere i picchi indesiderati in corrispondenza dei confini di visualizzazione (dove le sessioni terminano e iniziano allo stesso momento). |
| Cosa significa avere visualizzatori simultanei con granularità maggiore del minuto? | Con una granularità maggiore di un minuto, i visualizzatori simultanei sono la somma dei visualizzatori simultanei univoci per tutti i minuti entro l’intervallo di tempo in questione. Ad esempio, i visualizzatori simultanei con granularità a livello di ora corrispondono alla somma dei visualizzatori simultanei univoci per tutti i minuti all’interno di quell’ora. |
| Il pannello Workspace mostra le stesse informazioni del rapporto Visualizzatori simultanei? | No.  In Analysis Workspace, la metrica dei visualizzatori simultanei si riferisce al numero di visitatori univoci che visualizzano il flusso multimediale in un momento specifico. Indipendentemente dal numero di sessioni.<br><br>Questa metrica è diversa dal reporting sui visualizzatori simultanei nella sezione Rapporti, che utilizza le sessioni attive simultanee. L’utilizzo di account di persona univoci consente di rimuovere i picchi indesiderati in corrispondenza dei confini di visualizzazione (dove le sessioni terminano e iniziano allo stesso momento). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Pannello Tempo trascorso per la riproduzione di file multimediali](media-playback-time-spent.md)
>&#x200B;>[Pannello Pubblico medio per minuto del file multimediale](average-minute-audience-panel.md)
>