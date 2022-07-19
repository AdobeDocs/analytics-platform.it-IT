---
title: Ingressi e uscite del pannello Tempo di riproduzione dei supporti
description: Quali sono le impostazioni di ingresso e uscita Tempo di riproduzione multimediale trascorso?
feature: Panels
role: User, Admin
exl-id: 4c0380ff-f55c-48a7-a4b2-1a291511e4d9
source-git-commit: 9f1394df9b57707d57c701e997df8f4cd70c7baa
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 92%

---

# Tempo di riproduzione dei contenuti multimediali Ingressi e Uscite del pannello {#Inputs-and-outputs}

Puoi personalizzare il pannello Tempo di riproduzione multimediale trascorso utilizzando le seguenti impostazioni di input e output.

## Input del pannello {#Input}

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione trascorso) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi le suddivisioni, per ciascuna viene visualizzato un numero di riepilogo. |
| Suddivisione per serie di dati | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. Le suddivisioni sono limitate a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di suddivisione per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione in Ore:Minutes:Secondi (impostazione predefinita) oppure in Minuti (visualizzati in numeri interi, arrotondati a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due segmenti di intervallo di date come raggruppamenti di serie, vedrai l’opzione per scegliere tra Overlay (Sovrapposizione, impostazione predefinita) o Sequential (Sequenziale). La visualizzazione in sovrapposizione presenta le linee con un inizio comune dell’asse X, in parallelo; quella sequenziale presenta le linee in sequenza, ciascuna con il proprio inizio dell’asse X. Se i dati sono allineati (ad esempio, il segmento 1 termina alle 20:44 e il segmento 2 inizia alle 20:45), le linee vengono visualizzate in sequenza. |

### Vista predefinita

![Vista predefinita](../assets/mpts_default_view.png)

## Output del pannello {#Output}

Il pannello Tempo di riproduzione multimediale trascorso restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona della matita (Modifica) in alto a destra.

Se hai selezionato la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output tempo di riproduzione dei contenuti multimediali](../assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale in ore:minutes:secondi (o minuti) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |
