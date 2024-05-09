---
description: Crea intervalli di date personalizzati in Analysis Workspace e salvali come componenti Tempo.
keywords: Analysis Workspace
title: Creazione di intervalli di date personalizzati
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 47b7747b37f82e4d75d5272ce1d8d37f4e497bb5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 57%

---

# Creare intervalli di date personalizzati

Puoi creare intervalli di date personalizzati in Analysis Workspace e salvarli come componenti Tempo.

Per informazioni sull’aggiunta di intervalli di date esistenti a un progetto, consulta [Panoramica del calendario e degli intervalli di date](/help/components/date-ranges/calendar.md).

Per creare un intervallo di date personalizzato:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.

   ![pagina intervallo date](assets/date-ranges.png)

1. Seleziona [!UICONTROL **Crea un nuovo intervallo di date**].

1. Nel generatore di intervalli di date, specifica le seguenti informazioni:

   | Opzione | Descrizione |
   |---------|----------|
   | [!UICONTROL **Titolo**] | Titolo dell’intervallo di date che verrà visualizzato quando gli utenti lo selezioneranno in Analysis Workspace. |
   | [!UICONTROL **Descrizione**] | Descrizione dell’intervallo di date. |
   | [!UICONTROL **Tag**] | Qualsiasi tag che desideri applicare all’intervallo di date. |
   | [!UICONTROL **Intervallo date**] | Consente di scegliere un intervallo di date personalizzato. Per impostazione predefinita, sono selezionati gli ultimi 30 giorni. |
   | [!UICONTROL **Predefinito**] | Scegli da un elenco di intervalli di date predefiniti, come [!UICONTROL **Ieri**], [!UICONTROL **Ultimi 7 giorni**], [!UICONTROL **Ultimi 30 giorni**] e così via. |
   | [!UICONTROL **Ora di inizio**] | L’ora del giorno in cui inizia l’intervallo di date. |
   | [!UICONTROL **Ora di fine**] | L’ora del giorno in cui termina l’intervallo di date. |
   | [!UICONTROL **Utilizzare date continue**] | Le date continue consentono di generare un rapporto dinamico per un determinato periodo di tempo precedente o successivo all’esecuzione del rapporto. Ad esempio, per un rapporto su tutti gli ordini inseriti il “Mese scorso” (in base al campo Data creazione) eseguito in dicembre, vengono presentati gli ordini di novembre. Se esegui di nuovo lo stesso rapporto a gennaio, puoi vedere gli ordini di dicembre.<ul><li>**[!UICONTROL Date Preview]** (Anteprima data): indica il periodo di tempo coperto dal calendario continuo.</li><li>**[!UICONTROL Start]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li><li>**[!UICONTROL End]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li></ul><br>Selezionato per impostazione predefinita. |

1. Seleziona [!UICONTROL **Salva**].

## Esempio: intervallo di date per &quot;due mesi fa&quot; {#section_C4109C57CB444BB2A79CC8082BD67294}

Il seguente intervallo di date personalizzato mostra un intervallo per “due mesi fa”, con una visualizzazione del riepilogo delle modifiche che mostra i cambiamenti direzionali.

![](assets/date-range-two-months-ago.png)

L’intervallo di date personalizzato viene visualizzato nella parte superiore del pannello dei componenti [!UICONTROL Date Range] (Intervallo date) all’interno del progetto:

![](assets/date-range-panel-two-months-ago.png)

Puoi trascinare l’intervallo di date personalizzato all’interno di una colonna vicino a un intervallo di date continuo mensile personalizzato, utilizzando l’impostazione predefinita Mese precedente per un confronto. Aggiungi una visualizzazione di riepilogo delle modifiche e seleziona i totali da ogni colonna per mostrare il cambiamento direzionale:

![](assets/date-range-two-months-table.png)

## Esempio: utilizzare un intervallo di date continuo di 7 giorni {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Puoi creare un intervallo di date che specifica una finestra continua di 7 giorni che termina una settimana fa:

![](assets/create_date_range.png)

Utilizzare *`rolling daily`*.

* Le impostazioni Inizio corrispondono a *`current day minus 6 days`* (data attuale meno 14 giorni).

* Le impostazioni Fine corrispondono a *`current day minus 7 days`* (data attuale meno 7 giorni).

L’intervallo di date può diventare un componente da trascinare in qualsiasi tabella a forma libera.
