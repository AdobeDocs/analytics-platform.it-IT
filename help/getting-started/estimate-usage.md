---
title: Stimare e gestire l’utilizzo di CJA
description: Mostra due metodi per stimare l'utilizzo e un metodo per gestirlo.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 43%

---


# Stimare e gestire l’utilizzo di CJA

Per comprendere l’utilizzo di CJA, puoi utilizzare 2 metodi:

* Aggiungi le righe dei dati dell’evento per ogni connessione. (Vedi **Stimare la dimensione della connessione** sotto)
* Utilizza Analysis Workspace per creare rapporti sugli eventi del mese scorso. (Vedi **Creare un progetto Workspace utilizzando tutti i dati dell’evento** qui sotto.)

Per gestire l’utilizzo di CJA:

* Utilizza l’API CJA. (Vedi **Creare un rapporto nell’API CJA** qui sotto.)

## Stimare la dimensione della connessione {#estimate-size}

Potrebbe essere necessario sapere quante righe di dati evento si dispone attualmente in [!UICONTROL Customer Journey Analytics]. Per ottenere un resoconto accurato dell’utilizzo dei record di dati evento (righe di dati) per la tua organizzazione, procedi come segue **per ciascuna delle connessioni create dall’organizzazione**.

>[!NOTE]
>
>Effettua questa operazione il primo venerdì di ogni mese, in quanto Adobe esegue il rapporto sull’utilizzo più recente in quel giorno.

1. In [!UICONTROL Customer Journey Analytics], fai clic sulla scheda **[!UICONTROL Connections]**.

   Viene visualizzato un elenco di tutte le connessioni correnti.

1. Fai clic sul nome di ciascuna connessione per accedere alla funzione di gestione delle connessioni.

1. Aggiungi il **[!UICONTROL Records of event data available]** per ogni connessione creata dalla tua organizzazione. (A seconda delle dimensioni della connessione, la visualizzazione di questo valore potrebbe richiedere del tempo.)

   ![Dati evento](assets/event-data.png)

   >[!CAUTION]
   >
   >   Questo conteggio si applica solo ai dati evento, non ai dati di profilo o di ricerca. Se disponi di dati di profilo e ricerca, il conteggio sarà leggermente più alto. Tuttavia, attualmente non è possibile creare rapporti sull’utilizzo dei dati di profilo e di ricerca nell’interfaccia utente. Questa funzionalità è prevista per il 2023.

1. Una volta ottenuta la somma di tutte le righe di dati evento, controlla il diritto “Rows of Data” (Righe di dati) nel contratto per Customer Journey Analytics sottoscritto dalla tua azienda con Adobe.

   Si tratta del numero massimo di righe di dati autorizzato nell’ordine di vendita. Se il numero di righe di dati risultanti dal passaggio 3 è maggiore di questo valore massimo, si verifica un superamento del limite.

1. Per risolvere questa situazione, puoi scegliere tra diverse soluzioni:

   * Cambia le [impostazioni di conservazione dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=it#set-rolling-window-for-connection-data-retention).
   * [Elimina le connessioni non utilizzate](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * [Elimina un set di dati in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * Rivolgiti al tuo Adobe Account Manager per aggiungere alla licenza ulteriore capacità.

## Creare un progetto Workspace utilizzando tutti i dati dell’evento {#workspace-event-data}

1. Prima di creare il progetto in Workspace, [creare una visualizzazione dati](/help/data-views/create-dataview.md) che richiama i dati da TUTTE le tue connessioni e non ha filtri applicati. In altre parole, include tutti i tuoi dati.

1. In Workspace, crea un nuovo progetto ed esegui il richiamo di tutti gli eventi (dal **[!UICONTROL Metrics]** menu a discesa) per il mese precedente.

   ![Eventi](assets/events-usage.png)

1. eseguire questa operazione

## Creare un rapporto nell’API CJA {#api-report}

Utilizza la [API di reporting per CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) per eseguire un report su tutti i dati dell&#39;evento.