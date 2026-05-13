---
title: Editor di componenti condivisi
description: Creare o modificare dimensioni e metriche condivise.
exl-id: 3f6a808a-d6ac-4a47-a5e2-63b9f17952e8
TQID: https://experienceleague.adobe.com/vHmMlOpgjLAVzEg9t-MORtrHKsbqBABVcDFkuMlo5FM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 0%

---

# Editor di componenti condivisi

L’editor dei componenti condivisi consente di creare o modificare dimensioni e metriche condivise. Condivide molti elementi dell&#39;interfaccia utente quando [crea o modifica una visualizzazione dati](/help/data-views/create-dataview.md), ma queste interfacce sono distinte nello scopo:

* L’editor dei componenti della visualizzazione dati consente di creare e modificare componenti specifici di tale visualizzazione dati. Non è possibile modificare le dimensioni o le metriche condivise nell’editor dei componenti della visualizzazione dati. In questa interfaccia, le dimensioni e le metriche condivise possono essere identificate da un&#39;icona ![Componente condiviso](/help/assets/icons/CCLibrary.svg) accanto al nome del componente.
* L’editor dei componenti condivisi consente di creare e modificare dimensioni e metriche condivise. Non è possibile modificare i componenti che appartengono a una singola visualizzazione dati nell’editor di componenti condivisi.

![Schermata dell&#39;editor componenti](assets/component-editor.png)

In alto a destra sono presenti tre pulsanti:

* **[!UICONTROL Chiudi]** o **[!UICONTROL Annulla]**: se tutte le modifiche vengono salvate, il pulsante **[!UICONTROL Chiudi]** chiude l&#39;editor. Se sono presenti modifiche non salvate, il pulsante **[!UICONTROL Annulla]** chiude l&#39;editor senza salvare le modifiche.
* **[!UICONTROL Salva]**: salva tutti i componenti e mantiene aperto l&#39;editor.
* **[!UICONTROL Salva e termina]**: salva tutti i componenti e chiude l&#39;editor.

L’interfaccia include tre colonne/sezioni principali:

* **Selettore campo schema**: individua i campi schema desiderati e trascinali nell&#39;area dei componenti inclusi.
   * **Connessione**: la connessione attiva. Cambia la connessione attiva in [Gestione metriche e dimensioni condivise](smd-overview.md).
   * **Elenco componenti**: puoi scegliere se selezionare [!UICONTROL Campi schema] (al netto di nuove dimensioni e metriche condivise) o [!UICONTROL Metriche e dimensioni] (componenti condivisi esistenti) dal menu a discesa.
   * **Ricerca**: utilizza la ricerca di testo ![icona di ricerca](/help/assets/icons/Search.svg) per individuare il campo dello schema desiderato o il componente condiviso per nome. È inoltre possibile utilizzare i filtri ![icona filtro](/help/assets/icons/Filter.svg) per limitare l&#39;elenco dei componenti. Il filtro `Is not deprecated` è attivo per impostazione predefinita.
   * **Crea campo derivato**: consente di [creare un campo derivato](/help/data-views/derived-fields/derived-fields.md).
* **Componenti inclusi**: i componenti configurati per essere condivisi. Durante la creazione di componenti condivisi, puoi trascinare più di un campo schema in quest’area per creare più componenti contemporaneamente. Quando modifichi i componenti condivisi, puoi selezionare più componenti da modificare, in cui sono elencati tutti i componenti selezionati in quest’area.
* **Impostazioni componente**: quando si seleziona un componente nell&#39;area Componenti inclusi, è possibile configurare in questa colonna tutte le impostazioni disponibili. Vedere [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) per tutte le opzioni disponibili per dimensioni e metriche. Maiusc + clic su più elementi nell’area dei componenti inclusi consente di modificare contemporaneamente tutti i campi più comuni.
