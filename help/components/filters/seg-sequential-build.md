---
description: I filtri sequenziali vengono creati utilizzando l’operatore THEN, anziché AND o OR. THEN implica che si verifica un criterio di filtro, seguito da un altro. Per impostazione predefinita, un filtro sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I filtri sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni "Solo prima della sequenza" e "Solo dopo la sequenza".
title: Creare filtri sequenziali
feature: Filters
source-git-commit: 2a9880148864140254d8acb0a53d701c2986dcb1
workflow-type: tm+mt
source-wordcount: '3749'
ht-degree: 64%

---

# Creare filtri sequenziali

I filtri sequenziali vengono creati utilizzando l’operatore THEN, anziché AND o OR. THEN implica che si verifica un criterio di filtro, seguito da un altro. Per impostazione predefinita, un filtro sequenziale identifica tutti i dati corrispondenti, mostrando il filtro &quot;Includi tutti&quot;. I filtri sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni &quot;Solo prima della sequenza&quot; e &quot;Solo dopo la sequenza&quot;.

![](assets/before-after-sequence.png)

Ecco un video sulla segmentazione sequenziale:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Includi tutti {#include_everyone}

Quando crei un filtro in cui è impostato &quot;Includi tutti&quot;, il filtro identifica i percorsi che corrispondono al pattern specificato nel suo insieme. Questo è un esempio di un filtro di sequenza di base che cerca un hit (Pagina A) seguito da un altro (Pagina B) visitato dallo stesso visitatore. Il filtro è impostato su Includi tutti.

![](assets/filter.png)
![70a875e2-0ef9-4459-8648-77c60081d64d](https://git.corp.adobe.com/storage/user/5902/files/d55be11f-4c4c-4198-bba5-ecad27ebcabf)

| Se il risultato | Sequenza |
|--- | --- |
| Corrisponde | A then B<br>A then (in una visita diversa) BA then D then B |
| Non corrisponde | B then A |

## Solo prima della sequenza e Solo dopo la sequenza {#only_before_after}

Le opzioni **[!UICONTROL Only Before Sequence]** e **[!UICONTROL Only After Sequence]** filtra il filtro in un sottoinsieme di dati prima o dopo la sequenza specificata.

* **Solo prima della sequenza**: include tutti gli hit prima di una sequenza più il primo hit della sequenza stessa (vedi gli esempi 1 e 3). Se una sequenza appare più volte in un percorso, “Solo prima della sequenza” include il primo hit dell’ultima occorrenza della sequenza e tutti gli hit precedenti (vedi l’esempio 2).
* **Solo dopo la sequenza**: include tutti gli hit dopo una sequenza più l’ultimo hit della sequenza stessa (vedi gli esempi 1 e 3). Se una sequenza appare più volte in un percorso, “Solo dopo la sequenza” include l’ultimo hit della prima occorrenza della sequenza e tutti gli hit successivi (vedi l’esempio 2).

Ad esempio, considera una sequenza B -> D. I tre filtri identificano gli hit come segue:

**Esempio 1: B then D compare una volta**

| Esempio | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Includi tutti | A | B | C | D | E | F |
| Solo prima della sequenza | A | B |  |  |  |  |
| Solo dopo la sequenza |  |  |  | D | E | F |

**Esempio 2: B then D compare più volte**

| Esempio | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Includi tutti | A | B | C | D | B | C | D | E |
| Solo prima della sequenza | A | B | C | D | B |  |  |  |
| Solo dopo la sequenza |  |  |  | D | B | C | D | E |

Inquadriamo questo concetto anche con la dimensione Profondità di hit.

**Esempio 3: Profondità di hit 3 then 5**

![](assets/hit-depth.png)

## Vincoli della dimensione {#constraints}

In una clausola “within” (entro), tra istruzioni THEN, puoi aggiungere ad esempio “entro 1 istanza di parola chiave di ricerca”, “entro 1 istanza di eVar 47”. Questo vincola il filtro all’interno di un’istanza di una dimensione.

L&#39;impostazione di una clausola &#39;Entro il Dimension&#39; tra le regole consente a un filtro di limitare i dati alle sequenze in cui tale clausola è soddisfatta. Vedi l’esempio seguente, in cui il vincolo è impostato su “Entro 1 pagina”:

![](assets/sequence-filter4.png)

| Se il risultato | Sequenza |
|--- |--- |
| Corrisponde | A then B |
| Non corrisponde | A then C then B (perché B non si trovava entro 1 pagina rispetto ad A)<br>**Nota:** se elimini la restrizione della dimensione, sia “A then B” che “A then C then B” corrisponderanno. |

## Sequenza semplice di visualizzazione di pagina {#simple_sequence}

Identifica i visitatori che hanno visualizzato una pagina e poi un’altra pagina. I dati a livello di hit filtrano questa sequenza indipendentemente dalle sessioni di visita precedenti, passate o intermedie o dal momento o dal numero di visualizzazioni di pagina che si verificano tra le pagine.

**Esempio**: il visitatore ha visualizzato la pagina A e poi la pagina B nella stessa visita o in un’altra.

**Casi di utilizzo**

Di seguito sono riportati alcuni esempi di utilizzo del filtro.

1. I visitatori di un sito sportivo visualizzano la pagina di destinazione del calcio e poi la pagina di destinazione del basket in ordine sequenziale, ma non necessariamente nella stessa visita. In questo modo una campagna riceve l’istruzione di inviare contenuti relativi al basket ai visualizzatori durante la stagione calcistica.
1. Un rivenditore di automobili identifica una relazione tra coloro che visitano per prima cosa la pagina relativa alla fedeltà clienti e poi visitano la pagina video in qualsiasi momento durante la stessa visita o in un’altra visita.

**Crea questo filtro**

È possibile nidificare due regole di pagina all’interno di un contenitore principale [!UICONTROL Visitor] e sequenziare gli hit di pagina utilizzando l’operatore [!UICONTROL THEN].

![](assets/segment_sequential_1.png)

## Sequenza di visitatori in più visite {#sequence_across}

Identifica i visitatori che hanno abbandonato una campagna ma sono poi tornati alla sequenza di visualizzazioni di pagina in un’altra sessione.

**Esempio**: il visitatore ha visualizzato la pagina A in una visita, quindi ha visualizzato la pagina B in un’altra visita.

**Casi di utilizzo**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di filtro:

* I visitatori della pagina Sport di un sito di notizie visitano nuovamente la pagina Sport in un’altra sessione.
* Un rivenditore di abbigliamento individua una relazione tra i visitatori che visitano per prima cosa una pagina di destinazione in una sessione e quindi si spostano direttamente alla pagina di pagamento in un’altra sessione.

**Crea questo filtro**

In questo esempio vengono nidificati due **[!UICONTROL Visit]** contenitori all’interno del livello superiore **[!UICONTROL Visitor]** contenitore e crea una sequenza del filtro utilizzando [!UICONTROL THEN] operatore.

![](assets/visitor_seq_across_visits.png)

## Sequenza a livello misto {#mixed_level}

Identifica i visitatori che visualizzano due pagine nel corso di un numero indeterminato di visite, ma poi visualizzano una terza pagina in una visita separata.

**Esempio**: i visitatori visitano la pagina A e poi la pagina B in una o più visite e in seguito visualizzano la pagina C in una visita separata.

**Casi di utilizzo**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di filtro:

* Il visitatore visita prima un sito di notizie e poi la pagina Sport nella stessa visita. In un’altra visita il visitatore visita la pagina Meteo.
* Il rivenditore definisce i visitatori che accedono alla pagina Principale e poi alla pagina Il mio account. In un’altra visita, visualizzano la pagina Visualizza carrello.

**Crea questo filtro**

1. Rilascia due dimensioni pagina dai riquadri a sinistra all’interno di un contenitore principale [!UICONTROL Visitor].
1. Aggiungi l’operatore THEN tra le dimensioni.
1. Fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container]**, quindi aggiungi un contenitore [!UICONTROL Visit] sotto al livello [!UICONTROL Visitor]e crea una sequenza utilizzando l’operatore [!UICONTROL THEN].

![](assets/mixed_level_checkpoints.png)

## Aggregare i contenitori {#aggregate_containers}

L’aggiunta di più contenitori [!UICONTROL Hit] all’interno di un contenitore [!UICONTROL Visitor] consente di utilizzare gli operatori appropriati tra lo stesso tipo di contenitori e di utilizzare regole e dimensioni quali pagina e numero visite per definire la visualizzazione di pagina e fornire una dimensione di sequenza all’interno del contenitore [!UICONTROL Hit]. L’applicazione della logica a livello di hit consente di vincolare e combinare le corrispondenze a uno stesso livello di hit all’interno di [!UICONTROL Visitor] contenitore per la creazione di diversi tipi di filtri.

**Esempio**: i visitatori hanno visitato la pagina A dopo il primo hit nella sequenza di visualizzazioni di pagina (pagina D nell’esempio), poi hanno visitato la pagina B o la pagina C senza tenere conto del numero di visite.

**Casi di utilizzo**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di filtro:

* Per identificare i visitatori che visitano la pagina di destinazione Principale in una visita, poi visualizzano la pagina Abbigliamento uomo in un’altra visita e poi visualizzano la pagina di destinazione Abbigliamento donna o bambino in un’altra visita.
* Una rivista online acquisisce i visitatori che accedono alla Home page in una visita, alla pagina Sport in un’altra visita e alla pagina Opinioni in un’altra visita.

**Crea questo filtro**

1. Seleziona il contenitore [!UICONTROL Visitor] come contenitore principale.
1. Aggiungi due contenitori a livello di [!UICONTROL Hit]: una dimensione con una dimensione numerica appropriata unita allo stesso livello di [!UICONTROL Hit] dagli operatori [!UICONTROL AND] e [!UICONTROL OR].
1. All’interno del contenitore [!UICONTROL Visit], aggiungi un altro contenitore [!UICONTROL Hit] e nidifica altri due contenitori [!UICONTROL Hit] uniti con un operatore [!UICONTROL OR]o [!UICONTROL AND].

   Crea una sequenza per questi contenitori [!UICONTROL Hit] nidificati con l’operatore [!UICONTROL THEN].

![](assets/aggregate_checkpoints2.png)

## &quot;Nidificazione&quot; nei filtri sequenziali {#nesting}

Posizionando punti di controllo in corrispondenza di entrambi [!UICONTROL Visit] e [!UICONTROL Hit] livello, puoi vincolare il filtro in modo da soddisfare i requisiti all’interno di una visita specifica o di un hit specifico.

**Esempio**: il visitatore ha visitato la pagina A e poi la pagina B nella stessa visita. In una nuova visita, il visitatore è quindi passato alla pagina C.

**Crea questo filtro**

1. Trascina due dimensioni di pagina sotto un contenitore principale [!UICONTROL Visit].
1. Seleziona entrambe le regole, fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]** e modificalo in un contenitore [!UICONTROL Visit].
1. Uniscile con un operatore [!UICONTROL THEN].
1. Crea un contenitore Hit come peer per il contenitore [!UICONTROL Visit] e trascina una dimensione di pagina.
1. Unisci la sequenza nidificata nel contenitore [!UICONTROL Visit] con il contenitore [!UICONTROL Hit] utilizzando un altro operatore [!UICONTROL THEN].

