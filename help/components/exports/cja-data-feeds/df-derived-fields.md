---
title: Utilizzare campi derivati nei feed di dati
description: Scopri come utilizzare i campi derivati nei feed di dati.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Utilizzare campi derivati nei feed dati

{{release-limited-testing}}

Puoi eseguire trasformazioni di dati sui dati del feed di dati utilizzando [campi derivati](/help/data-views/derived-fields/derived-fields.md).

Molte funzioni di campo derivato eseguono trasformazioni che possono essere applicate anche utilizzando SQL, ad esempio la sostituzione di valori, la combinazione di campi o la conversione del tipo di dati di un campo, pertanto il metodo scelto è talvolta una questione di preferenze.

## Campi derivati e SQL

Nella tabella seguente vengono confrontati i vantaggi e gli svantaggi dell&#39;utilizzo di campi derivati o SQL.

| Metodo | Vantaggi | Svantaggi |
| --- | --- | --- |
| **Campi derivati** | <ul><li>La stessa logica si applica in modo coerente sia nell’output di Analysis Workspace che nell’output del feed dati, perché i campi derivati vengono inclusi come componenti nello schema del feed dati, insieme alle dimensioni e alle metriche standard.</li><li>Alcune trasformazioni, in particolare quelle che dipendono da un’impostazione di Ambito o che analizzano un URL, sono difficili da replicare in SQL.</li></ul> | Aggiunge il sovraccarico di elaborazione, che può influire sulle prestazioni di consegna dei feed di dati.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>Non limitato dai limiti di funzione e operatore che si applicano ai campi derivati.</li><li>Non ha alcun effetto sulle prestazioni di consegna dei feed di dati.</li></ul> | <ul><li>La logica non si applica in Analysis Workspace, pertanto dovrai duplicarla lì separatamente.</li><li>Alcune trasformazioni, in particolare quelle che dipendono da un’impostazione di Ambito o che analizzano un URL, sono difficili o impraticabili da replicare.</li></ul> |

{style="table-layout:auto"}

## Funzioni campo derivato

Nella tabella seguente vengono descritte tutte le funzioni di campo derivato, adatte a un campo derivato o a SQL, nonché tutte le considerazioni da tenere presenti prima di utilizzarle.

