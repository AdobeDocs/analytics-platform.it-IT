---
description: Scopri alcuni esempi di casi d’uso per l’analisi per coorte.
keywords: Analysis Workspace
title: Casi di utilizzo dell’analisi per coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 20%

---

# Casi di utilizzo dell’analisi per coorte

Questo articolo descrive alcuni esempi di casi d’uso per l’analisi per coorte.

## Caso di utilizzo per il livello di engagement generato da un’app

Supponiamo di voler analizzare il modo in cui gli utenti che installano l’app interagiscono con essa nel tempo. Lo installano e non lo usano mai? La usano solo per un po’? O rimangono impegnati nel tempo?

Puoi creare un’analisi per coorte della durata di sei mesi.

**Unità**: mensile, da gennaio 2015 a giugno 2015

**Metrica di inclusione**: installazioni dell’app

**Metrica di ritorno**: sessioni o avvii

Le persone non vengono considerate *coinvolte* nei mesi successivi, a meno che non abbiano sessioni attive o abbiano almeno avviato l&#39;app. [!UICONTROL Cohort Analysis] mostrerebbe quindi i pattern di utilizzo in cui *l&#39;installazione dell&#39;app* si verifica sempre nel mese 0. Potresti notare un calo di utilizzo nel mese 2, indipendentemente da quando gli utenti hanno installato l’app. (Per gli utenti che hanno installato l’app a gennaio 2015, il mese 2 è marzo 2015. Per coloro che hanno installato l’app a febbraio 2015, il mese 2 è aprile 2015 e così via.) Questa analisi ti consente di inviare un messaggio e-mail o push a tutti gli utenti durante il secondo mese successivo all’installazione dell’app, per ricordargli di utilizzarla.

## Caso di utilizzo: abbonamento

Lavori su Adobe.com e offri un abbonamento gratuito a Creative Cloud. L’obiettivo è quello di passare dalla versione gratuita alla versione di prova di 30 giorni o, in ultima analisi, alla versione a pagamento.

**Granularità**: mensile

**Metrica di inclusione**: collegamento di download

**Metrica di ritorno**: acquisto della versione a pagamento di Creative Cloud

Utilizzando [!UICONTROL Cohort Analysis], potresti notare ad esempio che un 8-10% degli utenti Creative Cloud gratuiti effettua l&#39;aggiornamento nel mese uno. Indipendentemente da quando sono stati installati gli utenti. Aggiornamento del 12-15% nel secondo mese di utilizzo. In seguito, gli aggiornamenti subiscono un calo significativo: 4-5% nel mese tre, 3-4% nel mese quattro e 1-2% nel mese cinque.

Non si vuole perdere potenziali clienti nel mese tre. Quindi, hai impostato una campagna e-mail progettata per andare fuori a metà del terzo mese a un campione di utenti. Offrire un coupon di 50 dollari agli utenti che non hanno ancora effettuato l&#39;aggiornamento.

Consulta i rapporti sull’analisi per coorte qualche mese dopo. Per le coorti formate dopo il lancio della campagna, la conversione in abbonamenti Creative Cloud a pagamento nel terzo mese è aumentata dal 4-5% al 13-14%. Questo aumento di conversione si traduce in centinaia di migliaia di dollari per coorte, per ogni coorte mensile che da quel momento in poi arriva al terzo mese.

## Caso di utilizzo: segmenti coorte complessi

Una grande catena alberghiera si rivolge a più gruppi di clienti per le promozioni e tiene traccia delle prestazioni. Per identificare i gruppi migliori di coorti di utenti su cui eseguire il targeting, si desidera creare gruppi di coorte molto specifici. Utilizzando i criteri aumentati di [!UICONTROL Inclusion] e [!UICONTROL Return] nelle tabelle [!UICONTROL Cohort], la catena di hotel è in grado di definire con precisione i raggruppamenti per coorte con più metriche e segmenti. In questo modo, la catena alberghiera può identificare gruppi di clienti con prestazioni insoddisfacenti per indirizzare i clienti verso promozioni e offerte volte ad aumentare le prenotazioni.

