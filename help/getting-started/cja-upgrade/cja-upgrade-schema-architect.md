---
title: Progettare uno schema da utilizzare con Customer Journey Analytics
description: Scopri come progettare uno schema XDM che sfrutta la flessibilità di Customer Journey Analytics e al contempo supporta un percorso di migrazione pratico da Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 9%

---

# Progettare uno schema da utilizzare con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Progettare uno schema"
>abstract="Discuti all’interno della tua organizzazione i requisiti di raccolta dei dati e determina come creare uno schema da utilizzare in Adobe Experience Platform. Questo passaggio viene visualizzato perché desideri utilizzare il processo di utilizzo consigliato di uno schema personalizzato per la tua organizzazione. È fondamentale eseguire correttamente questo passaggio, in quanto uno schema su cui allineare tutti i team all’interno della tua organizzazione semplifica notevolmente l’acquisizione dei dati.<br><br>Il tempo stimato per riunire tutte le parti rilevanti della tua organizzazione e allinearle su uno schema unificato è di 1-2 mesi. Questo intervallo di tempo dipende maggiormente dal numero di team necessari da coordinare e dal numero di dimensioni + metriche da allineare."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe consiglia di creare uno schema [Experience Data Model](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home) (XDM) personalizzato per Customer Journey Analytics durante l&#39;implementazione di [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/it/docs/experience-platform/collection/home). La creazione di questo schema viene in genere eseguita prima di qualsiasi modifica dell’implementazione o della modifica del codice. Uno schema personalizzato consente di progettare un contratto di dati conciso e specifico per l’organizzazione senza ereditare i vincoli da Adobe Analytics o gestire migliaia di campi non utilizzati. Consulta [Scegli lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) per ulteriori informazioni sui tipi di schemi disponibili per la tua organizzazione.

Gli schemi sono versioni raffinate di come desideri che i dati siano strutturati a lungo termine. Le modifiche agli schemi sono costose perché influiscono sulla raccolta dei dati, sulla convalida e sui servizi a valle. È possibile aggiungere schemi nel tempo in base ai requisiti aziendali; tuttavia, i campi degli schemi non possono essere rimossi una volta che i dati iniziano a fluire in essi.

## Confrontare schemi con visualizzazioni dati

La pipeline dei dati per Customer Journey Analytics contiene aree separate per la raccolta e l’interpretazione dei dati. Durante l’aggiornamento da Adobe Analytics, un passaggio errato comune consiste nel tentare di ricreare proprietà ed eVar con i loro comportamenti in XDM. È invece possibile utilizzare il Web SDK per raccogliere i dati e utilizzare [Visualizzazioni dati](/help/data-views/data-views.md) per determinare l&#39;interpretazione dei dati nei report.

| Layer | Scopo principale | Cosa appartiene | Cosa non appartiene |
|---|---|---|---|
| **Schema XDM** | Definire la struttura durevole e il significato dei dati raccolti | Forma evento ed entità, significato del campo, relazioni, valori consentiti, riutilizzo tra canali | &quot;Slot&quot; numerati (eVar1/prop1), logica di attribuzione/persistenza, soluzioni alternative specifiche per i rapporti |
| **Visualizzazioni dati** | Definire il comportamento dei dati raccolti nell’analisi | Impostazioni dei componenti, comportamento di attribuzione e persistenza, campi derivati, metriche filtrate, metriche calcolate | Significato fondamentale dei campi; tale significato dovrebbe essere stabile nello schema |

## Confrontare gli schemi con la raccolta dati di Adobe Analytics

Il Experience Data Model utilizzato da Customer Journey Analytics offre una flessibilità notevolmente superiore rispetto alla maggior parte delle altre soluzioni Analytics (incluso Adobe Analytics). La creazione di uno schema solido offre all’organizzazione l’opportunità di evitare di riportare vincoli esistenti in altri prodotti Analytics.

