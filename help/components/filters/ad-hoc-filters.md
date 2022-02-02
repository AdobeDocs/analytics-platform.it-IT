---
description: Utilizzare filtri ad hoc in Analysis Workspace.
title: Filtri di progetto ad hoc
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: cea2faeaf9c2779ab808506025780fd3659a94b1
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 10%

---

# Filtri di progetto ad hoc

Ecco un video sulla creazione di filtri per progetti ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puoi creare filtri di progetto ad hoc se desideri esplorare rapidamente in che modo un filtro potrebbe influenzare il progetto, senza passare al Generatore di segmenti. Considera questi filtri come filtri temporanei a livello di progetto. In genere non fanno parte della &quot;libreria&quot; del filtro, come i filtri dei componenti nella barra a sinistra. Tuttavia, puoi salvarli, come illustrato di seguito.

Per un confronto tra le funzioni dei filtri di progetto ad hoc e i filtri a livello di componente a tutti gli effetti, vai [qui](/help/components/filters/filters-overview.md).

1. Rilascia qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, filtro, modello di filtro, intervallo di date) nella zona di rilascio del filtro nella parte superiore di un pannello. I tipi di componente vengono automaticamente convertiti in filtri.
Ecco un esempio di come creare un filtro per il dominio di riferimento Twitter:

   ![](assets/ad-hoc1.png)

   Il pannello applica automaticamente questo filtro e potrai vedere immediatamente i risultati.

1. Puoi aggiungere a un pannello un numero illimitato di componenti.
1. Se decidi di salvare questo filtro, consulta la sezione seguente.

Nota bene:

* You **impossibile** rilascia i seguenti tipi di componenti nella zona filtro: metriche calcolate e dimensioni/metriche da cui non è possibile creare filtri.
* Per eventi e dimensioni complete, Analysis Workspace crea filtri hit &quot;exists&quot; (esiste). Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Se nella zona di rilascio del filtro viene rilasciato &quot;non specificato&quot; o &quot;nessuno&quot;, questo viene automaticamente convertito in un filtro &quot;non esiste&quot; in modo che venga trattato correttamente nel filtro.

>[!NOTE]
>
>I segmenti creati in questo modo sono interni al progetto.

## Salvare filtri di progetto ad hoc {#ad-hoc-save}

Puoi scegliere di salvare questi filtri seguendo questi passaggi:

1. Passa il puntatore del mouse sul filtro nella zona di rilascio e fai clic sull’icona &quot;i&quot;.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Save]**.

   ![](assets/segment-info.png)

## Cosa sono i filtri per soli progetti?

I filtri solo progetto sono filtri rapidi o filtri di progetto ad hoc di Workspace. Quando li si modifica/apre nel generatore di filtri, viene visualizzata la casella solo progetto. Se si applica un filtro rapido nel generatore ma non si seleziona la casella rendi disponibile, si tratta comunque di un filtro solo progetto, ma non può più essere aperto nel generatore QS. Se selezionano la casella e salvano ora è un filtro elenco di componenti.
