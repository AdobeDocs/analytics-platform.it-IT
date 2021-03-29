---
title: Come creare una nuova visualizzazione dati nel Customer Journey Analytics.
description: Descrive tutte le impostazioni necessarie per creare nuove visualizzazioni dati.
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '2314'
ht-degree: 5%

---


# Creare una nuova visualizzazione dati

La creazione di una visualizzazione dati comporta la creazione di metriche e dimensioni dagli elementi dello schema o l’utilizzo di componenti standard. La creazione di metriche o dimensioni offre un&#39;enorme flessibilità. In precedenza, si presupponeva che in Adobe Experience Platform, se si disponevano di set di dati, i campi stringa erano dimensioni e i campi numerici erano metriche. Per modificare uno qualsiasi di questi campi, era necessario modificare lo schema in Platform. L’interfaccia utente per la visualizzazione dei dati ora consente una definizione più libera di metriche e dimensioni.

## Configurare le impostazioni e i contenitori delle visualizzazioni dati

1. Al Customer Journey Analytics, vai alla scheda **Visualizzazioni dati** .
2. Fai clic su **Aggiungi** per creare una nuova visualizzazione dati e configurarne le impostazioni.

![](assets/new-data-view.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| Connessione | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| Nome | È obbligatorio assegnare un nome alla visualizzazione dati. |
| Descrizione | Una descrizione dettagliata non è obbligatoria, ma è consigliata. |
| Fuso orario | Scegli il fuso orario in cui dovranno essere presentati i dati. |
| Tag | I tag ti consentono di organizzare le visualizzazioni dati in categorie. |
| Contenitori | Puoi rinominare i contenitori qui ed ecco come appariranno in qualsiasi progetto Workspace basato su questa visualizzazione dati. I contenitori vengono utilizzati nei filtri e nell’abbandono/flusso per definire l’ampiezza o la restringenza dell’ambito o del contesto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| Il nome del contenitore della persona è... | Persona (predefinito). Il contenitore Persona include ogni visita e visualizzazione di pagina dei visitatori entro un intervallo di tempo specificato. È possibile rinominarlo &quot;Utente&quot; o qualsiasi altro termine preferito. |
| Il nome del contenitore della sessione è... | Sessione (impostazione predefinita). Il contenitore Sessione consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Puoi rinominarlo in &quot;Visita&quot; o in qualsiasi altro termine preferito. |
| Il nome del contenitore dell&#39;evento è... | Evento (predefinito). Il contenitore Evento definisce gli eventi di pagina da includere o escludere da un filtro. |

Successivamente, creerai metriche e dimensioni dagli elementi dello schema.

## Creare metriche e dimensioni dagli elementi dello schema

1. In [!UICONTROL Customer Journey Aalytics] > [!UICONTROL Data Views], fai clic sulla scheda [!UICONTROL Components] .

![](assets/components-tab.png)

Puoi vedere il [!UICONTROL Connection] in alto a sinistra, che contiene i set di dati, e il relativo [!UICONTROL Schema fields] qui sotto.

1. Ora trascina un campo schema, ad esempio [!UICONTROL pageTitle], dalla barra a sinistra nella sezione Metriche o Dimension .

   Puoi trascinare lo stesso campo schema ben più volte nelle dimensioni o metriche e configurare la stessa dimensione o metrica in modi diversi. Ad esempio, dal campo **[!UICONTROL pageTitle]** puoi creare una dimensione denominata &quot;Pagine di prodotto&quot; e un’altra denominata &quot;Pagine di errore&quot;, ecc. dal **[!UICONTROL pageTitle]**; Puoi anche creare metriche da un valore stringa. Ad esempio, puoi creare una o più metriche **[!UICONTROL Orders]** con diverse impostazioni di attribuzione e diversi valori di inclusione/esclusione.

   ![](assets/components-tab-3.png)

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
| Path | Obbligatorio. Un campo non modificabile che mostra il percorso dello schema da cui proviene il componente. |
| Nascondi componente nel reporting | Predefinito = disattivato. Consente di eliminare il componente dalla visualizzazione dati quando utilizzato nel rapporto. Questo non influisce sulle autorizzazioni, ma solo sulla cura dei componenti. In altre parole, puoi nascondere il componente da non amministratori nel reporting. Gli amministratori possono comunque accedervi facendo clic su [!UICONTROL Show All Components] in un progetto Analysis Workspace. |

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
| [!UICONTROL Case sensitive] | Predefinito = attivato. Questa impostazione è leggermente diversa per Dimension e metriche.<ul><li>**Metrica**: Questa impostazione si applica solo alla  [!UICONTROL Include/Exclude Values] sezione . Consente di specificare se il filtro applicato deve fare distinzione tra maiuscole e minuscole.</li><li>**Dimension** : Questa impostazione determina se i dati in questa dimensione devono essere aggregati in modo sensibile a maiuscole e minuscole o senza distinzione tra maiuscole e minuscole. Questo cambia il modo in cui vengono eseguiti i report/filtri/impostazioni di attribuzione per un campo stringa.</li></ul> |
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

Importante: Quando si modifica questo campo in un valore personalizzato, il valore personalizzato viene considerato come un valore di stringa legittimo. Pertanto, se si immette il valore &quot;Rosso&quot; in questo campo, anche tutte le istanze della stringa &quot;Rosso&quot; che compaiono nei dati stessi verranno riportate sotto la stessa riga specificata.

Inoltre, qualsiasi cosa specifichi in questo campo può essere utilizzata per un trattamento speciale dell’interfaccia utente della riga &quot;No Value&quot; nel reporting, come indicato nell’impostazione &quot;No Value Options&quot; (Nessuna opzione valore). (Non so cosa significhi.)

![](assets/no-value-options.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| Se mostrato, chiama [!UICONTROL No value].. | In questo punto è possibile rinominare **[!UICONTROL No value]** in un altro elemento. |
| Non mostrare **[!UICONTROL No value]** per impostazione predefinita | Questo valore non viene visualizzato nel rapporto. |
| Mostra **[!UICONTROL No value]** per impostazione predefinita | Mostra questo valore nel rapporto. |
| Considera **[!UICONTROL No value]** come un valore | Ad esempio, se la dimensione include tipi di dispositivi mobili, puoi rinominare l’elemento **[!UICONTROL No value]** in &quot;Desktop&quot;. |

### Configurare le impostazioni di persistenza

![](assets/persistence.png)

Queste impostazioni sono simili alle impostazioni eVar nella versione tradizionale di Adobe Analytics.

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| Impostare la persistenza | Tasto di attivazione/disattivazione |
| Allocazione | Consente di specificare il modello di allocazione utilizzato su una dimensione per la persistenza. Le opzioni sono: Più recente, Originale, Istanza, Tutto. Se desideri che un valore persista (simile alle eVar nella versione tradizionale di Analytics), questo è il punto in cui lo imposteresti. L’unica differenza chiave è che la persistenza massima impostabile è 90 giorni. Inoltre, [!UICONTROL Never expire] non è un’opzione. |
| Scadenza | Consente di specificare la finestra di persistenza per una dimensione. Le opzioni sono: Sessione (predefinita), Persona, Ora, Metrica. Potrebbe essere necessario essere in grado di scadere la dimensione su un acquisto (come termini di ricerca interni o altri casi di utilizzo di merchandising). &quot;Metrica&quot; consente di specificare una delle metriche definite come scadenza per questa dimensione (ad esempio, una metrica &quot;Acquisto&quot;). |

### Configurare le impostazioni di bucket dei valori

![](assets/value-bucketing.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| Valore fisso | Consente di creare una versione a blocchi di una dimensione numerica. Questo ti consente di creare rapporti su blocchi di ricavi o altri valori numerici come una dimensione nel reporting. Puoi creare fino a 5 blocchi. |
| Fino a | Consente di specificare i bordi del primo bucket dimensione numerica. Questo vale solo per le dimensioni numeriche. |
| Tra e fino a | Consente di specificare i bordi dei bucket di dimensione numerica successivi. |
| Aggiungi bucket | Consente di aggiungere un altro bucket alla creazione a blocchi di dimensioni numeriche. |

## Utilizzare i componenti Standard

Oltre a creare metriche e dimensioni da elementi dello schema, puoi utilizzare componenti standard anche nelle visualizzazioni dati.

I componenti standard sono componenti non generati dai campi dello schema del set di dati, ma generati dal sistema. Alcuni componenti di sistema sono necessari in qualsiasi visualizzazione dati per facilitare le funzionalità di reporting in Analysis Workspace, mentre altri componenti di sistema sono facoltativi.

![](RackMultipart20210326-4-374d6q_html_1100d8d54f8c09ac.png)

Componenti standard richiesti

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| Persone | Metrica | Precedentemente noto come [!UICONTROL Unique Visitors] nel tradizionale Analytics. Questa metrica si basa sull’ID persona specificato in una connessione. |
| Sessions | Metrica | Precedentemente noto come [!UICONTROL Visits] nel tradizionale Analytics. Questa metrica si basa sulle impostazioni di sessionizzazione specificate di seguito. |
| Eventi | Metrica | Precedentemente noto come [!UICONTROL Occurrences] nel tradizionale Analytics. Questa metrica rappresenta il numero di righe di tutti i set di dati evento in una connessione. |
| Giorno | Dimensione |  |
| Settimana | Dimensione |  |
| Mese | Dimensione |  |
| Trimestre | Dimensione |  |
| Anno | Dimensione |  |
| Ora | Dimensione |  |
| Minuto | Dimensione |  |

## Componenti standard opzionali

In qualsiasi visualizzazione dati sono necessari alcuni componenti di sistema per facilitare le funzionalità di reporting in Analysis Workspace, mentre quelli riportati di seguito sono facoltativi.

| Nome componente | Dimension o metrica | Note |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metrica | Questa metrica conta il numero di eventi che sono stati il primo evento di una sessione. Utilizzato in una definizione di filtro (ad esempio &#39;[!UICONTROL Session Starts] exists&#39;), filtra fino al primo evento di ogni sessione. Questo è un comportamento diverso da [!UICONTROL Entries] in quanto conta sempre il primo evento di una sessione - non il primo valore presente per una dimensione in una sessione. |
| [!UICONTROL Session Ends] | Metrica | Questa metrica conta il numero di eventi che sono stati l’ultimo evento di una sessione. Simile a [!UICONTROL Session Starts], può anche essere utilizzato in una definizione di filtro per filtrare gli elementi fino all&#39;ultimo evento di ogni sessione. Questo è un comportamento diverso da [!UICONTROL Exits] in quanto conta sempre l’ultimo evento di una sessione - non l’ultimo valore presente per una dimensione in una sessione. |
| [!UICONTROL Time Spent (seconds)] | Metrica | La metrica [!UICONTROL Time Spent] funziona in modo simile alla metrica tradizionale Adobe Analytics: il tempo tra due valori diversi per una dimensione viene calcolato sommando al tempo stesso due valori diversi. Tuttavia, utilizzando la metrica Avvio sessione e Fine sessione, i clienti possono creare autonomamente le metriche calcolate [!UICONTROL Time Spent per Person] e [!UICONTROL Time Spent per Session] (consulta i filtri OOTB e le metriche di calcolo di seguito). |
| [!UICONTROL Time Spent per Event] | Dimensione | Dal punto di vista funzionale, si tratta solo di un allungamento della metrica di cui sopra. Forniamo i bucket predefiniti, ma ti permettono di cambiare i secchi in qualsiasi cosa ti piaccia. |
| Tempo trascorso per sessione | Dimensione |  |
| Tempo trascorso per persona | Dimensione |  |
| ID batch | Dimensione |  |
| ID set di dati | Dimensione |  |
