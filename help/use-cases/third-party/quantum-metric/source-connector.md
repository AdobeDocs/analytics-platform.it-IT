---
title: Aggiungere dati della metrica quantistica a Customer Journey Analytics
description: Utilizza la metrica quantistica per la raccolta di dati su percorsi di utenti e comportamenti, quindi alimenta CJA da quei dati raccolti per ottenere informazioni più approfondite.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 942cc774812d4a6b3b7f45df837ff9277e8f9b46
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 4%

---

# Aggiungere dati della metrica quantistica a Customer Journey Analytics

>[!IMPORTANT]
>
>Il connettore di origine della metrica quantistica non è ancora disponibile in questo momento.

CJA consente di controllare in fase di report i dati QM, l’analisi sequenziale dei dati, l’attribuzione avanzata e altre funzioni avanzate di reporting.  QM può essere inviato ad AEP utilizzando il connettore di origine QM o l’estensione tag Quantum Metrics.

## Passaggio 1: creare un connettore di origine della metrica quantistica

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a [!UICONTROL Experience Platform] > [!UICONTROL Connessioni] > [!UICONTROL Origini].
1. Aggiungi il connettore di origine della metrica quantistica e segui le istruzioni per il completamento.

Per ulteriori informazioni, vedere [Connettori di origine Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home).

## Passaggio 2: creare una connessione in Customer Journey Analytics

La creazione di un connettore di origine per i dati della metrica quantistica crea automaticamente un set di dati in Adobe Experience Platform. Aggiungi questo set di dati a una [connessione](/help/connections/overview.md) nuova o esistente in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Connessioni]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.
1. Assegna un nome alla connessione e aggiungi il set di dati della metrica quantistica alla connessione.
1. Fai clic su **[!UICONTROL Salva]**.

>[!NOTE]
>Anche se è possibile aggiungere dati della metrica quantistica alla stessa connessione degli altri dati di Customer Journey Analytics, tali dati non possono essere uniti senza un ID persona comune tra i due set di dati. Per ottenere questo comportamento, Adobe consiglia di utilizzare l&#39;estensione [Tag](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/analytics/quantum-metric) invece del connettore di origine.

## Passaggio 3: creare una visualizzazione dati in Customer Journey Analytics

Crea una [visualizzazione dati](/help/data-views/data-views.md) per configurare le impostazioni delle dimensioni e delle metriche.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.
1. Seleziona la visualizzazione dati desiderata o crea una visualizzazione dati.
1. Individua le dimensioni e le metriche della metrica quantistica desiderate nell’elenco dei campi dello schema a destra e trascinale nell’area delle dimensioni e delle metriche al centro.
1. Utilizza il riquadro a destra per configurare ciascuna dimensione e metrica desiderata.

## Passaggio 4: iniziare a generare rapporti e analizzare in Customer Journey Analytics

Ora che i dati sono disponibili in Customer Journey Analytics, puoi iniziare a generare rapporti sui dati.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Trascina una dimensione o metrica della metrica quantistica desiderata nell’area di lavoro di Workspace per analizzare i dati.
