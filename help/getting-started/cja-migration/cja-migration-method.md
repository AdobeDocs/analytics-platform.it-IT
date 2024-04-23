---
title: Scegli il metodo di migrazione di Customer Journey Analytics
description: Scopri i vantaggi e gli svantaggi dei possibili metodi di migrazione durante la migrazione al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 2%

---

# Passaggio 2: scegliere il metodo di migrazione di Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 2, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| <span class="preview">**Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine.</span> |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Dopo aver deciso di eseguire la migrazione al Customer Journey Analytics, devi determinare il metodo di migrazione ottimale per la tua organizzazione.

Il metodo scelto per la migrazione da Adobe Analytics a Customer Journey Analytics dipende dai seguenti fattori:

* Implementazione di Adobe Analytics esistente

* I tuoi obiettivi per il futuro

Utilizza le informazioni in questa pagina per determinare quale metodo di migrazione di Customer Journey Analytics si allinea meglio agli obiettivi futuri e all’implementazione corrente della tua organizzazione.

Per determinare il metodo di migrazione ottimale per la tua organizzazione, le seguenti sezioni devono essere lette in sequenza:

1. In primo luogo, [comprendere i metodi di migrazione disponibili](#understand-migration-methods).

1. Allora, [valutare i metodi di migrazione disponibili](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. E infine... [valutare i vantaggi e gli svantaggi di ciascun metodo di migrazione](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Comprendere i metodi di migrazione

Esistono diversi metodi di migrazione per eseguire la migrazione da Adobe Analytics a Customer Journey Analytics.

In generale, ciascun metodo di migrazione varia in base al livello di impegno richiesto per eseguirla, nonché alla redditività a lungo termine raggiunta al termine della migrazione.

Nella tabella seguente sono elencati tutti i metodi di migrazione, il livello di impegno e la fattibilità a lungo termine:

| Metodo di migrazione | Livello di impegno | Redditività a lungo termine |
|---------|----------|---------|
| **Nuova implementazione del Web SDK**</br> Puoi eseguire una nuova implementazione di Adobe Experience Platform Web SDK per iniziare a inviare dati all’Edge Network Adobe Experience Platform <!-- what is the correct branding -->. <p>Per le organizzazioni che non utilizzano ancora il Web SDK, questo metodo di migrazione è forse il più semplice per portare i dati all’Edge Network (richiede il minor numero di passaggi); tuttavia, poiché tutto il lavoro è svolto in anticipo (ad esempio la creazione dello schema XDM), richiede uno sforzo iniziale maggiore.</p><p>I passaggi di base sono i seguenti:</p><ol><li>Crea uno schema XDM per la tua organizzazione.</li><li>Implementa l’SDK per web.</li><li>Invia dati a Platform.</li></ol> | Alta | Alta |
| **Migrare l’implementazione di Adobe Analytics per utilizzare l’SDK per web**</br> Se la tua implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, puoi migrarla per utilizzare Adobe Experience Platform Web SDK per iniziare a inviare dati ad Edge Network prima di inviarli al Customer Journey Analytics. <!-- what else? --><p>Questo è il modo più semplice e fluido per portare i dati all’Edge Network; richiede più passaggi, ma offre una transizione più metodica con tappe più tangibili.</p><p>I passaggi di base sono i seguenti:</p><ol><li>Sposta l’implementazione Adobe Analytics esistente nell’SDK per web e verifica che tutto funzioni lì.</li><li>Crea uno schema XDM per la tua organizzazione non appena hai tempo.</li><li>Utilizza la mappatura del flusso di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li><li>Invia dati a Platform.</li></ol> | Modera | Alta |
| **Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati al Customer Journey Analytics**</br> Se la tua implementazione di Adobe Analytics utilizza già Web SDK, puoi iniziare a inviare dati al Customer Journey Analytics con il minimo sforzo.<p>Prima di inviare i dati al Customer Journey Analytics, è consigliabile aggiornare lo schema di Adobe Analytics in base alle esigenze specifiche dell’organizzazione e di qualsiasi altra applicazione Platform che utilizzerai.</p><p>I passaggi di base sono i seguenti:</p><ol><li>Inizia a inviare dati al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Facoltativo) Crea uno schema XDM per la tua organizzazione non appena hai tempo.</li><li>(Condizionale) Se hai creato uno schema XDM, utilizza la mappatura del flusso di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li></ol> | Bassa | Alta |
| **Connettore di origine di Analytics**</br> Se la tua implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, puoi iniziare a inviare dati a una visualizzazione dati nel Customer Journey Analytics.<p>Questo è il modo più semplice per portare i dati al Customer Journey Analytics, ma è il metodo meno efficace a lungo termine.</p> | Bassa | Bassa |

{style="table-layout:auto"}

Utilizza il diagramma seguente per visualizzare in che modo ogni metodo di migrazione rientra nello spettro in termini di livello di sforzo e redditività a lungo termine:

![metodi di migrazione cja](assets/cja-migration-methods.png)

## Valuta i metodi di migrazione disponibili in base all’implementazione Adobe Analytics corrente

Non tutti i metodi di migrazione sono disponibili per ciascun tipo di implementazione di Adobe Analytics.

Utilizza le informazioni riportate di seguito per capire quale metodo di migrazione è più appropriato per la tua organizzazione.

Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante del tuo Adobe.

| Implementazione di Adobe Analytics | Metodi di migrazione disponibili |
|---------|----------|
| AppMeasurement | <ul><li>Nuova implementazione del Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li></ul> |
| Estensione Adobe Analytics | <ul><li>Nuova implementazione del Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li></ul> |
| Web SDK | <ul><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati al Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Valuta i vantaggi e gli svantaggi dei metodi di migrazione disponibili

I vantaggi e gli svantaggi di un determinato metodo di migrazione dipendono dall’implementazione di Adobe Analytics esistente.

Prima di utilizzare le informazioni riportate di seguito per determinare il metodo di migrazione più appropriato, esaminare le informazioni in [Comprendere i metodi di migrazione](#understand-migration-methods) se non lo hai già fatto.

### Per le implementazioni di Adobe Analytics che utilizzano: estensione AppMeasurement e Adobe Analytics

La tabella seguente mostra i metodi di migrazione disponibili per le organizzazioni che hanno implementato Adobe Analytics con AppMeasurement o l’estensione Adobe Analytics:

| Metodo di migrazione | Vantaggi | Svantaggi |
|---------|----------|---------|
| **Nuova implementazione del Web SDK** | <ul><li>Utilizza uno schema XDM, uno schema flessibile per definire tutti i campi necessari e solo quelli rilevanti (consente di allontanarsi dal gruppo di campi Adobe Analytics Experience Event)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li><li>Nessun limite di carattere (100 caratteri per prop)</li><li>Rapporti e disponibilità dei dati ad alte prestazioni perché Adobe Experience Platform è progettato per [casi di utilizzo della personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Scalabile (in grado di ricevere tutte le funzionalità e le caratteristiche più recenti)</li><li>Consolidare i tag per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>[ID dispositivo di prime parti](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it) per una maggiore precisione nell’identificazione dei visitatori</li></ul> | <ul><li>Il metodo di migrazione più lungo ed esigente<p>È necessario ricreare lo schema completo in XDM prima di poter iniziare a implementare Web SDK</p></li></ul> |
| **Migrare da Adobe Analytics a Web SDK** | <ul><li>Conserva le regole e gli elementi dati già configurati nell’implementazione di Adobe Analytics.</li><li>Consente di passare a Web SDK senza influire sui rapporti esistenti di Adobe Analytics.</li><li>Offre flessibilità per creare uno schema XDM per l’organizzazione in un secondo momento: uno schema flessibile per definire tutti i campi necessari e solo quelli rilevanti.</br>Non richiede il gruppo di campi Adobe Analytics Experience Event nel Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li><li>Nessun limite di carattere (100 caratteri per prop)</li><li>Rapporti e disponibilità dei dati ad alte prestazioni perché Adobe Experience Platform è progettato per [casi di utilizzo della personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Scalabile (in grado di ricevere tutte le funzionalità e le caratteristiche più recenti)</li><li>Consolidare i tag per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>[ID dispositivo di prime parti](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it) per una maggiore precisione nell’identificazione dei visitatori</li></ul> | <ul><li>Deve essere conforme a uno schema XDM in futuro, utilizzando la mappatura dello stream di dati.</li><li>Incontra un certo debito tecnico. Ad esempio, il codice di AppMeasurement o di estensione legacy di Analytics può rimanere. </li></ul> |
| **Connettore di origine di Analytics** | <ul><li>Metodo di migrazione meno lungo e impegnativo. <p>Migrazione rapida dei dati al Customer Journey Analytics con un investimento minimo</p></li></ul> | <ul><li>I dati non vengono inviati ad Edge Network e non possono essere condivisi con altre applicazioni Adobe Experience Platform; sono vincolati solo al Customer Journey Analytics<li>Difficoltà nel passare al Web SDK in futuro</li><li>Utilizza il gruppo di campi Evento esperienza di Analytics nello schema.</br>Questo gruppo di campi aggiunge molti eventi Adobe Analytics che non sono necessari nello schema del Customer Journey Analytics.  Questo può portare a uno schema più disordinato e complesso di quanto sia altrimenti necessario per il Customer Journey Analytics.</li><li>Livello massimo di [latenza](/help/admin/guardrails.md#latencies) in tutti i metodi di implementazione</li></ul> |

{style="table-layout:auto"}

### Per le implementazioni di Adobe Analytics che utilizzano: SDK web

La tabella seguente mostra i metodi di migrazione disponibili per le organizzazioni che hanno implementato Adobe Analytics con Web SDK:

| Metodo di migrazione | Vantaggi | Svantaggi |
|---------|----------|---------|
| **Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati al Customer Journey Analytics** | Questo è il metodo di migrazione preferito se l’implementazione di Adobe Analytics utilizza già l’SDK web. <p>Quando utilizzi questo metodo di implementazione, puoi scegliere se utilizzare lo schema Adobe Analytics esistente oppure puoi eseguire l’aggiornamento allo schema XDM per allinearlo meglio alle esigenze della tua organizzazione quando inizi a utilizzare altre applicazioni Platform.</p><p>**Utilizzo dello schema Adobe Analytics**</p><p>I vantaggi dell’utilizzo dello schema Adobe Analytics includono:</p><ul><li>Facilità di migrazione<p>Se invii già dati ad Adobe Analytics con Adobe Experience Platform Web SDK, puoi aggiungere un servizio aggiuntivo allo stream di dati per inviare dati a Adobe Experience Platform (che può quindi essere utilizzato nella configurazione del Customer Journey Analytics).</p></li></ul><p>Gli svantaggi dell’utilizzo dello schema Adobe Analytics includono:</p><ul><li>Anche se l’utilizzo dello schema Adobe Analytics non ti limita in termini di come può essere utilizzato con altre applicazioni Platform, si ottiene uno schema più complesso di quanto potrebbe essere altrimenti. Questo perché lo schema di Adobe Analytics contiene molti oggetti specifici di Adobe Analytics che probabilmente non saranno utilizzati dalla tua organizzazione.<p>Quando sono necessarie modifiche allo schema, è necessario esaminare migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></li></ul><p>**Utilizzo dello schema XDM**</p><p>I vantaggi dell’aggiornamento dello schema XDM includono:</p><ul><li>Schema semplificato personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate.</li><p>Quando sono necessarie modifiche allo schema, non è necessario esaminare migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></ul><p>Gli svantaggi dell’aggiornamento dello schema XDM includono:</p><ul><li>L’aggiornamento dello schema è un processo che richiede molto tempo prima di iniziare a inviare dati al Customer Journey Analytics.</li></ul> | Nessuno |

{style="table-layout:auto"}

## Quindi, invia i dati a Adobe Experience Platform

Dopo aver utilizzato le informazioni precedenti per scegliere un metodo di migrazione, scopri come [inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) a seconda del metodo di migrazione scelto.
