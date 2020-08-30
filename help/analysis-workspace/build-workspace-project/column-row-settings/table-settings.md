---
description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
title: Impostazioni riga
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: df326581abbbd0dd0d29638962ccb71bb0aee837
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 24%

---


# Impostazioni riga

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella. Per accedere alle impostazioni di riga, fai clic sull’icona Impostazioni accanto a una dimensione, a un segmento, a una metrica, a un periodo di tempo o a un’interruzione in ognuna di queste:

![](assets/row-settings.png)

| Impostazione | Descrizione |
|--- |--- |
| Allinea date | Si tratta di un&#39;impostazione a livello di tabella che allinea le date di ogni colonna affinché inizino tutte sulla stessa riga. L&#39;allineamento delle date è attivato per impostazione predefinita quando una dimensione temporale viene utilizzata nelle righe della tabella e nelle colonne vengono applicati intervalli di date diversi. Ad esempio, in una tabella giornaliera con ottobre e settembre applicati alle colonne, la colonna a sinistra inizia con 1 ottobre e la colonna a destra inizia con 1 settembre. |
| Suddivisione per posizione | Per impostazione predefinita, questa impostazione è disabilitata e le suddivisioni sono fisse su elementi di riga statici. Ad esempio, potete suddividere i primi 3 elementi dimensione pagina (Pagina principale, Risultati ricerca, Checkout) per canale di marketing. Quindi, lasciate il progetto e tornate due settimane dopo. Dopo aver riaperto il progetto, le prime 3 pagine sono cambiate, e ora Homepage, Risultati ricerca e Checkout sono le prime 4-6 pagine. Per impostazione predefinita, le suddivisioni del canale di marketing continueranno a essere visualizzate nella pagina principale, nei risultati di ricerca e nel checkout, anche se ora si trovano nelle righe 4-6. <br> Per contro, **Suddivisione per posizione** verranno sempre suddivisi i primi 3 elementi, a prescindere da cosa siano. Facendo riferimento al nostro esempio, quando riaprite il progetto, le suddivisioni del canale di marketing saranno collegate alle prime 3 pagine della tabella, non alla pagina iniziale, ai risultati di ricerca e al checkout che si trovano ora nelle righe 4-6. |
| Percentuali | **Calcola le percentuali per colonna** è l&#39;impostazione predefinita; le percentuali visibili in una colonna vengono calcolate in base al totale della colonna. <br>**Calcola le percentuali per riga** forza la tabella a forma libera a calcolare le percentuali delle celle sulla riga, anziché la colonna, con il totale complessivo come denominatore. Questo è utile in particolare per le percentuali di tendenza. Questa impostazione è abilitata per impostazione predefinita quando si utilizza l&#39;icona Visualizza. |
| Totali colonna | Queste impostazioni sono disponibili solo per [righe statiche](manual-vs-dynamic-rows.md). <br> **Mostra come somma delle righe correnti** mostra una somma lato client delle righe nella tabella, il che significa che il totale *not* deduplicare metriche come visite o visitatori. <br> **Mostra totale complessivo** mostra una somma lato server che indica che il totale annullerà le metriche. |
