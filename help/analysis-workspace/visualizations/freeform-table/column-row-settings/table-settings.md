---
description: Scopri come utilizzare le impostazioni di riga e come variano a seconda del componente trascinato in una tabella a forma libera in Analysis Workspace.
title: Impostazioni riga
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 13%

---

# Impostazioni riga


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Impostazioni riga e colonna in una tabella a forma libera](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella. Per accedere alle impostazioni delle righe della tabella, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Impostazioni]** accanto a una dimensione, a un segmento, a una metrica, a un periodo di tempo o a un raggruppamento all&#39;interno di ciascuno di questi oggetti.

![Tabella a forma libera che evidenzia l&#39;icona Impostazioni per le metriche](assets/row-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Raggruppamento per posizione]** | Per impostazione predefinita, questa impostazione è disabilitata e i raggruppamenti sono fissati su elementi di riga statici. Ad esempio, immagina di suddividere i primi 3 elementi dimensionali di pagina (Home page, Risultati ricerca, Pagamento) per canale di marketing. Poi abbandoni il progetto per due settimane. Quando lo riapri, le prime 3 pagine sono cambiate e ora Home page, Risultati ricerca e Pagamento sono le prime 4-6 pagine. Per impostazione predefinita, i raggruppamenti per canale di marketing vengono ancora visualizzati in Home page, Risultati ricerca e Pagamento, anche se ora si trovano nelle righe 4-6. <br> Al contrario, **Raggruppamento per posizione** raggrupperà sempre i primi 3 elementi, indipendentemente da quali siano. Facendo riferimento all’esempio, quando riapri il progetto, i raggruppamenti per canale di marketing sono legati alle prime 3 pagine della tabella. E non alla homepage, ai risultati della ricerca e al checkout, che ora si trovano nelle righe 4-6. |
| **[!UICONTROL Percentuali]** | **Calcola percentuali per colonna** (impostazione predefinita): le percentuali visibili in una cella vengono calcolate in base al totale della colonna. <br>**Calcola percentuali per riga**: le percentuali nelle celle vengono calcolate in una riga, anziché in una colonna, con il totale complessivo come denominatore. Questo calcolo è utile per le percentuali di tendenza. |
| **[!UICONTROL Totali colonne]** | Queste impostazioni sono disponibili solo per le [righe statiche](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostra come somma delle righe correnti** mostra una somma lato client delle righe nella tabella, il che significa che il totale *non* deduplica metriche quali visite o persone. <br> **Mostra totale** mostra una somma lato server, che indica il totale delle metriche deduplicate. |

## Modificare conteggio righe

Per modificare il numero di righe visualizzate:

1. Fai clic sul numero accanto a **[!UICONTROL Righe]** nella parte superiore della prima colonna della tabella.

   ![Tabella a forma libera che mostra il menu a discesa di per il numero di righe visualizzate. 400 righe selezionate.](assets/change-row-count.gif)

1. Dal menu a discesa, seleziona il numero di righe che si desidera visualizzare nella tabella.


## Menu di scelta rapida

Quando si seleziona l’intestazione della dimensione, sono disponibili le seguenti opzioni del menu di scelta rapida.

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Copia selezione negli Appunti]** | Copia la selezione dalla visualizzazione negli appunti. |
| **[!UICONTROL Scarica elementi come CSV (*nome dimensione*)]** | Scarica immediatamente gli elementi dimensionali (fino a un massimo di 50.000) della visualizzazione sul dispositivo locale. Un massimo di 50.000 elementi dimensionali per la dimensione selezionata. |
| **[!UICONTROL Scarica la selezione come CSV]** | Scarica immediatamente gli elementi dimensionali della visualizzazione sul dispositivo locale. |
| **[!UICONTROL Crea collegamento ipertestuale per tutti gli elementi della dimensione]** | Crea collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifica collegamento ipertestuale per tutti gli elementi dimensionali]** | Modifica i collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Rimuovi collegamento ipertestuale per tutti gli elementi dimensione]** | Rimuove i collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Elimina]** | Elimina la dimensione dalla tabella. |
| **[!UICONTROL Visualizza]** | Visualizza la dimensione utilizzando una qualsiasi delle visualizzazioni disponibili. |
| **[!UICONTROL Visualizza solo le righe selezionate]** | Visualizza solo gli elementi selezionati nella visualizzazione. |
| **[!UICONTROL Crea annotazione da selezione]** | Apri **[!UICONTROL Dettagli annotazione]** per aggiungere un&#39;annotazione. |