| Abitudine comune di Adobe Analytics | Migliore approccio in XDM + CJA |
|---|---|
| Progettazione intorno agli slot numerati (`eVar1`-`eVar250`, `prop1`-`prop75`) | Crea campi con un significato stabile (ad esempio, `search.term`, `content.category`, `user.membershipTier`) e riutilizzali in modo coerente |
| Codifica di persistenza/allocazione/scadenza nel modello di dati | Acquisire fatti durevoli nello schema; applicare l’attribuzione e il comportamento di persistenza a livello di visualizzazione dati |
| Duplicazione dello stesso valore in più variabili per ottenere comportamenti di reporting | Memorizza il valore una volta e crea più componenti (dimensioni/metriche) da esso nelle visualizzazioni dati |
| Creazione di un &quot;campo metrico&quot; univoco per ogni conteggio desiderato | Acquisisci i fatti giusti una volta (spesso come enum/booleani/stringhe), quindi definisci le metriche come conteggi filtrati nelle visualizzazioni dati |
| Progettazione di variabili per la generazione di rapporti di &quot;pre-risoluzione&quot; | Progetta lo schema per acquisire in modo affidabile i fatti e utilizzare le visualizzazioni dati per risolvere la semantica di reporting |

## Definizione di uno schema utilizzando attributi comuni

Uno schema unificato tra canali diventa possibile quando si standardizza un set di attributi riutilizzabili che vengono visualizzati in molti eventi. Alcuni esempi includono:

* **Contesto esperienza:** nome sito/app, ambiente, impostazioni locali, canale, marchio
* **Contesto Percorso:** identificatori campagna, contesto di riferimento, identificatori esperimento
* **Stato utente:** stato di accesso, livello di appartenenza, tipo di account
* **Dettagli interazione:** nome/tipo interazione, area dell&#39;interfaccia utente, etichetta elemento, categoria errore

La chiave è standardizzare ciò che il campo rappresenta indipendentemente dal canale. Evita di modellare lo stesso concetto in modo diverso tra i canali, a meno che non rappresenti realmente concetti diversi. Ad esempio, potrebbe essere opportuno evitare di disporre di campi schema separati per gli ID campagna web e per gli ID campagna mobile. Campi di schema separati rendono più difficile stabilire un ritorno cross-channel sui dati della spesa pubblicitaria. Se nel reporting è necessaria una differenziazione, puoi segmentare per canale o concatenare più campi per fornire tale distinzione. Lo stesso campo schema può essere utilizzato in qualsiasi numero di dimensioni o metriche.

Un modo pratico per supportare più canali mantenendo una strategia a schema singolo consiste nell&#39;utilizzare un pattern **core + estensioni**:

* **Campi core:** che si applicano a livello generale nei diversi canali e team
* **Estensioni:** gruppi di campi specifici per canale o dominio che si applicano solo dove necessario (interazione web, e-commerce, ciclo di vita mobile, specifiche lato server)

Questo modello supporta una singola strategia di schema organizzativo senza costringere ogni team a compilare campi che non si applicano al proprio canale.

## Preferisci gruppi di campi standard in cui rientrano

Adobe consiglia di utilizzare gruppi di campi standardizzati in cui soddisfino le tue esigenze e di estenderli con campi personalizzati per concetti specifici dell’organizzazione.

I gruppi di campi standard consentono in genere di:

* Ridurre l’ambiguità utilizzando la semantica dei campi nota
* Allineare più facilmente i team
* Supporto dell&#39;interoperabilità tra le applicazioni Adobe Experience Platform

I campi personalizzati sono appropriati quando:

* La tua organizzazione dispone di concetti che non vengono mappati in modo chiaro sui campi standard
* Sono necessari attributi aggiuntivi per soddisfare i requisiti di reporting, governance o attivazione
* Desideri rappresentare una tassonomia specifica per l’azienda (ad esempio, categorie di contenuto interne)

## Decidere dove si trova il &quot;significato metrico&quot;

In Adobe Analytics, molti team considerano la variabile `events` come la destinazione delle metriche. In Customer Journey Analytics, puoi modellare le metriche in più modi a seconda di cosa devi contare e di come desideri interpretarle.

