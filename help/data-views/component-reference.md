---
title: Documentazione dei componenti standard
description: Dettagli e informazioni su tutti i componenti standard che è possibile aggiungere a qualsiasi visualizzazione dati.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 4%

---

# Documentazione dei componenti standard

La maggior parte delle dimensioni e delle metriche in CJA si basa sugli elementi dello schema del set di dati di Adobe Experience Platform. Tuttavia, sono disponibili diversi componenti da aggiungere a una visualizzazione dati indipendentemente dalla connessione utilizzata.

[!UICONTROL Standard components] sono componenti che non sono generati dai campi dello schema del set di dati, ma che sono invece generati dal sistema. Alcuni componenti di sistema sono necessari per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![Componenti standard](assets/standard-components.png)

## Componenti standard richiesti

Per impostazione predefinita, questi componenti standard richiesti vengono aggiunti a ogni visualizzazione dati. Sono essenziali per le funzionalità di reporting offerte dal Customer Journey Analytics.

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| [!UICONTROL People] | Metrica | In base all’ID persona specificato in un [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metrica | In base alle impostazioni di sessione della visualizzazione dati. |
| [!UICONTROL Events] | Metrica | Il numero di righe da tutti i set di dati evento in un [!UICONTROL Connection]. |
| [!UICONTROL Minute] | Dimensione | Il minuto in cui si è verificato un dato evento (arrotondato per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. |
| [!UICONTROL Hour] | Dimensione | L&#39;ora in cui si è verificato un dato evento (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. |
| [!UICONTROL Day] | Dimensione | Il giorno in cui è accaduto un dato evento. Il primo elemento dimensione è il primo giorno dell’intervallo di date e l’ultimo elemento dimensione è l’ultimo giorno dell’intervallo di date. |
| [!UICONTROL Week] | Dimensione | La settimana in cui si è verificato un dato evento. Il primo elemento dimensione è la prima settimana nell’intervallo di date e l’ultimo elemento dimensione è l’ultima settimana nell’intervallo di date. |
| [!UICONTROL Month] | Dimensione | Il mese in cui si è verificato un determinato evento. Il primo elemento dimensione è il primo mese nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo mese nell’intervallo di date. |
| [!UICONTROL Quarter] | Dimensione | Il trimestre in cui si è verificato un dato evento. Il primo elemento dimensione è il primo trimestre nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo trimestre nell’intervallo di date. |
| [!UICONTROL Year] | Dimensione | L&#39;anno in cui si è verificato un dato evento. Il primo elemento dimensione è il primo anno nell’intervallo di date e l’ultimo elemento dimensione è l’anno più recente nell’intervallo di date. |

## Componenti standard opzionali

Componenti standard opzionali disponibili in **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** scheda > **[!UICONTROL Standard Components]** scheda .

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metrica | Il numero di eventi che sono stati il primo evento di una sessione. Utilizzato in una definizione di filtro (ad esempio &#39;[!UICONTROL Session Starts] esiste&#39;), si filtra fino al primo evento di ogni sessione. |
| [!UICONTROL Session Ends] | Metrica | Il numero di eventi che sono stati l&#39;ultimo evento di una sessione. Simile a [!UICONTROL Session Starts], può anche essere utilizzato in una definizione di filtro per filtrare gli elementi fino all’ultimo evento di ogni sessione. |
| [!UICONTROL Time Spent (seconds)] | Metrica | Somma il tempo tra due valori diversi per una dimensione. |
| [!UICONTROL Time Spent per Event] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica [!UICONTROL Event] secchi. |
| [!UICONTROL Time Spent per Session] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica [!UICONTROL Session] secchi. |
| [!UICONTROL Time Spent per Person] | Dimensione | Intervalli [!UICONTROL Time Spent] metrica [!UICONTROL Person] secchi. |
| [!UICONTROL Batch ID] | Dimensione | Rappresenta il batch di Experienci Platform che un [!UICONTROL Event] faceva parte di. |
| [!UICONTROL Dataset ID] | Dimensione | Rappresenta il set di dati di Experience Platform che un [!UICONTROL Event] faceva parte di. |