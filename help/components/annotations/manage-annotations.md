---
title: Gestire le annotazioni
description: Come gestire le annotazioni in Workspace.
role: User, Admin
feature: Components
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 92%

---

# Gestire le annotazioni

Il gestore [!UICONTROL Components] > [!UICONTROL Annotations] offre diversi modi per gestire le annotazioni, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.

Il gestore [!UICONTROL Annotations] mostra tutte le annotazioni di cui sei proprietario che sono definite nell’ambito di tutti i tuoi progetti e che sono condivise con te.

>[!NOTE]
>
>Le [!UICONTROL Annotations] create unicamente per uno specifico progetto non vengono visualizzate dal gestore.

## Interfaccia utente del gestore Annotazioni

![](assets/annotation-mgr.png)

| Elemento dell’interfaccia utente | Descrizione |
| --- | --- | 
| [!UICONTROL Title and Description] | Forniti nel generatore Annotazioni. Per modificare il titolo e la descrizione, fai clic sul collegamento del titolo; in questo modo verrai riportato al generatore Annotazioni. |
| [!UICONTROL Report Suite] | Le suite di rapporti a cui si applica l’annotazione. |
| [!UICONTROL Owner] | Indica il proprietario dell’annotazione. Se non hai privilegi da amministratore, puoi visualizzare solo le annotazioni di tua proprietà o che sono state condivise con te. |
| [!UICONTROL Applied Date Range] | Data o intervallo di date a cui si applica questa annotazione. |
| [!UICONTROL Shared with] | Elenca con quanti singoli utenti o gruppi hai condiviso l’annotazione. Fai clic per ulteriori dettagli. |
| [!UICONTROL Date Modified] | Mostra la data e l’ora dell’ultima modifica apportata all’annotazione. |

{style=&quot;table-layout:auto&quot;}

## Modificare le annotazioni

La modifica di un’annotazione consente di regolare intervalli di date, colori, ambito o se tale annotazione viene applicata o meno a tutte le suite di rapporti o ai progetti. È possibile modificare le annotazioni in due modi:

* In un grafico a linee, posiziona il cursore del mouse sull’annotazione e fai clic sull’icona della matita all’interno del messaggio a comparsa.

* In [!UICONTROL Annotations Manager], fai clic sul titolo dell’annotazione.

Entrambe queste opzioni consentono di tornare al Generatore di annotazioni. Da qui è possibile apportare le modifiche necessarie e salvare la nuova versione.

## Condividere le annotazioni

Quando condividi le annotazioni o lavori con annotazioni condivise con te, tieni presente quanto segue:

* Supponiamo che tu abbia creato un progetto con annotazioni di sola progettazione e in seguito lo condividi con un altro utente. Queste annotazioni verranno visualizzate, ma non possono essere modificate o eliminate da altri utenti con cui condividi il progetto.

* Se salvi un’annotazione e la condividi direttamente con un utente, questa può essere modificata o eliminata solo se dispone dei diritti di amministratore.

* Per ricapitolare, se il progetto è condiviso con te, verrà visualizzata solo in quel progetto. Se l’annotazione viene condivisa direttamente con te, viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma non con informazioni di tipo &quot;ora&quot; o &quot;fuso orario&quot;. Al momento del rapporto, viene sempre applicato il fuso orario della visualizzazione dati del pannello. Quindi un’annotazione creata per il giorno di Natale si attiva il 25 dicembre, indipendentemente dal fuso orario della suite di rapporti in cui ti trovi.

Un altro esempio è il giorno di Capodanno. A ogni ora che passa, le aree con fuso orario diverso accendono in successione i fuochi d’artificio allo scoccare del nuovo anno. Se ad esempio a Londra sono le 23:00, a Roma si sta festeggiando con i fuochi perché è già arrivata la mezzanotte.

## Altre attività di annotazione

Il gestore Annotazioni consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le annotazioni. Non è visibile agli utenti non amministratori.

È sufficiente selezionare una o più annotazioni per visualizzare la barra delle attività.

| Attività | Descrizione |
| --- | --- |
| Add | Consente di accedere al generatore di Annotazioni da dove è possibile creare nuove annotazioni. |
| Tag | Tutti gli utenti possono creare tag per le annotazioni e applicarne uno o più a una singola annotazione. Tuttavia, puoi visualizzare solo i tag per i segmenti di tua proprietà. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso</li><li>Tag di categorie: maschile; geografia</li><li>Tag del flusso di lavoro: curato per (una specifica unità operativa); approvato</li></ul> |
| Elimina | L’eliminazione di un’annotazione ne comporta la rimozione da qualsiasi progetto dell’organizzazione. |
| Rinomina | La ridenominazione di un’annotazione ne comporta la rinomina in tutti i progetti a cui è stata applicata. |
| Copia | Crea una copia distinta con il proprio ID di annotazione, ma con nome e definizione uguali. |
| Esporta in CSV | Esporta la definizione dell’annotazione in un file .csv. |
| Filtro (barra a sinistra) | Filtra in base a tag, suite di rapporti, proprietari e altri filtri (Personali, Approvati, Preferiti, Condivisi con me e Mostra tutto). |

{style=&quot;table-layout:auto&quot;}
