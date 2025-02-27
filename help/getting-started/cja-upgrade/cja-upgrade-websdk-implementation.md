---
title: Comprendere le opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics
description: Scopri le opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 43%

---

# Comprendere le opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Libreria JavaScript di Web SDK (alloy.js)"
>abstract="Includi la libreria Web SDK (alloy.js) in ogni pagina del sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Estensione tag Web SDK"
>abstract="(Consigliato) Se non utilizzi ancora i tag, installa il caricamento di tag sul sito. Se utilizzi già i tag, puoi aggiungere l’estensione Web SDK alla proprietà tag. Questa opzione include implementazioni utilizzando i tag all’interno della raccolta dati di Adobe Experience Platform e i sistemi di gestione dei tag di terze parti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Pacchetto NPM"
>abstract="Utilizza l’API di raccolta dati per inviare i dati direttamente a uno stream di dati. Sono supportati sia i tipi non autenticati (da client a server) che autenticati (da server a server)."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Il processo consigliato di aggiornamento da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics.

Sono disponibili tre metodi supportati per utilizzare Adobe Experience Platform Web SDK:

* [Estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe consiglia di utilizzare questo metodo. Installa un caricatore di tag sul sito, quindi utilizza l’interfaccia utente di Adobe Experience Platform Data Collection per configurare la tua implementazione.

* [Libreria JavaScript di Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): fai riferimento a un file di libreria ospitato da CDN o ospita il file di libreria utilizzando la tua infrastruttura. Effettua chiamate alla libreria all&#39;interno del codice sul tuo sito.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): installare Web SDK nel sito utilizzando Gestione pacchetti NPM.

Per ulteriori informazioni, vedere [Panoramica sull&#39;installazione di Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) nella Guida di Experience Platform Web SDK.



