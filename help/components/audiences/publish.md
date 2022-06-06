---
title: Creare e pubblicare tipi di pubblico in Profilo cliente in tempo reale
description: Scopri come pubblicare i tipi di pubblico dal Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: b7f0173959445cda64de4307bea8ce22ba5048cd
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 4%

---

# Creazione e pubblicazione di tipi di pubblico

>[!NOTE]
>
>Questa funzionalità è attualmente disponibile [prova limitata](/help/release-notes/releases.md).

Questo argomento illustra come creare e pubblicare tipi di pubblico rilevati nel Customer Journey Analytics (CJA) in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per il targeting dei clienti e la personalizzazione.

Leggi questo [panoramica](/help/components/audiences/audiences-overview.md) per acquisire familiarità con il concetto di pubblico CJA.

## Creare un pubblico

1. Per creare un pubblico, puoi iniziare in tre modi:

   | Metodo di creazione | Dettagli |
   | --- | --- |
   | Dal principale **[!UICONTROL Components]>[!UICONTROL Audiences]** menu | Viene visualizzata la pagina Audiences Manager (Audience Manager). Fai clic su **[!UICONTROL Create audience]** per aprire [!UICONTROL Audience builder]. |
   | Da una tabella a forma libera | Fai clic con il pulsante destro del mouse su un elemento in una tabella a forma libera e seleziona **[!UICONTROL Create an audience from selection]**. Questo metodo precompila il filtro con la dimensione o l’elemento dimensione selezionato nella tabella. |
   | Dall’interfaccia utente di creazione/modifica del filtro | Seleziona la casella che riporta **[!UICONTROL Create an audience from this filter]**. Questo metodo precompila il filtro. |

   {style=&quot;table-layout:auto&quot;}

1. Crea il pubblico.

   Configura queste impostazioni prima di pubblicare il pubblico.

   ![](assets/create-audience.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name] | Nome del pubblico. |
   | [!UICONTROL Tags] | Qualsiasi tag da assegnare al pubblico a scopo organizzativo. Puoi utilizzare un tag preesistente o inserirne uno nuovo. |
   | [!UICONTROL Description] | Aggiungi una buona descrizione del pubblico, per distinguerlo dagli altri. |
   | [!UICONTROL Refresh frequency] | Frequenza con cui desideri aggiornare il pubblico.<ul><li>Puoi scegliere di creare un pubblico una tantum (impostazione predefinita) che non necessita di aggiornamento, utile ad esempio per specifiche campagne una tantum.</li><li>È possibile selezionare altri intervalli di aggiornamento. Per la frequenza di 4 ore, esiste un limite di 150 tipi di pubblico, poiché questa frequenza di aggiornamento è molto intensa per l’elaborazione. Per gli altri intervalli, non esiste un numero massimo di tipi di pubblico.</li></ul> |
   | Data di scadenza | Quando il pubblico smetterà di rinfrescarsi. Il valore predefinito è 1 anno dalla data di creazione. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza del pubblico. |
   | Finestra di lookback di aggiornamento | Specifica la distanza dalla finestra dati da visualizzare nella creazione del pubblico. Il massimo è di 90 giorni. |
   | [!UICONTROL One-time date range] | Intervallo di date per pubblicare il pubblico una tantum. |
   | [!UICONTROL Filter] | I filtri sono l’input principale per il pubblico. Puoi aggiungere fino a 20 filtri. Questi filtri possono essere uniti con `And` o `Or` operatori. |
   | [!UICONTROL View sample IDs] | Un esempio di ID in questo pubblico. Utilizza la barra di ricerca per cercare ID di esempio. |

   {style=&quot;table-layout:auto&quot;}

