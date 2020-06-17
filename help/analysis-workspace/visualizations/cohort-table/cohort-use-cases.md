---
description: Esempi di utilizzo di analisi per coorte.
keywords: Analysis Workspace
title: Casi di utilizzo dell’analisi per coorte
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 75%

---


# [!UICONTROL Cohort Analysis] casi di utilizzo

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Esempi di utilizzo per [!UICONTROL Cohort Analysis].

## Caso di utilizzo per il livello di engagement generato da un’app

Immagina di voler analizzare in che modo gli utenti che installano la tua app si comportano nel tempo. La installano ma poi non la usano? La usano solo per un po’? O la usano con continuità nel tempo?

Puoi creare un periodo di sei mesi [!UICONTROL Cohort Analysis]:

**Unità**: mensile, da gennaio 2015 a giugno 2015

**Metrica di inclusione**: installazioni dell’app

**Metrica di ritorno**: sessioni o avvii

I visitatori non vengono considerati *`engaged`* nei mesi successivi a meno che non abbiano sessioni attive o abbiano almeno avviato l’app. [!UICONTROL Cohort Analysis] verranno quindi visualizzati i pattern di utilizzo in cui si verifica *`App Install`* sempre nel mese 0. Potresti notare dei cali di utilizzo dell’app nel mese 2, indipendentemente da quando gli utenti l’hanno installata. (Per coloro che hanno installato l’app a gennaio 2015, il mese 2 è marzo 2015. Per coloro che hanno installato l’app a febbraio 2015, il mese 2 è aprile 2015, e così via). A seguito di questa analisi, potresti ad esempio inviare un’e-mail o un messaggio push a tutti gli utenti nel corso del mese due per ricordare loro di utilizzare l’app.

## Caso di utilizzo: abbonamento

Supponiamo che lavori in Adobe.com e che offri un’iscrizione gratuita a Creative Cloud. L’obiettivo è quello di spingere gli utenti ad effettuare l’aggiornamento dalla versione gratuita alla versione di prova di 30 giorni o, meglio ancora, alla versione a pagamento.

**Granularità**: mensile

**Metrica di inclusione**: collegamento di download

**Metrica di ritorno**: acquisto della versione a pagamento di Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. Un 12-15% effettua l’aggiornamento nel mese due. In seguito, gli aggiornamenti subiscono un calo significativo: 4-5% nel mese tre, 3-4% nel mese quattro e 1-2% nel mese cinque.

Riconoscendo la necessità di non perdere potenziali clienti nel mese tre, imposti una campagna e-mail progettata per uscire a metà del mese tre per un campione di utenti, offrendo un coupon di 50 $ agli utenti che non hanno ancora effettuato l’aggiornamento.

Effettua nuovamente un’analisi per coorte qualche mese dopo. Per le coorti formate dopo il lancio della campagna, la conversione alle versioni a pagamento di Creative Cloud nel mese tre sono aumentate dal 4-5% al 13-14%, con conseguenti entrate per centinaia di migliaia di dollari per coorte, per ogni coorte mensile che raggiunge il mese tre da quel momento in avanti.

## Caso di utilizzo: segmenti coorte complessi

Una grande catena di alberghi indirizza delle promozioni a più gruppi di clienti e tiene traccia delle prestazioni. Per identificare le coorti di gruppi di utenti migliori a cui rivolgersi, verranno creati gruppi di coorti molto specifici. Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## Caso di utilizzo: adozione di una versione di un’app

Una grande compagnia di assicurazioni utilizza la propria app mobile per incentivare il coinvolgimento dei clienti. Tuttavia, sono state aggiunte all’app alcune nuove funzioni ed è importante che i clienti effettuino l’aggiornamento alla nuova versione dell’app. They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. Inoltre, è possibile tenere traccia sia della fidelizzazione che dell’abbandono degli utenti, per vedere se specifiche versioni incidono sulla probabilità di abbandono nel tempo. Tramite messaggi inviati a dispositivi mobili, è possibile coinvolgere nuovamente tali clienti invitandoli a passare all’ultima versione dell’app e a usufruire delle nuove funzioni.

## Caso di utilizzo: successo delle campagne

Una multinazionale nel settore dei media usa campagne mirate per incentivare gli utenti a visitare le sue diverse piattaforme e aumentarne il coinvolgimento. La spesa per annunci per piattaforma si basa sul livello di coinvolgimento e fidelizzazione dei clienti. Una campagna di successo è quindi un fattore chiave. They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. Possono quindi identificare quali aspetti rendono una campagna efficace e applicarla ad altre campagne per aumentare il coinvolgimento nelle varie piattaforme.

## Caso di utilizzo: lancio di prodotto

Un grande rivenditore di abbigliamento ha diversi segmenti di clienti che contribuiscono a grandi porzioni del fatturato. Ogni segmento ha specifici prodotti progettati e creati appositamente per tale segmento. Con ogni lancio di nuovi prodotti, vuole sapere in che modo il nuovo prodotto incrementa le vendite per varie coorti nel tempo. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. Utilizzando tali informazioni si possono individuare i prodotti che generano nuovi ricavi e quelli che invece non risultano convincenti.

## Utenti più fedeli – Caso d’utilizzo

Una grande compagnia aerea deve il suo successo e il suo fatturato soprattutto ai clienti fedeli che ritornano nel tempo. In molti casi, i viaggiatori più fedeli rappresentano la maggior parte del fatturato e per il successo a lungo termine è quindi fondamentale assicurare di mantenere tali clienti nel tempo. Può essere difficile individuare i clienti più fedeli e coerenti. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. La compagnia può quindi riservare a tali viaggiatori premi ed altri bonus come riconoscimento della loro fedeltà. Inoltre, cambiando il tipo di coorte da Retention (Fidelizzazione) a Churn (Abbandono), può identificare i clienti che non hanno effettuato acquisti ripetuti e riservare a tali segmenti specifiche promozioni volte a coinvolgerli nuovamente e incentivarne la fidelizzazione.
