---
title: Includi impostazioni del componente Valori di esclusione
description: Includi o escludi in modo condizionale un elemento dimensione a seconda del relativo valore.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Includi impostazioni del componente Valori di esclusione

Includi valori di esclusione consente di creare regole che dipendono dal valore di un elemento dimensione. I valori che non soddisfano i criteri impostati vengono trattati in Analysis Workspace come se non fossero mai esistiti, anche se i dati esistono ancora nel set di dati sottostante.

![Includi esclusione](../assets/include-exclude.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set include/exclude values] | Casella di controllo che consente di abilitare le condizioni in cui i dati vengono inclusi in una visualizzazione dati. |
| [!UICONTROL Case sensitive] | Visibile sui tipi di dati dello schema di stringa. L&#39;impostazione predefinita è attivata. Questa impostazione si applica solo alle [!UICONTROL Include/Exclude Values] , non al valore risultante. Ti consente di specificare se la regola fa distinzione tra maiuscole e minuscole. |
| [!UICONTROL Match] | Consente di specificare quali valori si desidera considerare per il reporting prima dell’attribuzione e dei filtri (ad esempio, utilizza solo valori contenenti la frase &quot;error&quot;). Puoi specificare **[!UICONTROL If all criteria are met]** o **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Consente di specificare la logica di corrispondenza da applicare a una regola di filtro specifica.<ul><li>**Stringa**: Contiene la frase, Contiene qualsiasi termine, Contiene tutti i termini, Non contiene alcun termine, Non contiene la frase, È uguale a, Non uguale a, Inizia con, Termina con</li><li>**Doppio/Intero**: è uguale a, non è uguale a, è maggiore di, è minore di, è maggiore o uguale a, è minore o uguale a</li><li>**Data**: è uguale a, non è uguale a, è successivo a, è precedente, si trova in</li></ul> |
| [!UICONTROL Match operand] | Consente di specificare l’operando di corrispondenza a cui deve essere applicato l’operatore di corrispondenza.<ul><li>**Stringa**: Campo di testo</li><li>**Doppio/Intero**: Campo di testo con frecce verso l’alto o il basso per i valori numerici</li><li>**Data**: Selettore di granularità del giorno (calendario)</li><li>**Data e ora**: Selettore di granularità data e ora</li></ul> |
| [!UICONTROL Add rule] | Consente di specificare un operatore di corrispondenza e un operando aggiuntivi. |