---
title: Unione
description: Scopri come creare e gestire i set di dati uniti
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 1%

---

# Creare e gestire i set di dati con unione delle identità

{{select-package}}

L’unione consente agli amministratori di unire le identità sui set di dati disponibili in Customer Journey Analytics. L’unione dei set di dati aumenta la precisione della rappresentazione di un profilo, con conseguente miglioramento dell’analisi e del reporting.

Il processo di unione ti consente di definire un **ID persistente** esistente in un set di dati. Quindi unisci l&#39;identificatore persistente per una finestra di ripetizione specificata (giornaliera, settimanale) con il **ID transitorio** più preciso (identificatore persona o autenticato) disponibile per tale set di dati. Esempi di identificatori transitori sono e-mail, numero di telefono, ID del sistema di gestione delle relazioni con i clienti o altre identità memorizzate nel grafico. Per ulteriori informazioni sull&#39;unione, vedere [Panoramica](overview.md).

## Creazione

Per avviare l’unione, puoi creare uno o più set di dati uniti. Per creare un set di dati uniti:

1. Seleziona **[!UICONTROL ** Unione **]** da **[!UICONTROL ** Gestione dati **]** nella barra superiore.

2. Nella schermata [!UICONTROL Stitched datasets], seleziona **[!UICONTROL ** Crea set di dati uniti **]**.

   Viene visualizzata una finestra di dialogo in cui vengono illustrate le proprie responsabilità.

3. Seleziona **[!UICONTROL ** Continua **]** se accetti queste responsabilità.

   >[!NOTE]
   >
   >    Se si seleziona **[!UICONTROL ** Annulla **]**, non è possibile creare un set di dati uniti.

4. Nella schermata [!UICONTROL Stitched datasets > Untitled stitched dataset] (Schema senza titolo):

   1. Definisci un **[!UICONTROL ** nome set di dati **]** e (facoltativo) **[!UICONTROL ** descrizione **]**,

   2. Seleziona la sandbox dall&#39;elenco **[!UICONTROL ** Sandbox **]** in cui è memorizzato il set di dati dell&#39;evento.

      ![Schermata di creazione iniziale](./assets/create-initial.png)

   3. Selezionare il pulsante **[!UICONTROL ** Seleziona set di dati di origine **]**.

      Nella finestra popup [!UICONTROL Select one dataset to stitch]:

      ![Selezionare un set di dati](./assets/select-one-dataset.png)

      - Seleziona un set di dati e seleziona **[!UICONTROL ** Seleziona **]** per continuare.

   4. Selezionare un identificatore permanente dall&#39;elenco **[!UICONTROL ** ID persistente **]**.

   5. Selezionare un identificatore transitorio dall&#39;elenco **[!UICONTROL ** ID transitorio **]**.

      Viene visualizzato un pannello di anteprima per calcolare i tassi di saturazione (il numero di volte in cui è presente un valore per ciascuno degli identificatori specificati rispetto al numero di eventi) per gli ultimi sette giorni. Al termine del calcolo, il pannello visualizza con colori se le condizioni minime per l’unione sono soddisfatte (verde) o meno (rosso).

      ![Crea set di dati uniti con tassi di staturazione](./assets/create-before-experimenting.png)

      Le condizioni minime sono:

      - saturazione dell’identificatore persistente: tasso >= 95%

      - saturazione identificatore transitorio: tasso >= 5%

        Se vengono soddisfatte le condizioni minime, puoi provare con valori di esempio.

      - Seleziona **[!UICONTROL ** Crea ID unione demo **]**.

        Nella finestra di dialogo [!UICONTROL Experiment with sample values] viene visualizzata una tabella con valore di esempio per [!UICONTROL timestamp], [!UICONTROL Persistent ID], [!UICONTROL Transient ID], [!UICONTROL Stitched ID (Live)], [!UICONTROL Stitched ID (1-day replay)] e [!UICONTROL Stitched ID (7-day replay)].

            .[Esperimento con valori di esempio](./assets/experiment-sample-values.png)
            
            1.  Immettere un valore per **[!UICONTROL **Persistent ID**]**.
            
            2.  Selezionare **[!UICONTROL **Refresh stitched IDs**]** per visualizzare l&#39;effetto del processo di unione sui dati nel set di dati.
            
            3.  Selezionare **[!UICONTROL **Close**]** al termine della sperimentazione con i valori di esempio.
        

        Nella schermata [!UICONTROL Stitched datasets > _Nome set di dati_]:

   6. Selezionare un&#39;opzione per la frequenza e il periodo di riesecuzione dei dati storici dall&#39;elenco **[!UICONTROL ** Finestra di ripetizione **]**.

      Puoi scegliere tra il valore predefinito **[!UICONTROL ** Giorno precedente, giornaliero **]** o **[!UICONTROL ** 7 giorni precedenti, settimanale **]**.

   7. Selezionare un valore dall&#39;elenco **[!UICONTROL ** Numero medio di eventi giornalieri **]**.

   8. Immetti un valore (compreso tra `0` e `12`) in **[!UICONTROL ** Numero di mesi per il backfill **]**.

   9. Seleziona **[!UICONTROL ** Salva **]** per salvare il set di dati uniti e avviare l&#39;unione.

