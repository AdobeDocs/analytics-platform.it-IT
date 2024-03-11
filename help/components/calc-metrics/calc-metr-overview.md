---
title: Panoramica delle metriche calcolate
description: Scopri le metriche filtrate derivate in fase di esecuzione dei rapporti.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '461'
ht-degree: 100%

---

# Panoramica delle metriche calcolate

Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti. I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover cambiare l’implementazione.

È possibile eseguire le seguenti azioni:

* Creare metriche filtrate derivate in fase di esecuzione dei rapporti, senza dover modificare l’implementazione. Queste possono essere visualizzate storicamente poiché sono basate su filtri.
* Applicare filtri alle metriche (solo per metriche calcolate avanzate). Ad esempio, puoi creare una metrica per “Nuove persone”, conteggiando le persone per le quali questa è la prima sessione.
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
| Generatore di metrica calcolata | <ul><li>Creare metriche calcolate e calcolate avanzate utilizzando modelli di allocazione avanzati.</li><li>Aggiungere filtri inline alle formule delle metriche.</li><li>Confrontare i filtri nello stesso rapporto. Ad esempio, confrontare le persone locali con quelle internazionali.</li><li>Utilizzare le funzioni statistiche.</li><li> Fornire descrizioni dettagliate delle metriche (mostrare cosa fanno, dove usarle, dove NON usarle).</li><li>Copiare le definizioni in nuove metriche.</li><li>Fornire un’anteprima delle metriche inline.</li><li>Impostare la polarità della metrica, che indica se è positivo o negativo se un dato evento personalizzato (metrica) aumenta.</li><li>Applicare tag alle metriche.</li></ul> |
| Gestore metriche calcolate | <ul><li>Condividere le metriche con altri utenti.</li><li>Approvare e curare le metriche.</li><li>Organizzare le metriche (assegnare tag) in modo che gli utenti possano trovarle.</li><li>Eliminare le metriche.</li><li>Rinominare le metriche.</li></ul> |
| API per metriche calcolate | Parte del set di API di Customer Journey Analytics. |

## Modelli di metriche calcolate in Customer Journey Analytics

| Nome della metrica calcolata | Descrizione della metrica calcolata |
| --- | --- |
| Sessions Per Person (Sessioni per persona) | Numero medio di sessioni per persona |
| Session Start Rate (Frequenza di inizio sessione) | La percentuale di tempo in cui si è verificato un elemento della dimensione nel primo evento di una sessione. |
| Session End Rate (Frequenza di fine sessione) | La percentuale di tempo in cui si è verificato un elemento della dimensione nell’ultimo evento di una sessione. |
| Time Spent per Person (Tempo trascorso per persona) | Il tempo medio trascorso da una persona per un dato elemento della dimensione. |
| Time Spent Per Session (Tempo trascorso per sessione) | Il tempo medio trascorso da una persona in una sessione per un dato elemento della dimensione. |
