---
title: Come creare un blocco di dati utilizzando il Report Builder in CJA
description: Descrive come creare un blocco di dati.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: d946e6dbda608499594cf48a9456131485e7349a
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---


# Creare un blocco di dati

Un *blocco dati* è la tabella di dati creata da una singola richiesta di dati. Una cartella di lavoro di un Report Builder può contenere più blocchi di dati. Quando crei un blocco di dati, configura prima il blocco di dati e quindi crea il blocco di dati.

## Configurare il blocco dati

Configura i parametri del blocco dati iniziale per la posizione del blocco dati, le visualizzazioni dati e un intervallo di date.

1. Fai clic su **Crea blocco dati**.

   ![](./assets/create_db.png)

1. Imposta la **posizione del blocco dati**.

   L&#39;opzione di posizione del blocco dati definisce la posizione del foglio di lavoro in cui Report Builder aggiunge i dati al foglio di lavoro.

   Per specificare la posizione del blocco dati, selezionare una singola cella nel foglio di lavoro o immettere un indirizzo di cella come a3, \\\$a3, a\\$3 o sheet1!a2. Al momento del recupero dei dati, la cella specificata sarà l’angolo superiore sinistro del blocco di dati.

1. Scegli le **Visualizzazioni dati**.

   L’opzione Visualizzazione dati consente di scegliere una visualizzazione dati da un menu a discesa o di fare riferimento a una visualizzazione dati da una posizione cella.

1. Imposta l&#39; **Intervallo di date**.

   L’opzione Intervallo date consente di scegliere un intervallo di date. Gli intervalli di date possono essere fissi o continui. Per ulteriori informazioni sulle opzioni dell’intervallo di dati, consulta &lt;&lt; link to date range section >>.

1. Fare clic su **Avanti**.

   ![](./assets/choose_date_data_view3.png)

   Dopo aver configurato il blocco dati, puoi selezionare dimensioni, metriche e filtri per creare il blocco dati. Le schede Dimension, Metriche e Filtri sono visualizzate sopra il riquadro Generatore tabella .
<!--
    ![](./assets/image9.png)
  -->


## Creare il blocco di dati

Per creare il blocco di dati, selezionare i componenti del rapporto, quindi personalizzare il layout.

1. Aggiungi Dimension, metriche e filtri.

   Scorri gli elenchi dei componenti o utilizza il campo **search** per individuare i componenti. Trascina i componenti nel riquadro Tabella oppure fai doppio clic sul nome di un componente nell’elenco per aggiungere automaticamente il componente al riquadro Tabella .

   Fai doppio clic su un componente per aggiungerlo a una sezione predefinita della tabella.

   - I componenti Dimension vengono aggiunti alla sezione Riga o alla sezione Colonna se la dimensione è già presente nelle colonne.
   - I componenti Data vengono aggiunti alla sezione Colonna .
   - I componenti filtro vengono aggiunti alla sezione Filtri .

1. Disporre gli elementi nel riquadro Tabella per personalizzare il layout del blocco dati.

   Trascina i componenti nel riquadro Tabella per riordinare i componenti oppure fai clic con il pulsante destro del mouse sul nome di un componente e scegli dal menu delle opzioni.

   Quando si aggiungono componenti alla tabella, viene visualizzata un&#39;anteprima del blocco dati nella posizione del blocco dati nel foglio di lavoro. Il layout dell’anteprima del blocco dati viene aggiornato automaticamente quando si aggiungono, si spostano o si rimuovono elementi nella tabella.

   ![](./assets/image10.png)

1. Fare clic su **Fine**.

   Durante il recupero dei dati di analisi viene visualizzato un messaggio di elaborazione.

   ![](./assets/image11.png)

   Il Report Builder recupera i dati e visualizza il blocco dati completato nel foglio di lavoro.

   ![](./assets/image12.png)
