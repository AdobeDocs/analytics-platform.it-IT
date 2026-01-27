---
title: Mappare i dati di Analytics da più organizzazioni IMS
description: Scopri come richiedere la mappatura dei dati dalle suite di rapporti di più organizzazioni IMS di origine a un’organizzazione IMS di destinazione.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 925da525b61c2a24156159f4029303c297e0af10
workflow-type: tm+mt
source-wordcount: '1162'
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

1. Invia un’e-mail all’account manager Adobe per conto dell’amministratore dell’organizzazione IMS di destinazione che richiede la mappatura dalle suite di rapporti all’interno di più organizzazioni IMS di origine all’organizzazione IMS di destinazione. Allega le e-mail di approvazione ricevute dagli amministratori dell’organizzazione IMS di origine.

Una volta che l’account manager di Adobe riceve l’e-mail con la richiesta di mappare i dati di Analytics da più organizzazioni, la richiesta viene rivista in Adobe. L’account manager Adobe ti contatta per eventuali domande aggiuntive, corsi di formazione facoltativi e altre informazioni.

Una volta approvata, viene creata la mappatura richiesta e ricevi una notifica. Il nome dell&#39;organizzazione IMS di origine viene aggiunto al nome della suite di rapporti nell&#39;[elenco delle suite di rapporti di Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) in Experience Platform.


## Limitazioni

Le seguenti limitazioni si applicano alla funzionalità *mappa dati di Analytics da più organizzazioni IMS*:

* Puoi collegare una suite di rapporti una sola volta tra le diverse organizzazioni.
* Prima di poter richiedere l’eliminazione del mapping, è necessario eliminare tutte le connessioni per un’organizzazione IMS definita come organizzazione IMS di destinazione in un mapping.
* Gli ECID non sono compatibili tra le organizzazioni IMS di origine mappate e non sono compatibili con l’organizzazione IMS di destinazione.


## Considerazioni

Prima di richiedere la funzionalità *Mappa dati di Analytics da più organizzazioni IMS*, considera i seguenti argomenti:

### Profili

Una volta approvata la funzionalità *mappa dati di Analytics da più organizzazioni IMS*, puoi aggiungere dati ad Experience Platform per una o più suite di rapporti nell&#39;organizzazione IMS di destinazione. Questa operazione viene eseguita tramite la configurazione del [connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). I set di dati di destinazione vengono quindi creati in Experience Platform. Come parte di questa configurazione e del processo, puoi inviare i dati del profilo da una o più suite di rapporti al servizio Profilo.

Stimare il numero totale di profili risultanti dalla configurazione e dal processo, come descritto in precedenza. Assicurati che il numero totale rientri nel numero di profili a cui hai diritto contrattualmente per l’organizzazione di destinazione. Applica [regole e condizioni di filtro](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} per includere o escludere i dati in modo selettivo dall&#39;acquisizione nel servizio Profilo. Oppure disabilita l’opzione per inviare i dati del profilo al servizio Profilo per le suite di rapporti pertinenti.


### Unione

Una volta approvata la funzionalità *mappa dati di Analytics da più organizzazioni IMS*, puoi aggiungere dati ad Experience Platform per una o più suite di rapporti nell&#39;organizzazione IMS di destinazione. Questa operazione viene eseguita tramite la configurazione del [connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). I set di dati di destinazione per le suite di rapporti configurate nel connettore di origine di Analytics vengono quindi creati in Experience Platform. Come parte di questa configurazione e del processo, puoi inviare i dati del profilo da una o più suite di rapporti al servizio Profilo.

Puoi utilizzare l&#39;unione [basata sui campi](/help/stitching/fbs.md) e [basata sui grafici](/help/stitching/gbs.md) nei set di dati di destinazione. Quando utilizzi l’unione basata su grafico su uno o più set di dati di destinazione, assicurati di rispettare i diritti contrattuali per il numero di profili, come descritto nella sezione [Profili](#profiles).

Se non disponi della licenza per Real-Time Customer Profile, ma desideri comunque utilizzare l&#39;unione basata su grafico su uno o più set di dati di destinazione, assicurati di abilitare solo il [servizio Identity](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) per questi set di dati di destinazione.


### Autorizzazioni

Un utente con autorizzazioni sufficienti per configurare il connettore di origine di Analytics nell’organizzazione IMS di destinazione può acquisire dati di Analytics da qualsiasi organizzazione IMS di origine mappata. Non viene verificata alcuna autorizzazione per tale utente per alcuna delle organizzazioni IMS di origine.

### Rapporto sui dati

La funzionalità *mappa dati di Analytics da più organizzazioni IMS* è solo un primo passo per garantire che sia possibile utilizzare i dati come parte di una [connessione](/help/connections/overview.md) di Customer Journey Analytics, una o più [visualizzazioni dati](/help/data-views/data-views.md) e [progetti Workspace](/help/analysis-workspace/home.md). È necessario esaminare attentamente i dati ora disponibili in un’organizzazione IMS. Inoltre, prima di creare rapporti appropriati su questi dati, considera funzioni quali la preparazione dei dati, i campi derivati, le tabelle di ricerca aggiuntive e altro ancora.
