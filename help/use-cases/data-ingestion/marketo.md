---
title: Rapporto sui dati Marketo Engage
description: Scopri come creare rapporti sui dati di Marketo Engage in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 51%

---

# Rapporto sui dati Marketo Engage

Puoi sfruttare i nuovi set di dati di Marketo Engage in Adobe Experience Platform (Adobe Experience Platform) per fornire preziose soluzioni di analisi e reporting agli esperti di marketing B2B. Quindi crea rapporti su questi set di dati in Adobe Customer Journey Analytics.

## Passaggio 1: mappare i campi dati di origine Marketo sui relativi campi di destinazione XDM

Mappa gli oggetti [Persons](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=it#persons) (Persone) e [Activities](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=it#activities) (Attività) ai rispettivi campi di destinazione dello schema XDM.

## Passaggio 2: inserire i dati Marketo in Adobe Experience Platform

Utilizza il [connettore Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=it) per portare i dati da Marketo ad Experience Platform e tenerli aggiornati utilizzando le applicazioni connesse a Platform.

## Passaggio 3: configurare una connessione al set di dati in Customer Journey Analytics

Per creare rapporti sui set di dati di Experience Platform devi prima stabilire una connessione tra i set di dati in Experience Platform e Customer Journey Analytics. Per ulteriori informazioni [Creare o modificare una connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it).

## Passaggio 4: creare una o più visualizzazioni dati

Una [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace; in questo caso, si tratta delle metriche e dimensioni specifiche di Marketo. Inoltre, specifica le colonne dalle quali le dimensioni e le metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

## Passaggio 5: generare report in Analysis Workspace

Un caso d’uso interessante è, ad esempio, la capacità di rispondere a quesiti quali: quante visite alle pagine web da parte dei lead abbiamo avuto nel periodo aprile-giugno 2020?

1. Apri [Analytics Workspace](/help/analysis-workspace/home.md) e crea un nuovo progetto.
I clienti con CDP B2B/B2P possono eseguire analisi in stile B2C in Customer Journey Analytics. Gli oggetti B2B non sono ancora disponibili.

1. Crea un [segmento](/help/components/segments/seg-create.md) per le visualizzazioni di pagine Web come segue - Tipo evento = web.webpagedetails.pageViews :

   ![Finestra di definizione che mostra il tipo di evento ed evento](../assets/marketo-filter.png)

1. Estrai il segmento creato nella tabella a forma libera, visualizzazioni pagina web, quindi inserisci l’intervallo di date Mese. In questo modo puoi vedere le visite alle pagine web in base da parte dei lead per ognuno dei mesi specificati:

   ![Tabella a forma libera che mostra gli eventi per mese.](../assets/marketo-freeform.png)

1. Oppure, puoi ottenere le seguenti dimensioni: Person Key (Chiave persona) o Work Email Address (Indirizzo e-mail di lavoro). In questo modo potrai vedere le visite alle pagine web per ciascun lead:

   ![Tabella a forma libera con eventi e workEmail.Address e visualizzazioni di pagine Web.](../assets/marketo-freeform2.png)