## Caso di utilizzo: adozione di una versione di un’app

Una grande compagnia di assicurazioni guida il coinvolgimento dei clienti attraverso l&#39;uso della sua app mobile. Tuttavia, con l’aggiunta di nuove funzioni all’app, è fondamentale che i clienti effettuino l’aggiornamento all’ultima versione dell’app. È possibile analizzare e confrontare tutte le versioni dell’app in uso tramite una coorte con [!UICONTROL Custom Dimension] per capire a quali clienti rivolgersi, in base alla versione dell’app. Inoltre, possono tenere traccia sia della fidelizzazione che dell’abbandono per vedere se specifiche versioni dell’app stanno allontanando i clienti dall’utilizzare l’app nel tempo. Grazie alle attività di messaggistica mobile, è possibile coinvolgere nuovamente questi utenti per aggiornarli alla versione più recente e sfruttarne le funzionalità più recenti.

## Caso di utilizzo: successo delle campagne

Una multinazionale del settore dei media utilizza campagne mirate per indirizzare gli utenti verso le varie piattaforme per stimolare il coinvolgimento. La spesa pubblicitaria per piattaforma si basa sul coinvolgimento e sulla fidelizzazione dei clienti; pertanto, le campagne di successo sono fondamentali per il successo della loro attività. Utilizzano la nuova funzione per coorti [!UICONTROL Custom Dimension] nelle tabelle [!UICONTROL Cohort] per confrontare varie campagne e individuare quelle più efficaci nell&#39;acquisizione e nella fidelizzazione degli utenti per aumentarne il coinvolgimento. È quindi possibile individuare gli aspetti che contribuiscono al successo di una campagna e applicarli ad altre campagne a beneficio delle varie piattaforme.

## Caso di utilizzo: lancio di prodotto

Un grande retailer di abbigliamento ha molti segmenti di clienti specifici che guidano grandi porzioni di fatturato per la loro attività. Ogni segmento dispone di prodotti specifici progettati e creati pensando a quel segmento. Con ogni lancio di nuovi prodotti, vuole sapere in che modo il nuovo prodotto incrementa le vendite per varie coorti nel tempo. Utilizzando la nuova impostazione [!UICONTROL Latency Table] in [!UICONTROL Cohort Analysis], può analizzare il comportamento e il ricavo generato da un particolare segmento di clienti nei periodi precedente e successivo al lancio. Utilizzando tali informazioni si possono individuare i prodotti che generano nuovi ricavi e quelli che invece non risultano convincenti.

## Singola aderenza - Caso di utilizzo: utenti più fedeli

Una grande compagnia aerea trae la maggior parte del suo successo e dei ricavi da clienti abituali e abituali. In molti casi, i viaggiatori fedeli rappresentano la maggior parte dei loro ricavi e il mantenimento di tali clienti è fondamentale per il loro successo a lungo termine. Spesso è difficile identificare i clienti più fedeli e coerenti. Tuttavia, utilizzando la nuova impostazione [!UICONTROL Rolling Calculation] in [!UICONTROL Cohort Analysis], la compagnia aerea è in grado di analizzare i segmenti dei clienti fedeli e individuare i viaggiatori che hanno effettuato più acquisti, mese dopo mese. La compagnia aerea è anche in grado di colpire questi viaggiatori con premi e vantaggi per la loro fedeltà. Inoltre, cambiando il tipo di coorte da Retention (Fidelizzazione) a Churn (Abbandono), la compagnia aerea è in grado di identificare i clienti che non hanno effettuato acquisti ripetuti, mese dopo mese, e riservare loro delle promozioni. In questo modo, la compagnia aerea può coinvolgere di nuovo questi clienti e assicurarsi che rimangano clienti fedeli in futuro.
