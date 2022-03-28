---
description: Utilizzare filtri ad hoc in Analysis Workspace.
title: Filtri di progetto ad hoc
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: c053a1517030b68875fe7f4518dbbd473dbe1b47
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%

---

# Filtri di progetto ad hoc

I filtri per progetti ad hoc ti consentono di trascinare e rilasciare qualsiasi componente direttamente nella zona di rilascio del pannello per creare un filtro. Il filtro diventa un [filtro a livello di progetto](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html?lang=it) locale al progetto corrente.

Ecco un video sulla creazione di filtri per progetti ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. Rilascia qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio del filtro nella parte superiore di un pannello. I tipi di componente vengono automaticamente convertiti in filtri ad hoc o [Filtri rapidi](/help/components/filters/quick-filters.md) se compatibile.

   Ecco un esempio di come creare un filtro per il dominio di riferimento Twitter:

   ![](assets/ad-hoc1.png)

   Il pannello applica automaticamente questo filtro e potrai vedere immediatamente i risultati.

1. Puoi aggiungere un numero illimitato di filtri a un pannello.
1. Se decidi di salvare questo filtro, consulta la sezione seguente.

Nota bene:

* You **impossibile** rilascia i seguenti tipi di componenti nella zona filtro: metriche calcolate e dimensioni/metriche da cui non è possibile creare filtri.
* Per eventi e dimensioni complete, Analysis Workspace crea filtri hit &quot;exists&quot; (esiste). Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Se nella zona di rilascio del filtro viene rilasciato &quot;non specificato&quot; o &quot;nessuno&quot;, questo viene automaticamente convertito in un filtro &quot;non esiste&quot; in modo che venga trattato correttamente nel filtro.

## Salvare filtri di progetto ad hoc {#ad-hoc-save}

Puoi scegliere di salvare questi filtri seguendo questi passaggi:

1. Passa il puntatore del mouse sul filtro nella zona di rilascio e fai clic sull’icona &quot;i&quot;.
1. Fai clic sulla matita di modifica per passare al Generatore di filtri.
1. Controlla **[!UICONTROL Make available to all projects and add to your component list]**.
1. Fai clic su **[!UICONTROL SAVE]**.

Una volta salvato, il filtro è disponibile nell’elenco dei componenti della barra a sinistra e può essere condiviso con altri utenti dal Gestore filtri.

