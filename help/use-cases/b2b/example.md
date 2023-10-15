---
title: Un esempio di progetto B2B
description: Scopri come impostare, configurare e creare rapporti sui dati B2B
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: c4a4dcd0e4c0d7473570c2db3aa3d99e34c2a1cf
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 13%

---

# Un esempio di progetto B2B

Questo articolo spiega, attraverso esempi, come impostare, configurare e creare rapporti sui dati B2B nel Customer Journey Analytics.

## Connessione

Definisci la connessione in modo da includere tutti i set di dati B2B rilevanti da Experienci Platform. Ciò include i set di dati di ricerca importanti necessari in una tipica configurazione B2B in Experienci Platform. Consulta [Aggiungere dati a livello di account come set di dati di ricerca](b2b.md) per ulteriori informazioni.

Set di dati da aggiungere alla connessione:

| Set di dati | Schema | Tipo di schema | Classe base | Descrizione |
|---|---|---|---|---|
| Set di dati sull’attività B2B | Schema attività B2B | Evento | XDM ExperienceEvent | Un ExperienceEvent è una registrazione fattuale di ciò che è accaduto, incluso il momento e l’identità dell’individuo coinvolto. ExperienceEvents possono essere espliciti (azioni umane direttamente osservabili) o impliciti (generati senza un’azione umana diretta) e vengono registrati senza aggregazione o interpretazione. Sono fondamentali per l’analisi del dominio del tempo in quanto consentono l’osservazione e l’analisi dei cambiamenti che si verificano in una determinata finestra temporale e il confronto tra più finestre temporali per monitorare le tendenze. |
| Set di dati persona B2B | Schema persona B2B | Profilo | Profilo individuale XDM | Un profilo individuale XDM costituisce una rappresentazione unica degli attributi e degli interessi sia di individui identificati che parzialmente identificati. I profili meno identificati possono contenere solo segnali comportamentali anonimi, come i cookie del browser, mentre i profili altamente identificati possono contenere informazioni personali dettagliate come nome, data di nascita, posizione e indirizzo e-mail. Man mano che un profilo cresce, diventa un solido archivio di informazioni personali, informazioni di identificazione, dettagli di contatto e preferenze di comunicazione per un individuo. |
| Set di dati dei membri della campagna B2B | Schema membro della campagna B2B | Ricerca | Membri della campagna aziendale XDM | XDM Business Campaign Members è una classe XDM (Experience Data Model) standard che descrive un contatto o un lead associato a una campagna aziendale. |
| Set di dati account B2B | Schema dell’account B2B | Ricerca | Account aziendale XDM | XDM Business Account è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di un account aziendale. |
| Set di dati relazione persona account B2B | Schema di relazione della persona dell’account B2B | Ricerca | Relazione della persona dell’account aziendale XDM | XDM Business Account Person Relation è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di una persona associata a un account aziendale. |
| Set di dati dell’opportunità B2B | Schema opportunità B2B | Ricerca | Opportunità di business XDM | XDM Business Opportunity è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di un’opportunità aziendale. |
| Set di dati relazione persona opportunità B2B | Schema di relazione persona opportunità B2B | Ricerca | Relazione della persona dell’opportunità di business XDM | La relazione tra persona opportunità aziendale XDM è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di una persona associata a un’opportunità aziendale. |
| Set di dati della campagna B2B | Schema campagna B2B | Ricerca | Campagna aziendale XDM | XDM Business Campaign è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di una campagna aziendale. |
| Set di dati dell’elenco di marketing B2B | Schema elenco di marketing B2B | Ricerca | Elenco di marketing XDM | XDM Business Marketing List è una classe XDM (Experience Data Model) standard che acquisisce le proprietà minime richieste di un elenco di marketing. Gli elenchi di marketing ti consentono di dare la priorità ai potenziali clienti che hanno maggiori probabilità di acquistare il tuo prodotto. |
| Set di dati dei membri dell’elenco di marketing B2B | Schema membri di elenchi marketing B2B | Ricerca | Membri dell’elenco di marketing XDM | XDM Business Marketing List Members è una classe XDM (Experience Data Model) standard che descrive membri, persone o contatti associati a un elenco di marketing. |

La relazione tra gli schemi di ricerca, lo schema di profilo e lo schema evento è definita nella configurazione B2B all’interno di Experienci Platform. Vedere Schemi in [Edizione B2B di Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) e [Definire una relazione molti-a-uno tra due schemi in Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) per ulteriori dettagli.

![Relazione tra schemi B2B](assets/classes.png)

Per ogni set di dati di ricerca aggiunto alla connessione, è necessario definire esplicitamente la relazione con un set di dati evento utilizzando Chiave e Chiave corrispondente nella finestra di dialogo Modifica set di dati. Ad esempio:

![Chiave - Chiave corrispondente](assets/key-matchingkey.png)


La tabella seguente fornisce un esempio di panoramica di [!UICONTROL Person ID], [!UICONTROL Key], e [!UICONTROL Matching key] per ciascuno dei set di dati.


