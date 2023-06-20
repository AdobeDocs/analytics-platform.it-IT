---
title: Come configurare le impostazioni per il Report Builder nel Customer Journey Analytics
description: Descrive come impostare la modalità offline, la lingua, la data di fine e le impostazioni per la risoluzione dei problemi.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 4%

---

# Impostazioni Report Builder

Utilizza il **Impostazioni** per configurare le impostazioni a livello di applicazione, ad esempio la lingua visualizzata dall&#39;interfaccia utente o se utilizzare o meno la modalità non in linea. Le impostazioni vengono applicate immediatamente e vengono impostate per tutte le sessioni future fino a quando non vengono modificate.

Per modificare le impostazioni del Report Builder

1. Fai clic su **Impostazioni** icona.

1. Apportare le modifiche necessarie per attivare la modalità offline, selezionare una lingua o attivare le impostazioni del registro di risoluzione dei problemi.

1. Fai clic su **Applica**.

   ![](./assets/image38.png)

## Modalità offline

Durante la creazione e la modifica di un blocco di dati in modalità offline, i dati non vengono recuperati. Al contrario, i dati di simulazione vengono utilizzati in modo da poter creare e modificare rapidamente un blocco di dati senza attendere l’esecuzione della richiesta. Quando si torna online, il *Aggiorna blocco di dati* comando o *Aggiorna tutti i blocchi di dati* Il comando aggiorna i blocchi di dati creati con i dati effettivi.

Per attivare la modalità offline

1. Fai clic su **Impostazioni** icona.

1. Seleziona **Abilita modalità offline**.

1. Inserisci un numero intero positivo nel campo **Visualizza dati metrica come** campo.

1. Fai clic su **Applica**.

## Lingua

Puoi scegliere la lingua per l’interfaccia utente del Report Builder. Sono disponibili tutte le lingue Adobe Analytics supportate.

Per selezionare la lingua utilizzata nell’interfaccia utente del Report Builder

1. Fai clic su Impostazioni.

1. Seleziona una lingua dal **Lingua** menu a discesa.

   ![](./assets/image39.png)

1. Fai clic su **Applica.**

## Risoluzione dei problemi

Utilizzare l&#39;impostazione Risoluzione dei problemi per registrare tutti i dati client/server in un file locale. Utilizza questa opzione per risolvere i ticket di supporto.

Per abilitare l’opzione Risoluzione dei problemi, seleziona **Registra la richiesta di Report Builder su file locale**.
