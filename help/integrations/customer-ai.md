---
description: Scopri in che modo AEP Customer AI si integra con Workspace in CJA.
title: Integrare Customer AI con CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: d59128c34deb7d8fb65d0fad4e6029453c449ea4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---


# Integrare Customer AI con CJA

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), come parte di Adobe Experience Platform Intelligent Services, offre agli addetti al marketing la possibilità di generare previsioni sui clienti a livello individuale.

Con l’aiuto di fattori influenti, Customer AI può dirvi cosa è probabile che faccia un cliente e perché. Inoltre, gli esperti di marketing possono trarre vantaggio dalle previsioni e dalle informazioni di Customer AI per personalizzare le esperienze dei clienti servendo le offerte e i messaggi più appropriati.

Customer AI funziona analizzando uno dei seguenti set di dati per prevedere i punteggi di propensione di abbandono o conversione:

* Dati di Adobe Analytics utilizzando il connettore di origine di Analytics
* Dati Adobe Audience Manager utilizzando il connettore di origine Audience Manager
* Set di dati Experience Event (EE)
* Set di dati di Consumer Experience Event (CEE)

Customer AI si integra con il Customer Journey Analytics (CJA) nella misura in cui i set di dati abilitati per Customer AI possono essere utilizzati nelle visualizzazioni dati e nel reporting in CJA.

## Flusso di lavoro

Alcuni dei passaggi vengono eseguiti in Adobe Experience Platform prima di lavorare con l’output in CJA.

### Passaggio 1: Scaricare i punteggi di Customer AI

Il download dei punteggi di Customer AI viene effettuato tramite una combinazione di chiamate API di Experience Platform, come descritto [qui](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### Passaggio 2: Definizione degli input e degli output di Customer AI

Questo processo è descritto in [Input e output in Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) documentazione.

### Passaggio 3: Configurare un’istanza di Customer AI

Dopo aver preparato i dati e aver impostato tutte le credenziali e gli schemi, inizia seguendo [Configurare un’istanza di Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guida.

### Passaggio 4: Impostare una connessione CJA ai set di dati di Customer AI

In CJA, ora puoi [creare una o più connessioni](/help/connections/create-connection.md) Experience Platform di set di dati che sono stati strumentalizzati per Customer AI. Questi set di dati vengono visualizzati con il prefisso &quot;Punteggi AI del cliente&quot;, come mostrato di seguito:

![Punteggi delle ICC](assets/cai-scores.png)

Ogni previsione, ad esempio &quot;Probabilità di aggiornare l’account&quot;, equivale a un set di dati.

Di seguito è riportato un esempio di schema XDM che CJA inserirebbe come parte di un set di dati esistente o di un nuovo set di dati:

![Schema CAI](assets/cai-schema.png)

(L’esempio è un set di dati di profilo; lo stesso set di oggetti schema farebbe parte di un set di dati Experience Event che CJA acquisirebbe. Il set di dati di Experience Event include marche temporali come data del punteggio.) Ogni cliente valutato in questo modello avrebbe un punteggio, una data punteggio, ecc. associati a loro.

### Passaggio 5: Crea visualizzazioni dati in base a queste connessioni

In CJA, ora puoi procedere per creare visualizzazioni dati con le dimensioni inserite come