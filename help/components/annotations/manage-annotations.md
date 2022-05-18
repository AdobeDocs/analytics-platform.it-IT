---
title: Gestire le annotazioni
description: Come gestire le annotazioni in Workspace.
role: User, Admin
feature: Components
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 4940f26c6c3b0b1f8baf0d715f4190c7f0f40efa
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 7%

---

# Gestire le annotazioni

La [!UICONTROL Components] > [!UICONTROL Annotations] manager offre diversi modi per gestire le annotazioni, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.

La [!UICONTROL Annotations] manager mostra tutte le annotazioni che possiedi che sono state assegnate a tutti i tuoi progetti e che sono state condivise con te.

>[!NOTE]
>
>[!UICONTROL Annotations] che hai creato solo per un progetto specifico non viene visualizzato nel manager.

## Interfaccia utente di Gestione annotazioni

![](assets/annotation-mgr.png)

| Elemento dell’interfaccia utente | Descrizione |
| --- | --- | 
| [!UICONTROL Title and Description] | Fornito nel Generatore di annotazioni. Per modificare il titolo e la descrizione, fai clic sul collegamento del titolo, che ti riporta al Generatore di annotazioni. |
| [!UICONTROL Report Suite] | Le suite di rapporti a cui si applica questa annotazione. |
| [!UICONTROL Owner] | Indica il proprietario dell’annotazione. In qualità di non amministratore, puoi visualizzare solo le annotazioni che possiedi o quelle condivise con te. |
| [!UICONTROL Applied Date Range] | Data o intervallo di date a cui si applica questa annotazione. |
| [!UICONTROL Shared with] | Elenca quanti singoli utenti o gruppi hanno condiviso l’annotazione. Fai clic su per ulteriori dettagli. |
| [!UICONTROL Date Modified] | Mostra la data e l’ora dell’ultima modifica apportata all’annotazione. |

## Modificare le annotazioni

La modifica di un’annotazione consente di regolare intervalli di date, colori, ambito o se si applica o meno a tutte le suite di rapporti o ai progetti. È possibile modificare le annotazioni in due modi:

* In un grafico a linee, posiziona il cursore del mouse sull’annotazione e fai clic sull’icona a forma di matita all’interno del puntatore.

* In [!UICONTROL Annotations Manager], fai clic sul titolo dell’annotazione.

Entrambe queste opzioni consentono di tornare al Generatore di annotazioni. In questo caso è possibile apportare le modifiche necessarie e salvare la nuova versione.

## Condividere le annotazioni

Quando condividi annotazioni o lavori con annotazioni condivise con te, tieni presente quanto segue:

* Supponiamo che crei un progetto con annotazioni di sola progettazione e quindi lo condividi con un altro utente. Queste annotazioni verranno visualizzate, ma non possono essere modificate o eliminate da altri utenti con cui condividi il progetto.

* Se salvi un’annotazione e la condividi direttamente con un utente, questa può essere modificata o eliminata solo se dispone dei diritti di amministratore.

* Per ricapitolare, se il progetto è condiviso con te, verrà visualizzato solo in quel progetto. Se l’annotazione viene condivisa direttamente con te, viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma non con informazioni di tipo &quot;ora&quot; o &quot;fuso orario&quot;. Al momento del rapporto, viene sempre applicato il fuso orario della visualizzazione dati del pannello. Quindi, il 25 dicembre si verifica un&#39;annotazione creata per Natale - indipendentemente dal fuso orario della suite di rapporti in cui ti trovi.

Un altro esempio è il giorno di Capodanno. Ogni ora, un fuso orario diverso inizia i fuochi d&#39;artificio all&#39;inizio del nuovo anno. Alle 10 ora USA di montagna, la costa orientale USA sta bruciando i fuochi d&#39;artificio perché è già alle 12 ora orientale.

## Altre attività di annotazione

Gestione annotazioni consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le annotazioni. Non è visibile agli utenti non amministratori.

È sufficiente selezionare una o più annotazioni e viene visualizzata la barra delle attività.

| Attività | Descrizione |
| --- | --- |
| Add | Consente di accedere al Generatore di annotazioni per creare nuove annotazioni. |
| Tag | Tutti gli utenti possono creare tag per le annotazioni e applicarne uno o più a un’annotazione. Tuttavia, puoi visualizzare solo i tag per i segmenti di tua proprietà. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso</li><li>Tag di categorie: maschile; geografia</li><li>Tag del flusso di lavoro: Curato per (una specifica unità operativa); Approvato</li></ul> |
| Elimina | L’eliminazione di un’annotazione la rimuove da qualsiasi progetto dell’organizzazione. |
| Rinomina | La denominazione di un’annotazione viene rinominata in tutti i progetti a cui è stata applicata. |
| Copia | Crea una copia distinta con il proprio ID di annotazione, ma con lo stesso nome e la stessa definizione. |
| Esporta in CSV | Esporta la definizione dell’annotazione in un file .csv . |
| Filtro (barra a sinistra) | Filtrare per tag, suite di rapporti, proprietari e altri filtri (Personali, Approvati, Preferiti, Condivisi con me e Mostra tutto). |
