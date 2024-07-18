---
title: Creare un intervallo di date
description: Crea un intervallo di date da utilizzare nel reporting.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 4%

---

# Creare un intervallo di date

Puoi creare un intervallo di date utilizzando uno dei due metodi seguenti:

* Direttamente in un progetto Workspace facendo clic sul pulsante &#39;`+`&#39; accanto all&#39;elenco dei componenti dell&#39;intervallo di date a sinistra
* Nel gestore degli intervalli di date

Per creare un intervallo di date nel gestore degli intervalli di date:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le credenziali Adobe ID.
1. Passa a [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Fare clic sul pulsante [!UICONTROL Add] per aprire la finestra modale che crea un intervallo di date.

## Creare una finestra modale di intervallo di date

La finestra modale dispone di quattro campi che è possibile modificare:

* **Intervallo date**: l&#39;intervallo di date desiderato per questo componente.
* **Titolo**: il nome desiderato per questo componente. Il titolo viene utilizzato nei progetti Workspace.
* **Descrizione**: la descrizione desiderata per questo componente. La descrizione viene visualizzata facendo clic sull&#39;icona ![i](../assets/i.png).
* **Tag**: utilizza i tag per organizzare gli intervalli di date. Un intervallo di date può appartenere a più tag.

## Selezione di un intervallo di date

Quando fai clic sull’intervallo di date nella finestra modale, puoi scegliere tra diverse opzioni:

* **Calendario**: selezionare la data di inizio e di fine.
* **Utilizza date continue**: seleziona questa casella se desideri che l&#39;intervallo di date cambi con il passare del tempo. Non selezionare questa casella se si desidera che l’intervallo di date rimanga statico.
* **Seleziona predefinito**: utilizza questa selezione a discesa se desideri un intervallo di date personalizzato basato su un intervallo offerto da Adobe per impostazione predefinita. Quando selezioni un predefinito, puoi personalizzare ulteriormente l’intervallo di date in base alle tue esigenze. Non influisce sul predefinito offerto da Adobe.

## Intervalli di date continui

Se desideri un intervallo di date continuo, puoi personalizzarlo durante il rollup. È possibile controllare quando le date di inizio e di fine vengono riportate indipendentemente l&#39;una dall&#39;altra.

* **Quando inizia la data**: scegliere se la data inizia all&#39;inizio di un periodo di tempo, alla fine di un periodo di tempo o utilizzare un giorno fisso.
* **Periodo di tempo da utilizzare**: scegliere la frequenza di rollup dell&#39;intervallo di date. Puoi farla rotolare ogni giorno, ogni settimana, ogni mese, ogni trimestre, o ogni anno.
* **Offset**: scegli l&#39;offset dell&#39;intervallo di date. È possibile aggiungere o sottrarre giorni, settimane, mesi, trimestri o anni.

## Esempi di date continue

Alcuni intervalli di date possono essere utili in alcuni rapporti.

Progressivo anno:

```text
Start: Start of current year
End: End of current day
```

Giovedì scorso a questo giovedì:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Anno fiscale (ad esempio, se un anno fiscale inizia in dicembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
