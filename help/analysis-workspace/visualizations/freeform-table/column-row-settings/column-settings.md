---
description: Le impostazioni colonna consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.
title: Impostazioni colonna
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 98%

---

# [!UICONTROL Column Settings]

Le [!UICONTROL Column Settings] consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.

Visualizza un video sulle impostazioni di riga e colonna qui:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## Modificare [!UICONTROL Column Settings] {#edit-column-settings}

Per accedere a [!UICONTROL Column Settings], trascina una tabella a forma libera nel progetto e fai clic sull’icona con l’ingranaggio nell’intestazione della colonna.

![](assets/column_settings.png)

È possibile modificare le impostazioni di **più colonne alla volta**. Seleziona più colonne e fai clic sull’icona delle impostazioni di una delle colonne. Le modifiche apportate verranno applicate a tutte le colonne contenenti celle selezionate.

| Elemento | Descrizione |
| --- | --- |
| Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| Anomalie | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale. |
| Grafico a barre | Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. |
| Formattazione condizionale | Consulta la sezione successiva. |
| Table Cell Preview (Anteprima celle tabella) | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |

## Formattazione condizionale {#conditional-formatting}

La formattazione condizionale applica la formattazione ai limiti superiori e inferiori e ai punti intermedi definiti dall’utente. L’applicazione della formattazione condizionale (colori, ecc.) nelle tabelle a forma libera è inoltre abilitata automaticamente nelle suddivisioni, a meno che non venga selezionata l’opzione per limiti personalizzati.

![](assets/conditional-formatting.png)

| Elemento | Descrizione |
| --- | --- |
| Formattazione condizionale | Applica i seguenti colori alle celle sulla base dei valori dei dati: <ul><li>Verde: valori massimi</li><li>Giallo: valori intermedi</li><li>Rosso: valori minimi</li></ul> <br> La sostituzione di una dimensione nella tabella ridefinisce i limiti della formattazione condizionale. La sostituzione di un dato ricalcola i limiti per la colonna (dove il dato si trova sull’asse X e la dimensione sull’asse Y). |
| Use Percent Limits (Usa limiti percentuali) | Modifica l’intervallo di limiti in modo che sia basato su percentuali anziché su valori assoluti. Funziona sia per metriche basate unicamente sulle percentuali (come Bounce Rate, o frequenza di rimbalzo), sia per quelle basate su conteggio e percentuale (come Visualizzazioni di pagina). |
| Generazione automatica | Calcola automaticamente i limiti superiori/medi/inferiori in base ai dati. Il limite superiore corrisponde al valore massimo nella colonna. Il limite inferiore corrisponde a quello minimo e il punto intermedio è la media fra il limite superiore e quello inferiore. |
| Personalizzato | Assegna manualmente i limiti superiori/medi/inferiori. Ciò offre la flessibilità di poter determinare quando il valore di una colonna diventa buono, medio o scarso. |

## Usa modello di attribuzione non predefinito {#attribution}

Analysis Workspace supporta l’[attribuzione](/help/analysis-workspace/attribution/overview.md) per quasi tutte le metriche.

1. Fai clic sull’icona delle impostazioni (a forma di ingranaggio) nella colonna di una tabella a forma libera.

   ![Casella di controllo di attribuzione](assets/attribution-checkbox.png)

1. In **[!UICONTROL Data Settings]**, spunta **[!UICONTROL Use non-default attribution model]**. Per ulteriori informazioni sui diversi modelli di attribuzione, consulta [Modelli di attribuzione](/help/analysis-workspace/attribution/models.md).

   ![Selezione del modello di attribuzione](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gestione delle origini dati](/help/analysis-workspace/visualizations/t-sync-visualization.md)

