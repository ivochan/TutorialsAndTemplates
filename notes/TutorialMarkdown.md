## Markdown 

### Introduzione

_Markdown_ è un linguaggio di *markup* o di "marcatura", cioè è basato su un insieme di regole utilizzate per la formattazione e la definizione del layout di un testo.

Il suo nome è un gioco di parole che si riferisce proprio ai linguaggi di mark-up, di cui fa parte, sottolineando però come esso sia meno corposo rispetto agli altri, come se fosse una miniatura, da qui mark-down.

Questo linguaggio è stato sviluppato da Gruber e poi presentato, con la collaborazione di Swartz, nel 2004, con lo scopo di fornire uno strumento che utilizzasse un formato di testo semplice, per quanto riguarda sia la scrittura che la lettura e che, se necessario, fosse convertibile in HTML o XHTML.

Sulla base di questo proposito, infatti, diversamente dagli altri linguaggi dello stesso tipo, è estremamente leggibile, perché non altera significativamente la struttura del testo da formattare ed è basato su costrutti sintattici semplici, che lo rendono leggero e versatile.

Inoltre, è indipendente dalla piattaforma di esecuzione, quindi è possibile scrivere un file in Markdown su una qualunque applicazione che lo supporti, non trattandosi di un formato proprietario, per poi leggerlo come un semplice file di testo da un dispositivo su cui giri un sistema operativo qualsiasi.

Gli utilizzi di questo linguaggio, allora, sono molteplici e spaziano dalla creazione di siti Internet e documenti, alla scrittura di email, libri e presentazioni.

In particolare, è ampiamente utilizzato nella scrittura di documenti di tipo "README.md", che descrivono le caratteristiche dei progetti caricati nei repository open source oppure le informazioni per l'installazione di un software.

Inoltre, tramite alcuni generatori di siti statici, è possibile convertire un file .md in una pagina web statica.

#### Sintassi

Tramite degli attributi di formattazione, è possibile agire sia sull'aspetto del testo, che sulla struttura vera e propria del documento.

Inoltre, è possibile utilizzare degli elementi aggiuntivi, come liste e tabelle, oltre che inserire, all'interno, immagini e collegamenti.

Per ignorare uno qualsiasi dei caratteri di formattazione che verranno illustrati, basta utilizzare `\` prima del carattere in questione.

#### Formattazione del testo

Per quanto riguarda la formattazione del testo, si può procedere come segue:

- si può definire un _paragrafo_ delimitando il suo corpo tramite l'inserimento di una riga vuota;
- si può inserire un carattere di _fine linea_ o line break inserendo due caratteri di tipo spazio al termine della riga;
- si può scrivere una parola in _grassetto_ includendola tra più caratteri di tipo  `**`  (_doppio asterisco_);
- si può scrivere una parola in _corsivo_ includendola tra due caratteri `_`  (_underscore_);
- si può scrivere una parola sia in _grassetto_ che in _corsivo_, racchiudendola tra i caratteri `***` (_triplo asterisco_);
- si può _barrare_ una parola, racchiudendola tra i caratteri `~~` (doppia tilde); 
- si può indicare che si sta riportando del _codice_, cioè che si sta scrivendo del testo a spaziatura fissa, racchiudendolo tra i caratteri ` `` ` (_apice inverso_ o _backtick_);
- per scrivere un intero blocco di codice, lo si può racchiudere tra i caratteri ` ``` `, presenti, quindi, all'inizio ed alla fine del testo di interesse;
- si può riportare una citazione o _block quote_, cioè scrivere un corpo di testo rientrato utilizzando il carattere `>` prima di ogni riga;
- si può inserire una nota a piè pagina scrivendo la nota come segue `[^numero_nota ]` e poi definire il suo riferimento tramite un blocco, posto, automaticamente, a piè di pagina, con la sintassi `[^numero_nota ]: descrizione della nota`.

#### Struttura del documento

Per quando riguarda la struttura del documento e quindi la sua suddivisione in più _livelli_, si possono utilizzare i caratteri seguenti:

- si può sottolineare il testo con più caratteri di tipo `=` oppure scrivere prima del testo di interesse il carattere `#`, per indicare che si tratta del titolo del documento, ad esempio `# Titolo1 `;
- si può sottolineare il testo con più caratteri di tipo `-` oppure si possono inserire prima del testo di interesse i caratteri `##` per indicare che si tratta si un sottotitolo, ovvero `## Titolo2`;
- si possono definire livelli inferiori di titoli incrementando il numero di caratteri `#` fino a sei, ad esempio `#### Titolo4`;
- si possono creare delle linee di interruzione orizzontali, digitando tre o più caratteri dello stesso tipo, quali `___`, `***`, oppure `---` sulla stessa riga.

#### Elementi aggiuntivi

Nella stesura di un documento può sopraggiungere la necessità di disporre di alcune strutture che diano enfasi al contenuto del corpo del testo, come gli elenchi, oppure che permettano di organizzarlo in tabelle o di completarlo con dei collegamenti ipertestuali e delle immagini.
Segue una breve trattazione su come utilizzare le strutture sopracitate:

#### Elenchi

Per creare un _elenco_ è sufficiente far sì che ogni voce di quest'ultimo costituisca una riga a sé stante, introdotta da uno qualsiasi dei seguenti caratteri: `-` , `*` , oppure `+` .

Se si volesse convertire un semplice elenco in una lista con delle caselle di controllo o _check list_, allora si dovrà anteporre, ad ogni voce, una coppia di parentesi quadre `[ ]` ed inserire, eventualmente, anche delle spunte, utilizzando la lettera`X`, racchiusa dalle parentesi, nel modo seguente `[X]`.

Se si volesse creare un _elenco numerato_, invece, è sufficiente anteporre, ad ogni voce, un numero, seguito poi dal carattere punto, ad esempio `1.` . 

Si precisa che, se l'elenco non è costituito da numeri disposti secondo una sequenza crescente, questi verranno convertiti automaticamente in questo ordine.

#### Tabelle

Nella creazione di una tabella, si devono delimitare le celle che la costituiscono tramite una barra verticale   `|` , cioè il carattere _pipe_ e nel caso in cui si volesse specificare un'intestazione per un gruppo di esse, utilizzare una serie di trattini `-` per tutte le celle di interesse.

Ad esempio, scrivendo:

```
|Intestazione 0|Intestazione ... |Intestazione n|
| :---: | :--- | ---: | 
|Cella 0,0|Cella ... |Cella 0,n|
|Cella n,0|Cella ... |Cella n,n|
```

Verrà visualizzato: 

|Intestazione 0|Intestazione ... |Intestazione n|
| :---: | :--- | ---: | 
|Cella 0,0|Cella ... |Cella 0,n|
|Cella n,0|Cella ... |Cella n,n|

#### Collegamenti

I collegamenti di tipo _ipertestuale_, che costituiscono degli elementi in-linea, si costruiscono scrivendo tra parentesi quadre il testo che si vuole visualizzare, seguito poi dal sito web a cui reindirizzare l'utente al click, racchiuso tra parentesi tonde, secondo il seguente formato `[testo_da_visualizzare](sito_web)`.

Si può anche assegnare un titolo al link, che verrà visualizzato dall'utente quando il cursore del mouse punterà sul _collegamento_, in questo modo `[vai su google](www.google.com "Google")`, cioè inserendo dopo l'_url_ un carattere spazio ed inserendo il titolo del sito tra una coppia di doppi apici `""`.

Come percorso o _path_ dell'immagine si può specificare:

* un url assoluto (del tipo `https://sito_immagine/nome_immagine.estensione`);
* un percorso assoluto che punti ad un file che si trova sul locale, cioè sul dispositivo da cui si sta scrivendo (a esempiio `C:\Users\nome_utente\Immagini\nome_immagine.estensione`);
* un percorso relativo che punti, anche in questo caso, ad un file che si trova sul dispositivo in uso (ad esempio `.../Immagini/nome_immagine.estensione`).

#### Immagini

Per inserire delle immagini all'interno del documento, anche se comunque non potranno essere visualizzate se lo si apre con un editor di testo, si adotterà un meccanismo simile a quello utilizzato per i collegamenti ipertestuali, anche se queste verranno considerate come degli elementi a blocco, invece che in-linea.

Nello specifico, per inserire un'immagine, si dovrà scrivere un punto esclamativo `!`, seguito dalla frase da visualizzare per descriverla, racchiusa da parentesi quadre e seguita poi dal percorso in cui si trova l'immagine, scritto, invece, tra parentesi tonde ed eventualmente il titolo tra i doppi apici,

#### Sito ufficiale

Le linee guida di questo linguaggio di markup sono state fornite dal suo creatore sul sito https://daringfireball.net/projects/markdown/, assieme a tutte le informazioni relative a questo progetto open source.

#### Tools

Per quanto riguarda gli editor online, è possibile utilizzare **Dilliger**, accessibile al sito https://dillinger.io/ .

Se invece si volesse installare un editor sul proprio pc, allora, si può usufruire del software multi-piattaforma **Typora**, scaricabile da https://typora.io/ (ad oggi a pagamento su Windows).

Per convertire un documento scritto in Markdown in sito web statico, invece, si può impiegare **Jekyll**, un progetto open source descritto su https://jekyllrb.com/.

Altri progetti free per Markdown: 

- obsidian 
- marktext (attenti perché tende a rovinare determinate formattazioni del documento originale)
- ghostwriter

#### Estensioni

Se si utilizza **Visual Studio Code**, si può provare l'estensione **Markdown All in One**, che mette a disposizione anche shortcuts da tastiera ed una funzionalità che consente la visualizzazione dell'anteprima del documento.

Se invece si vuole utilizzare questo linguaggio di markup per la scrittura di email, si può attivare l'estensione browser **MarkdownHere**, il cui sito è https://markdown-here.com/, disponibile per **Chrome**, **Firefox**, **Safari** e **Opera**, oltre che per le applicazioni di posta elettronica **Thunderbird** e **Postbox**.

