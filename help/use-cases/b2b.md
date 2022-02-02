---
title: (B2B) Aggiungere dati a livello di account come set di dati di ricerca
description: Scopri come aggiungere dati basati su account come set di dati di ricerca a CJA
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 3%

---

# (B2B) Aggiungere dati a livello di account come set di dati di ricerca

Questo caso d’uso B2B mostra come specificare i dati a livello di account anziché a livello di persona per l’analisi. L’analisi a livello di account può rispondere a domande quali

* A quale nome società corrisponde questo account?
* Quanti dipendenti sono associati a questo account/azienda?
* Quali ruoli sono rappresentati in questo account?
* Come si comporta questo account nel suo complesso rispetto a una campagna di marketing specifica, rispetto a un altro account?
* Alcuni ruoli (come IT Manager) in un account si comportano in modo diverso rispetto allo stesso ruolo in un account diverso?

Per eseguire tutto questo, inserisci le informazioni a livello di account come [ricerca](/help/getting-started/cja-glossary.md) set di dati.

Prima si crea uno schema di ricerca in Adobe Experience Platform, quindi si crea un set di dati della tabella di ricerca acquisendo dati a livello di account basati su .csv. Quindi devi procedere alla creazione di una connessione nel Customer Journey Analytics (CJA0) che combina diversi set di dati, incluso quello di ricerca creato. In seguito puoi creare una visualizzazione dati e infine utilizzare tutti questi dati in Workspace.

>[!NOTE]
>
>Le tabelle di ricerca possono avere dimensioni fino a 1 GB.

## 1. Creare lo schema di ricerca (Experience Platform)

Creazione di uno schema personalizzato per [ricerca](/help/getting-started/cja-glossary.md) la tabella assicura che il set di dati utilizzato sia disponibile in CJA con la configurazione corretta (tipo di record). Si consiglia di: [creare una classe di schema personalizzata](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) denominato &quot;Lookup&quot;, vuoto di qualsiasi elemento, che può essere riutilizzato per tutte le tabelle di ricerca.

![](assets/create-new-class.png)

## 2. Crea set di dati di ricerca (Experience Platform)

Una volta creato lo schema, è necessario creare, ad Experience Platform, un set di dati di ricerca da tale schema. Questo set di dati di ricerca contiene informazioni di marketing a livello di account, ad esempio: nome dell’azienda, numero totale di dipendenti, nome di dominio, a quale industria appartengono, ricavi annuali, che siano clienti attuali dell’Experience Platform o meno, in quale fase di vendita si trovano, in quale team all’interno dell’account sta utilizzando CJA, ecc.

>[!IMPORTANT]
>
>CJA non supporta gli interi nei set di dati di ricerca. Se si aggiungono campi interi nello schema XDM per il set di dati di ricerca, non sarà possibile utilizzare tali numeri interi come metriche o metriche calcolate. Ad esempio, se i ricavi annuali o i dipendenti totali sono definiti come numeri interi, nei rapporti di CJA verranno visualizzati come &quot;0&quot;. Tuttavia, se le assegni come stringhe, puoi utilizzarle come informazioni di ricerca.

Ad esempio, i ricavi annuali o i dipendenti totali sono definiti come Intero nell’esempio seguente, per questo motivo viene visualizzato &quot;0&quot; in CJA.

1. In Adobe Experience Platform, vai a **[!UICONTROL Data Management > Datasets]**.
1. Fai clic su **[!UICONTROL + Create dataset]**.
1. Fai clic su **[!UICONTROL Create dataset from schema]**.
1. Selezionare la classe Schema di ricerca creata.
1. Fai clic su **[!UICONTROL Next]**.
1. Denomina il set di dati (nel nostro esempio, Informazioni B2B) e fornisci una descrizione.
1. Fai clic su **[!UICONTROL Finish]**.

## 3. Inserire dati in Experience Platform

Istruzioni su come [Mappare un file CSV su uno schema XDM](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html) dovrebbe essere utile se utilizzi un file CSV.

[Altri metodi](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) sono anche disponibili.

L’inserimento dei dati e la determinazione della ricerca richiede circa 2-4 ore, a seconda delle dimensioni della tabella di ricerca.

## 4. Combinare set di dati in una connessione (Customer Journey Analytics)

Per questo esempio, stiamo combinando 3 set di dati in una singola connessione CJA:

| Nome set di dati | Descrizione | Classe AEP Schema | Dettagli del set di dati |
| --- | --- | --- | --- |
| Impression B2B | Contiene i dati a livello di evento e di click-stream a livello di account. Ad esempio, contiene l’ID e-mail e l’ID account corrispondente, nonché il nome marketing, per l’esecuzione degli annunci di marketing. Include inoltre le impression per tali annunci, per utente. | In base alla classe dello schema ExperienceEvent XDM | La `emailID` viene utilizzato come identità principale e assegnato a `Customer ID` spazio dei nomi. Di conseguenza, verrà visualizzato come predefinito **[!UICONTROL Person ID]** in Customer Journey Analytics. ![Impression](assets/impressions-mixins.png) |
| Profilo B2B | Questo set di dati di profilo offre ulteriori informazioni sugli utenti in un account, ad esempio il loro titolo del lavoro, l’account a cui appartengono, il loro profilo LinkedIn e così via. | In base alla classe di schema Profilo individuale XDM | Non è necessario selezionare `emailID` come ID principale in questo schema. Assicurati di abilitare **[!UICONTROL Profile]**; in caso contrario, CJA non sarà in grado di collegare il `emailID` nel profilo B2B con `emailID` nei dati di impression B2B. ![Profilo](assets/profile-mixins.png) |
| Informazioni B2B | Vedi &quot;Crea set di dati di ricerca&quot; sopra. | B2BAccount (classe di schema di ricerca personalizzata) | Il rapporto tra `accountID` e il set di dati sulle impressioni B2B è stato creato automaticamente connettendo il set di dati sulle informazioni B2B con il set di dati sulle impressioni B2B in CJA, come descritto nei passaggi seguenti. ![Ricerca](assets/lookup-mixins.png) |

Ecco come combinare i set di dati:

1. In Customer Journey Analytics, seleziona la **[!UICONTROL Connections]** scheda .
1. Seleziona i set di dati (nel nostro esempio, i tre precedenti) che desideri combinare.
1. Per il set di dati B2B Info , seleziona la variabile `accountID` chiave che verrà utilizzata nella tabella di ricerca. Quindi seleziona la chiave corrispondente (dimensione corrispondente), anche `accountID` nel set di dati dell’evento.
1. Fai clic su **[!UICONTROL Next]**.
1. Denominare e descrivere la connessione e configurarla in base a [queste istruzioni](/help/connections/create-connection.md).
1. Fai clic su **[!UICONTROL Save]**.

## 5. Crea una visualizzazione dati da questa connessione

Segui le istruzioni su [creazione di visualizzazioni dati](/help/data-views/create-dataview.md).

* Aggiungi tutti i componenti (dimensioni e metriche) necessari dai set di dati.

## 6. Analizzare i dati in Workspace

Ora puoi creare progetti Workspace basati sui dati provenienti da tutti e tre i set di dati.

Ad esempio, puoi trovare le risposte alle risposte fornite nell’introduzione:

* Analizza l’e-mailID per accountID per capire a quale società appartiene un ID e-mail.
* Quanti dipendenti vengono mappati su un ID account specifico?
* A che settore appartiene un ID account?

![](assets/project-lookup.png)
