---
title: Panoramica dell’analisi guidata
description: Un metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di generare facilmente rapporti e informazioni.
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# Panoramica dell’analisi guidata

{{release-limited-testing}}

L’analisi guidata è un formato di reporting che consente ai team di prodotto di gestire autonomamente e rapidamente le esigenze di dati in modo da poter prendere decisioni sui prodotti più basate sui dati. I team cross-functional possono connettersi in tempo reale per utilizzare e comprendere questi rapporti.

Analogamente alle scorecard per dispositivi mobili e Analysis Workspace, un rapporto di analisi guidato utilizza dati provenienti da un [Visualizzazione dati](../data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite un [Connessione](../connections/overview.md). Tutti i rapporti creati nell’analisi guidata possono essere trasferiti facilmente ad Analysis Workspace per ulteriori ricerche.

I rapporti di analisi guidata presentano attualmente tre tipi di analisi: [Funnel](analysis-types/funnel.md), [Tendenze](analysis-types/trends.md), e [Crescita degli utenti](analysis-types/user-growth.md). Ciascuno di questi tipi di analisi dispone di più tipi di visualizzazione, che forniscono informazioni aggiuntive a ciascuno di questi rapporti.

## Provisioning

L’analisi guidata è un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se la tua organizzazione desidera iniziare a utilizzare questa funzione, contatta il team del tuo account Adobe.

## Interfaccia

L’interfaccia per l’analisi guidata, indipendentemente dal tipo di analisi, comprende i seguenti elementi principali dell’interfaccia utente:

1. **Barra delle query**: utilizza questa barra a sinistra per creare l’analisi.
1. **Grafico**: dopo aver selezionato gli eventi, le persone o i passaggi desiderati, a destra viene visualizzato un grafico che visualizza i dati.
1. **Tabella**: tabella sotto il grafico che mostra i numeri utilizzati nella visualizzazione.
1. **Impostazioni e informazioni**: diversi elementi dell’interfaccia utente sopra il grafico che consentono di personalizzare i dati restituiti.

[Schermata dell’interfaccia utente]

L&#39;analisi guidata contiene le seguenti parti dell&#39;interfaccia:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| [Schermata della barra delle query] | Barra delle query | Configura i componenti desiderati che compongono un rapporto. Diversi tipi di analisi condividono diverse opzioni di query; se due tipi di analisi condividono opzioni di query, queste vengono trasferite quando si cambiano tipi di analisi. Consulta [Tipi di analisi](analysis-types/overview.md) per ulteriori informazioni sulle opzioni di query per ciascun tipo di analisi. |
| [Schermata del grafico] | Grafico | Visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione visualizzata dipende dal tipo di visualizzazione sopra il grafico. I tipi di visualizzazione disponibili dipendono dal [Tipo di analisi](analysis-types/overview.md) sopra la barra delle query. |
| [Schermata della tabella] | Tabella | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Le colonne della tabella dipendono dal tipo di visualizzazione sopra il grafico. I tipi di visualizzazione disponibili dipendono dal [Tipo di analisi](analysis-types/overview.md) sopra la barra delle query. |
| [Schermata delle impostazioni] | Impostazioni | Diverse opzioni sopra il grafico che consentono di personalizzare la modalità di restituzione dei dati da parte del grafico e della tabella.<ul><li>**Tipo di visualizzazione**: selettore a discesa che consente di presentare i dati per una determinata [Tipo di analisi](analysis-types/overview.md) in modo diverso. Ogni tipo di analisi dispone di almeno due tipi di vista.</li><li>**Impostazioni grafico**: ottimizzare l’aspetto del grafico e gli eventi da utilizzare. Le opzioni disponibili dipendono dal tipo di vista selezionato.</li><li>**Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date del rapporto. Alcuni tipi di analisi consentono anche intervalli, ad esempio giornalieri, settimanali o mensili.</li><li>**Approfondimenti**: fornisce informazioni contestuali a seconda del rapporto visualizzato. Puoi mostrare o nascondere queste informazioni utilizzando l’icona della lampadina in alto a destra.</li></ul> |
| [Schermata del menu di analisi] | Menu Analisi | Comandi in alto a destra di Analisi guidata che forniscono azioni generali.<ul><li>**Selettore visualizzazione dati**: modifica la visualizzazione dati utilizzata dall’analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>**Salva**: salva l&#39;analisi. Se stai salvando una nuova analisi, viene visualizzata una finestra modale che richiede un nome e una descrizione.</li><li>**Salva con nome**: salva l&#39;analisi separatamente dall&#39;analisi corrente, creando una copia. Viene visualizzata una finestra modale che richiede un nuovo nome e una nuova descrizione.</li><li>**Apri in Workspace**: ricrea l’analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. Utilizza questo comando quando l’analisi guidata non offre la flessibilità o le informazioni specifiche che stai cercando. Ad esempio, desideri un [Tendenze](analysis-types/trends.md) report che utilizza Sessioni per un segmento e Persone per un altro segmento.</li><li>**Scarica PNG**: scarica l&#39;elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li><li>**Scarica SVG**: scarica l&#39;elemento grafico come `.svg`. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li></ul> |

{style="table-layout:auto"}

## Autorizzazioni

Adobe pianifica di fornire in futuro autorizzazioni specifiche per l’analisi guidata.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
