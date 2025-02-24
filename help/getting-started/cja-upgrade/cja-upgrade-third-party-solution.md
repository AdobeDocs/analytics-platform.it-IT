---
title: Aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics
description: Scopri come effettuare l’aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: d2d945724e7972bd4a29fa13291577bb76288229
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 12%

---

# Aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Un prodotto non Adobe Analytics"
>abstract="Implementazione che raccoglie dati per un prodotto diverso da Adobe Analytics, ad esempio Google Analytics. Selezionando questa opzione nel questionario verranno disattivate diverse opzioni che non sono applicabili quando si esegue l’aggiornamento a Customer Journey Analytics da un prodotto non Adobe Analytics."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;[elenco di controllo per l&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Il processo consigliato di aggiornamento da una soluzione di analisi diversa da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics. Insieme al Web SDK, Adobe consiglia inoltre di acquisire in Adobe Experience Platform i dati storici dalla soluzione di analisi di terze parti.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilizza il seguente procedimento per passare a Customer Journey Analytics da una soluzione di analisi di terze parti, come Google Analytics:

1. Segui i [passaggi di aggiornamento consigliati dettagliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Questi passaggi sono destinati alle organizzazioni che eseguono l&#39;aggiornamento da Adobe Analytics. Quando segui questi passaggi, comprendi quanto segue:

   * Devi creare un flusso di dati.

   * Non è possibile eseguire la migrazione di progetti e componenti da una soluzione non Adobe Analytics.

   * A seconda della soluzione di analisi in uso, è possibile che sia disponibile un connettore di origine per l’acquisizione dei dati storici. Per ulteriori informazioni, consulta [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) in [Panoramica dei connettori Source](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) nella documentazione di Experience Platform.


Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

