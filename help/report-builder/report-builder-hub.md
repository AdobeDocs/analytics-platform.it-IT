---
title: Cos’è l’hub Report Builder in Customer Journey Analytics
description: Descrive i componenti dell’hub Report Builder
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: 48f5e9d6c5d3a33a5bae45e841eb8364b7172876
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 95%

---

# Hub Report Builder

Utilizza l’hub Report Builder per creare, aggiornare, eliminare e gestire i blocchi di dati.

L’hub Report Builder contiene i pulsanti Crea e Gestisci, l’elenco COMANDI e i pannelli QUICK EDIT (MODIFICA RAPIDA).

<img src="./assets/hub51.png" width="50%" alt="Hub Report Builder"/>


## Pulsanti Crea e Gestisci

Utilizza i pulsanti Crea o Gestisci per creare nuovi blocchi di dati o per gestire quelli esistenti.

## Pannello COMANDI

Utilizza il pannello COMANDI per accedere ai comandi compatibili con le celle selezionate o con un’azione precedente.

![Pannello Comandi nell’hub Report Builer](./assets/hub1.png)

### Comandi

| Comandi visualizzati | Quando è disponibile | Finalità |
|------|------------------|--------|
| Create data block (Crea blocco di dati) | Nella cartella di lavoro è selezionata una o più celle. | Utilizzato per creare un blocco di dati |
| Edit data block (Modifica blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzato per modificare un blocco di dati |
| Refresh data block (Aggiorna blocco di dati) | La selezione contiene almeno un blocco di dati. Il comando aggiorna solo i blocchi di dati nella selezione. | Utilizzato per aggiornare uno o più blocchi di dati |
| Refresh all data blocks (Aggiorna tutti i blocchi di dati) | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizzato per aggiornare tutti i blocchi di dati nella cartella di lavoro |
| Copy data block (Copia blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizzato per copiare un blocco di dati |
| Delete data block (Elimina blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzato per eliminare un blocco di dati |

## Pannello QUICK EDIT (MODIFICA RAPIDA)

Quando selezioni uno o più blocchi di dati in un foglio di calcolo, in Report Builder viene visualizzato il pannello QUICK EDIT (MODIFICA RAPIDA). Puoi utilizzarlo per modificare i parametri in un singolo blocco di dati o per modificare i parametri in più blocchi di dati contemporaneamente.

![Pannello Quick Edit (Modifica rapida) in Report Builder](./assets/hub2.png)

Le modifiche apportate utilizzando le sezioni di Quick Edit (Modifica rapida) si applicano a tutti i blocchi di dati selezionati.

### Visualizzazioni dati

I blocchi di dati estraggono i dati da una visualizzazione dati selezionata. Se più blocchi di dati sono selezionati in un foglio di lavoro e non estraggono dati dalla stessa visualizzazione dati, il collegamento **Visualizzazioni dati** visualizza *Multiple*.

Quando modifichi la visualizzazione dati, tutti i blocchi di dati nella selezione adottano la nuova visualizzazione dati. I componenti nel blocco di dati vengono associati alla nuova visualizzazione dati in base all’ID, ad esempio, corrispondente a ```evars```). Se un componente non viene trovato in un blocco di dati, viene visualizzato un messaggio di avvertenza e il componente viene rimosso dal blocco di dati.

Per modificare la visualizzazione dati, seleziona una nuova visualizzazione dati dal menu a discesa.

![Hub di Report Builder che mostra il menu a discesa della visualizzazione dati.](./assets/image16.png)

### Intervallo date

**Intervallo date** mostra l’intervallo di date per i blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più intervalli di date, il collegamento **Intervallo date** visualizza *Multiple* (Multiplo).

### Filtri

Il collegamento **Filtri** visualizza un elenco riepilogativo dei filtri utilizzati dai blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più filtri applicati, il collegamento **Filtri** visualizza *Multiple* (Multipli).
