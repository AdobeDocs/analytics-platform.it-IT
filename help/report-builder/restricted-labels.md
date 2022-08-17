---
title: Cosa sono le etichette limitate nel Report Builder
description: Descrive le etichette con restrizioni nel Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Etichette limitate nel Report Builder

In genere le impostazioni relative alla governance dei dati nel Customer Journey Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra CJA e la governance dei dati di Adobe Experience Platform consente di etichettare i dati sensibili di CJA e di applicare le politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di CJA. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili. Per informazioni sui set di dati, consulta [Panoramica dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

Inoltre, quando i dati vengono esportati da CJA (tramite reporting, esportazione, API ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti CJA possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

Per ulteriori informazioni, consulta [Customer Journey Analytics e governance dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Visualizzazione dei dati con restrizioni in Report Builder

In CJA vengono visualizzati due criteri definiti in Adobe che influiscono sul reporting, download e condivisione:

* Applica criteri di Analytics
* Applica criterio di download

I componenti interessati da queste policy sono disattivati. Quando passi il puntatore del mouse su un componente a cui è stato applicato un criterio, viene visualizzata una nota per indicare quanto segue: **In questo campo sono stati applicati criteri che ne vietano l’utilizzo.** Per ulteriori informazioni consulta [Etichette e politiche](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## Aggiornare i rapporti contenenti dati limitati

Nei casi in cui un utente abbia creato un rapporto di Report Builder con elementi dati successivamente soggetti a restrizioni, quando il rapporto viene aggiornato viene visualizzato un messaggio di errore.

![](assets/error-restricted-data.png)
