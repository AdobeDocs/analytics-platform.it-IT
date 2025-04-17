---
title: Valuta per quanto tempo avrai bisogno di Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics
description: Scopri come valutare per quanto tempo avrai bisogno di Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 86%

---

# Valutare quando disabilitare Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Eseguire lo spostamento completo a Customer Journey Analytics"
>abstract="(Consigliato) Adobe consiglia di passare completamente da Adobe Analytics a Customer Journey Analytics. Durante il periodo di transizione, pianifica di eseguire Adobe Analytics insieme a Customer Journey Analytics per eseguire confronti affiancati dei dati. Quando avrai dimestichezza con i dati, potrai disabilitare Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Mantenere entrambi i prodotti di analisi"
>abstract="(Non consigliato) Se selezioni questa opzione, il contratto con Adobe includerà sia Adobe Analytics che Customer Journey Analytics e, a lungo termine, questa scelta potrà risultare più costosa per l’organizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Disattiva il connettore di origine di Analytics per utilizzare i dati esclusivamente dal Web SDK"
>abstract="Il connettore di origine di Analytics viene utilizzato per fornire confronto dei dati affiancato, dati storici e accesso ad alcune funzioni che non sono completamente disponibili in Customer Journey Analytics. Se non hai più bisogno di Adobe Analytics per questi scopi, puoi disabilitare il connettore di origine di Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La maggior parte delle organizzazioni finisce per disabilitare Adobe Analytics dopo l’aggiornamento a Customer Journey Analytics. Ciò è dovuto al costo e alla complessità della manutenzione di due ambienti di analisi.

Tuttavia, Adobe consiglia di mantenere l’ambiente Adobe Analytics in esecuzione per un periodo di tempo dopo l’implementazione di Customer Journey Analytics. Nelle sezioni seguenti vengono descritti i motivi per farlo e i tempi consigliati per la disattivazione di Adobe Analytics.

## Utilizzi di Adobe Analytics durante e dopo un aggiornamento

Quando decidi se e quando la tua organizzazione deve disabilitare Adobe Analytics, considera i seguenti utilizzi di Adobe Analytics durante e dopo un aggiornamento a Customer Journey Analytics:

