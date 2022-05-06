---
title: Inserire il pubblico AEP nel Customer Journey Analytics
description: Spiega come inserire i tipi di pubblico AEP nel Customer Journey Analytics per ulteriori analisi.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 490a754270922481ebd893514c530a0667d9d6e4
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 1%

---

# Inserire il pubblico AEP nel Customer Journey Analytics (CJA)

Questo caso d’uso esplora un modo provvisorio e manuale di importare i tipi di pubblico di Adobe Experience Platform (AEP) in CJA. Questi tipi di pubblico possono essere stati creati nel Generatore di segmenti AEP, in Adobe Audience Manager o in altri strumenti e sono memorizzati nel Profilo cliente in tempo reale (RTCP). I tipi di pubblico sono costituiti da un set di ID profilo, insieme agli eventuali attributi/eventi/ecc. applicabili. e vogliamo portarli in CJA Workspace per l’analisi.

## Prerequisiti 

* Accesso a Adobe Experience Platform (AEP), in particolare Profilo cliente in tempo reale.
* Accesso per creare/gestire schemi e set di dati AEP.
* Accesso a AEP Query Service (e la capacità di scrivere SQL) o a un altro strumento per eseguire alcune trasformazioni leggere.
* Accesso al Customer Journey Analytics. Devi essere un amministratore di prodotto CJA per creare/modificare connessioni e visualizzazioni dati CJA.
* Possibilità di utilizzare le API di Adobe (segmentazione, facoltativamente altre)

## Passaggio 1: Scegliere il pubblico in Profilo cliente in tempo reale {#audience}

Adobe Experience Platform [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) (RTCP) consente di visualizzare una visualizzazione olistica di ogni singolo cliente combinando dati provenienti da più canali, inclusi online, offline, CRM e di terze parti.

Probabilmente hai già dei tipi di pubblico in RTCP che possono provenire da varie fonti. Scegli uno o più tipi di pubblico da inserire in CJA.

## Passaggio 2: Creare un set di dati dell’Unione profili per l’esportazione

