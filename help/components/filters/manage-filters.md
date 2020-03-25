---
title: Gestire i filtri
description: come gestire i filtri nell'analisi del percorso cliente
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Gestire i filtri

Gestione filtri offre diversi modi per curare i segmenti, ad esempio condividere, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.

Gestione filtri mostra tutti i filtri di proprietà e che sono stati condivisi con voi. Gli utenti a livello di amministratore possono visualizzare tutti i filtri dell&#39;organizzazione. Questa panoramica presenta l’interfaccia utente e le funzionalità di Filter Manager (Gestore filtri).

Accedere a Gestione filtri scegliendo **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** nella navigazione superiore.

## Interfaccia utente di Filter Manager

![](assets/filter-manager-ui.png)

| # | Funzionalità interfaccia | Descrizione |
|---|---|---|
| 1 | Barra degli strumenti Gestione filtri | Dopo aver selezionato un filtro, viene visualizzata la barra degli strumenti. La maggior parte delle attività di gestione può essere completata da questa barra degli strumenti. |
| 2 | Caselle di controllo | Per gestire un filtro, controllatelo. |
| 4 | Preferiti | Facendo clic sulla stella accanto a un filtro, la stella diventa gialla e il filtro viene contrassegnato come preferito. |
| 5 | Titolo e descrizione | Fornito nel generatore di filtri. Per modificare il titolo e la descrizione, fate clic sul collegamento del titolo; in questo modo tornerete al Generatore di filtri. |
| 6 | Suite di rapporti | Questa colonna indica in quale suite di rapporti è stato salvato l&#39;ultimo filtro. |
| 7 | Proprietario | Indica la proprietà del filtro. In qualità di non amministratore, potete visualizzare solo i filtri posseduti o quelli condivisi con voi. |
| 8 | Tag (non selezionato nel selettore colonna, di conseguenza la colonna non viene visualizzata) | Tag applicati al filtro, da voi stessi o da altri utenti che lo hanno condiviso con voi. |
| 9 | Condiviso con | Elenca i singoli o i gruppi (solo Amministratore) o Tutti (solo Amministratore) con cui avete condiviso il filtro. |
| 10 | Data di modifica | Mostra la data dell’ultima modifica apportata al filtro. |
| 11 | Selettore colonna | (In alto a destra) Consente di selezionare le colonne da visualizzare in Gestore filtri. |
| 12 | Icona condivisa | Indica che questo filtro è condiviso da voi o con voi. |
| 13 | Icona Approvata | Indica che il filtro è stato approvato da un amministratore. |
| 14 | Altri filtri | Consente di visualizzare i filtri per tag, suite di rapporti, proprietari e altri (Mostra tutto, Personale, Condiviso con me, Approvato, Preferiti). |

## Filtri di piano

Dedicare un po&#39; di tempo ai segmenti di pianificazione aumenta le possibilità che siano utili per la vostra organizzazione e che il loro numero venga controllato.

* Considerate il pubblico: Chi lo consumerà? Con chi la condividerete? Quali gruppi di persone useranno questo filtro e come lo dovrei assegnare di conseguenza? Questo significa anche fornire una buona descrizione del filtro. Come minimo, la descrizione deve rispondere alle seguenti domande:

   * A cosa serve questo filtro?

   * Quando dovrei usare questo filtro?

* Determinare l’ambito del filtro. Quale contenitore [di](/help/components/filters/filters-overview.md) filtro rappresenta meglio l&#39;ambito? Utilizzate il contenitore più piccolo possibile.

* Decidete quali elementi includere nella definizione del filtro e quali valori.

* Considerate come desiderate che si svolga il processo di approvazione. Una singola persona rivedrà e approverà i filtri o sarà una decisione del comitato?

* Consente di definire i filtri con la vista di una libreria di filtri che consente agli utenti aziendali di impilare e riutilizzare componenti o filtri in modo modulare. Quali &quot;moduli&quot; è necessario definire per realizzare questa libreria?

### Filtri tag

In Gestione filtri, i filtri per tag consentono di organizzarli. Tutti gli utenti possono creare tag per i filtri e applicare uno o più tag a un segmento. Tuttavia, potete visualizzare solo i tag per i filtri di proprietà o che sono stati condivisi con voi.

