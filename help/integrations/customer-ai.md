---
description: Scopri come la funzione IA per l’analisi dei clienti di AEP si integra con Workspace in CJA.
title: Integrare IA per l’analisi dei clienti con CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 317e45146d493f969176bc026590fa894b4d7fb1
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 90%

---

# Integrare i dati di Customer AI con CJA

>[!NOTE]
>
>Questa funzionalità è attualmente disponibile [prova limitata](/help/release-notes/releases.md) e non generalmente disponibile.

[IA per l’analisi dei clienti](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=it), parte di Adobe Experience Platform Intelligent Services, offre agli esperti marketing la possibilità di generare previsioni sui clienti a livello individuale.

Con l’aiuto di fattori di influenza, IA per l’analisi dei clienti può dirti cosa potrebbe fare un cliente e perché. Inoltre, gli esperti marketing possono trarre vantaggio dalle previsioni e dalle informazioni di IA per l’analisi dei clienti per personalizzare le customer experience fornendo le offerte e i messaggi più appropriati.

IA per l’analisi dei clienti si basa su dati comportamentali individuali e dati di profilo per il punteggio di tendenza. IA per l’analisi dei clienti è flessibile in quanto può accogliere più origini di dati, tra cui Adobe Analytics, Adobe Audience Manager, dati di Consumer Experience Event e di Experience Event. Se utilizzi il connettore di origine di Experience Platform per inserire i dati di Adobe Audience Manager e Adobe Analytics, il modello raccoglie automaticamente i tipi di evento standard per addestrare e valutare il modello. Se inserisci un set di dati di Experience Event senza tipi di evento standard, tutti i campi pertinenti dovranno essere mappati come eventi personalizzati o attributi di profilo se desideri utilizzarlo nel modello. Questo può essere fatto nel passaggio di configurazione di IA per l’analisi dei clienti in Experience Platform. 

IA per l’analisi dei clienti si integra con Customer Journey Analytics (CJA) nella misura in cui i set di dati abilitati per IA per l’analisi dei clienti possono essere utilizzati nelle visualizzazioni dati e nella reportistica in CJA. Con questa integrazione, puoi:

* **Tracciare i punteggi di tendenza di un segmento di utenti nel tempo**. Esempio di utilizzo: Qual è la probabilità che un cliente dell&#39;hotel acquisti un biglietto per lo show presso la sede del concerto dell&#39;hotel?
* **Analizzare gli eventi di successo o gli attributi associati ai punteggi di tendenza**. Caso d’uso di esempio: voglio comprendere gli attributi o gli eventi di successo associati ai punteggi di tendenza.
* **Seguire il flusso di entrata della tendenza del cliente su diverse esecuzioni di punteggio**. Esempio di utilizzo: Vorrei capire le persone che inizialmente erano utenti a bassa propensione e, nel tempo, sono diventati utenti ad alta propensione. &#x200B;
* **Osservare la distribuzione della tendenza**. Caso di utilizzo: Vorrei capire la distribuzione dei punteggi di propensione a Posso essere più precisa con i miei segmenti. &#x200B;Esempio: un rivenditore desidera effettuare una promozione specifica di $ 50 di sconto su un prodotto. Potrebbe voler gestire solo una promozione molto limitata per questioni di budget, ecc. Analizza i dati e decide di eseguire il targeting solo dell’80%+ dei suoi clienti.
* **Osservare la tendenza a eseguire un’azione per una particolare coorte nel tempo**. Caso di utilizzo: Vorrei tenere traccia di una coorte specifica nel tempo. È simile al primo, ma è puoi traccia di una coorte specifica nel tempo. Esempio di ospitalità: un esperto marketing può tracciare il suo livello bronzo rispetto al suo livello argento, o il livello argento rispetto al livello oro nel tempo. In seguito, può osservare la tendenza di ogni coorte a prenotare l’hotel nel tempo. 

## Flusso di lavoro

Alcuni dei passaggi vengono eseguiti in Adobe Experience Platform prima di lavorare sull’output in CJA.

### Passaggio 1: configurare un’istanza di IA per l’analisi dei clienti

Dopo aver preparato i dati e aver impostato tutte le credenziali e gli schemi, inizia seguendo la guida [Configure a Customer AI Instance](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=it) (Configurare un’istanza di IA per l’analisi dei clienti) in Adobe Experience Platform.

### Passaggio 2: configurare una connessione CJA ai set di dati di IA per l’analisi dei clienti

In CJA, ora puoi [creare una o più connessioni](/help/connections/create-connection.md) ai set di dati di Experience Platform che sono stati instrumentati per IA per l’analisi dei clienti. Ogni previsione, ad esempio “Likelihood to upgrade account” (Probabilità di aggiornamento dell’account), equivale a un set di dati. Questi set di dati vengono visualizzati con il prefisso “Customer AI Scores in EE Format – name_of_application” (Punteggi di IA per l’analisi dei clienti in formato EE, name_of_application).

>[!IMPORTANT]
>
>Ogni istanza di IA per l’analisi dei clienti dispone di due set di dati di output se l’interruttore è attivato per l’abilitazione dei punteggi per CJA durante la configurazione del passaggio 1. Un set di dati di output viene visualizzato in formato XDM di Profilo e uno in formato XDM di Experience Event.

![Punteggi IA per l’analisi dei clienti](assets/cai-scores.png)

![Creare una connessione](assets/create-conn.png)

Di seguito è riportato un esempio di schema XDM che CJA inserirebbe come parte di un set di dati esistente o nuovo:

![Schema IA per l’analisi dei clienti](assets/cai-schema.png)

L’esempio è un set di dati di profilo; lo stesso set di oggetti di schema farebbe parte di un set di dati di Experience Event che CJA acquisirebbe. Il set di dati di Experience Event includerebbe marche temporali come la data di punteggio. Ogni cliente valutato in questo modello avrebbe un punteggio, una data di punteggio e altri dati a lui associati.

### Passaggio 3: creare visualizzazioni dati in base a queste connessioni

In CJA, ora puoi [creare visualizzazioni dati](/help/data-views/create-dataview.md) con le dimensioni (come punteggio, data del punteggio, probabilità e così via) e le metriche inserite come parte della connessione stabilita.

![Creare una visualizzazione dati](assets/create-dataview.png)

### Passaggio 4: rapporto sui punteggi di IA per l’analisi dei clienti in Workspace

In CJA Workspace, ora puoi creare un nuovo progetto e richiamare le visualizzazioni.

**Generare punteggi di tendenza**

Ecco un esempio di un progetto Workspace con i dati di IA per l’analisi dei clienti che genera un punteggio di tendenza per un segmento di utenti nel tempo, in un grafico a barre in pila:

![Contenitori di punteggio](assets/workspace-scores.png)

**Tabella con codici motivo**

Ecco una tabella che mostra i codici del motivo per cui un segmento ha una tendenza alta o bassa:

![Codici motivo](assets/reason-codes.png)

**Flusso di ingresso della tendenza del cliente**

Questo diagramma di flusso mostra il flusso di ingresso della tendenza del cliente su diverse esecuzioni di punteggio:

![Flusso di ingresso](assets/flow.png)

**Distribuzione dei punteggi di tendenza**

Questo grafico a barre mostra la distribuzione dei punteggi di tendenza:

![Distribuzione](assets/distribution.png)

**Sovrapposizioni delle tendenze**

Questo diagramma di Venn mostra la sovrapposizione delle tendenze su diverse esecuzioni di punteggio:

![Sovrapposizioni delle tendenze](assets/venn.png)
