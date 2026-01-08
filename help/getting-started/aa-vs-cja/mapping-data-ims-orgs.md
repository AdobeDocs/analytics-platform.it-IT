---
title: Mappare i dati di Analytics da più organizzazioni IMS
description: Scopri come richiedere la mappatura dei dati dalle suite di rapporti di più organizzazioni IMS di origine a un’organizzazione IMS di destinazione.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Mappare i dati di Analytics da più organizzazioni IMS

Il connettore di origine di Analytics può acquisire solo dati dalle suite di rapporti di Adobe Analytics che appartengono alla stessa organizzazione per la quale hai i diritti per utilizzare Customer Journey Analytics. La funzione per mappare i dati di Analytics provenienti da più organizzazioni IMS offre una soluzione a questo limite. Il processo per abilitare questa funzione è descritto in questo articolo.


## Scenario

Hai effettuato il provisioning con più organizzazioni IMS e disponi di dati Analytics in più suite di rapporti per queste organizzazioni IMS. Questa configurazione potrebbe essere il risultato di:

* acquisizioni o fusioni
* requisiti della struttura organizzativa
* vincoli di distribuzione regionali

Non puoi creare rapporti sulla combinazione di dati provenienti da più suite di rapporti in più organizzazioni IMS in Customer Journey Analytics. Il motivo di questa limitazione è che l’acquisizione dei dati da Adobe Analytics in Experience Platform tramite il connettore di origine di Analytics supporta solo l’acquisizione di dati di proprietà di una singola organizzazione IMS. L’organizzazione IMS per la quale hai effettuato il provisioning e che utilizzi per accedere ad Adobe Analytics, Experience Platform e Customer Journey Analytics.

Con la funzionalità *mappa dati di Analytics da più organizzazioni IMS*, puoi richiedere ad Adobe di mappare i dati. La funzionalità utilizza il connettore di origine di Analytics per mappare i dati delle suite di rapporti che risiedono in più organizzazioni IMS *source* ai set di dati che fanno parte di un&#39;organizzazione IMS *destination*. Ad esempio:

| Illustrazione | Spiegazione |
|---|---|
| ![Mappatura dei dati tra più organizzazioni IMS](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Questa mappatura consente di creare rapporti sulle suite di rapporti esistenti nell’organizzazione IMS 1, nell’organizzazione IMS 2 e nell’organizzazione IMS 3 da una connessione in Customer Journey Analytics fornita nell’organizzazione IMS 3. |

{style="table-layout:fixed"}

## Come usare

Per configurare e abilitare la funzionalità *mappare i dati di Analytics da più organizzazioni IMS*, devi richiedere la mappatura tramite il tuo account manager Adobe. A tale scopo, effettua le seguenti operazioni:

1. In qualità di amministratore dell’organizzazione IMS di destinazione, richiedi le e-mail di approvazione da tutti gli amministratori dell’organizzazione IMS di origine per i quali desideri mappare le suite di rapporti. Per richiedere l’approvazione agli amministratori dell’organizzazione IMS di origine, puoi utilizzare il testo seguente come modello per l’e-mail.

   | Modello e-mail di esempio |
   | --- |
   | *Rappresentante del nome della società*, per consentire all’organizzazione di destinazione selezionata di accedere alle seguenti organizzazioni IMS (elenco delle organizzazioni IMS di origine), è necessario assicurarsi che un amministratore di ciascuna organizzazione IMS invii la propria approvazione per consentire l’accesso ai propri dati. Questo consente di rispettare le autorizzazioni di accesso ai dati da qualsiasi organizzazione IMS interessata. Per ottenere la corretta approvazione, rivolgiti a un amministratore Adobe registrato per ogni organizzazione amministratore affinché risponda a questa e-mail con il proprio nome e l’organizzazione IMS che rappresenta, indicando &quot;Approvo&quot; per indicare che ha dato la sua approvazione affinché i dati di questa organizzazione IMS vengano visualizzati nell’organizzazione di destinazione [elenca organizzazione IMS di destinazione]. Nota: questo amministratore deve essere un amministratore registrato in Adobe come amministratore per tale organizzazione IMS. |

1. Invia un’e-mail come amministratore dell’organizzazione IMS di destinazione all’account manager Adobe che richiede la mappatura dalle suite di rapporti all’interno di più organizzazioni IMS di origine all’organizzazione IMS di destinazione. Allega le e-mail di approvazione ricevute dagli amministratori dell’organizzazione IMS di origine.

Una volta che l’account manager riceve l’e-mail con la richiesta di mappare i dati di Analytics da più organizzazioni, la richiesta viene rivista in Adobe. L&#39;Account Manager contatta l&#39;utente per eventuali domande aggiuntive, corsi di formazione facoltativi e altre informazioni.

Una volta approvata, viene creata la mappatura richiesta e ricevi una notifica. Il nome dell&#39;organizzazione IMS di origine viene aggiunto al nome della suite di rapporti nell&#39;[elenco delle suite di rapporti di Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) in Experience Platform.

## Limitazioni e rischi

Le seguenti limitazioni si applicano alla funzionalità *mappa dati di Analytics da più organizzazioni IMS*:

* Puoi collegare una suite di rapporti una sola volta tra le diverse organizzazioni.
* Prima di poter richiedere l’eliminazione del mapping, è necessario eliminare tutte le connessioni per un’organizzazione IMS definita come organizzazione IMS di destinazione in un mapping.
* Gli ECID non sono compatibili tra le organizzazioni IMS di origine mappate e non sono compatibili con l’organizzazione IMS di destinazione.
* Un utente con autorizzazioni sufficienti per configurare il connettore di origine di Analytics nell’organizzazione IMS di destinazione può acquisire dati di Analytics da qualsiasi organizzazione IMS di origine mappata. Non viene verificata alcuna autorizzazione per tale utente per alcuna delle organizzazioni IMS di origine.
