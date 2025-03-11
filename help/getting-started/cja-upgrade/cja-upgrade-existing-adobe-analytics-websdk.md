---
title: Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati a Platform
description: Scopri come configurare l’implementazione di Adobe Analytics Web SDK esistente
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 52%

---

# Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati a Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Rimuovere Adobe Analytics as a service dallo stream di dati"
>abstract="Con i dati di Web SDK completamente funzionanti, rivolgiti all’amministratore di Platform per rimuovere Adobe Analytics as a service dallo stream di dati. Prima di eseguire questa operazione, assicurati che gli utenti siano passati dall’utilizzo di Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Se la tua implementazione di Adobe Analytics utilizza già Adobe Experience Platform Web SDK, puoi iniziare a inviare dati a Platform configurando un flusso di dati. Oppure, se invii già dati a Platform, devi semplicemente creare una connessione tra i set di dati di Platform e Customer Journey Analytics.


## Vantaggi e svantaggi

Considera i seguenti vantaggi e svantaggi della configurazione dell’implementazione Adobe Analytics Web SDK esistente per l’invio di dati a Platform:

| Vantaggi | Svantaggi |
|----------|---------|
| Questo è il percorso di aggiornamento preferito se l’implementazione di Adobe Analytics utilizza già il Web SDK.<ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti apportando modifiche minime alla logica di implementazione senza influire sulla reportistica di Adobe Analytics esistente.</li><li>**Fornisce un’opzione per utilizzare uno schema XDM**: puoi scegliere di utilizzare lo schema di Adobe Analytics esistente o di creare uno schema XDM e mappare i campi nell’oggetto dati per lo schema XDM. Gli [schemi XDM](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home#xdm-schemas) consistono in uno schema flessibile per definire tutti i campi necessari e solo quelli rilevanti. <p>Per ulteriori informazioni sui vantaggi derivanti dall’utilizzo dello schema XDM, consulta “Utilizzo del proprio schema XDM” di seguito.</p></li><li>**Conserva regole ed elementi di dati**: sebbene richieda nuove azioni relative alle regole, puoi riutilizzare gli elementi di dati esistenti e le condizioni delle regole con modifiche minime.</li><li>**All’avanguardia**: se scegli di utilizzare lo schema XDM, i futuri aggiornamenti dell’implementazione saranno più semplici.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell’oggetto dati sia una voce nello strumento di mappatura del flusso di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li><li>**Introduce ulteriore complessità nel tempo**: qualsiasi campo aggiunto in futuro deve essere mappato a XDM nello stream di dati.<p>Ogni volta che un nuovo campo viene aggiunto all’implementazione, è possibile effettuare una delle seguenti operazioni:</p><ul><li>**Opzione 1:** compila una nuova eVar arbitraria o una nuova proprietà nell&#39;oggetto dati, quindi mappala al campo XDM desiderato.<p>Questo processo favorisce la coerenza per l’implementazione lato client, ma richiede la mappatura.</p></li><li>**Opzione 2:** Lascia l&#39;oggetto dati come implementazione legacy e inizia a popolare solo l&#39;oggetto XDM per tutti i nuovi campi.<p>Questo processo non richiede la mappatura, ma significa che alcune delle variabili si trovano solo in un oggetto dati, mentre altre variabili si trovano solo in un oggetto XDM. Ogni volta che hai bisogno di risolvere un problema di implementazione, devi passare a due posizioni. Assicurati che i flussi di lavoro interni siano adatti a questo scopo.</p></li></ul> |

{style="table-layout:auto"}

## Passaggi di implementazione

1. Inizia a inviare dati da Edge Network a Platform. Invia tutte le variabili in formato AppMeasurement tramite l’oggetto dati.

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
   | <ul><p>I vantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>Uno schema semplificato personalizzato in base alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi.</li><p>Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></ul> | <p>Gli svantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>L’aggiornamento dello schema è un processo che richiede molto tempo prima di iniziare a inviare dati a Platform.</li></ul> |

+++

1. Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.

   Per ulteriori informazioni, consulta [Mappatura](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Preparazione per la raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) nella documentazione di Experience Platform.

{{upgrade-final-step}}
