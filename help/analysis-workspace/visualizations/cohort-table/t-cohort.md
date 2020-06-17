---
description: Creare una coorte ed eseguire un rapporto di analisi per coorte in Analysis Workspace.
keywords: Analysis Workspace
title: Esecuzione di un rapporto di analisi per coorte
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 69%

---


# Configurare un [!UICONTROL Cohort Analysis] rapporto

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. In Analysis Workspace, fai clic sull’icona **[!UICONTROL Visualizations]** (Pannelli) nella barra a sinistra e trascina un **[!UICONTROL Cohort Table]** (Pannello vuoto) nell’area di lavoro.

   ![](assets/cohort-table.png)

1. Definisci **[!UICONTROL Inclusion Criteria]** (Criteri di inclusione), **[!UICONTROL Return Criteria]** (Criteri di ritorno), **[!UICONTROL Cohort Type]** (Tipo di coorte) e **[!UICONTROL Settings]** (Impostazioni) come definito nella tabella seguente.

| Elemento | Descrizione |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | Puoi applicare fino a 10 segmenti di inclusione e fino a 3 metriche di inclusione. Il dato definisce se un utente viene incluso in una coorte. Ad esempio, se il dato di inclusione è Orders (Ordini), solo gli utenti che hanno effettuato un acquisto durante l’intervallo di tempo dell’analisi della coorte saranno inclusi nella coorte iniziale.<br>L’operatore predefinito tra più metriche è AND, ma è possibile cambiarlo in OR. Inoltre, è possibile aggiungere alle metriche un filtro numerico. Ad esempio: “Visite >= 1”.</br> |
| **[!UICONTROL Return Criteria]** | Puoi applicare fino a 10 segmenti di ritorno e fino a 3 metriche di ritorno. Questa metrica indica se l’utente è stato mantenuto (Retention, fidelizzazione) o meno (Churn, abbandono). Ad esempio, se la metrica di ritorno è Visualizzazioni video, saranno considerati fidelizzati solo gli utenti che hanno visualizzato un video durante i periodi successivi (dopo il periodo in cui sono stati aggiunti a una coorte). Un altro dato che quantifica la fidelizzazione è Visits (Visite). |
| **[!UICONTROL Granularity]** | Granularità temporale per Day, Week, Month, Quarter, o Year (Giorno, Settimana, Mese, Trimestre, Anno). |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]** (Fidelizzazione), impostazione predefinita: una coorte di fidelizzazione misura se le coorti dei visitatori ritornano a visitare la proprietà digitale nel tempo. Si tratta della coorte standard che abbiamo sempre usato e indica il comportamento degli utenti in merito a ritorno e visite ripetute. A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL Churn]** (Abbandono): una coorte di abbandono (anche detta di “perdita” o “attrito”) misura il modo in cui le coorti di visitatori abbandonano la proprietà digitale nel tempo. Abbandono = 1 - Fidelizzazione. [!UICONTROL Churn] è una buona misura di persistenza e opportunità mostrandovi la frequenza con cui i clienti non tornano. Utilizzando la coorte di abbandono si possono analizzare e individuare specifiche aree su cui concentrarsi, ovvero i segmenti di coorte che richiedono maggiore attenzione. A [!UICONTROL Churn] Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]** (Calcolo continuo): consente di calcolare il livello di fidelizzazione o abbandono in base alla colonna precedente, non alla colonna Included (Inclusione) che è l’impostazione predefinita. [!UICONTROL Rolling Calculation] modifica il metodo di calcolo per i periodi di &quot;ritorno&quot;. Con il calcolo normale vengono trovati in modo indipendente gli utenti che rispondono ai criteri di “ritorno” e che rientrano nel periodo di inclusione, a prescindere dalla loro inclusione nella coorte per il periodo precedente. Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL Return] i criteri vengono applicati a ciascuno dei periodi che precedono il periodo selezionato. </br><br>**[!UICONTROL Latency Table]**: Una [!UICONTROL Latency] tabella misura il tempo trascorso prima e dopo l&#39;evento di inclusione. [!UICONTROL Latency] è ideale per l&#39;analisi pre/post. For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the [!UICONTROL Latency] table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the [!UICONTROL Latency] Table are calculated by users who meet the [!UICONTROL Inclusion] criteria on the inclusion period and then meet the [!UICONTROL Return] criteria in the periods before the inclusion period. Note that [!UICONTROL Latency] tables and [!UICONTROL Custom Dimension] Cohort cannot be used together.</br><br>**[!UICONTROL Custom Dimension Cohort]** (Coorte con dimensione personalizzata): consente di creare coorti in base alla dimensione selezionata, anziché in base al tempo (impostazione predefinita). Molti clienti vogliono poter analizzare le coorti in base a fattori diversi dal tempo. Con la nuova funzione per coorti con dimensione personalizzata hai la flessibilità di creare le coorti in base alle dimensioni che rispondono alle tue esigenze. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia, in base a valori diversi di tali dimensioni. The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL Custom Dimension]Dopo aver scelto l’opzione Cohort (Coorte con dimensione personalizzata), puoi trascinare nella zona di rilascio la dimensione che ti interessa. Puoi quindi confrontare elementi con dimensione simile in uno stesso periodo di tempo. Ad esempio, puoi confrontare le prestazioni per diverse città, diversi prodotti, diverse campagne ecc. Vengono restituiti i primi 14 elementi per la dimensione in questione. Per visualizzare solo specifici elementi per la dimensione scelta, puoi anche usare un filtro, passando il cursore a destra della dimensione che hai trascinato. Non è possibile utilizzare una [!UICONTROL Custom Dimension] coorte con la funzione [!UICONTROL Latency] Tabella.</br> |

1. Per regolare gli elementi **[!UICONTROL Cohort Table Settings]** (Impostazioni tabella coorte), fai clic sull’icona a forma di ingranaggio.

| Impostazione | Descrizione |
| Only show percent (Mostra solo percentuale) | Rimuove il valore del numero e visualizza solo la percentuale. || Round percent to nearest whole (Arrotonda al valore percentuale più vicino) | Arrotonda il valore percentuale al numero intero più vicino invece di mostrare il valore decimale. |
| Show Average Percent Row (Mostra riga percentuale media) | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media dei valori all’interno di ogni colonna. |

## Creare il [!UICONTROL Cohort Analysis] rapporto

1. Fai clic su **[!UICONTROL Build]** (Crea).

   ![Risultato passaggio](assets/cohort-report.png)

   Il rapporto mostra i visitatori che hanno effettuato un ordine (colonna *`Included`*) e che sono ritornati al sito nelle visite successive. La riduzione delle visite nel tempo consente di individuare i problemi e di prendere delle contro misure.
1. (Facoltativo) Crea un segmento da una selezione.

   Seleziona le celle (contigue o non contigue), quindi fai clic con il pulsante destro del mouse e scegli > **[!UICONTROL Create Segment From Selection]** (Crea segmento da selezione).

1. In the [Filter Builder](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html), further edit the segment, then click **[!UICONTROL Save]**.

   Il segmento salvato è disponibile per l’utilizzo nel pannello [!UICONTROL Segment] (Segmento) di [!UICONTROL Analysis Workspace].
1. Rinomina e salva il progetto della coorte.
1. (Facoltativo) [Cura e condividi](/help/analysis-workspace/curate-share/curate.md) i componenti dei progetti.

   >[!NOTE]
   >
   >Prima di curare un progetto è necessario salvarlo.

