---
title: Domande frequenti sull’analisi guidata
description: Domande frequenti per l’analisi guidata.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: df00d954de5db89f0ccc40f7eb2474523d9e774e
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 71%

---

# Domande frequenti sull’analisi guidata

Domande frequenti per l’analisi guidata.

+++**La mia organizzazione ha accesso all&#39;analisi guidata?**

Le viste di analisi guidate sono incluse in tutti i pacchetti di Customer Journey Analytics. Per ulteriori informazioni sulle visualizzazioni sbloccate dal pacchetto CJA, consulta la sezione [provisioning](overview.md#provisioning) nella pagina della panoramica.

+++

+++**Quali modifiche di implementazione sono necessarie per utilizzare l’analisi guidata?**

Se già utilizzi Customer Journey Analytics, non sono necessarie ulteriori modifiche all’implementazione. L’analisi guidata utilizza le stesse [Visualizzazioni dati](../data-views/data-views.md) e [Connessioni](../connections/overview.md) di altre interfacce CJA come [Analysis Workspace](../analysis-workspace/home.md).

Per consentire agli utenti finali di avere il maggior successo nell&#39;analisi guidata, è consigliabile disporre di uno schema eventi e di una strategia di gestione affidabili in Adobe Experience Platform e [Visualizzazioni dati](../data-views/data-views.md).

+++

+++**Quando utilizzare l’analisi guidata o Analysis Workspace?**

L’**analisi guidata** può aiutare gli utenti a ottenere rapidamente informazioni approfondite di alta qualità. È utile per i team di prodotto, per gli utenti che desiderano lavorare in modo più affidabile con i dati e anche per gli analisti come punto di partenza per analisi più approfondite.

**[Analysis Workspace](../analysis-workspace/home.md)** è uno spazio a forma libera più ampio che consente di approfondire ulteriormente i dati per scoprire ulteriori informazioni. È utile per gli analisti e gli utenti esperti che hanno una buona comprensione dei dati e desiderano approfondirli.

+++

+++**Come si confronta la terminologia tra analisi guidata e Analysis Workspace?**

L’analisi guidata si serve di termini utilizzati più frequentemente tra i team di prodotto. È possibile fare riferimento a questa tabella quando si passa da analisi guidata ad [Analysis Workspace](../analysis-workspace/home.md).

| Termine di analisi guidata | Termine di Analysis Workspace |
| --- | --- |
| Evento | Metrica |
| Utenti | Persone |
| Proprietà | Dimensione |
| Valore | Elemento dimensione |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**Quali sono alcune differenze nell&#39;analisi guidata e nel reporting dell&#39;approccio di Analysis Workspace?**

Sebbene [Analysis Workspace](../analysis-workspace/home.md) e l’analisi guidata utilizzino gli stessi dati sottostanti, il modo in cui ciascuno strumento consente di creare query di tali dati è diverso.

* **Analysis Workspace è un’esperienza incentrata sulle dimensioni.** Generalmente, le tabelle sono costituite da righe dimensionali, mentre le colonne da metriche. I filtri possono essere applicati sia nelle righe che nelle colonne per ottenere i dati desiderati.

* **L’analisi guidata è un evento e un’esperienza incentrata sull’utente.** Ogni analisi inizia selezionando gli eventi, quindi è possibile aggiungere dimensioni e filtri per perfezionare i relativi dati.

![Visualizzazioni di analisi guidata e Analysis Workspace](assets/structure.png){style="border:1px solid gray"}

Prendi in considerazione l’esempio seguente in cui puoi concentrarti sui dati relativi alla pagina Home del tuo sito web. I team pongono domande simili, ma l’approccio di analisi può essere diverso.

* Un tipico approccio di Analysis Workspace incentrato sulle dimensioni consisterebbe nell’esaminare la home page e vedere quante visualizzazioni di pagina ha ricevuto.

  ![Approccio incentrato sulle dimensioni](assets/dimension-centered.png){style="border:1px solid gray"}

* Un tipico evento e un approccio di analisi guidata incentrato sull’utente sarebbero: &quot;Quanti utenti hanno visitato la home page?&quot;

  ![Approccio incentrato sull’evento](assets/event-centered.png){style="border:1px solid gray"}

+++
