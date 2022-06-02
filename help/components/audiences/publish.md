---
title: Creare e pubblicare tipi di pubblico in Profilo cliente in tempo reale
description: Scopri come pubblicare i tipi di pubblico dal Customer Journey Analytics
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 6%

---


# Creazione e pubblicazione di tipi di pubblico

In questo argomento viene illustrato come pubblicare i tipi di pubblico rilevati in Customer Journey Analytics (CJA) in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per il targeting dei clienti e la personalizzazione.

## Creare un pubblico

1. Per creare un pubblico, puoi iniziare in tre modi:

   | Metodo di creazione | Dettagli |
   | --- | --- |
   | Da **[!UICONTROL Components]>[!UICONTROL Audiences]** | Viene visualizzata la pagina Audiences Manager (Audience Manager). Fai clic su **[!UICONTROL Create audience]** per aprire [!UICONTROL Audience builder]. |
   | Da una tabella a forma libera | Fai clic con il pulsante destro del mouse su un elemento in una tabella a forma libera e seleziona **[!UICONTROL Create an audience from selection]**. Questo metodo precompila il filtro con la dimensione o l’elemento dimensione selezionato nella tabella. |
   | Dall’interfaccia utente di modifica del filtro | Seleziona la casella che riporta **[!UICONTROL Create an audience from this filter]**. Questo metodo precompila il filtro. |

   {style=&quot;table-layout:auto&quot;}

1. Configura il pubblico.

   | Impostazione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name] | Nome del pubblico. |
   | [!UICONTROL Tags] | Qualsiasi tag da assegnare al pubblico a scopo organizzativo. Puoi utilizzare un tag preesistente o inserirne uno nuovo. |
   | [!UICONTROL Description] | Aggiungi una buona descrizione del pubblico, per distinguerlo dagli altri. |
   | [!UICONTROL Refresh frequency] | Frequenza con cui desideri aggiornare il pubblico.<ul><li>Puoi scegliere di creare un pubblico una tantum (impostazione predefinita) che non necessita di aggiornamento, utile ad esempio per specifiche campagne una tantum.</li><li>È possibile selezionare altri intervalli di aggiornamento. Per la frequenza di 4 ore, esiste un limite di 150 tipi di pubblico, poiché questa frequenza di aggiornamento è molto intensa per l’elaborazione. Per altri intervalli, non esiste un numero massimo di tipi di pubblico.</li></ul> |
   | Data di scadenza | Quando il pubblico smetterà di rinfrescarsi. Il valore predefinito è 1 anno dalla data di creazione. |
   | Finestra di lookback di aggiornamento | Specifica la distanza dalla finestra dati da visualizzare nella creazione del pubblico. Il massimo è di 90 giorni. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza della pianificazione. |
   | [!UICONTROL One-time date range] | Intervallo di date per pubblicare il pubblico una tantum. |
   | [!UICONTROL Filter] | I filtri sono l’input principale per il pubblico. Puoi aggiungere fino a 20 filtri. Questi filtri possono essere uniti con `And` o `Or` operatori. |

   {style=&quot;table-layout:auto&quot;}

1. Interpreta l’anteprima dati.

   L’anteprima del pubblico viene visualizzata nella barra a destra.

   | Impostazione anteprima | Descrizione |
   | --- | --- |
   | Finestra di anteprima dati | L’intervallo di date per il pubblico. |
   | Totale persone nel pubblico | Un numero di riepilogo che può arrivare fino a 100 milioni. |
   | Limite dimensione del pubblico | Mostra quanto è lontano dal limite di 100 milioni di spettatori. |
   | Restituzione stimata del pubblico |  |
   | Stima del ritorno | Numero di riepilogo... |
   | Anteprima metriche |  |

   {style=&quot;table-layout:auto&quot;}


