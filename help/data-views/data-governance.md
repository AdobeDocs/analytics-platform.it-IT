---
title: Etichette e politiche
description: Scopri in che modo le etichette dati e i criteri definiti in AEP influiscono sulle visualizzazioni dati e sui rapporti in CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 56%

---

# Etichette e politiche

Quando crei un set di dati in Experience Platform, puoi creare [etichette di utilizzo dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=it) per alcuni o tutti gli elementi del set di dati. Finora, queste etichette non erano esposte in CJA. Con questa versione, puoi visualizzare queste etichette e criteri in CJA.

Di particolare interesse per CJA sono le seguenti etichette:

* L&#39; `C8` etichetta **[!UICONTROL No measurement]**. Questa etichetta indica che i dati non possono essere utilizzati per analisi sui siti web o sulle app dell’organizzazione.

* L&#39; `C12` etichetta **[!UICONTROL No General Data Export]**. I campi dello schema etichettati in questo modo non possono essere esportati o scaricati da CJA (tramite reporting, esportazione, API, ecc.)

L’etichettatura di per sé non significa che queste etichette di utilizzo dei dati siano applicate. Per questo vengono utilizzati i criteri. Crea i tuoi criteri tramite [API del servizio criteri](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=it) in Experience Platform.

In CJA vengono visualizzati due criteri definiti in Adobe e influiscono sul reporting e sul download/condivisione:

* **[!UICONTROL Enforce Analytics]** policy
* **[!UICONTROL Enforce Download]** policy

## Visualizzare le etichette dati nelle visualizzazioni dati di CJA

Le etichette dati create in Experience Platform vengono visualizzate in tre posizioni nell’interfaccia utente della visualizzazione dati:

| Posizione | Descrizione |
| --- | --- |
| Pulsante Informazioni su un campo schema | Fai clic su questo pulsante per indicare quale [!UICONTROL Data Usage Labels] attualmente applicabile a un campo:<p>![](assets/data-label-left.png) |
| Barra a destra sotto [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) | Qualsiasi [!UICONTROL Data Usage Labels] sono elencati qui:<p>![](assets/data-label-right.png) |
| Aggiungi etichette dati come colonna | Puoi aggiungere [!UICONTROL Data Usage Labels] come colonna del [!UICONTROL Included Components] nelle visualizzazioni dati. Fai clic sull’icona del selettore colonna e seleziona **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtrare le etichette per la governance dei dati nelle visualizzazioni dati

Nell’editor delle visualizzazioni dati, fai clic sull’icona Filtro nella traccia a sinistra e filtra i componenti delle visualizzazioni dati per **[!UICONTROL Data Governance]** e il tipo di **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali componenti dispongono di etichette collegate.

## Filtrare i criteri di governance dei dati nelle visualizzazioni dati

Puoi verificare se è attivato un criterio che blocca l’utilizzo di alcuni elementi di visualizzazione dati CJA per scopi di analisi o esportazione.

Di nuovo, fai clic sull’icona Filtro nella barra a sinistra e sotto **[!UICONTROL Data Governance]**, fai clic su **[!UICONTROL Policies]**:

![](assets/filter-policies.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali criteri sono abilitati.

## Effetti dei criteri abilitati sulle visualizzazioni dati

Se la **[!UICONTROL Enforce Analytics]** o **[!UICONTROL Enforce Download]** I criteri sono attivati e i componenti dello schema a cui sono associate determinate etichette di dati (come C8 o C12) non possono essere aggiunti alle visualizzazioni dati.

Questi componenti sono disattivati nella barra a sinistra [!UICONTROL Schema fields] elenco:

![](assets/component-greyed.png)

Non è inoltre possibile salvare una visualizzazione dati contenente campi bloccati.

>[!MORELIKETHIS]
>[Scaricare dati sensibili](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Cosa sono le etichette limitate nel Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)


