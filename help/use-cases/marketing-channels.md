---
title: Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform
description: Utilizza il Connettore dati di Analytics per inserire le regole di elaborazione del canale di marketing in Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 4%

---

# Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform

Se l&#39;organizzazione utilizza la variabile [Connettore dati di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) per inserire i dati della suite di rapporti in CJA, puoi configurare una connessione in CJA per creare rapporti sulle dimensioni del canale di marketing.

## Prerequisiti

* I dati della suite di rapporti devono già essere importati in Adobe Experience Platform utilizzando [Connettore dati di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Altre origini di dati non sono supportate, in quanto i canali di marketing si basano sulle regole di elaborazione in una suite di rapporti di Analytics.
* Le regole di elaborazione del canale di marketing devono già essere configurate. Vedi [Regole di elaborazione per i canali di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=it) nella guida ai componenti tradizionali di Analytics.

## Elementi dello schema del canale di marketing

Una volta stabilito il Connettore dati di Analytics su una suite di rapporti desiderata, viene creato uno schema XDM per te. Questo schema contiene tutte le dimensioni e le metriche di Analytics come dati non elaborati. Questi dati non elaborati non contengono attribuzione o persistenza. Al contrario, ogni evento viene eseguito attraverso le regole di elaborazione del canale di marketing e registra la prima regola a cui corrisponde. Quando crei una visualizzazione dati in CJA, specifichi attribuzione e persistenza.

1. [Creare una connessione](/help/connections/create-connection.md) che include un set di dati basato su Analytics Data Connector.
2. [Creare una visualizzazione dati](/help/data-views/create-dataview.md) che include le dimensioni seguenti:
   * **`channel.typeAtSource`**: Equivalente al [Canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) dimensione.
   * **`channel._id`**: Equivalente al [Dettaglio del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html)
3. Attribuisci a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Se desideri entrambe le dimensioni di primo e ultimo contatto, trascina più volte ciascuna dimensione del canale di marketing nell’area dei componenti. Attribuisci a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Adobe consiglia inoltre di assegnare a ciascuna dimensione un nome visualizzato per facilitarne l’utilizzo in Workspace.
4. Crea la visualizzazione dati.

Le dimensioni del tuo canale di marketing sono ora disponibili per l’uso in Analysis Workspace.

## Differenze di elaborazione e di architettura

>[!IMPORTANT]
>
>Esistono diverse differenze fondamentali di dati tra i dati della suite di rapporti e i dati della piattaforma. L’Adobe consiglia vivamente di regolare le regole di elaborazione dei canali di marketing della suite di rapporti per facilitare la corretta raccolta dei dati in Platform.

>[!NOTE]
>
>Per massimizzare l&#39;efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, ne abbiamo pubblicati alcuni [best practice riviste](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=it).

Le impostazioni del canale di marketing operano in modo diverso tra i dati della piattaforma e i dati della suite di rapporti. Quando si impostano i canali di marketing per CJA, considera le seguenti differenze:

* **È la prima pagina della visita**: Questo criterio della regola è comune in diverse definizioni di canale di marketing predefinite. Qualsiasi regola di elaborazione che contiene questo criterio viene ignorata in Platform (altri criteri nella stessa regola vengono comunque applicati). Le sessioni vengono determinate al momento della query dei dati anziché al momento della raccolta dei dati, impedendo a Platform di utilizzare questo criterio di regola specifico. Adobe consiglia di rivalutare eventuali regole di elaborazione del canale di marketing contenenti i criteri &quot;Is First Page of Visit&quot;, optando per approcci alternativi che raggiungono i tuoi obiettivi.

   ![Prima pagina di visita](assets/first-page-of-visit.png)

* **Ignora canale ultimo contatto**: Questa impostazione in Marketing Channel Manager normalmente impedisce a determinati canali di ottenere il credito del canale di ultimo contatto. Platform ignora questa impostazione, consentendo a canali ampi come &quot;Direct&quot; o &quot;Internal&quot; di attribuire metriche in modi potenzialmente indesiderati. Adobe consiglia di rimuovere i canali in cui l’opzione &quot;Ignora canale ultimo contatto&quot; è deselezionata.
   * Puoi eliminare il canale di marketing &quot;diretto&quot; nel Marketing Channel Manager, quindi affidarti all’elemento dimensione &quot;Nessun valore&quot; di CJA per quel canale. Puoi anche rinominare questo elemento dimensionale in &quot;Diretto&quot; o escludere completamente l’elemento dimensione durante la configurazione di una visualizzazione dati.
   * In alternativa, puoi creare una classificazione del canale di marketing, classificando ciascun valore su se stesso, ad eccezione dei canali che desideri escludere in CJA. Puoi quindi utilizzare questa dimensione di classificazione quando crei una visualizzazione dati invece che `channel.typeAtSource`.

   ![Ignora canale ultimo contatto](assets/override-last-touch-channel.png)

* **Scadenza canale di marketing**: Questa impostazione del periodo di coinvolgimento determina il periodo di inattività prima che un visitatore possa ottenere un nuovo canale di primo contatto nei dati della suite di rapporti. Platform utilizza le proprie impostazioni di attribuzione, pertanto questa impostazione viene ignorata completamente in CJA.

   ![Scadenza del canale di marketing](assets/marketing-channel-expiration.png)

## Confronto dei dati tra CJA e Analytics tradizionale

Poiché l’architettura di Adobe Experience Platform è diversa da una suite di rapporti Analytics tradizionale, i risultati non corrispondono. Tuttavia, puoi utilizzare i seguenti suggerimenti per semplificare il confronto:

* Verifica che le differenze architettoniche elencate sopra non influiscano sul confronto. Ciò include la rimozione dei canali che non sovrascrivono il canale di ultimo contatto e la rimozione dei criteri delle regole che sono il primo hit di una visita (sessione).
* Controlla che la tua connessione utilizzi la stessa suite di rapporti di Analytics tradizionale. Se la connessione CJA contiene più suite di rapporti con le proprie regole di elaborazione del canale di marketing, non esiste un modo semplice per confrontarla con la versione tradizionale di Analytics. Creare una connessione separata per ogni suite di rapporti per confrontare i dati.
* Assicurati di confrontare gli stessi intervalli di date e che l&#39;impostazione del fuso orario nella visualizzazione dati sia identica al fuso orario della suite di rapporti.
* Utilizza un modello di attribuzione personalizzato quando visualizzi i dati della suite di rapporti. Ad esempio, utilizza [Canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) con metriche che utilizzano un modello di attribuzione non predefinito. Adobe consiglia di non confrontare le dimensioni predefinite [Canale di primo contatto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) o [Canale di ultimo contatto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html), poiché si basano sull’attribuzione raccolta nella suite di rapporti. CJA non si basa sui dati di attribuzione di una suite di rapporti; viene invece calcolato quando viene eseguito un rapporto CJA.
* Alcune metriche non dispongono di un confronto ragionevole a causa di differenze architettoniche tra i dati della suite di rapporti e i dati della piattaforma. Gli esempi includono visite/sessioni, visitatori/persone e eventi/eventi.