Che tipo di tag creare? Di seguito sono riportati alcuni suggerimenti per tag utili:

* Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing.

* Tag del progetto (tag di analisi), ad esempio analisi per pagina di partecipazione.

* Tag categoria: Uomo; geografia.

* Tag del flusso di lavoro: Da approvare; Cura per (una specifica unità aziendale)

Per assegnare un tag a un filtro:

1. In Gestore filtri, contrassegnate la casella di controllo accanto al filtro a cui desiderate applicare il tag. Viene visualizzata la barra degli strumenti di gestione del filtro.

1. Fate clic **[!UICONTROL Tag]** su

   * selezionare da tag esistenti, oppure

   * immettete un nuovo nome per il tag e premete **[!UICONTROL Enter]**.

1. Fate **[!UICONTROL Tag]** di nuovo clic per assegnare un tag al segmento.

Il tag deve ora essere visualizzato nella colonna Tag. Fate clic sull’icona a forma di ingranaggio in alto a destra per gestire le colonne.
Potete anche filtrare i tag andando **[!UICONTROL Filters > Tags]**.

### Approvare i filtri

In Gestione filtri potete impostare un flusso di lavoro che include l&#39;approvazione del filtro per vari livelli di applicazione, per reparti o gruppi specifici e in linea con i criteri di reporting.

Come contrassegnare un filtro come approvato:

1. In Gestione filtri, selezionare la casella di controllo a sinistra del titolo Filtro.

1. Fate clic su **[!UICONTROL Approve]** nella barra delle attività di gestione del filtro.

1. Considera la condivisione dei segmenti approvati con la tua organizzazione.

1. Fai clic su **[!UICONTROL OK]**.

   Osservate l’icona di approvazione accanto al filtro nell’elenco:

   ![](assets/seg_approved.png)

1. Puoi anche annullare l’approvazione di un segmento approvato facendo clic su **[!UICONTROL Unapprove]**.

### Condivisione di filtri

A seconda delle autorizzazioni, potete condividere i filtri con l’intera organizzazione, i gruppi o i singoli utenti.

| Amministratore | Non amministratore |
|---|---|
| Può condividere i filtri con Tutti, Gruppi e Utenti. Per ulteriori informazioni, consulta la documentazione [di](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) Admin Console. | Può condividere i filtri solo con singoli utenti. |

Quando è necessario condividere i filtri con l’intera azienda anziché con un solo gruppo di utenti o singoli utenti? Seguono alcune best practice:

* In qualità di Amministratore, condividi un filtro con All se è utile per l&#39;intera azienda e tutti possono usarlo con facilità. In questo caso, si dovrebbe anche considerare la possibilità di renderlo un filtro approvato.

* In qualità di Amministratore, condividete un filtro con un profilo di prodotto specifico se il filtro fornisce un buon valore commerciale per quel team. Non approvare ufficialmente questo tipo di filtro.

* In qualità di Amministratore o di singolo utente, condividete un filtro con altri utenti per controllare e convalidare un filtro. Se non risulta utile, può essere scartato. Non approvare ufficialmente questo tipo di filtro.

Per condividere un filtro:

1. In Gestore filtri, contrassegnate la casella di controllo accanto al filtro da condividere.

1. Nella barra degli strumenti di gestione del filtro, fate clic su **[!UICONTROL Share]**.

1. Se siete un amministratore, potete selezionare Tutto o scegliere tra Gruppi e utenti nell’organizzazione. In qualità di non amministratore, potete visualizzare solo singoli utenti. Usate il campo Ricerca per cercare gruppi o utenti. Fai clic su **[!UICONTROL Share]**. Accanto al filtro viene visualizzata l&#39;icona Condiviso: ![](assets/share_icon.png)

1. Potete filtrare i filtri condivisi con voi selezionando Filtri > Altri filtri > Condiviso con me.

### Contrassegnare i filtri come preferiti

Contrassegnare i segmenti come preferiti è un altro modo per organizzarli in modo semplice e intuitivo.

1. In Gestione filtri, seleziona la stella accanto a qualsiasi filtro da contrassegnare come preferito. La stella diventa gialla quando la selezionate.

1. Potete anche filtrare i preferiti in Filtri > Altri filtri > Preferiti.

