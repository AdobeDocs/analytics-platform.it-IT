---
title: Come creare una nuova visualizzazione dati nel Customer Journey Analytics.
description: Descrive tutte le impostazioni necessarie per creare nuove visualizzazioni dati.
translation-type: tm+mt
source-git-commit: 1071ee32d0ff7fef1d3e96cb81c210dd521cedf0
workflow-type: tm+mt
source-wordcount: '2347'
ht-degree: 2%

---


# Creare una nuova visualizzazione dati

>[!IMPORTANT]
>
>Questa funzionalità sarà generalmente disponibile il 22 aprile 2021.

La creazione di una visualizzazione dati comporta la creazione di metriche e dimensioni dagli elementi dello schema o l’utilizzo di componenti standard. La creazione di metriche o dimensioni offre un&#39;enorme flessibilità. In precedenza, si presupponeva che in Adobe Experience Platform i set di dati fossero utilizzati come campi stringa e come metriche. Per modificare uno qualsiasi di questi campi, era necessario modificare lo schema in Platform. L&#39;interfaccia utente per la visualizzazione dei dati ora consente una [definizione più a forma libera di metriche e dimensioni](/help/data-views/data-views.md). Per ulteriori casi d’uso, consulta [Casi d’uso delle visualizzazioni dati](/help/data-views/data-views-usecases.md).

## 1. Configurare le impostazioni e i contenitori delle visualizzazioni dati

1. In Customer Journey Analytics, accedi alla scheda **[!UICONTROL Data Views]**.
2. Fai clic su **[!UICONTROL Add]** per creare una nuova visualizzazione dati e configurarne le impostazioni.

![](assets/new-data-view.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Connection] | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| [!UICONTROL Name] | È obbligatorio assegnare un nome alla visualizzazione dati. |
| [!UICONTROL Description] | Una descrizione dettagliata non è obbligatoria, ma è consigliata. |
| [!UICONTROL Time zone] | Scegli il fuso orario in cui dovranno essere presentati i dati. |
| [!UICONTROL Tags] | I tag ti consentono di organizzare le visualizzazioni dati in categorie. |
| [!UICONTROL Containers] | Puoi rinominare i contenitori qui ed ecco come appariranno in qualsiasi progetto Workspace basato su questa visualizzazione dati. I contenitori vengono utilizzati nei filtri e nell’abbandono/flusso per definire l’ampiezza o la restringenza dell’ambito o del contesto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| [!UICONTROL Person container name is…] | [!UICONTROL Person] (predefinito). Il contenitore [!UICONTROL Person] include ogni visita e visualizzazione di pagina per i visitatori entro un intervallo di tempo specificato. È possibile rinominarlo &quot;Utente&quot; o qualsiasi altro termine preferito. |
| [!UICONTROL Session container name is…] | [!UICONTROL Session] (predefinito). Il contenitore [!UICONTROL Session] ti consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Puoi rinominarlo in &quot;Visita&quot; o in qualsiasi altro termine preferito. |
| [!UICONTROL Event container name is…] | [!UICONTROL Event] (predefinito). Il contenitore [!UICONTROL Event] definisce gli eventi di pagina da includere o escludere da un filtro. |

Successivamente, puoi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti Standard .

## 2. Creazione di metriche e dimensioni dagli elementi dello schema

1. In [!UICONTROL Customer Journey Analytics] > [!UICONTROL Data Views], fai clic sulla scheda [!UICONTROL Components] .

![](assets/components-tab.png)

Puoi vedere il [!UICONTROL Connection] in alto a sinistra, che contiene i set di dati, e il relativo [!UICONTROL Schema fields] qui sotto.

