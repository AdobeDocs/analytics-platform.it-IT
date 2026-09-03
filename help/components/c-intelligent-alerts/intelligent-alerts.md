---
description: Informazioni su come utilizzare gli avvisi per consentire un controllo granulare sulle notifiche e un’integrazione con il rilevamento di anomalie.
title: Panoramica sugli avvisi
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
TQID: https://experienceleague.adobe.com/kXRxlgfo9-F6KyXQ590--TZOZcVqvHkZZGS6alcAC0E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: aff2ef09-fc60-4018-9197-e2befd623064
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 57%

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

Questa [esercitazione video](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fornisce una panoramica di base degli avvisi.



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