Per esportare il pubblico in un set di dati che può essere aggiunto a una connessione in CJA, devi creare un set di dati il cui schema è un profilo [Schema dell&#39;unione](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

Gli schemi unione sono composti da più schemi che condividono la stessa classe e sono stati abilitati per Profile. Lo schema di unione ti consente di visualizzare una combinazione di tutti i campi contenuti negli schemi che condividono la stessa classe. Profilo cliente in tempo reale utilizza lo schema unione per creare una visualizzazione olistica di ogni singolo cliente.

## Passaggio 3: Esportare un pubblico nel set di dati dell’Unione profili tramite chiamata API {#export}

Prima di poter portare un pubblico in CJA, devi esportarlo in un set di dati AEP. Questo può essere fatto solo utilizzando l’API di segmentazione, e in particolare il [Endpoint API per i processi di esportazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

Puoi creare un processo di esportazione utilizzando l’ID pubblico desiderato e inserire i risultati nel set di dati AEP dell’Unione profili creato al passaggio 2. Anche se puoi esportare vari attributi/eventi per il pubblico, devi solo esportare il campo ID profilo specifico che corrisponde al campo ID persona utilizzato nella connessione CJA che sfrutterai (vedi sotto al passaggio 5).

## Passaggio 4: Modificare l’output di esportazione

I risultati del processo di esportazione devono essere trasformati in un set di dati di profilo separato per essere acquisiti in CJA.  Questa trasformazione può essere effettuata con AEP Query Service o con un altro strumento di trasformazione a tua scelta.  È necessario solo l’ID profilo (che corrisponde all’ID persona in CJA) e uno o più ID pubblico per effettuare la generazione dei rapporti in CJA. Il processo di esportazione standard, tuttavia, contiene più dati e quindi è necessario modificare questo output per rimuovere i dati estranei e spostare alcuni elementi.  Inoltre, è necessario creare prima uno schema/set di dati prima di aggiungergli i dati trasformati.

Ecco un esempio dell’output di esportazione nel set di dati dell’unione profili, **prima** qualsiasi modifica:

![Uscita non necessaria](assets/export-unedited.png)

Tieni presente quanto segue:

* L&#39;ID del pubblico è contenuto in `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Lo stato deve essere &quot;realizzato&quot; o &quot;inserito&quot;, ma non &quot;uscito&quot;.

Questo è il formato del set di dati di profilo che puoi inviare a CJA.

![Uscita modificata](assets/export-edited.png)

Di seguito sono riportati gli elementi dati che devono essere presenti:

* `_aresprodvalidation` campo stringa: Fa riferimento al tuo ID organizzazione. Il tuo sarà diverso.
* `personID` campo stringa: Questo è il campo di schema XDM standard sui set di dati di profilo per identificare la persona. Utilizza l’ID profilo dall’esportazione.
* `audienceMembershipId` campo stringa: L&#39;ID del pubblico dall&#39;esportazione.  NOTA: Questo campo può essere denominato come desiderato (dal proprio schema).
* Aggiungi un nome descrittivo per il pubblico (`audienceMembershipIdName`), come

   ![Nome descrittivo del pubblico](assets/audience-name.png)

* Aggiungi altri metadati del pubblico, se lo desideri.

## Passaggio 5: Aggiungi questo set di dati di profilo a una connessione esistente in CJA

È possibile creare una nuova connessione, ma la maggior parte dei clienti desidera aggiungerla a una connessione esistente. Gli ID del pubblico &quot;arricchiscono&quot; i dati esistenti in CJA.

[Creare una connessione](/help/connections/create-connection.md)

## Passaggio 6: Modificare la visualizzazione dati CJA esistente (o crearne una nuova)

Aggiungi `audienceMembershipId`, `audienceMembershipIdName` e `personID` alla visualizzazione dati.

## Passaggio 7: Rapporto in Workspace

Ora puoi creare rapporti su `audienceMembershipId`, `audienceMembershipIdName` e `personID` in Workspace.

## Note aggiuntive

* Devi eseguire questo processo con cadenza regolare, in modo che i dati sul pubblico vengano costantemente aggiornati all’interno di CJA.
* Puoi importare più tipi di pubblico all’interno di una singola connessione CJA. Questo aggiunge ulteriore complessità al processo, ma è possibile. Affinché questo funzioni, devi apportare alcune modifiche al processo di cui sopra:
   1. Esegui questo processo per ogni pubblico desiderato nella tua raccolta di tipi di pubblico all&#39;interno di RTCP.
   1. Quando esegui le trasformazioni dell&#39;output del processo di esportazione, dovrai creare un elenco di `audienceMembershipId(s)`, perché un singolo ID persona CJA può appartenere a più tipi di pubblico. In futuro, CJA supporterà array/array di oggetti nei set di dati di profilo. Una volta supportati, utilizzando una matrice di oggetti per `audienceMembershipId` o `audienceMembershipIdName` sarà l&#39;opzione migliore. Nel frattempo, estrai tutti gli ID del pubblico correnti per ciascun ID profilo nell’output del processo di esportazione (con lo stato di &quot;realizzato&quot; o &quot;inserito&quot;) e inseriscili in una stringa di valori separati da virgole (ad esempio, `<id1>,<id2>,...`).  Se è presente un ID pubblico con lo stato &quot;uscito&quot;, assicurati che NON sia nell’elenco.  Se desideri mantenere l’associazione del nome descrittivo con l’id, puoi allegarlo alla fine di ogni ID nell’elenco (insieme a qualsiasi altro metadati).
   1. Nella visualizzazione dati, crea una nuova dimensione utilizzando la trasformazione Substring nella `audienceMembershipId` campo per convertire la stringa di valori separati da virgola in una matrice. NOTA: attualmente nella matrice è presente un limite di 10 valori.
   1. È ora possibile creare rapporti su questa nuova dimensione `audienceMembershipIds` in CJA Workspace.
