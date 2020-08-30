---
title: Gestire i filtri
description: Gestire i filtri in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 100%

---


# Gestire i filtri

Il Gestore filtri offre diversi modi per curare i segmenti, ad esempio condividere, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.

Gestione filtri mostra tutti i filtri di tua proprietà e che sono stati condivisi con te. Gli utenti a livello di amministratore possono visualizzare tutti i filtri dell’organizzazione. Questa panoramica presenta l’interfaccia utente e le funzionalità del Gestore filtri.

Accedi al Gestore filtri scegliendo **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** nella navigazione superiore.

## Interfaccia utente di Gestore filtri

![](assets/filter-manager-ui.png)

| # | Funzionalità dell’interfaccia utente | Descrizione |
|---|---|---|
| 1 | Barra degli strumenti di gestione dei filtri | Dopo aver selezionato un filtro, viene visualizzata questa barra degli strumenti. La maggior parte delle attività di gestione può essere completata da questa barra degli strumenti. |
| 2 | Caselle di controllo | Seleziona un filtro per gestirlo. |
| 4 | Preferiti | Facendo clic sulla stella accanto a un filtro, la stella diventa gialla e il filtro viene contrassegnato come preferito. |
| 5 | Titolo e descrizione | Fornito nel Generatore di filtri. Per modificare il titolo e la descrizione, fai clic sul collegamento del titolo; il quale ti riporta al Generatore di filtri. |
| 6 | Suite di rapporti | Questa colonna indica in quale suite di rapporti il filtro è stato salvato l’ultima volta. |
| 7 | Proprietario | Indica il proprietario del filtro. Come non amministratore, puoi visualizzare solo i filtri che possiedi o quelli che sono stati condivisi con te. |
| 8 | Tag (non selezionato nel selettore colonna, di conseguenza la colonna non viene visualizzata) | I tag applicati al filtro, da te stesso o da altri utenti che lo hanno condiviso con te. |
| 9 | Condiviso con | Elenca singoli utenti o gruppi (solo amministratore) o tutti coloro (solo amministratore) con cui hai condiviso il filtro. |
| 10 | Data di modifica | Mostra la data dell’ultima modifica apportata al filtro. |
| 11 | Selettore colonna | Si trova in alto a destra, consente di selezionare le colonne da visualizzare nel Gestore filtri. |
| 12 | Icona Condiviso | Indica che questo filtro è condiviso da te o con te. |
| 13 | Icona Approvato | Indica che il filtro è stato approvato da un amministratore. |
| 14 | Altri filtri | Ti consente di visualizzare i filtri per tag, suite di rapporti, proprietari e altro (Mostra tutto, Personali, Condivisi con me, Approvati, Preferiti). |

## Pianificare i filtri

Dedicare un po’ di tempo alla pianificazione dei segmenti aumenta le possibilità che siano utili per la tua organizzazione e che il loro numero venga controllato.

* Considera il pubblico: chi lo utilizzerà? Con chi lo condividerò? Quali gruppi di persone useranno questo filtro e di conseguenza come dovrei assegnare i tag? Ciò implica anche fornire una buona descrizione del filtro. La descrizione dovrebbe rispondere almeno alle seguenti domande:

   * A cosa serve questo filtro?

   * Quando dovrei usare questo filtro?

* Determina l’ambito del filtro. Quale [contenitore di filtri](/help/components/filters/filters-overview.md) rappresenta meglio l’ambito? Utilizza il contenitore più piccolo possibile.

* Decidi quali elementi includere nella definizione del filtro e quali valori.

* Rifletti su come desideri che si svolga il processo di approvazione. Una singola persona rivedrà e approverà i filtri o la decisione spetterà a una commissione?

* Definisci i filtri con una visualizzazione in una libreria di filtri che consenta agli utenti aziendali di sovrapporre e riutilizzare parti o componenti di filtri in modo modulare. Quali “moduli” è necessario definire per realizzare questa libreria?

### Assegnare tag ai filtri

Nel Gestore filtri, assegnare tag ai filtri ti consente di organizzarli. Tutti gli utenti possono creare tag per i filtri e applicarne uno o più a un segmento. Tuttavia, puoi visualizzare solo i tag dei filtri di tua proprietà o che sono stati condivisi con te.

Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:

* Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing.

* Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso.

* Tag di categorie: maschile; geografia.

* Tag del flusso di lavoro: Da approvare; Curato per (una specifica unità aziendale).

Per assegnare tag a un filtro:

1. Nel Gestore filtri, contrassegna la casella di controllo accanto al filtro a cui desideri assegnare il tag. Viene visualizzata la barra degli strumenti di gestione del filtro.

1. Fai clic su **[!UICONTROL Tag]** e

   * seleziona da tag esistenti, oppure

   * inserisci un nuovo nome di tag e premi **[!UICONTROL Enter]**.

1. Fa di nuovo clic su **[!UICONTROL Tag]** per assegnare il tag al segmento.

Ora il tag dovrebbe essere visualizzato nella colonna Tag (fai clic sull’icona a forma di ingranaggio in alto a destra per gestire le colonne).
Puoi anche filtrare i tag andando in **[!UICONTROL Filters > Tags]**.

### Approvare i filtri

Nel Gestore filtri puoi impostare un flusso di lavoro che includa l’approvazione del filtro per vari livelli di applicazione, per reparti o gruppi specifici e in linea con i criteri di reporting.

Ecco come contrassegnare un filtro come approvato:

1. Nel Gestore filtri, seleziona la casella di controllo a sinistra del Titolo del filtro.

1. Fai clic su **[!UICONTROL Approve]** nella barra delle attività di gestione del filtro.

1. Scegli se condividere i segmenti approvati con la tua organizzazione.

1. Fai clic su **[!UICONTROL OK]**.

   Osserva l’icona di approvazione accanto al filtro nell’elenco:

   ![](assets/seg_approved.png)

1. Puoi anche annullare l’approvazione di un segmento approvato facendo clic su **[!UICONTROL Unapprove]**.

### Condividere i filtri

A seconda delle autorizzazioni, puoi condividere i filtri con l’intera organizzazione, i gruppi o i singoli utenti.

| Amministratore | Non amministratore |
|---|---|
| Puoi condividere i filtri con tutti, con i gruppi e con gli utenti. Consulta la [documentazione di Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-products-and-profiles.html) per maggiori informazioni. | Puoi condividere i filtri solo con singoli utenti. |

Quando è necessario condividere i filtri con l’intera azienda anziché con un solo gruppo di utenti o singoli utenti? Ecco alcune best practice che puoi seguire:

* In qualità di Amministratore, condividi un filtro con tutti se è utile per l’intera azienda e tutti possono usarlo con facilità. In questo caso, dovresti anche considerare la possibilità di renderlo un filtro approvato.

* In qualità di Amministratore, condividi un filtro con un profilo di prodotto specifico se il filtro fornisce un buon valore aziendale per quel team. Non approvare ufficialmente questo tipo di filtro.

* In qualità di Amministratore o di singolo utente, condividi un filtro con altri singoli utenti per esaminarlo e convalidarlo. Se non risulta utile, può essere scartato. Non approvare ufficialmente questo tipo di filtro.

Per condividere un filtro:

1. Nel Gestore filtri, contrassegna la casella di controllo accanto al filtro che desideri condividere.

1. Nella barra degli strumenti di gestione del filtro, fai clic su **[!UICONTROL Share]**.

1. Se sei un amministratore, puoi selezionare Tutti o scegliere tra Gruppi e Utenti dell’organizzazione. In qualità di non amministratore, puoi visualizzare solo singoli utenti. Usa il campo Ricerca per cercare gruppi o utenti. Fai clic su **[!UICONTROL Share]**. Accanto al filtro viene visualizzata l’icona Condiviso: ![](assets/share_icon.png)

1. Puoi filtrare i filtri condivisi con te selezionando Filtri > Altri filtri > Condivisi con me.

### Contrassegnare i filtri come preferiti

Contrassegnare i segmenti come preferiti è un altro modo per organizzarli in modo semplice e intuitivo.

1. Nel Gestore filtri, seleziona la stella accanto a qualsiasi filtro che desideri contrassegnare come preferito. La stella diventa gialla quando la selezioni.

1. Puoi anche filtrare i preferiti in Filtri > Altri filtri > Preferiti.

