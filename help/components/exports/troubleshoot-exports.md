---
description: Gestire i registri per le esportazioni esistenti
keywords: Analysis Workspace
title: Risoluzione dei problemi di esportazione non riuscita
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 3252a41f5ee1f439a3f233b06a8be1fdf6150234
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---

# Risoluzione dei problemi di esportazione non riuscita

{{release-limited-testing}}

Quando [esportare tabelle complete da Analysis Workspace a destinazioni cloud](/help/analysis-workspace/export/export-cloud.md), è possibile visualizzare lo stato di tali esportazioni sia da [Scheda Esportazioni](/help/components/exports/manage-exports.md) e dal [Scheda Registri](/help/components/exports/manage-export-logs.md). Le esportazioni non riuscite mostrano lo stato [!UICONTROL **Non riuscito**].

## Errori e azioni comuni

Le esportazioni possono non riuscire per vari motivi. Nella tabella seguente vengono descritti alcuni dei motivi più comuni, con azioni che è possibile eseguire per risolvere gli errori:

| Motivo dell’errore | Azione suggerita | Ulteriori informazioni |
|---------|----------|---------|
| Informazioni sulla posizione o sull&#39;account non valide | Assicurati che le credenziali e altre informazioni siano corrette per l’account cloud e la posizione in cui stai effettuando l’esportazione. | [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md). |
| Una dimensione o metrica nel rapporto è stata rimossa dalla visualizzazione dati | Contatta l’amministratore di sistema per vedere quali componenti sono stati rimossi dalla visualizzazione dati. Potrebbe essere necessario utilizzare una visualizzazione dati diversa nell’esportazione oppure rimuovere dalla tabella i componenti non più disponibili. | [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md) |
| Limite righe superato | A seconda del tipo di licenza, è possibile esportare un massimo di 3 milioni, 30 milioni, 150 milioni o 300 milioni di righe. Aggiorna la tabella che stai esportando per ridurre il numero di righe totali. | [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md) |
| Scadenza esportazione pianificata | L&#39;esportazione pianificata configurata è scaduta. Aggiorna la scadenza dell’esportazione. | [Gestione esportazioni](/help/components/exports/manage-exports.md) |
| Dimension non supportato | <p>Qualsiasi dimensione che soddisfi tutti i seguenti criteri non è supportata in Esportazione tabella completa:</p> <ul><li>È stato creato da un campo che fa parte di un array di oggetti</li><li>Con persistenza abilitata<li>Non utilizza una dimensione di binding</li> | <ul><li>[Utilizzo di array di oggetti](/help/use-cases/object-arrays.md)</li><li>[Impostazioni dei componenti di persistenza](/help/data-views/component-settings/persistence.md)<li>[Utilizzare dimensioni e metriche di binding nel Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Un criterio di governance dei dati applicato dall’organizzazione impedisce l’esportazione di componenti nella tabella | Contatta l’amministratore di sistema per vedere quali componenti sono soggetti a restrizioni all’esportazione. Rimuovere i componenti con restrizioni prima dell&#39;esportazione. | *Filtrare i criteri di governance dei dati nelle visualizzazioni dati* sezione in [Etichette e criteri](/help/data-views/data-governance.md) |

## Contatta l’Assistenza clienti di Adobe

Se continui a riscontrare problemi, contatta l’Assistenza clienti Adobe. Quando contatta l’Assistenza clienti per un’esportazione non riuscita, accertati di disporre delle seguenti informazioni:

* Nome esportazione

* ID esportazione

* ID istanza

* Nome delle visualizzazioni dati

* Posizione

* Account

* Connessione

* Nome dell’azienda
