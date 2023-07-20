---
title: Domande frequenti sull’unione
description: Domande frequenti sull’unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: c87aaefdd15e02b7fe2cf8e638830aa278d46b92
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 35%

---

# Domande frequenti

Di seguito sono riportate alcune domande frequenti sull’unione:

+++**Come posso utilizzare l’unione per vedere come le persone si spostano da un canale all’altro?**

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Seleziona la **[!UICONTROL ** Visualizzare **]** a sinistra e trascinare un **[!UICONTROL ** Flusso **]** nell’area di lavoro a destra.
3. Seleziona la **[!UICONTROL ** Componenti **]** a sinistra e trascinare la quota **[!UICONTROL ** ID set di dati **]** alla posizione centrale contrassegnata **[!UICONTROL ** Dimension o elemento **]**.
4. Questo rapporto di flusso è interattivo. Per espandere i flussi alle pagine successive o precedenti, selezionare uno qualsiasi dei valori. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

+++

+++**Quanto indietro nel tempo va l’unione dei visitatori di ripetizione?**

L’intervallo di lookback per la rekeying dipende dalla frequenza di dati [ripetizione](explained.md) desiderata. Ad esempio, se imposti l’unione per riprodurre i dati una volta alla settimana, l’intervallo di lookback per la reimpostazione delle chiavi è di sette giorni. Se imposti l’unione per riprodurre i dati ogni giorno, l’intervallo di lookback per la reimpostazione delle chiavi è di un giorno.

+++

+++**Come vengono gestiti i dispositivi condivisi?**

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate (anche se provengono dallo stesso dispositivo).

+++

+++**In che modo l’unione gestisce le situazioni in cui una singola persona dispone di più ID persistenti?**

In alcune situazioni, un singolo utente può essere associato a più ID persistenti. Un esempio è la cancellazione frequente dei cookie del browser o l’utilizzo della modalità privata/in incognito del browser.

Il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di Customer Journey Analytics di eseguire unioni tra dispositivi.

+++

+++**Una volta contattato il mio Adobe Account Team con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?**

L’unione live è disponibile circa una settimana dopo l’attivazione dell’unione da parte di Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

+++

+++**Qual è la differenza tra l’analisi cross-device (una funzione nella versione tradizionale di Analytics) e l’analisi cross-channel?**

[Analisi cross-device](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) è una funzione specifica della versione tradizionale di Adobe Analytics che consente di comprendere il modo in cui le persone operano tra i dispositivi. Offre due flussi di lavoro per collegare i dati dei dispositivi: unione basata sui campi e grafico dei dispositivi.

L’analisi cross-channel è un caso di utilizzo specifico del Customer Journey Analytics che consente di comprendere il modo in cui le persone operano sia sui dispositivi che sui canali. Unisce l’ID persona di un set di dati, consentendo di combinare facilmente tale set di dati con altri set di dati. Questa funzione opera in modo simile all’unione basata sui campi di analisi cross-device, ma l’implementazione è diversa a causa della diversa architettura dei dati tra Analytics tradizionale e Customer Journey Analytics. Consulta [Stitching](overview.md) e [analisi cross-channel](../use-cases/cross-channel/cross-channel.md) caso d’uso per ulteriori informazioni.

+++**In che modo Stitching gestisce le richieste RGPD e CCPA?**

Adobe gestisce le richieste RGPD e CCPA in conformità alle leggi locali e internazionali. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

+++

+++**Cosa succede se il campo ID persistente in uno o più eventi è vuoto?**

Se il campo ID persistente è vuoto in un evento in un set di dati unito, l’ID unito per tale evento in viene determinato in uno dei due modi seguenti:

* Se il campo ID transitorio non è vuoto, il Customer Journey Analytics utilizza il valore in ID transitorio come ID unito.
* Se il campo ID transitorio è vuoto, anche Customer Journey Analytics lascia vuoto l’ID unione. In questo caso, ID persistente, ID transitorio e ID vincolato sono tutti vuoti durante l’evento. Questi tipi di eventi vengono eliminati da qualsiasi connessione di Customer Journey Analytics che utilizza il set di dati unito in cui l’ID unito è stato scelto come ID persona.

+++

+++**In che modo le metriche nei set di dati con unione di Customer Journey Analytics si confrontano con metriche simili nei set di dati senza unione di Customer Journey Analytics e con Adobe Analytics?**

Alcune metriche in Customer Journey Analytics sono simili alle metriche nella versione tradizionale di Analytics, ma altre sono diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Customer Journey Analytics dati uniti** | **Customer Journey Analytics dati non uniti** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di ID persona distinti in cui l’ID unione è scelto come ID persona. **Persone** può essere superiore o inferiore a **Visitatori unici** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione. | **Persone** = numero di ID persona distinti in base alla colonna selezionata come ID persona. **Persone** nei set di dati del connettore di origine di Analytics è simile a **Visitatori univoci** in Adobe Analytics tradizionale se `endUserIDs._experience.aaid.id` viene utilizzato come ID persona nel Customer Journey Analytics. | **Visitatori unici** = numero di ID visitatore distinti. **Visitatori unici** potrebbe non essere lo stesso del conteggio di valori univoci **ECID**. | Consulta [Persone](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=it). |
| **Sessioni**: definito in base alle impostazioni di sessione nella visualizzazione dati del Customer Journey Analytics. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: definito in base alle impostazioni di sessione specificate nella visualizzazione dati del Customer Journey Analytics. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it). | **Visite**: definito in base alle impostazioni di sessione specificate nella [suite di rapporti virtuali CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=it). |
| **Eventi** = conteggio delle righe nei dati uniti nel Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Nota, tuttavia, le domande frequenti sopra relative alle righe con un ID persistente vuoto. | **Eventi** = conteggio delle righe nei dati non uniti nel Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tuttavia, se uno qualsiasi degli eventi dispone di un ID persona vuoto nei dati non uniti nel data lake di Experience Platform, questi eventi non vengono inclusi nel Customer Journey Analytics. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). |

Altre metriche possono essere simili in Customer Journey Analytics e Adobe Analytics. Ad esempio, il conteggio totale per Adobe Analytics [eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=it) 1-100 è comparabile tra Adobe Analytics tradizionale e Customer Journey Analytics (sia che siano uniti o meno). [Differenze nelle funzionalità](/help/getting-started/aa-vs-cja/cja-aa.md)) come la deduplicazione degli eventi tra Customer Journey Analytics e Adobe Analytics, può causare discrepanze tra i due prodotti.

+++

+++**Il Customer Journey Analytics può utilizzare i campi di Identity Map?**

No, al momento il Customer Journey Analytics non può utilizzare i campi Identity Map per l’unione.

+++
