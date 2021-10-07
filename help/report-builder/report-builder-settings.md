---
title: Come configurare le impostazioni per il Report Builder in CJA
description: Descrive come impostare la modalità offline, la lingua, la data e le impostazioni di risoluzione dei problemi.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---


# Impostazioni Report Builder

Utilizza il riquadro **Impostazioni** per configurare le impostazioni a livello di applicazione, ad esempio la lingua visualizzata dall&#39;interfaccia utente o se lavorare o meno in modalità offline. Le impostazioni vengono applicate immediatamente e vengono impostate per tutte le sessioni future fino a quando non vengono modificate.

Per modificare le impostazioni del Report Builder

1. Fai clic sull&#39;icona **Impostazioni**.

1. Apportare modifiche alla modalità off-line, selezionare una lingua o abilitare le impostazioni del registro per la risoluzione dei problemi.

1. Fai clic su **Applica**.

   ![](./assets/image38.png)

## Modalità off-line

Durante la creazione e la modifica di un blocco di dati in modalità offline, i dati non vengono recuperati. Al contrario, i dati di simulazione vengono utilizzati per creare e modificare rapidamente un blocco di dati senza attendere l’esecuzione della richiesta. Quando si torna online, il comando *Aggiorna blocco dati* o *Aggiorna tutti i blocchi di dati* aggiorna i blocchi di dati creati con i dati effettivi.

Per attivare la modalità offline

1. Fai clic sull&#39;icona **Impostazioni**.

1. Selezionare **Abilita modalità offline**.

1. Immetti un numero intero positivo nel campo **Visualizza i dati della metrica come** .

1. Fai clic su **Applica**.

## Lingua

È possibile scegliere la lingua per l’interfaccia utente del Report Builder. Sono disponibili tutte le lingue Adobe Analytics supportate.

Selezione della lingua utilizzata nell’interfaccia utente del Report Builder

1. Fai clic su Impostazioni.

1. Seleziona una lingua dal menu a discesa **Lingua**.

   ![](./assets/image39.png)

1. Fai clic su **Applica.**

## Risoluzione dei problemi

Utilizzare l&#39;impostazione Risoluzione dei problemi per registrare tutti i dati client/server in un file locale. Utilizza questa opzione per risolvere i ticket di supporto.

Per abilitare l&#39;opzione Risoluzione dei problemi, selezionare **Registra richiesta generatore di report al file locale**.
