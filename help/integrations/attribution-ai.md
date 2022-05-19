---
description: Scopri in che modo AEP Attribution AI si integra con Workspace in CJA.
title: Integrare Attribution AI con CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 5d22437ec6514196146283af311b6661c1f2e45b
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 3%

---

# Integrare Attribution AI con CJA

>[!NOTE]
>
>Questa funzionalità verrà rilasciata il 25 maggio 2022.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), parte di Adobe Experience Platform Intelligent Services, è un servizio di attribuzione algoritmica multicanale che calcola l’influenza e l’impatto incrementale delle interazioni dei clienti rispetto a risultati specifici. Con Attribution AI, gli addetti al marketing possono misurare e ottimizzare le spese di marketing e pubblicitarie comprendendo l’impatto di ogni singola interazione con i clienti in ogni fase dei percorsi dei clienti.

Attribution AI supporta due categorie di punteggi: algoritmico e basato su regole. I punteggi algoritmici includono punteggi incrementali e influenzati.

* **Punteggi influenzati** divide il 100% del credito di conversione tra i canali di marketing.
* **Punteggi incrementali** per prima cosa, prendi in considerazione una linea di base di conversione che avresti ottenuto anche senza il marketing. Questa linea di base dipende dalle osservazioni AI di pattern, stagionalità e così via, dovute al riconoscimento del marchio esistente, alla lealtà e al passaparola. Il credito rimanente è suddiviso tra i canali di marketing.

I punteggi basati su regole includono [!UICONTROL First touch], [!UICONTROL Last touch], [!UICONTROL Linear], [!UICONTROL U-shaped]e [!UICONTROL Time-Decay]. Attribution AI supporta 3 schemi di Experience Platform: Evento esperienza, Adobe Analytics ed evento esperienza di consumo.

Attribution AI si integra con Customer Journey Analytics (CJA) nella misura in cui Attribution AI esegue i modelli rispetto ai dati e CJA importa l’output di tali modelli come set di dati, che può quindi essere integrato con il resto dei set di dati CJA. I set di dati abilitati per Attribution AI possono quindi essere utilizzati nelle visualizzazioni dati e nei rapporti in CJA.

## Flusso di lavoro

Alcuni dei passaggi vengono eseguiti in Adobe Experience Platform prima di lavorare con l’output in CJA. L’output è costituito da un set di dati con un modello di Attribution AI applicato.

### Passaggio 1: Creare un’istanza di Attribution AI

Ad Experience Platform, crea un’istanza Attribution AI selezionando e mappando i dati, definendo gli eventi e addestrando i dati, come descritto [qui](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Passaggio 2: Configurare una connessione CJA ai set di dati di Attribution AI

In CJA, ora puoi [creare una o più connessioni](/help/connections/create-connection.md) Experience Platform di set di dati che sono stati strumentalizzati per Attribution AI. Questi set di dati vengono visualizzati con il prefisso &quot;Punteggi Attribution AI&quot;, come mostrato di seguito:

![Punteggi di AAI](assets/aai-scores.png)

### Passaggio 3: Crea visualizzazioni dati in base a queste connessioni

In CJA, [creare una o più visualizzazioni dati](/help/data-views/create-dataview.md) che contengono i campi XDM di Attribution AI. (Sarebbe fantastico avere uno screenshot qui.)

### Passaggio 4: Report sui dati AAI in CJA Workspace

In un progetto di CJA Workspace, puoi inserire metriche quali &quot;Ordini AAI&quot; e dimensioni quali, ad esempio, &quot;Nome campagna AAI&quot; o &quot;Canale marketing AAI&quot;.

![Dimensioni AAI](assets/aai-dims.png)

Qui vediamo un progetto Workspace con dati AAI che mostra gli ordini con punteggi influenzati e incrementali.

![Progetto AAI](assets/aai-project.png)

![Progetto AAI](assets/aai-project2.png)


## Differenze tra Attribution AI e Attribution IQ

Quindi quando utilizzare i dati di Attribution AI rispetto a [Attribution IQ](/help/analysis-workspace/attribution/overview.md), una funzionalità CJA nativa? Questa tabella mostra alcune delle differenze di funzionalità:

| Funzionalità | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Attribuzione frazionale | Sì | No |
| Consente agli utenti di regolare il modello | Sì | Sì |
| Attribuzione tra canali diversi (Nota: AAI non utilizza gli stessi dati uniti utilizzati da CJA.) | Sì | Sì |
| Include punteggi incrementali e influenzati | Sì | No |
| Modellazione ML | Sì | Sì |
| Modellazione ML con previsioni | Sì | No |

{style=&quot;table-layout:auto&quot;}
