---
description: Domande frequenti su Workspace e suggerimenti per la risoluzione dei problemi.
title: Domande frequenti
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 84%

---

# Domande frequenti

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

| Domanda | Risposta |
|--- |--- |
| **Quali sono i prerequisiti per utilizzare Analysis Workspace?** | L&#39;utilizzo di Analysis Workspace richiede un&#39;implementazione del Customer Journey Analytics di lavoro. Assicurati che la tua organizzazione invii dati a Adobe Experience Platform prima di utilizzare lo strumento. |
| **Quali sono i requisiti di amministrazione e di accesso per Analysis Workspace?** | Consulta [Requisiti di amministrazione](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **L’utilizzo di Analysis Workspace influisce sulla raccolta dei dati?** | Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili. Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]* nel menu in alto a sinistra. |
| **Come si implementa Analysis Workspace?** | Non è richiesta alcuna implementazione particolare. Analysis Workspace è disponibile per tutti i Customer Journey Analytics aziendali. Tuttavia, si applicano le autorizzazioni standard per i contenuti (come i componenti del progetto) e per la cura e la condivisione di progetti. Consulta [Amministrazione e requisiti di accesso](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Come si ottimizzano le prestazioni di Analysis Workspace?** | Vedi [Ottimizzazione delle prestazioni](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Risoluzione dei problemi

**Quando trascino una metrica, visualizzo un messaggio indicante che i dati non sono validi.**

Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra.

**Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri.**

Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:

* Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.
* Vai al tuo sito web e utilizza il [Debugger](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html) per convalidare i dati raccolti.
