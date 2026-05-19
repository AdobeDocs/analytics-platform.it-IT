---
description: Scopri i casi d’uso tipici delle tabelle coorte in Analysis Workspace, che includono coinvolgimento dell’app, analisi dell’abbonamento, fedeltà delle campagne e lanci di prodotti.
keywords: Analysis Workspace
title: Casi di utilizzo dell’analisi per coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
autotag-review: '2026-05-19T08:40:45.448Z'
TQID: 'https://experienceleague.adobe.com/y3eY2-z0jYCzn58PVATdpxJfE-EYEHrZIJx2V31bAbM'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5520579-b31f-4df7-9281-f0d9f91e2edcid: c13ff12d-60f1-49cd-833a-d43359628223id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1019
ht-degree: 2%

---

# Casi di utilizzo dell’analisi per coorte

Questo articolo illustra diversi casi d’uso tipici per i quali le tabelle coorte sono utili per fornire informazioni utili per eseguire azioni successive.

## Coinvolgimento app

Supponiamo di voler analizzare il modo in cui gli utenti che installano l’app interagiscono con l’app nel tempo. Gli utenti installano l’app e non la utilizzano mai in seguito? Oppure l&#39;app viene utilizzata per un po&#39; di tempo e poi l&#39;app viene interrotta? O gli utenti rimangono coinvolti nel tempo?

Puoi creare un’analisi per coorte della durata di sei mesi. I visitatori non contano come *`engaged`* nei mesi successivi, a meno che questi utenti non abbiano una sessione o almeno avviino l&#39;app. [!UICONTROL Analisi per coorte] mostrerebbe quindi i pattern di utilizzo in cui *`App Install`* si verifica sempre nel mese 0. Potresti notare un calo di utilizzo nel mese 2, indipendentemente da quando gli utenti hanno installato l’app. Questa analisi ti consente di inviare un messaggio e-mail o push a tutti gli utenti durante il secondo mese successivo all’installazione dell’app, per ricordargli di utilizzarla.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo del coinvolgimento dell&#39;app](assets/app-engagement.png)

+++

## Iscrizione

Lavori su Adobe.com e offri un abbonamento gratuito a Creative Cloud. L’obiettivo è quello di passare dalla versione gratuita alla versione di prova di 30 giorni o, in ultima analisi, alla versione a pagamento.

Utilizza [!UICONTROL Analisi per coorte] per comprendere, ad esempio, che un 8-10% degli utenti Creative Cloud gratuiti effettua l&#39;aggiornamento nel mese uno, indipendentemente da quando è stata effettuata l&#39;installazione. Poi aggiornamento del 12-15% nel secondo mese di utilizzo. In seguito, gli aggiornamenti subiscono un calo significativo: 4-5% nel mese tre, 3-4% nel mese quattro e 1-2% nel mese cinque.

Riconoscendo che non desideri perdere potenziali clienti nel terzo mese, hai impostato una campagna e-mail progettata per andare fuori a metà del terzo mese a un campione di utenti. In questa campagna, offri un coupon di 50 $ agli utenti che non hanno ancora effettuato l’aggiornamento.

Ricontrolla con l’analisi per coorte qualche mese più tardi. Per le coorti formate dopo il lancio della campagna, la conversione in abbonamenti Creative Cloud a pagamento nel terzo mese è aumentata dal 4-5% al 13-14%. La conversione si traduce in centinaia di migliaia di dollari per coorte, per ogni coorte mensile che da quel momento in poi arriva al terzo mese.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo abbonamento](assets/subscription-use-case.png)

+++

## Segmenti di coorte complessi

Puoi eseguire analisi per una grande catena alberghiera che esegue il targeting di più gruppi di clienti per le promozioni e tenere traccia dei gruppi di clienti rispetto alle prestazioni. Per identificare i gruppi migliori di coorti di utenti da targetizzare, si desidera creare gruppi di coorte molto specifici. Utilizza i criteri di [!UICONTROL inclusione] e [!UICONTROL ritorno] migliorati nelle tabelle [!UICONTROL coorte] per definire solo i raggruppamenti di coorte corretti con più metriche e segmenti. Questa analisi ti aiuta a identificare i gruppi di clienti con prestazioni insoddisfacenti, in modo da poterli indirizzare a promozioni e offerte per aumentare le prenotazioni.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo: segmenti coorte complessi](assets/complex-cohort-segments.png)

