---
title: Creare Collegamenti Ipertestuali Per Le Dimensioni In Una Tabella A Forma Libera
description: Scopri come creare collegamenti ipertestuali per gli elementi dimensionali in una tabella a forma libera in Analysis Workspace.
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 97%

---

# Creare collegamenti ipertestuali

In Analysis Workspace puoi creare collegamenti ipertestuali per elementi dimensionali per renderli cliccabili all’interno di una tabella a forma libera.

Questa funzionalità è particolarmente utile quando si creano collegamenti ipertestuali per i seguenti tipi di elementi dimensionali:

* Elementi dimensionali con valori URL (ad esempio, una dimensione URL di pagina).

* Elementi dimensionali che contengono raggruppamenti con valori URL (ad esempio, una dimensione Nome pagina con raggruppamento di una dimensione URL di pagina).

* Elementi dimensionali o raggruppamenti con valori che fanno parte di un URL (ad esempio, una dimensione Nome pagina che fa parte di un URL).


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta, ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare collegamenti ipertestuali in una tabella a forma libera](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Creare collegamenti ipertestuali

Quando crei collegamenti ipertestuali per uno o più elementi dimensionali, considera quanto segue:

* I collegamenti ipertestuali creati vengono memorizzati nella tabella a forma libera all’interno del progetto Analysis Workspace. I collegamenti ipertestuali non persistono quando utilizzi gli stessi elementi dimensionali o la stessa dimensione in un’altra tabella o altro progetto.

* Se modifichi la visualizzazione dati della tabella a forma libera, tutti i collegamenti ipertestuali creati per le dimensioni o gli elementi dimensionali saranno ancora disponibili nella tabella. Questa funzionalità presuppone che la dimensione esista ancora nella visualizzazione dati.

* La validità degli URL non viene verificata durante la creazione del collegamento ipertestuale. Se

   * crei un collegamento ipertestuale con un URL non valido oppure
   * crei un collegamento ipertestuale con riferimento a un elemento dimensionale che non ha un valore URL (facendo riferimento direttamente all’elemento dimensionale o utilizzando le variabili `$value` o `$breakdown`),

  gli utenti che fanno clic sul collegamento ipertestuale visualizzano un messaggio di errore in cui viene indicato che l’URL non è valido.

* I collegamenti ipertestuali creati per un singolo elemento dimensionale sovrascrivono quelli creati sulla dimensione.

* I collegamenti ipertestuali non funzionano nei [file PDF scaricati](/help/analysis-workspace/export/download-send.md).

Per creare collegamenti ipertestuali per uno o più elementi dimensionali:

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Crea un collegamento ipertestuale per un singolo elemento dimensionale:** fai clic con il pulsante destro del mouse sull’elemento dimensionale all’interno della tabella per il quale desideri creare il collegamento ipertestuale, quindi seleziona [!UICONTROL **Crea collegamento ipertestuale**].

      1. Apri il menu di scelta rapida per l’elemento dimensionale.
      1. Seleziona [!UICONTROL **Crea collegamento ipertestuale**] dal menu di scelta rapida.

         Viene visualizzata la finestra di dialogo [!UICONTROL **Crea collegamento ipertestuale**]. Il nome dell’elemento dimensionale per il quale stai creando un collegamento ipertestuale viene visualizzato nella finestra di dialogo.

         ![Creare il collegamento ipertestuale per la finestra di dialogo di un singolo elemento](assets/hyperlink-dialog-single.png)

   * **Crea collegamenti ipertestuali per tutti gli elementi dimensionali nella colonna di una dimensione:** fai clic con il pulsante destro del mouse sul nome della dimensione nell’intestazione della colonna della dimensione, quindi seleziona [!UICONTROL **Crea collegamenti ipertestuali per tutti gli elementi dimensionali**].

      1. Apri il menu di scelta rapida dall’intestazione della colonna della dimensione.
      1. Seleziona [!UICONTROL **Crea collegamento ipertestuale per tutti gli elementi dimensionali**] dal menu di scelta rapida.

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         Viene visualizzata la finestra di dialogo [!UICONTROL **Crea collegamenti ipertestuali per tutti gli elementi dimensionali**]. Il nome della dimensione per la quale stai creando collegamenti ipertestuali viene visualizzato nella finestra di dialogo.

         ![Finestra di dialogo per la creazione di collegamenti ipertestuali](assets/hyperlink-dialog-multiple.png)

1. Scegli tra le seguenti opzioni:

   * [!UICONTROL **Utilizza il valore dell’elemento dimensionale come URL**]: scegli questa opzione per gli elementi dimensionali che hanno valori URL, ad esempio una dimensione URL di pagina.

     Ad esempio, se utilizzi una dimensione URL di pagina in cui il valore di ogni elemento dimensionale è un URL, selezionando questa opzione viene creato un collegamento ipertestuale all’URL.

   * [!UICONTROL **Crea un URL personalizzato**]: specifica un URL personalizzato statico o dinamico. Scegli questa opzione per creare collegamenti ipertestuali per gli elementi dimensionali che non hanno valori URL.

     Ad esempio: utilizzi una dimensione Nome pagina in cui il valore di ciascun elemento dimensionale è il nome di una pagina (e non un URL completo). Quindi seleziona questa opzione per specificare un collegamento ipertestuale da utilizzare come collegamento per l’elemento dimensionale.

     Se desideri creare URL dinamici per più elementi dimensionali, puoi utilizzare le variabili `$value` e `$breakdown` nell’URL personalizzato. Per ulteriori informazioni, consulta la tabella seguente.

     Per creare un URL personalizzato, specifica le seguenti informazioni:

     | Campo | Descrizione |
     |---------|----------|
     | [!UICONTROL **URL personalizzato**] | Specifica un URL personalizzato che desideri utilizzare per il collegamento ipertestuale. Gli URL devono essere immessi come URL del tutto idonei. Ad esempio: <https://www.example.com><p>L’URL personalizzato creato può essere statico o dinamico:</p> <ul><li>**URL statici:** quando desideri collegare tutti gli elementi allo stesso URL, puoi specificare un URL statico per uno solo o per tutti gli elementi dimensionali. Ad esempio: `https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**URL dinamici:** puoi creare un URL dinamico se desideri creare collegamenti ipertestuali univoci per più o per tutti gli elementi dimensionali in una colonna dimensione.<p>Per rendere dinamici gli URL personalizzati, includi una variabile per modificare l’URL in base al valore della dimensione o al valore della dimensione di raggruppamento.</p><p>Quando si utilizzano le variabili, tutti gli elementi dimensionali che contengono caratteri non validi negli URL (ad esempio gli spazi) sono URL-encoded.</p><p>Le seguenti variabili sono disponibili: (**Nota**: anche se è possibile utilizzare queste variabili nello stesso URL, è più comune utilizzarle separatamente).</p> <ul><li>**`$value`:** Consente di inserire il valore dell’elemento dimensionale nell’URL specificato. <p>Supponi di voler creare collegamenti ipertestuali per tutti gli elementi dimensionali Nome pagina in una tabella a forma libera, dove il valore di ogni elemento dimensionale fa parte dell’URL di una pagina web. In questo caso, puoi creare un singolo URL personalizzato che si adatti dinamicamente per ogni elemento dimensionale. <br/>Ad esempio: `https://company-name.com/browse/product#\$value`</p><p>Quando questo URL personalizzato viene applicato agli elementi dimensionali Nome pagina i cui valori sono “ProductY” e “ProductZ”, i collegamenti ipertestuali generati avranno un aspetto simile al seguente: <br/>`https://company-name.com/browse/product#ProductY` e<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![utilizzare valori nei collegamenti ipertestuali](assets/table-hyperlinks-vaule.png)</p><p>**Suggerimento**: l’aggiunta della sola variabile `$value` nel campo URL personalizzato equivale alla selezione dell’opzione [!UICONTROL **Utilizza il valore dell’elemento dimensionale**] durante la creazione dell’URL.</p></li><li>**`$breakdown`:** consente di inserire il valore dell’elemento dimensionale di raggruppamento nell’URL specificato. Con `$breakdown`, puoi utilizzare una dimensione con un nome descrittivo nel rapporto (ad esempio una dimensione Nome prodotto). E generare un collegamento ipertestuale basato su una dimensione di raggruppamento che potrebbe essere meno intuitiva (ad esempio una dimensione ID prodotto o URL pagina).<p>Quando si fa riferimento a una dimensione di raggruppamento, è più comune avere un solo elemento di raggruppamento per un dato elemento dimensionale. Se per un dato elemento dimensionale sono presenti più elementi di raggruppamento, nell’URL viene utilizzato il valore del primo elemento di raggruppamento. Se non sono elencati elementi di raggruppamento, l’URL non è valido. Agli elementi di raggruppamento viene applicato lo stesso ordine applicato alla tabella.</p><p>Specifica la dimensione di raggruppamento nel campo [!UICONTROL **Dimensione raggruppamento**] di seguito.</p> <p>Considera lo scenario di esempio descritto per il campo [!UICONTROL **Dimensione raggruppamento**] di seguito.</p></li></ul> |
     | [!UICONTROL **Dimensione raggruppamento (facoltativo)**] | Inizia a digitare il nome della dimensione di raggruppamento da utilizzare, quindi selezionala dal menu a discesa. <p>Se selezioni una dimensione di raggruppamento in questo campo, devi farvi riferimento utilizzando la variabile `$breakdown` nell’URL specificato nel campo [!UICONTROL **URL personalizzato**].</p><p>Supponi di voler creare collegamenti ipertestuali per tutti gli elementi dimensionali Nome prodotto in una tabella a forma libera. Ogni elemento dimensionale Nome prodotto contiene un raggruppamento di una dimensione ID prodotto.</p></p>In questo caso, puoi creare collegamenti ipertestuali per ogni dimensione Nome prodotto che indirizza gli utenti alla pagina del prodotto utilizzando il valore della dimensione di raggruppamento ID prodotto. </p><p>Aggiungi la variabile `$breakdown` alla fine dell’URL personalizzato specificato nel campo [!UICONTROL **URL personalizzato**]. Ad esempio:</p><p>`https://company-name.com/browse/product/$breakdown`</p>Quando questo URL personalizzato viene applicato agli elementi dimensionali Nome prodotto (che hanno elementi dimensionali di raggruppamento i cui valori sono “ProductY” e “ProductZ”), i collegamenti ipertestuali generati avranno un aspetto simile a:<br/>`https://company-name.com/browse/product/ProductY` e<br/>`https://company-name.com/browse/product/ProductZ`</p><p>Puoi quindi selezionare la dimensione ID prodotto nel campo [!UICONTROL **Dimensione raggruppamento**] </p><p>![utilizzare raggruppamenti nei collegamenti ipertestuali](assets/table-hyperlinks-breakdown.png)</p> |

1. Seleziona [!UICONTROL **Crea**].

   Gli utenti che visualizzano la tabella a forma libera, visualizzano gli elementi dimensionali con collegamento ipertestuale. Quando viene fatto clic su un elemento dimensionale, gli utenti vengono reindirizzati alle pagine con collegamento ipertestuale in una scheda del browser separata.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md) per salvare le modifiche.

