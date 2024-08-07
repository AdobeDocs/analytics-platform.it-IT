---
title: Panoramica sulle annotazioni
description: Come utilizzare le annotazioni in Workspace.
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---

# Panoramica sulle annotazioni

Le annotazioni consentono di comunicare in modo efficace dettagli sui dati contestuali a beneficio degli utenti in tutta l’organizzazione. Consentono di collegare eventi calendario a dimensioni o metriche specifiche. È possibile aggiungere a una data o un intervallo di date annotazioni relative a problemi noti, festività, avvii di campagne, ecc. Puoi quindi visualizzare gli eventi in modo grafico e vedere se campagne o altri eventi hanno influenzato il traffico del sito, l’utilizzo di app mobile, i ricavi o su qualsiasi altra metrica.

Ad esempio, supponiamo che tu condivida dei progetti con la tua organizzazione. Se si è verificato un picco importante nel traffico a seguito di una campagna di marketing, è possibile aggiungere un’annotazione “Data di lancio della campagna” e impostarla per l’intera visualizzazione dati. Quando altri utenti visualizzano i set di dati che includono tale data, vedono l’annotazione all’interno dei loro progetti, insieme ai relativi dati.

![Grafico a linee con annotazione evidenziata.](assets/multi-day.png)

Aspetti da considerare:

* Le annotazioni possono essere associate a una singola data o a un intervallo di date.

* Possono essere applicate all’intero set di dati oppure a metriche, dimensioni o filtri specifici.

* Possono essere applicate al progetto in cui sono state create (impostazione predefinita) oppure a tutti i progetti.

* Possono essere applicate alla visualizzazione dati in cui sono state create (per impostazione predefinita) oppure a tutte le visualizzazioni dati.

## Autorizzazioni

Per impostazione predefinita, solo gli amministratori possono creare annotazioni. Le autorizzazioni degli utenti per visualizzare le annotazioni sono analoghe a quelle degli altri componenti di Analytics (come filtri, metriche calcolate ecc.).

Tuttavia, gli amministratori possono assegnare agli utenti l’autorizzazione [!UICONTROL Annotation Creation] (Analytics Tools) tramite [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=it).

## Attivare o disattivare le annotazioni {#annotations-on-off}

Le annotazioni possono essere attivate o disattivate a diversi livelli:

* A livello di visualizzazione: Impostazioni [!UICONTROL Visualization] > [!UICONTROL Show annotations]

* A livello di progetto: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* A livello utente: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![Finestra di dialogo delle impostazioni di visualizzazione con Mostra annotazioni evidenziate](assets/show-ann.png)

![Preferenze utente che evidenziano Mostra annotazioni.](assets/show-ann2.png)
