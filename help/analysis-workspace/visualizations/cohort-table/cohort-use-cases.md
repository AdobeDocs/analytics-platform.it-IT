---
description: Scopri alcuni esempi di casi d’uso per l’analisi per coorte.
keywords: Analysis Workspace
title: Casi di utilizzo dell’analisi per coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 96%

---

# Casi di utilizzo dell’[!UICONTROL Cohort Analysis]

Esempi di utilizzo di [!UICONTROL Cohort Analysis].

## Caso di utilizzo per il livello di engagement generato da un’app

Immagina di voler analizzare in che modo gli utenti che installano la tua app si comportano nel tempo. La installano ma poi non la usano? La usano solo per un po’? O la usano con continuità nel tempo?

Puoi creare una [!UICONTROL Cohort Analysis] di sei mesi:

**Unità**: mensile, da gennaio 2015 a giugno 2015

**Metrica di inclusione**: installazioni dell’app

**Metrica di ritorno**: sessioni o avvii

I visitatori non vengono considerati *`engaged`* nei mesi successivi a meno che non abbiano sessioni attive o abbiano almeno avviato l’app. [!UICONTROL Cohort Analysis] mostrerebbe quindi i pattern di utilizzo in cui *`App Install`* si verifica sempre nel mese 0. Potresti notare dei cali di utilizzo dell’app nel mese 2, indipendentemente da quando gli utenti l’hanno installata. (Per coloro che hanno installato l’app a gennaio 2015, il mese 2 è marzo 2015. Per coloro che hanno installato l’app a febbraio 2015, il mese 2 è aprile 2015, e così via). A seguito di questa analisi, potresti ad esempio inviare un’e-mail o un messaggio push a tutti gli utenti nel corso del mese due per ricordare loro di utilizzare l’app.

## Caso di utilizzo: abbonamento

Supponiamo che lavori in Adobe.com e che offri un’iscrizione gratuita a Creative Cloud. L’obiettivo è quello di spingere gli utenti ad effettuare l’aggiornamento dalla versione gratuita alla versione di prova di 30 giorni o, meglio ancora, alla versione a pagamento.

**Granularità**: mensile

**Metrica di inclusione**: collegamento di download

**Metrica di ritorno**: acquisto della versione a pagamento di Creative Cloud

Utilizzando questa [!UICONTROL Cohort Analysis], potresti notare ad esempio che un 8-10% degli utenti della versione gratuita di Creative Cloud effettua l’aggiornamento nel mese uno, indipendentemente da quando è stata effettuata l’installazione. Un 12-15% effettua l’aggiornamento nel mese due. In seguito, gli aggiornamenti subiscono un calo significativo: 4-5% nel mese tre, 3-4% nel mese quattro e 1-2% nel mese cinque.

Riconoscendo la necessità di non perdere potenziali clienti nel mese tre, imposti una campagna e-mail progettata per uscire a metà del mese tre per un campione di utenti, offrendo un coupon di 50 $ agli utenti che non hanno ancora effettuato l’aggiornamento.

Effettua nuovamente un’analisi per coorte qualche mese dopo. Per le coorti formate dopo il lancio della campagna, la conversione alle versioni a pagamento di Creative Cloud nel mese tre sono aumentate dal 4-5% al 13-14%, con conseguenti entrate per centinaia di migliaia di dollari per coorte, per ogni coorte mensile che raggiunge il mese tre da quel momento in avanti.

## Caso di utilizzo: filtri coorte complessi

Una grande catena di alberghi indirizza delle promozioni a più gruppi di clienti e tiene traccia delle prestazioni. Per identificare le coorti di gruppi di utenti migliori a cui rivolgersi, verranno creati gruppi di coorti molto specifici. Grazie ai criteri ottimizzati per [!UICONTROL Inclusion] and [!UICONTROL Return] nelle tabelle [!UICONTROL Cohort], è possibile definire con precisione i raggruppamenti per coorte con più metriche e filtri e individuare i gruppi di clienti con prestazioni meno soddisfacenti. Sarà quindi possibile inviare a tali gruppi promozioni e offerte per incrementarne le prenotazioni.

## Caso di utilizzo: adozione di una versione di un’app

Una grande compagnia di assicurazioni utilizza la propria app mobile per incentivare il coinvolgimento dei clienti. Tuttavia, sono state aggiunte all’app alcune nuove funzioni ed è importante che i clienti effettuino l’aggiornamento alla nuova versione dell’app. È possibile analizzare e confrontare tutte le versioni dell’app in uso tramite una coorte con [!UICONTROL Custom Dimension] per capire a quali clienti rivolgersi, in base alla versione dell’app. Inoltre, è possibile tenere traccia sia della fidelizzazione che dell’abbandono degli utenti, per vedere se specifiche versioni incidono sulla probabilità di abbandono nel tempo. Tramite messaggi inviati a dispositivi mobili, è possibile coinvolgere nuovamente tali clienti invitandoli a passare all’ultima versione dell’app e a usufruire delle nuove funzioni.

## Caso di utilizzo: successo delle campagne

Una multinazionale nel settore dei media usa campagne mirate per incentivare gli utenti a visitare le sue diverse piattaforme e aumentarne il coinvolgimento. La spesa per annunci per piattaforma si basa sul livello di coinvolgimento e fidelizzazione dei clienti. Una campagna di successo è quindi un fattore chiave. In questo caso, la nuova funzione per coorti con [!UICONTROL Custom Dimension] nelle tabelle [!UICONTROL Cohort] viene usata per confrontare varie campagne e individuare quelle più efficaci nell’acquisizione e nella fidelizzazione degli utenti per aumentarne il coinvolgimento. È quindi possibile individuare gli aspetti che contribuiscono al successo di una campagna e applicarli ad altre campagne a beneficio delle varie piattaforme.

## Caso di utilizzo: lancio di prodotto

Un grande rivenditore di abbigliamento ha diversi filtri di clienti che contribuiscono a grandi porzioni del fatturato. Ogni filtro ha specifici prodotti progettati e creati appositamente per tale filtro. Con ogni lancio di nuovi prodotti, vuole sapere in che modo il nuovo prodotto incrementa le vendite per varie coorti nel tempo. Utilizzando la nuova impostazione [!UICONTROL Latency Table] in [!UICONTROL Cohort Analysis], può analizzare il comportamento e il ricavo generato da un particolare filtro di clienti nei periodi precedente e successivo al lancio. Utilizzando tali informazioni si possono individuare i prodotti che generano nuovi ricavi e quelli che invece non risultano convincenti.

## Singola aderenza - Caso di utilizzo: utenti più fedeli

Una grande compagnia aerea deve il suo successo e il suo fatturato soprattutto ai clienti fedeli che ritornano nel tempo. In molti casi, i viaggiatori più fedeli rappresentano la maggior parte del fatturato e per il successo a lungo termine è quindi fondamentale assicurare di mantenere tali clienti nel tempo. Può essere difficile individuare i clienti più fedeli e coerenti. Tuttavia, con la nuova impostazione [!UICONTROL Rolling Calculation] in [!UICONTROL Cohort Analysis], è possibile analizzare i filtri dei clienti fedeli e individuare i viaggiatori che hanno effettuato più acquisti, mese dopo mese. La compagnia può quindi riservare a tali viaggiatori premi ed altri bonus come riconoscimento della loro fedeltà. Inoltre, cambiando il tipo di coorte da Retention (Fidelizzazione) a Churn (Abbandono), può identificare i clienti che non hanno effettuato acquisti ripetuti e riservare a tali filtri specifiche promozioni volte a coinvolgerli nuovamente e incentivarne la fidelizzazione.
