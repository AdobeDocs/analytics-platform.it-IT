---
title: Implicazioni dell’eliminazione
description: Che cosa accade quando si eliminano connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 928c79f9ccf30cc33e0f334f715bf3190a257019
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 65%

---

# Implicazioni dell’eliminazione

Prima di eliminare connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform, considera quanto segue:

| Azione | Risultato |
| --- | --- |
| Eliminare una connessione in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.</li></ul>Non è possibile eliminare connessioni di Customer Journey Analytics che: <ul><li>È associato alle sandbox di Adobe Experience Platform per le quali non disponi delle autorizzazioni necessarie. Anche se disponi delle autorizzazioni per le visualizzazioni dati create su tali connessioni, non puoi eliminarle finché non ti vengono concesse le autorizzazioni per le sandbox di Adobe Experience Platform sottostanti.</li><li>Selezionare la seguente opzione di compatibilità per una visualizzazione dati associata alla connessione: **[!UICONTROL Set as default data view in Adobe Journey Optimizer]**<p>Per ulteriori informazioni su questa opzione di configurazione, vedere [Compatibilità](/help/data-views/create-dataview.md#compatibility) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md)</p></li></ul> |
| Eliminare un set di dati in [!UICONTROL Adobe Experience Platform] | L’eliminazione di un set di dati in AEP interrompe il flusso di dati da tale set di dati a qualsiasi connessione che lo include. Tutti i dati provenienti da tale set di dati vengono eliminati automaticamente dalle connessioni di Customer Journey Analytics associate. |
| Eliminare un set di dati in [!UICONTROL Customer Journey Analytics] | Quando elimini un set di dati da una connessione in Customer Journey Analytics, tutte le visualizzazioni dati e i progetti basati su tale set di dati non funzioneranno più. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform]) | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni [!UICONTROL Customer Journey Analytics] che lo contengono. [!UICONTROL Customer Journey Analytics] viene informato dei batch eliminati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante l’acquisizione** in [!UICONTROL Customer Journey Analytics] | Se nel set di dati è presente un solo batch, in [!UICONTROL Customer Journey Analytics] non verranno visualizzati dati o dati parziale da tale batch. L’acquisizione verrà annullata e verrà ripristinato lo stato precedente. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell’eliminazione del set di dati, i dati di tali 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Elimina set di dati di ricerca in [!UICONTROL Adobe Experience Platform] | Anche se eliminazione dei set di dati è possibile per altri connettori di origine, al momento non è supportata per il [Connettore di origine per le classificazioni di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=it). Se elimini un set di dati per errore, contatta l’Assistenza clienti Adobe. |
