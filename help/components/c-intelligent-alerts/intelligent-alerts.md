---
description: Gli avvisi consentono un controllo granulare sulle notifiche e un’integrazione con il rilevamento delle anomalie.
title: Panoramica sugli avvisi
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: ht
source-wordcount: '352'
ht-degree: 100%

---

# Panoramica sugli avvisi

Gli avvisi in Customer Journey Analytics ti consentono di ricevere notifiche in base a percentuali di modifica o a punti dati specifici.

A seconda del pacchetto di Customer Journey Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come “Avvisi intelligenti”) forniscono controlli granulari che si integrano con il [Rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandosi quando sono più necessari.

Gli avvisi permettono di:

* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso
* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore) (Disponibile solo per i clienti Customer Journey Analytics con un pacchetto Select, Prime o Ultimate)

Il seguente video tutorial fornisce una panoramica di base degli avvisi: [Avvisi](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Informazioni sulle differenze tra gli avvisi

Il processo di utilizzo degli avvisi in Customer Journey Analytics è quasi identico a quello degli avvisi in Adobe Analytics. Tuttavia, esistono differenze importanti.

Per ulteriori informazioni, consulta [Confronto delle funzioni degli avvisi: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Ricerca delle anomalie per gli avvisi

>[!NOTE]
>
>L’utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Customer Journey Analytics Select, Prime o Ultimate.

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, consulta [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creare avvisi

Per informazioni sulla creazione di avvisi in Customer Journey Analytics, consulta [Creare avvisi](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. Per gli avvisi, Adobe consiglia di utilizzare dati senza marca temporale.

## Gestire gli avvisi

Puoi gestire gli avvisi esistenti in Gestione avvisi. Puoi eseguire varie attività di gestione degli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

Per ulteriori informazioni su come gestire gli avvisi esistenti in Customer Journey Analytics, consulta [Gestire gli avvisi](/help/components/c-intelligent-alerts/alert-manager.md).
