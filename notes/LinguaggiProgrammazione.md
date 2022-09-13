## Introduzione

Seguono delle definizioni introduttive alla programmazione.



### Linguaggio

Il *linguaggio umano* è una forma di comunicazione, tra due o più individui, attraverso un determinato insieme di suoni, gesti, simboli e movimenti, dotato di significato, comune ad uno specifico ambiente di comunicazione.



### Linguaggio di programmazione

Un linguaggio di programmazione è costituito, come ogni altro tipo di linguaggio, da un alfabeto con cui viene costruito un insieme di parole chiave (il vocabolario) e da un insieme di regole sintattiche (la grammatica) per l’uso corretto delle parole appartenenti al linguaggio stesso.

In generale, può essere utilizzato per impartire, ad una macchina (un computer), una serie di istruzioni volte al conseguimento di un risultato, cioè l'ottenimento di un dato in uscita.

##### Paradigma di programmazione

L'insieme degli strumenti concettuali, forniti da un linguaggio di programmazione, per la stesura del codice sorgente di un programma definisce lo stile di programmazione, ossia il modo in cui il programmatore concepisce e struttura il programma stesso, definendo, quindi, un modello, detto paradigma di programmazione.

Le differenze che sussistono tra i vari paradigmi esistenti dipendono, dunque, dalle astrazioni utilizzate per rappresentare gli elementi di un programma, quali funzioni, oggetti, variabili e dai procedimenti impiegati per l'esecuzione delle procedure atte all'elaborazione dei dati, come, ad esempio, l'assegnazione, il calcolo e l'iterazione.

##### Codice sorgente

Per codice sorgente si intende il testo di un algoritmo di un programma, scritto in un determinato linguaggio di programmazione e memorizzato all'interno di un file sorgente, ovvero un file di testo che definisce il flusso di esecuzione del programma stesso.

Questo codice sorgente, detto anche "sorgente" o "listato", si occuperà, quindi, di fornire delle indicazioni alla macchina, su come il programma possa essere tradotto, ossia compilato, in linguaggio macchina.

Si precisa che, con questa espressione, ci si può riferire anche a file di testo scritti in linguaggi informatici di tipo diverso, cioè linguaggi non di programmazione, come i linguaggi di markup, come HTML, oppure i linguaggi di interrogazione, come SQL.

##### Algoritmo

Con il termine "algoritmo" ci si riferisce ad una strategia atta alla risoluzione di un problema, costituita da una sequenza finita di operazioni.

Questa sequenza di istruzioni deve seguire queste caratteristiche, ovvero:

- deve avere un numero finito di istruzioni (se fosse infinito sarebbe un loop);
- deve essere privo di ambiguità (per non incorrere in bug);
- deve essere composto da passi elementari, oppure nel caso di passi complessi, questi devono essere ricreati da altri algoritmi.

#### Linguaggio macchina

I microprocessori, ovvero i circuiti elettronici che si occupano di elaborare le informazioni ricevute dall'elaboratore, sono progettati per eseguire un insieme piuttosto ristretto di istruzioni fondamentali, detto *instruction* *set* (comprensivo di una serie di azioni elementari), scritte in un linguaggio a basso livello, il cosiddetto linguaggio macchina.

Il *linguaggio macchina*, quindi, indica il linguaggio in cui sono scritti i programmi che possono essere direttamente eseguiti da un computer, perché basato su un alfabeto, detto *binario*, in quanto costituito da due simboli soltanto, indicati con 0 ed 1, ciascuno detto *bit*.

Quindi si può notare come sia basato su una codifica estremamente compatta e poco intuitiva, strettamente dipendente dal microprocessore che costituisce la CPU della macchina che si sta considerando; infatti, ogni calcolatore è provvisto da istruzioni logicamente simili, ma comunque differenti, perché particolarizzate proprio sulla base dell'hardware che lo compone.

#### Linguaggio a basso livello

Ci si riferisce alla programmazione a *basso livello* quando si utilizza un linguaggio molto vicino alla macchina, al suo funzionamento interno.

I programmi di questo tipo vengono eseguiti molto velocemente, però sono complicati da scrivere e strettamente dipendenti dall'architettura del calcolatore utilizzato.