## Modificare i collegamenti ipertestuali

Puoi modificare i collegamenti ipertestuali creati su dimensioni o elementi dimensionali in una tabella a forma libera.

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Modifica un collegamento ipertestuale per un singolo elemento dimensionale:**

      1. Apri il menu di scelta rapida per l’elemento dimensionale.
      1. Seleziona [!UICONTROL **Modifica collegamento ipertestuale**] dal menu di scelta rapida.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **Modifica collegamenti ipertestuali per tutti gli elementi dimensionali nella colonna di una dimensione:**

      1. Apri il menu di scelta rapida dall’intestazione della colonna della dimensione.
      1. Seleziona **[!UICONTROL Edit hyperlink for all dimension items]** dal menu di scelta rapida.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. Seleziona [!UICONTROL **Modifica collegamenti ipertestuali per tutti gli elementi dimensionali**] dal menu di scelta rapida.

   Viene visualizzata la finestra di dialogo [!UICONTROL **Modifica collegamenti ipertestuali per elementi dimensione**].

1. Per informazioni sulle opzioni di configurazione per la modifica del collegamento ipertestuale, consulta il passaggio 3 nella sezione [Creare collegamenti ipertestuali per uno o più elementi dimensionali](#create-hyperlinks-for-one-or-more-dimension-items) sopra, quindi seleziona [!UICONTROL **Applica**] al termine degli aggiornamenti.

1. [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md) per salvare le modifiche.

## Rimuovere i collegamenti ipertestuali

È possibile rimuovere i collegamenti ipertestuali creati per gli elementi dimensionali di una tabella a forma libera.

>[!NOTE]
>
>In una tabella a forma libera, se elimini una dimensione che contiene collegamenti ipertestuali, questi non persistono se aggiungi nuovamente la stessa dimensione alla tabella a forma libera.

Per rimuovere i collegamenti ipertestuali dagli elementi dimensionali:

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Rimozione di un collegamento ipertestuale da un singolo elemento dimensionale:**

      1. Apri il menu di scelta rapida per l’elemento dimensionale.
      1. Seleziona [!UICONTROL **Rimuovi collegamento ipertestuale**] dal menu di scelta rapida.
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **Rimozione di collegamenti ipertestuali da tutti gli elementi dimensionali in una colonna dimensione:**

      1. Apri il menu di scelta rapida dall’intestazione della colonna della dimensione.
      1. Seleziona **[!UICONTROL Remove hyperlink for all dimension items]** dal menu di scelta rapida.

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   Se hai selezionato un singolo elemento dimensionale, il collegamento ipertestuale viene rimosso dal singolo elemento dimensionale. Oppure da tutti gli elementi dimensionali se hai selezionato il nome della dimensione nell’intestazione della colonna della dimensione.

1. Per salvare le modifiche, [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md).
