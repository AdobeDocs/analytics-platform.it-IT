---
title: Un esempio di progetto B2B
description: Scopri come impostare, configurare e creare rapporti sui dati B2B
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 9c60c00818e82a6ca891ab9d90260922437c6cca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 3%

---

# Un esempio di progetto B2B

Questo articolo spiega come impostare, configurare e creare rapporti sui dati B2B a livello di profilo (persona) nel Customer Journey Analytics.

## Connessione

Definisci la connessione in modo da includere tutti i set di dati B2B rilevanti da Experienci Platform. Assicurati di includere e trasformare tutti i set di dati di ricerca rilevanti necessari per un tipico scenario di reporting basato su persona B2B. Consulta [Trasformare i set di dati di ricerca B2B](/help/connections/transform-datasets-b2b-lookups.md) per ulteriori informazioni.

Set di dati da aggiungere alla connessione:

| Set di dati | Schema | Tipo di schema | Classe base | Descrizione |
|---|---|---|---|---|
| Set di dati sull’attività B2B | Schema attività B2B | Evento | XDM ExperienceEvent | Un ExperienceEvent è una registrazione fattuale di ciò che è accaduto, incluso il momento e l’identità dell’individuo coinvolto. ExperienceEvents possono essere espliciti (azioni umane direttamente osservabili) o impliciti (generati senza un’azione umana diretta) e vengono registrati senza aggregazione o interpretazione. Sono fondamentali per l’analisi del dominio del tempo in quanto consentono l’osservazione e l’analisi dei cambiamenti che si verificano in una determinata finestra temporale e il confronto tra più finestre temporali per monitorare le tendenze. |
| Set di dati persona B2B | Schema persona B2B | Profilo | Profilo individuale XDM | Un profilo individuale XDM costituisce una rappresentazione unica degli attributi e degli interessi sia di individui identificati che parzialmente identificati. I profili meno identificati possono contenere solo segnali comportamentali anonimi, come i cookie del browser, mentre i profili altamente identificati possono contenere informazioni personali dettagliate come nome, data di nascita, posizione e indirizzo e-mail. Man mano che un profilo cresce, diventa un solido archivio di informazioni personali, informazioni di identificazione, dettagli di contatto e preferenze di comunicazione per un individuo. |
| Set di dati relazione persona account B2B | Schema di relazione della persona dell’account B2B | Ricerca | Relazione della persona dell’account aziendale XDM | XDM Business Account Person Relation è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di una persona associata a un account aziendale. |
| Set di dati relazione persona opportunità B2B | Schema di relazione persona opportunità B2B | Ricerca | Relazione della persona dell’opportunità di business XDM | La relazione tra persona opportunità aziendale XDM è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di una persona associata a un’opportunità aziendale. |
| Set di dati dei membri dell’elenco di marketing B2B | Schema membri di elenchi marketing B2B | Ricerca | Membri dell’elenco di marketing XDM | XDM Business Marketing List Members è una classe XDM (Experience Data Model) standard che descrive membri, persone o contatti associati a un elenco di marketing. |
| Set di dati dei membri della campagna B2B | Schema membro della campagna B2B | Ricerca | Membri della campagna aziendale XDM | XDM Business Campaign Members è una classe XDM (Experience Data Model) standard che descrive un contatto o un lead associato a una campagna aziendale. |
<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


La relazione tra gli schemi di ricerca, lo schema di profilo e lo schema evento è definita nella configurazione B2B all’interno di Experienci Platform. Vedere Schemi in [Edizione B2B di Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html) e [Definire una relazione molti-a-uno tra due schemi in Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html) per ulteriori dettagli.

![Relazione tra schemi B2B](assets/classes.png)

Per ogni set di dati di ricerca aggiunto alla connessione, devi definire esplicitamente la relazione con un set di dati evento utilizzando **[!UICONTROL Key]** e **[!UICONTROL Matching key]** nel **[!UICONTROL Edit dataset]** . Ad esempio:

![Chiave - Chiave corrispondente](assets/key-matchingkey.png)

Quattro schemi vengono utilizzati esplicitamente per collegare lo schema Persona ad altri schemi rilevanti: Account, Opportunità, Campaign e Marketing List. Questi schemi si basano sulle seguenti classi di schema:

* Relazione della persona dell’account aziendale XDM
* Relazione della persona dell’opportunità di business XDM
* Membri dell’elenco di marketing aziendale XDM
* Membri della campagna aziendale XDM

Per ogni set di dati di ricerca, per uno schema basato su tale classe di schema, abilita anche **[!UICONTROL Transform dataset]** per garantire che i dati vengano trasformati per le ricerche basate su persone. Consulta [Trasformare i set di dati per le ricerche B2B](/help/connections/transform-datasets-b2b-lookups.md) per ulteriori informazioni.

La tabella seguente fornisce un esempio di panoramica di [!UICONTROL Person ID], [!UICONTROL Key], e [!UICONTROL Matching key] per ciascuno dei set di dati.


| Set di dati | ID persona | Chiave | Chiave corrispondente (nel set di dati dell’evento) |
|---|---|---|---|
| Set di dati sull’attività B2B | `personKey.sourceKey` | | |
| Set di dati persona B2B | `b2b.personKey.sourceKey` | | |
| Set di dati della persona dell’account B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Set di dati dell’opportunità B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Set di dati dei membri della campagna B2B | | `personKey.sourceKey` | `personKey.sourceKey` |
| Set di dati dell’elenco di marketing B2B | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

Consulta [Aggiungere e configurare i set di dati](../../connections/create-connection.md) per ulteriori informazioni su come configurare le impostazioni per un set di dati.


## Visualizzazione dati

Per poter accedere alle dimensioni e alle metriche B2B rilevanti durante la creazione di un progetto Workspace, devi definire di conseguenza la visualizzazione dati.

Puoi aggiungere i seguenti componenti come dimensioni alla visualizzazione dati per garantire la possibilità di creare rapporti a livello basato su persone in base ai dati B2B. I nomi dei componenti vengono modificati per maggiore chiarezza.

| Nome componente | Set di dati | Tipo di dati dello schema | Percorso schema |
|---|---|---|---|
| Persona | Attività B2B | Stringa | `personID` |
| Account | Persona dell’account B2B | Stringa | `accountKey.sourceID` |
| Campaign | Membro della campagna B2B | Stringa | `campaignKey.sourceKey` |
| Nome elenco di marketing | Elenco di marketing B2B | Stringa | `marketingListID` |
| opportunità | Persona opportunità B2B | Stringa | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## Workspace

Ora che i componenti sono definiti correttamente nella visualizzazione dati, puoi creare rapporti e visualizzazioni B2B specifici nel progetto Workspace.

Di seguito è riportato un progetto di esempio che si basa sulla connessione e sulla visualizzazione dati descritte in precedenza.

![Progetto di esempio](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
