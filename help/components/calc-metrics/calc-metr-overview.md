---
title: Panoramica sulle metriche calcolate
description: 'Scopri '
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 94%

---


# Panoramica sulle metriche calcolate

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti. I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover cambiare l’implementazione [!DNL Analytics].

È possibile

* Creare metriche filtrate derivate in fase di esecuzione dei rapporti, [senza dover modificare l’implementazione](https://youtu.be/CuQTm9RaUpY). Queste possono essere visualizzate storicamente poiché sono basate su filtri.
* Condividere le metriche tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.
* Applicare filtri alle metriche (solo per metriche calcolate avanzate). Ad esempio, puoi creare una metrica per “Nuovi visitatori”, conteggiando le persone per cui questa è la prima sessione.
* Incorporare funzioni statistiche per descrivere meglio i dati (solo per metriche calcolate avanzate). Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.

## Metriche calcolate e metriche calcolate avanzate

Ecco un confronto tra le funzionalità delle metriche calcolate e delle metriche calcolate avanzate:

| Opzioni di generazione | Metriche calcolate | Metriche calcolate avanzate (derivate) |
|---|---|---|
| Tipi di formato (decimale, ora, percentuale, valuta) | Sì | Sì |
| Modifiche dell’attribuzione (predefinita, lineare, di partecipazione, ecc.) | Sì | Sì |
| Tipi di metriche (standard, totale) | Sì | Sì |
| Operatori di base (aggiungere, sottrarre, moltiplicare, dividere) | Sì | Sì |
| Applicazione di filtri | No | Sì |
| [Funzioni di base (conteggio, valore assoluto, media, ecc.)](/help/components/calc-metrics/cm-functions.md) | No | Sì |
| [Funzioni avanzate (regressione, if/then, t-score, ecc.)](/help/components/calc-metrics/cm-adv-functions.md) | No | Sì |

## Strumenti

| Strumento | Funzionalità |
|--- |--- |
| Generatore di metrica calcolata | <ul><li>Creare metriche calcolate e calcolate avanzate utilizzando modelli di allocazione avanzati.</li><li>Aggiungere filtri inline alle formule delle metriche.</li><li>Confrontare i filtri nello stesso rapporto. Ad esempio, confrontare i visitatori locali con quelli internazionali.</li><li>Utilizzare le funzioni statistiche.</li><li> Fornire descrizioni dettagliate delle metriche (mostrare cosa fanno, dove usarle, dove NON usarle).</li><li>Copiare le definizioni in nuove metriche.</li><li>Fornire un’anteprima delle metriche inline.</li><li>Impostare la polarità della metrica, che indica se è positivo o negativo se un dato evento personalizzato (metrica) aumenta.</li><li>Applicare tag alle metriche.</li></ul> |
| Gestore metriche calcolate | <ul><li>Condividere le metriche con altri utenti.</li><li>Approvare e curare le metriche.</li><li>Organizzare le metriche (assegnare tag) in modo che gli utenti possano trovarle.</li><li>Eliminare le metriche.</li><li>Rinominare le metriche.</li></ul> |
| API per metriche calcolate | Parte del set di API di Adobe Analytics 2.0. |

