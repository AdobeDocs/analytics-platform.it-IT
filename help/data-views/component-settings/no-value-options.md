---
title: Nessuna impostazione del componente Opzioni valore
description: Determina come gestire una dimensione se è vuota.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---


# Nessuna impostazione del componente Opzioni valore

Nessuna opzione di valore consente di determinare come Analysis Workspace gestisce le situazioni in cui un evento in un set di dati contiene una metrica ma la dimensione non contiene un valore. Puoi scegliere il nome dell’elemento dimensione, nasconderlo completamente o persino trattarlo come valore effettivo.

![Nessuna opzione di valore](../assets/no-value-options.png)

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL If shown, call "No value"] | Campo di testo che consente di rinominare l’elemento **[!UICONTROL No value]** della dimensione in un altro elemento. |
| [!UICONTROL Don't show No value by default] | Questo valore non viene visualizzato nel rapporto. Le occorrenze della metrica non collegate a questa dimensione non sono visibili nel rapporto. |
| [!UICONTROL Show No value by default] | Mostra questo valore nel reporting. |
| [!UICONTROL Treat No value as a value] | Sostituisce i valori vuoti nei dati con il testo specificato in [!UICONTROL If shown, call "No value"]. Ad esempio, se la dimensione include tipi di dispositivi mobili, puoi rinominare l’elemento **[!UICONTROL No value]** in &quot;Desktop&quot;. Quando si modifica questo campo in un valore personalizzato, il valore personalizzato viene considerato come un valore stringa legittimo. Pertanto, se si immette il valore &quot;Rosso&quot; in questo campo, tutte le istanze della stringa &quot;Rosso&quot; che compaiono nei dati stessi vengono rotolate sotto la stessa riga specificata. |