![](assets/nesting_sequential_seg.png)

## Escludere gli hit {#exclude}

Le regole del segmento includono tutti i dati a meno che tu non escluda espressamente i dati di [!UICONTROL Visitor], [!UICONTROL Visit] o [!UICONTROL Hit] utilizzando la regola [!UICONTROL Exclude]. Ti consente di ignorare i dati comuni e creare filtri con più attenzione. Oppure consente di creare filtri escludendo i gruppi individuati per identificare il set di dati rimanente, ad esempio creando una regola che includa i visitatori che hanno effettuato un ordine e poi escludendoli per identificare i &quot;non acquirenti&quot;. Tuttavia, nella maggior parte dei casi è meglio creare regole che escludano valori ampi piuttosto che cercare di utilizzare la regola [!UICONTROL Exclude] per valori di inclusione specifici.

Esempio:

* **Escludi pagine**. Utilizza una regola di filtro per eliminare una pagina specifica (ad esempio *`Home Page`*) da un rapporto, crea una regola Hit in cui la pagina è uguale a &quot;Home page&quot;, quindi escludila. Questa regola include automaticamente tutti i valori eccetto “Home page”.
* **Escludi i domini di riferimento**. Utilizza una regola che include solo i domini di riferimento da Google.com ed esclude tutti gli altri.
* **Identifica i non acquirenti**. Identifica quando gli ordini sono maggiori di zero e quindi esclude il [!UICONTROL Visitor].

