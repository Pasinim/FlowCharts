# FlowCharts

Cartella contenente i diagrammi (UML + FSM) del corso di SWENG.

## Cosa è UML (Unified Modeling Language)?

Una macchina di stato in UML consente la modellazione dinamica ed è associata ad una *classe* e descrive il comportamento di un oggetto della classe. In UML si adotta la notazione di Harel.

Uno **stato** rappresena una condizione di esistenza dell'oggetto cioè l'attesa di un evento o l'esecuzione di certe *azioni* (operazione atomiche non interrompibili); <u>[vengono indicate con ```entry``` quando l'azione viene eseguita entrando nello stato o con ```exit``` quando l'azione viene eseguita uscendo dallo stato]</u> oppure di *attività* (operazioni che richiedono un certo tempo).

Le azioni `exit` precedono quelle della transizione mentre le azioni `entry` seguono quelle della transizione.

Una **guardia** è un predicato sullo stato di un'altra classe

Una **transizione** indica un passaggio di stato ed è etichettata con:

- gli eventi che comportano il cambiamento di stato e le condizioni sotto cui ha effetto: ```evento(parametri) [condizione] / azione ^ target.messaggio(parametri)```. <u>Dopo `/` viene indicata l'azione che viene eseguita.</u>

- le azioni che l'oggetto esegue prima di cambiare stato

## Tipi di evento

1. *Call event* (iterazione con altri oggetti): un oggetto invoca un'operazione propria o di un altro oggetto

2. *Signal event* (iterazione con altri oggetti): ( ```<<signal>>```) si verifica quando l'oggetto riceve un segnale da un altro oggetto

3. *Time Event* ```after(quantità temporale)```

4. *change event* ```when(espressione booleana)```

## Branching

- **Junction pseudostate:** viene utilizzata per la rappresentazione dei punti  di decisione:
  
  <img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-12-02-image.png" title="" alt="" width="440">

- **Choice pseudostate**: le guardie sono valutate nell'istante in cui il punto di decisione è raggiunto:
  
  <img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-12-40-image.png" title="" alt="" width="440">

## Stati composti sequenziali

Uno stato può contenere una macchina di stato:
<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-20-35-image.png" title="" alt="" width="485">

Esempio:
<img title="" src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-20-57-image.png" alt="" width="459">

## Transizione di completamento

Viene attivata da un completion event, che viene generato quando una macchina annidata o una attività interna termina:
<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-29-55-image.png" title="" alt="" width="428"> 

## Regole di scatto

Più transizioni possono essere abilitate dallo stesso evento nello stesso istante, hanno la precedenza le transizioni più interne:
<img title="" src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-33-21-image.png" alt="" width="435">

## Stati composti paralleli

Reagiscono ad uno stesso evento in modo simultaneo, come ad esempio superare un esame in cui ci sono più moduli:
<img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-51-51-image.png" title="" alt="" width="545">

## Iterazioni di diagrammi di stato

La sincronizzazione tra diagrammi in regioni parallele può avvenire tramite:

1. Condizioni o variabili condivise
   
   <img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-56-07-image.png" title="" alt="" width="391">

2. eventi: le azioni di un diagramma diventano eventi a cui altri diagrammi devono o possono reagire

3. stati di sincronizzazione
   
   <img src="file:///C:/Users/Marco/AppData/Roaming/marktext/images/2022-05-03-11-56-42-image.png" title="" alt="" width="435">

# Casi d'uso

I casi d'uso sono il punto di partenza per progettare il SW e sono il riferimento per la definizione, la progettazione e l'esecuzione dei test per la verifica. *Rappresentano delle naturali unità di rilascio* e descrive le funzionalità attese del sistema. Per identificarli si parte dai requisiti già rilevati e si identificano tutte le tipologie di utilizzatori del sistema. 
Il template per il caso d'uso è il seguente:

| Sezione caso d'uso                            | Commento                                                                |
| --------------------------------------------- | ----------------------------------------------------------------------- |
| Nome CU                                       | Inizia con un verbo                                                     |
| Portata                                       | Il sistema che si sta progettando                                       |
| Livello                                       | Obiettivo utente o sottofunzione                                        |
| Attore primario                               | Chiede al sistema di fornigli gli strumenti per raggiungere l'obiettivo |
| Parti interessate e Interessi (obiettivo)     | A chi interessa questo caso d'uso e che cosa desidera                   |
| Pre-condizioni                                | Cosa deve essere vero all'inizio                                        |
| Post-Condizioni                               | Cosa deve essere vero se il CU viene completato con successo            |
| Scenario principale di successo               | Scenario comune di successo                                             |
| Estensioni                                    | Scenari alternativi                                                     |
| Requisiti speciali                            | Requisiti non funzionali correlati                                      |
| Elenco delle varianti tecnologiche e dei dati | Varianti nei metodi di I/O e nel formato dei dati                       |
| Frequenza di ripetizione                      | Frequenza prevista di esecuzione del CU                                 |
| Varie                                         | Altri aspetti, problemi aperti, casi d'uso correlati, ecc...            |

È anche possibile definire delle relazioni tra casi d'uso (`extend`, `include`)
<u>Uno **scenario** è una istanza di un caso d'uso, ossia una esecuzione particolare dello use case</u>. Gli scenari possono essere di successo o di fallimento e si dividono in scenari principali (più possibili) e secondari (pochi ma significativi).

**Scenario base:** segnario più semplice che posta al successo del caso d'uso.
