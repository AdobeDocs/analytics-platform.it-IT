---
title: Gestione dell’assenza di valore nei rapporti di Customer Journey Analytics
description: Scopri quando **[!UICONTROL Nessun valore]** voci nei report di Customer Journey Analytics sono previste e quando segnalano un problema di raccolta dati che richiede attenzione.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: bc1e610ccf13ca831f40b2819a4665fe8ea21b7b
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 0%
---

# Come gestire Nessun valore

Quando si lavora con Customer Journey Analytics, la presenza di **[!UICONTROL voci Nessun valore]** nei report e nei dashboard solleva importanti domande sulla qualità dei dati, sui metodi di raccolta e sulla precisione dei report. Queste istanze devono essere monitorate attentamente, in quanto rivelano lacune nascoste nella raccolta dei dati. La sfida consiste nel distinguere tra due scenari: quando **[!UICONTROL Nessun valore]** voci necessitano di indagini da parte dei provider di origini dati e quando **[!UICONTROL Nessun valore]** voci riflettono il flusso naturale dei dati in Customer Journey Analytics. Comprendere questa distinzione è fondamentale per mantenere operazioni di analisi efficienti. Questa guida ti aiuta a prendere decisioni informate su **[!UICONTROL Nessun valore]** che compare nell&#39;implementazione di Customer Journey Analytics.

## Nessun valore

**[!UICONTROL Nessun valore]** viene visualizzato quando una dimensione non ha un valore corrispondente per un evento che altrimenti contiene una metrica. Vedere **[!UICONTROL Nessun valore]** in un report non è sempre un problema. In molti casi riflette la struttura prevista del set di dati.

Gli elementi di Dimension rientrano in una delle tre categorie seguenti:

* **Previsto [!UICONTROL Nessun valore]**: risultato naturale del modo in cui gli utenti si spostano nei tuoi dati, ad esempio visitatori che non hanno ancora effettuato l&#39;accesso o dimensioni che non si applicano a ogni evento
* **Problema [!UICONTROL Nessun valore]**: risultato di una raccolta dati non riuscita o di un errore di implementazione, dove esiste un valore mancante
* **Valore valido**: la dimensione ha acquisito un valore

Il diagramma seguente mostra come Customer Journey Analytics arriva a ciascuna di queste categorie durante lo spostamento dei dati dall’origine a Adobe Experience Platform.

Il diagramma di flusso illustra il modo in cui le valutazioni Customer Journey Analytics si concentrano sui dati in arrivo verificando innanzitutto la presenza di valori, quindi determinando se i valori mancanti sono previsti o problematici. Questa chiara valutazione consente agli amministratori e agli analisti di distinguere tra **[!UICONTROL Nessun valore]** casi che richiedono un&#39;indagine di origine e quelli che rappresentano le normali operazioni.

![Flusso decisionale che mostra i dati di origine che si spostano attraverso Adobe Experience Platform in Customer Journey Analytics, che controlla se è presente un valore di dimensione, quindi se un valore mancante è uno scenario previsto, con conseguente valore naturale No, problema No o valore valido](assets/no-value-flow.svg)

## Quando non è previsto alcun valore

Di seguito sono riportati i motivi comuni e previsti per la visualizzazione di **[!UICONTROL Nessun valore]** in un report:

* Una dimensione si applica solo a scenari specifici, ad esempio origine del traffico o tipo di dispositivo
* A un nuovo visitatore non è ancora stato assegnato un identificatore
* Un visitatore si trova in uno stato di pre-accesso e non ha fornito informazioni utente
* Una funzione o interazione con un prodotto non si applica a un particolare percorso di utenti
* Uno scenario multi-dispositivo non porta valori di dimensione tra dispositivi

In questi casi, **[!UICONTROL Nessun valore]** indica dove si trova un utente nel percorso di autenticazione, durante la transizione da uno stato non identificato a uno identificato, come illustrato di seguito.