L’operatore [!UICONTROL Exclude] può essere utilizzato per identificare una sequenza in cui visite o hit specifici non vengono eseguiti dal visitatore. [!UICONTROL Exclude Checkpoints] può essere incluso anche all’interno di un Gruppo logico (vedi di seguito).

### Escludi tra punti di controllo {#exclude_between}

Applica la logica per filtrare i visitatori quando un punto di controllo non si è verificato esplicitamente tra altri due punti di controllo.

**Esempio**: i visitatori che hanno visitato la pagina A e poi la pagina C, ma non la pagina B.

**Casi di utilizzo**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di filtro:

* I visitatori visualizzano una pagina Lifestyle e poi la sezione Teatro senza visitare la pagina Arte.
* Un rivenditore di automobili vede una relazione tra coloro che visitano la pagina di destinazione principale e poi vanno direttamente alla campagna Nessun interesse senza visitare la pagina Veicolo.

**Crea questo filtro**

Crea un filtro come faresti per un filtro sequenziale semplice, a livello misto o nidificato, quindi imposta il [!UICONTROL EXCLUDE] per l&#39;elemento contenitore. L’esempio seguente è un filtro di aggregazione in cui i tre [!UICONTROL Hit] i contenitori vengono trascinati nell’area di lavoro, il [!UICONTROL THEN] operatore assegnato per unire la logica del contenitore, quindi escludere il contenitore della visualizzazione di pagina centrale in modo da includere solo i visitatori che sono passati dalla pagina A alla pagina C nella sequenza.

