---
title: Gestione delle connessioni
description: Descrive come gestire le connessioni ai set di dati della Platform.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 37%

---


# Gestione delle connessioni

Una volta create una o più connessioni, puoi gestirle all’interno di [!UICONTROL Connections] Manager. È possibile

* Eliminare una connessione.
* Rinominare una connessione.
* Creare una visualizzazione dati a partire da una connessione.
* Avviare e interrompi lo streaming dei dati.

![Connections manager](assets/connections-manager.png) (Gestore connessioni)

1. Fai clic sulla scheda **[!UICONTROL Connections]**.

2. Seleziona le connessioni da modificare o gestire.

3. Completa una delle seguenti azioni:

   | Azione | Descrizione |
   |---|---|
   | [!UICONTROL Delete] | L’eliminazione di una connessione non comporta l’eliminazione del relativo set di dati, poiché i dati sono ancora presenti all’interno di [!DNL Adobe Experience Platform]. Vedi &quot;Elimina connessioni&quot; di seguito. |
   | [!UICONTROL Rename] | È possibile rinominare la connessione con un nome più descrittivo. |
   | [!UICONTROL Create Data View] | Questo collegamento ti porta al [data view builder](/help/data-views/create-dataview.md) (Generatore di visualizzazione dati). |
   | [!UICONTROL Start or stop data streaming] | La parola “streaming” indica che, se vengono aggiunti nuovi batch a uno qualsiasi dei set di dati della connessione, questi nuovi dati verranno inseriti in [!UICONTROL Customer Journey Analytics] a scopo di reporting. |

## Elimina connessioni

| E se io... | Ciò si verifica |
| --- | --- |
| Eliminare una connessione in [!UICONTROL Customer Journey Analytics]? | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Allo stesso modo, tutti i progetti Workspace che dipendono dalla visualizzazione dei dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare un set di dati in [!UICONTROL Adobe Experience Platform]? | L&#39;eliminazione di un set di dati in AEP interrompe il flusso di dati da tale set di dati a tutte le connessioni che lo includono. Eventuali dati provenienti da tale dataset non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Eliminare un set di dati in [!UICONTROL Customer Journey Analytics]? | Al momento non è possibile eliminare un dataset all&#39;interno di una connessione salvata. Dovreste eliminare l&#39;intera connessione e ricominciare da capo. Tuttavia, è possibile eliminare un set di dati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform])? | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni [!UICONTROL Customer Journey Analytics] che contengono tale batch specifico. [!UICONTROL Customer Journey Analytics] vengono notificati i batch in cui sono stati eliminati  [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante l&#39;assimilazione di** in [!UICONTROL Customer Journey Analytics]? | Se nel set di dati è presente un solo batch, nessun dato o dato parziale proveniente da tale batch verrà visualizzato in [!UICONTROL Customer Journey Analytics]. L&#39;assimilazione verrà ripristinata. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell&#39;eliminazione del set di dati, i dati provenienti da questi 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
