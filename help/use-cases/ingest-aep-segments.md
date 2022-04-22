---
title: Inserire il pubblico AEP nel Customer Journey Analytics
description: Spiega come inserire i tipi di pubblico AEP nel Customer Journey Analytics per ulteriori analisi.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: ed01fd0899cac21fff156e0c31dc2b52ff7c8cca
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 2%

---


# Inserire il pubblico AEP nel Customer Journey Analytics (CJA)

>[!NOTE]
>
>Questo argomento è in costruzione.

(Brandon, fyi, &#39;Unified Profile&#39; è un termine obsoleto per &#39;Real-time Customer Profile&#39; - secondo il doc manager AEP. Non troverai alcun documento su UP nel set di documenti AEP.)

Questo caso d’uso esplora un modo provvisorio e manuale di importare i tipi di pubblico di Adobe Experience Platform (AEP) in CJA. Questi tipi di pubblico possono essere stati creati nel Generatore di segmenti AEP, in Adobe Audience Manager o in altri strumenti e sono memorizzati nel Profilo cliente in tempo reale (RTCP). I tipi di pubblico sono costituiti da elenchi di ID persona, ID profilo e così via. e vogliamo portarli in CJA Workspace per l’analisi.

## Prerequisiti

* Accesso a Adobe Experience Platform (AEP), in particolare Profilo cliente in tempo reale.
* Accesso al Customer Journey Analytics
* Capacità di scrivere codice personalizzato?
* Che altro.

## Passaggio 1: Scegliere il pubblico in Profilo cliente in tempo reale {#audience}

Adobe Experience Platform [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) (RTCP) consente di visualizzare una visualizzazione olistica di ogni singolo cliente combinando dati provenienti da più canali, inclusi online, offline, CRM e di terze parti. Probabilmente hai già dei tipi di pubblico in RTCP che possono provenire da varie fonti. Scegli uno o più tipi di pubblico.

## Passaggio 2: Creare un set di dati dell’Unione profili per l’esportazione

Per esportare il pubblico in un set di dati che può quindi effettuare una connessione a CJA, devi creare un set di dati il cui schema è un profilo [Schema dell&#39;unione](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Gli schemi unione sono composti da più schemi che condividono la stessa classe e sono stati abilitati per Profile. Lo schema di unione ti consente di visualizzare una combinazione di tutti i campi contenuti negli schemi che condividono la stessa classe. Profilo cliente in tempo reale utilizza lo schema unione per creare una visualizzazione olistica di ogni singolo cliente.

## Passaggio 3: Esportare un pubblico a un set di dati tramite una chiamata API {#export}

Prima di poter portare un pubblico in CJA, devi esportarlo in un set di dati in AEP. Questo può essere fatto solo utilizzando l’API di segmentazione, e in particolare il [Endpoint API per i processi di esportazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Puoi creare un processo di esportazione e inserire i risultati nel set di dati AEP dell’Unione profili creato al passaggio 2.

## Passaggio 4: Modificare l’output di esportazione

Quando crei il processo di esportazione per un pubblico, è sufficiente che l’ID persona e l’ID pubblico eseguano il reporting in CJA. Il processo di esportazione standard, tuttavia, contiene più dati e pertanto è necessario modificare questo output per rimuovere i dati estranei.

Ecco un esempio dell’output di esportazione nel set di dati dell’unione profili, **prima** qualsiasi modifica:

![Uscita non necessaria](assets/export-unedited.png)

Tieni presente quanto segue:

* L&#39;ID del pubblico è contenuto in `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Lo stato deve essere &quot;realizzato&quot; o &quot;inserito&quot;, ma non &quot;uscito&quot;. Sostituisci &quot;uscito&quot; con &quot;vuoto&quot;.

Questo è il formato del set di dati di profilo che puoi inviare a CJA.

![Uscita modificata](assets/export-edited.png)

Di seguito sono riportati gli elementi dati che devono essere presenti:

* `_aresprodvalidation`: Fa riferimento al tuo ID organizzazione. Il tuo sarà diverso.
* `personID`: In questo caso, un nome descrittivo
* `audienceMembershipIdList` campo stringa: ID del pubblico
* Aggiungi un nome descrittivo per il pubblico (`audienceMembershipIdName`), come

   ![Nome descrittivo del pubblico](assets/audience-name.png)

## Passaggio 5: Creare una connessione in CJA a questo set di dati del profilo

[Creare una connessione](/help/connections/create-connection.md)

## Passaggio 6: Creare una visualizzazione dati

Aggiungi `audienceMembershipIdName` e `personID` alla visualizzazione dati.

## Passaggio 7: Rapporto in Workspace

Ora puoi creare rapporti su `audienceMembershipIdName` e `personID` in Workspace.
Screenshot sarebbe grandioso.

Per eseguire:

scrivi più passaggi per quando hai a che fare con persone che sono membri di più tipi di pubblico.




