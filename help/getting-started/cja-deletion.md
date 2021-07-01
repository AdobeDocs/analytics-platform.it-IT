---
title: Implicazioni di cancellazione
description: Che cosa accade quando si eliminano connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform.
source-git-commit: 3fa2c562abaf4aa1f18baa5de5ee66c7ad828f52
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Implicazioni di cancellazione

Considera questo prima di eliminare connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform:

| Quando... | Ciò si verifica... |
| --- | --- |
| Elimina una connessione in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Elimina un set di dati in [!UICONTROL Adobe Experience Platform] (AEP) | L’eliminazione di un set di dati in AEP interrompe il flusso di dati da tale set di dati a qualsiasi connessione che include tale set di dati. Eventuali dati provenienti da tale set di dati non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Elimina un set di dati in [!UICONTROL Customer Journey Analytics] | Al momento non è possibile eliminare un set di dati all’interno di una connessione salvata. Dovreste cancellare l&#39;intera connessione e ricominciare da capo. Tuttavia, puoi eliminare un set di dati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform]) | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni [!UICONTROL Customer Journey Analytics] che contengono tale batch specifico. [!UICONTROL Customer Journey Analytics] viene informato dei batch eliminati in  [!UICONTROL Adobe Experience Platform]. |
| Elimina un batch **durante l&#39;acquisizione** in [!UICONTROL Customer Journey Analytics] | Se nel set di dati è presente un solo batch, nessun dato o dato parziale da quel batch verrà visualizzato in [!UICONTROL Customer Journey Analytics]. L&#39;ingestione verrà rimandata. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell’eliminazione del set di dati, i dati di tali 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Elimina i set di dati di ricerca in [!UICONTROL Adobe Experience Platform] | Durante l’eliminazione dei set di dati è possibile per altri connettori di origine, al momento non è supportato per [Connettore dati classificazioni di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=en). Se elimini un set di dati per errore, contatta l’Assistenza clienti Adobe. |