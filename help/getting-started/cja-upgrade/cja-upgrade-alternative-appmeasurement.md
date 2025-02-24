---
title: Metodi alternativi per l'aggiornamento a Customer Journey Analytics
description: Scopri i metodi alternativi per l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 19%

---

# Alternativa di aggiornamento: utilizza la raccolta dati di AppMeasurement con Experience Platform Web SDK e Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Utilizzare la logica di AppMeasurement con il Web SDK"
>abstract="Invece di inviare dati tramite un oggetto XDM, invia tutte le variabili in formato AppMeasurement tramite l’oggetto dati.<br><br>Questa opzione consente di risparmiare tempo di implementazione consentendo di mappare la logica AppMeasurement su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, nel tempo introduce una complessità aggiuntiva, perché qualsiasi campo aggiunto in futuro deve essere mappato a XDM nello stream di dati."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;[elenco di controllo per l&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Durante l&#39;aggiornamento a Customer Journey Analytics, Adobe [consiglia una nuova implementazione di Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione.

È possibile utilizzare la logica di raccolta dati dell’estensione AppMeasurement o Analytics con il Web SDK per inviare dati a Platform e Customer Journey Analytics, invece di raccogliere dati con l’oggetto XDM. Tuttavia, questa alternativa introduce una complessità aggiuntiva nel tempo.

## Vantaggi e svantaggi

Questo metodo si esclude a vicenda con [l&#39;invio dell&#39;intero livello dati a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), perché entrambi i metodi eseguono la stessa attività. (Questo metodo è preferibile all’invio dell’intero livello dati ad Adobe. È più perfezionato perché prop ed eVar passano tutti attraverso i dati.__adobe.analytics._nome-variabile_.)

Considera i seguenti vantaggi e svantaggi dell’utilizzo di questa alternativa di aggiornamento:

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non confinato alla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Consente di mappare la logica AppMeasurement su XDM, anziché popolare un oggetto XDM da zero.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell’oggetto dati sia una voce nello strumento di mappatura del flusso di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li><li>**Introduce ulteriore complessità nel tempo**: qualsiasi campo aggiunto in futuro deve essere mappato a XDM nello stream di dati.<p>Ogni volta che un nuovo campo viene aggiunto all’implementazione, è possibile effettuare una delle seguenti operazioni:</p><ul><li>**Opzione 1:** compila una nuova eVar arbitraria o una nuova proprietà nell&#39;oggetto dati, quindi mappala al campo XDM desiderato.<p>Questo processo favorisce la coerenza per l’implementazione lato client, ma richiede la mappatura.</p></li><li>**Opzione 2:** Lascia l&#39;oggetto dati come implementazione legacy e inizia a popolare solo l&#39;oggetto XDM per tutti i nuovi campi.<p>Questo processo non richiede la mappatura, ma significa che alcune delle variabili si trovano solo in un oggetto dati, mentre altre variabili si trovano solo in un oggetto XDM. Ogni volta che hai bisogno di risolvere un problema di implementazione, devi passare a due posizioni. Assicurati che i flussi di lavoro interni siano adatti a questo scopo.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Passaggi di base

I passaggi di base per la migrazione di un’implementazione di Adobe Analytics (AppMeasurement o l’estensione Analytics) per utilizzare Web SDK per inviare dati a Customer Journey Analytics sono:

1. (Facoltativo) Esegui la migrazione dell’implementazione di Adobe Analytics per utilizzare Adobe Experience Platform Web SDK e iniziare a inviare dati ad Edge Network.

   Questo passaggio è facoltativo e consente di migrare l’implementazione Adobe Analytics esistente per utilizzare il Web SDK e verificare che tutto funzioni in Adobe Analytics. Una volta configurata e se i dati in Adobe Analytics sono soddisfacenti, puoi inviare dati da Edge Network a Customer Journey Analytics.

   Questa flessibilità consente un aggiornamento più metodico e attento a Customer Journey Analytics.

   Per informazioni su come eseguire questa operazione, consulta i seguenti articoli nella documentazione di Adobe Analytics:

   * [Esegui la migrazione al Web SDK utilizzando i tag](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Esegui la migrazione al Web SDK tramite JavaScript](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Invia dati da Edge Network a Customer Journey Analytics.

   1. Invia tutte le variabili in formato AppMeasurement tramite l’oggetto dati.

      Per ulteriori informazioni, vedere [Mappatura della variabile dell&#39;oggetto dati in Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Se non lo hai già fatto, crea uno schema XDM per la tua organizzazione.

      Per ulteriori informazioni, vedere [Creare uno schema personalizzato da utilizzare con l&#39;implementazione di Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.

      Per ulteriori informazioni, consulta [Mappatura](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Preparazione per la raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) nella documentazione di Experience Platform.