## Visualizza stato

È possibile visualizzare lo stato dell&#39;unione nell&#39;elenco [!UICONTROL Stitched datasets].

- Seleziona **[!UICONTROL ** Unione **]** da **[!UICONTROL ** Gestione dati **]** nella barra superiore.

  Viene visualizzato un elenco di set di dati uniti, ciascuno identificato con [!UICONTROL Sandbox], [!UICONTROL Source dataset], [!UICONTROL Status], [!UICONTROL Backfill status], [!UICONTROL Owner] e [!UICONTROL Date created].

  ![Panoramica dei set di dati uniti](./assets/overview-stitched-datasetts.png)

  I valori possibili per [!UICONTROL Status] sono:

  | Valore | Spiegazione |
  |-----|-----|
  | **[!UICONTROL ** In coda **]** | La richiesta viene ricevuta ed elaborata a breve. |
  | **[!UICONTROL ** Creazione **]** in corso | Le risorse e il set di dati appena uniti sono in fase di creazione. |
  | **[!UICONTROL ** Unione in corso **]** | Esistono risorse e set di dati uniti e l’unione è in corso |
  | **[!UICONTROL ** Errore **]** | Si è verificato un problema con l’unione. È possibile che uno schema sia stato modificato tra il set di dati di origine e il set di dati uniti, che il volume giornaliero sia troppo grande oppure... (_**ulteriori informazioni qui...**_) |

  >[!INFO]
  >
  >    Ogni volta che cambia lo stato, viene inviata una notifica con il messaggio **[!UICONTROL ** Il set di dati uniti _nome del set di dati_ è cambiato in stato _nome dello stato _**]**.


  [!UICONTROL Backfill status] può avere i seguenti valori: 0%, 25%, 50%, 75% o 100%.

  Puoi selezionare l’icona delle informazioni per visualizzare una finestra a comparsa con ulteriori dettagli sul set di dati uniti selezionato.


## Eliminazione

>[!NOTE]
>
>È possibile eliminare solo i set di dati con stato [!UICONTROL Stitching in progress], [!UICONTROL Error] o [!UICONTROL Queued].


Per eliminare un singolo set di dati uniti:

- Seleziona **[!UICONTROL **...**]** per il set di dati uniti e seleziona **[!UICONTROL ** Elimina **]** dal menu.

  ![Eliminare un set di dati uniti](./assets/delete-stitched-dataset.png)

Per eliminare più dati uniti:

- Seleziona più set di dati uniti utilizzando la casella di controllo all’inizio di ciascun set di dati elencato.

- Seleziona **[!UICONTROL **...**]** da uno dei set di dati uniti selezionati e seleziona **[!UICONTROL ** Elimina **]** dal menu.