In ogni caso, qualsiasi sia il linguaggio di programmazione utilizzato nella stesura del codice, prima della sua esecuzione dovrà passare, necessariamente, dal basso livello.

#### Linguaggio assemblativo

Il linguaggio *assembly*  è un linguaggio di programmazione simile al linguaggio macchina, che viene convertito in quest'ultimo tramite l'assembler, ovvero il programma "assemblatore".

I comandi scritti in questo linguaggio corrispondo a delle istruzioni che il processore può eseguire direttamente, perché rappresentate tramite delle stringhe di bit, però indicate attraverso delle parole-chiave più affini al linguaggio umano.

Questo processo di conversione da un linguaggio all'altro viene effettuato tramite l'associazione, a ciascuna istruzione, di un *Operation Code* corrispondente alla stessa, però in formato binario (oppure esadecimale)

Quindi, la diversità dei vari linguaggi assembly è dovuta al fatto che ciascuno di essi costituisce una translitterazioni delle istruzioni macchina di una particolare CPU.

##### Struttura di un calcolatore

Un generico sistema informatico è costituito da:

- una parte *hardware*, che consiste nei componenti fisici del sistema;
- una parte *software*, rappresentata dai programmi che vengono eseguiti dal sistema (ad esempio il sofwtare applicativo ed il software di base, come il sistema operativo).

Gli elementi funzionali che compongono l'hardware sono:

- l'unità di calcolo o processore, detta "Central Processing Unit", che svolge l'elaborazione ed il trasferimento dei dati, eseguendo dei programmi;
- la memoria centrale, detta "Random Access Memory", cioè la memoria principale che viene utilizzata per memorizzare i dati ed i programmi; è caratterizzata da dimensioni limitate, è volatile, quindi perde il suo contenuto quando si spegne il calcolatore, tuttavia garantisce un accesso rapido alle informazioni;
- le unità di ingresso/uscita, utilizzate per far comunicare il calcolatore con l’esterno (ad esempio la scheda video o le porte seriali);
- il bus di sistema, che collega tra loro tutti gli elementi funzionali;
- la memoria di massa, cioè una memoria secondaria che viene utilizzata per memorizzare grandi quantità di informazioni; è di tipo persistente ed è collegata ai dispositivi di ingresso-uscita, però l’accesso è meno rapido (perché, ad esempio, può essere costituita dal disco rigido);
- le periferiche che, essendo collegate ai dispositivi di ingresso uscita, forniscono delle funzionalità relative al trattamento delle informazioni (ad esempio il modem, la stampante, la scheda audio).

Il "cuore" di un elaboratore è strutturato secondo il modello della macchina di *von* *Neumann* ed è costituito da quattro degli elementi funzionali sopraelencati, ovvero: l'unità di elaborazione, la memoria centrale, le unità di I/O ed il bus di sistema. Quindi, le memorie di massa e le periferiche sono esterne a questa struttura e vi si interfacciano tramite le unità di ingresso/uscita.

La CPU, la memoria centrale ed i dispositivi di I/O sono realizzati con tecnologia digitale, perciò i dati e le operazioni effettuate vengono codificati tramite sequenze di impulsi elettrici, detti **bit** (binary digit).

Quindi, le operazioni che la CPU è in grado di eseguire sono di natura aritmetica, ma in rappresentazione binaria.  Queste possono essere di tipo logico, come AND,OR e NOT e di tipo matematico, cioè somma, differenza, moltiplicazione.

Utilizzando soltanto l'hardware dell'elaboratore, ossia la struttura fisica, l'utente si troverebbe a dover tradurre i comandi da impartire in sequenze di bit, cioè in linguaggio macchina.

##### Sistema operativo

Il sistema operativo rappresenta un insieme di programmi che opera direttamente al di sopra dell'hardware e che consente l’utilizzo di tutte le funzionalità dell’elaboratore.

Ad esempio, si occupa di gestire le risorse disponibili, di interpretare ed eseguire i comandi più elementari, di stampare, leggere e visualizzare a video. Inoltre, si interessa della gestione della memoria centrale e della memoria di massa.

Quindi, si può dire che un utente si interfaccia con la macchina tramite il sistema operativo che, in genere, è fornito dal costruttore stesso dell'elaboratore. 

