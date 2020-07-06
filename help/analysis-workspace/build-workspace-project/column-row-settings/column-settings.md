---
description: Le impostazioni colonna consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.
title: Impostazioni colonna
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 93%

---


# Impostazioni colonna

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Le impostazioni colonna consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.

## Impostazioni colonna {#section_C5A9C13553BF4BFDAD7FACE0139AECA3}

Per accedere a [!UICONTROL Column Settings] (Impostazioni colonna), trascina una tabella a forma libera nel progetto e fai clic sull’icona con l’ingranaggio nell’intestazione della colonna.

![](assets/column_settings.png)

È possibile modificare le impostazioni di **più colonne alla volta**. Seleziona più colonne e fai clic sull’icona delle impostazioni di una delle colonne. Le modifiche apportate verranno applicate a tutte le colonne contenenti celle selezionate.

| Elemento | Descrizione |
|--- |--- |
| Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| Anomalie | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale. |
| Grafico a barre | Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. |
| Formattazione condizionale | Consulta la sezione successiva. |
| Table Cell Preview (Anteprima celle tabella) | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |


## Formattazione condizionale {#section_3DD847151DA14914888A70FC4FD7BDFB}

La formattazione condizionale applica la formattazione ai limiti superiori e inferiori e ai punti intermedi definiti dall’utente. L’applicazione della formattazione condizionale (colori, ecc.) nelle tabelle a forma libera è inoltre abilitata automaticamente nelle suddivisioni, a meno che non venga selezionata l’opzione per limiti personalizzati.

![](assets/conditional-formatting.png)

| Elemento | Descrizione |
|--- |--- |
| Formattazione condizionale | Applica i seguenti colori alle celle sulla base dei valori dei dati: <ul><li>Verde: valori massimi</li><li>Giallo: valori intermedi</li><li>Rosso: valori minimi</li></ul><br>La sostituzione di una dimensione nella tabella ridefinisce i limiti della formattazione condizionale. La sostituzione di un dato ricalcola i limiti per la colonna (dove il dato si trova sull’asse X e la dimensione sull’asse Y). |
| Use Percent Limits (Usa limiti percentuali) | Permette di utilizzare limiti superiori e inferiori e punti intermedi basati sui valori percentuali per ogni metrica. Funziona sia per metriche basate unicamente sulle percentuali (come Bounce Rate, o frequenza di rimbalzo), sia per quelle basate su conteggio e percentuale (come Visualizzazioni di pagina). |
| Generazione automatica | Genera i limiti per la formattazione condizionale in modo automatico. Il limite superiore corrisponde al valore massimo nella colonna. Il limite inferiore corrisponde a quello minimo e il punto intermedio è la media fra il limite superiore e quello inferiore. |
| Personalizzato | Puoi assegnare manualmente i valori per i campi Limite superiore, Punto intermedio e Limite inferiore per la formattazione condizionale. Ciò offre la flessibilità di poter determinare quando il valore di una colonna diventa buono, medio o scarso. |
| Table Cell Preview (Anteprima celle tabella) | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |

## Usa modello attribuzione non predefinito

 Analysis Workspace supporta [l&#39;attribuzione](../../attribution/overview.md) per quasi tutte le metriche.

1. Fai clic sull’icona Impostazioni (a forma di ingranaggio) nella colonna di una tabella a forma libera.

   ![Casella di controllo Attribuzione](assets/attribution-checkbox.png)

2. Sotto **[!UICONTROL Data Settings]** (Impostazioni dati), spunta **[!UICONTROL Use non-default attribution model]** (Usa modello di attribuzione non predefinito). For more information on different attribution models, see [Attribution models](../../attribution/models.md).

   ![Seleziona modello di attribuzione](assets/attribution-select.png)


>[!MORELIKETHIS]
>
>* [Gestione delle origini dati](/help/analysis-workspace/visualizations/t-sync-visualization.md)