![](assets/exclude_between_checkpoints.png)

### Escludi all’inizio della sequenza {#exclude_beginning}

Se il punto di controllo di esclusione si trova all’inizio di un filtro sequenziale, ciò assicura che una visualizzazione di pagina esclusa non si sia verificata prima del primo hit non escluso.

Ad esempio, un ristorante vuole vedere gli utenti che tendono ad evitare la pagina di destinazione principale e vanno direttamente alla pagina Ordina. Puoi visualizzare questi dati escludendo gli hit nella pagina di destinazione e includendo gli hit nella pagina Ordina in un filtro sequenziale.

**Crea questo filtro**

Crea due contenitori Hit separati all’interno di un contenitore Visitor di livello principale. Quindi, imposta l’operatore [!UICONTROL EXCLUDE] per il primo contenitore.

![](assets/exclude_beginning_sequence.png)

### Escludi alla fine della sequenza {#exclude_end}

Se il punto di controllo di esclusione si trova alla fine di una sequenza, ciò assicura che il punto di controllo non si sia verificato tra l’ultimo punto di controllo non escluso e la fine della sequenza del visitatore.

Ad esempio, un negozio di abbigliamento vuole vedere tutti i visitatori che hanno visualizzato una pagina di prodotto ma poi non hanno mai visitato il loro carrello. Questo esempio può essere semplificato per un visitatore che va alla pagina A e non va mai alla pagina B nelle visite correnti o successive.

**Crea questo filtro**

Creare un filtro di sequenza semplice trascinandone due [!UICONTROL Hit] all’area di lavoro e collegarli utilizzando il [!UICONTROL THEN] operatore. Quindi assegna l’operatore [!UICONTROL EXCLUDE] al secondo contenitore [!UICONTROL Hit] della sequenza.

![](assets/exclude_end_sequence.png)

## Contenitori Gruppo logico {#logic_group}

