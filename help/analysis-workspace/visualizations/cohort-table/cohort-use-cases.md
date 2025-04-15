---
description: Scopri alcuni esempi di casi d’uso per l’analisi per coorte.
keywords: Analysis Workspace
title: Casi di utilizzo dell’analisi per coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 52%

---

# Casi di utilizzo dell’[!UICONTROL Cohort analysis]

Questo articolo descrive alcuni esempi di casi d&#39;uso per [!UICONTROL Cohort Analysis].

## Caso di utilizzo per il livello di engagement generato da un’app

Immagina di voler analizzare in che modo gli utenti che installano la tua app si comportano nel tempo. La installano ma poi non la usano? La usano solo per un po’? O la usano con continuità nel tempo?

Puoi creare una [!UICONTROL Cohort Analysis] di sei mesi:

**Unità**: mensile, da gennaio 2015 a giugno 2015

**Metrica di inclusione**: installazioni dell’app

**Metrica di ritorno**: sessioni o avvii

Le persone non vengono considerate *coinvolte* nei mesi successivi, a meno che non abbiano sessioni attive o abbiano almeno avviato l&#39;app. [!UICONTROL Cohort Analysis] mostrerebbe quindi i pattern di utilizzo in cui *l&#39;installazione dell&#39;app* si verifica sempre nel mese 0. Potresti notare dei cali di utilizzo dell’app nel mese 2, indipendentemente da quando gli utenti l’hanno installata. (Per gli utenti che hanno installato l’app a gennaio 2015, il mese 2 è marzo 2015. Per coloro che hanno installato l’app a febbraio 2015, il mese 2 è aprile 2015 e così via.) Questa analisi ti consente di inviare un messaggio e-mail o push a tutti gli utenti durante il secondo mese successivo all’installazione dell’app, per ricordargli di utilizzarla.

## Caso di utilizzo: abbonamento

Supponiamo che lavori in Adobe.com e che offri un’iscrizione gratuita a Creative Cloud. L’obiettivo è quello di spingere gli utenti ad effettuare l’aggiornamento dalla versione gratuita alla versione di prova di 30 giorni o, meglio ancora, alla versione a pagamento.

**Granularità**: mensile

**Metrica di inclusione**: collegamento di download

**Metrica di ritorno**: acquisto della versione a pagamento di Creative Cloud

Utilizzando [!UICONTROL Cohort Analysis], potresti notare ad esempio che un 8-10% degli utenti Creative Cloud gratuiti effettua l&#39;aggiornamento nel mese uno. Indipendentemente da quando sono stati installati gli utenti. Un 12-15% effettua l’aggiornamento nel mese due. In seguito, gli aggiornamenti subiscono un calo significativo: 4-5% nel mese tre, 3-4% nel mese quattro e 1-2% nel mese cinque.

Non si vuole perdere potenziali clienti nel mese tre. Quindi, hai impostato una campagna e-mail progettata per andare fuori a metà del terzo mese a un campione di utenti. Offrire un coupon di 50 dollari agli utenti che non hanno ancora effettuato l&#39;aggiornamento.

Consulta i rapporti sull’analisi per coorte qualche mese dopo. Per le coorti formate dopo il lancio della campagna, la conversione in abbonamenti Creative Cloud a pagamento nel terzo mese è aumentata dal 4-5% al 13-14%. Questo aumento di conversione si traduce in centinaia di migliaia di dollari per coorte, per ogni coorte mensile che da quel momento in poi arriva al terzo mese.

## Caso di utilizzo: segmenti coorte complessi

Una grande catena di alberghi indirizza delle promozioni a più gruppi di clienti e tiene traccia delle prestazioni. Per identificare i gruppi migliori di coorti di utenti su cui eseguire il targeting, si desidera creare gruppi di coorte molto specifici. Utilizzando i criteri aumentati di [!UICONTROL Inclusion] e [!UICONTROL Return] nelle tabelle [!UICONTROL Cohort], la catena di hotel è in grado di definire con precisione i raggruppamenti per coorte con più metriche e segmenti. In questo modo, la catena alberghiera può identificare gruppi di clienti con prestazioni insoddisfacenti per indirizzare i clienti verso promozioni e offerte volte ad aumentare le prenotazioni.

