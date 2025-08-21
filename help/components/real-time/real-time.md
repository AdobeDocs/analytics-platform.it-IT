---
description: Comprendere le funzionalità di reporting in tempo reale in Customer Journey Analytics.
title: Panoramica reportistica in tempo reale
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: 2461804f788b7a1417c4d7faa1d7133d8808cad5
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 4%

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

## Come funziona

Il reporting in tempo reale utilizza un set di dati consolidato completamente separato dal [set di dati consolidato (combinato)](/help/connections/combined-dataset.md) utilizzato per il reporting standard. Utilizza l&#39;[interruttore di aggiornamento in tempo reale](use-real-time.md) per passare da:

* Generazione di rapporti in tempo reale su un set di dati consolidato contenente fino a 24 ore di dati continui.
* Generazione di rapporti standard sul set di dati consolidato che contiene fino a 13 mesi di dati continui (o più nel caso in cui sia stata concessa la licenza per il componente aggiuntivo Capacità dati estesa).

![Reporting in tempo reale](assets/real-time-reporting-latencies.svg){zoomable="yes"}

### Latenze

La modalità di raccolta dei dati determina la latenza del reporting in tempo reale in Customer Journey Analytics. L’illustrazione precedente e la tabella seguente mostrano le latenze approssimative per vari scenari di raccolta dati quando si utilizzano rapporti standard in tempo reale e (per confronto).

| | Raccolta dati | Latenza reportistica in tempo reale <br/> (circa minore di) | Latenza di reporting standard <br/> (circa minore di) |
|:---:|---|--:|--:|
| 1 | SDK/API di Edge Network in Edge Network | 7 minuti | 95 minuti |
| 2 | Connettori di streaming | 17 minuti | 105 minuti |
| 3 | Connettore sorgente Adobe Analytics | 17 minuti | 105 minuti |
| 4 | Altri connettori di origine nei connettori di origine (inclusi i dati batch) | 25 ore | 25 ore |


## Limitazioni

Tieni presente le seguenti limitazioni per la generazione di rapporti in tempo reale:

* La generazione rapporti in tempo reale segnala solo i dati disponibili in un periodo continuo di 24 ore. Dati superiori a   24 ore non è disponibile per la generazione di rapporti in tempo reale. Quando l&#39;[aggiornamento in tempo reale](use-real-time.md) per un report è disattivato o disattivato automaticamente, tutti i dati rilevanti sono disponibili una volta di più dal [set di dati consolidato](/help/connections/combined-dataset.md) utilizzato in genere per il reporting in Customer Journey Analytics.
* Attribuzione, segmentazione, metriche calcolate e altro ancora funzionano solo sui dati disponibili entro il periodo continuo di 24 ore. Ad esempio, un segmento *Visitatori ripetuti* include pochissime persone in un rapporto in tempo reale perché il rapporto include solo le persone che hanno visitato più volte nelle ultime 24 ore. Una limitazione simile si applica quando si crea un rapporto in tempo reale su persone che in precedenza hanno fatto clic su una campagna non più attiva.
* Il reporting in tempo reale funziona meglio sui dati a livello di evento e di sessione ed è necessario prestare attenzione quando si utilizza il reporting in tempo reale per i dati a livello di persona. Poiché per i rapporti in tempo reale sono disponibili solo gli eventi del periodo continuo di 24 ore, anche la cronologia degli eventi di una persona è limitata a questa finestra. Quando selezioni una dimensione e metriche (calcolate), considera la preferenza per i dati a livello di evento e di sessione. E quando utilizzi funzionalità quali raggruppamenti, successivo o precedente e altro nel pannello con aggiornamento in tempo reale abilitato.
* Non è possibile combinare l’unione con il reporting in tempo reale. Il reporting in tempo reale riguarda i dati a livello di evento e di sessione ed è meno rilevante per i dati basati su persone.
* Non sono disponibili metriche per elementi multimediali raccolti con heartbeat, ad eccezione delle metriche di avvio e chiusura dei contenuti multimediali. Pertanto, puoi comunque utilizzare la reportistica in tempo reale per abilitare un caso d’uso dei contenuti multimediali.
* Quando utilizzi le [opzioni di download o esportazione](/help/analysis-workspace/export/download-send.md) per scaricare un progetto o esportare dati da una tabella a forma libera, considera quanto segue:
   * Un progetto CSV scaricato o un file CSV esportato contiene i dati in tempo reale disponibili al momento del download o dell’esportazione.
   * Un progetto PDF scaricato contiene dati non in tempo reale, simili a quelli visualizzati quando l’aggiornamento in tempo reale è disattivato.