I contenitori Gruppo logico sono necessari per raggruppare le condizioni in un singolo punto di controllo del filtro sequenziale. Il contenitore Gruppo logico è disponibile solo nella segmentazione sequenziale per assicurare che le sue condizioni siano soddisfatte dopo qualsiasi punto di controllo sequenziale precedente e prima di qualsiasi punto di controllo sequenziale successivo. Le condizioni all’interno del punto di controllo del Gruppo logico stesso possono essere soddisfatte in qualsiasi ordine. Al contrario, i contenitori non sequenziali (Hit, Visita, Visitatore) non richiedono che le loro condizioni siano soddisfatte all’interno della sequenza globale, generando risultati poco intuitivi se utilizzati con un operatore THEN.
Il contenitore [!UICONTROL Logic Group] è stato progettato per trattare *diversi punti di controllo come un gruppo*, *senza alcun ordine* tra i punti di controllo raggruppati. In altre parole, l’ordine dei punti di controllo all’interno di quel gruppo è irrilevante. Ad esempio, non è possibile nidificare un contenitore [!UICONTROL Visitor] all’interno di un contenitore [!UICONTROL Visitor]. È invece possibile nidificare un contenitore [!UICONTROL Logic Group] all’interno di un contenitore [!UICONTROL Visitor] con specifici punti di controllo a livello di [!UICONTROL Visit] e [!UICONTROL Hit].

>[!NOTE]
>
>A [!UICONTROL Logic Group] può essere definito solo in un filtro sequenziale, il che significa che [!UICONTROL THEN] all&#39;interno dell&#39;espressione.

| Gerarchia dei contenitori | Illustrazione | Definizione |
|---|---|---|
| Gerarchia dei contenitori standard | ![](assets/nesting_container.png) | All&#39;interno del [!UICONTROL Visitor] contenitore, il [!UICONTROL Visit] e [!UICONTROL Hit] i contenitori sono nidificati in sequenza per estrarre i filtri in base agli hit, al numero di visite e al visitatore. |
| Gerarchia dei contenitori logica | ![](assets/logic_group_hierarchy.png) | La gerarchia dei contenitori standard è necessaria anche all’esterno del contenitore [!UICONTROL Logic Group]. Ma all’interno del contenitore [!UICONTROL Logic Group], i punti di controllo non richiedono un ordine o una gerarchia stabiliti, devono semplicemente essere soddisfatti dal visitatore in qualsiasi ordine. |

I gruppi logici possono sembrare scoraggianti. Ecco alcune best practice per utilizzarli:

**Gruppo logico o contenitore Hit/Visita?**
Se desideri raggruppare punti di controllo sequenziali, il “contenitore” di cui hai bisogno è Gruppo logico. Tuttavia, se i punti di controllo sequenziali devono verificarsi nell’ambito di un singolo hit o di una visita, è necessario un contenitore Hit o Visita. Risulta ovvio che il contenitore Hit non è adatto per un gruppo di punti di controllo sequenziali, quando un hit può accreditare non più di un punto di controllo.

**I gruppi logici semplificano la creazione di filtri sequenziali?**
Sì. Supponiamo che tu stia cercando di identificare questo filtro di visitatori: **I visitatori che hanno visualizzato la pagina A e poi le pagine B, C e D**

Puoi creare questo filtro senza un contenitore Gruppo logico, ma è complesso e laborioso. Dovresti specificare ogni sequenza di pagine che il visitatore può visualizzare:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

Un contenitore Gruppo logico semplifica notevolmente la creazione di questo filtro, come illustrato di seguito:

![](assets/logic-grp-example.png)


### Creare un filtro Gruppo logico {#logic_group_filter}

Come altri contenitori, i contenitori [!UICONTROL Logic Group] possono essere costruiti in più modi all’interno del [!UICONTROL Segment Builder]. Di seguito viene illustrata la modalità consigliata per la nidificazione dei contenitori [!UICONTROL Logic Group]:

1. Trascina dimensioni, eventi o filtri dai riquadri a sinistra.
1. Modifica il contenitore in alto in un contenitore [!UICONTROL Visitor].
1. Modifica l’operatore [!UICONTROL AND] o [!UICONTROL OR] inserito per impostazione predefinita e imposta l’operatore THEN.
1. Seleziona i contenitori [!UICONTROL Hit] (Dimensione, Evento o Elemento) e fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**.
1. Fai clic sull’icona del contenitore e seleziona **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. Ora puoi impostare il contenitore [!UICONTROL Hit] all’interno del contenitore [!UICONTROL Logic Group] senza considerare la gerarchia.