Quando si progetta uno schema, attenersi ai fatti. Ad esempio, `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Definisci le metriche nella visualizzazione dati come conteggi e conteggi filtrati su tali fatti. Ad esempio:

* `checkout.step` (enum/stringa) può alimentare:
   * &quot;Pagamento: passaggio di spedizione raggiunto&quot; (conteggio dove `checkout.step == "shipping"`)
   * &quot;Pagamento: livello di pagamento raggiunto&quot;
* `error.type` (enum/stringa) può alimentare:
   * &quot;Errori di convalida&quot;
   * &quot;Errori di autorizzazione&quot;
* `user.isLoggedIn` (booleano) può alimentare:
   * &quot;Sessioni autenticate&quot;
   * &quot;Conversioni autenticate&quot;

>[!TIP]
>
>Quando si decide se qualcosa deve essere un campo dedicato rispetto a un campo derivato in un secondo momento, preferisci acquisire il fatto durevole nello schema, se è ampiamente utile e stabile. È possibile utilizzare i campi derivati per correggere o modificare la forma dei dati dopo la raccolta.

## Mantenimento della parità con Adobe Analytics durante la transizione senza bagaglio dello schema

Alcune organizzazioni devono continuare a generare rapporti con Adobe Analytics durante l’aggiornamento a Customer Journey Analytics. Puoi mantenere la parità senza introdurre artefatti specifici di Analytics nella progettazione di schemi a lungo termine utilizzando il seguente approccio:

1. **Usa percorsi di campi XDM riconosciuti e mappati automaticamente da Adobe Analytics:** Quando invii campi XDM riconosciuti tramite Edge Network ad Adobe Analytics, vengono [mappati automaticamente](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/xdm-var-mapping) senza configurazioni aggiuntive.
1. **Utilizza campi XDM personalizzati per concetti specifici dell&#39;organizzazione:** Tutti i campi XDM che non sono mappati automaticamente a una variabile Analytics vengono inoltrati come [Variabili di dati di contesto](https://experienceleague.adobe.com/it/docs/analytics/implementation/vars/page-vars/contextdata) in Adobe Analytics.
1. **Utilizza le regole di elaborazione di Adobe Analytics per mappare tali variabili di dati di contesto su prop/eVar:** [Le regole di elaborazione](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) ti consentono in ultima analisi di mappare qualsiasi campo XDM personalizzato in qualsiasi eVar o prop. Questo concetto supporta il reporting sulla parità in Adobe Analytics, mantenendo allo stesso tempo lo schema pulito e centrato su Customer Journey Analytics.

## Identificare le parti interessate e definire la proprietà

La progettazione dello schema ha esito positivo quando il significato del campo viene concordato e mantenuto. Sebbene le strutture organizzative siano diverse, i seguenti ruoli partecipano comunemente:

* **Amministratore/analista di Analytics**: definisce le domande di reporting, verifica che i campi rappresentino concetti significativi e rivede la semantica dell&#39;analisi nelle visualizzazioni dati.
* **Proprietario sviluppatore/implementazione**: assicura che i campi possano essere raccolti in modo affidabile utilizzando Web SDK e siano allineati con la strumentazione del livello dati/app.
* **Architetto/ingegnere dati**: garantisce la coerenza dello schema, il riutilizzo tra domini diversi e la compatibilità con i servizi downstream.
* **Interessato privacy/governance**: esamina la minimizzazione dei dati, le aspettative di consenso e i vincoli di utilizzo dei dati.

Definisci un proprietario chiaro per le modifiche allo schema. Uno schema stabile con un controllo disciplinato delle modifiche previene la rottura a valle e riduce la rielaborazione. Prendi in considerazione l’utilizzo di un flusso di lavoro o di uno strumento di governance del tracciamento per rendere accessibili le richieste e gestire il controllo delle modifiche nel tempo.

## Considerazioni sulla privacy e sulla governance

La progettazione dello schema deve riflettere le aspettative sulla privacy e sulla governance, in base alle politiche sulla privacy della tua organizzazione. Durante l’architettura dello schema, considera i seguenti punti:

* Raccogli solo ciò di cui hai bisogno per supportare casi d’uso definiti.
* Assicurati che i requisiti di consenso e utilizzo dei dati si riflettano nella strategia di raccolta. Per ulteriori informazioni, vedere [Utilizzare Web SDK per elaborare i dati sul consenso dei clienti](https://experienceleague.adobe.com/it/docs/experience-platform/landing/governance-privacy-security/consent/sdk).
* Considera come i campi sensibili vengono etichettati e controllati negli strumenti di governance di Adobe Experience Platform. Consulta [Adobe Customer Journey Analytics e governance dei dati](/help/privacy/privacy-overview.md) per ulteriori informazioni.

## Passaggi successivi

Dopo aver definito e concordato un’architettura di schema, puoi iniziare a crearla in Adobe Experience Platform. Per ulteriori informazioni, vedere [Creare uno schema personalizzato da utilizzare con Customer Journey Analytics](cja-upgrade-schema-create.md).
