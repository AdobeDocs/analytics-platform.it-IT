---
description: Informazioni su come utilizzare gli avvisi per consentire un controllo granulare sulle notifiche e un’integrazione con il rilevamento di anomalie.
title: Panoramica sugli avvisi
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# Panoramica sugli avvisi

Gli avvisi in Customer Journey Analytics ti consentono di ricevere notifiche in base a percentuali di modifica o a punti dati specifici.

A seconda del pacchetto di Customer Journey Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come *Avvisi intelligenti*) forniscono controlli granulari che si integrano con [Rilevamento anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandoli quando sono più necessari.

* Visualizzare in anteprima la frequenza di attivazione di un avviso.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Crea avvisi *in pila* che acquisiscono più metriche in un singolo avviso.
* Creare avvisi in base a:
   * Le anomalie nelle metriche esistenti sono superiori o inferiori ai valori di soglia previsti.

     [Il rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) genera un valore previsto più un limite superiore e inferiore utilizzando i dati storici. Se il valore della metrica effettiva supera il limite superiore o inferiore al limite inferiore definito come valore di soglia, tale evento viene considerato un’anomalia al livello di affidabilità della soglia e attiva l’avviso. Una soglia più elevata (ad esempio, 99% o 99,9%) implica una banda più ampia e comporta un minor numero di avvisi causati da anomalie più estreme. Una soglia più bassa (ad esempio, 90%) implica una banda più stretta, il che si traduce in un maggior numero di avvisi causati da anomalie meno estreme.
   * Modifiche nelle metriche di una percentuale specifica.
   * Metriche superiori, inferiori o uguali a un valore specifico. (disponibile solo per i clienti Adobe Analytics con un pacchetto Select, Prime o Ultimate)

Questa [esercitazione video](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fornisce una panoramica di base degli avvisi.



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
