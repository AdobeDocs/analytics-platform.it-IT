---
title: Impostazioni dei componenti
description: Visualizzare le impostazioni di base di un componente visualizzazione dati.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---

# Impostazioni dei componenti

Impostazioni di base utilizzate da un componente di visualizzazione dati.

![Impostazioni dei componenti](../assets/component-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Component type] | Obbligatorio. Consente di cambiare un componente da Metrica a Dimension o viceversa. Modificando questo menu a discesa, il componente viene spostato nella rispettiva area dei componenti inclusi. |
| [!UICONTROL Component Name] | Obbligatorio. Consente di specificare il nome descrittivo visualizzato in Analysis Workspace. È possibile rinominare un componente per assegnargli un nome specifico per la visualizzazione dati. |
| [!UICONTROL Description] | Facoltativo ma consigliato. Fornisce informazioni sul componente ad altri utenti. |
| [!UICONTROL Tags] | Facoltativo. Consente di assegnare al componente tag personalizzati o predefiniti per facilitarne la ricerca e il filtraggio nell’interfaccia utente di Analysis Workspace. |
| [!UICONTROL Field Name] | Nome del campo schema. |
| [!UICONTROL Dataset type] | Obbligatorio. Un campo non modificabile che mostra il tipo di set di dati (evento, ricerca o profilo) da cui proviene il componente. |
| [!UICONTROL Dataset] | Un campo non modificabile che mostra da quale set di dati proviene il componente. Questo campo può contenere più set di dati. |
| [!UICONTROL Schema Type] | Campo non modificabile che mostra il tipo di dati del componente.  Anche se è possibile utilizzare qualsiasi tipo di campo di schema supportato in Platform, non tutti i tipi di campi sono supportati in CJA. Sono supportati i seguenti tipi di dati: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`e `Boolean`. Solo il `String` il tipo di dati dello schema è consentito nei set di dati di ricerca in questo momento. |
| [!UICONTROL Component ID] | Obbligatorio. La [API CJA](https://adobe.io/cja-apis/docs) utilizza questo campo per fare riferimento al componente. Ogni componente in una visualizzazione dati deve essere univoco. Adobe genera automaticamente un ID per ogni componente; tuttavia, puoi fare clic sull’icona di modifica e modificare l’ID del componente. La modifica dell’ID del componente interrompe tutti i progetti Workspace esistenti che contengono questo componente. Sebbene ogni componente abbia bisogno di un ID univoco in una singola visualizzazione dati, puoi usare lo stesso ID componente in altre visualizzazioni dati. Se utilizzi lo stesso ID componente in altre visualizzazioni dati, puoi rendere i progetti Workspace compatibili tra le visualizzazioni dati. |
| [!UICONTROL Path] | Obbligatorio. Un campo non modificabile che mostra il percorso dello schema da cui proviene il componente. |
| [!UICONTROL Data Usage Labels] | Tutte le etichette di utilizzo dei dati assegnate a questo componente in Adobe Experience Platform. Ulteriori informazioni |
| [!UICONTROL Hide component in reporting] | Consente di eliminare il componente dalla visualizzazione dati per i non amministratori. Gli amministratori possono comunque accedervi facendo clic su [!UICONTROL Show All Components] in un progetto Analysis Workspace. |

{style=&quot;table-layout:auto&quot;}

Ecco un video sulle impostazioni dei componenti nelle visualizzazioni dati:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
