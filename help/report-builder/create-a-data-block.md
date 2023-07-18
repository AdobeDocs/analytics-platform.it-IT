---
title: Come creare un blocco di dati utilizzando il Report Builder nel Customer Journey Analytics
description: Descrive come creare un blocco di dati.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: fe52730e3904ba5ccc5d1e7e5ff89eed8a575fbc
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Creare un blocco di dati

A *blocco di dati* è la tabella di dati creata da una singola richiesta di dati. Una cartella di lavoro di Report Builder può contenere più blocchi di dati. Quando crei un blocco di dati, configura prima il blocco di dati e quindi lo genera.

## Configurare il blocco di dati

Configura i parametri iniziali dei blocchi di dati per la posizione del blocco di dati, le visualizzazioni dati e un intervallo di date.

1. Clic **Creare un blocco di dati**.

   ![](./assets/create_db.png)

1. Imposta il **Posizione blocco dati**.

   L&#39;opzione Posizione blocco dati definisce la posizione del foglio di lavoro in cui Report Builder aggiunge i dati al foglio di lavoro.

   Per specificare la posizione del blocco di dati, selezionare una singola cella nel foglio di lavoro oppure immettere un indirizzo di cella come a3, \\\$a3, a\\\$3 o sheet1!a2. La cella specificata sarà l’angolo superiore sinistro del blocco di dati quando i dati vengono recuperati.

1. Scegli la **Visualizzazioni dati**.

   L’opzione Visualizzazioni dati consente di scegliere una visualizzazione dati da un menu a discesa o di fare riferimento a una visualizzazione dati da una posizione cella.

1. Imposta il **Intervallo di date**.

   L’opzione Intervallo date ti consente di scegliere un intervallo di date. Gli intervalli di date possono essere fissi o continui. Per informazioni sulle opzioni dell’intervallo di dati, consulta [Seleziona un intervallo di date](select-date-range.md).

1. Clic **Successivo**.

   ![](./assets/choose_date_data_view3.png)

   Dopo aver configurato il blocco di dati, puoi selezionare dimensioni, metriche e filtri per crearlo. Le schede Dimension, Metriche e Filtri vengono visualizzate sopra il riquadro Generatore tabella.
<!--
    ![](./assets/image9.png)
  -->


## Creare il blocco di dati

Per creare il blocco di dati, seleziona i componenti del rapporto, quindi personalizza il layout.

1. Aggiungere Dimension, metriche e filtri.

   Scorri gli elenchi dei componenti o utilizza **ricerca** per individuare i componenti. Trascina i componenti nel riquadro Tabella oppure fai doppio clic sul nome di un componente nell’elenco per aggiungerlo automaticamente al riquadro Tabella.

   Fai doppio clic su un componente per aggiungerlo a una sezione predefinita della tabella.

   - I componenti Dimension vengono aggiunti alla sezione Riga o alla sezione Colonna se una dimensione è già presente nelle colonne.
   - I componenti data vengono aggiunti alla sezione Colonna.
   - I componenti Filtro vengono aggiunti alla sezione Filtri.

1. Disporre gli elementi nel riquadro Tabella per personalizzare il layout del blocco di dati.

   Trascina i componenti nel riquadro Tabella per riordinarli oppure fai clic con il pulsante destro del mouse sul nome di un componente e scegli dal menu delle opzioni.

   Quando si aggiungono componenti alla tabella, nella posizione del blocco di dati nel foglio di lavoro viene visualizzata un&#39;anteprima del blocco di dati. Il layout dell’anteprima dei blocchi di dati viene aggiornato automaticamente quando aggiungi, sposti o rimuovi elementi nella tabella.

   ![](./assets/image10.png)

   **Visualizzare o nascondere le intestazioni di riga e di colonna**

1. Fai clic su **Tabella** impostazioni.

   ![immagine segnaposto](./assets/table-settings.png){width="35%"}

1. Seleziona o deseleziona l’opzione per Visualizzare le intestazioni di riga e colonna. Le intestazioni vengono visualizzate per impostazione predefinita.

   **Nascondere o mostrare etichette dimensione e intestazioni metriche**

1. Fai clic sull’icona dei puntini di sospensione sulle dimensioni o sulle intestazioni di colonna per visualizzare le impostazioni.

   ![immagine segnaposto](./assets/row-heading.png){width="35%"}

1. Fate clic su Nascondi (Hide) o Mostra (Show) per attivare/disattivare le etichette di quota o le intestazioni di colonna. Tutte le etichette sono visualizzate per impostazione predefinita.

1. Clic **Fine**.

   Durante il recupero dei dati di analisi viene visualizzato un messaggio di elaborazione.

   ![](./assets/image11.png)

   Il Report Builder recupera i dati e visualizza il blocco di dati completato nel foglio di lavoro.

   ![](./assets/image12.png)