## Caso di utilizzo: adozione di una versione di un’app

Una grande compagnia di assicurazioni guida il coinvolgimento dei clienti attraverso l&#39;uso della sua app mobile. Tuttavia, sono state aggiunte all’app alcune nuove funzioni ed è importante che i clienti effettuino l’aggiornamento alla nuova versione dell’app. È possibile analizzare e confrontare tutte le versioni dell’app in uso tramite una coorte con [!UICONTROL Custom Dimension] per capire a quali clienti rivolgersi, in base alla versione dell’app. Inoltre, è possibile tenere traccia sia della fidelizzazione che dell’abbandono degli utenti, per vedere se specifiche versioni incidono sulla probabilità di abbandono nel tempo. Tramite messaggi inviati a dispositivi mobili, è possibile coinvolgere nuovamente tali clienti invitandoli a passare all’ultima versione dell’app e a usufruire delle nuove funzioni.

## Caso di utilizzo: successo delle campagne

Una multinazionale nel settore dei media usa campagne mirate per incentivare gli utenti a visitare le sue diverse piattaforme e aumentarne il coinvolgimento. La spesa per annunci per piattaforma si basa sul livello di coinvolgimento e fidelizzazione dei clienti. Una campagna di successo è quindi un fattore chiave. Utilizzano la nuova funzione per coorti [!UICONTROL Custom Dimension] nelle tabelle [!UICONTROL Cohort] per confrontare varie campagne e individuare quelle più efficaci nell&#39;acquisizione e nella fidelizzazione degli utenti per aumentarne il coinvolgimento. È quindi possibile individuare gli aspetti che contribuiscono al successo di una campagna e applicarli ad altre campagne a beneficio delle varie piattaforme.

## Caso di utilizzo: lancio di prodotto

Un grande rivenditore di abbigliamento ha diversi segmenti di clienti che contribuiscono a grandi porzioni del fatturato. Ogni segmento ha specifici prodotti progettati e creati appositamente per tale segmento. Con ogni lancio di nuovi prodotti, vuole sapere in che modo il nuovo prodotto incrementa le vendite per varie coorti nel tempo. Utilizzando la nuova impostazione [!UICONTROL Latency Table] in [!UICONTROL Cohort Analysis], può analizzare il comportamento e il ricavo generato da un particolare segmento di clienti nei periodi precedente e successivo al lancio. Utilizzando tali informazioni si possono individuare i prodotti che generano nuovi ricavi e quelli che invece non risultano convincenti.

## Singola aderenza - Caso di utilizzo: utenti più fedeli

Una grande compagnia aerea deve il suo successo e il suo fatturato soprattutto ai clienti fedeli che ritornano nel tempo. In molti casi, i viaggiatori più fedeli rappresentano la maggior parte del fatturato e per il successo a lungo termine è quindi fondamentale assicurare di mantenere tali clienti nel tempo. Può essere difficile individuare i clienti più fedeli e coerenti. Tuttavia, utilizzando la nuova impostazione [!UICONTROL Rolling Calculation] in [!UICONTROL Cohort Analysis], la compagnia aerea è in grado di analizzare i segmenti dei clienti fedeli e individuare i viaggiatori che hanno effettuato più acquisti, mese dopo mese. La compagnia aerea è anche in grado di colpire questi viaggiatori con premi e vantaggi per la loro fedeltà. Inoltre, cambiando il tipo di coorte da Retention (Fidelizzazione) a Churn (Abbandono), la compagnia aerea è in grado di identificare i clienti che non hanno effettuato acquisti ripetuti, mese dopo mese, e riservare loro delle promozioni. In questo modo, la compagnia aerea può coinvolgere di nuovo questi clienti e assicurarsi che rimangano clienti fedeli in futuro.
