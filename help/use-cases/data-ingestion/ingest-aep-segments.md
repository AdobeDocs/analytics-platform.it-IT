---
title: Inserire il pubblico Adobe Experience Platform nel Customer Journey Analytics
description: Come acquisire il pubblico Adobe Experience Platform nel Customer Journey Analytics per ulteriori analisi.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 52%

---

# Inserire il pubblico di Adobe Experience Platform in Adobe Customer Journey Analytics

Questo caso d’uso descrive come importare in modo provvisorio e manuale i tipi di pubblico di Adobe Experience Platform (Adobe Experience Platform) nel Customer Journey Analytics. Questi tipi di pubblico possono essere stati creati nel Generatore di segmenti di Adobe Experience Platform, in Adobe Audience Manager o in altri strumenti e sono memorizzati nel Profilo cliente in tempo reale (RTCP, Real-time Customer Profile). I tipi di pubblico sono costituiti da un set di ID profilo ed eventuali attributi, eventi ecc. applicabili e vogliamo portarli in Customer Journey Analytics Workspace per l’analisi.

## Prerequisiti

* Accesso a Adobe Experience Platform (Adobe Experience Platform), in particolare Real-time Customer Profile.
* Accesso per creare/gestire schemi e set di dati di Adobe Experience Platform.
* Accesso a Adobe Experience Platform Query Service (e la possibilità di scrivere codice SQL) o a un altro strumento per eseguire alcune trasformazioni leggere.
* Accesso a Customer Journey Analytics. Per poter creare e modificare connessioni di Customer Journey Analytics e visualizzazioni dati, devi essere un amministratore di Customer Journey Analytics.
* Capacità di utilizzare le API di Adobe (segmentazione, facoltativamente altre)

## Passaggio 1: scegliere il pubblico in Real-time Customer Profile {#audience}

Adobe Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) (RTCP) offre una visualizzazione olistica di ogni singolo cliente combinando dati provenienti da più canali, inclusi online, offline, CRM e di terze parti.

Probabilmente hai già dei tipi di pubblico in RTCP che possono provenire da varie origini. Scegli uno o più tipi di pubblico da inserire nel Customer Journey Analytics.

## Passaggio 2: creare un set di dati Unione profili da esportare

Per esportare il pubblico in un set di dati che può essere aggiunto a una connessione in un Customer Journey Analytics, devi creare un set di dati con uno schema di tipo Profilo [Schema di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=it#understanding-union-schemas).

Gli schemi di unione sono composti da più schemi che condividono la stessa classe e sono stati abilitati per Profilo. Lo schema di unione consente di visualizzare una combinazione di tutti i campi contenuti negli schemi che condividono la stessa classe. Real-time Customer Profile utilizza lo schema di unione per creare una visualizzazione olistica di ogni cliente.

## Passaggio 3: esportare un pubblico nel set di dati di Unione profili tramite chiamata API {#export}

Prima di importare un pubblico in un Customer Journey Analytics, devi esportarlo in un set di dati di Adobe Experience Platform. Questo può essere fatto solo utilizzando l’API di segmentazione, e in particolare l’[endpoint API per processi di esportazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=it).

Puoi creare un processo di esportazione utilizzando l’ID pubblico desiderato e inserire i risultati nel set di dati Unione profili di Adobe Experience Platform creato nel passaggio 2. Anche se puoi esportare vari attributi/eventi per il pubblico, devi solo esportare il campo ID profilo specifico che corrisponde al campo ID persona utilizzato nella connessione di Customer Journey Analytics che userai (vedi di seguito nel passaggio 5).

## Passaggio 4: modificare l’output di esportazione

Per poter essere acquisiti nel Customer Journey Analytics, i risultati del processo di esportazione devono essere trasformati in un set di dati profilo separato.  Questa trasformazione può essere eseguita con [Servizio query Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it)o un altro strumento di trasformazione a tua scelta. Per eseguire la generazione dei rapporti nel Customer Journey Analytics, è necessario solo l’ID profilo (che corrisponde all’ID persona nel Customer Journey Analytics) e uno o più ID pubblico.

Il processo di esportazione standard, tuttavia, contiene anche altri dati ed è quindi necessario modificare l’output per rimuovere i dati estranei e spostare alcuni elementi. Inoltre, è necessario creare uno schema o set di dati prima di aggiungervi i dati trasformati.

Ecco un esempio dell’output di esportazione nel set di dati Unione profili, **prima** di qualsiasi modifica:

![Output non modificato](../assets/export-unedited.png)

Tieni presente quanto segue:

* L’ID del pubblico si trova in `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Lo stato deve essere “realized” (realizzato) o “entered” (entrato), ma non “exited” (uscito).

Questo è il formato del set di dati profilo che puoi inviare al Customer Journey Analytics.

![Output modificato](../assets/export-edited.png)

Di seguito sono riportati gli elementi dati necessari:

* Campo stringa `_aresprodvalidation`: fa riferimento all’ID della tua organizzazione. Il tuo specifico valore sarà diverso da questo esempio.
* Campo stringa `personID`: campo dello schema XDM standard nei set di dati profilo con cui viene identificata la persona. Utilizza l’ID profilo dall’esportazione.
* Campo stringa `audienceMembershipId`: ID del pubblico dall’esportazione. NOTA: puoi denominare questo campo in base alle tue esigenze (dal tuo schema).
* Aggiungi al pubblico un nome descrittivo (`audienceMembershipIdName`), ad esempio:

  ![Nome descrittivo del pubblico](../assets/audience-name.png)

* Se necessario, aggiungi altri metadati di pubblico.

## Passaggio 5: aggiungi questo set di dati profilo a una connessione esistente nel Customer Journey Analytics

Puoi [crea una nuova connessione](/help/connections/create-connection.md), ma nella maggior parte dei casi si vorrà aggiungere il set di dati profilo a una connessione esistente. Gli ID pubblico &quot;arricchiscono&quot; i dati esistenti nel Customer Journey Analytics.

## Passaggio 6: modificare la visualizzazione dati del Customer Journey Analytics esistente (o crearne una nuova)

Aggiungi `audienceMembershipId`, `audienceMembershipIdName` e `personID` alla visualizzazione dati.

## Passaggio 7: creare un rapporto in Workspace

Ora puoi creare un rapporto in Workspace basato su `audienceMembershipId`, `audienceMembershipIdName` e `personID`.

## Note aggiuntive

* Esegui questa procedura su base regolare, in modo che i dati del pubblico vengano costantemente aggiornati entro il Customer Journey Analytics.
* Puoi importare più tipi di pubblico all’interno di una singola connessione di Customer Journey Analytics. Il processo sarà un po’ più complesso, ma è possibile. Dovrai apportare alcune modifiche al processo di cui sopra:
   1. Esegui questo processo per ogni pubblico desiderato nella raccolta di tipi di pubblico in RTCP.
   1. Il Customer Journey Analytics supporta array/array di oggetti nei set di dati profilo. Utilizzare un [array di oggetti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=it) per audienceMembershipId o audienceMembershipIdName è l’opzione migliore.
   1. Nella visualizzazione dati, crea una nuova dimensione utilizzando la trasformazione Substring (Sottostringa) nel campo `audienceMembershipId` per convertire la stringa di valori separati da virgola in un array. NOTA: attualmente un array può contenere un massimo di 10 valori.
   1. Ora puoi creare rapporti sulla nuova dimensione `audienceMembershipIds` in Customer Journey Analytics Workspace.
