---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# Calcoli statistici nel pannello Sperimentazione di CJA: Dettagli

In questa pagina sono documentati i calcoli statistici dettagliati utilizzati nel pannello Sperimentazione di CJA. È destinato agli utenti tecnici.


## Tasso di conversione

il tasso di conversione o **meschino**, *μ<sub>ν</sub>* per ogni variante *ν* in un esperimento è definito come un rapporto tra la somma della metrica e il numero di unità assegnate a tale metrica, *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="media"></p>
Qui,

- *Y<sub>idroid</sub>* è il valore della metrica per ogni unità *i*, che è stato assegnato a una determinata variante *ν*.
- La somma su unità *i* dipende dalla scelta della metrica di normalizzazione.
   - Se *Persone* è la metrica di normalizzazione, ogni unità è una persona/profilo univoco.
   - Se *Sessioni* è la metrica di normalizzazione, ogni unità è una sessione univoca.
   - Se *Eventi* è la metrica di normalizzazione, ogni unità è un evento univoco.

In generale, questa metrica di normalizzazione deve essere scelta per essere equivalente alla tua unità di indipendenza, ovvero, se il comportamento di un utente in una sessione sarà indipendente dal suo comportamento in un&#39;altra sessione, le sessioni saranno una metrica di normalizzazione ragionevole.

Se necessario, viene utilizzata la deviazione standard del campione, con l&#39;espressione


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="media"></p>


## Incremento

L’incremento tra una variante  *ν* e la variante di controllo  *ν<sub>0</sub>* è il relativo &quot;delta&quot; nei tassi di conversione, definito come
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="media"></p>
dove i singoli tassi di conversione sono definiti sopra.


## Sequenze di affidabilità

Non visualizzata nel pannello Sperimentazione CJA, la sequenza di affidabilità per una singola variante *ν* è centrale nella metodologia statistica utilizzata dall&#39;Adobe, e così è definito qui (riprodotto da [Waudby-Smith et al.](https://doi.org/10.48550/arXiv.2103.06476)).

> Supponiamo che uno sia interessato a stimare un parametro target *R* (come il tasso di conversione di una variante in un esperimento). Quindi, la dicotomia tra una sequenza di intervalli di affidabilità a tempo fisso e una sequenza di confidenza uniforme in termini di tempo può essere riassunta come segue:
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="media"></p>

In parole: per un intervallo di affidabilità regolare , la garanzia probabilistica che il parametro target si trovi all’interno dell’intervallo di valori *Ċ<sub>t</sub>* è valido solo a un singolo valore fisso di *n* (4) *n* è il numero di campioni). Al contrario per una sequenza di affidabilità, siamo certi che in ogni momento/ tutti i valori della dimensione del campione *t*, il valore &quot;true&quot; del parametro di interesse si trova entro i limiti *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

Questo ha alcune profonde implicazioni che sono molto importanti per i test online:
- Il CS può essere aggiornato facoltativamente ogni volta che nuovi dati diventano disponibili.
- Gli esperimenti possono essere monitorati in modo continuo, arrestati in modo adattivo o continuati.
- L&#39;errore di tipo I viene controllato in tutti i momenti di arresto, compresi i tempi dipendenti dai dati.

L’Adobe utilizza le sequenze di confidenza asintotica, che per una singola variante con stima media *μ* ha il modulo

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="media"></p>

Dove:
- *N* è il numero di unità della variante
- *Þ* è una stima campione della deviazione standard (definita in precedenza)
- *α* è il livello desiderato di errore di tipo I (o probabilità di errore di copertura)
- *true*<sup> 2</sup> è una costante che regola la dimensione del campione a cui il CS è più stretto. L&#39;Adobe ha scelto un valore universale di *true*<sup> 2</sup> = 10<sup>-2,8</sup>, appropriato per i tipi di tassi di conversione rilevati negli esperimenti online.


## Confidence

L&#39;affidabilità utilizzata dall&#39;Adobe è un&#39;affidabilità &quot;valida in qualsiasi momento&quot;, ottenuta invertendo la sequenza di confidenza per l&#39;effetto di trattamento medio.

Per essere precisi, si nota che in un campione *t* per verificare la differenza di mezzi tra due varianti, esiste una mappatura 1:1 tra i *p*-value per questo test e l&#39;intervallo di affidabilità per la differenza nei mezzi. Per analogia, una qualsiasi volta valida *p*-value può essere ottenuto invertendo la sequenza di confidenza (in qualsiasi momento valida) per il calcolatore medio dell&#39;effetto di trattamento:
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="media"></p>

Lo stimatore che usiamo è uno stimatore di tendenza inversa (IPW). Considera *N = N<sub>0</sub>* + *N<sub>1</sub>* unità, le assegnazioni di variante per ciascuna unità $i$ etichettate da *A<sub>i</sub>=0,1* se l&#39;unità è assegnata alla variante=0,1. Se gli utenti sono assegnati con probabilità fissa (propensione) *π<sub>0</sub>, (1 π)<sub>0</sub>)* e la metrica del loro risultato è *Y<sub>i</sub>*, quindi lo stimatore IPW è
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="media"></p>

Nota che *f* è la funzione di influenza, Waudby-Smith et al. mostra che la sequenza di affidabilità per questo stimatore è:
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="media"></p>

Sostituzione della probabilità di assegnazione con le relative stime empiriche: *π<sub>0</sub> = N<sub>0</sub>/N*, il termine di varianza può essere espresso in termini di stime medie dei singoli campioni  *μ<sub>{0,1}</sub>* e stime di deviazione standard,  *Þ<sub>{0,1}</sub>* come:

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="media"></p>


rammentando che per un test di ipotesi regolare con dati statistici sul test *z = (μ<sub>1</sub> - μ<sub>0</sub>)/<sub>p</sub>*, esiste una corrispondenza tra i valori $p$ e gli intervalli di affidabilità:

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="media"></p>

dove *Þ* è la distribuzione cumulativa della norma normale. In qualsiasi momento valido *p*-valori, data la sequenza di affidabilità per l&#39;effetto di trattamento medio sopra definito, possiamo invertire questa relazione:
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="media"></p>

Infine, la **in qualsiasi momento valido *fiducia*** è
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="media"></p>


## Dichiarare conclusivo un esperimento

Per un esperimento con due bracci, il pannello Sperimentazione CJA visualizza un messaggio che informa che un esperimento è **conclusivo** quando l&#39;affidabilità valida in qualsiasi momento supera il 95% (ovvero, la validità in qualsiasi momento *p*-value è inferiore al 5%).

Se sono presenti più di due varianti, viene applicata la correzione Bonferonni. Per un esperimento con *K* trattamenti, e un unico trattamento di base (controllo), ci sono *K-1* test di ipotesi indipendenti. La correzione Bonferonni significa che respingiamo l&#39;ipotesi null secondo cui il controllo e una determinata variante hanno mezzi uguali, se valida in qualsiasi momento *p*-value è inferiore a una soglia di 0,05/(K-1).


## Braccio dalle prestazioni migliori

Quando un esperimento viene dichiarato conclusivo, viene visualizzato il braccio con le prestazioni migliori. Questa è la leva con le migliori prestazioni (media più alta o tasso di conversione), tra il Set che include il controllo, e tutti i bracci che hanno un *p*-valore inferiore alla soglia Bonferonni.