### Punti di controllo del Gruppo logico in qualsiasi ordine {#any_order}

L’utilizzo di [!UICONTROL Logic Group] consente di soddisfare le condizioni all’interno del gruppo che risiedono al di fuori della sequenza. Questo consente di creare filtri in cui [!UICONTROL Visit] o [!UICONTROL Hit] il contenitore si verifica indipendentemente dalla gerarchia normale.

**Esempio**: visitatori che hanno visitato la pagina A e poi la pagina B e C in qualsiasi ordine.

**Crea questo filtro**

Le pagine B e C sono nidificate in un contenitore [!UICONTROL Logic Group] all’interno del contenitore [!UICONTROL Visitor] esterno. Il contenitore [!UICONTROL Hit] per A è seguito dal contenitore [!UICONTROL Logic Group] in cui B e C sono identificate utilizzando l’operatore [!UICONTROL AND]. Poiché si trova in [!UICONTROL Logic Group], la sequenza non è definita e visitare le pagine B e C in un qualsiasi ordine rende l’argomento true.

![](assets/logic_group_any_order2.png)

**Un altro esempio**: visitatori che hanno visitato la pagina B o la pagina C e poi hanno visitato la pagina A.

![](assets/logic_group_any_order3.png)

Il filtro deve corrispondere ad almeno uno dei punti di controllo del gruppo logico (B o C). Inoltre, le condizioni del gruppo logico possono essere soddisfatte nello stesso hit o tra più hit&#x200B;.

### Prima corrispondenza del Gruppo logico {#first_match}

L’utilizzo di [!UICONTROL Logic Group] consente di soddisfare le condizioni all’interno del gruppo che risiedono al di fuori della sequenza. In questo filtro di prima corrispondenza non ordinato, il [!UICONTROL Logic Group] Le regole sono identificate inizialmente come una visualizzazione di pagina della pagina B o della pagina C, poi come la visualizzazione richiesta della pagina A.

**Esempio**: visitatori che hanno visitato la pagina B o la pagina C e poi hanno visitato la pagina A.

**Crea questo filtro**

Le dimensioni di pagina B e pagina C sono raggruppate all’interno di un contenitore [!UICONTROL Logic Group] in cui è selezionato l’operatore [!UICONTROL OR], e poi all’interno del contenitore [!UICONTROL Hit] che identifica come valore la visualizzazione della pagina A.

![](assets/logic_group_1st_match.png)

### Escludi AND in Gruppo logico {#lg_exclude_and}

Creare filtri utilizzando [!UICONTROL Logic Group] quando più visualizzazioni di pagina sono aggregate per definire quali pagine dovevano essere visitate necessariamente mentre altre pagine sono state specificatamente saltate. ****

**Esempio**: il visitatore ha visitato la pagina A, poi ha esplicitamente saltato la pagina B o C, ma ha visualizzato la pagina D.

**Crea questo filtro**

Crea questo filtro trascinando Dimension, Eventi e filtri pregenerati dai riquadri a sinistra. Consulta la sezione sulla Creazione di un filtro Gruppo logico.

Dopo aver nidificato i valori all’interno del [!UICONTROL Logic Group], fai clic sul pulsante **[!UICONTROL Exclude]** all’interno del contenitore [!UICONTROL Logic Group].

![](assets/logic_exclude_and.png)

### Escludi OR in Gruppo logico {#lg_exclude_or}

Creare filtri utilizzando [!UICONTROL Logic Group] quando più visualizzazioni di pagina sono aggregate per definire quali pagine dovevano essere visitate necessariamente mentre altre pagine sono state specificatamente saltate.

**Esempio**: visitatori che hanno visitato la pagina A, ma non hanno visitato la pagina B o la pagina C prima della pagina A.

**Crea questo filtro**

Le pagine B e C iniziali sono identificate in un contenitore [!UICONTROL Logic Group], che viene escluso, e sono seguite da un hit della pagina A da parte del visitatore.

Crea questo filtro trascinando Dimension, eventi e segmenti predefiniti dai riquadri a sinistra.

Dopo aver nidificato i valori all’interno del [!UICONTROL Logic Group], fai clic sul pulsante **[!UICONTROL Exclude]** all’interno del contenitore [!UICONTROL Logic Group].