1. Interpreta l’anteprima dati.

   L’anteprima del pubblico viene visualizzata nella barra a destra. Consente un’analisi avanzata del pubblico creato.

   ![](assets/data-preview.png)

   | Impostazione anteprima | Descrizione |
   | --- | --- |
   | [!UICONTROL Data preview] window | L’intervallo di date per il pubblico. |
   | [!UICONTROL Total people] | Numero sintetico del numero totale di persone presenti nel pubblico. Può raggiungere i 100 milioni di persone. Se il pubblico supera i 100 milioni di persone, devi ridurre la dimensione del pubblico prima di poterlo pubblicare. |
   | [!UICONTROL Audience size limit] | Mostra quanto è lontano dal limite di 100 milioni di spettatori. |
   | [!UICONTROL Estimated audience return] | Questa impostazione è utile per i clienti di retargeting di questo pubblico che ritornano al tuo sito. (In altre parole, che sono visti di nuovo in questo set di dati). <p>Qui puoi selezionare l’intervallo di tempo (7 giorni successivi, 2 settimane successive, mese successivo) per il numero stimato di clienti che potrebbero tornare. |
   | [!UICONTROL Estimated to return] | Questo numero fornisce un numero stimato di clienti fidelizzati nell’intervallo di tempo selezionato dall’elenco a discesa. Guardiamo il tasso di abbandono storico per il pubblico per prevedere questo numero. |
   | [!UICONTROL Preview metrics] | Questa impostazione ti consente di esaminare metriche specifiche per verificare se il pubblico contribuisce in misura sproporzionata a questa metrica, ad esempio &quot;[!UICONTROL Revenue]&#39; o &#39;[!UICONTROL Average time on site]&quot;. Ti dà il conteggio aggregato della metrica, così come la percentuale del totale che rappresenta. Puoi selezionare qualsiasi metrica disponibile nella visualizzazione dati. |
   | [!UICONTROL Namespaces included] | I namespace specifici associati alle persone nel pubblico. Alcuni esempi includono ECID, ID CRM, indirizzi e-mail e così via. |
   | [!UICONTROL Sandbox] | La [sandbox di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) in cui risiede il pubblico. Quando pubblichi questo pubblico in Platform, puoi utilizzarlo solo entro i confini di questa sandbox. |

   {style=&quot;table-layout:auto&quot;}

1. Verifica la configurazione del pubblico e fai clic su **[!UICONTROL Publish]**.

   Se tutto è andato bene, riceverai un messaggio di conferma della pubblicazione del pubblico.

1. Fai clic su **[!UICONTROL View audience in AEP]** all&#39;interno dello stesso messaggio e sarai portato al [Interfaccia utente del segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=en) in Adobe Experience Platform. Per ulteriori informazioni, consulta di seguito.

## Utilizzare i tipi di pubblico di CJA in Experience Platform

CJA ora prende tutte le combinazioni di namespace e ID dal pubblico pubblicato e le trasmette in streaming al Profilo cliente in tempo reale. RTCP esamina quindi ogni combinazione di spazio dei nomi/ID e cerca un profilo di cui potrebbe far parte. Se ne trova uno, aggiungerà lo spazio dei nomi e l’ID agli altri ID in questo profilo come attributo di appartenenza al segmento. Ora, ad esempio, &quot;user@adobe.com&quot; può essere eseguito il targeting su tutti i suoi dispositivi e canali. Se non viene trovato alcun profilo, ne viene creato uno nuovo.

Puoi visualizzare i tipi di pubblico CJA in Platform accedendo a **[!UICONTROL Segments]** > **[!UICONTROL Create segments]** > **[!UICONTROL Audiences]** scheda > **[!UICONTROL CJA Audiences]**.

Puoi trascinare i tipi di pubblico CJA nella definizione del segmento per i segmenti AEP.

![](assets/audiences-aep.png)

Se scegli di esportare questo pubblico in AEP Data Lake, verrà visualizzato come un set di dati conforme alla classe di schema del profilo individuale XDM:

![](assets/aep-datalake.png)


## Passaggi successivi

* Per gestire questo pubblico, vai alla pagina [Interfaccia utente di gestione](/help/components/audiences/manage.md).
