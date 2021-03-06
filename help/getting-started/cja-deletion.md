---
title: Implicazioni dell’eliminazione
description: Che cosa accade quando si eliminano connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 3f20520a2021d9b6066b0492ed11a1a4619ab1d4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 93%

---

# Implicazioni dell’eliminazione

Prima di eliminare connessioni, set di dati o batch in Customer Journey Analytics o Adobe Experience Platform, considera quanto segue:

| Azione | Risultato |
| --- | --- |
| Eliminare una connessione in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare un set di dati in [!UICONTROL Adobe Experience Platform] (AEP) | L’eliminazione di un set di dati in AEP interrompe il flusso di dati da tale set di dati a qualsiasi connessione che lo include. Eventuali dati provenienti da tale set di dati non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Eliminare un set di dati in [!UICONTROL Customer Journey Analytics] | Al momento non è possibile eliminare un set di dati all’interno di una connessione salvata. Occorre cancellare l’intera connessione e ricominciare da capo. Tuttavia, puoi eliminare un set di dati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform]) | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni [!UICONTROL Customer Journey Analytics] che lo contengono. [!UICONTROL Customer Journey Analytics] viene informato dei batch eliminati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante l’acquisizione** in [!UICONTROL Customer Journey Analytics] | Se nel set di dati è presente un solo batch, in [!UICONTROL Customer Journey Analytics] non verranno visualizzati dati o dati parziale da tale batch. L’acquisizione verrà annullata e verrà ripristinato lo stato precedente. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell’eliminazione del set di dati, i dati di tali 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Eliminate i set di dati di ricerca in [!UICONTROL Adobe Experience Platform] | Mentre l’eliminazione dei set di dati è possibile per altri connettori di origine, al momento non è supportata per [Connettore origine classificazioni di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=it). Se elimini un set di dati per errore, contatta l’Assistenza clienti Adobe. |
