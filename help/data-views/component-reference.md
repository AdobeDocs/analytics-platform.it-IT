---
title: Documentazione dei componenti standard
description: Dettagli e informazioni su tutti i componenti standard che è possibile aggiungere a qualsiasi visualizzazione dati.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 77%

---

# Documentazione dei componenti standard

La maggior parte delle dimensioni e delle metriche in Customer Journey Analytics si basa sugli elementi dello schema del set di dati di Adobe Experience Platform. Tuttavia, sono disponibili diversi componenti da aggiungere a una visualizzazione dati indipendentemente dalla connessione utilizzata.

[!UICONTROL Standard components] sono componenti che non sono generati dai campi dello schema del set di dati, ma che sono invece generati dal sistema. Alcuni componenti di sistema sono necessari per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![Componenti standard](assets/dataview-standard-components.png)

## Componenti standard richiesti {#required}

Per impostazione predefinita, questi componenti standard richiesti vengono aggiunti a ogni visualizzazione dati. Sono essenziali per le funzionalità di reporting offerte dal Customer Journey Analytics.

### Dimensioni standard

{{standard-dimensions}}


### Metriche standard

{{standard-metrics}}


## Componenti standard opzionali {#optional}

Componenti standard opzionali disponibili in **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** scheda > **[!UICONTROL Standard Components]** scheda.

| Nome componente | Dimensione o metrica | Note e valori |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Dimensione suddivisa in base al tempo | Mattina o pomeriggio |
| [!UICONTROL Batch ID] | Dimensione | Identificatore per il batch Experience Platform di cui faceva parte un [!UICONTROL Event]. |
| [!UICONTROL Dataset ID] | Dimensione | Identificatore per il set di dati di Experience Platform di cui faceva parte un [!UICONTROL Event]. |
| [!UICONTROL Day of Month] | Dimensione suddivisa in base al tempo | 1-31 |
| [!UICONTROL Day of Week] | Dimensione suddivisa in base al tempo | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| [!UICONTROL Day of Year] | Dimensione suddivisa in base al tempo | 1-366 |
| [!UICONTROL Hour of Day] | Dimensione suddivisa in base al tempo | 0-23 |
| [!UICONTROL &#x200B; Month of Year] | Dimensione suddivisa in base al tempo | Gennaio - Dicembre |
| [!UICONTROL First-time Sessions] | Metrica | Prima sessione definita da una persona all&#39;interno dell&#39;intervallo di reporting. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Return Sessions] | Metrica | Il numero di sessioni che non sono state le prime sessioni di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Person ID] | Dimensione | Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono ID cookie, ID unione, ID utente, Codice di tracciamento, ecc. La dimensione [!UICONTROL Person ID] è la base per combinare i set di dati e identificare persone univoche in Customer Journey Analytics.<p>Eventuali casi d’uso includono:<ul><li>Crea un segmento su un valore ID persona specifico per segmentare tutto in base al comportamento dell’utente.</li><li>Debug: accertati che siano presenti i dati per un ID cookie specifico (o un ID cliente specifico).</li><li>Identificazione degli utenti che hanno effettuato l&#39;accesso a un call center.</li></ul> |
| [!UICONTROL Person ID namespace] | Dimensione | Quale tipo di ID è costituito da [!UICONTROL Person ID]. Alcuni esempi: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Global Account ID] | Dimensione | [!UICONTROL Global Account ID], quando utilizzi il contenitore Account globale nella tua connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Account ID] | Dimensione | [!UICONTROL Account ID], quando utilizzi il contenitore Account nella connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Opportunity ID] | Dimensione | [!UICONTROL Opportunity ID], quando utilizzi il contenitore Opportunità nella connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Buying Group ID] | Dimensione | [!UICONTROL Buying Group ID], quando utilizzi il contenitore Gruppo acquisti nella connessione. |
| [!UICONTROL Quarter of Year] | Dimensione suddivisa in base al tempo | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Metrica | Il numero di sessioni che non sono state le prime sessioni di una persona. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Session Type] | Dimensione | Questa dimensione ha due valori: 1. [!UICONTROL First-Time] e 2. Ritorno. La riga [!UICONTROL First-time] include tutti i comportamenti (ovvero le metriche rispetto a questa dimensione) di una sessione che è stata determinata come prima sessione definita di una persona. Tutto il resto è incluso nell’elemento di riga [!UICONTROL Returning] (supponendo che tutto appartenga a una sessione). Se le metriche non fanno parte di alcuna sessione, rientrano nel bucket “Non applicabile” per questa dimensione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Event] bucket. |
| [!UICONTROL Time Spent per Session] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Session] bucket. |
| [!UICONTROL Time Spent per Person] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica nei [!UICONTROL Person] bucket. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Dimensione suddivisa in base al tempo | Fine settimana o giorno feriale |

{style="table-layout:auto"}
