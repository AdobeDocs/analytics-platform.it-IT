---
title: Etichette Limitate In Report Builder
description: Scopri le etichette per limitazioni in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 42%

---

# Etichette per limitazioni in Report Builder

In genere, le impostazioni relative alla governance dei dati in Customer Journey Analytics vengono ereditate da Experience Platform. L’integrazione tra Customer Journey Analytics e Governance dei dati di Experience Platform consente l’etichettatura dei dati Customer Journey Analytics sensibili e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Queste etichette interrompono o avvisano gli utenti che creano metriche e dimensioni da campi sensibili. Per informazioni sui set di dati, consulta [Panoramica sui set di dati](https://experienceleague.adobe.com/it/docs/experience-platform/catalog/datasets/overview)

Inoltre, quando i dati vengono esportati da Customer Journey Analytics (tramite reporting, esportazione, API ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un report contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti di Customer Journey Analytics possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

Per ulteriori informazioni, consulta [Customer Journey Analytics e governance dei dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Visualizza dati con restrizioni

In Customer Journey Analytics vengono visualizzati due criteri definiti da Adobe che influiscono su reporting, download e condivisione:

* Criterio Enforce Analytics (Applica analisi)
* Criterio Enforce Download (Applica download)

I componenti soggetti a questi criteri sono disattivati e dispongono di un&#39;icona ![InfoOutline](/help/assets/icons/InfoOutline.svg). Quando passi il cursore sull&#39;icona delle informazioni, viene visualizzata una nota per indicare che a questo campo sono stati applicati **[!UICONTROL criteri che impediscono l&#39;utilizzo di questi dati]**.

Per ulteriori informazioni, vedere [Etichette e criteri](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![Nota del criterio che indica l&#39;utilizzo non consentito dei dati.](assets/restricted-label.png){zoomable="yes"}


## Aggiornare i rapporti che contengono dati con restrizioni

Nei casi in cui un utente abbia creato in Report Builder un rapporto con elementi dati a cui sono state successivamente applicate delle limitazioni, quando il rapporto viene aggiornato viene visualizzato un messaggio di errore.

![Messaggio di errore visualizzato dopo che gli elementi dati saranno stati sottoposti a restrizioni in un secondo momento.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
