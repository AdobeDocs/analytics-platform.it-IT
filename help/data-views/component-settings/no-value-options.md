---
title: Impostazioni dei componenti nelle opzioni “Nessun valore”
description: Determina come gestire una dimensione se è vuota.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 64%

---

# Impostazioni dei componenti nelle opzioni “Nessun valore” {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="Opzioni per “Nessun valore”"
>abstract="Configura il comportamento predefinito quando in una dimensione non è presente alcun valore."

<!-- markdownlint-enable MD034 -->


[!UICONTROL No value options] consente di determinare come Analysis Workspace gestisce le situazioni in cui un evento in un set di dati contiene una metrica ma la dimensione non contiene un valore. Puoi scegliere il nome di tale elemento dimensione, nasconderlo completamente o anche considerarlo come un valore effettivo.

![Opzioni per “Nessun valore”](../assets/no-value-options.png)

## Impostazioni {#settings}

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL If shown, call "No value"]** | Campo di testo che consente di rinominare l’elemento dimensione **[!UICONTROL No value]** con altro nome. |
| **[!UICONTROL Don't show "No value" by default]** | Questo valore non viene visualizzato nella generazione rapporti. Le occorrenze della metrica non collegate a questa dimensione non sono visibili nel rapporto. |
| **[!UICONTROL Show "No value" by default]** | Mostra questo valore nella generazione rapporti. |
| **[!UICONTROL Treat "No value" as a value]** | (Non supportato per le dimensioni numeriche) Sostituisce i valori vuoti nei dati con il testo specificato in [!UICONTROL If shown, call "No value"]. Ad esempio, se la dimensione è rappresentata dai tipi di dispositivi mobili, puoi rinominare l’elemento **[!UICONTROL No value]** in “Desktop”. Quando modifichi questo campo in un valore personalizzato, tale valore viene considerato come un valore stringa legittimo. Pertanto, se in questo campo immetti il valore “Rosso”, tutte le istanze della stringa “Rosso” che compaiono nei dati stessi vengono raccolte sotto la stessa riga che hai specificato. |

## Supporto di &quot;Nessun valore&quot; per dimensioni numeriche {#numeric}

Quando utilizzi un valore numerico come dimensione, puoi

* Configura l’opzione &quot;Nessun valore&quot; in una visualizzazione dati. Tutte le impostazioni di configurazione mostrate sopra sono supportate ad eccezione di **[!UICONTROL Treat "No value" as a value]**.
* Utilizzare **[!UICONTROL Include "No value"]** per le dimensioni numeriche in una tabella a forma libera in Workspace.
* Nel Generatore di segmenti, utilizza gli operatori **[!UICONTROL exists]** o **[!UICONTROL does not exist]** con dimensioni numeriche.


>[!MORELIKETHIS]
>
>Ecco un post di blog correlato su [gestione di “nessun valore” in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).

