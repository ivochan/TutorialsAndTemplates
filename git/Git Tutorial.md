## Git

### Introduzione

*Git* è uno strumento che è stato ideato per il controllo di versione, ovvero la gestione di più versioni di informazioni, che siano di tipo software o documentali, però di tipo distribuito, permettendo così di tenere traccia di tutte le modifiche attuate, senza, però, dover utilizzare un server centrale.

Pur essendo stato creato da *Linus Torvalds*, nel 2005, come ausilio per lo sviluppo del kernel Linux, è diventato, negli anni, uno dei software per il controllo di versione più diffusi, rimanendo, comunque, sotto una licenza di software libero, la GNU GPL v2.

Questo è stato ideato per funzionare da riga di comando e su sistemi operativi basati su GNU/Linux. Tuttavia, la sua portabilità è stata estesa anche in sistemi unix-like, come BSD e Solaris. Inoltre, è eseguibile anche in Windows, utilizzando l'ambiente Cygwin (un'emulazione POSIX).



### Installazione

Segue una trattazione di come installarlo sulle differenti distribuzioni Linux.

#### Debian/ Ubuntu e derivate

L’installazione, in quest ambienti, verrà eseguita tramite il gestore di pacchetti *apt*, digitando il comando seguente:

```bash
apt install git
```

#### Archlinux/ Manjaro e derivate

Su Archlinux e derivate, invece, si utilizzerà il gestore pacchetti *pacman*, dando il comando:

```bash
pacman -S git
```

#### Windows

//TODO

#### Documentazione

Per usufruire della documentazione, tramite la consultazione delle pagine *man*, si può clonare il relativo repository scrivendo:

 ```bash
 git clone git://github.com/gitster/git-manpages.git
 ```

E dando poi il comando:

```bash
make quick-install-man
```

### Funzionamento

Per quanto riguarda la memorizzazione dei dati, Git prevede tre stadi differenti, che sono, nello specifico, i seguenti:

- il primo, detto **working area**, che consiste nello stato in cui si trovano i file sui cui si sta, attualmente, lavorando;  
- il secondo, ovvero la **stagin area**, in cui verranno spostati i file al termine del processo di modifica, con l'aggiunta degli *object*s, che conterranno le relative informazioni, riguardo i cambiamenti che vi sono stati apportati;
- il terzo stadio, rappresentato dal **repository**, dove saranno creati i file *incremento*, che descrivono, invece, come si è evoluta la propria working area;

In conclusione, questi dati verranno poi memorizzati nel repository creato ad hoc.

Si precisa che queste tre aree sopradescritte possono trovare un proprio corrispettivo anche in locale, ossia sul file system del sistema in uso. 

Nello specifico:

- la **working area**, rappresenterà, anche in questo caso, i file su cui si sta lavorando, ovvero l'intera *cartella di progetto*;
- la **staging area**, che costituirà, in realtà, una distinzione fittizia, in quanto non si tratta di una fase di memorizzazione vera e propria, ma soltanto di un processo di creazione di una serie di file che indicheranno quali informazioni siano effettivamente cambiate, rispetto all'ultimo *commit*;
- il **repository**, situato in una cartella nascolta, all'interno del progetto `.git`.

Il passaggio, dei file di interesse, dalla working area alla stagin area, è indicato come un'operazione di *add*, di aggiunta di quest'ultima versione.

Il movimento che, invece, interessa il passaggio dall'area di staging al repository costituisce un'operazione di *commit*.

Per quanto riguarda lo scambio effettivo di informazioni tra un repository remoto ed il suo corrispettivo locale, si definisce operazione di *pull*, il trasferimento di dati dal primo al secondo ed operazione di *push* il processo inverso, cioè il trasferimento di una versione dei dati, modificata sul locale, come ultima modifica da memorizzare anche in remoto.

### Configurazione ed utilizzo

Segue una descrizione delle principali funzionalità di Git, comprensive di esempi applicativi.

#### Creazione di un repository

Si suppone di dover creare un repository  *.git* nella cartella di progetto.

A titolo esemplificativo, verrà fatta una prova utilizzando le seguenti cartelle:

- *project_directory*, cioè la cartella che conterrà il progetto di sviluppo e quindi i codici su cui si sta lavorando;
- *main_remote_repository*, ossia una directory che conterrà, soltanto, il repository, di tipo locale o remoto, sui cui non verranno apportate, esplicitamente, delle modifiche;
- *second_remote_repository*, che conterrà i file di progetto ed il relativo repository, andando a costituire una sorta di copia (o clone) della cartella di progetto (denominata, in precedenza, project_directory);

A questo punto, dopo aver aperto il terminale in *project_directory*, si dia il comando:

```bash
git init
```

In questo modo  verrà creato, il relativo repository, che sarà vuoto, in quanto soltanto inizializzato (lo stesso procedimento dovrà essere ripetuto per la cartella denominata *second_remote_repository*). 

Se all'interno di questa cartella sono già presenti dei file, questi possono essere memorizzati sul repository scrivendo:

```bash
git add .
```

In questo modo è stata effettuata, quindi, un'operazione di aggiunta (il carattere '.' sta ad indicare la totalità dei file contenuti nella cartella), che verrà, poi, seguita da un'operazione di commit, tramite il comando:

```bash
git commit -m "messagge" .
```

Si ha anche la possibilità di creare un *repository minimale*, da utilizzare per clonare dei dati, da condividere, eventualmente, con altre postazioni, eseguendo, nella cartella designata a questa funzionalità, ad esempio *main_remote_repository*, il comando:

```bash
git init --bare
```

La differenza di output risultante dai due differenti comandi di *init*, eseguiti, rispettivamente, sulla cartella di progetto e su quella identificativa del repository remoto, si può apprezzare esaminando il contenuto delle due directory.

Nello specifico, nella prima, *project_directory*, si potranno visionare i file su cui si stava, eventualmente, lavorando ed una cartella nascosta, denominata *.git*, che avrà lo stesso contenuto della cartella *main_remote_repository*, ovvero dei file che definiscono i vari brach, gli stati del progetto, lo storico dei dati che sono stati creati e i file di log delle modifiche apportate, così come è in questo contesto che verrà quali siano i file che si trovano in stato di *add* e quali altri siano passati, invece, allo stato di *commit*. 

Si precisa che, talvolta, alcune di queste informazioni sono memorizzate all'interno di file in formato binario, che non possono essere, quindi, modificati direttamente e di difficile consultazione.

 #### Aggiunta di un repository remoto

Per testare l'aggiunta di un repository remoto, prendendo in considerazione l'esempio sopradescritto, si dovrà tenere presente che le cartelle *project_directory* e *second_remote_repository* punteranno, entrambe, al repository remoto indicato come *main_remote_repository*. Si precisa, inoltre, che *project_directory* avrà un secondo repository remoto, costituito proprio da *second_remote_repository/.git*.

Il comando da digitare, dopo essersi posizionati nella cartella che si vuole punti al repository remoto, è il seguente:

```bash
git remote add [repository_name] [repository_path]
```

Ad esempio, dopo aver lanciato il terminale in *project_directory*, si dovrà digitare:

```bash
# project_directory deve puntare a main_remote_repository
git remote add main_repository ~/main_remote_repository 

# project_directory deve puntare a second_remote_repository/.git
git remote add second_repository ~/second_remote_repository/.git
```

Essendo *main_remote_repository* un repository di tipo minimale, per aggiungerlo, come repository remoto, sarà suffciente indicare la cartella stessa.

Per quanto riguarda *second_remote_repository*, invece, bisognerà includere, nel path, anche la cartella *.git*.

Tuttavia, in genere, ci si troverà ad utilizzare un repository che, il più delle volte, sarà identificato tramite un URL.

Infine, avviando il terminale dalla cartella *second_remote_repository*, si potrà scrivere, in modo che anch'essa punti allo stesso repository remoto di *project_directory*, il comando seguente:

```bash
# second_remote_repository deve puntare a main_remote_repository
git remote add orgin ~/main_remote_repository
```

#### Comunicazione con un repository remoto

Le operazioni principali sono:

- l'azione di *push*, per scaricare lo stato dei dati attuale, sul locale, tramite il comando:

  ```bash
  git pull [repository_name] [branch_name]
  ```

- l'istruzione di *pull*, per caricare lo stato delle modifiche attuale, dal locale, sul repository remoto, scrivendo:

  ```bash
  git push [repository_name] [branch_name]
  ```

Si specifica che è possibile omettere il nome del branch, così come quello del repository, se ne esiste uno soltanto.