![Il percorso di autenticazione utente visualizza un utente che visita il sito e immette uno stato di pre-accesso senza informazioni utente disponibili, quindi un evento di accesso che popola le informazioni dell&#39;utente](assets/no-value-login-flow.svg)


## Quando Nessun valore richiede attenzione

Esaminare **[!UICONTROL Nessuna voce di valore]** quando derivano da uno dei seguenti elementi:

**Problemi di implementazione nell&#39;origine dati:**

* Elementi dati mancanti o valori Null
* Mappatura variabile errata
* Un livello dati configurato in modo errato
* Raccolta dati non riuscita
* Mancata corrispondenza tra dati in arrivo e schema definito

**Problemi relativi alla qualità dei dati:**

* Codice di tracciamento interrotto
* Raccolta dati incompleta
* Errori di integrazione
* Errori introdotti durante la trasformazione dei dati
* Interruzioni nella pipeline dei dati

## Gestisci Nessun valore nelle impostazioni della visualizzazione dati

Le impostazioni della visualizzazione dati consentono di controllare la modalità di visualizzazione di **[!UICONTROL Nessun valore]** elementi nei report, inclusa la ridenominazione dell&#39;etichetta, la visualizzazione o la visualizzazione degli elementi per impostazione predefinita e il trattamento di **[!UICONTROL Nessun valore]** come valore stringa legittimo. Per l&#39;elenco completo delle impostazioni e per informazioni su come influiscono su distribuzioni percentuali, filtri e segmentazione, vedere [Impostazioni dei componenti delle opzioni per i valori](/help/data-views/component-settings/no-value-options.md).

Durante la configurazione di queste impostazioni, valuta i requisiti di reporting e il modo in cui la presenza di **[!UICONTROL Nessun valore]** influisce sull&#39;analisi. Considera sia gli effetti immediati sulla visibilità dei dati che gli impatti a lungo termine sull’analisi delle tendenze e sulla coerenza dei rapporti. Configurazioni ben scelte migliorano la chiarezza dei dati mantenendo le informazioni aziendali accessibili e utilizzabili, indipendentemente da come **[!UICONTROL Nessun valore]** viene visualizzato nei rapporti. La configurazione ideale bilancia la rappresentazione dei dati con le esigenze analitiche pratiche, creando un ambiente di reporting che fornisce informazioni accurate e significative anche quando sono presenti dati **[!UICONTROL Nessun valore]**.

Nella tabella seguente sono riepilogate le varie configurazioni disponibili.

<table>
<thead>
<tr>
<th>Categoria</th>
<th>Impostazione</th>
<th>Funzionamento</th>
<th>Impatto</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="2">Mostra opzioni</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Può essere incluso o escluso tramite la selezione di caselle di controllo all’interno del filtro di ricerca della tabella a forma libera.</td>
<td rowspan="2">Visibilità</td>
</tr>
<tr>
<td><img src="assets/dont-show-no-value-default.png"/></td>
</tr>
<tr>
<td rowspan="2">Denominazione personalizzata</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Influisce sulla visualizzazione del valore della dimensione di reporting e potenzialmente sul consolidamento del valore e sull’aggregazione delle metriche.</td>
<td rowspan="2">Denominazione</td>
</tr>
<tr>
<td><img src="assets/show-unknown-as-value.png"/></td>
</tr>
<tr>
<td rowspan="3">Opzioni di trattamento</td>
<td><img src="assets/treat-no-value-as-value.png"/></td>
<td>Si applica solo a dimensioni non numeriche.
Ha effetto sia sull’attribuzione che sull’opzione include **[!UICONTROL Nessun valore]** nel filtro di ricerca di tabelle a forma libera.</td>
<td>Gestione del valore e visibilità</td>
</tr>
<tr>
<td rowspan="2">Supporto dimensioni numeriche:<br><img src="assets/dont-show-no-value-default.png"/><br/><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Può essere incluso o escluso tramite la selezione di caselle di controllo nel filtro di ricerca della tabella a forma libera</td>
<td rowspan="2">Visibilità</td>
</tr>
<tr>
</tr>
</tbody>
</table>


### Se mostrato, chiama &quot;No value&quot;

Questa impostazione consente di personalizzare la modalità di visualizzazione delle righe **[!UICONTROL Nessun valore]** nei report. Puoi immettere un nome personalizzato per l&#39;elemento dimensione **[!UICONTROL Nessun valore]** nel campo di testo, fornendo un contesto più significativo tramite **[!UICONTROL Se mostrato, chiama &quot;Nessun valore&quot;]**. L&#39;utilizzo di termini chiari e intuitivi invece di `No value` consente all&#39;organizzazione di comprendere meglio i valori dei rapporti. Anche se non è possibile utilizzare **[!UICONTROL Nessun valore]** direttamente come stringa nei segmenti, è possibile ottenere lo stesso effetto utilizzando l&#39;operatore **[!UICONTROL does not exist]**.

È possibile sostituire `No value` con termini descrittivi come `Pre-login User` per lo stato di autenticazione, `No Customer Tier` per i clienti senza livelli o `No Tracked Marketing Channel` per origini di marketing non identificate. Questo consente di creare rapporti più intuitivi. `Pre-login User` mostra chiaramente dove si trova un cliente nel suo percorso, mentre `No Customer Tier` fornisce un contesto specifico. Ricorda che la descrizione scelta si applica a tutte le **[!UICONTROL istanze No value]** per quella dimensione, quindi seleziona termini che riflettano accuratamente tutti gli scenari in cui i valori di dimensione sono assenti.

### Non mostrare alcun valore per impostazione predefinita

Questa impostazione determina se nascondere **[!UICONTROL Nessun valore]** righe per impostazione predefinita nei rapporti. Quando sono abilitate, queste righe vengono inizialmente escluse ma possono comunque essere visualizzate all’interno di una tabella a forma libera, se necessario, selezionando la casella di controllo all’interno del filtro di ricerca della tabella a forma libera. Tenere presente che nascondere **[!UICONTROL Nessuna riga di valore]** influisce sulla distribuzione percentuale dei valori rimanenti, poiché le percentuali vengono ricalcolate solo in base agli elementi visibili.

### Non mostrare alcun valore per impostazione predefinita

Questa impostazione controlla se **[!UICONTROL Nessun valore]** viene visualizzato per impostazione predefinita nei report. Quando questa opzione è attivata, le voci **[!UICONTROL Nessun valore]** sono visibili, anche se gli utenti possono escluderle utilizzando la casella di controllo nel filtro di ricerca delle tabelle a forma libera. L&#39;inclusione o l&#39;esclusione di **[!UICONTROL Nessuna riga valore]** influisce sulle distribuzioni percentuali, in quanto le percentuali vengono calcolate solo in base agli elementi visibili.

### Considera nessun valore come valore

Questa impostazione tratta **[!UICONTROL Nessun valore]** come valore stringa (ad eccezione delle dimensioni numeriche), consentendo di personalizzarne la rappresentazione come valore di dimensione. Questa personalizzazione influisce sia sull&#39;attribuzione che sull&#39;opzione **[!UICONTROL Includi nessun valore]** nel filtro di ricerca delle tabelle a forma libera. Tieni presente che quando assegni un valore di stringa personalizzato, tutti i valori corrispondenti nel set di dati vengono consolidati sotto lo stesso valore di stringa della dimensione.

L&#39;impostazione **[!UICONTROL Considera &quot;Nessun valore&quot; come valore]** ha uno scopo diverso rispetto alla visualizzazione di **[!UICONTROL Nessun valore]** per impostazione predefinita. Se la visualizzazione per impostazione predefinita controlla solo la visibilità, il trattamento come valore cambia il modo in cui Customer Journey Analytics gestisce logicamente queste voci. Ecco perché questa distinzione conta:

* Consente un controllo più granulare nel filtraggio e nella segmentazione, rendendo **[!UICONTROL Nessun valore]** un valore di dimensione distinto e actionable.
* Mantiene l&#39;attribuzione e la rappresentazione coerenti in tutta l&#39;analisi trattando **[!UICONTROL Nessun valore]** come valore di dimensione legittimo sia nei modelli di attribuzione che nelle visualizzazioni.

Considera **[!UICONTROL Nessun valore]** come valore quando:

* L’assenza di dati di per sé è significativa per l’analisi (ad esempio, stati di pre-accesso o traffico non attribuito).
* Devi creare segmenti o metriche calcolate che eseguano il targeting o escludano specificamente questi casi.

Per contro, la visualizzazione di **[!UICONTROL Nessun valore]** per impostazione predefinita è più adatta quando è necessaria la visibilità di base dei dati mancanti senza la complessità della logica e dell&#39;attribuzione aggiuntive associate al loro trattamento come valori.

### Nessun valore supportato per le dimensioni numeriche

Per le dimensioni numeriche sono disponibili diverse opzioni di configurazione. Nelle impostazioni delle dimensioni della visualizzazione dati è possibile configurare tutte le opzioni **[!UICONTROL Nessun valore]** eccetto **[!UICONTROL Considera &quot;Nessun valore&quot; come valore]**. Puoi anche gestire **[!UICONTROL Includere &quot;Nessun valore&quot;]** per le dimensioni numeriche selezionando la casella di controllo all&#39;interno del filtro di ricerca della tabella a forma libera. Durante la creazione di segmenti, puoi utilizzare gli operatori **[!UICONTROL exists]** o **[!UICONTROL does not exist]** con dimensioni numeriche.

### Nessuna dimensione a livello di valore e di elemento

Alcune dimensioni si applicano a livello di elemento all’interno di un array, anziché al livello principale di un evento. Ad esempio, `productListItems.SKU` ha un valore solo quando esiste un elemento dell&#39;elenco di prodotti per quell&#39;evento. Questa differenza nella granularità dei dati cambia il comportamento di **[!UICONTROL Nessun valore]**.

Per una dimensione standard di primo livello, Customer Journey Analytics può inserire una metrica in un bucket **[!UICONTROL Nessun valore]** ogni volta che tale dimensione risulta mancante o presenta un valore null in un evento che altrimenti contiene una metrica. Una dimensione a livello di elemento dipende dall’elemento esistente. Se un evento contiene una metrica ma mancano gli elementi dell&#39;elenco prodotti, Customer Journey Analytics non dispone di righe per allegare tale metrica o contrassegnare i dati come **[!UICONTROL Nessun valore]**.

Customer Journey Analytics non crea un segnaposto o una riga vuota per gli array vuoti o mancanti. Di conseguenza, puoi configurare correttamente le impostazioni di visualizzazione dati di **[!UICONTROL Nessun valore]** e continuare a non visualizzare **[!UICONTROL Nessun valore]** voci in un report a livello di elemento, ad esempio un raggruppamento SKU. Le voci mancanti corrispondono a una differenza di granularità dei dati e non a un problema di configurazione. **[!UICONTROL Nessuna impostazione di valore]** regola la visualizzazione delle righe esistenti e una matrice vuota indica che non esistono righe a tale livello di granularità dei dati.

Quando i conteggi **[!UICONTROL Nessun valore]** a livello di elemento sembrano inferiori al previsto, verificare se i dati dell&#39;array mancanti spiegano il gap prima di supporre che l&#39;impostazione della visualizzazione dati debba essere corretta.

## Best practice

Dopo aver identificato **[!UICONTROL istanze senza valore]** problematiche, è necessario sviluppare e implementare una strategia di correzione. Questa correzione può essere eseguita in due modi:

* Regolare le impostazioni delle opzioni del componente Visualizzazione dati **[!UICONTROL Nessun valore]** oppure
* Sono stati risolti dei problemi relativi all’origine di raccolta dati.

Scegli il tuo approccio con attenzione, in quanto ogni percorso ha implicazioni diverse sia per le correzioni rapide che per la qualità dei dati a lungo termine. L’implementazione segue un processo metodologico che corregge i problemi correnti ed evita quelli futuri. Il successo dipende dalla pianificazione, dall&#39;esecuzione sistematica e dal monitoraggio continuo.

Di seguito sono riportate le considerazioni strategiche chiave per il piano di correzione:

### Impedisci problemi di valore

* Convalidare i dati prima che vengano elaborati
* Imposta i valori di dimensione predefiniti laddove appropriato (mai per un ID persona)
* Documenta gli scenari in cui **[!UICONTROL Non è previsto alcun valore]**
* Aggiungere controlli di qualità al punto di raccolta dei dati
* Monitorare la conformità al modello dati
* Registra gli errori durante la raccolta dati
* Aggiungere test automatizzati per l’implementazione
* Richiedi campi schema in cui esiste sempre un valore

### Convalida nessun valore nei rapporti

* Crea segmenti che isolano **[!UICONTROL Nessun valore]** pattern
* Crea un dashboard di controllo qualità che monitori le tendenze di **[!UICONTROL Nessun valore]** nel tempo
* Imposta avvisi che tengono traccia delle modifiche nel volume **[!UICONTROL Nessun valore]**
* Genera report automatizzati che evidenziano le modifiche significative ai pattern
* **[!UICONTROL Nessun valore]** pattern tra dimensioni correlate
* Eseguire controlli regolari della configurazione della visualizzazione dati
* Gestisci un registro modifiche alla strategia **[!UICONTROL Nessun valore]**
* Creare procedure operative standard e modelli di documentazione per le parti interessate

## Conclusione

Non tutte le voci **[!UICONTROL Nessun valore]** segnalano un problema. Per interpretare correttamente **[!UICONTROL Nessun valore]** è necessario comprendere l&#39;architettura dei dati di Adobe Experience Platform e Customer Journey Analytics e il modo in cui gli utenti si spostano all&#39;interno del prodotto o del sito. Anziché tentare di eliminare ogni istanza di **[!UICONTROL Nessun valore]**, stabilire regole documentate a livello di organizzazione che distinguano il **[!UICONTROL Nessun valore]** previsto dal **[!UICONTROL Nessun valore]** problematico, basate sui propri percorsi di utenti e casi aziendali.

>[!MORELIKETHIS]
>
>[Playbook completo per la gestione di **[!UICONTROL Nessun valore]** in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/the-complete-playbook-for-handling-no-value-in-adobe-cja-12769?profile.language=it)
