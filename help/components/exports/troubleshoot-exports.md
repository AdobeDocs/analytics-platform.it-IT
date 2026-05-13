---
description: Gestire i registri per le esportazioni esistenti
keywords: Analysis Workspace
title: Risoluzione dei problemi di esportazione non riuscita
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
TQID: https://experienceleague.adobe.com/pKXaX-DMxsFn9Y39AjqL1VGaSM--WFda9fuD7zJLgoI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 6%

---

# Risoluzione dei problemi di esportazione non riuscita

Quando [esporti tabelle complete da Analysis Workspace a destinazioni cloud](/help/analysis-workspace/export/export-cloud.md), puoi visualizzare lo stato di tali esportazioni sia dalla [scheda Esportazioni](/help/components/exports/manage-exports.md) che dalla [scheda Registri](/help/components/exports/manage-export-logs.md). Le esportazioni non riuscite mostrano uno stato di [!UICONTROL **Non riuscito**].

## Errori e azioni comuni

Le esportazioni possono non riuscire per vari motivi. Nella tabella seguente vengono descritti alcuni dei motivi più comuni, con azioni che è possibile eseguire per risolvere gli errori:

| Motivo dell’errore | Azione suggerita | Ulteriori informazioni |
|---------|----------|---------|
| Informazioni sulla posizione o sull&#39;account non valide | Assicurati che le credenziali e altre informazioni siano corrette per l’account cloud e la posizione in cui stai effettuando l’esportazione. | [Configura account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configura percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md). |
| Una dimensione o metrica nel rapporto è stata rimossa dalla visualizzazione dati | Contatta l’amministratore di sistema per vedere quali componenti sono stati rimossi dalla visualizzazione dati. Potrebbe essere necessario utilizzare una visualizzazione dati diversa nell’esportazione oppure rimuovere dalla tabella i componenti non più disponibili. | [Esporta report Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md) |
| Limite righe superato | A seconda del tipo di licenza, è possibile esportare un massimo di 3 milioni, 30 milioni, 150 milioni o 300 milioni di righe. Aggiorna la tabella che stai esportando per ridurre il numero di righe totali. | [Esporta report Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md) |
| Scadenza esportazione pianificata | L&#39;esportazione pianificata configurata è scaduta. Aggiorna la scadenza dell’esportazione. | [Gestisci esportazioni](/help/components/exports/manage-exports.md) |
| Dimension non supportato | <p>Qualsiasi dimensione che soddisfi tutti i seguenti criteri non è supportata in Esportazione tabella completa:</p> <ul><li>È stato creato da un campo che fa parte di un array di oggetti</li><li>Con persistenza abilitata<li>Non utilizza una dimensione di binding</li> | <ul><li>[Utilizzo di array di oggetti](/help/use-cases/object-arrays.md)</li><li>[Impostazioni del componente di persistenza](/help/data-views/component-settings/persistence.md)<li>[Utilizzare dimensioni e metriche di binding in Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Un criterio di governance dei dati applicato dall’organizzazione impedisce l’esportazione di componenti nella tabella | Contatta l’amministratore di sistema per vedere quali componenti sono soggetti a restrizioni all’esportazione. Rimuovere i componenti con restrizioni prima dell&#39;esportazione. | *Filtra i criteri di governance dei dati nelle visualizzazioni dati* sezione in [Etichette e criteri](/help/data-views/data-governance.md) |

## Contatta l’Assistenza clienti di Adobe

Se riscontri ancora problemi, contatta l’Assistenza clienti Adobe. Quando contatta l’Assistenza clienti per un’esportazione non riuscita, accertati di disporre delle seguenti informazioni:

* Nome esportazione

* ID esportazione

* ID istanza

* Nome delle visualizzazioni dati

* Posizione

* Account

* Connessione

* Nome società