Invece, nel caso di più repository, è conveniente utilizzare l'opzione *upstream*, come segue:

```bash
git push --set-upstream [repository_name] [branch_name]
```

In modo che il repository ed il branch vengano selezionati in maniera predefinita, nel caso in cui non siano stati specificati.

È consigliato effettuare sempre un'operazione di *pull*, prima di apportare delle modifiche in locale, ossia prima di eseguire un'istruzione di *push*.

#### File da escludere dalla memorizzazione

Talvolta, può rivelarsi utile evitare che una determinata categoria di dati non venga registrata nella storia di un progetto, come spesso accade, nel caso di sviluppo di un software, di voler escludere, ad esempio, i file binari risultati dalla compilazione del codice in questione.

A questo proposito, Git consente di definire un file, denominato *.gitignore*, che conterrà proprio un listato, scrivendo ciascuna voce su una riga differente, delle estensioni dei file o dei nomi delle cartelle,  che dovranno essere, per l'appunto, ignorati. A supporto di ciò, potranno essere utilizzati dei caratteri speciali, ossia:

- `*`, per indicare una qualsiasi combinazione di caratteri (ad esempio **.class* si riferisce a tutti quei file che abbiano estensione *.class*, a prescindere da come siano stati denominati);
- `?` , per riferirsi ad un generico, ma singolo, carattere che potrà variare (ad esempio, nel caso di *.project?*, si intende che, al posto del carattere speciale, potrà essere presente qualsiasi carattere);

La struttura di generico file `.gitignore`, situato nella directory di progetto, è la seguente:

```bash
bin/
*.class
.classpath
.settings
.project?
src/*/samples/
```

Segue una descrizione delle voci presenti, quali:

- `bin/` , per escludere la cartella *bin* e tutte le sue sottocartelle, poichè spesso contiene i file compilati;
- `*.class` , per impedire la memorizzazione di tutti i file con estensione *.class*, come, ad esempio, i file compilati di *Java*;
- `.classpath` , per escludere il file denominato *.classpath*, utilizzato da vari Desktop Environment per indicare, ad esempio, il classpath di Java;
- `.project?` , per evitare il caricamento di tutti quei file il cui nome inizi con *.project*, seguito poi da qualsiasi altro carattere, come accade nel caso di *.projects*, oppure per le cartelle denominate *.project*, che corrisponde alla scrittura *.project/*;
- `src/*/samples/` , per escludere una cartella specifica, in questo caso *samples*, presente in *src*;

### Comandi principali di gestione

Segue una descrizione dei principali comandi che saranno utili per la gestione e l'organizzazione di un determinato repository, in modo da avere un riferimento su quali siano le operazioni da seguire per effettuare le azioni principali, ossia di rimozione, modifica e sincronizzazione di un repository remoto, oltre che l'aggiunta di file specifici ai differenti alberi di lavoro.

#### Configurazione dell'utente

Per quanto riguarda le configurazioni dell'utente che usufruisce delle funzionalità di Git, sarà sufficiente definire quali siano, rispettivamente, il nome ed il relativo indirizzo di posta elettronica.

Quindi, per impostare il nome utente basterà digitare:

```bash
git config --global user.name "user_name"
```

Invece, per specificare l'indirizzo email, si dovrà scrivere:

```bash
git config --global user.email "mail_address"
```

Dove *user_name* e *mail_address* sono i campi da sostituire con i valori di interesse.

Si precisa che le configurazioni attuate con l'opzione `--global` valgono per qualsiasi progetto, in quanto saranno memorizzate nelle cartelle di configurazione di sistema (quali `/etc/gitconfig`, oppure `~/.gitconfig` nel caso di sistemi Linux). 

Dunque, se si volessero definire, per un determinato progetto soltanto, delle configurazioni differenti, allora si dovrà aprire un terminale nella cartella di interesse e digitare il comando opportuno, a meno dell'opzione sopradescritta, come mostrato di seguito:

```bash
git config user.name "own_project_nickname"
```

In questo modo si può specificare una firma, intesa come nome ed email, che sia differente, per un determinato progetto, da quella definita in precedenza, tramite l'opzione *global*.

Un'altra configurazione che si può personalizzare riguarda l'editor di testo che verrà utilizzato per la scrittura dei messaggi di commit. In genere, come scelta predefinita, viene richiamato quello di sistema, ma se si volesse impostarne uno differente, allora, basterà scrivere:

```bash
git config --global core.editor [editor_execution_command]
```

Lo stesso procedimento può essere seguito per specificare quale programma di "fusione", ossia di *merge*, utilizzare, nel caso in cui si presentino dei conflitti, tra le varie mofiche che sono state apportate ai dati su cui si sta lavorando, in modo da attuarle ed unirle in maniera controllata, senza compromettere, dunque, l'integrità di questi. Il comando da eseguire è questo:

```bash
git config --global merge.tool [merge_tool_execution_command]
```

Uno strumento che di potrebbe utilizzare è, ad esempio, *Meld*.

#### Attuazione o annullamento delle modifiche

Per rendere effettive delle modifiche che sono state fatte al progetto su cui si sta lavorando è necessario che queste siano aggiunte alla staging area, scrivendo:

```bash
# aggiungere alla staging area un file specifico
git add [file_path]
```

dove per path si intende il nome di un file o di un'intera cartella. Nel caso in cui si vogliano caricare tutte le modfiche effettuate, senza selezionare dei file specifici, sarà sufficiente, aprendo il terminale della directory di progetto, dare il seguente comando:

```bash 
# aggiungere alla staging area tutti i file modificati
git add .
```

Per invertire questo processo, con un conseguente annullamento delle modifiche, si dovrà invertire il processo di *add*, ritnornando, così, dalla staging area alla working area, tramite un'operazione di *remove* sulla cache, digitando, nel caso di un solo file, l'istruzione:

```bash
git rm --cached [file_path]
```

Se, invece, si vuole che questa azione sia applicata a tutti i file oppure ad un'intera cartella, di cui le relative modifiche sono state già approvate, si dovrà indicare l'opzione `-r` per specificare che si tratta di un'operazione di tipo ricorsivo, scrivendo, quindi:

```bash
git rm --cached -r  [directory_path]
```

Se, al contrario, il caso di specie dovesse riguardare l'annullamento di un'erronea azione di eliminazione di alcuni file, allora si dovranno eseguire questi comandi:

```bash
# annullamento dell'operazione di add
git reset

