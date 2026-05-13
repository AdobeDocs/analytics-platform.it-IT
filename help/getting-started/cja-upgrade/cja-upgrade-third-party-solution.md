---
title: Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
description: Scopri come aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
TQID: https://experienceleague.adobe.com/xvxs9sNeqtLOnCQ9G9BvDVeJ-hAxFc-Clq4b2T5-vsU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# Aggiornare da una soluzione di analisi di terze parti a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Prodotto diverso da Adobe Analytics"
>abstract="Un’ implementazione che raccoglie dati per un prodotto diverso da Adobe Analytics, ad esempio Google Analytics. Selezionando questa opzione verranno disabilitate diverse opzioni della guida all’aggiornamento che non vengono applicate durante l’aggiornamento a Customer Journey Analytics da un prodotto di analisi diverso da Adobe."

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

