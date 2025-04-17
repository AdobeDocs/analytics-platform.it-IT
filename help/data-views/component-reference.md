---
title: Documentazione dei componenti standard
description: Dettagli e informazioni su tutti i componenti standard che è possibile aggiungere a qualsiasi visualizzazione dati.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 82%

---

# Documentazione dei componenti standard

La maggior parte delle dimensioni e delle metriche in Customer Journey Analytics si basa sugli elementi dello schema del set di dati di Adobe Experience Platform. Tuttavia, sono disponibili diversi componenti da aggiungere a una visualizzazione dati indipendentemente dalla connessione utilizzata.

[!UICONTROL Standard components] sono componenti che non sono generati dai campi dello schema del set di dati, ma che sono invece generati dal sistema. Alcuni componenti di sistema sono necessari per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![Componenti standard](assets/dataview-standard-components.png)

## Componenti standard richiesti {#required}

Per impostazione predefinita, questi componenti standard richiesti vengono aggiunti a ogni visualizzazione dati. Sono essenziali per le funzionalità di reporting offerte dal Customer Journey Analytics.

| Nome componente | Dimensione o metrica | Note |
| --- | --- | --- |
| [!UICONTROL People] | Metrica | In base all’ID persona specificato in un [!UICONTROL Connection]. |
| [!UICONTROL Accounts] | Metrica | In base all&#39;ID account specificato in un [!UICONTROL Connection]. |
| [!UICONTROL Global Accounts] | Metrica | In base all&#39;ID account globale specificato in [!UICONTROL Connection]. |
| [!UICONTROL Opportunity] | Metrica | Le opportunità, in base all&#39;ID opportunità specificato in [!UICONTROL Connection]. |
| [!UICONTROL Buying Group] | Metrica | I gruppi di acquisto, in base all&#39;ID gruppo di acquisto specificato in [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metrica | In base alle impostazioni di sessione della visualizzazione dati. |
| [!UICONTROL Events] | Metrica | Il numero di righe da tutti i set di dati evento in un [!UICONTROL Connection]. |
| [!UICONTROL Seconds] | Dimensione | Il secondo in cui si è verificato un dato evento (arrotondato per difetto). Il primo elemento dimensione è il primo secondo nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo secondo nell’intervallo di date. |
| [!UICONTROL Minute] | Dimensione | Il minuto in cui si è verificato un dato evento (arrotondato per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. |
| [!UICONTROL Hour] | Dimensione | L&#39;ora in cui si è verificato un dato evento (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. |
| [!UICONTROL Day] | Dimensione | Il giorno in cui è accaduto un dato evento. Il primo elemento dimensione è il primo giorno dell’intervallo di date e l’ultimo elemento dimensione è l’ultimo giorno dell’intervallo di date. |
| [!UICONTROL Week] | Dimensione | La settimana in cui si è verificato un dato evento. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. |
| [!UICONTROL Month] | Dimensione | Il mese in cui si è verificato un determinato evento. Il primo elemento dimensione è il primo mese nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo mese nell’intervallo di date. |
| [!UICONTROL Quarter] | Dimensione | Il trimestre in cui si è verificato un dato evento. Il primo elemento dimensione è il primo trimestre nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo trimestre nell’intervallo di date. |
| [!UICONTROL Year] | Dimensione | L&#39;anno in cui si è verificato un dato evento. Il primo elemento dimensione è il primo anno nell’intervallo di date e l’ultimo elemento dimensione è l’anno più recente nell’intervallo di date. |
| [!UICONTROL Session Starts] | Metrica | Il numero di eventi che sono stati il primo evento di una sessione. Utilizzato in una definizione di segmento, ad esempio &#39;[!UICONTROL Session Starts] exists&#39;, si segmenta fino al primo evento di ogni sessione.<p>Questo componente deve essere incluso nella visualizzazione dati in modo che la seguente [metrica calcolata](/help/components/calc-metrics/default-calcmetrics.md) sia disponibile in Workspace: <ul><li>Frequenza di avvio sessione</li></p> |
| [!UICONTROL Session Ends] | Metrica | Il numero di eventi che sono stati l&#39;ultimo evento di una sessione. Simile a [!UICONTROL Session Starts], può essere utilizzato anche in una definizione di segmento per segmentare elementi fino all&#39;ultimo evento di ogni sessione.<p>Questo componente deve essere incluso nella visualizzazione dati in modo che la seguente [metrica calcolata](/help/components/calc-metrics/default-calcmetrics.md) sia disponibile in Workspace: <ul><li>Frequenza di fine sessione</li></p> |
| [!UICONTROL Time Spent (seconds)] | Metrica | Somma il tempo tra due valori diversi per una dimensione.<p>Questo componente deve essere incluso nella visualizzazione dati in modo che le seguenti [metriche calcolate](/help/components/calc-metrics/default-calcmetrics.md) siano disponibili in Workspace: <ul><li>Time Spent Per Person (Tempo trascorso per persona)</li><li>Tempo trascorso per sessione</li></p> |

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
| [!UICONTROL Return Sessions] | Metrica | Il numero di sessioni che non sono state le prime sessioni di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Person ID] | Dimensione | Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono ID cookie, ID unione, ID utente, Codice di tracciamento, ecc. La dimensione [!UICONTROL Person ID] è la base per combinare i set di dati e identificare persone univoche in Customer Journey Analytics.<p>Eventuali casi d’uso includono:<ul><li>La creazione di un segmento su un valore ID persona specifico per segmentare tutto in base al comportamento dell’utente.</li><li>Debug: accertati che siano presenti i dati per un ID cookie specifico (o un ID cliente specifico).</li><li>Identificazione degli utenti che hanno effettuato l&#39;accesso a un call center.</li></ul> |
| [!UICONTROL Person ID namespace] | Dimensione | Quale tipo di ID è costituito da [!UICONTROL Person ID]. Alcuni esempi: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Global Account ID] | Dimensione | [!UICONTROL Global Account ID], quando utilizzi il contenitore Account globale nella tua connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Account ID] | Dimensione | [!UICONTROL Account ID], quando utilizzi il contenitore Account nella connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Opportunity ID] | Dimensione | [!UICONTROL Opportunity ID], quando utilizzi il contenitore Opportunità nella connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Buying Group ID] | Dimensione | [!UICONTROL Buying Group ID], quando utilizzi il contenitore Gruppo acquisti nella connessione. |
| [!UICONTROL Quarter of Year] | Dimensione suddivisa in base al tempo | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Metrica | Il numero di sessioni che non sono state le prime sessioni di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Session Type] | Dimensione | Questa dimensione ha due valori: 1. [!UICONTROL First-Time] e 2. Ritorno. La riga [!UICONTROL First-time] include tutti i comportamenti (ovvero le metriche rispetto a questa dimensione) di una sessione che è stata determinata come prima sessione definita di una persona. Tutto il resto è incluso nell’elemento di riga [!UICONTROL Returning] (supponendo che tutto appartenga a una sessione). Se le metriche non fanno parte di alcuna sessione, rientrano nel bucket “Non applicabile” per questa dimensione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Event] bucket. |
| [!UICONTROL Time Spent per Session] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Session] bucket. |
| [!UICONTROL Time Spent per Person] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Person] bucket. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Dimensione suddivisa in base al tempo | Fine settimana o giorno feriale |

{style="table-layout:auto"}
