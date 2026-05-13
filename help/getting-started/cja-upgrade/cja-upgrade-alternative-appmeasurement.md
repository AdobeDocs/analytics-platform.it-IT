---
title: Metodi alternativi per l'aggiornamento a Customer Journey Analytics
description: Scopri i metodi alternativi per l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
TQID: https://experienceleague.adobe.com/ZqnH8IZau2fC-ucGAjMFQyolfhCe2pYbLiWJ7BKKhII
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1381
ht-degree: 59%

---

# Alternativa di aggiornamento: utilizzare la raccolta dati di AppMeasurement con Experience Platform Web SDK e Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Utilizzare la logica AppMeasurement con Web SDK"
>abstract="Invece di inviare dati tramite un oggetto XDM, è possibile inviare tutte le variabili in formato AppMeasurement tramite l’oggetto dati.<br><br>Questa opzione riduce il tempo di implementazione consentendoti di mappare la logica AppMeasurement su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, nel tempo introduce ulteriori complessità, in quanto qualsiasi campo aggiunto successivamente dovrà essere mappato su XDM nello stream di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="Modificare la logica di AppMeasurement in modo che punti a Web SDK"
>abstract="Questo passaggio viene visualizzato perché hai adottato una scelta rapida per l’implementazione. Copia o modifica la logica di AppMeasurement per popolare l’oggetto dati anziché l’oggetto s. Ad esempio, cambia l’assegnazione di s.eVar1 in data.__adobe.analytics.eVar1 e ripeti l’operazione per tutte le variabili di Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Durante l’aggiornamento a Customer Journey Analytics, Adobe [consiglia una nuova implementazione di Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi per l’aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione.

È possibile utilizzare la logica di raccolta dati dell’estensione AppMeasurement o Analytics con il Web SDK per inviare dati a Platform e Customer Journey Analytics, invece di raccogliere dati con l’oggetto XDM. Tuttavia, questa alternativa introduce una complessità aggiuntiva nel tempo.

## Vantaggi e svantaggi

