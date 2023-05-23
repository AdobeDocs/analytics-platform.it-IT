---
title: Interfaccia di analisi guidata
description: Scopri la struttura generale dell’interfaccia utente del progetto di analisi guidata.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Interfaccia di analisi della guida

{{release-limited-testing}}

Indipendentemente dal tipo di analisi, l’interfaccia di un progetto di analisi guidata include i seguenti elementi principali dell’interfaccia utente:

* **Barra delle query**: utilizza questa barra a sinistra del progetto per creare l’analisi.
* **Grafico**: dopo aver selezionato gli eventi, le persone o i passaggi desiderati, a destra viene visualizzato un grafico che visualizza i dati.
* **Tabella**: tabella sotto il grafico che mostra i numeri utilizzati nella visualizzazione.
* **Impostazioni e informazioni**: diversi elementi dell’interfaccia utente sopra il grafico che consentono di personalizzare i dati restituiti.

[Schermata dell’interfaccia utente]

## Barra delle query

[Schermata della barra delle query]

La barra delle query è il punto in cui puoi configurare i componenti desiderati che compongono un rapporto. Diversi tipi di analisi condividono diverse opzioni di query; se due tipi di analisi condividono opzioni di query, queste vengono trasferite quando si cambiano tipi di analisi. Consulta [Tipi di analisi](analysis-types/overview.md) per ulteriori informazioni sulle opzioni di query per ciascun tipo di analisi.

## Grafico

[Schermata del grafico]

Visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione visualizzata dipende dal tipo di visualizzazione sopra il grafico. I tipi di visualizzazione disponibili dipendono dal [Tipo di analisi](analysis-types/overview.md) sopra la barra delle query.

## Tabella

[Schermata della tabella]

Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Le colonne della tabella dipendono dal tipo di visualizzazione sopra il grafico. I tipi di visualizzazione disponibili dipendono dal [Tipo di analisi](analysis-types/overview.md) sopra la barra delle query.

## Impostazioni

[Schermata delle impostazioni]

Diverse opzioni sopra il grafico che consentono di personalizzare la modalità di restituzione dei dati da parte del grafico e della tabella.

* **Tipo di visualizzazione**: selettore a discesa che consente di presentare i dati per una determinata [Tipo di analisi](analysis-types/overview.md) in modo diverso. Ogni tipo di analisi dispone di almeno due tipi di vista.
* **Impostazioni grafico**: ottimizzare l’aspetto del grafico e gli eventi da utilizzare. Le opzioni disponibili dipendono dal tipo di vista selezionato.
* **Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date del rapporto. Alcuni tipi di analisi consentono anche intervalli, ad esempio giornalieri, settimanali o mensili.
* **Approfondimenti**: fornisce informazioni contestuali a seconda del rapporto visualizzato. Puoi mostrare o nascondere queste informazioni utilizzando l’icona della lampadina in alto a destra.

## Menu Progetto

[Schermata del menu del progetto]

Comandi in alto a destra del progetto che forniscono azioni generali.

* **Selettore visualizzazione dati**: modifica la visualizzazione dati utilizzata dal progetto. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.
* **Salva**: salva il progetto. Se salvi un nuovo progetto, viene visualizzata una finestra modale che richiede un nome e una descrizione.
* **Salva con nome**: salva il progetto separatamente dal progetto corrente, creando una copia. Viene visualizzata una finestra modale che richiede un nuovo nome e una nuova descrizione.
* **Apri in Workspace**: ricrea il progetto di analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante il lavoro sul progetto di analisi guidata. Utilizza questo comando quando l’analisi guidata non ti offre la flessibilità o le informazioni specifiche che stai cercando. Ad esempio, desideri un [Tendenze](analysis-types/trends.md) report che utilizza Sessioni per un segmento e Persone per un altro segmento.
* **Scarica PNG**: scarica l&#39;elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nell&#39;immagine.
* **Scarica SVG**: scarica l&#39;elemento grafico come `.svg`. La barra delle query e la tabella non sono incluse nell&#39;immagine.
