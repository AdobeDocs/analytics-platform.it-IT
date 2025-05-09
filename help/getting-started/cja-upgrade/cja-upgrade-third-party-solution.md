---
title: Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
description: Scopri come aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 54%

---

# Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Prodotto diverso da Adobe Analytics"
>abstract="Un’ implementazione che raccoglie dati per un prodotto diverso da Adobe Analytics, ad esempio Google Analytics. Selezionando questa opzione nella guida aggiornata verranno disattivate diverse opzioni che non vengono applicate durante l’aggiornamento a Customer Journey Analytics da un prodotto diverso da Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Il processo consigliato di aggiornamento da una soluzione di analisi diversa da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics. Insieme a Web SDK, Adobe consiglia inoltre di acquisire in Adobe Experience Platform i dati storici dalla soluzione di analisi di terze parti.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilizza il seguente procedimento per passare a Customer Journey Analytics da una soluzione di analisi di terze parti, come Google Analytics:

1. Segui i [passaggi di aggiornamento consigliati dettagliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Questi passaggi sono destinati alle organizzazioni che eseguono l&#39;aggiornamento da Adobe Analytics. Quando segui questi passaggi, comprendi quanto segue:

   * Devi creare un flusso di dati.

   * Non è possibile eseguire la migrazione di progetti e componenti da una soluzione non Adobe Analytics.

   * A seconda della soluzione di analisi in uso, è possibile che sia disponibile un connettore di origine per l’acquisizione dei dati storici. Per ulteriori informazioni, consulta [Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home#analytics) in [Panoramica dei connettori Source](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home) nella documentazione di Experience Platform.


Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