Questo metodo si esclude a vicenda con [l&#39;invio dell&#39;intero livello dati a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), perché entrambi i metodi eseguono la stessa attività. (Questo metodo è preferibile all’invio dell’intero livello dati ad Adobe. È più raffinato perché tutte le proprietà e le eVar passano attraverso data.__ adobe.analytics._variable-name_.)

Considera i seguenti vantaggi e svantaggi dell’utilizzo di questa alternativa di aggiornamento:

| Vantaggi | Svantaggi |
|----------|---------|
| Questo è il percorso di aggiornamento preferito se l’implementazione di Adobe Analytics utilizza già Web SDK.<ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti apportando modifiche minime alla logica di implementazione senza influire sulla reportistica di Adobe Analytics esistente.</li><li>**Fornisce un’opzione per utilizzare uno schema XDM**: puoi scegliere di utilizzare lo schema di Adobe Analytics esistente o di creare uno schema XDM e mappare i campi nell’oggetto dati per lo schema XDM. Gli [schemi XDM](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home#xdm-schemas) consistono in uno schema flessibile per definire tutti i campi necessari e solo quelli rilevanti. <p>Per ulteriori informazioni sui vantaggi derivanti dall’utilizzo dello schema XDM, consulta “Utilizzo del proprio schema XDM” di seguito.</p></li><li>**Conserva regole ed elementi di dati**: sebbene richieda nuove azioni relative alle regole, puoi riutilizzare gli elementi di dati esistenti e le condizioni delle regole con modifiche minime.</li><li>**All’avanguardia**: se scegli di utilizzare lo schema XDM, i futuri aggiornamenti dell’implementazione saranno più semplici.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell’oggetto dati sia una voce nello strumento di mappatura del flusso di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li><li>**Introduce ulteriore complessità nel tempo**: qualsiasi campo aggiunto in futuro deve essere mappato a XDM nello stream di dati.<p>Ogni volta che un nuovo campo viene aggiunto all’implementazione, è possibile effettuare una delle seguenti operazioni:</p><ul><li>**Opzione 1:** compila una nuova eVar arbitraria o una nuova proprietà nell&#39;oggetto dati, quindi mappala al campo XDM desiderato.<p>Questo processo favorisce la coerenza per l’implementazione lato client, ma richiede la mappatura.</p></li><li>**Opzione 2:** Lascia l&#39;oggetto dati come implementazione legacy e inizia a popolare solo l&#39;oggetto XDM per tutti i nuovi campi.<p>Questo processo non richiede la mappatura, ma significa che alcune delle variabili si trovano solo in un oggetto dati, mentre altre variabili si trovano solo in un oggetto XDM. Ogni volta che hai bisogno di risolvere un problema di implementazione, devi passare a due posizioni. Assicurati che i flussi di lavoro interni siano adatti a questo scopo.</p></li></ul> |

{style="table-layout:auto"}

## Passaggi di base

I passaggi di base per la migrazione di un’implementazione di Adobe Analytics (AppMeasurement o l’estensione Analytics) per utilizzare Web SDK per inviare dati a Customer Journey Analytics sono:

1. Esegui la migrazione dell’implementazione di Adobe Analytics per utilizzare Adobe Experience Platform Web SDK e iniziare a inviare dati ad Edge Network.

   Questo passaggio ti consente di migrare l’implementazione Adobe Analytics esistente per utilizzare il Web SDK. Facoltativamente, puoi inviare dati ad Adobe Analytics per verificare che tutto funzioni in Adobe Analytics prima di inviare dati a Customer Journey Analytics. Una volta configurata e se i dati in Adobe Analytics sono soddisfacenti, puoi inviare dati da Edge Network a Customer Journey Analytics.

   Tale flessibilità consente un aggiornamento più metodico e attento a Customer Journey Analytics.

   Per informazioni su come eseguire questa operazione, consulta i seguenti articoli nella documentazione di Adobe Analytics:

   * [Migrare a Web SDK utilizzando i tag](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrare a Web SDK utilizzando JavaScript](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Inizia a inviare dati da Edge Network a Platform.

   1. Invia tutte le variabili in formato AppMeasurement tramite l’oggetto dati.

      Per ulteriori informazioni, vedere [Mappatura della variabile dell&#39;oggetto dati in Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Scegli lo schema.

      Puoi scegliere se utilizzare lo schema Adobe Analytics esistente oppure puoi creare uno schema XDM per allinearlo meglio alle esigenze della tua organizzazione quando inizi a utilizzare altri servizi Platform.

      Adobe consiglia di creare uno schema XDM. Per ulteriori informazioni, vedere [Creare uno schema personalizzato da utilizzare con l&#39;implementazione di Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

      +++Utilizzare lo schema Adobe Analytics

      | Vantaggi | Svantaggi |
      |----------|---------|
      | <p>I vantaggi derivanti dall’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Facilità di aggiornamento<p>Se stai già inviando dati ad Adobe Analytics con Adobe Experience Platform Web SDK, puoi aggiungere un servizio aggiuntivo allo stream di dati per inviare dati ad Adobe Experience Platform (che potrà quindi essere utilizzato nella configurazione di Customer Journey Analytics).</p></li></ul> | <p>Gli svantaggi dell’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Sebbene l’utilizzo dello schema di Adobe Analytics non limiti in termini di come può essere utilizzato con altre applicazioni di Platform, risulta in uno schema più complesso di quanto potrebbe essere altrimenti. Questo perché lo schema di Adobe Analytics contiene molti oggetti specifici di Adobe Analytics che difficilmente verranno utilizzati dall’organizzazione.<p>Quando sono necessarie delle modifiche allo schema, è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></li></ul> |

      +++

      +++Creare uno schema XDM

      | Vantaggi | Svantaggi |
      |----------|---------|
      | <ul><p>I vantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>Uno schema semplificato personalizzato in base alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi.</li><p>Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></ul> | <p>Gli svantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>L’aggiornamento dello schema è un processo dispendioso in termini di tempo, necessario prima di iniziare a inviare i dati a Platform.</li></ul> |

      +++

   1. Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.

      Per ulteriori informazioni, consulta [Mappatura](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Preparazione per la raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) nella documentazione di Experience Platform.

{{upgrade-final-step}}.




