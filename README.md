# FlowCharts

Cartella contenente i diagrammi (UML + FSM) del corso di SWENG.



## Cosa è UML?

Una macchina di stato in UML consente la modellazione dinamica ed è associata ad una *classe* e descrive il comportamento di un oggetto della classe. In UML si adotta la notazione di Harel.

Uno **stato** rappresena una condizione di esistenza dell'oggetto cioè l'attesa di un evento o l'esecuzione di certe *azioni* (operazione atomiche non interrompibili); <u>[vengono indicate con ```entry``` quando l'azione viene eseguita entrando nello stato o con ```exit``` quando l'azione viene eseguita uscendo dallo stato]</u> oppure di *attività* (operazioni che richiedono un certo tempo).

Le azioni `exit` precedono quelle della transizione mentre le azioni `entry` seguono quelle della transizione.

Una **guardia** è un predicato sullo stato di un'altra classe

Una **transizione** indica un passaggio di stato ed è etichettata con:

- gli eventi che comportano il cambiamento di stato e le condizioni sotto cui ha effetto: ```evento(parametri) [condizione] / azione ^ target.messaggio(parametri)```

- le azioni che l'oggetto esegue prima di cambiare stato

## Tipi di evento

1. *Call event* (iterazione con altri oggetti): un oggetto invoca un'operazione propria o di un altro oggetto

2. *Signal event* (iterazione con altri oggetti): ( ```<<signal>>```) si verifica quando l'oggetto riceve un segnale da un altro oggetto

3. *Time Event* ```after(quantità temporale)```

4. *change event* ```when(espressione booleana)```

## Branching

- **Junction pseudostate:** viene utilizzata per la rappresentazione dei punti  di decisione:
  <img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-12-02-image.png" title="" alt="" width="440">

- **Choice pseudostate**: le guardie sono valutate nell'istante in cui il punto di decisione è raggiunto:<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-12-40-image.png" title="" alt="" width="440">

## Stati composti sequenziali

Uno stato può contenere una macchina di stato:
<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-20-35-image.png" title="" alt="" width="485">

Esempio:
<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-20-57-image.png" title="" alt="" width="515">
