---
title: Creare una connessione
description: Descrive come creare una connessione a un set di dati di Platform in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: b17bdb20b120ec37a9f11425062bc7f8bcebd7e7
workflow-type: tm+mt
source-wordcount: '1896'
ht-degree: 99%

---

# Creare una connessione

Una connessione consente di integrare i set di dati da [!DNL Adobe Experience Platform] a [!UICONTROL Workspace]. Per creare rapporti sui set di dati [!DNL Experience Platform] bisogna prima stabilire una connessione tra i set di dati in [!DNL Experience Platform] e [!UICONTROL Workspace].

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Autorizzazioni necessarie

Per creare una connessione CJA, è necessario disporre delle seguenti autorizzazioni in [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Modellazione dati: visualizzare schemi, gestire schemi
* Gestione dati: visualizzare i set di dati, gestire i set di dati
* Acquisizione dei dati: gestisci origini

Customer Journey Analytics
* Accesso amministratore prodotto

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.

## Seleziona sandbox e set di dati

1. Vai a [https://analytics.adobe.com](https://analytics.adobe.com) e accedi con il tuo Adobe ID.

1. Fai clic sull’icona [!DNL Customer Journey Analytics].

1. Fai clic sulla scheda **[!UICONTROL Connections]**.

1. Fai clic su **[!UICONTROL Create new connection]** in alto a destra.

   ![Crea connessione](assets/create-connection0.png)

1. Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.

   Adobe Experience Platform fornisce [sandboxe](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come “silos di dati” che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.  Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamare.

   >[!IMPORTANT]
   >
   >Non è possibile accedere ai dati tra sandbox diverse, ovvero è possibile combinare solo set di dati che si trovano all’interno della stessa sandbox.

1. Seleziona uno o più set di dati da richiamare in [!UICONTROL Customer Journey Analytics] e fai clic su **[!UICONTROL Add]**.

   (Se sono presenti molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca **[!UICONTROL Search datasets]** sopra l’elenco dei set di dati).

## Configurare il set di dati

Sul lato destro è ora possibile configurare i set di dati aggiunti.

![Configurare il set di dati](assets/create-connection.png)

1. **[!UICONTROL Dataset type]**: per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo di set di dati in base ai dati in arrivo.

   >[!IMPORTANT]
   >
   >È necessario aggiungere almeno un set di dati evento come parte di una connessione.


   Esistono 3 tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile] e dati [!UICONTROL Lookup].

   | Tipo di set di dati | Descrizione | Marca temporale | Schema | ID persona |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc.). Questi possono essere ad esempio tipici dati di click-stream, con un ID cliente o un ID cookie e un timestamp. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | È impostato automaticamente sul campo marca temporale predefinito dagli schemi basati sull’evento in [!UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuno di questi può essere utilizzato come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento), ecc. |
   | [!UICONTROL Lookup] | Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati ricerca che mappano ID numerici nei dati evento ai nomi dei prodotti. Consulta [questo caso d’uso](/help/use-cases/b2b.md) per un esempio. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
   | [!UICONTROL Profile] | Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.<br>![ID persona ](assets/person-id.png)**Nota**: se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire in modo efficace i set di dati è necessario utilizzare lo stesso ID persona. |

1. **[!UICONTROL Dataset ID]**: questo ID viene generato automaticamente.

1. **[!UICONTROL Time stamp]**: solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in [!UICONTROL Experience Platform].

1. **[!UICONTROL Schema]**: questo è lo [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=it) in base a cui il set di dati è stato creato in Adobe Experience Platform.

1. **[!UICONTROL Person ID]**: seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.

   >[!IMPORTANT]
   >
   >Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Visualizza [questo video](https://youtu.be/G_ttmGl_LRU) su come definire un’identità in Experience Platform.

1. Fai clic su **[!UICONTROL Next]** per passare alla finestra di dialogo [!UICONTROL Enable Connection].

### Utilizzare Identity Map come ID persona

Customer Journey Analytics ora supporta la possibilità di utilizzare Identity Map per il proprio ID persona. Identity Map è una struttura di dati a mappa che consente a un utente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. Identity Map esiste su ogni riga/evento caricato e viene compilato di conseguenza per ogni riga.

Identity Map è disponibile per qualsiasi set di dati che utilizza uno schema basato sulla classe [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). Quando selezioni un set di dati da includere in una connessione CJA, puoi selezionare un campo come ID principale o Identity Map:

![](assets/idmap1.png)

Se selezioni Identity Map, ottieni due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| [!UICONTROL Use Primary ID Namespace] | Questo indica a CJA, per riga, di trovare l’identità nella Identity Map contrassegnata con un attributo primary=true e utilizzarla come ID persona per quella riga. Questo significa che si tratta della chiave primaria che verrà utilizzata in Experience Platform per il partizionamento. È anche il candidato principale per l’utilizzo come ID visitatore di CJA (a seconda di come il set di dati è configurato in una connessione CJA). |
| [!UICONTROL Namespace] | (Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID primario). Gli spazi dei nomi di identità sono un componente di [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it) che fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, CJA cercherà l’Identity Map di ogni riga per questa chiave dello spazio dei nomi e utilizzerà l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché CJA non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi di nomi sono effettivamente presenti, nel menu a discesa vengono elencati tutti gli spazi di nomi possibili. È necessario sapere quali spazi di nomi sono specificati nei dati, non è possibile rilevare automaticamente questo valore. |

### Casi edge di Identity Map

Questa tabella mostra le due opzioni di configurazione quando i casi edge sono presenti e come vengono gestiti:

| Opzione | Nessun ID presente in Identity Map | Nessun ID contrassegnato come primario | Gli ID multipli sono contrassegnati come primari | L’ID singolo è contrassegnato come primario | Spazio dei nomi non valido con un ID contrassegnato come primario |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] controllato** | La riga viene rilasciata da CJA. | La riga viene rilasciata da CJA, in quanto non è specificato alcun ID primario. | Tutti gli ID contrassegnati come primari, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Sono quindi ordinati alfabeticamente. Con questo nuovo ordinamento, il primo spazio dei nomi con il primo ID viene utilizzato come ID persona. | Il singolo ID contrassegnato come primario viene utilizzato come ID persona. | Anche se lo spazio dei nomi può non essere valido (non presente in AEP), CJA utilizza l’ID primario nello spazio dei nomi come ID persona. |
| **[!UICONTROL Specific Identity Map namespace] selezionato** | La riga viene rilasciata da CJA. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. (Al momento della creazione della connessione è possibile selezionare solo uno spazio dei nomi valido, pertanto non è possibile utilizzare uno spazio dei nomi/un ID non valido come ID persona). |

## Abilita connessione

![Abilita connessione](assets/create-connection2.png)

1. Per abilitare una connessione, definisci queste impostazioni per l’intera connessione, ovvero tutti i set di dati della connessione:

   | Opzione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name Connection] | Assegna alla connessione un nome descrittivo. Impossibile salvare la connessione senza un nome. |
   | [!UICONTROL Description] | Aggiungi ulteriori dettagli per distinguere questa connessione dalle altre. |
   | [!UICONTROL Datasets] | Set di dati inclusi in questa connessione. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Seleziona questa opzione se desideri stabilire una connessione continua in modo che tutti i nuovi batch di dati aggiunti ai set di dati in questa connessione passino automaticamente in [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Quando selezioni questa opzione e salvi la connessione verranno importati o recuperati tutti i dati esistenti (storici) da [!DNL Experience Platform] per tutti i set di dati presenti in questa connessione. In futuro verranno importati automaticamente anche tutti i dati storici esistenti per eventuali nuovi set di dati aggiunti a questa connessione salvata. Consulta anche [Recupero dati storici](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#backfill-historical-data) sotto.<br>**Ricorda che una volta salvata la connessione questa impostazione non può essere modificata.** |
   | [!UICONTROL Average number of daily events] | È necessario specificare il numero medio di eventi giornalieri da importare (nuovi dati **e** dati di backfill) per tutti i set di dati della connessione. Seleziona un’opzione dal menu a discesa. In questo modo Adobe può allocare spazio sufficiente per questi dati.<br>Se non si conosce il numero medio di eventi giornalieri che l’azienda sta per importare, è possibile eseguire una semplice query SQL in [Servizi query Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) per scoprirlo.<br>Consulta “Calcolare il numero medio di eventi giornalieri” di seguito. |

1. Fai clic su **[!UICONTROL Save and create data view]**. Per la documentazione consulta [creare una visualizzazione dati](/help/data-views/create-dataview.md).

### Recupero dati storici

**[!UICONTROL Import all existing data]** consente di recuperare i dati storici. Nota bene:

* È stata rimossa la limitazione della retrocompilazione (importazione di dati storici). In precedenza era possibile retrocompilare in autonomia un massimo di 2,5 miliardi di righe, e richiedere l’intervento degli ingegneri per superare questo limite. Ora non esiste più alcun limite ai dati che è possibile retrocompilare da soli.
* Diamo priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.
* Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La latenza è influenzata dalla quantità di dati storici disponibili, combinati con l’impostazione **[!UICONTROL Average number of daily events]** selezionata. Ad esempio, se disponi di più di un miliardo di righe di dati al giorno, più 3 anni di dati storici, l’importazione potrebbe richiedere più settimane. D’altra parte, se ci sono meno di un milione di righe al giorno e una settimana di dati storici, ci vorrebbe meno di un’ora.
* La retrocompilazione si applica all’intera connessione, non a ogni singolo set di dati.
* Il [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/ingest-data-from-adobe-analytics.html?lang=it) importa fino a 13 mesi di dati, indipendentemente dalle dimensioni.

### Calcolare il numero medio di eventi giornalieri

Questo calcolo deve essere fatto per ogni set di dati della connessione.

1. Vai a [Servizi di query di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) e crea una nuova query.

   La query si presenta così:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In questo esempio, “analytics_demo_data” è il nome del set di dati.

1. Esegui la query `Show Tables` per mostrare tutti i set di dati esistenti in AEP.
