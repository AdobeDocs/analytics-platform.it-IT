---
title: Aggiungere dati a livello di account come set di dati di ricerca
description: Scopri come aggiungere dati basati su account come set di dati di ricerca al Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: b4c77c3ef4d57aac6e914a2373b6a9169f4872df
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 73%

---

# Aggiungere dati a livello di account come set di dati di ricerca

Questo caso d’uso B2B mostra come specificare i dati a livello di account anziché a livello di persona per l’analisi. L’analisi a livello di account può rispondere a domande quali

* A quale ragione sociale corrisponde questo account?
* Quanti dipendenti sono associati a questo account/azienda?
* Quali ruoli sono rappresentati in questo account?
* Come si comporta questo account nel suo complesso rispetto a una campagna di marketing specifica, rispetto a un altro account?
* Alcuni ruoli (come IT Manager) in un account si comportano in modo diverso rispetto allo stesso ruolo in un account diverso?

Per eseguire tutto questo, inserisci le informazioni a livello di account come set di dati di [ricerca](/help/technotes/glossary.md).

Innanzitutto, crea uno schema di ricerca in Adobe Experience Platform, quindi crea un set di dati della tabella di ricerca acquisendo dati a livello di account basati su .csv. Quindi procedi alla creazione di una connessione in Customer Journey Analytics (Customer Journey Analytics) che combina set di dati diversi, incluso quello di ricerca creato. In seguito puoi creare una visualizzazione dati e infine utilizzare tutti questi dati in Workspace.

>[!NOTE]
>
>Le dimensioni delle tabelle di ricerca possono essere fino a 1 GB.

## 1. Crea lo schema di ricerca (Experience Platform)

La creazione di uno schema personalizzato per la tabella [lookup](/help/technotes/glossary.md) garantisce che il set di dati utilizzato sia disponibile nel Customer Journey Analytics con la configurazione corretta (tipo di record). Ti consigliamo di [creare una classe di schema personalizzata](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#create-new-class) denominata “Ricerca”, priva di qualsiasi elemento, che può essere riutilizzata per tutte le tabelle di ricerca.

![Finestra di dialogo Crea nuova classe.](../assets/create-new-class.png)

## 2. Creare un set di dati di ricerca (Experience Platform)

Una volta creato lo schema, è necessario creare un set di dati di ricerca da tale schema in Experience Platform. Questo set di dati di ricerca contiene informazioni di marketing a livello di account, ad esempio: nome della società, numero totale di dipendenti, nome di dominio, a quale settore appartengono, ricavi annuali, se sono clienti attuali dell’Experience Platform o meno, in quale fase di vendita si trovano, in quale team all’interno dell’account utilizza il Customer Journey Analytics e così via.

1. In Adobe Experience Platform, vai su **[!UICONTROL Data Management > Datasets]** (Set di dati).
1. Fai clic su **[!UICONTROL + Create dataset]** (Crea set di dati).
1. Fai clic su **[!UICONTROL Create dataset from schema]** (Crea set di dati da schema).
1. Seleziona la classe Lookup Schema (Schema di ricerca) creata.
1. Fai clic su **[!UICONTROL Next]** (Avanti).
1. Assegna un nome al set di dati (nel nostro esempio, Informazioni B2B) e fornisci una descrizione.
1. Fai clic su **[!UICONTROL Finish]** (Fine).

## 3. Inserisci i dati in Experience Platform

Le istruzioni su come [mappare un file CSV su uno schema XDM](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=it) possono essere utili se utilizzi un file CSV.

Sono anche disponibili [altri metodi](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it).

L’inserimento dei dati e la determinazione della ricerca richiede circa da 2 a 4 ore, a seconda delle dimensioni della tabella di ricerca.

## 4. Combinare i set di dati in una connessione (Customer Journey Analytics)

Per questo esempio, stiamo combinando 3 set di dati in una connessione di Customer Journey Analytics:

| Nome del set di dati | Descrizione | Classe schema Adobe Experience Platform | Dettagli del set di dati |
| --- | --- | --- | --- |
| Impression B2B | Contiene i dati clickstream, a livello di evento e a livello di account. Ad esempio, contiene l’ID e-mail e l’ID account corrispondente, nonché la denominazione commerciale, per l’esecuzione degli annunci di marketing. Include inoltre le impression per tali annunci, per utente. | In base alla classe dello schema ExperienceEvent XDM | `emailID` viene utilizzato come identità principale e assegnato allo spazio dei nomi `Customer ID`. Di conseguenza, verrà visualizzato come **[!UICONTROL Person ID]** (ID persona) predefinito in Customer Journey Analytics. ![Impression](../assets/impressions-mixins.png) |
| Profilo B2B | Questo set di dati di profilo offre ulteriori informazioni sugli utenti in un account, ad esempio la loro posizione lavorativa, l’account a cui appartengono, il loro profilo LinkedIn e così via. | In base alla classe di schema XDM Individual Profile | Seleziona `emailID` come ID primario in questo schema. |
| Informazioni B2B | Consulta &quot;Creare set di dati di ricerca&quot; qui sopra. | Account B2B (classe di schema di ricerca personalizzata) | La relazione tra `accountID` e il set di dati Impression B2B è stata creata automaticamente connettendo il set di dati Info B2B con il set di dati Impression B2B nel Customer Journey Analytics, come descritto nei passaggi seguenti. ![Ricerca](../assets/lookup-mixins.png) |

Ecco come combinare i set di dati:

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]** (Connessioni).
1. Seleziona i set di dati (nel nostro esempio, i tre precedenti) che desideri combinare.
1. Per il set di dati Informazioni B2B, seleziona la chiave `accountID` che verrà utilizzata nella tabella di ricerca. Quindi seleziona la chiave corrispondente (dimensione corrispondente), anche `accountID` nel set di dati dell’evento.
1. Fai clic su **[!UICONTROL Next]** (Avanti).
1. Assegna un nome e una descrizione alla connessione e configurarla in base a [queste istruzioni](/help/connections/create-connection.md).
1. Fai clic su **[!UICONTROL Save]** (Salva).

## 5. Creare una visualizzazione dati da questa connessione

Segui le istruzioni sulla [creazione di visualizzazioni dati](/help/data-views/create-dataview.md).

* Aggiungi tutti i componenti (dimensioni e metriche) necessari dai set di dati.

## 6. Analizzare i dati in Workspace

Ora puoi creare progetti Workspace basati sui dati provenienti da tutti e tre i set di dati.

Ad esempio, puoi trovare le risposte alle domande poste nell’introduzione:

* Analizza l’emailID per accountID per capire a quale società appartiene un ID e-mail.
* Quanti dipendenti vengono mappati su un ID account specifico?
* A quale settore appartiene un ID account?

![project-lookup2](assets/analyze.png)
