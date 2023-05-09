---
title: Campi derivati
description: Un campo derivato specifica la manipolazione in fase di report dei campi dello schema e/o dei componenti standard tramite un set di funzioni e modelli di funzioni disponibili.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
badgeDerivedFields: label="New Feature" type="Positive"
source-git-commit: cb63cd52a1618f2e1048f2779c4e6c0317e94f64
workflow-type: tm+mt
source-wordcount: '2914'
ht-degree: 6%

---


# Campi derivati

{{release-limited-testing}}

>[!NOTE]
>
>Gli aggiornamenti finali in sospeso potrebbero essere visualizzati [!UICONTROL Custom field] anziché [!UICONTROL Derived field] nell’interfaccia utente.


I campi derivati sono un aspetto importante della funzionalità di reporting in tempo reale in Customer Journey Analytics (CJA). Un campo derivato ti consente di definire al volo (spesso complesse) le manipolazioni dei dati tramite un generatore di regole personalizzabile. Puoi quindi utilizzare tale campo derivato come componente (metrica o dimensione) in [Area di lavoro](../../analysis-workspace/home.md) o ancora definire ulteriormente il campo derivato come componente in [Visualizzazione dati](../data-views.md).

I campi derivati possono risparmiare molto tempo e fatica rispetto alla trasformazione o manipolazione dei dati in altre aree al di fuori di CJA. Ad esempio [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it), [Distiller dati](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)oppure all’interno dei propri processi di estrazione del carico di trasformazione (ETL) / estrazione della trasformazione del carico (ELT).

I campi derivati sono definiti in [Visualizzazioni dati](../data-views.md), si basano su un set di funzioni definite come regole e applicate ai campi standard e/o schema disponibili.

Esempi di casi di utilizzo:

- Definire un campo Nome pagina derivato che corregga i valori errati dei nomi di pagina raccolti per correggere i valori dei nomi di pagina.

- Definisci un campo del canale di marketing derivato che determina il canale di marketing appropriato in base a una o più condizioni (ad esempio, parametro URL, URL pagina, nome pagina).

## Interfaccia campo derivata

Quando si crea o si modifica un campo derivato, è possibile utilizzare l’interfaccia del campo derivato.

![Finestra di dialogo dei campi derivati](assets/derived-field-dialog.png)


|  | Nome | Descrizione |
|---------|----------|--------|
| 1 | **Selettore** | Utilizza l’area del selettore per selezionare, trascinare e rilasciare la ![Funzione](assets/Smock_Function_18_N.svg) funzione,![Icona del modello di funzione](assets/Smock_FileTemplate_18_N.svg) modello di funzione,![Icona del campo schema](assets/Smock_Folder_18_N.svg) campo schema, oppure![Icona del campo standard](assets/Smock_DragHandle_18_N.svg)campo standard nel generatore di regole. <br/>Utilizza il menu a discesa per selezionare tra [!UICONTROL Functions], [!UICONTROL Function templates], [!UICONTROL Schema fields]e [!UICONTROL Standard fields].<br/>È possibile cercare campi di funzioni, modelli di funzioni, schemi e standard utilizzando ![Icona Ricerca](assets/Smock_Search_18_N.svg) Casella di ricerca. <br/>È possibile filtrare l’elenco di oggetti selezionati selezionando ![Icona Filtro](assets/Smock_Filter_18_N.svg) Filtrare e specificare i filtri nel [!UICONTROL Filter fields by] finestra di dialogo. È possibile rimuovere facilmente i filtri utilizzando ![Icona Chiudi](assets/CrossSize75.svg) per ogni filtro. |
| 2 | **Generatore di regole** | Puoi creare il campo derivato in sequenza utilizzando una o più regole. Una regola è un&#39;implementazione specifica di una funzione ed è quindi sempre associata a una sola funzione. Puoi creare una regola trascinando e rilasciando una funzione nel generatore di regole. Il tipo di funzione determina l&#39;interfaccia della regola.<br/>Consulta la sezione [Interfaccia regola](#rule-interface) per ulteriori informazioni. <br/>È possibile inserire una funzione all&#39;inizio, alla fine o tra le regole già disponibili nel generatore di regole. L&#39;ultima regola nel generatore di regole determina l&#39;output finale del campo derivato. |
| 3 | **[!UICONTROL ** Impostazioni campo **]** | È possibile assegnare un nome e descrivere il campo derivato ed esaminarne il tipo di campo. |
| 4 | **[!UICONTROL ** Output finale **]** | In questa area viene visualizzata un’anteprima aggiornata al volo dei valori di output, basata sui dati degli ultimi 30 giorni e sulle modifiche apportate al campo derivato nel generatore di regole. |

