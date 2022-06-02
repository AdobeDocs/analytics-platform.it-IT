---
title: Gestisci i tipi di pubblico creati nel Customer Journey Analytics
description: Scopri come gestire i tipi di pubblico in Customer Journey Analytics
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---


# Gestisci i tipi di pubblico creati nel Customer Journey Analytics

La gestione dei tipi di pubblico creati in precedenza consente di:

* **Pianificazione o disprogrammazione** aggiornamento/aggiornamento automatico del pubblico. La scadenza massima sulla pianificazione è di 1 anno.
* **Rinnovare una pianificazione di aggiornamento del pubblico** quando sta per scadere. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza della pianificazione.
* **Visualizza l&#39;ultima volta che un pubblico è stato aggiornato**
* Approfondisci **tempo necessario per produrre un pubblico** dal Customer Journey Analytics (CJA) e il tempo necessario per far apparire il pubblico nel Profilo del cliente in tempo reale a scopo di attivazione.
* Scopri se i tipi di pubblico in CJA sono **utilizzato attivamente dal profilo cliente in tempo reale** o (idealmente) qualsiasi applicazione di Experience Platform che utilizzi i tipi di pubblico creati da CJA.

## Interfaccia utente di gestione

schermata

| Impostazione dell’interfaccia utente | Definizione |
| --- | --- |
| Nascondi/Mostra filtri | Consente di mostrare o nascondere i seguenti filtri nella barra a sinistra: <ul><li>Visualizzazione dati</li><li>Proprietario</li><li>Frequenza di aggiornamento</li><li>Tag</li></ul> |
| Titolo e descrizione |  |
| Visualizzazione dati |
| Dimensione del pubblico |  |
| Proprietario |  |
| Frequenza di aggiornamento |  |
| Tag |  |
| Ultimo aggiornamento |  |
| Ultima modifica |  |

{style=&quot;table-layout:auto&quot;}

## Visualizzare e utilizzare i tipi di pubblico di CJA in Experience Platform

Puoi visualizzare i tipi di pubblico CJA in Platform accedendo a [!UICONTROL Segments] > [!UICONTROL Create segments] > [!UICONTROL Audiences] scheda > [!UICONTROL CJA Audiences].

![](assets/audiences-aep.png)

Se scegli di esportare questo pubblico in AEP Data Lake, verrà visualizzato come un set di dati conforme alla classe di schema del profilo individuale XDM:

![](assets/aep-datalake.png)

