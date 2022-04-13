---
title: Impostazioni del componente della sottostringa
description: Utilizzare un sottoinsieme di una stringa come elementi dimensionali.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: a8bdb5b0c00a9dbca2f466452a5d18045b2e9971
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# [!UICONTROL Substring] Impostazioni del componente

[!UICONTROL Substring] le impostazioni dei componenti consentono di eseguire più metodi di manipolazione delle stringhe per ottenere gli elementi dimensionali desiderati nei rapporti.

[!UICONTROL Substring] è disponibile solo sulle dimensioni ed è retroattivo ai dati a cui viene applicato. Si tratta di una trasformazione immediata dei dati che avviene prima dell’applicazione di filtri o di altre operazioni di analisi.

![Impostazioni della sottostringa](../assets/substring-settings.png)

## Da sinistra/destra

Prendi parte di una stringa in base alla sua posizione all’inizio o alla fine di una stringa. **[!UICONTROL From the Left]** e **[!UICONTROL From the Right]** i metodi forniscono due elenchi a discesa: **[!UICONTROL From]** (quando inizia l&#39;uscita) e **[!UICONTROL To]** (dove termina l&#39;output).

* **[!UICONTROL String Start]**: L&#39;inizio della stringa.
* **[!UICONTROL String End]**: Fine della stringa.
* **[!UICONTROL Position]**: Un numero statico di caratteri da sinistra o da destra, a seconda del metodo .
* **[!UICONTROL String]**: Per indicare l’inizio o la fine di una stringa, fai corrispondere un carattere o una sequenza di caratteri. Questo menu a discesa rivela anche opzioni aggiuntive:
   * **[!UICONTROL Match]**: Stringa corrispondente. Se l’input non corrisponde a questo campo, [Nessuna opzione di valore](no-value-options.md) applicare.
   * **[!UICONTROL Index]**: La **[!UICONTROL Match]** I criteri possono essere presenti più volte in una stringa. Questo numero intero determina la corrispondenza con cui avviare o terminare l&#39;output, a seconda del metodo. Ad esempio, un indice di `1` rappresenta la prima corrispondenza. Se l&#39;indice è superiore al numero di corrispondenze disponibili, [Nessuna opzione di valore](no-value-options.md) applicare.
   * **[!UICONTROL Include String]**: Una casella di controllo che include **[!UICONTROL Match]** stringa nell&#39;output se abilitata.
* **[!UICONTROL Length]**: Un numero intero che specifica il numero di caratteri da includere dopo la posizione iniziale dell&#39;output. Disponibile solo in **[!UICONTROL To]** a discesa.

## Delimitatore

Utilizzare questo metodo per i campi che utilizzano un delimitatore per separare più valori stringa. È possibile estrarre un singolo elemento da utilizzare come output oppure convertire la stringa in un elemento schema array di oggetti.

* **[!UICONTROL Criterion]**: Come trattare l’elenco delimitato di valori.
   * **[!UICONTROL From the Left]**: Inizia dall’inizio dell’elenco delimitato e conta in avanti.
   * **[!UICONTROL From the Right]**: Inizia dalla fine dell’elenco delimitato e conta all’indietro.
   * **[!UICONTROL Convert to array]**: Considera questa dimensione come un elemento schema array di oggetti.
* **[!UICONTROL Delimiter]**: Il delimitatore utilizzato dal campo.
* **[!UICONTROL Index]**: Disponibile solo se il criterio è Da sinistra/Da destra. Il numero dell&#39;elemento come se si trovasse in una matrice. Ad esempio, se l’input della stringa è `"Fox,Turtle,Rabbit,Wolf"` con un indice di 3, l&#39;output è `"Rabbit"`. Se l&#39;indice è superiore al numero di elementi delimitati, [Nessuna opzione di valore](no-value-options.md) applicare.

## Analisi URL

Da utilizzare con campi contenenti URL. Utilizzo dell’URL di esempio `https://example.com/store/index.html?cid=campaign#cart`, sono disponibili le seguenti opzioni:

* **[!UICONTROL Get protocol]**: Ottieni il protocollo dell’URL. Ad esempio, `"https://"`.
* **[!UICONTROL Get host]**: Ottieni l&#39;host dell&#39;URL. Ad esempio, `"example.com"`.
* **[!UICONTROL Get path]**: Ottieni il percorso dell’URL. Ad esempio, `"store/index.html"`.
* **[!UICONTROL Get query string value]**: Ottieni il valore da una singola stringa di query. Inserisci il parametro della stringa di query desiderato nel **[!UICONTROL Query key]** campo . Se l&#39;URL di cui sopra viene utilizzato con `"cid"` chiave di query, l&#39;output è `"campaign"`.
* **[!UICONTROL Get hash value]**: Ottieni il valore hash dell’URL. Ad esempio, `"cart"`.

Se l’input non è un URL valido o se il componente URL desiderato non è presente, [Nessuna opzione di valore](no-value-options.md) applicare.

## Rifila

Consente di ritagliare lo spazio vuoto o i caratteri speciali dalla stringa.

* **[!UICONTROL Trim whitespaces]**: Casella di controllo che rimuove tutti gli spazi all’inizio e alla fine della stringa, se abilitata.
* **[!UICONTROL Trim special characters]**: Una casella di controllo che rivela un **[!UICONTROL Special characters]** campo di input se abilitato. Tutti i caratteri in questo campo vengono rimossi dall’output. I caratteri multibyte non sono supportati.

## Regex

Applica espressioni regolari a una dimensione per recuperare il valore desiderato.

* **[!UICONTROL Regex]**: Formula di espressione regolare.
* **[!UICONTROL Output format]**: Campo facoltativo che consente di aggiungere testo o riordinare l’output del sottogruppo regex. Se questo campo è vuoto, l&#39;output della stringa è l&#39;espressione regex valutata.
* **[!UICONTROL Case sensitive]**: Una casella di controllo che forza l’espressione regolare a fare distinzione tra maiuscole e minuscole, se abilitata.

CJA utilizza un sottoinsieme della sintassi regex Perl. Se l’input non corrisponde all’espressione regolare e alla variabile **[!UICONTROL Output format]** è vuoto, [Nessuna opzione di valore](no-value-options.md) applicare. Sono supportate le seguenti espressioni:

| Espressione | Descrizione |
| --- | --- |
| `a` | Un singolo carattere `a`. |
| `a|b` | Un singolo carattere `a` o `b`. |
| `[abc]` | Un singolo carattere `a`, `b`oppure `c`. |
| `[^abc]` | Qualsiasi carattere singolo tranne `a`, `b`oppure `c`. |
| `[a-z]` | Qualsiasi carattere singolo nell&#39;intervallo di `a`-`z`. |
| `[a-zA-Z0-9]` | Qualsiasi carattere singolo nell&#39;intervallo di `a`-`z`, `A`-`Z`o cifre `0`-`9`. |
| `^` | Corrisponde all’inizio della riga. |
| `$` | Corrisponde alla fine della riga. |
| `\A` | Inizio della stringa. |
| `\z` | Fine della stringa. |
| `.` | Corrisponde a qualsiasi carattere. |
| `\s` | Qualsiasi carattere spazio vuoto. |
| `\S` | Qualsiasi carattere tranne gli spazi vuoti. |
| `\d` | Qualsiasi cifra. |
| `\D` | Qualsiasi carattere tranne le cifre. |
| `\w` | Qualsiasi lettera, numero o carattere di sottolineatura. |
| `\W` | Qualsiasi carattere non alfanumerico. |
| `\b` | Qualsiasi confine di parola. |
| `\B` | Qualsiasi carattere che non sia un limite di parola. |
| `\<` | Inizio della parola. |
| `\>` | Fine della parola. |
| `(...)` | Acquisire tutti i caratteri racchiusi tra parentesi. |
| `(?:...)` | Cattura senza marcatura. Impedisce il riferimento alla corrispondenza nella stringa di output. |
| `a?` | Zero o uno di `a`. |
| `a*` | Zero o più di uno di `a`. |
| `a+` | Uno o più di `a`. |
| `a{3}` | Esattamente 3 di `a`. |
| `a{3,}` | 3 o più di `a`. |
| `a{3,6}` | Tra 3 e 6 di `a`. |

Sono supportati anche i segnaposto di output. È possibile utilizzare queste sequenze nella **[!UICONTROL Output format]** qualsiasi numero di volte e in qualsiasi ordine per ottenere l&#39;output della stringa desiderato.

| Sequenza segnaposto di output | Descrizione |
| --- | --- |
| `$&` | Restituisce ciò che corrisponde all’intera espressione. |
| `$n` | Restituisce ciò che corrisponde all’ennesima espressione secondaria. Ad esempio: `$1` restituisce la prima espressione secondaria. |
| ``$` `` | Invia il testo tra la fine dell’ultima corrispondenza trovata (o l’inizio del testo, se non è stata trovata alcuna corrispondenza precedente) e l’inizio della corrispondenza corrente. |
| `$+` | Restituisce ciò che corrisponde all’ultima espressione secondaria contrassegnata nell’espressione regolare. |
| `$$` | Invia il carattere stringa `"$"`. |
