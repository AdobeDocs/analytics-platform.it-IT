---
title: Impostazioni componente ambito
description: Configura il modo in cui un componente ha l'ambito per il reporting sulla popolazione totale.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
source-git-commit: a4f7eef26a019f4f8a716f44d49985290b135112
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 5%

---


# Impostazioni componente ambito {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="Ambito"
>abstract="Determina il modo in cui un componente viene valutato quando viene utilizzato nei rapporti. Puoi scegliere tra basato su evento, basato su profilo o basato su totale."

L’ambito di un componente metrica determina il modo in cui il componente viene utilizzato nei rapporti.

| Ambito | Descrizione |
|---|---|
| In base all’evento | L’ambito del componente metrica è basato su eventi. |
| In base al profilo | L’ambito del componente metrica è basato sul profilo. Quando il componente viene utilizzato nel reporting, negli intervalli di date, la metrica restituisce la popolazione dai dati del profilo, indipendentemente dall’intervallo di date applicato al pannello. I filtri di data e i confronti tra intervalli di date non influiscono sul reporting di questa metrica. |
| In base al totale | L’ambito del componente metrica è basato su profili ed eventi. Quando il componente viene utilizzato nel reporting, la metrica restituisce la popolazione dai dati del profilo e dell’evento, indipendentemente dall’intervallo di date applicato al pannello. I filtri di data e i confronti tra intervalli di date non influiscono sul reporting di questa metrica. |