# recupero dei file erroneamente eliminati
git checkout --
```

Per eliminare delle modifiche apportate a dei file specifici, sfruttando sempre l'istruzione *checkout*, basterà scrivere:

```bash
git checkout -- [file_name]
```

Un comando più drastico è il seguente:

```bash
git reset --hard
```

Infatti, l'esecuzione di questa istruzione, nella directory di progetto, consentirà di scartare tutte le modifiche effettuate, in locale. Questo perchè si andrà a modificare il contenuto sia della staging area, che della working area, facendo in modo che i dati vengano ripristinati allo stato delle modfiche dell'ultimo commit.

#### Dalla staging area alla registrazione delle modifiche

Per registrare tutti i cambiamenti che sono stati apportati della directory di progetto in questione si dovrà utilizzare l'istruzione di *commit*.

Questa dovrà essere completata inserendo un messaggio, il cui contenuto fornirà una breve descrizione dei cambiamenti che sono stati effettuati, semplificando, anche, la realizzazione di un tracciato evolutivo della storia del progetto che si sta sviluppando, che potrà essere consultato in qualsiasi momento.

```bash
git commit -m "commit_message" [file_name]
```

dove al posto della voce "file_name" si potrà, anche, scrivere un elenco di file o cartelle, oppure il carattere ".", per specificare di validare le modifiche effettuate in qualsiasi cartella, con le rispettive sottocartelle, del progetto in questione.

##### Attuazione della totalità delle modifiche e scrittura dei messaggi di commit

Se a seguito del comando di commit non viene espressa alcuna speficifica di percorso, allora verranno presi in considerazione tutti gli aggiornamenti risultati, anche se, il comando previsto per questa funzione è il seguente:

```bash
# commit di tutte le modifiche effettuate
git commit -a
```

Si precisa che, a seguito dell'esecuzione di questa istruzione, verrà aperto l'editor di testo predefinito per scrivere il corrispettivo messaggio di commit.

L'ultimo messaggio inserito potrà essere modificato digitando:

```bash
git commit --amend
```

Si consiglia di effettuare sempre dei commit che corrispondano a delle modifiche che siano sì significative, ma poco corpose e complesse, in modo da avere sempre la possibilità, soprattutto in caso di malfunzionamenti, di individuare e correggere la sezione che causa la criticità.

> Nota: 
>
> per generare un messaggio di commit in maniera casuale si può utilizzare il sito [whatthecommit.com](http://whatthecommit.com) digitando:
>
> ```bash
> git commit -m "$(curl -s http://whatthecommit.com/index.txt)"
> ```
>
> 

##### Log dei commit

Dopo aver eseguito un'azione di commit, questa verrà registrata nei file di *log*, una sequenza temporale di tutte le operazione effettuate sulla directory di progetto remota. Infatti, proprio tramite la consultazione di questi file, sarà possibile avere contezza della storia di tutte le modifiche e dei messaggi effettuati, accompagnati dalle date in cui si sono verificate e da codici identificativi.

Per accedere a queste informazioni sarà sufficiente digitare:

```bash
git log
```

Se si avesse la necessità di consultare soltanto il messaggio di commit, oppure il codice ad essa associato, usufruendo dell'opzione *--oneline*, si potrà avere un riepilogo di quest'utilimi, scrivendo:

```bash
git log --oneline
```

Se, al contrario, si volesse visionare un file di log, che sia il più accurato e dettagliato possibile, si potrà utilizzare il comando:

```bash
git whatchanged
```

includendo, in questo modo, anche i nomi dei dati che sono stati interessati dai cambiamenti.

#### Dall'azione di commit alla working directory per invertirne gli effetti

Nel caso in cui sia stata effettuata un'operazione di commit indesiderata e di cui, dunque, se ne vogliono annullare gli effetti, è possibile invertire il processo tramite l'azione di *revert*. Tramite questo comando, infatti, sarà possibile portare lo stato della directory di progetto ad momento precedente a quello dell'ultimo commit effettuato, causando, quindi, una regressione  di quest'ultimo, tramite quella che non sarà altro che un nuovo commit. Questo vuol dire che sarà possibile, sempre tramite un'azione di revert, annullare anche gli effetti di questa particolare operazione.

Per prima cosa sarà necessario controllare quale sia il codice del commit che risulta essere successivo a quello che si riferisce allo stato delle modifiche a cui si vuole ritornare e quindi mantenere. A questo proposito basterà consultare il log tramite il comando:

```bash
git log --oneline
```

Dopo di che si potrà eseguire l'operazione di *revert* scrivendo:

```bash
git revert [commit_code]
```

dove al posto di "commit_code" bisognerà scrivere il codice del commit che si vuole annullare.

Per evitare di annullare le modifiche di un commit che si vuole, invece, mantenere, si potrà scrivere:

```bash
git revert -n [commit_code]
```

Per eliminare totalmente la storia delle modifiche fino ad un determinato commit si potrà, invece, utilizzare l'istruzione di *reset*, nel modo seguente:

```bash
git reset [commit_code]
```

Nel caso in cui il commit da annullare sia il primo effettuato in tutta la storia del progetto, allora, bisognerà cancellarla, digitando:

```bash
git update-ref -d HEAD
```

Se si tratta di un commit successivo al primo, allora, si potrà scrivere:

```bash
git reset --soft HEAD
```

#### Controllo dello stato delle modifiche

Per controllare se i dati di interesse siano stati interessati o meno da dei cambiamenti si potrà utilizzare l'istruzione di *check*, digitando:

```bash
git status
```

Nel caso in cui si volessero avere delle informazioni più dettagliate, anche per quanto riguarda i repository coinvolti, si potrà eseguire, prima effettuare un controllo sullo stato, un'azione di *fetch*, scrivendo:

```bash
git fetch [repository_name]
```



















# TODO Comandi



- ci si posiziona nella cartella di progetto
    cd WumpusGame/
- si inizializza il repository
    //git init --initial-branch=main con rename del branch
	git init
    

-si rinomina il repository 
	git branch -m master main

- si assegna un nome ad un repository

    //se creo il repository dal locale per mandarlo su github
    git remote add github https://github.com/ivochan/WumpusGame
    (in questo caso il nome e' "github")
    
    //se clono un repository gia' esistente
    git remote rename origin github

- per riconciliare il branch
    git branch --set-upstream-to=github/main main
    Branch 'main' impostato per tracciare il branch remoto 'main' da 'github'.
- per scaricare i file
    git pull github main
- per caricare i file
    git push github main





> Grazie a PsykeDady per il suo articolo su linuxhub.it