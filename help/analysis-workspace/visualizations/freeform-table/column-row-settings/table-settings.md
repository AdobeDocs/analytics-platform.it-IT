---
description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
title: Impostazioni riga
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 88%

---

# Impostazioni riga

Visualizza un video sulle impostazioni di riga e colonna qui:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella. Per accedere alle impostazioni di riga, fai clic sull’icona [!UICONTROL Settings] accanto a una dimensione, a un filtro, a una metrica, a un periodo di tempo o a un raggruppamento in ognuna di queste:

![Tabella a forma libera che evidenzia l’icona Impostazioni per le metriche](assets/row-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| Allinea date | Si tratta di un’impostazione a livello di tabella che allinea le date di ogni colonna affinché inizino tutte sulla stessa riga. L’allineamento delle date è attivato per impostazione predefinita quando una dimensione temporale viene utilizzata nelle righe della tabella e nelle colonne vengono applicati intervalli di date diversi. Ad esempio, in una tabella giornaliera con ottobre e settembre applicati alle colonne, la colonna a sinistra inizia con il 1° ottobre e la colonna a destra inizia con il 1° settembre. |
| Raggruppamento per posizione | Per impostazione predefinita, questa impostazione è disabilitata e i raggruppamenti sono fissati su elementi di riga statici. Ad esempio, supponiamo che tu abbia raggruppato i primi 3 elementi dimensionali di pagina (Home page, Risultati ricerca, Pagamento) per canale di marketing. Poi abbandoni il progetto per due settimane. Quando lo riapri, le prime 3 pagine sono cambiate e ora Home page, Risultati ricerca e Pagamento sono le prime 4-6 pagine. Per impostazione predefinita, i raggruppamenti per canale di marketing continueranno a essere visualizzati in Home page, Risultati ricerca e Pagamento, anche se ora si trovano nelle righe 4-6. <br> Al contrario, **Raggruppamento per posizione** raggrupperà sempre i primi 3 elementi, indipendentemente da quali siano. Facendo riferimento all’esempio precedente, quando riapri il progetto, i raggruppamenti per canale di marketing saranno collegati alle prime 3 pagine della tabella, non a Home page, Risultati ricerca e Pagamento, che ora si trovano nelle righe 4-6. |
| Percentuali | **Calcola percentuali per colonna** è l’impostazione predefinita. Le percentuali visibili in una colonna vengono calcolate in base al totale della colonna. <br>**Calcola percentuali per riga** costringe la tabella a forma libera a calcolare le percentuali delle celle di una riga, anziché di una colonna, utilizzando il totale come denominatore. Questo è utile in particolare per le percentuali di tendenza. Questa impostazione è abilitata per impostazione predefinita quando si utilizza l’icona Visualizza. |
| Totali colonna | Queste impostazioni sono disponibili solo per le [righe statiche](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostra come somma delle righe correnti** mostra una somma lato client delle righe nella tabella, il che significa che il totale *non* deduplicare metriche quali visite o persone. <br> **Mostra totale** mostra una somma lato server, il che significa che il totale deduplica le metriche. |

## Modificare conteggio righe

Per modificare il numero di righe visualizzate:

1. Fai clic sul numero accanto a [!UICONTROL Rows] in cima alla tabella.

   ![Tabella a forma libera che mostra l’elenco a discesa per il numero di righe visualizzate. È selezionata una riga da 400.](assets/row-number.png)

1. Dall’elenco a discesa, seleziona il numero di righe che si desidera visualizzare nella tabella.