Quando si selezionano uno o più elementi dimensionali (prima colonna) o una o più celle singole nella tabella a forma libera, sono disponibili le seguenti opzioni aggiuntive del menu di scelta rapida.

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Crea collegamento ipertestuale]** | Crea un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifica collegamento ipertestuale]** | Modificare un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Rimuovi collegamento ipertestuale]** | Rimuove un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Raggruppamento]** | Suddividi l’elemento dimensione. Seleziona dall&#39;elenco di **[!UICONTROL Dimensioni]**, **[!UICONTROL Metriche]**, **[!UICONTROL Segmenti]** o **[!UICONTROL Intervalli di date]**. Ricerca alternativa per un componente, utilizzando *Ricerca*. |
| **[!UICONTROL Elimina selezionati]** | Elimina le righe (elementi) selezionate. |
| **[!UICONTROL Selezione tendenze]** | Crea una visualizzazione con grafico a linee di tendenza per la selezione. |
| **[!UICONTROL Visualizza solo le righe selezionate]** | Visualizza solo le righe selezionate nella visualizzazione. |
| **[!UICONTROL Visualizza tutte le righe]** | Visualizza tutte le righe della visualizzazione. |
| **[!UICONTROL Crea segmento da selezione]** | Apri **[!UICONTROL Generatore di segmenti]** per creare un segmento dalla selezione. |
| **[!UICONTROL Crea pubblico da selezione]** | Apri la finestra di dialogo **[!UICONTROL Crea pubblico]** per creare un pubblico dalla selezione. |

Quando si seleziona un’intestazione di colonna di una metrica, sono disponibili le seguenti opzioni aggiuntive del menu di scelta rapida.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Crea metrica da selezione]** | Crea una nuova metrica dalla metrica selezionata. La metrica può essere Media, Media, Colonna max, Colonna min, Somma colonna. Puoi anche selezionare Apri nel generatore di metriche calcolate per creare una metrica calcolata. |
| **[!UICONTROL Aggiungi colonna periodo di tempo]** | Aggiungi una colonna Periodo di tempo. Sono disponibili diverse opzioni, in cui l&#39;intervallo di calendario del pannello determina l&#39;*intervallo di date*: <li>**[!UICONTROL Precedente *intervallo di date* a questo intervallo di date]**</li><li>**[!UICONTROL Questo *intervallo di date* va a questo intervallo]**.</li><li>**[!UICONTROL Intervallo date personalizzato per questo intervallo di date]**. Apre **[!UICONTROL Generatore di intervalli di date]** per specificare l&#39;intervallo di date.</li>Per ulteriori informazioni, consulta [Confronto date](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Confronta periodi di tempo]** | Aggiunge le colonne del periodo di tempo di confronto. Disponibile solo quando la dimensione non è basata sul tempo. Sono disponibili diverse opzioni che determinano l&#39;*intervallo di date*: <li>**[!UICONTROL Precedente *intervallo di date* a questo intervallo di date]**</li><li>**[!UICONTROL Intervallo date personalizzato per questo intervallo di date]**. Apre **[!UICONTROL Generatore di intervalli di date]** per specificare l&#39;intervallo di date.</li>Per ulteriori informazioni, consulta [Confronto date](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Modifica modelli di attribuzione]** | Modifica il modello di attribuzione per la colonna. |
| **[!UICONTROL Confronta modello di attribuzione]** | Specifica un nuovo modello di attribuzione e confrontalo con il modello di attribuzione per la colonna selezionata. Viene aggiunta una nuova colonna con le nuove metriche del modello di attribuzione. Inoltre, viene aggiunta una colonna Percentuale di variazione per il confronto. |
| **[!UICONTROL Reimposta larghezza colonne]** | Ripristina la larghezza predefinita delle colonne. |
| **[!UICONTROL Crea annotazione da selezione]** | Apri **[!UICONTROL Dettagli annotazione]** per aggiungere un&#39;annotazione. |
| **[!UICONTROL Crea segmento da selezione]** | Apri **[!UICONTROL Generatore di segmenti]** per creare un segmento dalla selezione. |
| **[!UICONTROL Crea pubblico da selezione]** | Apri la finestra di dialogo **[!UICONTROL Crea pubblico]** per creare un pubblico dalla selezione. |

## Modificare l&#39;altezza delle righe

È possibile impostare la [densità di visualizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density) di un progetto su **[!UICONTROL Compatto]**, **[!UICONTROL Comoda]** e **[!UICONTROL Espansa]**.