1. Ora trascina un campo schema, ad esempio [!UICONTROL pageTitle], dalla barra a sinistra nella sezione Metriche o Dimension .

   Puoi trascinare più volte lo stesso campo schema nelle sezioni di dimensioni o metriche e configurare la stessa dimensione o metrica in modi diversi. Ad esempio, dal campo **[!UICONTROL pageTitle]** puoi creare una dimensione denominata &quot;Pagine di prodotto&quot; e un’altra denominata &quot;Pagine di errore&quot;, ecc. dal **[!UICONTROL pageTitle]**; Puoi anche creare metriche da un valore stringa. Ad esempio, puoi creare una o più metriche **[!UICONTROL Orders]** con diverse impostazioni di attribuzione e diversi valori di inclusione/esclusione.

   ![](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Puoi trascinare dall’barra a sinistra intere cartelle di campi schema, che verranno ordinate automaticamente nelle sezioni tradizionali. I campi stringa finiranno nella sezione [!UICONTROL Dimensions] e le cifre nella sezione [!UICONTROL Metrics]. In alternativa, puoi fare clic su **[!UICONTROL Add all]** per aggiungere tutti i campi dello schema.

1. Una volta selezionato il componente, vengono visualizzate una serie di impostazioni a destra. Configura il componente utilizzando le impostazioni descritte di seguito.

### Configurare le impostazioni dei componenti

![](assets/component-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Component type] | Obbligatorio. Consente di cambiare un componente da Metrica a Dimension o viceversa. |
| [!UICONTROL Component Name] | Obbligatorio. Consente di specificare il nome descrittivo che verrà visualizzato in Analysis Workspace. È possibile rinominare un componente per assegnargli un nome specifico per la visualizzazione dati. |
| [!UICONTROL Description] | Facoltativo ma consigliato per fornire informazioni sul componente per altri utenti. |
| [!UICONTROL Tags] | Facoltativo. Consente di assegnare al componente tag personalizzati o predefiniti per facilitarne la ricerca e il filtraggio nell’interfaccia utente di Analysis Workspace. |
| [!UICONTROL Field Name] | Nome del campo schema. |
| [!UICONTROL Dataset type] | Obbligatorio. Un campo non modificabile che mostra il tipo di set di dati (evento, ricerca o profilo) da cui proviene il componente. |
| [!UICONTROL Dataset] | Obbligatorio. Un campo non modificabile che mostra il tipo di campo di origine del componente (ad esempio Stringa, Intero, ecc.). Questo campo può contenere più set di dati, ad esempio quando si combinano più suite di rapporti. |
| [!UICONTROL Schema type] | Indica se il componente è una stringa, un numero intero, ecc. |
| [!UICONTROL Component ID] | Obbligatorio. Il [CJA API](https://adobe.io/cja-apis/docs) utilizza questo campo per fare riferimento al componente. Puoi fare clic sull’icona di modifica e modificare l’ID del componente. Tuttavia, la modifica dell’ID del componente interrompe tutti i progetti Workspace esistenti che contengono questo componente.<br>Se crei un’altra visualizzazione dati che utilizza un campo diverso per una dimensione pageTitle, puoi rinominarla e rendere compatibile la visualizzazione dati incrociati della dimensione. |
| [!UICONTROL Path] | Obbligatorio. Un campo non modificabile che mostra il percorso dello schema da cui proviene il componente. |
| [!UICONTROL Hide component in reporting] | Predefinito = disattivato. Consente di eliminare il componente dalla visualizzazione dati quando utilizzato nel rapporto. Questo non influisce sulle autorizzazioni, ma solo sulla cura dei componenti. In altre parole, puoi nascondere il componente da non amministratori nel reporting. Gli amministratori possono comunque accedervi facendo clic su [!UICONTROL Show All Components] in un progetto Analysis Workspace. |

### Configurare le impostazioni del formato

Le impostazioni del formato sono solo per le metriche.

![](assets/format-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Format] | Consente di specificare la formattazione di una metrica, come Decimale, Tempo, Percentuale o Valuta. |
| [!UICONTROL Decimal Places] | Consente di specificare il numero di posizioni decimali da visualizzare in una metrica. |
| [!UICONTROL Show upward trend as] | Consente di specificare se una tendenza verso l’alto per questa metrica deve essere considerata buona (verde) o cattiva (rossa). |
| [!UICONTROL Currency] | Questa impostazione viene visualizzata solo se il formato della metrica selezionata è [!UICONTROL Currency]. È disponibile un elenco di opzioni di valuta. Il valore predefinito è nessuna valuta. Questo ti consente di rappresentare i ricavi nella valuta scelta nel reporting. Questa non è una conversione di valuta, ma solo un&#39;opzione di formattazione dell&#39;interfaccia utente. |

### Configurare le impostazioni di attribuzione

![](assets/attribution-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set attribution] | Consente di specificare le impostazioni di attribuzione da applicare a questa metrica per impostazione predefinita quando viene utilizzata. Questa impostazione predefinita può essere ignorata nelle tabelle a forma libera o in una metrica calcolata. |
| [!UICONTROL Attribution model] | Consente di specificare un modello di attribuzione predefinito, attivo solo quando si attiva l’impostazione [!UICONTROL Use Non-default attribution model]. Predefinito su [!UICONTROL Last Touch]. Le opzioni sono: Ultimo contatto, Primo contatto, Lineare, Partecipazione, Stesso contatto, A forma di U, Curva J, J inversa, Decadimento nel tempo, Personalizzato, Algoritmico. Alcune di queste opzioni creano campi aggiuntivi da compilare, come Personalizzato o Decadimento nel tempo. È possibile creare più metriche utilizzando lo stesso campo, il che significa che è possibile avere una metrica di entrate [!UICONTROL Last touch] e una metrica di ricavi [!UICONTROL First Touch], ma basata sullo stesso campo di ricavi nello schema. |
| [!UICONTROL Lookback window] | Consente di specificare un intervallo di lookback predefinito per una metrica, attivo solo quando si attiva l’impostazione [!UICONTROL Use Non-default attribution model]. Le opzioni sono: Persona (finestra di reporting), Sessione, Personalizzata. Quando è selezionata l’opzione Personalizzato , è anche possibile selezionare un numero qualsiasi di giorni/settimane/mesi/ecc. (fino a 90 giorni), proprio come le Attribution IQ. Puoi avere più metriche utilizzando lo stesso campo dello schema, ma ciascuna con un intervallo di lookback separato. |

### Configurare le impostazioni Includi/Escludi valori

Questa impostazione consente di modificare i dati sottostanti sui quali si sta eseguendo il reporting al momento della query. Non è lo stesso di un filtro (precedentemente denominato segmento). Ma i filtri rispetteranno questa nuova dimensione, così come il percorso e l’attribuzione.

Ad esempio, puoi creare una dimensione fuori dal campo pageTitle , ma chiamarla &quot;pagine di errore&quot; e includere qualsiasi pagina che sia [!UICONTROL contains the phrase] &quot;error&quot;.

![](assets/include-exclude.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Case sensitive] | Predefinito = attivato. Questa impostazione si applica solo alla sezione [!UICONTROL Include/Exclude Values]. Ti consente di stabilire se la regola di inclusione/esclusione che stai applicando deve fare distinzione tra maiuscole e minuscole. |
| [!UICONTROL Match] | Consente di specificare quali valori si desidera considerare per il reporting prima dell’attribuzione e della segmentazione (ad esempio, utilizza solo valori contenenti la frase &quot;error&quot;). Puoi specificare: **[!UICONTROL If all criteria are met]** o **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Consente di specificare la logica di corrispondenza da applicare a una regola di filtro specifica.<ul><li>**Stringa**: Contiene la frase, Contiene qualsiasi termine, Contiene tutti i termini, Non contiene alcun termine, Non contiene la frase, È uguale a, Non uguale a, Inizia con, Termina con</li><li>**Doppio/Intero**: è uguale a, non è uguale a, è maggiore di, è minore di, è maggiore o uguale a, è minore o uguale a</li><li>**Data**: è uguale a, non è uguale a, è successivo a, è precedente, si trova in</li></ul> |
| [!UICONTROL Match operand] | Consente di specificare l’operando di corrispondenza a cui deve essere applicato l’operatore di corrispondenza.<ul><li>**Stringa**: Campo di testo</li><li>**Doppio/Intero**: Campo di testo con frecce verso l’alto o il basso per i valori numerici</li><li>**Data**: Selettore di granularità del giorno (calendario)</li><li>**Data e ora**: Selettore di granularità data e ora</li></ul> |
| [!UICONTROL Add rule] | Consente di specificare un operatore di corrispondenza e un operando aggiuntivi. |

### Configurare le impostazioni del comportamento

![](assets/behavior-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Count values] | Questo consente di creare un conteggio del numero di volte in cui un campo booleano è stato impostato su `true`; come metrica. Ad esempio, il numero di [!UICONTROL Page Views] in cui un campo booleano denominato `isPage` è impostato su `true`. |
| [!UICONTROL Count instances] | Consente di specificare se un campo numerico o di tipo data utilizzato come metrica deve contare le ore impostate anziché il valore stesso.<br> Se si desidera sommare le istanze di un campo numerico e si desidera semplicemente aggiungere il numero di volte in cui è stato  ** impostato un campo, anziché il valore effettivo all’interno.<br>Questa funzione è utile, ad esempio, per creare una  [!UICONTROL Orders] metrica da un  [!UICONTROL Revenue] campo. Se sono stati impostati i ricavi, vogliamo contare 1 singolo ordine invece dell&#39;importo numerico dei ricavi. |

### Configurare le impostazioni [!UICONTROL No Value Options]

[!UICONTROL No Value Options] le impostazioni sono simili ai  [!UICONTROL Unspecified] valori  [!UICONTROL None] o nel reporting. Nell’interfaccia utente delle visualizzazioni dati, a seconda dei singoli componenti, puoi decidere come trattare questi valori nei rapporti. Puoi anche rinominare [!UICONTROL No value] in modo che sia più adatto al tuo ambiente, ad esempio [!UICONTROL Null], [!UICONTROL Not set] o ad altri.

Inoltre, qualsiasi cosa specifichi in questo campo può essere utilizzata per un trattamento speciale dell’interfaccia utente della riga [!UICONTROL No Value] nel reporting, come indicato nell’impostazione [!UICONTROL No Value Options].

![](assets/no-value-options.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL If shown, call No value]… | In questo punto è possibile rinominare **[!UICONTROL No value]** in un altro elemento. |
| [!UICONTROL Don't show No value by default] | Questo valore non viene visualizzato nel rapporto. |
| [!UICONTROL Show No value by default] | Mostra questo valore nel rapporto. |
| [!UICONTROL Treat No value as a value] | Ad esempio, se la dimensione include tipi di dispositivi mobili, puoi rinominare l’elemento **[!UICONTROL No value]** in &quot;Desktop&quot;. Tieni presente che quando modifichi questo campo in un valore personalizzato, il valore personalizzato viene considerato come un valore di stringa legittimo. Pertanto, se si immette il valore &quot;Rosso&quot; in questo campo, anche tutte le istanze della stringa &quot;Rosso&quot; che compaiono nei dati stessi verranno riportate sotto la stessa riga specificata. |

### Configurare le impostazioni di persistenza

![](assets/persistence.png)

Queste impostazioni sono simili alle impostazioni eVar nella versione tradizionale di Adobe Analytics.

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set persistence] | Tasto di attivazione/disattivazione |
| [!UICONTROL Allocation] | Consente di specificare il modello di allocazione utilizzato su una dimensione per la persistenza. Le opzioni sono: [!UICONTROL Most recent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL All]. Se desideri che un valore persista (simile alle eVar nella versione tradizionale di Analytics), questo è il punto in cui lo imposteresti. L’unica differenza chiave è che la persistenza massima impostabile è 90 giorni. Inoltre, [!UICONTROL Never expire] non è un’opzione. |
| [!UICONTROL Expiration] | Consente di specificare la finestra di persistenza per una dimensione. Le opzioni sono: [!UICONTROL Session] (predefinito), [!UICONTROL Person], [!UICONTROL Time], [!UICONTROL Metric]. Potrebbe essere necessario poter scadere la dimensione su un acquisto (ad esempio termini di ricerca interni o altri casi d’uso di merchandising). [!UICONTROL Metric] consente di specificare una delle metriche definite come scadenza per questa dimensione (ad esempio, una  [!UICONTROL Purchase] metrica). |

### Configurare le impostazioni di bucket dei valori

Ad esempio, un bucket &quot;compreso tra 5 e 10&quot; verrà visualizzato come voce di riga &quot;da 5 a 10&quot; nel reporting di Workspace.

![](assets/value-bucketing.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Bucket value] | Consente di creare una versione a blocchi di una dimensione numerica. Questo ti consente di creare rapporti su blocchi di ricavi o altri valori numerici come una dimensione nel reporting. Puoi creare fino a 5 blocchi. |
| [!UICONTROL Up to] | Consente di specificare i bordi del primo bucket dimensione numerica. Questo vale solo per le dimensioni numeriche. |
| [!UICONTROL Between and up to] | Consente di specificare i bordi dei bucket di dimensione numerica successivi. |
| [!UICONTROL Add bucket] | Consente di aggiungere un altro bucket alla creazione a blocchi di dimensioni numeriche. |

### Seleziona [!UICONTROL Standard components]

Oltre a creare metriche e dimensioni da elementi dello schema, puoi utilizzare componenti standard anche nelle visualizzazioni dati.

[!UICONTROL Standard components] sono componenti che non sono generati dai campi dello schema del set di dati, ma che sono invece generati dal sistema. Alcuni componenti di sistema sono necessari in qualsiasi visualizzazione dati per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![](assets/standard-components.png)

Componenti standard richiesti

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| [!UICONTROL People] | Metrica | Precedentemente noto come [!UICONTROL Unique Visitors] nel tradizionale Analytics. Questa metrica si basa sull’ID persona specificato in una connessione. |
| [!UICONTROL Sessions] | Metrica | Precedentemente noto come [!UICONTROL Visits] nel tradizionale Analytics. Questa metrica si basa sulle impostazioni di sessionizzazione specificate di seguito. |
| [!UICONTROL Events] | Metrica | Precedentemente noto come [!UICONTROL Occurrences] nel tradizionale Analytics. Questa metrica rappresenta il numero di righe di tutti i set di dati evento in una connessione. |
| [!UICONTROL Day] | Dimensione |  |
| [!UICONTROL Week] | Dimensione |  |
| [!UICONTROL Month] | Dimensione |  |
| [!UICONTROL Quarter] | Dimensione |  |
| [!UICONTROL Year] | Dimensione |  |
| [!UICONTROL Hour] | Dimensione |  |
| [!UICONTROL Minute] | Dimensione |  |

### Componenti standard opzionali

In qualsiasi visualizzazione dati sono necessari alcuni componenti di sistema per facilitare le funzionalità di reporting in Analysis Workspace, mentre quelli riportati di seguito sono facoltativi.

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metrica | Questa metrica conta il numero di eventi che sono stati il primo evento di una sessione. Utilizzato in una definizione di filtro (ad esempio &#39;[!UICONTROL Session Starts] exists&#39;), filtra fino al primo evento di ogni sessione. Questo è un comportamento diverso da [!UICONTROL Entries] in quanto conta sempre il primo evento di una sessione - non il primo valore presente per una dimensione in una sessione. |
| [!UICONTROL Session Ends] | Metrica | Questa metrica conta il numero di eventi che sono stati l’ultimo evento di una sessione. Simile a [!UICONTROL Session Starts], può anche essere utilizzato in una definizione di filtro per filtrare gli elementi fino all&#39;ultimo evento di ogni sessione. Questo è un comportamento diverso da [!UICONTROL Exits] in quanto conta sempre l’ultimo evento di una sessione - non l’ultimo valore presente per una dimensione in una sessione. |
| [!UICONTROL Time Spent (seconds)] | Metrica | La metrica [!UICONTROL Time Spent] funziona in modo simile alla metrica tradizionale Adobe Analytics: il tempo tra due valori diversi per una dimensione viene calcolato sommando al tempo stesso due valori diversi. Tuttavia, utilizzando la metrica Avvio sessione e Fine sessione, i clienti possono creare autonomamente le metriche calcolate [!UICONTROL Time Spent per Person] e [!UICONTROL Time Spent per Session] (consulta i filtri OOTB e le metriche di calcolo di seguito). |
| [!UICONTROL Time Spent per Event] | Dimensione | Dal punto di vista funzionale, si tratta solo di un allungamento della metrica di cui sopra. Forniamo i bucket predefiniti, ma ti permettono di cambiare i secchi in qualsiasi cosa ti piaccia. |
| [!UICONTROL Time Spent per Session] | Dimensione |  |
| [!UICONTROL Time Spent per Person] | Dimensione |  |
| [!UICONTROL Batch ID] | Dimensione |  |
| [!UICONTROL Dataset ID] | Dimensione |  |

### Filtrare campi e dimensioni/metriche dello schema

Puoi filtrare i campi dello schema nella barra a sinistra in base ai seguenti tipi di dati:

![](assets/filter-fields.png)

Puoi anche filtrare per set di dati e specificando se un campo di schema contiene dati o se si tratta di un&#39;identità:

![](assets/filter-other.png)

## 3. Aggiungi un filtro globale alla visualizzazione dati

Puoi aggiungere filtri (precedentemente denominati segmenti) applicabili all’intera visualizzazione dati, in modo analogo alla visualizzazione filtrata dei dati nelle suite di rapporti virtuali (Adobe Analytics tradizionale).

1. Fare clic sulla scheda [!UICONTROL Settings] in [!UICONTROL Data views].
1. Trascina un filtro dall’elenco nella barra a sinistra fino al campo [!UICONTROL Add filters] .
