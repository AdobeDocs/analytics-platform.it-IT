---
title: Aggiungere dati della metrica quantistica a Customer Journey Analytics
description: Utilizza la metrica quantistica per la raccolta di dati su percorsi di utenti e comportamenti, quindi alimenta CJA da quei dati raccolti per ottenere informazioni più approfondite.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Aggiungere dati della metrica quantistica a Customer Journey Analytics

>[!IMPORTANT]
>
>Il connettore di origine della metrica quantistica non è ancora disponibile in questo momento.

CJA consente di controllare in fase di report i dati QM, l’analisi sequenziale dei dati, l’attribuzione avanzata e altre funzioni avanzate di reporting.  QM può essere inviato ad AEP utilizzando il connettore di origine QM o l’estensione tag Quantum Metrics.

## Passaggio 1: creare un connettore di origine della metrica quantistica

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a [!UICONTROL Experience Platform] > [!UICONTROL Connections] > [!UICONTROL Sources].
1. Aggiungi il connettore di origine della metrica quantistica e segui le istruzioni per il completamento.

Per ulteriori informazioni, vedere [Connettori di origine Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home).

## Passaggio 2: creare una connessione in Customer Journey Analytics

La creazione di un connettore di origine per i dati della metrica quantistica crea automaticamente un set di dati in Adobe Experience Platform. Aggiungi questo set di dati a una [connessione](/help/connections/overview.md) nuova o esistente in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Connections]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.
1. Assegna un nome alla connessione e aggiungi il set di dati della metrica quantistica alla connessione.
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>Anche se è possibile aggiungere dati della metrica quantistica alla stessa connessione degli altri dati di Customer Journey Analytics, tali dati non possono essere uniti senza un ID persona comune tra i due set di dati. Per ottenere questo comportamento, Adobe consiglia di utilizzare l&#39;estensione [Tag](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/analytics/quantum-metric) invece del connettore di origine.

## Passaggio 3: creare una visualizzazione dati in Customer Journey Analytics

Crea una [visualizzazione dati](/help/data-views/data-views.md) per configurare le impostazioni delle dimensioni e delle metriche.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Data views]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.
1. Seleziona la visualizzazione dati desiderata o crea una visualizzazione dati.
1. Individua le dimensioni e le metriche della metrica quantistica desiderate nell’elenco dei campi dello schema a destra e trascinale nell’area delle dimensioni e delle metriche al centro.
1. Utilizza il riquadro a destra per configurare ciascuna dimensione e metrica desiderata.

## Passaggio 4: iniziare a generare rapporti e analizzare in Customer Journey Analytics

Ora che i dati sono disponibili in Customer Journey Analytics, puoi iniziare a generare rapporti sui dati.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Trascina una dimensione o metrica della metrica quantistica desiderata nell’area di lavoro di Workspace per analizzare i dati.
