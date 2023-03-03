---
title: Chiavi gestite dal cliente
description: Scopri come configurare le chiavi gestite dal cliente per CJA.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---

# Chiavi gestite dal cliente

Customer Journey Analytics (CJA) offre ai clienti di [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e Privacy &amp; Security Shield l’opzione di utilizzare una chiave gestita dal cliente di Azure (CMK) da applicare ai dati CJA.  Tieni presente che questo processo è separato dalla [configurazione della CMK in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=it).

>[!NOTE]
>
>Le chiavi gestite dal cliente sono attualmente disponibili solo per le organizzazioni che hanno acquistato il componente aggiuntivo [Healthcare Shield o Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=it).

## Configurare la CMK per CJA

Per configurare la CMK per CJA, segui questi passaggi:

1. Assicurati di avere diritto alla CMK di Adobe CJA controllando con il tuo account team di Adobe.
1. Assicurati di essere un amministratore con un ruolo privilegiato in Azure, ad esempio Amministratore di applicazioni, Amministratore di applicazioni cloud o Amministratore globale. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/active-directory/roles/permissions-reference)
1. Crea un nuovo Key Vault di Azure da utilizzare solo con CJA. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/key-vault/general/)
1. Concedi all’app di Azure di Adobe l’accesso alla tua chiave nell’insieme di credenziali delle chiavi. Questo è l’ID applicazione di Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Ulteriori informazioni da Microsoft](https://learn.microsoft.com/it-it/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Crea un ticket dell’Assistenza clienti di Adobe per richiedere la configurazione della CMK. Includi l’URI di Azure nel ticket. L’URI si trova nel campo **Identificatore chiave** della chiave di Azure.

   ![](assets/key-identifier.png)

1. L’Assistenza clienti di Adobe confermerà il completamento dell’applicazione CMK sui tuoi dati CJA.

Tutti i dati utilizzati da Platform sono crittografati sia durante il trasferimento che quando sono inattivi per proteggerli con o senza CMK. Per informazioni sulla crittografia di Adobe Experience Platform, vedi [ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=it).
