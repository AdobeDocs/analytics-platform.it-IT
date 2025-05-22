---
title: Aggiornare da Adobe Analytics a Customer Journey Analytics
description: Scopri i passaggi consigliati durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: ht
source-wordcount: '3268'
ht-degree: 100%

---

# Aggiornare da Adobe Analytics a Customer Journey Analytics

Durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics, puoi seguire i [passaggi di aggiornamento consigliati](#recommended-upgrade-steps-for-most-organizations). Oppure puoi [generare dinamicamente i passaggi di aggiornamento](#dynamically-generate-upgrade-steps-for-your-organization) per le circostanze specifiche della tua organizzazione.

## Passaggi di aggiornamento consigliati per la maggior parte delle organizzazioni {#upgrade-process}

Il processo consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics. Insieme al Web SDK, Adobe consiglia anche di utilizzare il connettore di origine di Analytics per facilitare la transizione a Customer Journey Analytics. Utilizza il connettore di origine di Analytics per conservare i dati storici di Adobe Analytics ed eseguire confronti di dati affiancati.

Quando hai raccolto un numero sufficiente di dati storici utilizzando Experience Platform Web SDK e hai effettuato la transizione completa a Customer Journey Analytics, il connettore di origine di Analytics può essere disattivato e il Web SDK può essere utilizzato in modo esclusivo.

>[!NOTE]
>
>Se i passaggi di aggiornamento descritti in questa sezione non sono funzionali per la tua organizzazione, utilizza la guida all’aggiornamento da Adobe Analytics a Customer Journey Analytics per generare in modo dinamico passaggi di aggiornamento personalizzati per la situazione specifica della tua organizzazione. Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.)

### Processo di aggiornamento consigliato di alto livello {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Dati storici da Adobe Analytics"
>abstract="Importare i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementare Experience Platform Web SDK (per la raccolta dati continua)**

   Una nuova implementazione di Experience Platform Web SDK è il modo migliore per raccogliere dati per Customer Journey Analytics. La soluzione fornisce le basi migliori per ottenere il massimo da Customer Journey Analytics perché è il metodo più performante, semplice e a prova di futuro per implementare Customer Journey Analytics.

   * Reporting e disponibilità dei dati offrono eccellenti prestazioni, perché Adobe Experience Platform è progettato per alimentare casi d’uso di personalizzazione in tempo reale

   * Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)

   * Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)

1. **Configurare il connettore di origine di Adobe Analytics (per il recupero dei dati storici)**

   Per facilitare la transizione all’utilizzo di Experience Platform Web SDK con Customer Journey Analytics, Adobe consiglia inoltre di utilizzare il connettore di origine di Adobe Analytics. Questo consente di conservare i dati storici e visualizzare i dati dell’implementazione Adobe Analytics esistente in Customer Journey Analytics, affiancando i dati della nuova implementazione di Experience Platform Web SDK.

   Il connettore di origine di Analytics ti consente di:

   * Importare i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics.

     Puoi mantenere in funzione il connettore di origine di Analytics per il tempo necessario a conservare i dati storici di Adobe Analytics.

   * Visualizzare i dati raccolti con l’implementazione originale di Adobe Analytics (AppMeasurement, estensione Analytics o estensione Web SDK) in Customer Journey Analytics. Puoi confrontare questi dati affiancandoli a quelli della nuova implementazione di Web SDK.

     Puoi mantenere in funzione il connettore di origine di Analytics fino a quando non avrai una soddisfacente familiarità con le differenze. <!--elaborate on what those differences are? -->

   Il connettore di origine di Analytics come implementazione autonoma non è un metodo consigliato a lungo termine per l’utilizzo di Customer Journey Analytics. Ciò è dovuto a latenza elevata, schemi ingombranti e complessi, dipendenza dalla nomenclatura di Adobe Analytics (prop, eVar e così via) e difficoltà nel passare infine dal connettore di origine di Analytics all’implementazione consigliata di Web SDK.

