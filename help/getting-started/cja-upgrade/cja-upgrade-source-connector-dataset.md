---
title: Aggiungere il set di dati del connettore di origine di Analytics alla connessione
description: Scopri come aggiungere il set di dati del connettore di origine di Analytics alla connessione
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 31%

---

# Aggiungere il set di dati del connettore di origine di Analytics alla connessione {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Aggiungere il set di dati del connettore di origine di Analytics alla connessione"
>abstract="Ora che i dati storici della suite di rapporti di Analytics sono in Adobe Experience Platform, aggiungi il set di dati alla connessione esistente creata durante la configurazione iniziale di Customer Journey Analytics. Una volta completato questo passaggio, i dati storici saranno disponibili in Customer Journey Analytics.<br><br>L’aggiunta di un set di dati a una connessione in Customer Journey Analytics è semplice e richiede solo pochi minuti per essere completata."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oppure i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

## Comprendere come il connettore di origine di Analytics può inserire dati storici in Customer Journey Analytics

Puoi usare il connettore di origine di Analytics per inserire in Adobe Experience Platform i dati della suite di rapporti di Adobe Analytics. Questi dati possono quindi essere utilizzati come dati storici in Customer Journey Analytics.

Questo processo presuppone che si desideri [creare uno schema XDM durante l&#39;aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), perché si desidera uno schema semplificato personalizzato in base alle esigenze della propria organizzazione e alle applicazioni Platform specifiche utilizzate.

Per utilizzare il connettore di origine di Analytics per inserire dati storici in Customer Journey Analytics, è necessario:

1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Se non disponi già di un connettore di origine Analytics, [crea il connettore di origine Analytics e mappa i campi sullo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oppure

   Se disponi già di un connettore di origine Analytics, [mappa i campi dal connettore di origine allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Aggiungi il set di dati del connettore di origine di Analytics alla connessione, come descritto di seguito.

## Aggiungere il set di dati del connettore di origine di Analytics alla connessione

Dopo aver [creato un connettore di origine Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), viene automaticamente creato un set di dati per i dati di Analytics.

È necessario aggiungere questo set di dati creato automaticamente alla stessa connessione creata per l’implementazione di Web SDK. In questo modo, i dati di Analytics vengono inseriti nella stessa visualizzazione dati in Customer Journey Analytics dei dati del Web SDK.

Per aggiungere il set di dati creato automaticamente alla stessa connessione creata per l’implementazione di Web SDK:

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]**.

1. Selezionare la connessione [creata per l&#39;implementazione di Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Seleziona **[!UICONTROL Edit]**.

   ![Modifica connessione](assets/connection-add-dataset.png)

1. Seleziona **[!UICONTROL Add datasets]** in alto a destra.

   ![Modifica connessione](assets/connection-add-dateset2.png)

1. Scorri fino al set di dati creato automaticamente al momento della creazione del connettore di origine di Analytics o esegui una ricerca per esso.

   Il nome di questo set di dati è il nome della suite di rapporti, seguito da `midValues`. Ad esempio: `My report suite midValues`

1. Selezionare la casella di controllo accanto al nome del set di dati, quindi selezionare **[!UICONTROL Next]**.

   ![Modifica connessione](assets/connection-add-dataset3.png)

1. Specifica le seguenti informazioni:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Disponibile solo per i set di dati evento e profilo. Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni. <p>Il valore per l’ID persona selezionato è considerato sensibile a maiuscole e minuscole. Ad esempio: `abc123` e `ABC123` sono due valori diversi. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento e riepilogo, questa impostazione viene settata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Timezone]** | Disponibile solo per i dati di riepilogo. Seleziona il fuso orario appropriato per i dati di riepilogo delle serie temporali. |
   | **[!UICONTROL Data source type]** | Seleziona un tipo di origine dati. <br/>I tipi di origini dati includono: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Questo campo viene utilizzato per esaminare i tipi di origini dati in uso. |

   {style="table-layout:auto"}

1. Nella sezione **[!UICONTROL Import new data]**, lascia disabilitata l&#39;opzione **[!UICONTROL Import all new data]**.

   Poiché utilizzi il set di dati del connettore di origine di Analytics per i dati storici, non desideri trasferire in questo set di dati i dati futuri raccolti.

1. Nella sezione **[!UICONTROL Dataset backfill]**, selezionare **[!UICONTROL Request backfill]**.

1. Definire il periodo che si desidera includere nella retrocompilazione della connessione in Customer Journey Analytics immettendo le date di inizio e di fine o selezionando l&#39;icona del calendario ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Indica in modo esplicito le date della richiesta di backfill. A seconda di diversi fattori, potrebbe essere utile effettuare una delle seguenti operazioni:

   * Scegli una data di fine corrispondente alla data della prima raccolta dei dati con l’implementazione di Web SDK.

   * Scegli una data di fine che sia poco successiva alla data in cui hai iniziato a raccogliere i dati con l’implementazione del Web SDK, quindi utilizza i segmenti di visualizzazione dati per filtrare i dati sovrapposti.

   * Scegli una data di fine che determini una maggiore sovrapposizione nei dati, quindi utilizza i segmenti di visualizzazione dati per filtrare i dati sovrapposti.

     **Nota:** questa opzione comporterebbe costi maggiori perché la connessione conterrebbe più righe.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Seleziona **[!UICONTROL Queue backfill]**.

1. Seleziona **[!UICONTROL Add datasets]**, quindi seleziona **[!UICONTROL Save]** per salvare la connessione.

1. (Condizionale) Se utilizzi i set di dati di ricerca, devi creare il set di dati di ricerca e aggiungerlo alla connessione. Per ulteriori informazioni, vedere [Creare set di dati di ricerca per classificare i dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Questa opzione è necessaria solo se non è già stata eseguita durante la configurazione dell’implementazione di Web SDK.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