In questo modo, il livello di astrazione del linguaggio macchina viene elevato passando ad un livello successivo, in cui l'interazione utente-elaboratore avviene in maniera meno difficoltosa, perché dall'utilizzo di intere sequenze di bit si passa all'impiego di comandi descritti tramite delle parole-chiave, all'esecuzione di programmi ed alla gestione dei dati in maniera più immediata per l'utilizzatore.

Questo perché le richieste dell'utente verranno poi convertite dal sistema operativo stesso in impulsi elettrici da sottoporre all'hardware, svolgendo, in un certo senso, un processo di traduzione delle stesse.

Esempi di sistemi operativi: Windows, MacOS, Linux.

#### Linguaggio ad alto livello

Si parla di programmazione ad alto livello quando si utilizzano linguaggi più sofisticati ed astratti, slegati dal funzionamento fisico della macchina, per avere una maggiore semplicità di scrittura e comprensione, da cui conseguono tempi di sviluppo più brevi.

Questo vantaggio, però, andrà ad incidere sulle performance della macchina e quindi sull'efficienza con cui verrà eseguito il codice in questione.

Tuttavia, ad oggi, la potenza dei calcolatori, valutata in termini di prestazioni, ha notevolmente compensato questo svantaggio, perciò i linguaggi ad alto livello risultano essere quelli maggiormente utilizzati.

Per *livello di astrazione* di un linguaggio si intende, quindi, quanto questo si "distacchi" da quelli che sono i dettagli del funzionamento di un calcolatore e della specificità del suo linguaggio macchina.

Questa idea della definizione di un linguaggio di programmazione che fosse automaticamente "traducibile" in linguaggio macchina, rimanendo, però, il più possibile affine alla logica umana, prese forma, negli Stati Uniti, a partire dal 1950, quando si diffuse il primo linguaggio ad alto livello , il Fortran. Questo linguaggio, detto "FORmula TRANslator", ovvero "traduttore di formule", è tuttora utilizzato, soprattutto per la scrittura di programmi che dovranno essere eseguiti dai supercomputer, come quelli usati, ad esempio, per l'elaborazione di dati per effettuare delle previsioni meteorologiche, poiché basati su dei modelli matematici che descrivono la fisica dell'atmosfera.

Siccome un linguaggio di programmazione ad alto livello non è direttamente eseguibile dal calcolatore, non trattandosi di linguaggio macchina, è necessario seguire dei modelli di esecuzione, quali compilazione ed interpretazione.

##### Compilazione

Ogni programma che non è stato scritto direttamente in codice binario passa attraverso il compilatore (un traduttore). 



##### Interpretazione

Nel caso in cui si stia considerando un programma scritto in un  linguaggio ad alto livello, questo, oltre che per il compilatore, dovrà passare anche attraverso l'interprete (traduttore istantaneo).







### Tipi di linguaggi

Sulla base di alcune caratteristiche che li accomunano, i linguaggi di programmazione possono essere distinti in vari tipi.

#### Linguaggi imperativi

Per *programmazione imperativa* si intende un paradigma di programmazione secondo cui un programma viene considerato come un insieme di istruzioni, dette anche direttive o comandi, ciascuna delle quali può essere considerata come un "ordine" che viene impartito alla macchina virtuale del linguaggio che si sta utilizzando.

Sintatticamente, i costrutti appartenenti ai linguaggi di questo tipo sono riconducili al modo indicativo di alcuni verbi, ad esempio READ, WRITE, LOAD.

```assembly
1: READ a
2: PRINT a
3: GOTO 1
```

I linguaggi sviluppati per questo tipo di programmazione sono più adatti alla manipolazione numerica che simbolica ed adottano uno stile di tipo prescrittivo, in cui tutte le operazioni da compiere sono già state previste all'interno del programma stesso. L'ordine di esecuzione è sequenziale, ad eccezione delle strutture di controllo (ad esempio salti e cicli), perciò le istruzioni verranno eseguite una dopo l'altra, a partire dalla prima in alto, fino all'ultima.



Un programma, che secondo il paradigma imperativo è una unione di istruzioni e dati, è strutturato in:

- una parte dichiarativa in cui si dichiarano tutte le variabili del programma e il loro tipo;
- una parte che descrive l'algoritmo risolutivo utilizzato, mediante istruzioni del linguaggio.











•Il modello computazionale è basato sui cambiamenti di stato della memoria della macchina

•È centrale il concetto di assegnazione di un valore ad una locazione di memoria (variabile)

•Il compito del programmatore è costruire una sequenza di assegnazioni (spesso reiterandole più volte) che producano lo stato finale (in modo tale che questo rappresenti la soluzione del problema)







##### Macchina virtuale

In [informatica](https://it.wikipedia.org/wiki/Informatica) il termine **macchina virtuale** (**VM**) indica un [software](https://it.wikipedia.org/wiki/Software) che, attraverso un processo di [virtualizzazione](https://it.wikipedia.org/wiki/Virtualizzazione), crea un ambiente virtuale che emula tipicamente il comportamento di una macchina fisica ([PC](https://it.wikipedia.org/wiki/PC), [client](https://it.wikipedia.org/wiki/Client) o [server](https://it.wikipedia.org/wiki/Server)) grazie all'assegnazione di risorse hardware (porzioni di [disco rigido](https://it.wikipedia.org/wiki/Disco_rigido), [RAM](https://it.wikipedia.org/wiki/RAM) e risorse di [processamento](https://it.wikipedia.org/wiki/Processore)) e in cui alcune [applicazioni](https://it.wikipedia.org/wiki/Applicazione_(informatica)) possono essere [eseguite](https://it.wikipedia.org/wiki/Esecuzione_(informatica)) come se interagissero con tale macchina; infatti se dovesse andare fuori uso il [sistema operativo](https://it.wikipedia.org/wiki/Sistema_operativo) che gira sulla macchina virtuale, il sistema di base non ne risentirebbe affatto. Tra i vantaggi vi è il fatto di poter offrire contemporaneamente ed efficientemente a più utenti diversi [ambienti operativi](https://it.wikipedia.org/wiki/Sistema_operativo) separati, ciascuno attivabile su effettiva richiesta, senza "sporcare" il sistema fisico reale con il [partizionamento](https://it.wikipedia.org/wiki/Partizione_(informatica)) del [disco rigido](https://it.wikipedia.org/wiki/Disco_rigido) oppure fornire ambienti [clusterizzati](https://it.wikipedia.org/wiki/Computer_cluster) su sistemi [server](https://it.wikipedia.org/wiki/Server).[[1\]](https://it.wikipedia.org/wiki/Macchina_virtuale#cite_note-vmwa_What-1)[[2\]](https://it.wikipedia.org/wiki/Macchina_virtuale#cite_note-redh_Cos'-2)[[3\]](https://it.wikipedia.org/wiki/Macchina_virtuale#cite_note-azur_Chec-3)

##### Tipi di istruzioni

Le istruzioni si dividono in:

- istruzioni di lettura e scrittura (scrittura a video, scrittura su disco, lettura da tastiera);
- istruzioni di assegnamento (astrazione di cella di memoria);
- istruzioni di controllo (if, while, for, foreach, try-catch).







##### Linguaggi procedurali

//TODO

##### Linguaggi orientati agli oggetti

•Il modello computazionale è basato sul concetto di classe (insieme) di oggetti con cui sono definite le strutture dati per la rappresentazione delle informazioni su cui opera il programma

•Le funzioni e le procedure sono metodi definiti per operare su specifici oggetti

•Si basano sui concetti di incapsulamento (un oggetto presenta una interfaccia con cui può essere usato e non rende visibile la propria implementazione), ereditarietà (le classi di oggetti possono essere definite estendendo le caratteristiche di altre classi di oggetti), polimorfismo (uno stesso metodo può avere comportamenti diversi su oggetti di classi differenti



#### Linguaggi dichiarativi

•Il modello computazionale è basato sui concetti di funzione e relazione

•Il programmatore non ragiona in termini di assegnazioni di valori, ma di relazioni fra entità e di valori di una funzione

##### Linguaggi funzionali

//TODO

##### Linguaggi Relazionali

//TODO

### Programmazione non strutturata

//TODO

### Programmazione procedurale

//TODO

