---
description: Documentazione che descrive come filtrare e ordinare le tabelle in Analysis Workspace.
title: Filtrare e ordinare tabelle
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 7%

---

# Filtrare e ordinare tabelle

Le tabelle a forma libera in Analysis Workspace sono alla base dell’analisi interattiva dei dati. In quanto tali, possono contenere migliaia di righe di informazioni. Filtrare e ordinare i dati può essere una parte fondamentale per una corretta visualizzazione delle informazioni più importanti.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Tabelle di filtro {#section_36E92E31442B4EBCB052073590C1F025}

I filtri in Analysis Workspace ti aiutano a far emergere le informazioni più importanti.

Per filtrare i dati nelle tabelle a forma libera:

1. In una tabella a forma libera, passa il cursore del mouse sulla colonna contenente i dati da filtrare. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleziona la **Filtro** quando appare.

   ![Icona del filtro in una tabella](assets/table-filter-icon.png)

1. In [!UICONTROL **Ricerca di parole o frasi**] specificare una parola o una frase che si desidera filtrare. Vengono visualizzate solo le righe contenenti la parola o la frase esatta specificata.

1. (Facoltativo) Per filtrare in base a criteri diversi o a più criteri, seleziona [!UICONTROL **Mostra avanzate**].

   Sono disponibili le seguenti opzioni

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi non specificato (nessuno)**] | Selezionare questa opzione per visualizzare nella tabella i dati che non rientrano in nessuna delle dimensioni della tabella. <!--what is this?--> |
   | [!UICONTROL **Corrispondenza**] | <p>Scegli [!UICONTROL **Se tutti i criteri sono soddisfatti**] per mostrare solo i dati che soddisfano tutti i criteri specificati. In genere, questa opzione genera dati più precisi.</p> <p>Scegli [!UICONTROL **Se sono soddisfatti dei criteri**] per mostrare i dati che soddisfano uno qualsiasi dei criteri di filtro specificati. Questa opzione genera in genere dati meno elaborati.</p> |
   | [!UICONTROL **Criteri**] | <p>Seleziona tra le seguenti opzioni filtro:</p><p>(Seleziona [!UICONTROL **Aggiungi riga**] per aggiungere più criteri di filtro. L’opzione selezionata nella [!UICONTROL **Corrispondenza**] determina se tutti i criteri aggiunti devono essere soddisfatti o meno.)</p><ul><li><p>[!UICONTROL **Contiene la frase**]: Nei risultati filtrati vengono inclusi solo i dati che contengono la frase esatta specificata. Le parole devono essere nell&#39;ordine specificato nel [!UICONTROL **Campo parola o frase di ricerca**].<p>Questa è l’impostazione predefinita quando si esegue una ricerca semplice.</p></p></li><li><p>[!UICONTROL **Contiene qualsiasi termine**]: Nei risultati filtrati sono inclusi solo i dati contenenti una o più parole della frase specificata. </p></li><li><p>[!UICONTROL **Contiene tutti i termini**]: Nei risultati filtrati sono inclusi solo i dati che contengono tutte le parole della frase specificata. Le parole non devono necessariamente essere nell&#39;ordine specificato nel [!UICONTROL **Campo parola o frase di ricerca**].</p></li><li><p>[!UICONTROL **Non contiene alcun termine**]: Nei risultati filtrati sono inclusi solo i dati che non contengono alcuna delle parole della frase specificata. </p></li><li><p>[!UICONTROL **Non contiene la frase**]: Nei risultati filtrati sono inclusi solo i dati che non contengono la frase esatta specificata. Le parole devono essere nell&#39;ordine specificato nel [!UICONTROL **Campo parola o frase di ricerca**].</p></li><li><p>[!UICONTROL **Uguale**]: Nei risultati filtrati vengono inclusi solo i dati che corrispondono esattamente alla frase specificata. </p></li><li><p>[!UICONTROL **Non uguale a**]: Nei risultati filtrati vengono inclusi solo i dati che non corrispondono esattamente alla frase specificata. </p></li><li><p>[!UICONTROL **Inizia con**]: Nei risultati filtrati sono inclusi solo i dati che iniziano con la parola o la frase esatta specificata. </p></li><li><p>[!UICONTROL **Termina con**]: Nei risultati filtrati sono inclusi solo i dati che terminano con la parola o la frase esatta specificata. </p></li></ul> |
   | [!UICONTROL **Escludere sempre gli elementi**] | Specifica il nome degli elementi da escludere dai dati filtrati. |

1. Seleziona [!UICONTROL **Applica**] per filtrare i dati.

   La **Filtro** icona ![Tabella filtrata icona filtro blu](assets/table-filter-blue-icon.png) diventa blu quando un filtro viene applicato alla tabella.

## Ordinare le tabelle

Puoi ordinare i dati di una tabella a forma libera in base a qualsiasi colonna di Analysis Workspace che sia un Dimension o una metrica.

Icona a freccia giù ![Icona a freccia in giù, colonna della tabella ordinata](assets/table-sort-arrow-icon.png) è visibile nell’intestazione della colonna in base alla quale i dati vengono ordinati.

1. In una tabella a forma libera in Analysis Workspace, fai clic sulla freccia accanto al nome del Dimension o della metrica.

   Quando si esegue l’ordinamento, tenere presente quanto segue:

   * La freccia giù ordina in ordine decrescente e la freccia su (impostazione predefinita) in ordine crescente.
   * È possibile ordinare i Dimension in ordine alfabetico o numerico. Ad esempio, è possibile che in un flusso di lavoro siano presenti passaggi numerati e che si desideri ordinare in base al numero del passaggio. Puoi ordinare una dimensione relativa alla data in base alla data. Oppure è possibile ordinare alfabeticamente le origini dati, come nell&#39;immagine seguente.

   ![](assets/sort-dimensions.png)


