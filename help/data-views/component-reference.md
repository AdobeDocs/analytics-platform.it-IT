---
title: Documentazione dei componenti standard
description: Dettagli e informazioni su tutti i componenti standard che è possibile aggiungere a qualsiasi visualizzazione dati.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 949f0870c8607879d4f685f4fbeb838ddb68f80a
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 74%

---

# Documentazione dei componenti standard

La maggior parte delle dimensioni e delle metriche in Customer Journey Analytics si basa sugli elementi dello schema del set di dati Adobe Experience Platform. Tuttavia, sono disponibili diversi componenti da aggiungere a una visualizzazione dati indipendentemente dalla connessione utilizzata.

[!UICONTROL Standard components] sono componenti che non sono generati dai campi dello schema del set di dati, ma che sono invece generati dal sistema. Alcuni componenti di sistema sono necessari per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![Componenti standard](assets/dataview-standard-components.png)

## Componenti standard richiesti {#required}

Per impostazione predefinita, questi componenti standard richiesti vengono aggiunti a ogni visualizzazione dati. Sono essenziali per le funzionalità di reporting offerte dal Customer Journey Analytics.

| Nome componente | Dimensione o metrica | Note |
| --- | --- | --- |
| [!UICONTROL People] | Metrica | In base all’ID persona specificato in un [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metrica | In base alle impostazioni di sessione della visualizzazione dati. |
| [!UICONTROL Events] | Metrica | Il numero di righe da tutti i set di dati evento in un [!UICONTROL Connection]. |
| [!UICONTROL Seconds] | Dimensione | Il secondo evento (arrotondato per difetto). Il primo elemento dimensione è il primo secondo nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo secondo nell’intervallo di date. |
| [!UICONTROL Minute] | Dimensione | Il minuto in cui si è verificato un dato evento (arrotondato per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. |
| [!UICONTROL Hour] | Dimensione | L&#39;ora in cui si è verificato un dato evento (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. |
| [!UICONTROL Day] | Dimensione | Il giorno in cui è accaduto un dato evento. Il primo elemento dimensione è il primo giorno dell’intervallo di date e l’ultimo elemento dimensione è l’ultimo giorno dell’intervallo di date. |
| [!UICONTROL Week] | Dimensione | La settimana in cui si è verificato un dato evento. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. |
| [!UICONTROL Month] | Dimensione | Il mese in cui si è verificato un determinato evento. Il primo elemento dimensione è il primo mese nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo mese nell’intervallo di date. |
| [!UICONTROL Quarter] | Dimensione | Il trimestre in cui si è verificato un dato evento. Il primo elemento dimensione è il primo trimestre nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo trimestre nell’intervallo di date. |
| [!UICONTROL Year] | Dimensione | L&#39;anno in cui si è verificato un dato evento. Il primo elemento dimensione è il primo anno nell’intervallo di date e l’ultimo elemento dimensione è l’anno più recente nell’intervallo di date. |
| [!UICONTROL Session Starts] | Metrica | Il numero di eventi che sono stati il primo evento di una sessione. Se utilizzato in una definizione di filtro (ad esempio, &quot;[!UICONTROL Session Starts] exists’), si filtra fino al primo evento di ogni sessione.<p>Questo componente deve essere incluso nella visualizzazione dati per i seguenti elementi [metrica calcolata](/help/components/calc-metrics/default-calcmetrics.md) per essere disponibile in Workspace: <ul><li>Session Start Rate (Frequenza di inizio sessione)</li></p> |
| [!UICONTROL Session Ends] | Metrica | Il numero di eventi che sono stati l&#39;ultimo evento di una sessione. Simile a [!UICONTROL Session Starts], può anche essere utilizzato in una definizione di filtro per filtrare gli elementi fino all’ultimo evento di ogni sessione.<p>Questo componente deve essere incluso nella visualizzazione dati per i seguenti elementi [metrica calcolata](/help/components/calc-metrics/default-calcmetrics.md) per essere disponibile in Workspace: <ul><li>Session End Rate (Frequenza di fine sessione)</li></p> |
| [!UICONTROL Time Spent (seconds)] | Metrica | Somma il tempo tra due valori diversi per una dimensione.<p>Questo componente deve essere incluso nella visualizzazione dati per i seguenti elementi [metriche calcolate](/help/components/calc-metrics/default-calcmetrics.md) per essere disponibile in Workspace: <ul><li>Tempo trascorso per persona</li><li>Time Spent Per Session (Tempo trascorso per sessione)</li></p> |

{style="table-layout:auto"}

## Componenti standard opzionali {#optional}

Componenti standard opzionali disponibili in **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** scheda > **[!UICONTROL Standard Components]** scheda.

| Nome componente | Dimensione o metrica | Note e valori |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Dimensione suddivisa in base al tempo | Mattina o pomeriggio |
| [!UICONTROL Batch ID] | Dimensione | Rappresenta il batch di Experience Platform di cui faceva parte un [!UICONTROL Event]. |
| [!UICONTROL Dataset ID] | Dimensione | Rappresenta il set di dati di Experience Platform di cui faceva parte un [!UICONTROL Event]. |
| [!UICONTROL Day of Month] | Dimensione suddivisa in base al tempo | 1-31 |
| [!UICONTROL Day of Week] | Dimensione suddivisa in base al tempo | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| [!UICONTROL Day of Year] | Dimensione suddivisa in base al tempo | 1-366 |
| [!UICONTROL Hour of Day] | Dimensione suddivisa in base al tempo | 0-23 |
| [!UICONTROL  Month of Year] | Dimensione suddivisa in base al tempo | Gennaio - Dicembre |
| [!UICONTROL First-time Sessions] | Metrica | Prima sessione definita da una persona all&#39;interno dell&#39;intervallo di reporting. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Return Sessions] | Metrica | Il numero di sessioni che non sono state la prima sessione di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Person ID] | Dimensione | Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di monitoraggio) e così via. Il [!UICONTROL Person ID] La dimensione è la base per combinare i set di dati e identificare persone univoche nel Customer Journey Analytics.<p>Eventuali casi d’uso includono:<ul><li>Creazione di un filtro per un valore ID persona specifico per filtrare tutto in base al comportamento dell’utente.</li><li>Debug: accertati che siano presenti i dati per un ID cookie specifico (o un ID cliente specifico).</li><li>Identificazione degli utenti che hanno effettuato l&#39;accesso a un call center.</li></ul> |
| [!UICONTROL Person ID namespace] | Dimensione | Quale tipo di ID è costituito da [!UICONTROL Person ID]. Alcuni esempi: `email address`, `cookie ID`, `Analytics ID` |
| [!UICONTROL Quarter of Year] | Dimensione suddivisa in base al tempo | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Metrica | Il numero di sessioni che non sono state le prime sessioni di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Session Type] | Dimensione | Questa dimensione ha due valori: 1) [!UICONTROL First-Time] e 2) Ritorno. Il [!UICONTROL First-time] l’elemento riga include tutti i comportamenti (metriche rispetto a questa dimensione) di una sessione che è stata determinata come prima sessione definita da una persona. Tutto il resto è incluso nell’elemento riga [!UICONTROL Returning] (supponendo che tutto appartenga a una sessione). Se le metriche non fanno parte di alcuna sessione, rientrano nel bucket &quot;Non applicabile&quot; per questa dimensione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Event] bucket. |
| [!UICONTROL Time Spent per Session] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Session] bucket. |
| [!UICONTROL Time Spent per Person] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Person] bucket. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Dimensione suddivisa in base al tempo | Fine settimana o giorno feriale |

{style="table-layout:auto"}
