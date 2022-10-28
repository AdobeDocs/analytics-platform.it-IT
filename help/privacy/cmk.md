---
title: Chiavi gestite dal cliente
description: Scopri come configurare le chiavi gestite dal cliente per CJA.
hide: true
hidefromtoc: true
source-git-commit: 90521aa7326486b9016321d35191a73ef891a0bc
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# Chiavi gestite dal cliente

>[!NOTE]
>
>Questa funzionalità sarà disponibile a novembre 2022.

Customer Journey Analytics (CJA) offre l’opzione per [Scudo sanitario](https://www.adobe.com/trust/compliance/hipaa-ready.html) e i clienti Privacy &amp; Security Shield per utilizzare una chiave gestita dal cliente di Azure (CMK) da applicare ai dati CJA.  Tieni presente che questo processo è separato da [Configurazione Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Le chiavi gestite dal cliente sono attualmente disponibili solo per le organizzazioni che hanno acquistato il [Scudo sanitario o scudo per la privacy e la sicurezza](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) offerta aggiuntiva.

## Configurare CMK per CJA

Per impostare CMK per CJA, effettua le seguenti operazioni:

1. Assicurati di avere diritto ad Adobe CJA CMK controllando con il team dell’account Adobe.
1. Assicurati di essere un amministratore con un ruolo privilegiato in Azure, ad esempio Amministratore applicazioni, Amministratore applicazioni cloud o Amministratore globale. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Crea un nuovo archivio chiavi di Azure da utilizzare solo con CJA. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Concedi all’app di Azure Adobe l’accesso alla tua chiave nell’insieme di chiavi. Adobe ID applicazione: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Crea un ticket di Adobe dell’Assistenza clienti per richiedere la configurazione CMK. Includi l’URI di Azure nel ticket. L’URI si trova nel campo ID chiave della chiave di Azure.
1. L’Assistenza clienti Adobe confermerà il completamento dell’applicazione CMK sui dati CJA.
