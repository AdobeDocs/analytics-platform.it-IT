---
title: Creare collegamenti ipertestuali in una tabella a forma libera
description: Scopri come creare collegamenti ipertestuali per gli elementi dimensionali in una tabella a forma libera in Analysis Workspace
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# Creare collegamenti ipertestuali in una tabella a forma libera

Puoi creare collegamenti ipertestuali per gli elementi dimensionali per renderli cliccabili all’interno di una tabella a forma libera in Analysis Workspace.

Questa funzionalità è particolarmente utile quando si creano collegamenti ipertestuali per i seguenti tipi di elementi dimensionali:

* Elementi di Dimension con valori URL (ad esempio, una dimensione URL pagina).

* Elementi del Dimension che contengono raggruppamenti con valori URL (ad esempio, una dimensione Nome pagina con raggruppamento di una dimensione URL pagina).

* Elementi o raggruppamenti di Dimension con valori che fanno parte di un URL (ad esempio, una dimensione Nome pagina che fa parte di un URL).


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare collegamenti ipertestuali in una tabella a forma libera](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"} per un video demo.

>[!ENDSHADEBOX]


## Creare collegamenti ipertestuali

Quando crei collegamenti ipertestuali per uno o più elementi dimensionali, considera quanto segue:

* I collegamenti ipertestuali creati vengono memorizzati nella tabella a forma libera all’interno del progetto Analysis Workspace. I collegamenti ipertestuali non persistono quando si utilizzano gli stessi elementi dimensione o dimensione in un’altra tabella o in un altro progetto.

* Se modifichi la visualizzazione dati della tabella a forma libera, sono ancora disponibili tutti i collegamenti ipertestuali creati per le dimensioni o gli elementi dimensionali nella tabella. Questa funzionalità presuppone che la dimensione esista ancora nella visualizzazione dati.

* La validità degli URL non viene verificata durante la creazione del collegamento ipertestuale. Se

   * creare un collegamento ipertestuale con un URL non valido oppure
   * creare un collegamento ipertestuale che faccia riferimento a un elemento dimensione che non ha un valore URL (facendo riferimento direttamente all&#39;elemento dimensione o utilizzando le variabili `$value` o `$breakdown`),

  gli utenti che fanno clic sul collegamento ipertestuale visualizzano quindi un messaggio di errore in cui viene indicato che l’URL non è valido.

* I collegamenti ipertestuali creati per un singolo elemento dimensionale sovrascrivono quelli creati sulla dimensione.

* I collegamenti ipertestuali non funzionano in [file PDF scaricati](/help/analysis-workspace/export/download-send.md).

Per creare collegamenti ipertestuali per uno o più elementi dimensionali:

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Creare un collegamento ipertestuale per un singolo elemento dimensione:** Fare clic con il pulsante destro del mouse sull&#39;elemento dimensione all&#39;interno della tabella per il quale si desidera creare il collegamento ipertestuale, quindi selezionare [!UICONTROL **Crea collegamento ipertestuale**].

      1. Apre il menu di scelta rapida per l&#39;elemento dimensione.
      1. Selezionare [!UICONTROL **Crea collegamento ipertestuale**] dal menu di scelta rapida.

         Viene visualizzata la finestra di dialogo [!UICONTROL **Crea collegamento ipertestuale**]. Il nome dell’elemento dimensione per il quale stai creando un collegamento ipertestuale viene visualizzato nella finestra di dialogo.

         ![Crea collegamento ipertestuale per la finestra di dialogo di un singolo elemento](assets/hyperlink-dialog-single.png)

   * **Creare collegamenti ipertestuali per tutti gli elementi dimensione nella colonna di una dimensione:** Fare clic con il pulsante destro del mouse sul nome della dimensione nell&#39;intestazione della colonna della dimensione, quindi selezionare [!UICONTROL **Creare collegamenti ipertestuali per tutti gli elementi dimensione**].

      1. Aprite il menu di scelta rapida dall&#39;intestazione della colonna della quota.
      1. Selezionare [!UICONTROL **Crea collegamento ipertestuale per tutti gli elementi dimensionali**] dal menu di scelta rapida.

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         Viene visualizzata la finestra di dialogo [!UICONTROL **Crea collegamenti ipertestuali per tutti gli elementi della dimensione**]. Il nome della dimensione per la quale si stanno creando collegamenti ipertestuali viene visualizzato nella finestra di dialogo.

         ![Finestra di dialogo per la creazione di collegamenti ipertestuali](assets/hyperlink-dialog-multiple.png)

1. Scegli tra le seguenti opzioni:

   * [!UICONTROL **Utilizzare il valore dell&#39;elemento dimensione come URL**]: scegliere questa opzione per gli elementi dimensione che hanno valori URL, ad esempio una dimensione URL pagina.

     Ad esempio, se utilizzi una dimensione URL pagina in cui il valore di ogni elemento dimensione è un URL, selezionando questa opzione viene creato un collegamento ipertestuale all’URL.

   * [!UICONTROL **Creare un URL personalizzato**]: specificare un URL personalizzato statico o dinamico. Scegli questa opzione per creare collegamenti ipertestuali per gli elementi dimensione che non hanno valori URL.

     Ad esempio: utilizzi una dimensione Nome pagina in cui il valore di ciascun elemento dimensione è il nome di una pagina (e non un URL completo). Quindi seleziona questa opzione per specificare un collegamento ipertestuale da utilizzare come collegamento per l’elemento dimensione.

     Se desideri creare URL dinamici per più elementi di dimensione, puoi utilizzare le variabili `$value` e `$breakdown` nell&#39;URL personalizzato. Per ulteriori informazioni, consulta la tabella seguente.

     Per creare un URL personalizzato, specifica le seguenti informazioni:

     | Campo | Descrizione |
     |---------|----------|
     | [!UICONTROL **URL personalizzato**] | Specificare un URL personalizzato da utilizzare per il collegamento ipertestuale. Gli URL devono essere immessi come URL completi. Ad esempio: <https://www.example.com><p>L’URL personalizzato creato può essere statico o dinamico:</p> <ul><li>**URL statici:** È possibile specificare un URL statico per un singolo elemento di dimensione o per tutti gli elementi di dimensione quando si desidera collegare tutti gli elementi allo stesso URL. Ad esempio: `https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**URL dinamici:** Puoi creare un URL dinamico se desideri creare collegamenti ipertestuali univoci per più elementi dimensionali o per tutti gli elementi dimensionali in una colonna dimensione.<p>Per rendere dinamici gli URL personalizzati, includi una variabile nell’URL per modificare l’URL in base al valore della dimensione o al valore della dimensione di raggruppamento.</p><p>Quando si utilizzano le variabili, tutti gli elementi dimensionali che contengono caratteri non validi negli URL (ad esempio gli spazi) sono codificati in URL.</p><p>Sono disponibili le seguenti variabili: (**Nota**: anche se è possibile utilizzare queste variabili nello stesso URL, è più comune utilizzarle separatamente.)</p> <ul><li>**`$value`:** Consente di inserire il valore dell&#39;elemento dimensione nell&#39;URL specificato. <p>Supponiamo di voler creare collegamenti ipertestuali per tutti gli elementi dimensione Nome pagina in una tabella a forma libera, dove il valore di ogni elemento dimensione fa parte dell’URL di una pagina web. In questo caso, puoi creare un singolo URL personalizzato che si adatta dinamicamente per ogni elemento dimensione. <br/>Ad esempio: `https://company-name.com/browse/product#\$value`</p><p>Quando questo URL personalizzato viene applicato agli elementi dimensione Nome pagina i cui valori sono &quot;ProductY&quot; e &quot;ProductZ&quot;, i collegamenti ipertestuali generati avranno un aspetto simile al seguente: <br/>`https://company-name.com/browse/product#ProductY` e<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![usa valori nei collegamenti ipertestuali](assets/table-hyperlinks-vaule.png)</p><p>**Suggerimento**: l&#39;aggiunta della sola variabile `$value` nel campo URL personalizzato equivale alla selezione dell&#39;opzione [!UICONTROL **Utilizza il valore dell&#39;elemento dimensione**] durante la creazione dell&#39;URL.</p></li><li>**`$breakdown`:** consente di inserire il valore dell&#39;elemento della dimensione di raggruppamento nell&#39;URL specificato. Con `$breakdown`, puoi utilizzare una dimensione con un nome descrittivo nel rapporto (ad esempio una dimensione Nome prodotto). E genera un collegamento ipertestuale basato su una dimensione di raggruppamento che potrebbe essere meno semplice da usare (ad esempio una dimensione ID prodotto o URL pagina).<p>Quando si fa riferimento a una dimensione di raggruppamento, è più comune avere un solo elemento di raggruppamento per un dato elemento di dimensione. Se per un dato elemento dimensionale sono presenti più elementi di raggruppamento, nell’URL viene utilizzato il valore del primo elemento di raggruppamento. Se non sono elencati elementi di suddivisione, l’URL non è valido. Agli elementi di suddivisione viene applicato lo stesso ordinamento applicato alla tabella.</p><p>Specifica la dimensione di raggruppamento nel campo [!UICONTROL **Dimensione raggruppamento**] di seguito.</p> <p>Considera lo scenario di esempio descritto per il campo [!UICONTROL **Raggruppamento dimensione**] di seguito.</p></li></ul> |
     | [!UICONTROL **Dimensione raggruppamento (facoltativo)**] | Inizia a digitare il nome della dimensione di raggruppamento da utilizzare, quindi selezionala dall’elenco a discesa. <p>Se selezioni una dimensione di raggruppamento in questo campo, devi farvi riferimento utilizzando la variabile `$breakdown` nell&#39;URL specificato nel campo [!UICONTROL **URL personalizzato**].</p><p>Supponiamo di voler creare collegamenti ipertestuali per tutti gli elementi dimensionali Nome prodotto in una tabella a forma libera. Ogni elemento dimensione Nome prodotto contiene un raggruppamento di una dimensione ID prodotto.</p></p>In questo caso, puoi creare collegamenti ipertestuali per ogni dimensione Nome prodotto che indirizza gli utenti alla pagina del prodotto utilizzando il valore della dimensione di raggruppamento ID prodotto. </p><p>Aggiungi la variabile `$breakdown` alla fine dell&#39;URL personalizzato specificato nel campo [!UICONTROL **URL personalizzato**]. Ad esempio:</p><p>`https://company-name.com/browse/product/$breakdown`</p>Quando questo URL personalizzato viene applicato agli elementi dimensione Nome prodotto (che hanno elementi dimensione di raggruppamento i cui valori sono &quot;ProductY&quot; e &quot;ProductZ&quot;), i collegamenti ipertestuali generati avranno un aspetto simile a:<br/>`https://company-name.com/browse/product/ProductY` e<br/>`https://company-name.com/browse/product/ProductZ`</p><p>Puoi quindi selezionare la dimensione ID prodotto nel campo [!UICONTROL **Dimensione raggruppamento**] </p><p>![utilizzare le suddivisioni nei collegamenti ipertestuali](assets/table-hyperlinks-breakdown.png)</p> |

1. Seleziona [!UICONTROL **Crea**].

   Gli utenti che visualizzano la tabella a forma libera visualizzano gli elementi dimensionali con collegamento ipertestuale. Quando si fa clic su un elemento dimensione, gli utenti vengono reindirizzati alle pagine con collegamento ipertestuale in una scheda del browser separata.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md) per salvare le modifiche.

## Modifica collegamenti ipertestuali

Puoi modificare i collegamenti ipertestuali creati su dimensioni o elementi dimensionali in una tabella a forma libera.

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Modifica un collegamento ipertestuale per un singolo elemento dimensione:**

      1. Apre il menu di scelta rapida per l&#39;elemento dimensione.
      1. Selezionare [!UICONTROL **Modifica collegamento ipertestuale**] dal menu di scelta rapida.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **Modifica collegamenti ipertestuali per tutti gli elementi dimensionali nella colonna di una dimensione:**

      1. Aprite il menu di scelta rapida dall&#39;intestazione della colonna della quota.
      1. Selezionare **[!UICONTROL Edit hyperlink for all dimension items]** dal menu di scelta rapida.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. Selezionare [!UICONTROL **Modifica collegamenti ipertestuali per tutti gli elementi dimensionali**] dal menu di scelta rapida.

   Viene visualizzata la finestra di dialogo [!UICONTROL **Modifica collegamenti ipertestuali per elementi dimensione**].

1. Per informazioni sulle opzioni di configurazione per la modifica del collegamento ipertestuale, vedere il passaggio 3 nella sezione [Creare collegamenti ipertestuali per uno o più elementi dimensionali](#create-hyperlinks-for-one-or-more-dimension-items) sopra, quindi selezionare [!UICONTROL **Applica**] al termine degli aggiornamenti.

1. [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md) per salvare le modifiche.

## Rimuovere i collegamenti ipertestuali

È possibile rimuovere i collegamenti ipertestuali creati per gli elementi dimensionali di una tabella a forma libera.

>[!NOTE]
>
>In una tabella a forma libera, se si elimina una dimensione che contiene collegamenti ipertestuali, questi non persistono se si aggiunge nuovamente la stessa dimensione alla tabella a forma libera.

Per rimuovere i collegamenti ipertestuali dagli elementi dimensione:

1. In una tabella a forma libera in Analysis Workspace, effettua una delle seguenti operazioni:

   * **Rimozione di un collegamento ipertestuale da un singolo elemento dimensione:**

      1. Apre il menu di scelta rapida per l&#39;elemento dimensione.
      1. Selezionare [!UICONTROL **Rimuovi collegamento ipertestuale**] dal menu di scelta rapida.
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **Rimozione di collegamenti ipertestuali da tutti gli elementi di dimensione in una colonna dimensione:**

      1. Aprite il menu di scelta rapida dall&#39;intestazione della colonna della quota.
      1. Selezionare **[!UICONTROL Remove hyperlink for all dimension items]** dal menu di scelta rapida.

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   Se hai selezionato un singolo elemento dimensione, il collegamento ipertestuale viene rimosso dal singolo elemento dimensione. Oppure da tutti gli elementi dimensione se hai selezionato il nome della dimensione nell’intestazione della colonna della dimensione.

1. [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md) per salvare le modifiche.