{style="table-layout:auto"}

## Creazione guidata modello di campo

Quando si accede per la prima volta all&#39;interfaccia del campo derivato, la [!UICONTROL Start with a field template] viene visualizzata la procedura guidata.

1. Selezionare il modello che descrive meglio il tipo di campo che si sta tentando di creare.
2. Seleziona la **[!UICONTROL ** Seleziona **]** per continuare.

La finestra di dialogo del campo derivato viene compilata con regole (e funzioni) necessarie o utili per il tipo di campo selezionato. Vedi [Modelli di funzione](#function-templates) per ulteriori informazioni sui modelli disponibili.

## Interfaccia regola

Quando definisci una regola nel generatore di regole, utilizza l&#39;interfaccia della regola.

![Interfaccia regola](assets/rule-interface.png)

|  | Nome | Descrizione |
|---------|----------|--------|
| A | **Nome della regola** | Per impostazione predefinita, il nome della regola è **Regola X** (X che fa riferimento a un numero di sequenza). Per modificare il nome di una regola, selezionane il nome e digita il nuovo nome, ad esempio `Query Parameter`. |
| B | **Nome funzione** | Nome della funzione selezionata per la regola, ad esempio [!DNL URL PARSE]. Quando la funzione è l&#39;ultima nella sequenza di funzioni e determina i valori di output finali, il nome della funzione è seguito da [!DNL - FINAL OUTPUT], ad esempio [!DNL URL PARSE - FINAL OUTPUT]. <br/>Per visualizzare una finestra a comparsa con ulteriori informazioni sulla funzione, selezionare ![Icona Aiuto](assets/Smock_HelpOutline_18_N.svg). |
| C | **Descrizione regola** | Facoltativamente, puoi aggiungere una descrizione a una regola.<br/>Seleziona ![Icona Altro](assets/More.svg), quindi seleziona **[!UICONTROL ** Aggiungi descrizione **]** per aggiungere una descrizione o **[!UICONTROL ** Modifica descrizione **]** per modificare una descrizione esistente.<br/>Utilizza l’editor per inserire una descrizione. È possibile utilizzare la barra degli strumenti per formattare il testo (utilizzando il selettore di stile, grassetto, corsivo, sottolineato, destro, sinistro, centrato, colore, elenco numerato, elenco puntato) e aggiungere collegamenti a informazioni esterne. <br/>Per terminare la modifica della descrizione, fai clic all’esterno dell’editor. |
| D | **Area della funzione** | Definisce la logica della funzione. L’interfaccia dipende dal tipo di funzione. Vedi [Riferimento della funzione](#function-reference) informazioni dettagliate su ciascuna delle funzioni supportate. |

{style="table-layout:auto"}

## Creare un campo derivato

1. Selezionare una visualizzazione dati esistente o crearne una. Vedi [Visualizzazioni dati](../data-views.md) per ulteriori informazioni.

2. Seleziona la **[!UICONTROL ** Componenti **]** scheda della visualizzazione Dati.

3. Seleziona **[!UICONTROL ** Crea campo derivato **]** dalla barra a sinistra.

4. Per definire il campo derivato, utilizza il [!UICONTROL Create derived field] interfaccia. Vedi [Interfaccia campo derivata](#derived-field-interface).

   Per salvare il nuovo campo derivato, seleziona **[!UICONTROL ** Salva **]**.

5. Il nuovo campo derivato viene aggiunto al [!UICONTROL Derived fields >] come parte di **[!UICONTROL ** Campi dello schema **]** nella barra a sinistra della visualizzazione Dati.


## Modificare un campo derivato

1. Selezionare una visualizzazione dati esistente. Vedi [Visualizzazioni dati](../data-views.md) per ulteriori informazioni.

2. Seleziona la **[!UICONTROL ** Componenti **]** scheda della visualizzazione Dati.

3. Seleziona **[!UICONTROL ** Campi dello schema **]** nella scheda [!UICONTROL Connection] a sinistra.

4. Seleziona **[!UICONTROL ** Campi derivati >**]** contenitore.

5. Passa il puntatore del mouse sul campo derivato da modificare e seleziona ![Icona Modifica](assets/Smock_Edit_18_N.svg).

6. Per modificare il campo derivato, utilizza il [!UICONTROL Edit derived field] interfaccia. Vedi [Interfaccia campo derivata](#derived-field-interface).

   - Seleziona **[!UICONTROL ** Salva **]** per salvare il campo derivato aggiornato.

   - Seleziona **[!UICONTROL ** Annulla **]** per annullare eventuali modifiche apportate al campo derivato.

   - Seleziona **[!UICONTROL ** Salva con nome **]** per salvare il campo derivato come nuovo campo derivato. Il nuovo campo derivato ha lo stesso nome del campo derivato modificato originale con `(copy)` aggiunto.

## Eliminare un campo derivato

1. Selezionare una visualizzazione dati esistente. Vedi [Visualizzazioni dati](../data-views.md) per ulteriori informazioni.

2. Seleziona la **[!UICONTROL ** Componenti **]** scheda della visualizzazione Dati.

3. Seleziona **[!UICONTROL ** Campi dello schema **]** scheda in [!UICONTROL Connection] riquadro.

4. Seleziona **[!UICONTROL ** Campi derivati >**]** contenitore.

5. Passa il puntatore del mouse sul campo derivato che desideri eliminare e seleziona ![Icona Modifica](assets/Smock_Edit_18_N.svg).

6. Nell’uso **[!UICONTROL ** Modifica campo derivato **]** , selezionare Elimina.

   A [!UICONTROL Delete component] viene richiesto di confermare l’eliminazione. Considera eventuali riferimenti esterni al campo derivato al di fuori della visualizzazione Dati.

   - Seleziona **[!UICONTROL ** Continua **]** per eliminare il campo derivato.


## Modelli di funzione

Per creare rapidamente un campo derivato per casi d’uso specifici, sono disponibili modelli di funzione. Questi modelli di funzioni sono accessibili dall’area del selettore nell’interfaccia del campo derivato o sono presentati al primo utilizzo nel [!UICONTROL Start with a field template] procedura guidata.


### Canali di marketing

Questo modello è configurato per utilizzare il [Analisi Url](#dnl-url-parse) e [Case quando](#dnl-case-when) funziona più volte per ottenere i valori appropriati da un URL. A questi valori viene quindi applicata la logica per associare l’URL a un canale di marketing specifico.

+++ Dettagli

Per utilizzare il modello, è necessario specificare i parametri corretti per ogni funzione elencata come parte delle regole nel modello. Vedi [Riferimento della funzione](#function-reference) per ulteriori informazioni.

![Generatore di regole per i modelli di canale di marketing](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Riferimento della funzione

Per ogni funzione supportata, trova i dettagli seguenti su:

- specifiche:
   - tipo di dati di input: tipo di dati supportati,
   - input: possibili valori di input,
   - operatori inclusi: gli operatori supportati per questa funzione (se presenti),
   - limite: numero massimo di regole (con questa funzione) utilizzabili in un campo derivato,
   - output.

- casi d’uso, compresi:
   - dati prima di definire il campo derivato,
   - come definire il campo derivato,
   - dopo aver definito il campo derivato.

- eventuali vincoli.


<!-- Concatenate -->

### [!DNL Concatenate]

Combina due o più campi, campi derivati o valori immessi dall’utente in un singolo campo con delimitatori definiti.

+++ Dettagli

## Specifiche {#concatenate-io}

| Tipo di dati di input | Ingresso | Operatori inclusi | Limite | Output |
|---|---|---|:--:|---|
| <p>Stringa</p> | <ul><li>Due o più valori da combinare<ul><li>Campi</li><li>Valore derivato da una regola precedente</li><li>Valore immesso dall’utente</li></ul></li><li>Delimitatori<ul><li>Input o selezione di un delimitatore per ciascun valore</li></ul></li> </ul> | <p>N/D</p> | <p>2</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d’uso {#concatenate-uc}

Attualmente si raccolgono i codici dell&#39;aeroporto di origine e di destinazione come campi separati. Prendi i due campi e combinali in una singola dimensione separata da un trattino (-). Così puoi analizzare la combinazione di origine e destinazione per identificare i percorsi principali prenotati.

Ipotesi:

- I valori di origine e destinazione vengono raccolti in campi separati nella stessa tabella.
- L’utente determina l’utilizzo del delimitatore &quot;-&quot; tra i valori.

Immagina che si verifichino le seguenti prenotazioni:

- Il cliente ABC123 prenota un volo tra Salt Lake City (SLC) e Orlando (MCO)
- Il cliente ABC456 prenota un volo tra Salt Lake City (SLC) e Los Angeles (LAX)
- Il cliente ABC789 prenota un volo tra Salt Lake City (SLC) e Seattle (SEA)
- Il cliente ABC987 prenota un volo tra Salt Lake City (SLC) e San Jose (SJO)
- Il cliente ABC654 prenota un volo tra Salt Lake City (SLC) e Orlando (MCO)

Il rapporto desiderato si presenta così:

| Origine / Destinazione | Prenotazioni |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| MARE SLC | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Dati precedenti {#concatenate-uc-databefore}

| Origin | Destinazione |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | MARE |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Campo derivato {#concatenate-derivedfield}

Definisci un nuovo [!UICONTROL Origin - Destination] campo derivato. Utilizzi le [!UICONTROL CONCATENATE] per definire una regola per concatenare il [!UICONTROL Original] e [!UICONTROL Destination] campi che utilizzano `-` [!UICONTROL Delimiter].

![[!DNL Concatenate] regola](assets/concatenate.png)

### Dati dopo {#concatenate-dataafter}

| Origine - Destinazione<br/>(campo derivato) |
|---|
| SLC-MCO |
| SLC-LAX |
| MARE SLC |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

Applica le condizionali in base a criteri definiti da uno o più campi. Questi criteri vengono quindi utilizzati per definire i valori in un nuovo campo derivato, in base alla sequenza delle condizioni.

+++ Dettagli

## Specifiche {#casewhen-io}

| Tipo di dati di input | Ingresso | Operatori inclusi | Limite | Output |
|---|---|---|:---:|---|
| <ul><li>Stringa</li><li>Numeriche</li><li>Data/Ora</li></ul> | <ul><li>Campi di input</li><li>Criteri</li></ul> | <p><u>Stringhe</u></p><ul><li>È uguale a</li><li>Uguale a qualsiasi termine</li><li>Contiene la frase</li><li>Contiene qualsiasi termine</li><li>Contiene tutti i termini</li><li>Inizia con</li><li>Inizia con qualsiasi termine</li><li>Termina con</li><li>Termina con qualsiasi termine</li><li>È diverso da</li><li>Non è uguale a nessun termine</li><li>Non contiene la frase</li><li>Non contiene alcun termine</li><li>Non contiene tutti i termini</li><li>Non inizia con</li><li>Non inizia con alcun termine</li><li>Non termina con</li><li>Non termina con alcun termine</li><li>È impostato</li><li>Non impostato</li></ul><p><u>Numeriche</u></p><ul><li>È uguale a</li><li>È diverso da</li><li>È maggiore di</li><li>È maggiore o uguale a</li><li>È minore di</li><li>È minore o uguale a</li><li>È impostato</li><li>Non impostato</li></ul><p><u>Date</u></p><ul><li>È uguale a</li><li>È diverso da</li><li>È successivo a</li><li>È successivo o uguale a</li><li>È prima di</li><li>È precedente o uguale a</li><li>È impostato</li><li>Non impostato</li></ul> | <p>5</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d&#39;uso 1 {#casewhen-uc1}

Desideri definire regole per identificare vari canali di marketing applicando una logica a cascata per impostare un campo del canale di marketing sul valore corretto:

- Se il referente proviene da un motore di ricerca e la pagina dispone di un valore della stringa di query in cui `cid` contiene `ps_`, il canale di commercializzazione deve essere identificato come [!DNL *Ricerca a pagamento*].
- Se il referente proviene da un motore di ricerca e la pagina non dispone della stringa di query `cid`, il canale di commercializzazione deve essere identificato come [!DNL *Ricerca naturale*].
- Se una pagina dispone di un valore di stringa di query in cui `cid` contiene `em_`, il canale di marketing deve essere identificato come [!DNL *E-mail*].
- Se una pagina dispone di un valore di stringa di query in cui `cid` contiene `ds_`, il canale di commercializzazione deve essere identificato come [!DNL *Annuncio visualizzato*].
- Se una pagina dispone di un valore di stringa di query in cui `cid` contiene `so_`, il canale di commercializzazione deve essere identificato come [!DNL *Social a pagamento*].
- Se il referente proviene da un dominio di riferimento di [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]oppure [!DNL tiktok.com], il canale di commercializzazione deve essere identificato come [!DNL *Social naturale*].
- Se nessuna delle regole di cui sopra corrisponde, il canale di marketing deve essere identificato come [!DNL *Altro referente*].

Nel caso in cui il sito riceva i seguenti eventi di esempio, contenenti [!UICONTROL Referrer] e [!UICONTROL Page URL], tali eventi devono essere identificati come segue:

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 |  | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### Dati precedenti {#casewhen-uc1-databefore}

| [!UICONTROL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### Campo derivato {#casewhen-uc1-derivedfield}

Definisci un nuovo `Marketing Channel` campo derivato. Utilizzi le [!UICONTROL CASE WHEN] per definire regole che creano valori per in base ai valori esistenti per entrambi i tipi di `Page URL` e `Referring URL` campo .

Nota l&#39;utilizzo della funzione [!UICONTROL URL PARSE] per definire regole per recuperare i valori `Page Url` e `Referring Url` prima del [!UICONTROL CASE WHEN] vengono applicate le regole.

![[!DNL Case when] regola 1](assets/case-when-1.png)

### Dati dopo {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## Caso d&#39;uso 2 {#casewhen-uc2}

Hai raccolto diverse varianti di ricerca all’interno del tuo [!DNL Product Finding Methods] dimensione. Per comprendere le prestazioni complessive della ricerca rispetto alla navigazione, è necessario dedicare molto tempo combinando manualmente i risultati.

Il sito raccoglie i seguenti valori per [!DNL Product Finding Methods] dimensione. Alla fine, tutti questi valori indicano una ricerca.

| Valore raccolto | Valore effettivo |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes ] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### Dati precedenti {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### Campo derivato {#casewhen-uc2-derivedfield}

Definisci un `Product Finding Methods (new)` campo derivato. Crea quanto segue [!UICONTROL CASE WHEN] regole nel generatore di regole. Queste regole applicano la logica a tutte le possibili varianti della [!UICONTROL Product Finding Methods] valori dei campi per `search` e `browse` utilizzando [!UICONTROL Contains the phrase] criterio.

![[!DNL Case When] regola 2](assets/case-when-2.png)

### Dati dopo {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## Caso d&#39;uso 3 {#casewhen-uc3}

In qualità di società di viaggi, ti piacerebbe prenotare la durata del viaggio per i viaggi prenotati in modo da poter segnalare su lunghezze intasate di viaggi.

Ipotesi:

- L&#39;organizzazione sta raccogliendo la durata del viaggio in un campo numerico.
- Vorrebbero impennare 1-3 giorni di durata in un secchio chiamato &#39;[!DNL short trip]&#39;
- Vorrebbero impennare le durate 4-7 giorni in un secchio chiamato &#39;[!DNL medium trip]&#39;
- Vorrebbero impennare 8 durate più giorni in un secchio chiamato &#39;[!DNL long trip]&#39;
- 132 viaggi sono stati prenotati per una durata di 1 giorno
- 110 viaggi sono stati prenotati per una durata di 2 giorni
- 105 viaggi sono stati prenotati per una durata di 3 giorni
- 99 viaggi sono stati prenotati per una durata di 4 giorni
- 92 viaggi sono stati prenotati per una durata di 5 giorni
- Sono stati prenotati 85 viaggi per una durata di 6 giorni
- 82 viaggi sono stati prenotati per una durata di 7 giorni
- Sono stati prenotati 78 viaggi per una durata di 8 giorni
- 50 viaggi sono stati prenotati per una durata di 9 giorni
- 44 viaggi sono stati prenotati per una durata di 10 giorni
- 38 viaggi sono stati prenotati per una durata di 11 giorni
- 31 viaggi sono stati prenotati per una durata di 12 giorni

Il rapporto desiderato dovrebbe essere simile al seguente:

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### Dati precedenti {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### Campo derivato {#casewhen-uc3-derivedfield}

Definisci un `Trip Duration (bucketed)` campo derivato. Crea quanto segue [!UICONTROL CASE WHEN] nel generatore di regole. Questa regola applica la logica al bucket precedente [!UICONTROL Trip Duration] valori dei campi in tre valori: `short trip`, `medium  trip`e `long trip`.

![[!DNL Case When] regola 3](assets/case-when-3.png)


### Dati dopo {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## Vincoli

CJA utilizza una struttura di contenitori nidificati, modellata dopo l’Adobe Experience Platform di [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) (Experience Data Model). Vedi [Contenitori](../create-dataview.md#containers) e [Contenitori di filtri](../../components/filters/filters-overview.md#filter-containers) per ulteriori informazioni di base. Questo modello di contenitore, anche se flessibile per natura, impone alcuni vincoli quando si utilizza il generatore di regole.

CJA utilizza il seguente modello di contenitore predefinito:

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>



I seguenti vincoli si applicano e vengono applicati quando *selezione* e *impostazione* valori.

|  | Vincoli |
|:---:|----|
| **<span style='color: red'>A</span>** | Valori *select* all&#39;interno dello stesso [!UICONTROL If], [!UICONTROL Else If] costrutto (utilizzando [!UICONTROL And] o [!UICONTROL Or]) in una regola deve provenire dallo stesso contenitore e può essere di qualsiasi tipo (stringa ![Stringa](assets/Smock_ABC_18_N.svg), numerico ![Numerico](assets/Smock_123_18_N.svg)e così via). <br/>![Dipendenza A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | Tutti i valori *set* in una regola deve provenire dallo stesso contenitore e avere lo stesso tipo o un valore derivato dello stesso tipo. <br/> ![Dipendenza B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | I valori da te impostati *select* in [!UICONTROL If], [!UICONTROL Else If] costrutti nella regola do *not* devono provenire dallo stesso contenitore e devono *not* devono essere dello stesso tipo. <br/> ![Dipendenza C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

Trova tutti i valori in un campo selezionato e li sostituisce con un valore diverso in un nuovo campo derivato.

+++ Dettagli

## Specifiche {#findreplace-io}

| Tipo di dati di input | Ingresso | Operatori inclusi | Limite | Output |
|---|---|---|:---:|---|
| <p>Stringa</p> | <ul><li><span>Criteri di campo &quot;Quando sostituire&quot;</span></li><li><span>Valore del campo &quot;Sostituisci con&quot;</span><ul><li><span>Inserito dall’utente</span></li><li><span>Campo separato</span></li></ul></li></ul> | <p><u>Stringhe</u></p><ul><li>Trova tutto e sostituisci tutto</li></ul> | <p>1</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d’uso {#findreplace-uc}

Hai ricevuto alcuni valori non validi per il report dei canali di marketing esterni, ad esempio `email%20 marketing` anziché `email marketing`. Questi valori malformati fraudolono il reporting e rendono più difficile vedere come funziona l’e-mail. Sostituire `email%20marketing` con `email marketing`.

**Rapporto originale**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**Rapporto preferito**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### Dati precedenti {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### Campo derivato {#findreplace-uc-derivedfield}

Definisci un `Email Marketing (updated)` campo derivato. Utilizzi le [!UICONTROL FIND AND REPLACE] per definire una regola per trovare e sostituire tutte le occorrenze di `email%20marketing` con `email marketing`.

![[!DNL Find and Replace] regola](assets/find-and-replace.png)

### Dati dopo {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

Definisce un set di valori di ricerca sostituiti dai valori corrispondenti.

+++ Dettagli


## Specifiche {#lookup-io}

| Tipo di dati di input | Ingresso | Operatori inclusi | Limite | Output |
|---|---|---|:---:|---|
| <ul><li>Stringa</li><li>Numeriche</li><li>Data</li></ul> | <ul><li>Campo singolo</li><li>File di ricerca<ul><li>Colonna chiave</li><li>Nuova colonna campo</li></ul></li></ul> | <p>N/D</p> | <p>5</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d&#39;uso 1 {#lookup-uc1}

Hai un file CSV che include una colonna chiave per `hotelID` e una o più colonne aggiuntive associate al `hotelID`: `city`, `rooms`, `hotel name`.
Stai raccogliendo [!DNL Hotel ID] in una dimensione ma desidera creare un [!DNL Hotel Name] dimensione derivata dalla `hotelID` nel file CSV.

**Struttura e contenuto di file CSV**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |

{style="table-layout:auto"}

**Rapporto corrente**

| [!DNL Hotel ID] | Visualizzazioni prodotto |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |

{style="table-layout:auto"}


**Rapporto desiderato**

| [!DNL Hotel Name] | Visualizzazioni prodotto |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### Dati precedenti {#lookup-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |

{style="table-layout:auto"}


### Campo derivato {#lookup-uc1-derivedfield}

Definisci un `Hotel Name` campo derivato. Utilizzi le [!UICONTROL LOOKUP] per definire una regola in cui è possibile cercare i valori della [!UICONTROL Hotel ID] e sostituisci con nuovi valori.

![[!DNL Lookup] regola 1](assets/lookup-1.png)

### Dati dopo {#lookup-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## Caso d&#39;uso 2 {#lookup-uc2}

Per più pagine sono stati raccolti gli URL invece del nome della pagina descrittiva. Questa raccolta mista di valori interrompe il reporting.

### Dati precedenti {#lookup-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Campo derivato {#lookup-uc2-derivedfield}

Definisci un `Page Name (updated)` campo derivato. Utilizzi le [!UICONTROL LOOKUP] funzione per definire una regola in cui è possibile cercare i valori della [!UICONTROL Page Name] e sostituisci con valori corretti aggiornati.

![[!DNL Lookup] regola 2](assets/lookup-2.png)

### Dati dopo {#lookup-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

Analizza parti diverse di un URL che includono parametri di protocollo, host, percorso o query.

+++ Dettagli

## Specifiche {#urlparse-io}

| Tipo di dati di input | Ingresso | Operatori inclusi | Limite | Output |
|---|---|---|:---:|---|
| <ul><li>Stringa</li></ul> | <ul><li>Campo singolo</li><li>Opzione Analisi<ul><li>Ottieni protocollo</li><li>Ottieni host</li><li>Ottieni percorso</li><li>Ottieni valore query<ul><li>Parametro query</li></ul></li><li>Ottieni valore hash</li></ul></li></ul></li></ul> | <p>N/D</p> | <p>5</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d&#39;uso 1 {#urlparse-uc1}

Vuoi utilizzare il dominio di riferimento solo dall’URL di riferimento come parte del set di regole di un canale di marketing.

### Dati precedenti {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Campo derivato {#urlparse-uc1-derivedfield}

Definisci un  `Referring Domain` campo derivato. Utilizzi le [!UICONTROL URL PARSE] per definire una regola per recuperare l&#39;host dal [!UICONTROL Referring URL] e memorizzalo nel nuovo campo derivato.

![[!DNL Url Parse] regola 1](assets/url-parse-1.png)

### Dati dopo {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## Caso d&#39;uso 2 {#urlparse-uc2}

Desideri utilizzare il valore della `cid` parametro di una stringa query in una [!DNL Page URL] come parte dell&#39;output di un report del codice di tracciamento derivato.

### Dati precedenti {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Campo derivato {#urlparse-uc2-derivedfield}

Definisci un `Query String CID` campo derivato. Utilizzi le [!UICONTROL URL PARSE] per definire una regola per recuperare il valore del parametro della stringa query nel [!UICONTROL Page URL] campo, specifica `cid` come parametro di query. Il valore di output viene memorizzato nel nuovo campo derivato.

![[!DNL Url Parse] regola 2](assets/url-parse-2.png)

### Dati dopo {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++
