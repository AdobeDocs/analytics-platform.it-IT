---
title: Visualizza e gestisci l’utilizzo di Customer Journey Analytics
description: Mostra due metodi per stimare l’utilizzo e un metodo per la gestione.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 71%

---

# Visualizza e gestisci l’utilizzo di Customer Journey Analytics

Per visualizzare l’utilizzo del Customer Journey Analytics, puoi utilizzare diversi metodi:

* Aggiungi le righe dei dati dell’evento per ogni connessione. Consulta la sezione [Stimare la dimensione della connessione](#stimare la dimensione) di seguito. Questo è un modo semplice per visualizzare i dati della riga dell’evento, per ogni connessione, per una specifica marca temporale.
* Puoi visualizzare l’utilizzo in tre modi, descritti più dettagliatamente di seguito:
   * Utilizza Analysis Workspace per creare rapporti sugli eventi del mese scorso.
   * Utilizza Report Builder per creare rapporti sugli eventi del mese scorso.
   * Utilizza l’API di Customer Journey Analytics per creare un rapporto automatico.

Per gestire l&#39;utilizzo del Customer Journey Analytics:

* Definire una finestra dei dati continua.

## Stimare la dimensione della connessione {#estimate-size}

Potrebbe essere necessario sapere quante righe di dati evento si hanno attualmente in [!UICONTROL Customer Journey Analytics]. Per ottenere un resoconto accurato dell’utilizzo dei record di dati evento (righe di dati) per la tua organizzazione, procedi come segue **per ciascuna delle connessioni create dall’organizzazione**.

>[!NOTE]
>
>Effettua questa operazione il primo venerdì di ogni mese, in quanto Adobe genera il rapporto sull’utilizzo più recente in quel giorno.

1. In [!UICONTROL Customer Journey Analytics], fai clic sulla scheda **[!UICONTROL Connections]**.

   Viene visualizzato un elenco di tutte le connessioni correnti.

1. Fai clic sul nome di ciascuna connessione per accedere alla funzione di gestione delle connessioni.

1. Aggiungi il **[!UICONTROL Records of event data available]** (Registro dei dati evento disponibili) per ogni connessione creata dalla tua organizzazione. (A seconda delle dimensioni della connessione, la visualizzazione di questo valore potrebbe richiedere del tempo.)

   ![Dati evento](./assets/event-data.png)

   >[!CAUTION]
   >
   >   Questo conteggio si applica solo ai dati evento, non ai dati di profilo o di ricerca. Se disponi di dati di profilo e ricerca, il conteggio sarà leggermente più alto. Tuttavia, attualmente non è possibile creare rapporti sull’utilizzo dei dati di profilo e di ricerca nell’interfaccia utente. Questa funzionalità è prevista per il 2023.

1. Una volta ottenuta la somma di tutte le righe di dati evento, controlla il diritto “Rows of Data” (Righe di dati) nel contratto per Customer Journey Analytics sottoscritto dalla tua azienda con Adobe.

   Si tratta del numero massimo di righe di dati autorizzato nell’ordine di vendita. Se il numero di righe di dati risultanti dal passaggio 3 è maggiore di questo valore massimo, si verifica un superamento del limite.

1. Per risolvere questa situazione, puoi scegliere tra diverse soluzioni:

   * Cambia le [impostazioni di conservazione dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=it#set-rolling-window-for-connection-data-retention).
   * [Elimina le connessioni non utilizzate](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * [Eliminare un set di dati in Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * Contatta il tuo Adobe Account Team per aggiungere alla licenza ulteriore capacità.

## Creare un progetto Workspace utilizzando tutti i dati evento {#workspace-event-data}

Questo metodo consente di eseguire un’analisi più approfondita dei dati di utilizzo e della cronologia di utilizzo.

1. Prima di creare il progetto in Workspace, [crea una visualizzazione dati](/help/data-views/create-dataview.md) per ciascuna connessione, senza applicare alcun filtro.

>[!WARNING]
>
>    Non creare una nuova connessione che includa tutti i dati solo per misurare l’utilizzo, in quanto ciò raddoppierebbe l’utilizzo.

1. In Workspace, crea nuovi progetti basati su ciascuna delle visualizzazioni dati e richiama tutti gli eventi (dalla sezione **[!UICONTROL Metrics]** (elenco a discesa) fino al primo venerdì del mese, a partire dal primo giorno del contratto di Customer Journey Analytics corrente.

   ![Eventi](./assets/events-usage.png)

   Da qui puoi avere un’idea dell’andamento del tuo consumo mese per mese.

1. A seconda delle tue esigenze, puoi approfondire i set di dati, ecc.

## Creare un blocco dati in Report Builder {#arb}

In Report Builder, [crea un blocco dati](/help/report-builder/create-a-data-block.md) per ogni visualizzazione dati, quindi sommali.

## Creazione di un rapporto automatico nell’API di Customer Journey Analytics {#api-report}

1. Utilizza il [API di reporting per Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) per eseguire un report su tutti i dati evento, **per ogni connessione**. Usa questa configurazione per generare il rapporto

   * ogni primo venerdì di ogni mese.
   * tornare al primo giorno del contratto di Customer Journey Analytics corrente.

   Da qui puoi avere un’idea dell’andamento del tuo consumo mese per mese. Ti fornirà il numero totale di righe su tutte le connessioni di Customer Journey Analytics.

1. Usa Excel per personalizzare ulteriormente il rapporto.

## Gestire l’utilizzo definendo una finestra dati continua {#rolling}

Per gestire l’utilizzo, il [Interfaccia utente connessioni](/help/connections/create-connection.md) consente di definire la conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.

Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.

Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati verrà sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di 25 mesi di dati in Experience Platform, il Customer Journey Analytics riceverà 25 mesi di dati tramite backfill. Se elimini 10 di questi mesi in Platform, il Customer Journey Analytics mantiene i restanti 15 mesi.

La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Se la connessione include qualsiasi profilo o set di dati di ricerca, poiché sono uniti con set di dati evento, i dati vengono conservati in Customer Journey Analytics in base alle impostazioni di conservazione dei dati sulle marche temporali del set di dati evento.