| Set di dati | ID persona | Chiave | Chiave corrispondente (nel set di dati dell’evento) |
|---|---|---|---|
| Set di dati sull’attività B2B | `personKey.sourceKey` | | |
| Set di dati persona B2B | `b2b.personKey.sourceKey` | | |
| Set di dati account B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Set di dati dell’opportunità B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Set di dati della campagna B2B | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| Set di dati dell’elenco di marketing B2B | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


Nella tabella *_organizationID*`.interaction.*`, si riferisce al gruppo di campi personalizzato aggiunto allo schema di attività B2B per definire la relazione con l’account B2B e lo schema di opportunità B2B. Il `listOperations.listKey.sourceKey` fa riferimento al gruppo di campi Aggiungi all’elenco aggiunto allo schema di attività B2B per monitorare quando una persona viene aggiunta a un elenco specifico.

Consulta [Aggiungere e configurare i set di dati](../../connections/create-connection.md) per ulteriori informazioni su come configurare le impostazioni per un set di dati.


## Visualizzazioni dati

Per poter accedere alle dimensioni e alle metriche B2B rilevanti durante la creazione di un progetto Workspace, devi definire di conseguenza la visualizzazione dati.

Questa sezione fornisce consigli e suggerimenti su quali dimensioni e metriche includere durante la definizione del [componenti](../../data-views/create-dataview.md#components) della visualizzazione dati.

Per ciascun componente, vengono forniti il nome, il percorso dello schema e (se applicabile) i dettagli sulla configurazione.


### Set di dati per attività B2B

Il set di dati dell’attività B2B contiene gli eventi di esperienza rilevanti ed è richiesto come parte di una connessione.

+++ Dettagli

#### Metriche

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Aggiungi a campagna | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Aggiungi all’opportunità | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Applicazione chiusa | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `application.close` |
| Avvio applicazione | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `application.launch` |
| Flusso campagna | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Cassa | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.checkouts` |
| Converti lead | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| E-mail selezionata | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| E-mail consegnata | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| E-mail aperta | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| E-mail inviata | Stringa | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| E-mail per cui è stata annullata l’iscrizione | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Modulo compilato | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `web.formFilledOut` |
| Modulo avviato | Stringa | `web.fillOutForm.webFormName` | |
| Lead | Stringa | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunità aggiornata | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Prezzo | Doppio | *_organizationID*`.interactions.products.price` |  |
| Priorità | Intero | `leadOperation.changeScore.priority` |  |
| Aggiungi elenco di produzione | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Elenco prodotti aperto | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Visualizzazione produzione | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Acquisti | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Rimuovi dall’opportunità | Stringa | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Salva per dopo | Stringa | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Chiave account (chiave di origine) | Stringa | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Stato convertito | Stringa | `leadOperation.convertLead.convertedStatus` | |
| Tipo evento | Stringa | `eventType` | |
| Nome modulo | Stringa | `leadOperation.newLead.formName` | |
| Identificatore | Stringa | `_id` | |
| Viene inviata una notifica | Booleano | `leadOperation.convertLead.isSentNotificationEmail` | |
| Parole chiave | Stringa | `search.keywords` | |
| ID elenco | Stringa | `listOperations.listID` | |
| Nome elenco | Stringa | `leadOperation.newLead.listName` | |
| Nome pagina | Stringa | `web.webPageDetails.name` | |
| Chiave persona (chiave sorgente) | Stringa | `personKey.sourceKey` | |
| Prodotto da | Stringa | productby | |
| Nome prodotto | Stringa | *_organizationID*`.Interactions.products.name` | |
| Ruolo | Stringa | `opportunityEvent.role` | |
| Marca temporale | Data-ora | `timestamp` | Formato data-ora: **[!UICONTROL Day]** |
| URL | Stringa | `web.webPageDetails.URL` | |
| Nome modulo web | Stringa | `web.fillOutForm.webFormName` | |
| URL prodotto | Stringa | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


### Set di dati persona B2B

Il set di dati Persona B2B contiene i profili rilevanti.

+++ Dettagli


#### Metriche

Nessun componente metrico è definito come parte di questo set di dati.


#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Data ultima attività | Data-ora | `extSourceSystemAudit.lastActivityDate` | Formato data-ora: **[!UICONTROL Day]** |
| ID persona | Stringa | `personID` | |

{style="table-layout:auto"}

+++ Dettagli

### Set di dati dell’opportunità B2B

Il set di dati Opportunità B2B contiene le opportunità rilevanti.

+++ Dettagli

#### Metriche

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Ricavi previsti | Doppio | `expectedRevenue.amount` | Comportamento: **[!UICONTROL Count values]** |
| Importo dell’opportunità | Doppio | `opportunityAmount.amount` | Comportamento: **[!UICONTROL Count values]** |
| Fase dell’opportunità - Libro chiuso | Stringa | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `Closed - Booked` |
| Fase dell’opportunità - Prospect | Stringa | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `Prospect` |
| Fase dell’opportunità - Qualifica | Stringa | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Fase dell’opportunità - Definizione della soluzione | Stringa | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Corrispondenza:**[!UICONTROL If all criteria are met]**<br/> Criteri: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Flag chiuso | Booleano | `isClosed` | |
| ID Azienda | Stringa | `opportunityID` | |
| Categoria previsione | Stringa | `forecastCategoryName` | |
| Data ultima attività | Data-ora | `lastActivityDate` | Formato data-ora: **[!UICONTROL Day]** |
| Sorgente lead | Stringa | `leadSource` | |
| Nome dell’opportunità | Stringa | `opportunityName` | |
| Stato dell’opportunità | Stringa | `opportunityStage` | |
| Flag acquisizione | Booleano | `isWon` | |

{style="table-layout:auto"}

+++

### Set di dati della campagna B2B

Il set di dati della campagna B2B contiene dati della campagna.

+++ Dettagli

#### Metriche

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Costo campagna | Doppio | `actualCost.amount` | |

{style="table-layout:auto"}


#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| ID campagna | Stringa | `campaignID` | |
| Nome della campagna | Stringa | `campaignName` | |
| Data di inizio della campagna | Data-ora | `campaignStartDate` | Formato data-ora: **[!UICONTROL Day]** |
| Nome canale | Stringa | `channelName` | |
| ID campagna principale | Stringa | `parentCampaignID` | |

{style="table-layout:auto"}

+++


### Set di dati dell’account B2B

Il set di dati dell’account B2B contiene i dati dell’account.

+++ Dettagli

#### Metriche

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Entrate annuali | Doppio | `accountOrganization.annualRevenue.amount` | |
| Numero di dipendenti | Intero | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Identificatore account | Stringa | `accountID` | |
| Tipo di account | Stringa | `accountType` | |
| Città | Stringa | `accountBillingAddress.city` | |
| Paese | Stringa | `accountBillingAddress.country` | |
| Settore | Stringa | `accountOrganization.industry` | |
| Area geografica | Stringa | `accountBillingAddress.region` | |
| ID sorgente | Stringa | `accountKey.sourceID` | |
| ID istanza sorgente | Stringa | `accountKey.sourceInstanceID` | |
| Chiave sorgente | Stringa | `accountKey.sourceKey` | |
| Tipo di origine | Stringa | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


### Set di dati dei membri della campagna B2B

Il set di dati Membro della campagna B2B contiene le interazioni dei membri delle campagne.

+++ Dettagli

#### Metriche

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| Rifiutato | Lungo | *_organizationID*`.campaignBounced` | Comportamento: **[!UICONTROL Count values]** |
| Clic effettuato | Lungo | *_organizationID*`.campaignClicked` | Comportamento: **[!UICONTROL Count values]** |
| Aperto | Lungo | *_organizationID*`.CampaignOpened` | Comportamento: **[!UICONTROL Count values]** |
| Inviate | Lungo | *_organizationID*`.campaignSent` | Comportamento: **[!UICONTROL Count values]** |
| Abbonato | Lungo | *_organizationID*`.campaignSubscribed` | Comportamento: **[!UICONTROL Count values]** |
| Registrazioni webinar | Lungo | *_organizationID*`.Registrations` | Comportamento: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

#### Dimensioni

| Nome componente | Tipo di dati dello schema | Percorso schema | Configurazione |
|---|---|---|---|
| ID campagna | Stringa | `campaignID` | |
| ID membro della campagna | Stringa | `campaignMemberID` | |
| Stato membro della campagna | Stringa | `memberStatus` | |
| Motivo dello stato del membro della campagna | Stringa | `memberStatusReason` | |
| Data di creazione | Data-ora | `extSourceSystemAudit.createdDate` | Formato data-ora: **[!UICONTROL Day]** |
| Data della prima risposta | Stringa | `firstRespondedDate` | Formato data-ora: **[!UICONTROL Day]** |
| Ha raggiunto il successo | Booleano | `hasReachedSuccess` | |
| Ha risposto | Booleano | `hasResponded` | |
| Ultimo stato | Stringa | `lastStatus` | |
| Data ultimo aggiornamento | Data-ora | `extSourceSystemAudit.lastUpdatedDate` | Formato data-ora: **[!UICONTROL Day]** |
| Data di iscrizione | Data-ora | `membershipDate` | Formato data-ora: **[!UICONTROL Day]** |
| Cadenza dello sviluppo | Stringa | `nurtureCadence` | |
| Nome della traccia di sviluppo | Stringa | `nurtureTrackName` | |
| ID persona | Stringa | `personID` | |
| Data di raggiungimento del successo | Data-ora | `reachedSuccessDate` | Formato data-ora: **[!UICONTROL Day]** |
| ID registrazione webinar | Stringa | `webinarRegistrationID` | |
| URL di registrazione al webinar | Stringa | `webinarConfirmationUrl` | |
| isExausted | Booleano | isExausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

Una volta definiti correttamente i componenti, ora puoi creare visualizzazioni B2B specifiche nel progetto Workspace.

Di seguito è riportato un progetto Workspace di esempio che si basa sulla connessione e sulla visualizzazione dati descritte in precedenza. Per ulteriori dettagli, consulta le descrizioni di ciascuna visualizzazione.

+++ Dettagli

![Visualizzazioni](assets/visualizations.png)

+++

