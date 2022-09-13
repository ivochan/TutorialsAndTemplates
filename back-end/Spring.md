# Spring Framework

## Introduzione

**Spring** è un framework open source, dedito allo sviluppo di applicazioni aziendali (Enterprise Application), su piattaforma Java.
La prima versione di questo framework, distribuito sotto licenza Apache, fu presentata da Rod Johnson tramite la pubblicazione del libro "Expert One-on-One Java EE Design and Development", nel 2002.

```
"un framework open source nato con l’intento di gestire la complessità nello sviluppo di applicazioni enterprise"
```

Rispetto ad altri, Spring risulta essere un framework più leggero. Questo perchè, grazie alla sua architettura modulare, si ha la possibilità di utilizzarne soltanto le parti di interesse, facilitandone, di conseguenza, l'integrazione con altri framework.

Inoltre, è stato riconosciuto, all'interno della comunità Java, come un'adeguata alternativa a Jakarta EE (la versione successiva di Java EE e Java 2 Enterprise Edition), basata sugli Enterprise Java Beans (EJB). 
E' per questo che viene definito un *lightweight container*, reso ancora più semplice dall'utilizzo di strumenti come l'Inversion of Control e l'Aspect Oriented Programming.

Quindi, in generale, il vantaggio dell'utilizzo di un framework come Spring, consiste nella semplificazione della gestione di alcune attività, ricorrenti e talvolta problematiche, nello sviluppo software, come l'accesso al database, il testing e la specifica delle dipendenze.

## Architettura 

La struttura di Spring consente, grazie alla sua modularità, di integrare nel codice che si sta sviluppando, solamente le parti di cui si ha necessità, escludendo quelle superflue.

Questa architettura è costituita da cinque livelli, quali:

-**Core Container**, ovvero la parte fondamentale di Spring, il cuore su cui è basato l'intero framework.
è costituito da quattro moduli, tra cui *Core* e *Beans*, che forniscono le funzionalità di Ioc e DI, occupandosi, di conseguenza, della creazione, della gestione e della manipolazione di qualsiasi tipo di oggetti, detti beans. Sulla base dei servizi offerti da questi due moduli è stato realizzato il modulo *Context*, che si occupa di esternderli, tramite l'aggiunta del supporto per l'internazionalizzazione(l18N, "I- diciotto lettere -N", ovvero la localizzazione, cioè di adattamento dei servizi a lingue e/o culture differenti), la propagazione degli eventi, il caricamento delle risorse e la creazione dei contesti, oltre che per alcuni strumenti di Java EE, come EJB, JMX ed il supporto per la connessione remota. L'ultimo modulo presente nel Core Container è *Expression Language*, che rappresenta un linguaggio di interrogazione e modifica degli oggetti a runtime, in quanto consente il recupero e l'assegnamento dei valori delle proprietà degli oggetti, oltre che la selezione e l'aggregazione di liste;

