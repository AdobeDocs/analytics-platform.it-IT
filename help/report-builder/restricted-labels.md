---
title: Cosa sono le etichette per limitazioni in Report Builder
description: Descrive le etichette per limitazioni in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# Etichette per limitazioni in Report Builder

In generale, Customer Journey Analytics eredita tutte le impostazioni relative alla privacy da Adobe Experience Platform. L’integrazione tra CJA e Governance dei dati di Adobe Experience Platform consente di etichettare i dati CJA sensibili e di applicare i criteri di privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di CJA. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili. Per informazioni sui set di dati, consulta [Panoramica sui set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=it)

Inoltre, quando i dati vengono esportati da CJA (tramite reporting, esportazione, API ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti CJA possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

Per ulteriori informazioni, consulta [Customer Journey Analytics e governance dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=it)

## Visualizzazione dei dati con limitazioni in Report Builder

In CJA vengono visualizzati due criteri definiti da Adobe che influiscono su reporting, download e condivisione:

* Criterio Enforce Analytics (Applica analisi)
* Criterio Enforce Download (Applica download)

I componenti interessati da questi criteri sono visualizzati in grigio. Quando passi il cursore su un componente a cui è stato applicato un criterio, viene visualizzata una nota per indicare che **a questo campo sono stati applicati criteri che impediscono l’utilizzo dei dati.** Per ulteriori informazioni consulta [Etichette e criteri](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=it).

![](assets/rb-restricted-label.png)

## Aggiornare i rapporti contenenti dati con limitazioni

Nei casi in cui un utente abbia creato in Report Builder un rapporto con elementi dati a cui sono state successivamente applicate delle limitazioni, quando il rapporto viene aggiornato viene visualizzato un messaggio di errore.

![](assets/error-restricted-data.png)
