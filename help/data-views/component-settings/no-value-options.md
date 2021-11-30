---
title: Nessuna impostazione del componente Opzioni valore
description: Determina come gestire una dimensione se è vuota.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%

---

# Nessuna impostazione del componente Opzioni valore

Nessuna opzione di valore consente di determinare come Analysis Workspace gestisce le situazioni in cui un evento in un set di dati contiene una metrica ma la dimensione non contiene un valore. Puoi scegliere il nome dell’elemento dimensione, nasconderlo completamente o persino trattarlo come valore effettivo.

![Opzioni per “Nessun valore”](../assets/no-value-options.png)

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL If shown, call "No value"] | Campo di testo che consente di rinominare il **[!UICONTROL No value]** elemento dimensionale a qualcos&#39;altro. |
| [!UICONTROL Don't show No value by default] | Questo valore non viene visualizzato nel rapporto. Le occorrenze della metrica non collegate a questa dimensione non sono visibili nel rapporto. |
| [!UICONTROL Show No value by default] | Mostra questo valore nel reporting. |
| [!UICONTROL Treat No value as a value] | Sostituisce i valori vuoti nei dati con il testo specificato in [!UICONTROL If shown, call "No value"]. Ad esempio, se la dimensione contiene tipi di dispositivi mobili, puoi rinominare il **[!UICONTROL No value]** da &quot;Desktop&quot;. Quando si modifica questo campo in un valore personalizzato, il valore personalizzato viene considerato come un valore stringa legittimo. Pertanto, se si immette il valore &quot;Rosso&quot; in questo campo, tutte le istanze della stringa &quot;Rosso&quot; che compaiono nei dati stessi vengono rotolate sotto la stessa riga specificata. |
