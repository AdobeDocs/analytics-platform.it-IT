---
title: Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
description: Scopri come aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '238'
ht-degree: 100%

---

# Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Prodotto di analisi non Adobe"
>abstract="Un’ implementazione che raccoglie dati per un prodotto di analisi di terze parti, ad esempio Google Analytics. Selezionando questa opzione verranno disabilitate diverse opzioni della guida all’aggiornamento che non vengono applicate durante l’aggiornamento a Customer Journey Analytics da un prodotto di analisi diverso da Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Il processo consigliato per l’aggiornamento da una soluzione di analisi diversa da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics. Insieme a Web SDK, Adobe consiglia inoltre di acquisire in Adobe Experience Platform i dati storici dalla soluzione di analisi di terze parti.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilizza il seguente procedimento per passare a Customer Journey Analytics da una soluzione di analisi di terze parti, come Google Analytics:

1. Segui i [passaggi di aggiornamento dettagliati consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Questi passaggi sono destinati alle organizzazioni che eseguono l’aggiornamento da Adobe Analytics. Quando segui questi passaggi, tieni presente quanto segue:

   * È necessario creare uno stream di dati.

   * Non è possibile eseguire la migrazione di progetti e componenti da una soluzione di analisi diversa da Adobe.

   * A seconda della soluzione di analisi in uso, è possibile che sia disponibile un connettore di origine per l’acquisizione dei dati storici. Per ulteriori informazioni, consulta [Analisi](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home#analytics) in [Panoramica dei connettori di origine](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home) nella documentazione di Experience Platform.


Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il tuo rappresentante Adobe.

