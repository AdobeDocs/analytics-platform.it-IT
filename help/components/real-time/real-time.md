---
description: Comprendere le funzionalità di reporting in tempo reale in Customer Journey Analytics.
title: Panoramica reportistica in tempo reale
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
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

* I casi d’uso rilevanti ma meno importanti per la generazione di rapporti in tempo reale sono casi d’uso di convalida.
Desideri convalidare, ad esempio:

   * Il percorso della campagna che hai lanciato di recente funziona davvero?
   * Quando la nuova pagina di prodotto viene pubblicata, raccogli i dati dei clienti dalla pagina?
   * Il tuo evento multimediale in diretta va bene?

Non considerare la generazione di rapporti in tempo reale per i casi di utilizzo relativi al monitoraggio delle operazioni. Ad esempio, per rispondere alla domanda se un sito funziona correttamente. Poiché l&#39;[aggiornamento in tempo reale](use-real-time.md) viene disattivato automaticamente dopo 30 minuti e il report in tempo reale non viene più aggiornato, non utilizzare un report in tempo reale come origine affidabile per questi casi d&#39;uso.


## Definizione

L’aspetto in tempo reale del reporting in tempo reale per Customer Journey Analytics è definito come dati e visualizzazioni aggiornati entro circa 6,5 minuti dal momento in cui i dati sottostanti vengono acquisiti tramite la connessione associata.

Diversi componenti nella configurazione della raccolta dati determinano la latenza di reporting in tempo reale.

![Reporting in tempo reale](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Descrizione | Latenza |
|:---:|---|--:|
| 1 | Dati raccolti tramite SDK/API di Edge Network in Edge Network. | &lt; 500 millisecondi |
| 2 | Dati replicati da Edge Network al servizio di raccolta e convalida dei dati nell’hub Experience Platform. | &lt; 5 minuti |
| 3 | Dati raccolti tramite connettori di streaming nel servizio di raccolta e convalida dei dati nell’hub Experience Platform. | &lt; 15 minuti |
| 4 | Dati raccolti tramite Adobe Analytics e inoltrati dal connettore di origine di Analytics al processore dei connettori di origine nell’hub Experience Platform. | &lt; 15 minuti |
| 5 | Dati raccolti tramite altri connettori sorgente nel processore dei connettori sorgente in Experience Platform Hub. | &lt; 24 ore |
| 6 | Dati elaborati dal processore in tempo reale per un set di dati consolidato per il reporting in tempo reale. | &lt; 90 secondi |

## Limitazioni

Tieni presente le seguenti limitazioni per la generazione di rapporti in tempo reale:

* La generazione rapporti in tempo reale segnala solo i dati disponibili in un periodo continuo di 24 ore. I dati che attraversano questo periodo continuo di 24 ore sono nascosti per il reporting in tempo reale. Quando l&#39;[aggiornamento in tempo reale](use-real-time.md) per un report viene disattivato o disattivato automaticamente, tutti i dati rilevanti per un report sono nuovamente disponibili.
* Attribuzione, segmentazione, metriche calcolate e altro ancora funzionano solo sui dati disponibili entro il periodo continuo di 24 ore.
* Il reporting in tempo reale funziona meglio sui dati a livello di evento e di sessione ed è necessario prestare attenzione quando si utilizza il reporting in tempo reale per i dati a livello di persona. <!--Need to explain this a bit better --> Poiché solo gli eventi del periodo continuo di 24 ore sono disponibili per i report in tempo reale, anche la cronologia degli eventi di una persona è limitata a questa finestra. Quando selezioni una dimensione e metriche (calcolate), considera la preferenza per i dati a livello di evento e di sessione. E quando utilizzi funzionalità quali raggruppamenti, successivo o precedente e altro nel pannello con aggiornamento in tempo reale abilitato.
* Non è possibile combinare l’unione con il reporting in tempo reale. <!-- Do we need to explain this in more detail, why? --> Il reporting in tempo reale riguarda i dati a livello di evento e di sessione ed è meno rilevante per i dati basati su persona.
* Non sono disponibili metriche per elementi multimediali raccolti con heartbeat, ad eccezione delle metriche di avvio e chiusura dei contenuti multimediali. Pertanto, puoi comunque utilizzare la reportistica in tempo reale per abilitare un caso d’uso dei contenuti multimediali.
* Quando utilizzi le [opzioni di download o esportazione](/help/analysis-workspace/export/download-send.md) per scaricare un progetto o esportare dati da una tabella a forma libera, considera quanto segue:
   * Un progetto CSV scaricato o un file CSV esportato contiene i dati in tempo reale disponibili al momento del download o dell’esportazione.
   * Un progetto PDF scaricato contiene dati non in tempo reale, simili a quelli visualizzati quando l’aggiornamento in tempo reale è disattivato.
