---
title: Chiavi gestite dal cliente
description: Scopri come configurare chiavi gestite dal cliente per Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# Chiavi gestite dal cliente

Adobe Customer Journey Analytics fornisce alla clientela di [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e Privacy &amp; Security Shield l’opzione di utilizzare le chiavi gestite dal cliente (CMK) per i dati Customer Journey Analytics. Tieni presente che questo processo è separato dalla [configurazione CMK di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Le chiavi gestite dal cliente sono attualmente disponibili solo per le organizzazioni che hanno acquistato l’offerta del componente aggiuntivo [Healthcare Shield o Privacy &amp; Security Shield](https://experienceleague.adobe.com/it/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurare le chiavi gestite dal cliente per Customer Journey Analytics in Azure

Per configurare le CMK per Customer Journey Analytics in esecuzione su Azure, segui questi passaggi:

1. Assicurati di avere diritto alle CMK di Adobe Customer Journey Analytics e che la tua organizzazione utilizzi Adobe Experience Platform in esecuzione su Azure. Per verificare questi diritti, contatta il team del tuo account Adobe.
1. Assicurati di essere un amministratore con un ruolo privilegiato in Azure, ad esempio Amministratore di applicazioni, Amministratore di applicazioni cloud o Amministratore globale. Per ulteriori informazioni, consulta [Ruoli incorporati di Microsoft Entra](https://learn.microsoft.com/it-it/entra/identity/role-based-access-control/permissions-reference).
1. Crea un nuovo Key Vault di Azure da utilizzare solo con Customer Journey Analytics. Per ulteriori informazioni, consulta la [documentazione Key Vault di Microsoft Azure](https://learn.microsoft.com/it-it/azure/key-vault/general/).
1. Concedi all’app di Azure di Adobe l’accesso alla tua chiave nell’insieme di credenziali delle chiavi. Per ulteriori informazioni, consulta [Configurare le chiavi gestite dal cliente per un account esistente](https://learn.microsoft.com/it-it/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault). L’ID applicazione Adobe è:

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Crea un ticket dell’Assistenza clienti di Adobe per richiedere la configurazione della CMK. Includi l’URI di Azure nel ticket. L’URI può essere trovato nel campo **Identificatore chiave** della chiave di Azure:

   ![Campi dell’identificatore chiave che mostrano l’URI per https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. L’Assistenza clienti di Adobe conferma il completamento dell’applicazione CMK sui tuoi dati Customer Journey Analytics.

Tutti i dati utilizzati da Platform sono crittografati sia durante il trasferimento che quando sono inattivi in modo da garantirne la sicurezza, con o senza chiavi gestite dal cliente. Per informazioni sulla crittografia di Adobe Experience Platform, consulta [Crittografia dei dati in Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configurare le chiavi gestite dal cliente per Customer Journey Analytics su Amazon Web Services

>[!AVAILABILITY]
>
>Questa sezione viene applicata alle implementazioni di Experience Platform in esecuzione su Amazon Web Services (AWS). Experience Platform in esecuzione su AWS è attualmente disponibile per un numero limitato di clienti. Per ulteriori informazioni sull’infrastruttura Experience Platform supportata, consulta la [Panoramica multi-cloud di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/multi-cloud).

Se la tua organizzazione utilizza Adobe Experience Platform in esecuzione su Amazon Web Services, le CMK sono già configurate per te. Non è necessaria alcuna configurazione aggiuntiva.
