---
description: Gli avvisi consentono un controllo granulare sulle notifiche e un’integrazione con il rilevamento delle anomalie.
title: Panoramica degli avvisi
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 27%

---

# Panoramica degli avvisi

Gli avvisi nel Customer Journey Analytics ti consentono di ricevere notifiche in base a percentuali modificate o a punti dati specifici.

A seconda del pacchetto di Customer Journey Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come &quot;Avvisi intelligenti&quot;) forniscono controlli granulari che si integrano con [Rilevamento anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandosi quando sono più necessari.

Gli avvisi consentono di:

* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso
* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore) (Disponibile solo per i clienti del Customer Journey Analytics con un pacchetto Select, Prime o Ultimate)

Il seguente tutorial video fornisce una panoramica di base degli avvisi: [Avvisi](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Comprendere le differenze tra gli avvisi e il Customer Journey Analytics di Adobe Analytics

La procedura di utilizzo degli avvisi in Customer Journey Analytics è quasi identica a quella di utilizzo degli avvisi in Adobe Analytics. Tuttavia, ci sono importanti differenze.

Per ulteriori informazioni, vedere [Confronto delle funzionalità degli avvisi: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Ricerca delle anomalie per gli avvisi

>[!NOTE]
>
>L&#39;utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Select di Customer Journey Analytics, Prime o Ultimate.

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, vedere [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creare avvisi

Per informazioni sulla creazione di avvisi nel Customer Journey Analytics, vedere [Creazione di avvisi](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. L’Adobe consiglia di utilizzare dati senza marca temporale per gli avvisi.

## Gestire gli avvisi

È possibile gestire gli avvisi esistenti nella Gestione avvisi. È possibile eseguire varie attività di gestione sugli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

Per ulteriori informazioni su come gestire gli avvisi esistenti nel Customer Journey Analytics, vedere [Gestione degli avvisi](/help/components/c-intelligent-alerts/alert-manager.md).

