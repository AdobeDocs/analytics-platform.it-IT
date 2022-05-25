---
description: Scopri in che modo AEP Customer AI si integra con Workspace in CJA.
title: Integrare Customer AI con CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: c1e9fdb0e6d62da91b2b5c81eb21462890945b62
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Integrare Customer AI con CJA

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), come parte di Adobe Experience Platform Intelligent Services, offre agli addetti al marketing la possibilità di generare previsioni sui clienti a livello individuale.

Con l’aiuto di fattori influenti, Customer AI può dirvi cosa è probabile che faccia un cliente e perché. Inoltre, gli esperti di marketing possono trarre vantaggio dalle previsioni e dalle informazioni di Customer AI per personalizzare le esperienze dei clienti servendo le offerte e i messaggi più appropriati.

Customer AI si basa su dati comportamentali individuali e dati di profilo per il punteggio di propensione. Customer AI è flessibile in quanto può assumere più origini dati, tra cui Adobe Analytics, Adobe Audience Manager, dati Consumer Experience Event e dati Experience Event. Se utilizzi il connettore dati AEP per inserire i dati di Adobe Audience Manager e Adobe Analytics, il modello raccoglie automaticamente i tipi di evento standard per addestrare e valutare il modello. Se inserisci un set di dati Evento esperienza personalizzato senza tipi di evento standard, tutti i campi rilevanti dovranno essere mappati come eventi personalizzati o attributi di profilo se desideri utilizzarlo nel modello. Questo può essere fatto nel passaggio di configurazione di Customer AI . &#x200B;

Customer AI si integra con il Customer Journey Analytics (CJA) nella misura in cui i set di dati abilitati per Customer AI possono essere utilizzati nelle visualizzazioni dati e nel reporting in CJA. Con questa integrazione, puoi

* **Tracciare i punteggi di propensione per un segmento di utenti nel tempo**. Esempio di utilizzo: Qual è la probabilità che un cliente dell&#39;hotel acquisti un biglietto per lo show presso la sede del concerto dell&#39;hotel?
* **Analizzare gli eventi di successo o gli attributi associati ai punteggi di propensione**. &#x200B;Esempio di utilizzo: Voglio comprendere gli attributi o gli eventi di successo associati ai punteggi di propensione.
* **Segui il flusso di entrata per la propensione del cliente su diverse esecuzioni di punteggio**. Esempio di utilizzo: Vorrei capire le persone che inizialmente erano utenti a bassa propensione e, nel tempo, sono diventati utenti ad alta propensione. &#x200B;
* **Guardate la distribuzione della propensione**. Caso di utilizzo: Vorrei comprendere la distribuzione dei punteggi di propensione a Posso essere più precisa con i miei segmenti. &#x200B;Esempio: un rivenditore desidera effettuare una promozione specifica per 50 $ su un prodotto.  Possono solo voler gestire una promozione molto limitata a causa del budget, ecc. Analizzano i dati e decidono di eseguire il targeting solo dei primi &#x200B; dell’80%+ dei loro clienti.
* **Osserva la propensione a eseguire un’azione per una particolare coorte nel tempo**. Caso di utilizzo: Vorrei tenere traccia di una coorte specifica nel tempo. È simile al primo, ma è possibile tenere traccia di una coorte specifica nel tempo. &#x200B; Esempio di ospitalità: Un esperto di marketing può rintracciare il loro livello bronzo rispetto al loro livello argento, o livello argento rispetto al loro livello oro nel tempo. Poi possono vedere la propensione di ogni coorte a prenotare l&#39;hotel nel tempo. &#x200B;

## Flusso di lavoro

Alcuni dei passaggi vengono eseguiti in Adobe Experience Platform prima di lavorare con l’output in CJA.

### Passaggio 1: Configurare un’istanza di Customer AI

Dopo aver preparato i dati e aver impostato tutte le credenziali e gli schemi, inizia seguendo [Configurare un’istanza di Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guida.

### Passaggio 2: Impostare una connessione CJA ai set di dati di Customer AI

In CJA, ora puoi [creare una o più connessioni](/help/connections/create-connection.md) Experience Platform di set di dati che sono stati strumentalizzati per Customer AI. Ogni previsione, ad esempio &quot;Probabilità di aggiornare l’account&quot;, equivale a un set di dati. Questi set di dati vengono visualizzati con il prefisso &quot;Punteggi Customer AI in Formato EE - nome_dell_applicazione&quot;.

>[!IMPORTANT]
>
>Ogni istanza di Customer AI dispone di due set di dati di output se l’interruttore è attivato per abilitare i punteggi per CJA durante la configurazione del passaggio 1. Un set di dati di output viene visualizzato in formato XDM profilo e uno in formato XDM evento esperienza.

![Punteggi delle ICC](assets/cai-scores.png)

![Crea connessione](assets/create-conn.png)

Di seguito è riportato un esempio di schema XDM che CJA inserirebbe come parte di un set di dati esistente o nuovo:

![Schema CAI](assets/cai-schema.png)

(L’esempio è un set di dati di profilo; lo stesso set di oggetti schema farebbe parte di un set di dati Experience Event che CJA acquisirebbe. Il set di dati di Experience Event include marche temporali come data del punteggio.) Ogni cliente valutato in questo modello avrebbe un punteggio, una data punteggio, ecc. associati a loro.

### Passaggio 3: Crea visualizzazioni dati in base a queste connessioni

In CJA, ora puoi procedere per [creare visualizzazioni dati](/help/data-views/create-dataview.md) con le dimensioni (come punteggio, data del punteggio, probabilità e così via) e le metriche inserite come parte della connessione stabilita.

![Creare una visualizzazione dati](assets/create-dataview.png)

### Passaggio 4: Report sui punteggi ICC in Workspace

In CJA Workspace, ora puoi creare un nuovo progetto e inserire le visualizzazioni .

Ecco un esempio di un progetto Workspace con dati ICC che genera un punteggio di propensione per un segmento di utenti nel tempo, in &#x200B; un grafico a barre sovrapposto:

![Punti elenco](assets/workspace-scores.png)

Ecco una tabella che mostra i codici motivo per cui un segmento ha un &#x200B; di propensione alto o basso:

![Codici dei motivi](assets/reason-codes.png)

Questo diagramma di flusso mostra il flusso di ingresso per la propensione del cliente su diverse esecuzioni di punteggio &#x200B;:

![Flusso di ingresso](assets/flow.png)

Questo grafico a barre mostra la distribuzione dei punteggi di propensione &#x200B;:

![Distribuzione](assets/distribution.png)

Questo diagramma di Venn mostra la sovrapposizione della propensione su diverse esecuzioni di punteggio:

![Sovrapposizioni tendenza](assets/venn.png)
