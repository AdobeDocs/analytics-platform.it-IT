---
title: Metodi alternativi per l'aggiornamento a Customer Journey Analytics
description: Scopri i metodi alternativi per l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 9%

---

# Alternativa di aggiornamento: invia il livello dati a Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Inviare il livello di dati ad Adobe"
>abstract="Invece di inviare dati tramite un oggetto XDM, puoi inviare l’intero livello di dati ad Adobe tramite l’oggetto dati.<br><br>Questa opzione consente di risparmiare tempo di implementazione consentendo di mappare il livello dati su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, questa mappatura è un lavoro molto lungo, perché ci sarà una quantità significativa di dati che Adobe non è in grado di interpretare facilmente. Questa opzione introduce anche una complessità aggiuntiva nel tempo, perché qualsiasi campo aggiunto ai dati in un secondo momento deve essere mappato a XDM nello stream di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Inviare il livello dati ad Adobe"
>abstract="Configura l’implementazione per inviare i dati ad Adobe al momento desiderato e configura il payload JSON affinché sia l’intero livello di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Assegnare ogni elemento del livello dati a XDM"
>abstract="Mappa ogni elemento del livello dati sul campo XDM desiderato. Tutti gli elementi del livello dati che non sono mappati a un campo XDM vengono eliminati in modo permanente, in quanto Adobe non sa dove o come memorizzare tali dati."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Durante l&#39;aggiornamento a Customer Journey Analytics, Adobe [consiglia una nuova implementazione di Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione.

Puoi inviare l’intero livello dati a Customer Journey Analytics invece di raccogliere i dati con l’oggetto XDM. Tuttavia, questa alternativa introduce una complessità aggiuntiva nel tempo.

## Vantaggi e svantaggi

Questo metodo si esclude a vicenda con [utilizzando la logica di raccolta dati di AppMeasurement con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), poiché entrambi i metodi eseguono la stessa attività.

Di seguito sono riportati i vantaggi e gli svantaggi dell&#39;utilizzo di questa alternativa di aggiornamento:

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza la logica del livello dati corrente**: questo metodo utilizza la logica del livello dati corrente al posto di un&#39;implementazione convenzionale di Web SDK. Anche se questo approccio richiede una certa configurazione, non richiede un’implementazione completamente nuova da zero e non richiede il popolamento di elementi di dati o regole di tag. Consente di mappare i dati dal livello dati a XDM, anziché popolare un oggetto XDM da zero.</li></ul> | <ul><li>**È necessaria la mappatura per inviare dati a Platform**: quando l&#39;organizzazione è pronta per utilizzare Customer Journey Analytics, è necessario inviare dati a un set di dati in Adobe Experience Platform. <p>Poiché questa opzione consente di inserire l’intero livello dati lato client nell’oggetto dati e inviarlo ad Adobe, si ottiene una quantità significativa di dati che Adobe non è in grado di interpretare facilmente. Per consentire ad Adobe di interpretare i dati, devi utilizzare la mappatura dello stream di dati per mappare ogni singolo campo al campo XDM desiderato.</p></li><li>**Implementazione rigida**: l&#39;implementazione è vincolata a ciò che fornisce il livello dati al momento dell&#39;invio dell&#39;hit. Questo potrebbe essere accettabile per le organizzazioni con esigenze di dati di base, ma la maggior parte delle organizzazioni dovrebbe evitare questo tipo di implementazione rigida a favore di un’implementazione più flessibile che consenta di popolare gli elementi di dati.</li><li>**Le modifiche future sono più difficili da implementare**: qualsiasi campo aggiunto ai dati in un secondo momento deve essere mappato a XDM nello stream di dati.</li></ul> |

{style="table-layout:auto"}

## Passaggi di base

I passaggi di base per inviare l’intero livello dati a Customer Journey Analytics sono i seguenti:

1. Configura l’implementazione per inviare i dati ad Adobe al momento desiderato e configura il payload JSON affinché sia l’intero livello di dati.

1. Mappa ogni elemento del livello dati sul campo XDM desiderato.

   Tutti gli elementi del livello dati che non sono mappati a un campo XDM vengono eliminati in modo permanente, in quanto Adobe non sa dove o come memorizzare tali dati.
