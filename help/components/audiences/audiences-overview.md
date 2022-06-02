---
title: Panoramica sulla pubblicazione di CJA Audiences
description: Scopri il concetto di pubblicazione di tipi di pubblico in Customer Journey Analytics
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 3%

---


# Panoramica sulla pubblicazione di CJA Audience

Ora puoi pubblicare i tipi di pubblico rilevati in Customer Journey Analytics (CJA) in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per il targeting dei clienti e la personalizzazione. Con Profilo cliente in tempo reale puoi visualizzare una visualizzazione olistica di ogni singolo cliente combinando dati provenienti da più canali, inclusi online, offline, CRM e di terze parti. Il profilo ti consente di consolidare i dati dei clienti in una visualizzazione unificata che offre un account utilizzabile e con marca temporale per ogni interazione con il cliente.

Il pubblico di pubblicazione offre un modo chiaro di agire sulle informazioni presenti all’interno di CJA. Tali azioni possono includere:

* Invio di e-mail a questo pubblico.
* Invio di messaggi push a questo pubblico.
* Utilizzo del pubblico per un percorso in Adobe Journey Optimizer.
* Esportazione del pubblico in terze parti tramite una destinazione AEP

## Terminologia chiave

**Pubblico**: Un set o un elenco di identità con uno spazio dei nomi e un ID specifico correlati a tale spazio dei nomi. I tipi di pubblico sono trasportabili dal Adobe Experience Platform e dalle applicazioni che lo compongono (come CJA). I tipi di pubblico possono contenere spazi dei nomi misti.

**Filtro**: Un insieme di regole che, se valutate in un insieme di dati per un periodo di tempo, produce un sottoinsieme di dati. Un filtro può essere utilizzato nel processo di creazione di un pubblico quando è associato ad altri servizi di supporto. I filtri sono definiti e mantenuti in CJA.

**Filtri** contro **Segmenti**: CJA non utilizza il concetto di &quot;segmenti&quot;, ma utilizza &quot;filtri&quot;. Sebbene siano entrambe un insieme di regole che possono contenere logica simile, producono output diversi. Un filtro viene utilizzato per limitare un set di dati a scopo di analisi. Un segmento viene utilizzato per generare un elenco di identità che possono essere utilizzate per l’attivazione. I segmenti producono tipi di pubblico in Profilo cliente in tempo reale, mentre i filtri (da soli) no. CJA Audience Publishing è il processo tramite il quale utilizziamo un filtro CJA per creare un pubblico che può essere utilizzato dal profilo cliente in tempo reale.

## Autorizzazioni

Gli amministratori ricevono automaticamente il [!UICONTROL Audience Publishing] in Adobe Admin Console. Possono concedere questa autorizzazione a singoli utenti.

## Passaggi successivi



