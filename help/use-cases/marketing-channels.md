---
title: Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform
description: Utilizza il Connettore dati di Analytics per inserire le regole di elaborazione del canale di marketing in Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---

# Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform

Se la tua organizzazione utilizza il [Connettore dati Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) per inserire i dati della suite di rapporti in CJA, puoi configurare una connessione in CJA per creare rapporti sulle dimensioni del canale di marketing.

## Prerequisiti

* I dati della suite di rapporti devono già essere importati in Adobe Experience Platform utilizzando il [Connettore dati di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Altre origini di dati non sono supportate, in quanto i canali di marketing si basano sulle regole di elaborazione in una suite di rapporti di Analytics.
* Le regole di elaborazione del canale di marketing devono già essere configurate. Consulta [Regole di elaborazione per i canali di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html) nella guida tradizionale ai componenti di Analytics.

## Elementi dello schema del canale di marketing

Una volta stabilito il Connettore dati di Analytics su una suite di rapporti desiderata, viene creato uno schema XDM per te. Questo schema contiene tutte le dimensioni e le metriche di Analytics come dati non elaborati. Questi dati non elaborati non contengono attribuzione o persistenza. Al contrario, ogni evento viene eseguito attraverso le regole di elaborazione del canale di marketing e registra la prima regola a cui corrisponde. Quando crei una visualizzazione dati in CJA, specifichi attribuzione e persistenza.

1. [Crea una ](/help/connections/create-connection.md) connessione che include un set di dati basato su Connettore dati di Analytics.
2. [Crea una ](/help/data-views/create-dataview.md) visualizzazione dati che include le dimensioni seguenti:
   * **`channel.typeAtSource`**: Equivalente alla dimensione  [del ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) canale di marketing.
   * **`channel._id`**: Equivalente al dettaglio del canale  [di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html)
3. Attribuisci a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Se desideri entrambe le dimensioni di primo e ultimo contatto, trascina più volte ciascuna dimensione del canale di marketing nell’area dei componenti. Attribuisci a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Adobe consiglia inoltre di assegnare a ciascuna dimensione un nome visualizzato per facilitarne l’utilizzo in Workspace.
4. Crea la visualizzazione dati.

Le dimensioni del tuo canale di marketing sono ora disponibili per l’uso in Analysis Workspace.

## Differenze di elaborazione e di architettura

>[!IMPORTANT]
>
>Esistono diverse differenze fondamentali di dati tra i dati della suite di rapporti e i dati della piattaforma. L’Adobe consiglia vivamente di regolare le regole di elaborazione dei canali di marketing della suite di rapporti per facilitare la corretta raccolta dei dati in Platform.

Le impostazioni del canale di marketing operano in modo diverso tra i dati della piattaforma e i dati della suite di rapporti. Quando si impostano i canali di marketing per CJA, considera le seguenti differenze:

* **È la prima pagina della visita**: Questo criterio della regola è comune in diverse definizioni di canale di marketing predefinite. Qualsiasi regola di elaborazione che contiene questo criterio viene ignorata in Platform (altri criteri nella stessa regola vengono comunque applicati). Le sessioni vengono determinate al momento della query dei dati anziché al momento della raccolta dei dati, impedendo a Platform di utilizzare questo criterio di regola specifico. Adobe consiglia di rimuovere i criteri &quot;Is First Page of Visit&quot; da ogni regola di elaborazione del canale di marketing.

   ![Prima pagina di visita](assets/first-page-of-visit.png)

* **Ignora canale** ultimo contatto: Questa impostazione in Marketing Channel Manager normalmente impedisce a determinati canali di ottenere il credito del canale di ultimo contatto. Platform ignora questa impostazione, consentendo a canali ampi come &quot;Direct&quot; o &quot;Internal&quot; di attribuire metriche in modi potenzialmente indesiderati. Adobe consiglia di rimuovere i canali in cui l’opzione &quot;Ignora canale ultimo contatto&quot; è deselezionata.
   * Puoi eliminare il canale di marketing &quot;diretto&quot; nel Marketing Channel Manager, quindi affidarti all’elemento dimensione &quot;Nessun valore&quot; di CJA per quel canale. Puoi anche rinominare questo elemento dimensionale in &quot;Diretto&quot; o escludere completamente l’elemento dimensione durante la configurazione di una visualizzazione dati.
   * In alternativa, puoi creare una classificazione del canale di marketing, classificando ciascun valore su se stesso, ad eccezione dei canali che desideri escludere in CJA. Puoi quindi utilizzare questa dimensione di classificazione quando crei una visualizzazione dati invece di `channel.typeAtSource`.

   ![Ignora canale ultimo contatto](assets/override-last-touch-channel.png)

* **Scadenza** canale di marketing: Questa impostazione del periodo di coinvolgimento determina il periodo di inattività prima che un visitatore possa ottenere un nuovo canale di primo contatto nei dati della suite di rapporti. Platform utilizza le proprie impostazioni di attribuzione, pertanto questa impostazione viene ignorata completamente in CJA.

   ![Scadenza del canale di marketing](assets/marketing-channel-expiration.png)

## Confronto dei dati tra CJA e Analytics tradizionale

Poiché l’architettura di Adobe Experience Platform è diversa da una suite di rapporti Analytics tradizionale, i risultati non corrispondono. Tuttavia, puoi utilizzare i seguenti suggerimenti per semplificare il confronto:

* Verifica che le differenze architettoniche elencate sopra non influiscano sul confronto. Ciò include la rimozione dei canali che non sovrascrivono il canale di ultimo contatto e la rimozione dei criteri delle regole che sono il primo hit di una visita (sessione).
* Controlla che la tua connessione utilizzi la stessa suite di rapporti di Analytics tradizionale. Se la connessione CJA contiene più suite di rapporti con le proprie regole di elaborazione del canale di marketing, non esiste un modo semplice per confrontarla con la versione tradizionale di Analytics. Creare una connessione separata per ogni suite di rapporti per confrontare i dati.
* Assicurati di confrontare gli stessi intervalli di date e che l&#39;impostazione del fuso orario nella visualizzazione dati sia identica al fuso orario della suite di rapporti.
* Utilizza un modello di attribuzione personalizzato quando visualizzi i dati della suite di rapporti. Ad esempio, utilizza la dimensione [Canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) con metriche che utilizzano un modello di attribuzione non predefinito. L’Adobe sconsiglia di confrontare le dimensioni predefinite [Canale di primo contatto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) o [Canale di ultimo contatto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html), perché si basano sull’attribuzione raccolta nella suite di rapporti. CJA non si basa sui dati di attribuzione di una suite di rapporti; viene invece calcolato quando viene eseguito un rapporto CJA.
* Alcune metriche non dispongono di un confronto ragionevole a causa di differenze architettoniche tra i dati della suite di rapporti e i dati della piattaforma. Gli esempi includono visite/sessioni, visitatori/persone e eventi/eventi.
