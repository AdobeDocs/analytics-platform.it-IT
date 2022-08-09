---
title: Supporto di CJA per la governance dei dati di Adobe Experience Platform
description: Scopri in che modo le etichette dati e i criteri definiti in AEP influiscono sul reporting in CJA.
mini-toc-levels: 3
source-git-commit: 82060862c64aae10ea6dd375a8cd65d67ee21704
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 1%

---


# Supporto di CJA per la governance dei dati di Adobe Experience Platform

>[!NOTE]
>
>Questa funzionalità è attualmente in [fase di test](/help/release-notes/releases.md).

Integrazione tra CJA e [Governance dei dati di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) consente l’etichettatura dei dati CJA sensibili e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di CJA. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili.

Inoltre, quando i dati vengono esportati da CJA (tramite reporting, esportazione, API ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti CJA possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

## Etichette e criteri in Adobe Experience Platform

Quando crei un set di dati in Experience Platform, puoi creare [etichette di utilizzo dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) per alcuni o tutti gli elementi del set di dati. Finora, queste etichette non erano esposte in CJA. Con questa versione, puoi visualizzare queste etichette in CJA. Di particolare interesse per CJA sono le seguenti etichette:

* La `C8` etichetta **[!UICONTROL No measurement]**. Questa etichetta indica che i dati non possono essere utilizzati per analisi sui siti web o sulle app dell’organizzazione.

* La `C12` etichetta **[!UICONTROL No General Data Export]**. I campi dello schema etichettati in questo modo non possono essere esportati o scaricati da CJA (tramite reporting, esportazione, API, ecc.)

L’etichettatura di per sé non significa che queste etichette di utilizzo dei dati siano applicate. Per questo vengono utilizzati i criteri. Crea i tuoi criteri tramite [API del servizio criteri](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform.

I criteri hanno due componenti: l’etichetta dei dati e un’azione di marketing che i consumatori possono intraprendere nel contesto di criteri di utilizzo dei dati limitati. Nel contesto di CJA, due Adobi definiti [azioni di marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) sono importanti:

* Analytics : utilizza i dati a scopo di analisi, ad esempio per misurare, analizzare e generare rapporti sull’utilizzo da parte del consumatore dei siti o delle app della tua organizzazione.

* Esportazione di dati a terze parti, ovvero dall’ambiente Adobe.

È possibile collegare etichette e azioni di marketing a un criterio e quindi attivare il criterio. La politica prende l&#39;etichetta e l&#39;azione di marketing e dice: applica questa restrizione. In CJA vengono visualizzati due criteri definiti in Adobe e influiscono sul reporting e sul download/condivisione:

* Applica criteri di Analytics
* Applica criterio di download


### Visualizzare le etichette dati nelle visualizzazioni dati di CJA

Le etichette dati create in Experience Platform vengono visualizzate in tre posizioni nell’interfaccia utente della visualizzazione dati:

| Posizione | Descrizione |
| --- | --- |
| Pulsante Informazioni su un campo schema | Fai clic su questo pulsante per indicare le etichette di utilizzo dei dati attualmente applicabili a un campo:<p>![](assets/data-label-left.png) |
| Barra a destra sotto [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) | Tutte le etichette di utilizzo dei dati sono elencate qui:<p>![](assets/data-label-right.png) |
| Aggiungi etichette dati come colonna | Puoi aggiungere Etichette dati come colonna alle colonne Componenti inclusi nelle visualizzazioni dati. Fai clic sull’icona del selettore colonna e seleziona Etichette di utilizzo dati:<p>![](assets/data-label-column.png) |

### Filtrare le etichette per la governance dei dati nelle visualizzazioni dati

Nell’editor delle visualizzazioni dati, fai clic sull’icona Filtro nella traccia a sinistra e filtra i componenti delle visualizzazioni dati in base alle etichette di governance dei dati:

![](assets/filter-labels.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali componenti dispongono di etichette collegate.

### Filtrare i criteri di governance dei dati nelle visualizzazioni dati

Puoi verificare se è attivato un criterio che blocca l’utilizzo di alcuni elementi di visualizzazione dati CJA per scopi di analisi o esportazione.

Di nuovo, fai clic sull’icona Filtro nella barra a sinistra e in Governance dei dati fai clic su Criteri:

![](assets/filter-policies.png)

Fai clic su **[!UICONTROL Apply]** per vedere quali criteri sono abilitati _per questa visualizzazione dati?_

### Come funziona [!UICONTROL Enforce Analytics] i criteri influiscono sui progetti Workspace

Se questo criterio è attivato, i campi dello schema a cui sono associate determinate etichette di dati (come C8) non possono essere utilizzati a scopo di analisi in CJA Workspace.

Per la generazione di rapporti, ciò significa che

* Non è possibile aggiungere questi campi alle visualizzazioni dati e sono disattivati nella barra a sinistra [!UICONTROL Schema fields] elenco.
* Non è possibile salvare una visualizzazione dati contenente campi bloccati.

Se tenti di eseguire analisi di Workspace sulle visualizzazioni di dati che contengono elementi non consentiti per Analytics, riceverai un avviso simile al seguente:

![](assets/policy-enforce.png)

Per i singoli componenti, il messaggio è simile al seguente:

![](assets/policy-enforce2.png)

### Come funziona [!UICONTROL Enforce Download] i criteri influiscono sui progetti Workspace

Se questa policy è attivata, qualsiasi download (ad esempio e-mail o condivisione di pdf) di progetti Workspace eseguirà l’hash dei campi sensibili. Puoi comunque eseguire l’analisi di questi campi in Workspace, ma se tenti di inviare un messaggio e-mail o di condividere in altro modo un progetto, i campi bloccati verranno visualizzati come elementi con hash nel file .pdf .

Aggiungi uno screenshot qui.

### Visualizza etichette nel Report Builder

Vedi _questa sezione_ per ulteriori informazioni. (link al documento di Christine)
