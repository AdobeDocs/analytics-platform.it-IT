---
title: Etichette e criteri
description: Scopri in che modo le etichette per dati e i criteri definiti in Adobe Experience Platform influiscono sulle visualizzazioni dati e sul reporting in Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: ht
source-wordcount: '539'
ht-degree: 100%

---

# Etichette e criteri

Quando crei un set di dati in Experience Platform, puoi creare [etichette di utilizzo dei dati](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/reference) per alcuni o tutti gli elementi del set di dati. Puoi visualizzare queste etichette e criteri in Customer Journey Analytics.

Le seguenti etichette sono di particolare interesse per Customer Journey Analytics:

* L&#39; `C8` etichetta **[!UICONTROL No measurement]**. Questa etichetta indica che i dati non possono essere utilizzati per analisi sui siti web o sulle app dell’organizzazione.

* L&#39; `C12` etichetta **[!UICONTROL No general data export]**. I campi dello schema etichettati in questo modo non possono essere esportati o scaricati da Customer Journey Analytics (tramite reporting, esportazione, API, ecc.)

>[!NOTE]
>
>Le etichette di utilizzo dei dati non vengono propagate automaticamente ai set di dati uniti. Tuttavia, possono essere aggiunte manualmente.

L’etichettatura di per sé non significa che queste etichette di utilizzo dei dati siano applicate. Per questo vengono utilizzati i criteri. Puoi creare i tuoi criteri utilizzando l’[Interfaccia utente Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/policies/user-guide) o tramite l’[API di Privacy Service](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/api/overview) in Experience Platform.

In Adobe sono disponibili due criteri definiti da Experience Platform che possono emergere in Customer Journey Analytics e influire sul reporting e sull’esportazione dei dati:

* Il criterio **[!UICONTROL Restrict usage analytics and user based measurement]**, utilizzando l’etichetta `C8` e
* il criterio **[!UICONTROL Restrict data export]**, utilizzando l’etichetta `C12`.

## Visualizzare le etichette dati nelle visualizzazioni dati di Customer Journey Analytics

Le etichette dati create da te o da altri in Experience Platform vengono visualizzate in tre aree nell’interfaccia utente della visualizzazione dati:

| Posizione | Descrizione |
| --- | --- |
| Pulsante Informazioni su un campo schema | Fai clic su questo pulsante per indicare le [!UICONTROL Data Usage Labels] attualmente applicabili a un campo:<p>![](assets/data-label-left.png) |
| Barra a destra sotto [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) | Tutte le [!UICONTROL Data Usage Labels] sono elencate qui:<p>![](assets/data-label-right.png) |
| Aggiungi etichette dati come colonna | Puoi aggiungere una colonna [!UICONTROL Data Usage Labels] alle colonne dei [!UICONTROL Included Components] nelle visualizzazioni dati. Seleziona l’icona del selettore colonne, quindi **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrare le etichette per la governance dei dati nelle visualizzazioni dati

Nell’editor delle visualizzazioni dati, seleziona l’icona [!UICONTROL filter] nella barra a sinistra e filtra i componenti delle visualizzazioni dati in base alla **[!UICONTROL Data Governance]** e al tipo di **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali componenti dispongono di etichette collegate.

## Filtrare i criteri di governance dei dati nelle visualizzazioni dati

Puoi verificare se un criterio (ad esempio, un criterio creato, denominato **[!UICONTROL Enforce Analytics]**) è attivato. E se tale criterio blocca l’utilizzo di determinati elementi di visualizzazione dati di Customer Journey Analytics per l’analisi o l’esportazione di dati.

Di nuovo, seleziona l’icona [!UICONTROL filter] nella barra a sinistra e in **[!UICONTROL Data Governance]** seleziona **[!UICONTROL Policies]**:

![Filtra i componenti inclusi per elenco, mostrando la selezione dell’analisi di Limita utilizzo e delle misurazione basata sull’utente](assets/filter-policies.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali criteri sono abilitati.

## Effetti dei criteri abilitati sulle visualizzazioni dati

Se uno o più criteri sono attivati con etichette C8 o C12, i componenti dello schema a cui sono applicate determinate etichette dati non possono essere aggiunti alle visualizzazioni dati.

Questi componenti sono disattivati nell’elenco [!UICONTROL Schema fields] della barra a sinistra:

![I componenti disattivati e il messaggio Criteri che indica l’applicazione dei criteri a questo campo limitando l’utilizzo dei dati](assets/component-greyed.png)

Inoltre, non è possibile salvare una visualizzazione dati contenente campi bloccati.

Prova ad applicare etichette di accesso e governance dei dati (tramite criteri) ai campi o ai gruppi di campi di Experience Platform, per i quali hai già definito dei componenti nella visualizzazione dati. Potrebbe essere visualizzata questa finestra di dialogo.

![Violazione](assets/violation.png)

Devi innanzitutto risolvere la violazione (ad esempio rimuovere i componenti dalla visualizzazione dati).


>[!MORELIKETHIS]
>
>[Scaricare dati sensibili](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Cosa sono le etichette per limitazioni in Report Builder?](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


