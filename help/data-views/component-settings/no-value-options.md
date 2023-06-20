---
title: Impostazioni dei componenti nelle opzioni “Nessun valore”
description: Determina come gestire una dimensione se è vuota.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 89%

---

# Impostazioni dei componenti nelle opzioni “Nessun valore”

Le opzioni “Nessun valore” consentono di determinare come Analysis Workspace gestisce situazioni in cui un evento in un set di dati contiene una metrica, ma la dimensione non contiene un valore. Puoi scegliere il nome di tale elemento dimensione, nasconderlo completamente o anche considerarlo come un valore effettivo.

![Opzioni per “Nessun valore”](../assets/no-value-options.png)

## Impostazioni {#settings}

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL If shown, call "No value"] | Campo di testo che consente di rinominare l’elemento dimensione **[!UICONTROL No value]** con altro nome. |
| [!UICONTROL Don't show No value by default] | Questo valore non viene visualizzato nella generazione rapporti. Le occorrenze della metrica non collegate a questa dimensione non sono visibili nel rapporto. |
| [!UICONTROL Show No value by default] | Mostra questo valore nella generazione rapporti. |
| [!UICONTROL Treat No value as a value] | Sostituisce i valori vuoti nei dati con il testo specificato in [!UICONTROL If shown, call "No value"]. Ad esempio, se la dimensione è rappresentata dai tipi di dispositivi mobili, puoi rinominare l’elemento **[!UICONTROL No value]** in “Desktop”. Quando modifichi questo campo in un valore personalizzato, tale valore viene considerato come un valore stringa legittimo. Pertanto, se in questo campo immetti il valore “Rosso”, tutte le istanze della stringa “Rosso” che compaiono nei dati stessi vengono raccolte sotto la stessa riga che hai specificato. |

{style="table-layout:auto"}

## Post di blog

Ecco un post correlato su [gestione di &quot;nessun valore&quot; nel Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).
