---
title: Aggiungere dati account come set di dati di ricerca
description: Scopri come aggiungere dati account come set di dati di ricerca al Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 35%

---

# Aggiungere dati account come set di dati di ricerca

Questo caso d’uso B2B mostra come aggiungere dati di account a un’analisi a livello di persona e di evento. Quando si aggiungono i dati dell&#39;account, è possibile rispondere a domande quali:

* A quale ragione sociale corrisponde questo account?
* Quali ruoli sono rappresentati in questo account?
* Alcuni ruoli (come IT Manager) in un account si comportano in modo diverso rispetto allo stesso ruolo in un account diverso?

Per aggiungere informazioni sui dati dell&#39;account, aggiungere e utilizzare un set di dati [lookup](/help/technotes/glossary.md) che contiene tali informazioni.

Le fasi previste sono le seguenti:

1. [Creare uno schema di ricerca](#create-lookup-schema) in Experience Platform.
1. [Crea un set di dati di ricerca](#create-lookup-dataset) nell&#39;Experience Platform che consente di acquisire dati dell&#39;account basati su CSV.
1. [Combina i set di dati in una connessione](#combine-datasets-in-a-connection) nel Customer Journey Analytics, incluso quello di ricerca creato.
1. [Crea una visualizzazione dati](#create-a-data-view-from-this-connection) nel Customer Journey Analytics.
1. [Analizza questi dati](#analyze-the-data-in-workspace) in Workspace nel Customer Journey Analytics.

>[!NOTE]
>
>Le dimensioni delle tabelle di ricerca possono essere fino a 1 GB.
>

## Crea schema di ricerca

Quando si crea uno schema personalizzato per la tabella [lookup](/help/technotes/glossary.md), tale schema garantisce che il set di dati utilizzato sia disponibile nel Customer Journey Analytics con la configurazione corretta (tipo di record). Si consiglia di [creare una classe di schema personalizzata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) che possa essere riutilizzata per tutte le tabelle di ricerca.

![Finestra di dialogo Crea nuova classe.](../assets/create-new-class.png)

## Crea set di dati di ricerca

Una volta creato lo schema, è necessario creare un set di dati di ricerca, in base a tale schema, ad Experience Platform. Questo set di dati di ricerca contiene le informazioni sull’account. Ad esempio: nome società, numero totale di dipendenti, nome dominio, settore di appartenenza della società, ricavi annuali e altro ancora. Assicurati che i dati contengano un identificatore della persona che possa corrispondere all’identificatore della persona utilizzato nei dati dell’evento.

1. Ad Experience Platform, passa a **[!UICONTROL Data Management > Datasets]**.
1. Fai clic su **[!UICONTROL + Create dataset]** (Crea set di dati).
1. Fai clic su **[!UICONTROL Create dataset from schema]** (Crea set di dati da schema).
1. Selezionare la classe dello schema di ricerca creata.
1. Fai clic su **[!UICONTROL Next]**.
1. Denomina il set di dati (ad esempio, `B2B Info`) e fornisci una descrizione.
1. Fai clic su **[!UICONTROL Finish]**.

## Acquisire dati

Le istruzioni su come [mappare un file CSV su uno schema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) possono essere utili se utilizzi un file CSV.

Sono anche disponibili [altri metodi](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home).

L’inserimento dei dati e la determinazione della ricerca richiede circa da 2 a 4 ore, a seconda delle dimensioni della tabella di ricerca.

## Combinare set di dati in una connessione

In questo esempio, puoi combinare 3 set di dati in una connessione di Customer Journey Analytics:

| Nome del set di dati | Descrizione | Classe schema Adobe Experience Platform | Dettagli del set di dati |
| --- | --- | --- | --- |
| Impression B2B | Contiene i dati clickstream, a livello di evento e a livello di account. Ad esempio, contiene l’ID e-mail e l’ID account corrispondente, nonché la denominazione commerciale, per l’esecuzione degli annunci di marketing. Include inoltre le impression per tali annunci per utente. | In base alla classe dello schema XDM ExperienceEvent | `emailID` viene utilizzato come identità principale e assegnato allo spazio dei nomi `Customer ID`. Di conseguenza, viene visualizzato come **[!UICONTROL Person ID]** predefinito nel Customer Journey Analytics. ![Impression](../assets/impressions-mixins.png) |
| Profilo B2B | Questo set di dati di profilo offre ulteriori informazioni sugli utenti in un account, ad esempio la loro posizione lavorativa, l’account a cui appartengono, il loro profilo LinkedIn e così via. | In base alla classe di schema XDM Individual Profile | Seleziona `emailID` come ID primario in questo schema. |
| Informazioni B2B | Consulta &quot;Creare set di dati di ricerca&quot; qui sopra. | Account B2B (classe schema di ricerca personalizzata) | La relazione tra `accountID` e il set di dati Impression B2B viene creata automaticamente quando si connette il set di dati Info B2B con il set di dati Impression B2B nel Customer Journey Analytics, come descritto nei passaggi seguenti. ![Ricerca](../assets/lookup-mixins.png) |

Ecco come combinare i set di dati:

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]** (Connessioni).
1. Seleziona i set di dati da combinare.
1. Per il set di dati di informazioni B2B, seleziona la chiave utilizzata nella tabella di ricerca (ad esempio `personKey.sourceKey`). Quindi seleziona la chiave corrispondente (dimensione corrispondente), anche nel set di dati dell&#39;evento (ad esempio p`ersonKey.sourceKey`).
1. Fai clic su **[!UICONTROL Next]** (Avanti).
1. Assegna un nome e una descrizione alla connessione e configurarla in base a [queste istruzioni](/help/connections/create-connection.md).
1. Fai clic su **[!UICONTROL Save]** (Salva).

## Crea una visualizzazione dati da questa connessione

Segui le istruzioni per [creare visualizzazioni dati](/help/data-views/create-dataview.md).

* Aggiungi tutti i componenti (dimensioni e metriche) necessari dai set di dati. Assicurati che per le metriche che richiedono la deduplicazione per un conteggio eccessivo, configura di conseguenza queste metriche (vedi [Impostazioni dei componenti di deduplicazione delle metriche](/help/data-views/component-settings/metric-deduplication.md)). Esempi di tali metriche sono il numero di dipendenti o i ricavi.

## Analizzare i dati in Workspace

Ora puoi creare progetti Workspace basati sui dati provenienti da tutti e tre i set di dati.

Ad esempio, puoi trovare le risposte alle domande poste nell’introduzione:

* Analizza l’emailID per accountID per capire a quale società appartiene un ID e-mail.
* Quanti dipendenti vengono mappati su un ID account specifico?
* A quale settore appartiene un ID account?

>[!MORELIKETHIS]
>
>Per ulteriori dettagli, vedere [Un progetto B2B di esempio](example.md).

