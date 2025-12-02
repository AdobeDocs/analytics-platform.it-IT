---
title: Unione
description: Scopri come creare e gestire i set di dati uniti
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Creare e gestire i set di dati con unione delle identità

{{select-package}}

L’unione consente agli amministratori di unire le identità sui set di dati disponibili in Customer Journey Analytics. L’unione dei set di dati aumenta la precisione della rappresentazione di un profilo, con conseguente miglioramento dell’analisi e del reporting.

Il processo di unione ti consente di definire un **ID persistente** esistente in un set di dati. Quindi unisci l&#39;identificatore persistente per una finestra di ripetizione specificata (giornaliera, settimanale) con l&#39;**ID persona** (identificatore persona o autenticato) più preciso disponibile per tale set di dati. Esempi di identificatori di persona sono e-mail, numero di telefono, ID del sistema di gestione delle relazioni con i clienti o altre identità memorizzate nel grafico. Per ulteriori informazioni sull&#39;unione, vedere [Panoramica](overview.md).

## Creazione

Per avviare l’unione, puoi creare uno o più set di dati uniti. Per creare un set di dati uniti:

1. Seleziona **[!UICONTROL ** Unione **]** da **[!UICONTROL **&#x200B; Gestione dati &#x200B;**]** nella barra superiore.

2. Nella schermata [!UICONTROL Set di dati uniti], selezionare **[!UICONTROL **&#x200B; Crea set di dati uniti &#x200B;**]**.

   Viene visualizzata una finestra di dialogo in cui vengono illustrate le proprie responsabilità.

3. Seleziona **[!UICONTROL **&#x200B; Continua &#x200B;**]** se accetti queste responsabilità.

   >[!NOTE]
   >
   >    Se si seleziona **[!UICONTROL **&#x200B; Annulla &#x200B;**]**, non è possibile creare un set di dati uniti.

4. Nella schermata [!UICONTROL Set di dati uniti > Set di dati uniti senza titolo]:

   1. Definisci un **[!UICONTROL ** nome set di dati **]** e (facoltativo) **[!UICONTROL **&#x200B; descrizione &#x200B;**]**,

   2. Seleziona la sandbox dall&#39;elenco **[!UICONTROL **&#x200B; Sandbox &#x200B;**]** in cui è memorizzato il set di dati dell&#39;evento.

      ![Schermata di creazione iniziale](./assets/create-initial.png)

   3. Selezionare il pulsante **[!UICONTROL **&#x200B; Seleziona set di dati di origine &#x200B;**]**.

      Nella finestra popup [!UICONTROL Seleziona un set di dati da unire]:

      ![Selezionare un set di dati](./assets/select-one-dataset.png)

      - Seleziona un set di dati e seleziona **[!UICONTROL **&#x200B; Seleziona &#x200B;**]** per continuare.

   4. Selezionare un identificatore permanente dall&#39;elenco **[!UICONTROL **&#x200B; ID persistente &#x200B;**]**.

   5. Selezionare un identificatore di persona dall&#39;elenco **[!UICONTROL **&#x200B; ID transitorio &#x200B;**]**.

      Viene visualizzato un pannello di anteprima per calcolare i tassi di saturazione (il numero di volte in cui è presente un valore per ciascuno degli identificatori specificati rispetto al numero di eventi) per gli ultimi sette giorni. Al termine del calcolo, il pannello visualizza con colori se le condizioni minime per l’unione sono soddisfatte (verde) o meno (rosso).

      ![Crea set di dati uniti con tassi di staturazione](./assets/create-before-experimenting.png)

      Le condizioni minime sono:

      - saturazione dell’identificatore persistente: tasso >= 95%

      - saturazione dell’identificatore della persona: tasso >= 5%

        Se vengono soddisfatte le condizioni minime, puoi provare con valori di esempio.

      - Seleziona **[!UICONTROL **&#x200B; Crea ID unione demo &#x200B;**]**.

        Nella finestra di dialogo [!UICONTROL Esperimento con valori di esempio], viene visualizzata una tabella con valore di esempio per [!UICONTROL timestamp], [!UICONTROL ID persistente], [!UICONTROL ID transitorio], [!UICONTROL ID vincolato (Live)], [!UICONTROL ID vincolato (riproduzione di 1 giorno)] e [!UICONTROL ID vincolato (riproduzione di 7 giorni)].

            .[Esperimento con valori di esempio](./assets/experiment-sample-values.png)
            
            1. Immetti un valore per **[!UICONTROL **ID persistente**]**.
            
            2. Seleziona **[!UICONTROL **Aggiorna ID uniti**]** per visualizzare l&#39;effetto del processo di unione sui dati nel set di dati.
            
            3. Seleziona **[!UICONTROL **Chiudi**]** al termine della sperimentazione con i valori di esempio.
        

        Torna alla schermata [!UICONTROL Set di dati uniti > _Nome set di dati_]:

   6. Selezionare un&#39;opzione per la frequenza e il periodo di riesecuzione dei dati storici dall&#39;elenco **[!UICONTROL **&#x200B; Finestra di ripetizione &#x200B;**]**.

      Puoi scegliere tra il valore predefinito **[!UICONTROL ** Giorno precedente, giornaliero **]** o **[!UICONTROL **&#x200B; 7 giorni precedenti, settimanale &#x200B;**]**.

   7. Selezionare un valore dall&#39;elenco **[!UICONTROL **&#x200B; Numero medio di eventi giornalieri &#x200B;**]**.

   8. Immetti un valore (compreso tra `0` e `12`) in **[!UICONTROL **&#x200B; Numero di mesi per il backfill &#x200B;**]**.

   9. Seleziona **[!UICONTROL **&#x200B; Salva &#x200B;**]** per salvare il set di dati uniti e avviare l&#39;unione.

## Visualizza stato

Puoi visualizzare lo stato dell&#39;unione nell&#39;elenco [!UICONTROL Set di dati uniti].

- Seleziona **[!UICONTROL ** Unione **]** da **[!UICONTROL **&#x200B; Gestione dati &#x200B;**]** nella barra superiore.

  Viene visualizzato un elenco di set di dati uniti, ciascuno identificato con [!UICONTROL Sandbox], [!UICONTROL Set di dati di Source], [!UICONTROL Stato], [!UICONTROL Stato backfill], [!UICONTROL Proprietario] e [!UICONTROL Data di creazione].

  ![Panoramica dei set di dati uniti](./assets/overview-stitched-datasetts.png)

  I valori possibili per [!UICONTROL Stato] sono:

  | Valore | Spiegazione |
  |-----|-----|
  | **[!UICONTROL **&#x200B; In coda &#x200B;**]** | La richiesta viene ricevuta ed elaborata a breve. |
  | **[!UICONTROL **&#x200B; Creazione &#x200B;**]** in corso | Le risorse e il set di dati appena uniti sono in fase di creazione. |
  | **[!UICONTROL **&#x200B; Unione in corso &#x200B;**]** | Esistono risorse e set di dati uniti e l’unione è in corso |
  | **[!UICONTROL **&#x200B; Errore &#x200B;**] **&#x200B; | Si è verificato un problema con l’unione. È possibile che uno schema sia stato modificato tra il set di dati di origine e il set di dati uniti, che il volume giornaliero sia troppo grande oppure... (_**&#x200B;ulteriori informazioni qui...**_) |

  >[!INFO]
  >
  >    Ogni volta che cambia lo stato, viene inviata una notifica con il messaggio **[!UICONTROL **&#x200B; Il set di dati uniti _nome del set di dati_ è cambiato in stato _nome dello stato _**]**.


  Lo stato di [!UICONTROL backfill] può avere i seguenti valori: 0%, 25%, 50%, 75% o 100%.

  Puoi selezionare l’icona delle informazioni per visualizzare una finestra a comparsa con ulteriori dettagli sul set di dati uniti selezionato.


## Eliminazione

>[!NOTE]
>
>È possibile eliminare solo i set di dati con stato [!UICONTROL Unione in corso], [!UICONTROL Errore] o [!UICONTROL In coda].


Per eliminare un singolo set di dati uniti:

- Seleziona **[!UICONTROL **...**]** per il set di dati uniti e seleziona **[!UICONTROL **&#x200B; Elimina &#x200B;**]** dal menu.

  ![Eliminare un set di dati uniti](./assets/delete-stitched-dataset.png)

Per eliminare più dati uniti:

- Seleziona più set di dati uniti utilizzando la casella di controllo all’inizio di ciascun set di dati elencato.

- Seleziona **[!UICONTROL **...**]** da uno dei set di dati uniti selezionati e seleziona **[!UICONTROL **&#x200B; Elimina &#x200B;**]** dal menu.
