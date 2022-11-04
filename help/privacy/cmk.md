---
title: Chiavi gestite dal cliente
description: Scopri come configurare le chiavi gestite dal cliente per CJA.
source-git-commit: 903c1423c91b220524174fa900a9ec13cd2051c6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 83%

---

# Chiavi gestite dal cliente

>[!NOTE]
>
>Questa funzionalità sarà disponibile a novembre 2022.

Customer Journey Analytics (CJA) offre ai clienti di [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e Privacy &amp; Security Shield l’opzione di utilizzare una chiave gestita dal cliente di Azure (CMK) da applicare ai dati CJA.  Tieni presente che questo processo è separato dalla [configurazione della CMK in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=it).

>[!NOTE]
>
>Le chiavi gestite dal cliente sono attualmente disponibili solo per le organizzazioni che hanno acquistato il componente aggiuntivo [Healthcare Shield o Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den).

## Configurare la CMK per CJA

Per configurare la CMK per CJA, segui questi passaggi:

1. Assicurati di avere diritto alla CMK di Adobe CJA controllando con il tuo account team di Adobe.
1. Assicurati di essere un amministratore con un ruolo privilegiato in Azure, ad esempio Amministratore di applicazioni, Amministratore di applicazioni cloud o Amministratore globale. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/active-directory/roles/permissions-reference)
1. Crea un nuovo Key Vault di Azure da utilizzare solo con CJA. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/key-vault/general/)
1. Concedi all’app di Azure di Adobe l’accesso alla tua chiave nell’insieme di credenziali delle chiavi. Questo è l’ID applicazione di Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Crea un ticket dell’Assistenza clienti di Adobe per richiedere la configurazione della CMK. Includi l’URI di Azure nel ticket. L’URI si trova nella variabile **Identificatore chiave** campo della chiave di Azure.

   ![](assets/key-identifier.png)

1. L’Assistenza clienti di Adobe confermerà il completamento dell’applicazione CMK sui tuoi dati CJA.

Tutti i dati utilizzati da Platform sono crittografati in transito e a riposo per proteggere i tuoi dati, con o senza CMK. Per informazioni sulla crittografia Adobe Experience Platform, [ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).