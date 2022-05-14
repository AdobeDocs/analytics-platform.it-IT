---
description: Scopri in che modo AEP Attribution AI si integra con Workspace in CJA.
title: Integrare Attribution AI con CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: e75836841cdaf8acd2408723111f13048d31505d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 5%

---

# Integrare Attribution AI con CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), parte di Adobe Experience Platform Intelligent Services, è un servizio di attribuzione algoritmica multicanale che calcola l’influenza e l’impatto incrementale delle interazioni dei clienti rispetto a risultati specifici. Con Attribution AI, gli addetti al marketing possono misurare e ottimizzare le spese di marketing e pubblicitarie comprendendo l’impatto di ogni singola interazione con i clienti in ogni fase dei percorsi dei clienti.

Attribution AI supporta due categorie di punteggi: algoritmico e basato su regole. I punteggi algoritmici includono punteggi incrementali e influenzati. I punteggi basati su regole includono Primo contatto, Ultimo contatto, Lineare, A forma di U e Decadimento nel tempo.

Attribution AI si integra con Customer Journey Analytics (CJA) nella misura in cui Attribution AI esegue i modelli rispetto ai dati e CJA importa l’output di tali modelli come set di dati, che può quindi essere integrato con il resto dei set di dati CJA. I set di dati abilitati per Attribution AI possono quindi essere utilizzati nelle visualizzazioni dati e nei rapporti in CJA.

Attribution AI supporta 3 schemi di Experience Platform: Evento esperienza, Adobe Analytics ed evento esperienza di consumo.

## Flusso di lavoro

Alcuni dei passaggi vengono eseguiti in Adobe Experience Platform prima di lavorare con l’output in CJA.

### Scaricare i punteggi delle Attribution AI

1. Ad Experience Platform, scarica i punteggi delle Attribution AI come descritto [qui](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).
1. Ad Experience Platform, crea un’istanza Attribution AI selezionando e mappando i dati, definendo gli eventi e addestrando i dati, come descritto [qui](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).
1. In CJA,

## Differenze tra Attribution AI e Attribution IQ

Quindi quando utilizzare i dati di Attribution AI rispetto a [Attribution IQ](/help/analysis-workspace/attribution/overview.md), una funzionalità CJA nativa? Questa tabella mostra alcune delle differenze di funzionalità:

| Funzionalità | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Attribuzione frazionale | Sì | No |
| Consente agli utenti di regolare il modello | No | Sì |
| Attribuzione tra canali diversi (Nota: AAI non utilizza gli stessi dati uniti utilizzati da CJA.) | Sì | Sì |
| Include punteggi incrementali e influenzati | Sì | No |
| Modellazione ML | Sì | Sì |
| Modellazione ML con previsioni | Sì | No |

{style=&quot;table-layout:auto&quot;}
