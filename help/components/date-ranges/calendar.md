---
description: Come specificare date e intervalli di date o selezionare un predefinito.
title: Panoramica del calendario e degli intervalli di date
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
source-git-commit: be49bcbbc9d1b7d3989e15a30114da8cbc5e4851
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 51%

---

# Panoramica del calendario e degli intervalli di date

Utilizzando il calendario, puoi specificare date e intervalli di date o selezionare un predefinito. Gli intervalli di date sono un tipo di componente utilizzabile nei progetti Workspace. Consentono di visualizzare i dati con le tendenze nel tempo o di vedere quando gli eventi si verificano maggiormente. Gli intervalli di date sono contraddistinti dal colore viola. Gli intervalli di date personalizzati ti consentono di personalizzare le date visualizzate nei progetti Workspace.

Le selezioni di calendario sono applicabili a livello del singolo pannello, ma è possibile applicarle a tutti i pannelli. Quando fai clic su un intervallo di date in Workspace, l’interfaccia mostra il mese del calendario corrente e il mese del calendario precedente. È possibile regolare questi due calendari facendo clic sulle frecce destra e sinistra nei rispettivi angoli superiori.

![Calendario](assets/aw_calendar2.png){width="60%"}

Il primo clic su un calendario avvia una selezione di intervalli di date. Il secondo clic completa la selezione di un intervallo di date, che viene evidenziato. Se si tiene premuto il tasto `Shift` (o se si fa clic con il pulsante destro del mouse), si aggiunge all’intervallo attualmente selezionato.

È inoltre possibile trascinare le date (e dimensioni orarie) in un progetto Workspace. Puoi selezionare specifici giorni, settimane, mesi, anni, oppure una data continua.

[Utilizzo degli intervalli di date e del calendario in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=it) (4:07)

| Impostazione | Descrizione |
| --- | --- |
| Giorni selezionati | Giorni/settimane/mesi/anni selezionati |
| Uso delle date continue | Le date continue consentono di generare un rapporto dinamico per un determinato periodo di tempo precedente o successivo all’esecuzione del rapporto. Ad esempio, per un rapporto su tutti gli ordini inseriti il “Mese scorso” (in base al campo Data creazione) eseguito in dicembre, vengono presentati gli ordini di novembre. Se esegui di nuovo lo stesso rapporto a gennaio, puoi vedere gli ordini di dicembre.<ul><li>**[!UICONTROL Date Preview]** (Anteprima data): indica il periodo di tempo coperto dal calendario continuo.</li><li>**[!UICONTROL Start]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li><li>**[!UICONTROL End]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li></ul>Un esempio è disponibile [qui](/help/components/date-ranges/custom-date-ranges.md). |
| Intervallo date | Consente di scegliere un intervallo di date predefinito. Il valore predefinito è Ultimi 30 giorni. **[!UICONTROL This week/month/quarter/year (excluding today)]** consente di scegliere tra intervalli di date che non includono dati per giorni parziali a partire da oggi. |
| Applica a tutti i pannelli | Consente di selezionare l’intervallo di date per il pannello corrente e per tutti gli altri pannelli del progetto. |
| Applica | Applica l’intervallo di date solo al pannello corrente. |

## Informazioni sugli intervalli di date del pannello relativo {#relative-panel-dates}

Se lavori in Workspace, puoi rendere i componenti dell’intervallo di date relativi al calendario del pannello. Tre casi d’uso comuni in cui vedrai che le date del pannello relativo diventano effettive sono i grafici combinati, il riepilogo delle metriche chiave e gli intervalli di date delle tabelle a forma libera.

Per utilizzare gli intervalli di date del pannello relativo

1. Seleziona la **Workspace** scheda.
1. Seleziona **Progetto vuoto**.
1. Aggiungi dimensioni, metriche e filtri dalla barra a sinistra.
1. Fai clic sul campo intervallo date del pannello per attivare/disattivare l’impostazione dell’intervallo date del pannello relativo.
1. Seleziona **Rendi i componenti dell’intervallo di date relativi al calendario del pannello**.
   * Seleziona l’opzione per rendere i componenti dell’intervallo di date relativi al calendario del pannello.
Se sono selezionate date relative, le date continue verranno basate sulla data di inizio del calendario del pannello e non sulla data odierna.
   * Se questa opzione non è selezionata, le date di rotazione saranno basate sulla data odierna.

   ![date relative del pannello](assets/relative-date-selected.png){width="60%"}

1. Fai clic su **Applica**.
Le date relative sono visualizzate in alto a destra.

   ![date relative a forma libera ](assets/relative-date-range1.png)

## Linee guida per intervalli di date relativi del pannello {#guidelines}

Quando utilizzi intervalli di date relativi per il pannello, tieni presenti le seguenti linee guida.

### Formule e intervalli di date relativi {#formula-relative-dates}

Se hai selezionato date relative, tutte le formule di date utilizzeranno la data di inizio del pannello come punto iniziale.

### Calendari personalizzati e intervalli di date relativi {#custom-calendar-formulas}

Quando si utilizza un calendario personalizzato basato su settimane e si aggiungono mesi o anni, la formula calcola lo scostamento del giorno nel periodo specificato. La data effettiva può essere diversa a causa dell&#39;offset. La formula sceglie il giorno di destinazione nello stesso punto del calendario personalizzato. Ad esempio, il terzo venerdì della terza settimana in un calendario personalizzato.

### Informazioni sui filtri che utilizzano date continue e intervalli di date del pannello relativo {#segments-relative-dates}

Se crei un filtro o utilizzi un filtro con una data continua, ad esempio gli Ultimi 7 giorni o le Ultime 2 settimane, e fai clic sull’anteprima del filtro, la data continua verrà avviata a partire da *Oggi* invece della data di inizio del pannello. Di conseguenza, l’anteprima del filtro non corrisponderà a quando utilizzi effettivamente il filtro nella tabella. È interessata l’anteprima, non il filtro stesso.

## Linee guida per intervalli di date e anteprime del pannello {#guidelines-panel-dates}

* A partire dalla versione di febbraio, le anteprime dei dati e dei componenti saranno basate sull’intervallo di date del pannello e non sugli ultimi 90 giorni.
* Tutti i componenti elencati nella barra a sinistra saranno disponibili in base all’intervallo di date del pannello.
* Tutte le anteprime di date nei generatori di filtri e metriche calcolate saranno basate sull’intervallo di date del pannello (a meno che i gestori dei componenti non vi abbiano accesso, saranno ancora basate sugli ultimi 90 giorni).
* Tutte le anteprime dei dati mostreranno dati o componenti in base all’intervallo di date del pannello.