| Utilizzi di Adobe Analytics durante e dopo un aggiornamento | Spiegazione |
|---------|----------|
| Esegui confronti dei dati affiancati | Adobe consiglia di mantenere l’ambiente Adobe Analytics in esecuzione per un periodo di tempo dopo l’esecuzione e la raccolta dei dati del nuovo ambiente Customer Journey Analytics. Questo è il modo migliore per confrontare i dati Customer Journey Analytics affiancati ai dati Adobe Analytics.<p>Non disabilitare Adobe Analytics finché non hai acquisito dimestichezza con i dati nell’ambiente Customer Journey Analytics.</p><p>**Nota:** Adobe consiglia una nuova implementazione di Web SDK per l’ambiente Customer Journey Analytics, insieme al connettore di origine di Analytics per i dati storici. [Ulteriori informazioni](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Conserva i dati storici di Adobe Analytics | Adobe consiglia di mantenere l’ambiente Adobe Analytics in posizione con il connettore di origine Analytics per un periodo di tempo dopo l’esecuzione e la raccolta dei dati del nuovo ambiente Customer Journey Analytics. Questo è il modo migliore per inserire i dati storici Adobe Analytics in Customer Journey Analytics.<p>Dopo aver raccolto una quantità sufficiente di dati storici in Customer Journey Analytics con la nuova implementazione di Web SDK, puoi rimuovere completamente il connettore di origine di Analytics. Puoi farlo quando utilizzi esclusivamente i dati storici raccolti con la nuova implementazione di Customer Journey Analytics Web SDK.</p><p>**Nota:** Adobe consiglia una nuova implementazione di Web SDK per l’ambiente Customer Journey Analytics, insieme al connettore di origine di Analytics per i dati storici. [Ulteriori informazioni](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Utilizza i feed di dati o altre funzioni di Adobe Analytics | Una piccola serie di funzioni non è ancora completamente disponibile in Customer Journey Analytics. Se hai bisogno di accedere a queste funzioni, potrebbe essere necessario utilizzare Adobe Analytics insieme a Customer Journey Analytics fino a quando non saranno disponibili. <p>Le funzioni non completamente disponibili in Customer Journey Analytics includono Feed di dati e Analisi dei contributi. Per un elenco completo delle funzioni non ancora disponibili, consulta [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Processo e timeline per la disattivazione di Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Disattivare un sistema di gestione tag di terze parti"
>abstract="Con i dati di Web SDK completamente funzionanti, collabora con il tuo amministratore di tag per rimuovere la libreria di AppMeasurement dal sistema di gestione di tag di terze parti.<br><br>Il tempo stimato per l’esecuzione di questo passaggio dipende dalla semplicità con cui è possibile disabilitare AppMeasurement dal prodotto di gestione dei tag, nonché dal ciclo di rilascio utilizzato dall’organizzazione per distribuire e gestire il codice dei tag."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Disattivare l’estensione Analytics nei tag"
>abstract="Con i dati di Web SDK completamente funzionanti, rivolgiti all’amministratore dei tag per rimuovere l’estensione Adobe Analytics dalla proprietà tag. Prima di eseguire questa operazione, assicurati che gli utenti siano passati dall’utilizzo di Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Disattiva la raccolta dati API per Adobe Analytics"
>abstract="Con i dati di Web SDK completamente funzionanti, collabora con il team di progettazione applicabile per rimuovere il codice Adobe Analytics dal progetto. Prima di eseguire questa operazione, assicurati che gli utenti siano passati dall’utilizzo di Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

L’implementazione di Adobe Analytics esistente è un elemento chiave per la riuscita dell’aggiornamento a Customer Journey Analytics, come descritto nella sezione precedente [Utilizzi di Adobe Analytics durante e dopo un aggiornamento](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Quando non hai più bisogno di Adobe Analytics per gli scopi descritti nella sezione precedente, utilizza le seguenti informazioni per rimuovere Adobe Analytics:

1. Interrompi la raccolta di dati con Adobe Analytics.

   Dopo aver effettuato con soddisfazione i confronti affiancati dei dati di Adobe Analytics e di Customer Journey Analytics, puoi interrompere la raccolta dei dati con l’implementazione di Adobe Analytics. I nuovi dati di Adobe Analytics non verranno più trasmessi a Customer Journey Analytics tramite il connettore di origine di Analytics.

   Tuttavia, i dati raccolti dall’ambiente Adobe Analytics prima di questo punto sono ancora disponibili come dati storici in Customer Journey Analytics tramite il connettore di origine di Analytics.

   Questo processo varia a seconda del metodo di raccolta dei dati utilizzato per implementare Adobe Analytics:

+++ AppMeasurement

   [Disabilita la raccolta dati di AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Estensione di Analytics (tag)

   Disattiva l’estensione Analytics nei tag.

+++

+++ API

   Disabilita la raccolta dati delle API.

+++

+++ Terze parti

   Rivolgiti all’amministratore dei tag per rimuovere la libreria AppMeasurement dal sistema di gestione dei tag di terze parti.

+++

1. Rimuovi Adobe Analytics come servizio dallo stream di dati.

   Con i dati di Web SDK completamente funzionanti, rivolgiti all’amministratore di Platform per rimuovere Adobe Analytics come servizio dallo stream di dati.

   Prima di rimuovere Adobe Analytics come servizio, accertati che gli utenti di Analytics utilizzino Customer Journey Analytics e non Adobe Analytics.

1. Rimuovi completamente il connettore di origine di Analytics

   Dopo aver raccolto una quantità sufficiente di dati storici in Customer Journey Analytics con la nuova implementazione di Web SDK, puoi rimuovere completamente il connettore di origine di Analytics.

   Esegui questa operazione quando non hai più bisogno dei dati storici dal tuo ambiente Adobe Analytics tramite il connettore di origine di Analytics e puoi affidarti esclusivamente ai dati storici raccolti con la nuova implementazione di Web SDK.

{{upgrade-final-step}}

