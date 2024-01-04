---
description: Scopri come modificare le impostazioni delle colonne per configurare la formattazione delle colonne, che può essere parzialmente condizionale.
title: Impostazioni colonna
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 77%

---

# [!UICONTROL Column Settings]

Le [!UICONTROL Column Settings] consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.

Visualizza un video sulle impostazioni di riga e colonna qui:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## Modificare [!UICONTROL Column Settings] {#edit-column-settings}

Per accedere a [!UICONTROL Column Settings], trascina una tabella a forma libera nel progetto e fai clic sull’icona con l’ingranaggio nell’intestazione della colonna.

![Impostazioni delle colonne che mostrano le celle totali, le celle di tabella e l&#39;anteprima delle celle di tabella.](assets/column_settings.png)

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

![Le opzioni di formattazione condizionale con Personalizzato selezionato.](assets/conditional-formatting.png)

| Elemento | Descrizione |
| --- | --- |
| Formattazione condizionale | Applica alle celle un set di colori preconfigurato scelto. A seconda delle 4 combinazioni di colori disponibili selezionate, i diversi colori vengono assegnati a valori alti, valori intermedi e valori bassi. <br> La sostituzione di una dimensione nella tabella ridefinisce i limiti della formattazione condizionale. La sostituzione di un dato ricalcola i limiti per la colonna (dove il dato si trova sull’asse X e la dimensione sull’asse Y). |
| Use Percent Limits (Usa limiti percentuali) | Modifica l’intervallo di limiti in modo che sia basato su percentuali anziché su valori assoluti. Funziona sia per metriche basate unicamente sulle percentuali (come Bounce Rate, o frequenza di rimbalzo), sia per quelle basate su conteggio e percentuale (come Visualizzazioni di pagina). |
| Generazione automatica | Calcola automaticamente i limiti superiori/medi/inferiori in base ai dati. Il limite superiore corrisponde al valore massimo nella colonna. Il limite inferiore corrisponde a quello minimo e il punto intermedio è la media fra il limite superiore e quello inferiore. |
| Personalizzato | Assegna manualmente i limiti superiori/medi/inferiori. Ciò offre la flessibilità di poter determinare quando il valore di una colonna diventa buono, medio o scarso. |
| Tavolozza con formattazione condizionale | Scegli quale delle 4 combinazioni di colori disponibili utilizzare per la formattazione condizionale. |

## Usa modello di attribuzione non predefinito {#attribution}

Consente di ignorare il modello di attribuzione predefinito impostato in [Visualizzazioni dati](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Quando aggiorni l’attribuzione di un componente a un modello di attribuzione non predefinito, tieni presente quanto segue:
>
>* **Quando si utilizza il componente in un rapporto con *una singola dimensione*:** L’attribuzione del componente ignora il modello di allocazione quando viene utilizzato un modello di attribuzione non predefinito.
>
>* **Quando si utilizza il componente in un rapporto con *dimensioni multiple*:** L’attribuzione del componente mantiene il modello di allocazione quando viene utilizzato un modello di attribuzione non predefinito.
>
>   Più dimensioni sono disponibili solo quando [esportazione di dati nel cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Per ulteriori informazioni sull’allocazione, consulta [Impostazioni dei componenti di persistenza](/help/data-views/component-settings/persistence.md).

Per utilizzare un modello di attribuzione non predefinito per una metrica in un Analysis Workspace:

1. Fai clic sull’icona Impostazioni (ingranaggio) di una metrica nella colonna di una tabella a forma libera.

   ![Le opzioni Column Setting (Impostazione colonna) evidenziano l’opzione Data Settings (Impostazioni dati): Use non-default attribution mode (Usa modalità di attribuzione non predefinita).](assets/attribution-checkbox.png)

2. In **[!UICONTROL Data Settings]**, spunta **[!UICONTROL Use non-default attribution model]**. Per ulteriori informazioni sui diversi modelli di attribuzione, consulta [Modelli di attribuzione](/help/data-views/component-settings/attribution.md).

   ![Le opzioni Column Attribution Model (Modello di attribuzione colonna) mostrano l&#39;opzione Lineare selezionata.](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gestione delle origini dati](/help/analysis-workspace/visualizations/t-sync-visualization.md)
