---
description: Utilizza i sottotitoli intelligenti per generare informazioni sul linguaggio naturale e far emergere rapidamente le tendenze all’interno delle visualizzazioni.
title: Sottotitoli intelligenti
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 1%

---

# Sottotitoli intelligenti

I sottotitoli intelligenti utilizzano l’apprendimento automatico avanzato e l’intelligenza artificiale generativa per fornire informazioni preziose sul linguaggio naturale per le visualizzazioni di Workspace. La versione iniziale fornisce informazioni generate automaticamente per [Linea](line.md) visualizzazione. Seguiranno altre visualizzazioni.

I sottotitoli intelligenti sono orientati verso:

* Analisti che hanno bisogno di narrazioni da condividere con altri utenti. Gli analisti hanno bisogno di queste informazioni per fornire contesto ai loro utenti.
* Utenti aziendali che desiderano scoprire rapidamente soluzioni di alto livello.

I sottotitoli sono disponibili per tutti gli utenti del Customer Journey Analytics e non richiedono autorizzazioni speciali.

## Avvia sottotitoli intelligenti {#launch}

Per avviare i sottotitoli generati automaticamente per una visualizzazione delle linee, fai clic sul pulsante **[!UICONTROL Intelligent captions]** in alto a destra nella visualizzazione.

![Finestra di analisi dell&#39;avvio che mostra la tendenza dei sottotitoli intelligenti per le visualizzazioni del prodotto. ](assets/intell-caps-1.png)

Vengono ora generate informazioni sul linguaggio naturale.

Nota bene

* Sono necessari almeno 3 punti dati per generare correttamente i sottotitoli. In caso contrario, potrebbe venire visualizzato un messaggio di errore che indica &quot;Dati insufficienti per l&#39;analisi&quot;.

* Le didascalie vengono generate ogni volta che i dati selezionati sottostanti cambiano nella tabella che alimenta la visualizzazione.

* Se la tabella contiene più metriche, le didascalie vengono generate solo per la prima metrica o per la metrica attualmente selezionata dall’utente.

* Se salvi il progetto a questo punto e lo ricarichi in un secondo momento, i sottotitoli vengono aggiornati automaticamente con i nuovi dati. Lo stesso vale per i progetti programmati e i file PDF esportati da questo progetto.

## Visualizzare e interpretare i sottotitoli {#view}

Ecco un esempio di sottotitoli:

![Didascalie intelligenti per la visualizzazione delle linee, tra cui Stagionalità, Min, Max, Spike e Declino.](assets/captions.png)

## Copia negli Appunti {#copy}

È possibile copiare i sottotitoli negli Appunti e incollarli in un Powerpoint o in un altro strumento. Trova il **[!UICONTROL Copy captions to clipboard]** in alto a destra nella finestra di dialogo sottotitoli.

## Modifica didascalie {#edit}

Puoi modificare i sottotitoli, ad esempio per nascondere o rendere visibile una particolare categoria di informazioni. Ad esempio, se non desideri conoscere l’ordine minimo, puoi semplicemente nasconderlo e fare clic su Applica, ma non verrà più visualizzato.

1. Clic **[!UICONTROL Edit intelligent captions display]** accanto all&#39;icona degli Appunti.

1. Nella finestra di dialogo per modifica, fai clic sull’icona dell’occhio accanto all’informazione che desideri nascondere.

1. Fai clic su **[!UICONTROL Apply]**.

Utilizza lo stesso processo per mostrare le didascalie.

## Esporta sottotitoli {#export}

È possibile **esportare sottotitoli tramite PDF**, purché il progetto venga salvato con i sottotitoli generati.

## Disattiva sottotitoli {#toggle}

Se preferisci che non vengano generati sottotitoli intelligenti, puoi disattivare questa funzione dalle Preferenze di visualizzazione e deselezionare **[!UICONTROL Show intelligent captions]**.

![Opzioni di visualizzazione delle linee con l’opzione per deselezionare Mostra sottotitoli intelligenti.](assets/toggle-captions.png)

## Sottotitoli intelligenti nelle scorecard per dispositivi mobili

I sottotitoli intelligenti sono disponibili anche in Customer Journey Analytics [scorecard per dispositivi mobili](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).