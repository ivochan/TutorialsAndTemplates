# HTML
## Introduzione

HTML, ossia "HyperText Markup LAnguage", è un linguaggio di markup, utilizzato per la formattazione e per l'impaginazione di documenti ipertestuali.

Per definire il modo in cui gli elementi di una pagina dovranno essere disposti al suo interno si utilizzano dei marcatori.
E' possibile, inoltre, stabilire i collegamenti, detti *link*,  che sussitono tra più pagine.

In genere, una pagina di tipo HTML consiste in un documento di testo, con estensione .html.

Se HTML, dunque, è un linguaggio che consente di definire la struttura di una pagina Web, per specificarne l'aspetto, in termini di colori, animazioni e qualsiasi altra caratteristica visuale, si può utilizzare CSS, andando a definire i cosiddetti "fogli di stile".

Qualora, inoltre, dovesse servire interverire su qualsiasi aspetto di una pagina Web, anche per gestire, eventualmente, l'interazione con l'utente, è richiesto l'uso di un linguaggio di programmazione, come Javascript.

## Elementi

In una pagina HTML, dunque, tutti gli elementi che la compongono sono connotati tramite dei *tag*, ossia delle etichette, scritte in minuscolo e racchiuse tra parantesi angolate, che ne andranno a specificare il tipo, o più precisamente il ruolo semantico che ciascuno di questi assume.

### Attributi 

Ogni tag può essere corredato da vari attributi, in modo da specificare, eventualmente, la funzione o la tipologia dell'elemento in questione, ma anche per la memorizzazione dei dati.

Questi *attributi* possono essere considerati come delle coppie chiave-valore, racchiuse tra virgolette oppure dagli apici, avendo cura di inserire almeno un carattere di tipo spazio dopo il nome dell'elemento del tag di apertura, oppure, se si tratta di elementi non contenitori, nell'unico tag specificato.

Gli attributi possono essere distinti in:
- attributi di base o *core*, utilizzati per la rappresentazione grafica degli elementi;
- attributi per la gestione degli eventi;

#### Attribuiti Core

Ecco un elenco dei principali attribuiti di questo tipo:

- *title*, per descrivere il contenuto dell'elmento, da mostrare al passaggio del mouse;
- *lang*, per indicare la lingua del contenuto (ad esempio `<p lang="it>ciao</p>`;
- *id*, per associare ad un elemento un identificatore univoco, diverso da quello di ogni altro elemento contenuto nella stessa pagina;
- *class*, per specificare l'appartenenza di un elemento ad una serie di "classi", separandole con degli spazi (ad esempio `<p class="saluto" "testo-chiaro">ciao</p>`);
- *style*, per assegnare le proprietà grafiche all'elemento, definite tramite stili CSS;
- *draggable*, per stabilire, tramite un valore booleano, se l'elemento a cui si riferisce è di tipo trascinabile per consentire, eventualmente, un'operazione di drag and drop; 


#### Attributi per gli eventi

Questo tipo di attributi è necessario per l'associazione di determinati comportamenti dell'interfaccia utente 


Per quanto riguarda la definizione della struttura di una pagina si possono usare i tag seguenti:

- ` <body></body> `, per descrivere il contenuto di tutta la pagina;
- `<p></p>`, che denota un paragrafo;
- `<hn></hn>`, per indicare la rilevanza di un titolo o *heading*, nel documento (dove n rappresenta un numero da 1, se l'elemento rappresenta il tema principale della pagina, fino a 6);
- `<br></br>`, che rappresenta l'istruzione di *break line*, per andare a capo nel mezzo di un testo;

Una struttura di questo tipo, in cui i tag indicano dei contenitori, annidati l'uno dentro l'altro, può essere definita di tipo ad albero.
In base alla disposizione che ogni elemento dovrà avere nella pagina, si possono distinguere le seguenti tipologie:
- *block*, ossia elementi che costituiscono un blocco, come i paragrafi o le sezioni e che quindi necessitano dell'anadare a capo;
- *inline*, ovvero gli elementi "in linea", che possono essere integrati nel testo, come i link;
- *list*, delle liste numerate oppure non numerate, dedite alla definizione di elenchi o menu.