-**Data Access/Integration**, cioè il livello di astrazione dedito all'accesso ai dati, per semplificare ed uniformare i meccanismi legati alla gestione delle connessioni, delle transazioni e delle eccezioni. I moduli che lo compongono sono: JDBC, che permette di interpretare codici di errore specifici per i diversi tipi di database; ORM, che si occupa dell'integrazione con i principali framework di Object-Relational Mapping (cioè il paradigma della programmazione orientata agli oggetti nel caso di RDBMS, cioè sistemi per la gestione basi di dati relazionali; OXM, per utilizzare diverse implementazioni di Object/XML mapper, ovvero del mapping della gerarchia di oggetti in dati in formato XML; JMS, che garantisce l'utilizzo del servizio di messagistica Java; e Ttransaxtion, che consente di gestire le transazioniper qualsiasi tipo di oggetto (POJO, ossia "Plain Old Java Object", un comune oggetto Java, di tipo ordinario, che non implementa alcuna interfaccia, non estenda alcuna classe specifica e non contenga alcuna annotazione);

-**Spring AOP**, è il modulo che realizza l'integrazione delle funzionalità proprie della programmazione Aspect Oriented, occupandosi della gestione delle transazioni per gli oggetti di una qualsiasi applicazione Spring, in modo da evitare l'utilizzo degli EJB;

-**Web**, ossia il livello dedito alla definizione ed all'integrazione di tutte quelle funzionalità basilari richieste per lo sviluppo web-oriented. Inoltre, tramite un'implementazione del pattern Model View Controller, cioè lo Spring MVC Framework, consente di realizzare applicazioni Web in maniera completa ed altamente configurabile, potendo usufruire anche del supporto a varie tecnologie di visualizzazione;

-**Testing**, è il livello che garantisce il supporto alle attività di testing, uno dei tratti distintivi propri di Spring, anche tramite l'integrazione con JUnit e TestNG, oltre che alla presenza di Mock Objects, per testare del codice in isolamento.

## Dependency Injection

Per *Inversion of Control* si intende una carettistica tale per cui il controllo del flusso del software viene realizzato, anzichè dall'applicativo, dal framework stesso. Questo principio architetturale si basa, quindi, sul concetto che riguarda l'inversione del controllo del flusso di sistema, rispetto alla programmazione tradizionale (in cui la logica del flusso viene definita dallo sviluppatore). La volontà è quindi quella di disaccoppiare le dipendenze tra oggetti, in modo da rendere indipendenti, appunto, tra loro, le differenti parti di un codice, agevolandone, di conseguenza, la modifica.
Questa IoC può essere ottenuta, in maniera efficace, tramite *Dependency Injection*, che rappresenta, proprio, una sua implementazione. Tramite la DI, ad essere invertito sarà il processo di risoluzione delle dipendenze, facendo in modo che queste possano essere inizializzate dall'esterno, non essendo più vincolate alle classi ed alla dipendenza che si instaurerebbe tra queste.

Allora, adottando la tecnica della Dependency Injection, si avrà un componente esterno, indicato come assembler, che si occuperà di tutto il processo di creazione degli oggetti, comprensivo della definizione delle loro dipendenze, proprio tramite il meccanismo dell'injection.

Si possono definire tre forme di Injection, quali:

-*Constructor Injection*, che consiste nel caso in cui la dipendenza da esplicitare viene assegnata come parametro del costrutore dell'oggetto di interesse;

-*Setter Injection*, quando la dipendenza viene dichiarata tramite l'utilizzp di un metodo modificatore di tipo set();

-*Interface Injection*, se l'iniezione della dipendenza  è basata sulla mappatura che sussiste tra l'interfaccia e la rispettiva implementazione (questo approccio non è utilizzato in Spring);

### Container

Per effettuare un'operazione di injection si può utilizzare, come assemblatore, un IoC Container.
Questo componente, sulla base di alcune configurazioni, si occuperà, dunque, di dichiarare le dipendenze di un dato oggettoo componente, in Spring identificato come "Bean", evitando che queste siano esplicitate dallo sviluppatore.
Per usufruire di questo strumento si utilizza l'interfaccia *BeanFactory*, dedita alla creazione di tutti i bean di cui necessita l'applicazione. Questa si occuperà, poi, di inizializzarne le dipendenze, tramite il meccanismo dell'injection e di gestirne il ciclo di vita.
Le configurazioni da specificare, lato utente, affinchè il container possa svolgere la sua attività in maniera adeguata,riguardano la specifica dei bean che si dovranno gestire e le dipendenze che vi sussistono.


## Aspect Object Programming

L'*Aspect Oriented Programming* rappresenta una tecnica che sfrutta la modularità della programmazione orientata agli oggetti, introducendo un nuovo livello di modularizzazione, arrivando a gestire persino le funzionalità di un'applicazione (oltre che gli oggetti, tramite l'organizzazione del codice in classi) in maniera separata tra loro, perchè trattate da moduli differenti, favorendo anche il riuso del codice da più classi.


## Sviluppo veloce

Per iniziare a sviluppare utilizzando questo framework, si può scaricare il progetto di demo dal sito https://start.spring.io, sfruttando, in questo modo, l'ausilio di **Spring Boot**.
Questo ha come scopo quello di ridurre la complessità della configurazione di un nuovo progetto Spring, ad esempio incorporando direttamente applicazioni web server/container, deifinendo le specifiche di Maven tramite i POM (Project Object Models), ma anche configurando in maniera automatica Spring.
Prima di generare il progetto su cui si andrà a lavorare  è possibile, dunque, specificare che si tratterà di un progetto *Maven*, scritto in linguaggio *Java*, scegliere la versione di *SpringBoot* che si vuole utilizzare e specificare i *Metadata* relativi al progetto. Inoltre, sulla destra, si potranno inserire direttamente le dipendenze, come lo *Spring Boot DevTools*, *Lombok* e *Spring Web*.

Il progetto da utilizzare come base si troverà nella cartella "initial".

Nel file "pom.xml" verranno raccolte tutte le informazioni sul progetto come, ad esempio, le dipendenze, ma anche la versione di Java utilizzata.

### Tomcat 

*Apache Tomcat* è un server web, ovvero un'applicazione software che, essendo in esecuzione su un server, consente di gestire le richieste di trasferimento di pagine web di un client, che può essere un generico web browser. E', nello specifico, un contenitore servlet che opera, quindi, all'interno di unserver (il nome è stato scelto in contrapposizione alle Java applet che, invece, vengono eseguite lato client), open source, sviluppato dalla Apache Software Foundation.

Se per abilitare l'avvio automatico di Tomcat è necessario che tra le dipendenze sia presente la dictura sottostante:

```<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```
In questo modo verrà avviato un Tomcat non appena sarà eseguito il comando *run*.

### Context Root

La radice del contesto di un'applicazione Web identifica la directory che la contiene.
Quindi, per pubblicare, cioè effettuare un'operazione di *deploy* su Tomcat, è necessario definirne il contesto.
Ogni contesto Tomcat, quindi, rappresenta una web application ed ogni server Tomcat può avere in esecuzione più contesti, pr potendo definire uno tra questi come quello di default (omettendo il suo nome nell'URL **TODO**).

Quindi, il context root altro non è che un path, aggiunto all'indirizzo ip, come base per tutte le chiamate API.

Si può specificare aggiungendo nel file *application.property* la eguente specifica:

`server.servlet.context-path=/MIOCONTEXTROOT`


## Building del progetto

Per effettuare un'operazione di builing del progetto bisognerà eseguire il comando seguente:

`./mvnw spring-boot:run`

### Maven

Qualora *Maven* dovesse riscontrare dei problemi sulla variabile d'ambiente `JAVA_HOME`, si può risolvere con il comando `setx -m JAVA_HOME "C:\Program FIlese\Java\jdk-18.0.2`, specificando quindi il path della JDK ed esportando poi questa variabile d'ambiente del sistema scrivendo 
`export JAVA_HOME`. Per verificare che sia stato impostato in maniera corretta si può visualizzare il percorso su console tramite il comando `echo $JAVA_HOME`.

### Dev Build

Per avviare il progetto senza doverlo ricompilare dopo eventuali modifiche bisogna accertarsi che nel pom.xml sia presente questa dipendenza:

```
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-devtools</artifactId>
	<scope>runtime</scope>
	<optional>true</optional>
</dependency>
```

## Response/JSON Mapping

