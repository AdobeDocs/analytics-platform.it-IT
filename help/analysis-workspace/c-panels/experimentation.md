---
description: Scopri come analizzare i risultati dei test A/B nel pannello Sperimentazione CJA .
title: Pannello sperimentale
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Pannello sperimentale

>[!NOTE]
>
>Questa funzionalità è attualmente in [fase di test](/help/release-notes/releases.md).

La **[!UICONTROL Experimentation]** ti consente di confrontare diverse varianti di esperienza utente, marketing o messaggistica per determinare quale sia meglio guidare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, Adobe Journey Optimizer e persino i dati BYO (risorse disponibili).

>[!IMPORTANT]
>
>A questo punto, [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) (A4T) I dati non possono essere valutati nel [!UICONTROL Experimentation] pannello.

## Controllo degli accessi

Il pannello Sperimentazione è disponibile per tutti gli utenti del Customer Journey Analytics (CJA). Non sono necessari diritti di amministratore o altre autorizzazioni. Tuttavia, la configurazione richiede etichette nelle visualizzazioni dati che solo gli amministratori possono assegnare.

## Terminologia

* **Esperimento**: Un esperimento è un insieme di varianti di un’esperienza che è stata esposta agli utenti finali per determinare quale sia meglio mantenere in perpetuità. Un esperimento è costituito da due o più varianti, una delle quali è considerata la variazione di controllo.

* **Variazione**: Una delle due o più modifiche nell&#39;esperienza di un utente finale che vengono confrontate allo scopo di identificare l&#39;alternativa migliore. Una variante deve essere selezionata come controllo e una sola variante può essere considerata come la variante di controllo.

* **Controllo**: Una variazione specifica che rappresenta lo status quo o lo stato predefinito dell’esperienza di un utente. A cosa vengono confrontate tutte le altre variazioni.

* **Normalizzazione della metrica**: Base (sessioni o persone) in cui verrà eseguito un test. Ad esempio, un test può confrontare i tassi di conversione di diverse varianti quando il tasso di conversione è calcolato come conversioni per sessione o conversioni per persona.

* **Metrica di conversione**: La metrica con cui un utente confronta le varianti. La variante con il risultato più auspicabile per la metrica di conversione (sia più alta che più bassa) è dichiarata &quot;vincitrice&quot; di un esperimento.

## Passaggio 1: Creare una connessione per sperimentare i set di dati

Dopo che i dati dell&#39;esperimento sono stati [acquisito](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) in Adobe Experience Platform, [creare una connessione in CJA](/help/connections/create-connection.md) a uno o più set di dati di prova.

## Passaggio 2: Aggiungere etichette di contesto nelle visualizzazioni dati

Nelle impostazioni delle visualizzazioni dati di CJA, gli amministratori possono aggiungere [etichette di contesto](/help/data-views/component-settings/overview.md) a una dimensione o a una metrica e ai servizi CJA come [!UICONTROL Experimentation] possono utilizzare queste etichette per i loro scopi. Per il pannello Sperimentazione vengono utilizzate due etichette predefinite:

* [!UICONTROL Experiment]
* [!UICONTROL Variant]

Nella visualizzazione dati che contiene dati di sperimentazione, scegli due dimensioni, una con i dati di sperimentazione e una con i dati della variante. Quindi etichettate queste dimensioni con il **[!UICONTROL Experiment]** e **[!UICONTROL Variant]** etichette.

![etichetta di contesto](assets/context-label.png)

Senza queste etichette presenti, il pannello Esperimento non funziona.

## Passaggio 3: Configurare il pannello Esperimento

1. In CJA Workspace, trascina il pannello Sperimentazione in un progetto.

![pannello sperimentale](assets/experiment.png)