| Funzione campo derivato | Difficoltà di replica con SQL | Adatta (campo derivato o SQL) | Considerazioni |
| --- | --- | --- | --- |
| [**Caso Quando**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> Applica i condizionali in base ai criteri di uno o più campi, imposta il valore di output in base alla corrispondenza della condizione. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. Questa funzione è particolarmente utile quando è coinvolto un numero elevato di regole, ad esempio una classificazione del canale di marketing. |
| [**Classifica**](/help/data-views/derived-fields/derived-fields.md#classify)<br/> Definisce un insieme di valori sostituiti dai valori corrispondenti in un nuovo campo derivato. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Concatenare**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/> Combina i valori dei campi in un unico nuovo campo derivato utilizzando delimitatori definiti, ad esempio nome pagina e canale di marketing. | Facile da moderare | Oppure | Riflette la funzionalità di aggiunta di più colonne di dimensione a una tabella a forma libera, limitata all’esportazione della tabella completa. Un campo derivato rende disponibile un output simile in un feed di dati. |
| [**Matematica data**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> Restituisce la differenza tra due campi data o data-ora (ad esempio, giorni tra una data di prenotazione e una data di check-in), con ambito Evento, Sessione o Persona. | Difficile | Campo derivato | Complesso da replicare in SQL. Questa funzione dipende dall’impostazione di un ambito. Per ulteriori informazioni, vedere [Effetti delle impostazioni di ambito nelle funzioni sui feed di dati](#scope-settings). |
| [**Deduplica**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/> Impedisce il conteggio di un valore più volte, con ambito Persona o Sessione (ad esempio, deduplicando un ID di conferma della prenotazione). | Difficile | Campo derivato | Questa funzione dipende dall’impostazione di un ambito. Per ulteriori informazioni, vedere [Effetti delle impostazioni di ambito nelle funzioni sui feed di dati](#scope-settings). |
| [**Profondità**](/help/data-views/derived-fields/derived-fields.md#depth)<br/> Restituisce la profondità di un campo, in modo analogo alla dimensione Profondità evento standard (ad esempio, profondità di ricerca interna). | Difficile | Campo derivato | Utilizza la sessione come ambito e non è configurabile. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> Il comportamento del contatore quando una sessione si estende su un limite di consegna di feed è ancora in fase di conferma con il team ingegneristico. Questa funzione dipende dall’impostazione di un ambito. Per ulteriori informazioni, vedere [Effetti delle impostazioni di ambito nelle funzioni sui feed di dati](#scope-settings). |
| [**Trova e sostituisci**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/> Trova tutti i valori in un campo selezionato e li sostituisce con un valore diverso. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Ricerca**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/> Cerca un valore da un set di dati di ricerca utilizzando una chiave corrispondente e lo restituisce in un nuovo campo derivato. | Facile da moderare | Oppure | SQL funziona se esiste già una tabella di ricerca. |
| [**In minuscolo**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> Converte i valori da un campo in minuscolo. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Matematica**](/help/data-views/derived-fields/derived-fields.md#math)<br/> Applica gli operatori matematici di base (aggiungere, sottrarre, moltiplicare, dividere o aumentare a una potenza) ai campi numerici, valutati hit per hit. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Unisci campi**](/help/data-views/derived-fields/derived-fields.md#merge)<br/> Controlla se il primo di due o più campi contiene un valore. In caso contrario, utilizza il campo successivo e così via. | Facile da moderare | Oppure | Nessuno |
| [**Successivo o Precedente**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/> Risolve il valore successivo o precedente di un campo della tabella Visita o Evento con ambito Persona o Sessione. | Difficile | Campo derivato | Questa funzione dipende dall’impostazione di un ambito. Per ulteriori informazioni, vedere [Effetti delle impostazioni di ambito nelle funzioni sui feed di dati](#scope-settings). |
| [**Regex Replace**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/> Sostituisce un valore di un campo utilizzando un&#39;espressione regolare. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Dividi**](/help/data-views/derived-fields/derived-fields.md#split)<br/> Divide un valore da un campo in un nuovo campo derivato (ad esempio, convertendo un elenco delimitato in un array). | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Riepiloga**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/> Applica funzioni di aggregazione, ad esempio somma, conteggio o la più comune, a un campo con ambito Evento, Sessione o Persona. | Difficile | Campo derivato | Questa funzione dipende dall’impostazione di un ambito. Per ulteriori informazioni, vedere [Effetti delle impostazioni di ambito nelle funzioni sui feed di dati](#scope-settings). |
| [**Taglia**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> Taglia spazi vuoti, caratteri speciali o un numero impostato di caratteri dall&#39;inizio o dalla fine dei valori di un campo. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Tipo**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/> Modifica il tipo di dati di un campo per renderlo disponibile per ulteriori trasformazioni. | Facile da moderare | Oppure | Riproducibile in SQL, ma l’utilizzo di un campo derivato mantiene la stessa logica applicata in modo coerente sia nell’output di Analysis Workspace che nell’output del feed di dati. |
| [**Analisi URL**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> Analizza parti di un URL, inclusi protocollo, host, percorso, parametro della stringa di query o valore hash. | Difficile | Campo derivato | SQL richiede l&#39;analisi personalizzata delle stringhe per estrarre gli stessi componenti. |

{style="table-layout:auto"}

### Effetti delle impostazioni di ambito nelle funzioni sui feed di dati {#scope-settings}

[!UICONTROL **Matematica data**], [!UICONTROL **Deduplica**], [!UICONTROL **Successiva o Precedente**] e [!UICONTROL **Riepiloga**] dipendono entrambi da un&#39;impostazione [!UICONTROL **Ambito**] di Evento, Sessione o Persona (le opzioni disponibili variano in base alla funzione). [!UICONTROL **Profondità**] non dispone di un campo di ambito configurabile, ma è intrinsecamente legato alla sessione, simile alla dimensione Profondità evento standard. Qualsiasi campo con un ambito scrive lo stesso valore in ogni riga all’interno di tale ambito e tale valore dipende dai dati all’interno dell’intervallo di date di lookback.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Poiché l’intervallo di date di lookback slitta in avanti con ogni consegna di feed di dati, lo stesso campo può restituire un valore diverso in una consegna successiva, anche per eventi che si sono già verificati.

Aumenti del rischio con la dimensione dell’ambito: l’ambito della persona comporta più rischi rispetto all’ambito della sessione, perché la cronologia di una persona non ha limiti di tempo naturali all’interno di un’esecuzione di un feed.

## Modelli di funzione campo derivato

[Modelli di funzione campo derivato](/help/data-views/derived-fields/derived-fields.md#templates) ti consentono di creare rapidamente un campo derivato per un caso d&#39;uso specifico, ad esempio la creazione di canali di marketing, il rilevamento di bot o l&#39;estrazione di un parametro UTM da un URL. Poiché un modello viene creato da una catena di regole predefinite, è quasi sempre preferibile utilizzarne una invece di riprodurre la stessa logica in SQL da zero.

Se un modello include una funzione che dipende da un&#39;impostazione di ambito, il modello eredita l&#39;attenzione di ambito di tale funzione. Vedi [Come le impostazioni di ambito nelle funzioni influiscono sui feed di dati](#scope-settings).

