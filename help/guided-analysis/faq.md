---
title: Domande frequenti sull’analisi guidata
description: Domande frequenti sull’analisi guidata.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: analisi dei prodotti
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Domande frequenti sull’analisi guidata

Domande frequenti sull’analisi guidata.

+++**Come posso effettuare il provisioning della mia organizzazione per l’analisi guidata?**

L’analisi guidata è un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se desideri iniziare a utilizzare questo componente aggiuntivo, contatta il team del tuo account di Adobe.

+++

+++**Quali modifiche di implementazione sono necessarie per utilizzare l’analisi guidata?**

Se utilizzi già oggi il Customer Journey Analytics, non sono necessarie ulteriori modifiche all’implementazione. L’analisi guidata utilizza lo stesso [Visualizzazioni dati](../data-views/data-views.md) e [Connessioni](../connections/overview.md) come altre interfacce CJA [Analysis Workspace](../analysis-workspace/home.md).

Per consentire agli utenti finali di ottenere il massimo successo con l’analisi guidata, è consigliabile disporre di uno schema degli eventi e di una strategia di gestione affidabili in Adobe Experience Platform e [Visualizzazioni dati](../data-views/data-views.md).

+++

+++**Quando utilizzare Analisi guidata o Analysis Workspace?**

**Analisi guidata** può aiutare gli utenti a ottenere rapidamente informazioni di alta qualità. È utile per i team di prodotto, per gli utenti che desiderano lavorare in modo più affidabile con i dati e anche per gli analisti come punto di partenza per analisi più approfondite.

**[Analysis Workspace](../analysis-workspace/home.md)** è uno spazio a forma libera più ampio che consente di immergerti ulteriormente nei dati per scoprire ulteriori informazioni. È utile per gli analisti e gli utenti esperti che comprendono bene i dati e desiderano approfondirli.

+++

+++**Come si confronta la terminologia tra analisi guidata e Analysis Workspace?**

L’analisi guidata utilizza termini utilizzati più frequentemente tra i team di prodotto. Potete fare riferimento a questa tabella quando passate da un&#39;analisi guidata a un&#39;altra [Analysis Workspace](../analysis-workspace/home.md).

| Termine di analisi guidata | Termine Analysis Workspace |
| --- | --- |
| Evento | Metrica |
| Utenti | Persone |
| Proprietà | Dimensione |
| Valore | Elemento Dimension |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**Quali sono alcune differenze nell’analisi guidata e nell’approccio di reporting di Analysis Workspace?**

Mentre [Analysis Workspace](../analysis-workspace/home.md) e l&#39;analisi guidata utilizza gli stessi dati sottostanti, il modo in cui ogni strumento consente di creare query di tali dati è diverso.

* **Analysis Workspace è un’esperienza incentrata sulle dimensioni.** Le tabelle sono in genere costituite da righe dimensionali, mentre le colonne sono in genere metriche. I filtri possono essere applicati sia nelle righe che nelle colonne per ottenere i dati desiderati.

* **L’analisi guidata è un’esperienza incentrata sugli eventi.** Ogni analisi inizia selezionando gli eventi, quindi è possibile aggiungere dimensioni e filtri per perfezionare i dati dell’evento.

![Visualizzazioni di analisi guidata e Analysis Workspace](assets/structure.png)

Prendi in considerazione l’esempio seguente in cui ti concentri sui dati intorno alla pagina principale del tuo sito web. I team pongono domande simili, ma l’approccio di analisi può essere diverso.

* Un tipico approccio Analysis Workspace incentrato sulle dimensioni consiste nel &quot;Esaminiamo la home page e vediamo quante visualizzazioni di pagina ha ricevuto&quot;.

  ![Dimension centrato](assets/dimension-centered.png)

* Un tipico approccio di analisi guidata incentrata sugli eventi sarebbe: &quot;Quanti utenti hanno visualizzato la home page?&quot;

  ![Evento centrato](assets/event-centered.png)

+++
