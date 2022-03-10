---
title: Come stimare la dimensione della connessione CJA
description: Rapporto sull’utilizzo corrente del Customer Journey Analytics
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 74934c8684198104c808284310bcdfd633085574
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 43%

---

# Stimare la dimensione della connessione

Potrebbe essere necessario sapere quante righe di dati si hanno attualmente in [!UICONTROL Customer Journey Analytics]. Per ottenere un account accurato dell&#39;utilizzo dei record di dati evento (righe di dati) della tua organizzazione, procedi come segue **per ciascuna delle connessioni create dall&#39;organizzazione**.

1. In [!UICONTROL Customer Journey Analytics], fai clic sulla scheda **[!UICONTROL Connections]**.

   È ora possibile visualizzare un elenco di tutte le connessioni correnti.

1. Fare clic sul nome di ciascuna connessione per accedere a Gestione connessioni.

1. Aggiungi il **[!UICONTROL Records of event data available]** per tutte le connessioni create. (A seconda delle dimensioni della connessione, la visualizzazione del numero potrebbe richiedere del tempo.)

   ![dati evento](assets/event-data.png)

1. Una volta che hai una somma di tutte le righe di dati dell’evento, cerca il diritto &quot;Righe di dati&quot; nel contratto di Customer Journey Analytics firmato dalla tua azienda con Adobe.

   In questo modo si ottiene il numero massimo di righe di dati autorizzati nell&#39;ordine di vendita. Se il numero di righe di dati risultanti dal passaggio 3 è maggiore di questo numero, si verifica un&#39;overage.

1. Per risolvere questa situazione, è possibile scegliere tra diverse opzioni:

   * Cambia il tuo [impostazioni di conservazione dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=it#set-rolling-window-for-connection-data-retention).
   * [Elimina le connessioni non utilizzate](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * [Eliminare un set di dati in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
   * Contatta il tuo Adobe Account Manager per richiedere la licenza di una capacità aggiuntiva.

## Per quanto riguarda le eccedenze di utilizzo

I limiti di utilizzo sono rigorosamente controllati e applicati dall&#39;Adobe, su base giornaliera. Per &quot;righe di dati&quot; si intendono le righe medie giornaliere di dati disponibili per l’analisi all’interno del Customer Journey Analytics.

Supponiamo che il diritto al contratto limiti il numero di righe a 1 milione. Supponiamo che al giorno 1 dell&#39;utilizzo del Customer Journey Analytics, si caricino 2 milioni di righe di dati. Il giorno 2, elimini 1 milione di righe e mantieni l’utilizzo al massimo impegnato per il resto del periodo di licenza. A seconda dei termini contrattuali, è comunque possibile che si verifichino costi di utilizzo eccessivo proporzionati per il giorno 1.

## Diagnosticare le discrepanze

In alcuni casi, puoi notare che il numero totale di eventi acquisiti dalla connessione è diverso dal numero di righe nel set di dati in [!UICONTROL Adobe Experience Platform]. In questo esempio, il set di dati “Impressione B2B” ha 7650 righe, ma il set di dati contiene 3830 righe in [!UICONTROL Adobe Experience Platform]. Ci sono diversi motivi per cui possono verificarsi discrepanze e possono essere adottate le seguenti misure per diagnosticare:

1. Suddividi questa dimensione per **[!UICONTROL Platform Dataset ID]** e noterai due set di dati con le stesse dimensioni ma diversi **[!UICONTROL Platform Dataset IDs]**. Ogni set di dati ha 3825 record. Ciò significa che [!UICONTROL Customer Journey Analytics] ha ignorato 5 record a causa di ID persona mancanti o marche temporali mancanti:

   ![raggruppamento](assets/data-size2.png)

1. Inoltre, se controlliamo in [!UICONTROL Adobe Experience Platform], non esiste un set di dati con ID “5f21c12b732044194bffc1d0”, quindi qualcuno ha cancellato questo particolare set di dati da [!UICONTROL Adobe Experience Platform] quando è stata creata la connessione iniziale. Più tardi è stato aggiunto di nuovo al Customer Journey Analytics, ma un [!UICONTROL Platform Dataset ID] è stato generato da [!UICONTROL Adobe Experience Platform].

Ulteriori informazioni sulle [implicazioni del set di dati e dell’eliminazione della connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] e [!UICONTROL Adobe Experience Platform].