+++

## Adozione della versione app

Sei l’analista di una grande compagnia di assicurazioni che guida il coinvolgimento dei clienti attraverso l’utilizzo della sua app mobile. Quando vengono aggiunte nuove funzioni all’app, i clienti devono effettuare l’aggiornamento alla versione più recente. Puoi analizzare e confrontare le versioni dell&#39;app una accanto all&#39;altra utilizzando la coorte [!UICONTROL Personalizza Dimension] per vedere a quali clienti rivolgersi, in base alla versione dell&#39;app. Inoltre, puoi tenere traccia della fidelizzazione e dell’abbandono per vedere se specifiche versioni dell’app allontanano i clienti dall’utilizzo dell’app nel tempo. Grazie alle attività di messaggistica mobile, puoi coinvolgere nuovamente questi utenti in modo che effettuino l’aggiornamento alla versione più recente per sfruttare le funzioni più recenti.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo dell&#39;app rispetto al caso di adozione](assets/app-versus-adoption.png)

+++

## Stickiness della campagna

Sei l’analista di una multinazionale del settore dei media che utilizza campagne mirate per indirizzare gli utenti verso le varie piattaforme al fine di stimolare il coinvolgimento. La spesa pubblicitaria per piattaforma si basa sul coinvolgimento e sulla fidelizzazione dei clienti. Le campagne di successo sono fondamentali per il successo dell’azienda. Utilizza la nuova funzionalità per coorti [!UICONTROL Custom Dimension] nelle tabelle [!UICONTROL Cohort] per confrontare varie campagne e individuare quelle più efficaci nell&#39;acquisizione e nella fidelizzazione degli utenti per aumentare il coinvolgimento. Puoi quindi identificare gli aspetti che contribuiscono al successo di una campagna e applicare tali conoscenze ad altre campagne per aumentare il coinvolgimento nelle varie piattaforme.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo della fedeltà della campagna](assets/campaign-stickiness.png)

+++

## Lancio del prodotto

Sei l’analista di un’ampia retailer di abbigliamento con molti segmenti di clienti specifici che generano grandi porzioni di fatturato per la loro attività. Ogni segmento dispone di prodotti specifici progettati e creati pensando a quel segmento. Con ogni lancio di prodotto, vuoi sapere in che modo il nuovo prodotto ha incrementato le vendite per varie coorti nel tempo. Utilizzando la nuova impostazione [!UICONTROL Tabella di latenza] in [!UICONTROL Analisi per coorte], puoi analizzare il comportamento e il ricavo generato da un particolare segmento di clienti nei periodi precedente e successivo al lancio. Utilizzando queste informazioni, puoi identificare quali prodotti generano nuovi ricavi e quali non sono in grado di attrarre i clienti.

+++ Esempio di visualizzazione di una tabella coorte

![Caso di utilizzo del lancio del prodotto](assets/product-launch.png)

+++

## Stickiness individuale - utenti più fedeli

Sei l’analista di una grande compagnia aerea che ricava la maggior parte del suo successo e dei ricavi da clienti abituali e abituali. In molti casi, i viaggiatori fedeli rappresentano la maggior parte dei ricavi e il mantenimento di tali clienti è fondamentale per il successo a lungo termine. Spesso è difficile identificare i clienti più fedeli e coerenti. Tuttavia, utilizzando la nuova impostazione [!UICONTROL Calcolo continuo] in [!UICONTROL Analisi per coorte], puoi analizzare i segmenti dei clienti fedeli e individuare i viaggiatori che hanno effettuato più acquisti, mese dopo mese. Puoi quindi indirizzare a questi viaggiatori premi e vantaggi per la loro fedeltà. Inoltre, cambiando il tipo di coorte da Retention (Fidelizzazione) a Churn (Abbandono), puoi anche identificare quali clienti non hanno effettuato acquisti ripetuti, mese dopo mese. Potrai riservare a quei segmenti specifiche promozioni volte a coinvolgere di nuovo i clienti, in modo che rimangano fedeli in futuro.

+++ Esempi di visualizzazioni della tabella coorte

![Caso di utilizzo di Sticky Case individuale - conservazione](assets/individual-stickiness-1.png)

![Singolo caso di utilizzo di coerenza - abbandono](assets/individual-stickiness-2.png)

+++
