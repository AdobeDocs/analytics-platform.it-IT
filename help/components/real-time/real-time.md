---
description: Comprendere le funzionalità di reporting in tempo reale in Customer Journey Analytics.
title: Panoramica reportistica in tempo reale
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---


# Panoramica reportistica in tempo reale

Il reporting in tempo reale in Customer Journey Analytics mostra e aggiorna dati e visualizzazioni in uno o più pannelli in Analysis Workspace in tempo reale.

{{release-limited-testing}}

{{ultimate-package}}

## Casi d’uso

Questa sezione fornisce una panoramica dei casi d’uso tipici di valore e meno preziosi. E anche informazioni su quando non considerare la generazione di rapporti in tempo reale.

* I casi d’uso più importanti per la generazione di rapporti in tempo reale riguardano vendite, promozioni o lanci di prodotti importanti.
Come parte di quel lancio, vuoi sapere:

   * Qual è il rapporto tra le vendite e l&#39;ultima vendita?
   * Quali sono le differenze tra il lancio di questo prodotto e quello dell&#39;ultimo?
   * Le tue promozioni per questo giorno importante o evento funzionano davvero?

* I casi d’uso rilevanti ma meno importanti per la generazione di rapporti in tempo reale sono i casi d’uso di convalida.
Desideri convalidare, ad esempio:

   * Il percorso della campagna, che hai lanciato di recente, sta funzionando?
   * La nuova pagina di prodotto è stata pubblicata e stai raccogliendo i dati dei clienti dalla pagina?
   * Il tuo evento multimediale in diretta va bene?

Non considerare la generazione di rapporti in tempo reale per i casi di utilizzo relativi al monitoraggio delle operazioni. Ad esempio, per rispondere alla domanda se il sito funziona effettivamente?


## Definizione

L’aspetto in tempo reale del reporting in tempo reale per Customer Journey Analytics è definito come dati e visualizzazioni che vengono aggiornati entro circa 5 minuti dal momento in cui i dati sottostanti vengono acquisiti tramite la connessione associata.

## Limitazioni

Tieni presente le seguenti limitazioni per la generazione di rapporti in tempo reale:

* La generazione rapporti in tempo reale segnala solo i dati disponibili in un periodo continuo di 24 ore. I dati che attraversano questo periodo continuo di 24 ore non sono disponibili.
* Attribuzione, segmentazione, metriche calcolate e altro ancora funzionano solo sui dati disponibili entro il periodo continuo di 24 ore.
* Il reporting in tempo reale funziona meglio sui dati a livello di evento e di sessione ed è necessario prestare attenzione all’utilizzo del reporting in tempo reale per i dati a livello di persona. <!--Need to explain this a bit better --> Quando si selezionano le metriche delle dimensioni (calcolate), prendere in considerazione la preferenza per i dati a livello di evento e di sessione. E quando utilizzi funzionalità quali raggruppamenti, successivi o precedenti e altro nel pannello con aggiornamento in tempo reale abilitato.
* Non è possibile combinare l’unione con il reporting in tempo reale. <!-- Do we need to explain this in more detail, why? --> Come accennato in precedenza, il reporting in tempo reale riguarda i dati a livello di evento e di sessione e non tanto i dati basati su persone.
* Non sono disponibili metriche per elementi multimediali raccolti con heartbeat, ad eccezione delle metriche di avvio e chiusura dei contenuti multimediali. In questo modo puoi comunque utilizzare la reportistica in tempo reale per abilitare un caso di utilizzo dei contenuti multimediali.
