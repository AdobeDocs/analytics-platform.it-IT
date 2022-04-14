---
title: Inserire dati di Marketo Engage in AEP e generare rapporti in CJA
description: Scopri come inserire dati di Marketo Engage in CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: ad8e3c18dbb73a064662a4543cb0e553cd52cec3
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---

# Inserire dati di Marketo Engage in AEP e generare rapporti in CJA

Puoi sfruttare i set di dati di Marketo Engage disponibili di recente in Adobe Experience Platform (AEP) per fornire preziose soluzioni di analisi e reporting agli esperti di marketing B2B. Quindi genera rapporti su questi set di dati in Customer Journey Analytics (CJA).

## Passaggio 1: Mappatura dei campi dati sorgente Marketo sui relativi target XDM

Mappa la [Persone](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) e [Attività](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) oggetti ai rispettivi campi di destinazione dello schema XDM.

## Passaggio 2: Inserire dati Marketo in AEP

Utilizza la [Connettore Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) portare i dati da Marketo ad Experience Platform e tenerli aggiornati utilizzando le applicazioni connesse a Platform.

## Passaggio 3: Configurare una connessione a questo set di dati in CJA

Per creare rapporti sui set di dati di Experience Platform, è innanzitutto necessario stabilire una connessione tra i set di dati in Experience Platform e CJA. Per ulteriori informazioni, consulta [Creare una connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it).

## Passaggio 4: Creare una o più visualizzazioni dati

A [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico del Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, in questo caso le metriche e le dimensioni specifiche di Marketo. Specifica inoltre da quali colonne le dimensioni e le metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione al reporting in Analysis Workspace.

## Passaggio 5: Report in Analysis Workspace

Un caso d’uso che potresti esplorare è: Quante visite di siti web da parte dei lead abbiamo avuto nell&#39;aprile-giugno 2020?

1. Apri [Area di lavoro di Analytics](/help/analysis-workspace/home.md) e crea un nuovo progetto.
I clienti con CDP B2B/B2P possono eseguire analisi in stile B2C in CJA. Gli oggetti B2B non sono ancora disponibili.

1. Crea un [filter](/help/components/filters/create-filters.md) per le visualizzazioni di pagina web come segue - Tipo evento = web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. Nella tabella a forma libera, seleziona il filtro creato, Visualizzazioni pagina web, quindi inserisci l’intervallo di date del mese. In questo modo è possibile visualizzare le visite alle pagine Web in base ai lead ogni mese:

   ![](assets/marketo-freeform.png)

1. Oppure estraete le seguenti dimensioni: Chiave persona o indirizzo e-mail di lavoro. In questo modo le visite alla pagina web di ciascun lead:

   ![](assets/marketo-freeform2.png)
