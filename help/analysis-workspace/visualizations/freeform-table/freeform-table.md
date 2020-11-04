---
title: Tabella a forma libera
description: Informazioni sulle tabelle a forma libera e sul generatore di tabelle a forma libera
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 100%

---


# Tabella a forma libera

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

In Analysis Workspace, una tabella a forma libera non è semplicemente una tabella di dati, ma è soprattutto una visualizzazione interattiva. Puoi trascinare una combinazione di [componenti](/help/components/overview.md) nelle righe e nelle colonne per creare una tabella personalizzata per l’analisi. Man mano che ciascun componente viene rilasciato, la tabella viene aggiornata immediatamente in modo da poter eseguire analisi rapide.

Puoi personalizzare la tabella in diversi modi:

* **Righe**
   * Prima dell’impaginazione ogni riga delle dimensioni può visualizzare fino a 400 righe. È possibile inserire più righe in una singola schermata regolando la [densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) del progetto.
   * Le righe possono essere suddivise per componenti aggiuntivi. Per suddividere più righe alla volta, seleziona semplicemente più righe e quindi trascina il componente successivo sopra le righe selezionate. Scopri di più sulle [suddivisioni](/help/components/dimensions/t-breakdown-fa.md).
   * Le righe possono essere [filtrate](/help/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md) per visualizzare un set ridotto di elementi. Sono disponibili altre impostazioni in [Impostazioni riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

* **Colonne**
   * I componenti possono essere impilati all’interno di colonne per creare metriche segmentate, analisi incrociate e altro ancora.
   * La visualizzazione di ogni colonna può essere regolata nelle [impostazioni della colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
   * Sono disponibili diverse azioni tramite il [menu di scelta rapida](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). A seconda dell’elemento su cui fai clic (intestazione della tabella, righe o colonne), il menu fornisce azioni diverse.

## Generatore di tabelle a forma libera

Se prima preferisci aggiungere diversi componenti alla tabella e quindi eseguire il rendering dei dati, puoi attivare il Generatore di tabelle a forma libera. Con il generatore abilitato, puoi trascinare e rilasciare più dimensioni, raggruppamenti, metriche e segmenti per creare tabelle che rispondano a esigenze più complesse. I dati non verranno aggiornati istantaneamente, ma solo dopo aver fatto clic su **[!UICONTROL Build]** (Crea).

Il Generatore di tabelle è un’opzione che consente di risparmiare tempo quando hai complesse richieste da estrapolare tramite i dati, e hai chiare idee su come creare la tabella affinché fornisca le giuste risposte alle tue domande. Altri vantaggi del generatore di tabelle includono la possibilità di:

* Disporre la tabella esattamente nel formato desiderato, senza dover attendere i tempi di rendering per ogni azione.
* Esegui rapidamente fino a 4 livelli di raggruppamento.
* Definisci le impostazioni di riga e raggruppamento per ogni riga della tabella e colonna delle dimensioni.
* **[!UICONTROL Breakdown by Position]** (Suddivisione per posizione) per ogni livello della tabella per impostazione predefinita (nelle tabelle a forma libera tradizionali, l’impostazione predefinita è **[!UICONTROL Breakdown by Item]** (Suddivisione per elemento)).
* Ordina manualmente le righe statiche nella tabella. Ad esempio, per visualizzare le righe di metrica in un determinato ordine.
* Visualizza in anteprima il formato della tabella prima di eseguire il rendering dei dati reali.

Osserva il Generatore di tabelle a forma libera in azione [qui](https://youtu.be/GUMWiJAmMGI).

## Esportare i dati dalla tabella a forma libera

I dati contenuti in una tabella a forma libera possono essere copiati da Analysis Workspace in alcuni modi:

* Fai clic con il pulsante destro del mouse su un’intestazione di tabella e seleziona **[!UICONTROL Copy to Clipboard]** (Copia negli Appunti). Verrà esportata la tabella completa (visibile).
* Per evidenziare celle specifiche nella tabella, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Copy to Clipboard]** (Copia negli Appunti), oppure usa la combinazione di tasti Ctrl + C.
* **[!UICONTROL Project > Download CSV]** (Progetto > scarica CSV). In questo modo tutte le tabelle visibili nel progetto verranno esportate come CSV.
