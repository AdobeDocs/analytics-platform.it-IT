---
description: Nel calendario, puoi specificare date e intervalli di date o selezionare un predefinito.
title: Panoramica del calendario e degli intervalli di date
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
source-git-commit: 969040538e12ef3c3d15881ae225af02bef1cba4
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 51%

---

# Panoramica del calendario e degli intervalli di date

Nel calendario, puoi specificare date e intervalli di date o selezionare un predefinito.

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

## Informazioni sugli intervalli di date relativi al pannello {#relative-panel-dates}

Se lavori in Workspace, puoi rendere i componenti dell’intervallo di date relativi al calendario del pannello. Tre casi d’uso comuni in cui vengono applicate le date dei pannelli relativi sono grafici combinati, riepilogo delle metriche chiave e intervalli di date delle tabelle a forma libera.

Per utilizzare intervalli di date relativi al pannello

1. Seleziona la **Area di lavoro** scheda .
1. Seleziona **Progetto vuoto**.
1. Aggiungi dimensioni, metriche e segmenti dalla barra a sinistra.
1. Fai clic sul campo dell’intervallo di date del pannello per attivare/disattivare l’impostazione dell’intervallo di date relativo al pannello.
1. Seleziona **Rendere i componenti dell’intervallo di date relativi al calendario del pannello**.
   * Seleziona l’opzione per rendere i componenti dell’intervallo di date relativi al calendario del pannello.
Se sono selezionate date relative, le date continue saranno basate sulla data di inizio del calendario del pannello e non sulla data odierna.
   * Se questa opzione non è selezionata, le date continue saranno basate sulla data odierna.

   ![date del pannello relativo](assets/relative-date-selected.png){width="60%"}

1. Fai clic su **Applica**.
Le date relative vengono visualizzate in alto a destra.

   ![date relative a forma libera ](assets/relative-date-range1.png)

## Linee guida per gli intervalli di date relativi al pannello {#guidelines}

Quando utilizzi intervalli di date relativi al pannello, ricorda quanto segue.

### Formule e intervalli di date relativi {#formula-relative-dates}

Se selezioni date relative, come punto iniziale verranno utilizzate tutte le formule per date.

### Calendari personalizzati e intervalli di date relativi {#custom-calendar-formulas}

Quando si utilizza un calendario personalizzato basato su una settimana e si aggiungono mesi o anni, la formula calcola l&#39;offset del giorno nel periodo specificato. La data effettiva può essere diversa a causa dell&#39;offset. La formula sceglie l’destinazione del giorno nello stesso punto del calendario personalizzato. Ad esempio, il terzo venerdì della terza settimana in un calendario personalizzato.

### Informazioni sui segmenti che utilizzano date continue e intervalli di date relativi al pannello {#segments-relative-dates}

Se crei un segmento o utilizzi un segmento con una data continua, ad esempio gli Ultimi 7 giorni o le Ultime 2 settimane, e fai clic sull’anteprima del segmento, la data continua verrà avviata da *Oggi* anziché la data di inizio del pannello. Di conseguenza, l’anteprima del segmento non corrisponderà quando si utilizza effettivamente il segmento nella tabella. L’anteprima è interessata, non il segmento stesso.
