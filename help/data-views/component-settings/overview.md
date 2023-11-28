---
title: Impostazioni del componente
description: Visualizzare le impostazioni di base di un componente vista dati.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 67%

---

# Impostazioni del componente

Impostazioni di base utilizzate da un componente di vista dati.

![Impostazioni dei componenti descritte in questa sezione](../assets/component-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Component type] | Obbligatorio. Consente di cambiare un componente da Metrica a Dimension o viceversa. Modificando questa selezione a discesa, il componente viene spostato nella rispettiva area dei componenti inclusi. |
| [!UICONTROL Component Name] | Obbligatorio. Consente di specificare il nome descrittivo visualizzato in Analysis Workspace. È possibile rinominare un componente per assegnargli un nome specifico per la vista dati. |
| [!UICONTROL Description] | Facoltativo ma consigliato. Fornisce informazioni sul componente ad altri utenti. |
| [!UICONTROL Tags] | Facoltativo. Consente di assegnare al componente tag personalizzati o predefiniti per facilitarne la ricerca e il filtraggio nell’interfaccia utente di Analysis Workspace. |
| [!UICONTROL Context labels] | Facoltativo. Elenco a discesa delle etichette disponibili definite dal sistema che possono essere applicate a un componente. Queste etichette possono essere necessarie per definire un set di componenti utilizzati per la generazione di rapporti nei progetti o nei pannelli di Analysis Workspace. |
| [!UICONTROL Schema field name] | Nome del campo schema. |
| [!UICONTROL Dataset type] | Obbligatorio. Un campo non modificabile che mostra il tipo di set di dati (evento, ricerca o profilo) da cui proviene il componente. |
| [!UICONTROL Dataset] | Un campo non modificabile che mostra da quale set di dati proviene il componente. Questo campo può contenere più set di dati. |
| [!UICONTROL Schema Type] | Campo non modificabile che mostra il tipo di dati del componente. Anche se è possibile utilizzare qualsiasi tipo di campo di schema supportato in Platform, non tutti i tipi di campi sono supportati in Customer Journey Analytics. Sono supportati i seguenti tipi di dati: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`e `Boolean`. Solo il `String` Il tipo di dati dello schema è attualmente consentito nei set di dati di ricerca. |
| [!UICONTROL Component ID] | Obbligatorio. Il [API CUSTOMER JOURNEY ANALYTICS](https://adobe.io/cja-apis/docs) utilizza questo campo per fare riferimento al componente. Ogni componente in una visualizzazione dati deve essere univoco. Adobe genera automaticamente un ID per ogni componente; tuttavia, puoi fare clic sull’icona di modifica e modificare l’ID del componente. La modifica dell’ID del componente interrompe tutti i progetti Workspace esistenti che contengono questo componente. Sebbene ogni componente abbia bisogno di un ID univoco in una singola visualizzazione dati, puoi usare lo stesso ID componente in altre visualizzazioni dati. Se utilizzi lo stesso ID componente in altre visualizzazioni dati, puoi rendere i progetti Workspace compatibili tra le visualizzazioni dati. <br/>Per i componenti basati su profilo e ricerca, l’ID componente ha un prefisso ID basato sull’ID del set di dati (ad esempio: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Quando desideri riutilizzare un profilo o un componente basato sulla ricerca, ad esempio `person.name.firstName`, nel progetto Workspace e configurando questo componente in diverse visualizzazioni dati, assicurati di rinominare l’ID componente in modo univoco (ad esempio: `myUniqueID.person.name.firstName`) nelle visualizzazioni dati. |
| [!UICONTROL Path] | Obbligatorio. Un campo non modificabile che mostra il percorso dello schema da cui proviene il componente. |
| [!UICONTROL Data Usage Labels] | Tutte le etichette di utilizzo dei dati assegnate a questo componente in Adobe Experience Platform. [Ulteriori informazioni](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Consente di eliminare il componente dalla visualizzazione dati per i non amministratori. Gli amministratori possono comunque accedervi facendo clic su [!UICONTROL Show All Components] in un progetto Analysis Workspace. |

{style="table-layout:auto"}

Ecco un video sulle impostazioni dei componenti nelle visualizzazioni dati:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