![](assets/logic_exclude_or.png)

## Creare filtri entro e dopo il tempo {#time_within_after}

Utilizza gli operatori [!UICONTROL Within] e [!UICONTROL After] incorporati nell’intestazione di ciascun contenitore per definire periodo di tempo, eventi e conteggio.

![](assets/then_within_operators.png)

Puoi limitare la corrispondenza a una determinata durata utilizzando gli operatori [!UICONTROL Within] e [!UICONTROL After] specificando granularità e conteggio. L’operatore [!UICONTROL Within] viene utilizzato per specificare un limite massimo per il periodo di tempo tra due punti di controllo. L’operatore [!UICONTROL After] viene utilizzato per specificare un limite minimo per il periodo di tempo tra due punti di controllo.

>[!NOTE]
>
>Esistono differenze nella valutazione tra elementi con nomi simili, come **Giorno/i** o **Giorno**. Per le definizioni basate sul tempo di Within e After, utilizzate le opzioni elencate per prime nella finestra a comparsa:
>
>![immagine](https://git.corp.adobe.com/storage/user/5902/files/70a875e2-0ef9-4459-8648-77c60081d64d)
>
>Per le definizioni basate sulle dimensioni entro e dopo, utilizza le opzioni del sottomenu *Altri Dimension*:
>
>![immagine](https://git.corp.adobe.com/storage/user/5902/files/b808eeb0-5e3f-499b-8096-c7eb0d51c57a)

### Operatori After e Within {#after_within}

La durata è specificata da una singola lettera maiuscola che rappresenta la granularità seguita da un numero che rappresenta il conteggio di ripetizioni della granularità.

**[!UICONTROL Within]** include il punto finale (minore o uguale a).

**[!UICONTROL After]** non include il punto finale (maggiore di).

| Operatori | Descrizione |
|--- |--- |
| AFTER (DOPO) | L’operatore After viene utilizzato per specificare un limite minimo per il periodo di tempo tra due punti di controllo. Quando si impostano i valori After, il limite di tempo inizia quando viene applicato il filtro. Ad esempio, se l’operatore After è impostato su un contenitore per identificare i visitatori che visitano la pagina A ma non tornano per visitare la pagina B fino a un giorno dopo, quel giorno inizierà quando il visitatore esce dalla pagina A. Affinché il visitatore sia incluso nel filtro, devono trascorrere almeno 1440 minuti (un giorno) dopo l’abbandono della pagina A per visualizzare la pagina B. |
| WITHIN (ENTRO) | L’operatore Within viene utilizzato per specificare un limite massimo per il periodo di tempo tra due punti di controllo. Ad esempio, se l’operatore Within è impostato su un contenitore per identificare i visitatori che visitano la pagina A e poi ritornano a visitare la pagina B entro un giorno, quel giorno inizierà quando il visitatore esce dalla pagina A. Per essere incluso nel filtro, il visitatore avrà un tempo massimo di un giorno prima di aprire la pagina B. Affinché il visitatore sia incluso nel filtro, la visita alla pagina B deve avvenire entro un massimo di 1440 minuti (un giorno) dopo l’abbandono della pagina A per visualizzare la pagina B. |
| AFTER/WITHIN (DOPO/ENTRO) | Quando si utilizza sia After che Within, è importante comprendere che entrambi gli operatori inizieranno e finiranno in parallelo, non in modo sequenziale.   Ad esempio, se crei un filtro con il contenitore impostato su:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Quindi le condizioni per identificare i visitatori nel filtro sono soddisfatte solo tra 1 e 2 settimane. Entrambe le condizioni vengono applicate dal momento del primo hit pagina. |

### Utilizzare l’operatore After {#after}

* After consente di monitorare per anno, mese, giorno, ora e minuto per far corrispondere le visite.
* After può essere applicato solo a un contenitore [!UICONTROL Hit], perché è l’unico livello per il quale è definita una granularità così fine.

**Esempio**: i visitatori che hanno visitato la pagina A hanno visitato la pagina B solo dopo 2 settimane.****

![](assets/time_between_after_operator.png)

**Creare il segmento**: questo filtro viene creato aggiungendo una [!UICONTROL Visitor] contenitore con due [!UICONTROL Hit] contenitori. È quindi possibile impostare l’operatore [!UICONTROL THEN], aprire il menu a discesa dell’operatore [!UICONTROL AFTER] e impostare il numero di settimane.

![](assets/after_operator.png)

**Corrispondenze**

Se si imposta “After 2 weeks” (Dopo 2 settimane), se un hit per la pagina A si verifica il 1° giugno 2019 alle 00:01, un hit successivo per la pagina B corrisponderà ad esso se si verifica prima del 15 giugno 2019 alle 00:01 (14 giorni dopo).

| Hit A | Hit B | Corrispondenza |
|--- |--- |--- |
| Hit **A**: 1° giugno 2019, 00:01 | Hit **B**: 15 giugno 2019, 00:01 | **Corrisponde:** questo vincolo di tempo corrisponde perché è dopo il 1° giugno 2019 (due settimane). |
| Hit **A**: 1° giugno 2019, 00:01 | Hit **B**: 8 giugno 2019, 00:01 Hit B: 15 giugno 2019, 00:01 | **Non corrisponde:** il primo hit sulla pagina B non corrisponde perché è in conflitto con il vincolo che lo richiede dopo due settimane. |

### Utilizzare l’operatore Within {#within}

* [!UICONTROL Within] consente di monitorare per anno, mese, giorno, ora e minuto per far corrispondere le visite.
* [!UICONTROL Within] può essere applicato solo a un contenitore [!UICONTROL Hit], perché è l’unico livello per il quale è definita una granularità così fine.

>[!TIP]
>
>In una clausola “within” (entro), tra istruzioni THEN, puoi aggiungere ad esempio “entro 1 istanza di parola chiave di ricerca”, “entro 1 istanza di eVar 47”. Questo vincola il filtro all’interno di un’istanza di una dimensione.

**Esempio**: i visitatori che hanno visitato la pagina A hanno visitato la pagina B entro 5 minuti.

![](assets/time_between_within_operator.png)

**Creare il filtro**: questo filtro viene creato aggiungendo una [!UICONTROL Visitor] contenitore, quindi trascinamento con due [!UICONTROL Hit] contenitori. È quindi possibile impostare l’operatore [!UICONTROL THEN], aprire l’elenco a discesa dell’operatore [!UICONTROL AFTER] e impostare l’intervallo: hit, visualizzazioni di pagina, visite, minuti, ore, giorni, settimane, mesi, trimestri o anni.

![](assets/within_operator.png)

**Corrispondenze**

Le corrispondenze devono verificarsi entro il limite di tempo. Per l’espressione, se un visitatore visita la pagina A alle 00:01, un hit successivo alla pagina B corrisponderà ad esso se si verifica alle 00:06 o prima (cinque minuti dopo, incluso l’ultimo minuto). Gli hit nello stesso minuto corrisponderanno a loro volta.

### Gli operatori Within e After {#within_after}

Utilizzare [!UICONTROL Within] e [!UICONTROL After] per fornire un punto finale massimo e minimo a entrambe le estremità di un filtro.

**Esempio**: i visitatori che hanno visitato la pagina A hanno poi visitato la pagina B dopo 2 settimane, ma entro 1 mese.

![](assets/time_between_using_both_operators.png)

**Creare il segmento**: crea il filtro sequenziando due [!UICONTROL Hit] contenitori all’interno di una [!UICONTROL Visitor] contenitore. Quindi imposta gli operatori [!UICONTROL After] e [!UICONTROL Within].

![](assets/within_after_together.png)

**Corrispondenze**

Tutti i visitatori che hanno raggiunto la pagina A il 1° giugno 2019 e ritornano dopo le 00:01 del 15 giugno 2019, ma *prima di* 1 luglio 2019 sono inclusi nel filtro. Confronta con la sezione sul periodo tra le esclusioni.

Il [!UICONTROL After] e [!UICONTROL Within] Gli operatori possono essere utilizzati insieme per definire un filtro sequenziale.

![](assets/time_between_within_after.png)

In questo esempio viene illustrata una seconda visita alla pagina B dopo due settimane, ma entro un mese.
