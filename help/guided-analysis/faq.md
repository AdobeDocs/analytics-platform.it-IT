---
title: Domande frequenti sull’analisi guidata
description: Domande frequenti sull’analisi guidata.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
TQID: https://experienceleague.adobe.com/4fwNjSWPcLFNewlSHjxJq6MVWQY1Lc0-CpSomNkU69M
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 443
ht-degree: 89%

---

# Domande frequenti sull’analisi guidata

Domande frequenti sull’analisi guidata.

+++**La mia organizzazione ha accesso all’analisi guidata?**

Le visualizzazioni di analisi guidata sono incluse in tutti i pacchetti di Customer Journey Analytics. Per ulteriori informazioni sulle visualizzazioni sbloccate dal pacchetto CJA, consulta la sezione [provisioning](overview.md#provisioning) nella pagina della panoramica.

+++

+++**Quali modifiche di implementazione sono necessarie per utilizzare l’analisi guidata?**

Se già utilizzi Customer Journey Analytics, non sono necessarie ulteriori modifiche all’implementazione. L’analisi guidata utilizza le stesse [Visualizzazioni dati](../data-views/data-views.md) e [Connessioni](../connections/overview.md) di altre interfacce CJA come [Analysis Workspace](../analysis-workspace/home.md).

Per consentire agli utenti finali di utilizzare al meglio l’analisi guidata, è consigliabile mettere in atto uno schema degli eventi e di una strategia di gestione affidabili in Adobe Experience Platform e nelle [Visualizzazioni dati](../data-views/data-views.md).

+++

+++**Quando utilizzare l’analisi guidata o Analysis Workspace?**

L’**analisi guidata** può aiutare gli utenti a ottenere rapidamente informazioni approfondite di alta qualità. È utile per i team di prodotto, per gli utenti che desiderano lavorare in modo più affidabile con i dati e anche per gli analisti come punto di partenza per analisi più approfondite.

**[Analysis Workspace](../analysis-workspace/home.md)** è uno spazio a forma libera più ampio che consente di approfondire ulteriormente i dati per scoprire ulteriori informazioni. È utile per gli analisti e gli utenti esperti che hanno una buona comprensione dei dati e desiderano approfondirli.

+++

+++**Come si  confronta la terminologia tra l’analisi guidata e Analysis Workspace?**

L’analisi guidata e [Analysis Workspace](../analysis-workspace/home.md) si allineano alla maggior parte della terminologia chiave, con alcune piccole differenze.

| Termine di analisi guidata | Termine di Analysis Workspace |
| --- | --- |
| Evento (metrica binaria 1/0) | Metrica |
| Utenti | Persone |
| Dimensione | Dimensione |
| Elemento dimensione | Elemento dimensione |
| Segmento | Segmento |
| Filtro | Filtro rapporto |
| Metriche calcolate, metriche | Metrica calcolata |

{style="table-layout:auto"}

+++

+++**Quali sono le differenze nell’approccio di reporting tra l’analisi guidata e Analysis Workspace?**

Sebbene [Analysis Workspace](../analysis-workspace/home.md) e l’analisi guidata utilizzino gli stessi dati sottostanti, il modo in cui ciascuno strumento consente di creare query di tali dati è diverso.

* **Analysis Workspace è un&#39;esperienza incentrata sulle dimensioni.** Le tabelle sono in genere costituite da righe dimensionali, mentre le colonne sono in genere metriche. I segmenti possono essere applicati sia nelle righe che nelle colonne per ottenere i dati desiderati.

* **L&#39;analisi guidata è un evento e un&#39;esperienza incentrata sull&#39;utente.** Ogni analisi inizia selezionando gli eventi, quindi è possibile aggiungere dimensioni e segmenti per perfezionare i dati dell’evento.

![Visualizzazioni di analisi guidata e Analysis Workspace](assets/structure.png){style="border:1px solid gray"}

Prendi in considerazione l’esempio seguente in cui puoi concentrarti sui dati relativi alla pagina Home del tuo sito web. I team pongono domande simili, ma l’approccio di analisi può essere diverso.

* Un tipico approccio di Analysis Workspace incentrato sulle dimensioni consisterebbe nell’esaminare la home page e vedere quante visualizzazioni di pagina ha ricevuto.

  ![Approccio incentrato sulle dimensioni](assets/dimension-centered.png){style="border:1px solid gray"}

* Un tipico approccio di analisi guidata incentrato sull’evento e sull’utente consisterebbe nell’esaminare quanti utenti hanno visitato la pagina Home

  ![Approccio incentrato sull’evento](assets/event-centered.png){style="border:1px solid gray"}

+++