### Passaggi dettagliati consigliati per l’aggiornamento

I passaggi seguenti descrivono il processo consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

Ogni passaggio fornisce una spiegazione di alto livello di un processo più dettagliato. Segui il collegamento di ogni passaggio e completa le attività associate, quindi torna a questa pagina e continua con il passaggio successivo del processo.

1. [Pianifica l’architettura dello schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crea lo schema personalizzato che desideri in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Quando crei lo schema, considera le seguenti opzioni:

   * Per integrare Customer Journey Analytics con RTCDP, devi abilitare l’opzione **[!UICONTROL Profile]** nello schema, come descritto in [Creare uno schema XDM da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Con questa opzione abilitata, i dati inseriti in set di dati basati su questo schema vengono uniti sul profilo cliente in tempo reale.

   * Se desideri includere dati multimediali in streaming, devi [configurare lo schema per acquisire e utilizzare dati in streaming](/help/data-ingestion/streaming.md).

1. [Crea un set di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Facoltativo) Se utilizzi i dati di classificazione in Adobe Analytics, puoi aggiungerli al set di dati in Customer Journey Analytics.

   Per farlo, [crea un set di dati di ricerca per ogni dimensione contenente dati di classificazione](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Per le implementazioni Adobe Analytics che utilizzano AppMeasurement o l’estensione Analytics (tag), [crea uno stream di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Per le implementazioni Adobe Analytics che utilizzano il Web SDK, esiste già uno stream di dati. Per ulteriori informazioni, consulta [Configurare l’implementazione di Adobe Analytics Web SDK esistente per inviare i dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Aggiungi Adobe Experience Platform come servizio allo stream di dati](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Facoltativo) Se desideri integrare Customer Journey Analytics con Adobe Journey Optimizer, utilizza l’oggetto di personalizzazione nella tua implementazione per l’utilizzo in Adobe Journey Optimizer.

1. Espandi la sezione che descrive come implementare Experience Platform Web SDK per l’implementazione di Customer Journey Analytics, quindi completa i passaggi associati:

   +++Implementazione manuale (file JS)

   1. [Aggiungi alloy.js al tuo sito](https://experienceleague.adobe.com/it/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Popola un oggetto XDM e invialo allo stream di dati.

+++

   +++Tag

   1. [Crea una proprietà tag e aggiungi l’estensione Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Aggiungere l’estensione Adobe Experience Platform Web SDK alla proprietà tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implementa il tag loader sul sito](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Aggiungi la logica di raccolta dati XDM al tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilizza l’API di Edge Network per inviare dati allo stream di dati desiderato.

+++

1. [Verifica che l’implementazione di Web SDK stia inviando dati a un set di dati](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Crea una connessione in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Facoltativo) Collega i dati web con dati provenienti da altri canali, ad esempio i dati del call center.

   A tale scopo, aggiungi set di dati aggiuntivi alla tua connessione Customer Journey Analytics, come descritto in [Importare dati da web e call center](/help/use-cases/cross-channel/call-center.md).

1. [Crea una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Verifica che i dati vengano trasmessi alla visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. Nell’ambiente Adobe Analytics, [utilizza l’inventario di Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/analytics-inventory) per visualizzare una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora.

1. [Migra progetti e componenti](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Facoltativo) Se utilizzi i canali di marketing in Adobe Analytics, puoi [creare un campo derivato dal canale di marketing in Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   I campi derivati sono un aspetto importante del reporting in tempo reale in Customer Journey Analytics. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile.

   Un utilizzo per i campi derivati consiste nel definire un campo Canale di marketing derivato che determina il canale di marketing corretto in base a una o più condizioni (ad esempio, parametro URL, URL pagina o nome pagina).

   Utilizza [il modello di funzione canali di marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) nei campi derivati per creare rapidamente un campo derivato per i canali di marketing.

1. Confronta i dati in Adobe Analytics dalla vecchia implementazione con i dati in Customer Journey Analytics dalla nuova implementazione e assicurati di comprendere eventuali differenze e perché esistono. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Acquisisci dati storici da Adobe Analytics utilizzando il connettore di origine Analytics:

   >[!NOTE]
   >
   >Se non hai creato in precedenza un connettore di origine Analytics, procedi come segue.
   >
   >Se utilizzi già il connettore di origine Analytics con Customer Journey Analytics, segui i passaggi descritti in [Passaggio dal connettore di origine Analytics al Web SDK per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Se non disponi già di un connettore di origine Analytics, [crea il connettore di origine Analytics e mappa i campi allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Oppure

      Se disponi già di un connettore di origine Analytics, [mappa i campi dal connettore di origine allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Aggiungi il set di dati del connettore di origine Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Pianifica l’onboarding degli utenti.

   Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.

   Dovresti lasciare agli utenti il tempo necessario (3 - 6 mesi) per familiarizzare con le differenze chiave dell’utilizzo di Analysis Workspace in Customer Journey Analytics.

   Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Scopri [il supporto delle funzionalità in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). In Customer Journey Analytics è supportata la maggior parte delle funzioni di Adobe Analytics, molte funzionalità aggiuntive sono disponibili in Customer Journey Analytics.

1. Disabilita Adobe Analytics quando l’implementazione di Customer Journey Analytics Web SDK è completa e hai familiarità con i dati che stai raccogliendo.

   Adobe consiglia di mantenere l’ambiente Adobe Analytics in esecuzione per un periodo di tempo dopo l’implementazione di Customer Journey Analytics.

   Per ulteriori informazioni sugli usi di Adobe Analytics durante e dopo un aggiornamento, nonché sulla tempistica consigliata per la disabilitazione di Adobe Analytics, consulta [Valutare per quanto tempo mantenere Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Generare in modo dinamico i passaggi di aggiornamento per la tua organizzazione

A seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati descritti in [Comprendere i passaggi di aggiornamento consigliati](#recommended-upgrade-steps-for-most-organizations) potrebbero non essere pratici per la tua organizzazione. In questo caso, puoi generare dinamicamente i passaggi di aggiornamento per le circostanze specifiche della tua organizzazione. Il processo di generazione di questi passaggi varia a seconda che tu abbia già accesso a Customer Journey Analytics.

### Per la clientela che ha accesso a Customer Journey Analytics

Per generare in modo dinamico i passaggi di aggiornamento per le circostanze specifiche dell’organizzazione:

1. Completa la Guida all’aggiornamento di Customer Journey Analytics.

   In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.

   Dopo aver completato la guida all’aggiornamento, ti vengono fornite istruzioni dettagliate che descrivono i passaggi di aggiornamento ottimali e specifici per i requisiti aziendali. Questi sono i passaggi di aggiornamento più adatti all’ambiente Adobe Analytics esistente e agli obiettivi per Customer Journey Analytics. I passaggi di aggiornamento sono disponibili come collegamento condivisibile o come file .csv scaricabile.

1. Segui le istruzioni dettagliate generate per l’aggiornamento a Customer Journey Analytics.

### Per la clientela che non ha ancora accesso a Customer Journey Analytics

Per generare in modo dinamico i passaggi di aggiornamento per le circostanze specifiche dell’organizzazione:

1. Contatta il team del tuo account Adobe per completare la Guida all’aggiornamento di Customer Journey Analytics.

   Il team del tuo account Adobe può assisterti nella guida all’aggiornamento e fornirti un file .csv contenente le domande, le risposte e i passaggi di aggiornamento generati in modo dinamico e specifico per la tua organizzazione.

   Prima di contattare il team del tuo account Adobe, acquisisci familiarità con le domande incluse nella Guida all’aggiornamento di Customer Journey Analytics e determina le risposte. La Guida all’aggiornamento di Customer Journey Analytics contiene le seguenti domande e possibili risposte:


   | Domanda | Risposte disponibili | Informazioni aggiuntive |
   |---------|----------|---------|
   | Seleziona l’opzione che descrive l’implementazione Adobe Analytics corrente. Queste informazioni possono influenzare le opzioni di aggiornamento alternative che potrebbero essere disponibili durante l’aggiornamento a Customer Journey Analytics. | Selezionane una: <ul><li>**AppMeasurement:**<br/>: implementazione di JavaScript che carica AppMeasurement.js su una pagina e invia i dati ad Adobe utilizzando l’oggetto s (ad esempio, s.eVar1).</li><li>**Estensione Adobe Analytics (tag):** <br/>implementazione di tag che carica la raccolta dati di Adobe Experience Platform (precedentemente nota come Launch). Nel tag è installata l’estensione di Adobe Analytics.</li><li>**Estensione Experience Platform Web SDK (tag):**<br/> implementazione di tag che carica la raccolta dati di Adobe Experience Platform (precedentemente nota come Launch). Nel tag è installata l’estensione Web SDK.</li><li>**Experience Platform Web SDK (alloy.js):** implementazione di JavaScript che carica la libreria Web SDK (alloy.js) su una pagina e invia i dati ad Adobe utilizzando un payload JSON.</li><li>**API di inserimento dati in blocco:**<br/> implementazione che utilizza l’API di inserimento dati o l’API di inserimento dati in blocco.</li><li>**Experience Platform Mobile SDK:**<br/> implementazione che utilizza Adobe Experience Platform Mobile SDK.</li><li>**AppMeasurement utilizza uno strumento di gestione di tag di terze parti:**<br/> implementazione che utilizza uno strumento di gestione di tag di terze parti.</li><li>**Prodotto non Adobe Analytics:**<br/> implementazione che raccoglie dati per un prodotto di analisi di terze parti, ad esempio Google Analytics. Selezionando questa opzione verranno disabilitate diverse opzioni della guida all’aggiornamento che non vengono applicate durante l’aggiornamento a Customer Journey Analytics da un prodotto di analisi diverso da Adobe. </li><li>**Non so:**<br/> se non sei la persona che gestisce l’implementazione, puoi selezionare temporaneamente questa opzione.</li></ul><p>Seleziona, se applicabile:<ul><li>**La nostra implementazione utilizza attualmente il connettore di origine di Analytics:**<br/> il connettore di origine di Analytics consente di ottenere facilmente valore da Customer Journey Analytics, ma richiede il pagamento sia per Adobe Analytics che per Customer Journey Analytics. Questa guida consente di passare a un’implementazione indipendente di Web SDK.</li></ul></p> | <ul><li>[Comprendere l’implementazione di Adobe Analytics e il modo in cui influisce sull’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transizione dal connettore di origine di Analytics a Web SDK per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | La maggior parte delle funzioni di Adobe Analytics sono prontamente disponibili in Customer Journey Analytics. Tuttavia, durante il processo di aggiornamento, è necessario prendere in considerazione le funzioni seguenti. Seleziona le funzioni che prevedi di utilizzare. | Seleziona tutte quelle pertinenti:<ul><li>**Dati storici da Adobe Analytics:**</br> importare i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics.</li><li>**Componenti e progetti da Adobe Analytics:**</br> i componenti di Adobe Analytics includono progetti (con le relative tabelle a forma libera e visualizzazioni associate), segmenti e metriche calcolate.</li><li>**Sovrapposizione Activity map e tracciamento dei collegamenti:**</br> estensione del browser che consente di visualizzare i dati di tracciamento dei collegamenti come sovrapposizione sul sito.</li><li>**Dati di classificazione:**</br> raggruppa o categorizza i dati come dimensioni separate.</li><li>**Canali marketing:**</br> crea regole che categorizzano il modo in cui la clientela arriva sul sito.</li><li>**Data Warehouse:**</br> esporta dati elaborati da Adobe Analytics in formato di foglio di calcolo.</li><li>**Feed di dati.**Una sostituzione esatta dei feed di dati non è ancora disponibile in Customer Journey Analytics. Tuttavia, funzionalità simili possono essere ottenute con caratteristiche quali l’esportazione di tabelle complete, l’esportazione di set di dati di Platform, l’integrazione di strumenti BI e l’API di reporting.</br></li><li>**Dati di file multimediali in streaming:**</br> componente aggiuntivo per Adobe Analytics e Customer Journey Analytics, specializzato nella raccolta dati di file multimediali, come audio, video o contenuti in streaming.</li></ul> | <ul><li>[Informazioni sul supporto delle funzioni di Adobe Analytics durante l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | La maggior parte delle nuove funzioni sono facilmente disponibili in Customer Journey Analytics. Tuttavia, durante il processo di aggiornamento, è necessario prendere in considerazione le funzioni seguenti. Seleziona le funzioni che prevedi di utilizzare. | Seleziona tutte quelle pertinenti:<ul><li>**Collega i dati raccolti con dati provenienti da altre origini (ad esempio, i dati del centro contatti):**</br>(consigliato) collega i dati provenienti da varie proprietà web, mobile e offline per creare una singola visualizzazione consolidata del comportamento della clientela. La possibilità di combinare dati di analisi provenienti da altri canali è il caso d’uso principale per Customer Journey Analytics.</li><li>**Unisci gli hit provenienti da altri set di dati utilizzando una dimensione personalizzata:**<br/> se un set di dati non condivide un identificatore principale (ad esempio, un ID Experience Cloud), puoi comunque unire i dati utilizzando un’altra dimensione, ad esempio il nome utente o l’indirizzo e-mail di accesso.</li><li>**Integra con Adobe Journey Optimizer :**<br/> fornisci alla clientela esperienze connesse, contestuali e personalizzate.</li><li>**Integra con Adobe Real-Time CDP:**<br/> combina i dati di profilo da più origini per generare tipi di pubblico e segmenti in base alle caratteristiche degli utenti.</li><li>**Integra con Adobe Target (A4T):**<br/> Adobe consiglia di eseguire l’integrazione con Adobe Journey Optimizer per i casi d’uso di personalizzazione. L’integrazione con Adobe Target è possibile, ma si tratta di una soluzione temporanea.</li><li>**Integra con Adobe Audience Manager:**<br/> Adobe consiglia di eseguire l’integrazione con Adobe Real-time CDP per i casi d’uso basati sul pubblico. L’integrazione con Audience Manager è possibile, ma si tratta di una soluzione temporanea.</li></ul> | [Informazioni sulle funzioni univoche di Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Seleziona la modalità di utilizzo finale prevista di Adobe Analytics e Customer Journey Analytics: | Selezionane una: <ul><li>**Intendo passare completamente a Customer Journey Analytics da Adobe Analytics:**<br/> (consigliato) Adobe consiglia di effettuare una transizione completa da Adobe Analytics a Customer Journey Analytics. Durante il periodo di transizione, pianifica di eseguire Adobe Analytics insieme a Customer Journey Analytics per eseguire confronti affiancati dei dati. Quando avrai dimestichezza con i dati, potrai disabilitare Adobe Analytics.</li><li>**Intendo mantenere entrambi i prodotti Analytics:**<br/>(non consigliato) se selezioni questa opzione, il contratto con Adobe includerà sia Adobe Analytics che Customer Journey Analytics e, a lungo termine, questa scelta potrà risultare più costosa per l’organizzazione.</li></ul> | [Valutare quando disabilitare Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Seleziona la modalità di configurazione dello schema di Customer Journey Analytics: | Selezionane una: <ul><li>**Desidero utilizzare uno schema personalizzato in base alla mia organizzazione:**</br>(consigliato) la personalizzazione dello schema consente all’organizzazione di tenere traccia solo di ciò che è necessario, evitando il sovraccarico derivante da campi disordinati e non necessari. Questa opzione include i gruppi di campi aggiunti dal Web SDK e quelli personalizzati per la tua organizzazione.</li><li>**Desidero utilizzare lo schema predefinito di Adobe Analytics:**</br> (non consigliato) lo schema di Adobe Analytics contiene più di mille campi, che possono causare un ingombro e una complessità dello schema. La tua organizzazione sarebbe costretta a continuare ad aderire al concetto di prop ed eVar, che è un concetto legacy non utilizzato in Customer Journey Analytics. L’integrazione con altri servizi Adobe Experience Platform è più difficile.</li></ul> | [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Seleziona il modo preferito per implementare Customer Journey Analytics: | <ul><li>**Implementazione manuale (alloy.js):**<br/> includi la libreria web SDK (alloy.js) in ogni pagina del sito.</li><li>**Tag:**<br/>(consigliato) se non utilizzi ancora i tag, installa il tag loader sul sito. Se utilizzi già i tag, puoi aggiungere l’estensione Web SDK alla proprietà tag. Questa opzione include implementazioni utilizzando i tag all’interno della raccolta dati di Adobe Experience Platform e i sistemi di gestione dei tag di terze parti.</li><li>**API:**<br/> utilizza l’API di raccolta dati per inviare i dati direttamente a uno stream di dati. Sono supportati sia i tipi non autenticati (da client a server) che autenticati (da server a server).</li></ul> | [Informazioni sulle opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Facoltativo) Selezionare un metodo di aggiornamento alternativo | <ul><li>**Utilizza unicamente il connettore di origine Analytics:**<br/>(non consigliato) puoi utilizzare il connettore di origine Analytics come unico percorso di implementazione per Customer Journey Analytics.<p>Questa opzione consente di ridurre i tempi di implementazione inviando rapidamente i dati a Customer Journey Analytics. Tuttavia, presenta diverse lacune, come una latenza più elevata e difficoltà durante la migrazione ad Adobe Analytics in futuro.</p></li><li>**Desidero utilizzare la logica di AppMeasurement con il Web SDK:**<br/> anziché inviare dati tramite un oggetto XDM, invia tutte le variabili in formato AppMeasurement tramite l’oggetto dati.<p>Questa opzione consente di ridurre i tempi di implementazione permettendoti di mappare la logica AppMeasurement su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, nel tempo introduce ulteriori complessità, in quanto qualsiasi campo aggiunto successivamente dovrà essere mappato su XDM nello stream di dati.</p></li><li>**Desidero inviare il livello dati ad Adobe senza configurazione aggiuntiva:**<br/> anziché inviare dati tramite un oggetto XDM, puoi inviare l’intero livello dati ad Adobe tramite l’oggetto dati.<p>Questa opzione consente di ridurre i tempi di implementazione permettendoti di mappare il livello dati su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, tale mappatura può essere laborioso, a causa di una quantità significativa di dati che potrebbero non essere facilmente interpretati da Adobe. Inoltre, questa opzione introduce nel tempo ulteriori complessità, in quanto qualsiasi campo aggiunto ai dati in un secondo momento dovrà essere mappato su XDM nello stream di dati.</p></li></ul> | <ul><li>[Alternativa di aggiornamento: utilizzare solo il connettore di origine di Analytics per l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Alternativa di aggiornamento: utilizzare la raccolta dati di AppMeasurement con Experience Platform Web SDK e Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Alternativa di aggiornamento: inviare il livello dati a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Dopo aver completato questa guida all’aggiornamento con il team Adobe Account, riceverai un file .csv contenente le domande, le risposte e i passaggi di aggiornamento generati in modo dinamico che si allineano al meglio all’ambiente Adobe Analytics esistente e agli obiettivi per Customer Journey Analytics.

1. Segui le istruzioni dettagliate generate nel file .csv per effettuare l’aggiornamento a Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
