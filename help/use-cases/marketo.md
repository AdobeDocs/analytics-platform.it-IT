---
title: Acquisire i dati Marketo Engage in AEP e generare rapporti in CJA
description: Scopri come inserire dati Marketo Engage in CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: ad8e3c18dbb73a064662a4543cb0e553cd52cec3
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# Acquisire i dati Marketo Engage in AEP e generare rapporti in CJA

Puoi sfruttare i nuovi set di dati di Marketo Engage in Adobe Experience Platform (AEP) per fornire preziose soluzioni di analisi e reporting agli esperti di marketing B2B. Quindi, in Customer Journey Analytics (CJA), puoi generare rapporti su tali set di dati.

## Passaggio 1: mappare i campi dati di origine Marketo sui relativi campi di destinazione XDM

Mappa gli oggetti [Persons](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=it#persons) (Persone) e [Activities](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=it#activities) (Attività) ai rispettivi campi di destinazione dello schema XDM.

## Passaggio 2: inserire i dati Marketo in AEP

Utilizza il [connettore Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=it) per portare i dati da Marketo ad Experience Platform e tenerli aggiornati utilizzando le applicazioni connesse a Platform.

## Passaggio 3: configurare una connessione al set di dati in CJA

Per generare rapporti sui set di dati occorre innanzitutto stabilire una connessione tra i set di dati in Experience Platform e CJA. Per ulteriori informazioni, consulta [Creare una connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it).

## Passaggio 4: creare una o più visualizzazioni dati

Una [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace; in questo caso, si tratta delle metriche e dimensioni specifiche di Marketo. Inoltre, specifica le colonne dalle quali le dimensioni e le metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

## Passaggio 5: generare report in Analysis Workspace

Un caso d’uso interessante è, ad esempio, la capacità di rispondere a quesiti quali: quante visite alle pagine web da parte dei lead abbiamo avuto nel periodo aprile-giugno 2020?

1. Apri [Analytics Workspace](/help/analysis-workspace/home.md) e crea un nuovo progetto.
I clienti con CDP B2B/B2P possono eseguire analisi in stile B2C in CJA. Gli oggetti B2B non sono ancora disponibili.

1. Crea un [filtro](/help/components/filters/create-filters.md) per le visualizzazioni di pagine web come segue - Tipo evento = web.webpagedetails.pageViews:

   ![](assets/marketo-filter.png)

1. Nella tabella a forma libera, seleziona il filtro appena creato (Visualizzazioni pagine web), quindi inserisci l’intervallo di date relativo ai mesi. In questo modo puoi vedere le visite alle pagine web in base da parte dei lead per ognuno dei mesi specificati:

   ![](assets/marketo-freeform.png)

1. Oppure, puoi ottenere le seguenti dimensioni: Person Key (Chiave persona) o Work Email Address (Indirizzo e-mail di lavoro). In questo modo potrai vedere le visite alle pagine web per ciascun lead:

   ![](assets/marketo-freeform2.png)
