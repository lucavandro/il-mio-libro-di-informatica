# Architettura client-server per siti web

## Il ruolo di client e di server nel web

Nel mondo di Internet, la comunicazione avviene principalmente secondo un modello chiamato "client-server". Questo modello è la base fondamentale su cui si regge la maggior parte dei servizi che utilizziamo quotidianamente, dalle pagine web alle applicazioni di messaggistica istantanea.

Un **client** è un computer, uno smartphone, un tablet o qualsiasi dispositivo che richiede un servizio o delle informazioni. Quando utilizzi il browser web sul tuo computer, quel computer agisce da client: invia richieste per ottenere pagine web, immagini, video e altri contenuti. Il client non possiede direttamente i dati, ma sa dove e come andare a cercarli.

Un **server**, invece, è un computer potente e sempre acceso che rimane in ascolto costante delle richieste provenienti dai client. Il server archivia le informazioni, elabora le richieste ricevute e invia le risposte appropriate. Un server è generalmente una macchina più potente di un computer domestico, perché deve gestire simultaneamente le richieste provenienti da migliaia di client diversi. I server si trovano solitamente in enormi strutture chiamate "data center", dove vengono mantenuti a temperature controllate e protetti da sistemi di sicurezza sofisticati.

Una curiosità interessante è che la distinzione tra client e server non è tanto una caratteristica hardware, ma piuttosto un ruolo funzionale: un computer può essere sia client che server. Ad esempio, il tuo computer potrebbe ospitare un server web locale mentre contemporaneamente funge da client per accedere ad altri servizi online.

La comunicazione tra client e server segue un protocollo ben definito, cioè un insieme di regole che entrambi devono rispettare per comprendersi. Il protocollo più importante per il web è l'HTTP (HyperText Transfer Protocol), che definisce come deve avvenire lo scambio di richieste e risposte.

### Gli indirizzi IP e il DNS

Per comunicare su Internet, ogni dispositivo necessita di un identificatore univoco, esattamente come le case hanno un indirizzo per ricevere la posta. Questo identificatore è l'**indirizzo IP** (Internet Protocol address). Un indirizzo IP è una sequenza numerica che identifica in modo univoco un computer connesso a una rete. Attualmente esistono due versioni principali di indirizzi IP: la versione 4 (IPv4) e la versione 6 (IPv6).

Un **indirizzo IPv4** è composto da quattro numeri separati da punti, come `192.168.1.1`. Ogni numero può andare da 0 a 255, il che significa che con IPv4 è possibile avere circa 4 miliardi di indirizzi diversi. Se questo numero potesse sembrare enorme, devi considerare che Internet ha superato il numero di indirizzi IPv4 disponibili già intorno al 2011! Ecco perché è stato introdotto l'**IPv6**, che utilizza numeri molto più grandi (fino a 340 undecilioni di indirizzi possibili) ed è rappresentato da una sequenza di numeri e lettere esadecimali.

Tuttavia, gli indirizzi IP numerici sono difficili da ricordare e molto poco intuitivi. Non potremmo pretendere dagli utenti di ricordare che per visitare Google devono digitare `142.250.185.46` nel browser! Per risolvere questo problema, esiste il **DNS** (Domain Name System), un sistema che funziona come una "rubrica telefonica" di Internet.

Il DNS traduce i nomi di dominio leggibili, come "google.com" o "wikipedia.org", nei corrispondenti indirizzi IP numerici. Quando digiti un URL nel tuo browser, il computer non sa direttamente quale indirizzo IP ha quel sito. Quindi invia una richiesta a un server DNS, chiedendo: "Qual è l'indirizzo IP di google.com?". Il server DNS risponde fornendo l'indirizzo IP corretto. Questo processo avviene molto rapidamente, solitamente in meno di un secondo, e accade completamente dietro le quinte senza che l'utente se ne accorga.

Una curiosità affascinante è che il primo server DNS di Internet è ancora in funzione: è il server "A.root-server.net", gestito dall'organizzazione VeriSign, e risponde alle richieste DNS da ormai oltre trent'anni! Il sistema dei server root-nameserver è ridondante e distribuito globalmente proprio per garantire che Internet rimanga sempre funzionante anche in caso di problemi in diverse regioni.

#### Domande di verifica

1. Qual è la differenza principale tra un client e un server nella comunicazione su Internet?
2. Spiega con parole tue perché un indirizzo IP da solo non è sufficiente e perché abbiamo bisogno del DNS.
3. Quanti indirizzi IPv4 diversi è possibile creare teoricamente?
4. Se inserisci un URL nel browser, quali passaggi avvengono prima che la pagina web venga visualizzata?
5. Cosa fa un server DNS e perché è importante per il funzionamento di Internet?

## I siti web statici

Un **sito web statico** è il tipo più semplice di sito web. Consiste in una raccolta di file, principalmente file HTML, CSS e JavaScript, che il server invia esattamente come sono memorizzati. Ogni volta che un utente visita la stessa pagina, riceve identicamente gli stessi contenuti, indipendentemente da chi sia l'utente o da quante volte visiti il sito.

Per comprendere meglio cosa significhi "statico", immagina una biblioteca. Se una pagina del tuo libro di testo fosse sempre identica, indipendentemente da chi la legga o quando la legga, quella sarebbe come una pagina statica. Il contenuto non cambia, non viene personalizzato, rimane sempre uguale.

Un sito web statico è estremamente veloce da servire al client, perché il server non deve eseguire alcun calcolo o elaborazione. Deve solo leggere i file dal disco rigido e inviarli al browser. Per questo motivo, i siti statici sono ancora molto utilizzati per portfolio personali, documentazione, blog semplici e siti informativi. Una curiosità interessante è che alcuni siti statici di grande successo, come i blog tecnologici o le pagine di landing per il marketing, rimangono statici perché sono estremamente efficienti e veloci a caricarsi, il che piace sia agli utenti che ai motori di ricerca.

L'architettura di un sito statico è molto semplice: il server contiene una struttura di cartelle e file. Quando riceve una richiesta da un client (ad esempio, la richiesta di accedere a www.example.com/pagina), il server individua il file corrispondente nel suo file system e lo invia al browser. Il browser riceve il file HTML, lo interpreta, scarica eventuali risorse aggiuntive (immagini, fogli di stile CSS, script JavaScript) e visualizza la pagina.

Un vantaggio importante dei siti statici è la loro sicurezza relativa: poiché non c'è elaborazione lato server, il rischio di vulnerabilità è minore. Non ci sono database da proteggere (per lo meno non dal lato web pubblico), e non c'è codice server che possa essere sfruttato. Tuttavia, uno svantaggio significativo è la mancanza di personalizzazione e interattività: tutti gli utenti vedono le stesse cose, non è possibile memorizzare preferenze personali, e non è possibile creare esperienze dinamiche.

#### Domande di verifica

1. Che cos'è un sito web statico e come si differenzia da altri tipi di siti?
2. Perché un sito web statico è generalmente più veloce di un sito dinamico nel caricamento?
3. Descrivi il processo che avviene dal momento in cui un utente digita un URL fino a quando vede la pagina web completamente caricata.
4. Quali sono i vantaggi e i limiti di un sito web statico?
5. Puoi fare esempi di siti web che potrebbero essere efficacemente realizzati come siti statici?

## I siti web dinamici

Un **sito web dinamico** è un'evoluzione del sito statico: il contenuto non è fisso, ma viene generato dal server al momento della richiesta. Questo significa che lo stesso URL potrebbe fornire contenuti diversi a seconda di vari fattori: chi è l'utente, quando visita il sito, cosa ha inserito in un modulo, o quali dati sono disponibili nel database.

Per visualizzare un esempio concreto: immagina Facebook. Quando accedi al tuo profilo, vedi i tuoi contenuti personali, i tuoi amici, i tuoi messaggi. Un altro utente, visitando il proprio profilo nello stesso momento, vede un contenuto completamente diverso. Questo è possibile solo grazie ai siti dinamici. Il server riceve la richiesta, esegue del codice (generalmente scritto in linguaggi come PHP, Python, Node.js, Java e altri), accede a un database per recuperare le informazioni corrette, elabora tutto e genera una pagina HTML personalizzata che invia al browser.

La differenza fondamentale nel flusso di comunicazione è questa: in un sito statico il server dice "Ecco il file HTML che ho", mentre in un sito dinamico il server dice "Dimmi di te, lo farò e poi ti mostrerò una pagina creata apposta per te". Questa personalizzazione rende i siti dinamici molto più potenti e utili per applicazioni complesse, ma anche più complessi da gestire e manutenere.

Un sito dinamico richiede tre componenti principali: un **server web** (che gestisce le richieste HTTP e invia risposte), un **linguaggio di scripting lato server** (che esegue la logica di business), e un **database** (dove sono memorizzati i dati). Quando un utente invia una richiesta, il server web la riceve e la passa al linguaggio di scripting. Questo elabora la richiesta, effettua query al database, elabora i dati ricevuti e infine genera il codice HTML finale che viene inviato al browser dell'utente.

Una curiosità affascinante è che la pagina HTML che vedi nel browser quando visiti un sito dinamico non esiste realmente nel server prima della tua richiesta! È creata al volo, solo per te, nel momento esatto in cui la richiedi. Se la scaricassi e la guardatri il codice HTML sorgente, non troverai alcun codice di scripting: troverai solo HTML, CSS e JavaScript lato client, perché tutto il codice server è stato già eseguito e il suo risultato è stato convertito in HTML.

I siti dinamici offrono molti vantaggi: personalizzazione, interattività, la possibilità di salvare preferenze utente, di gestire login e sicurezza, di creare contenuti generati dagli utenti, e di mantenere facilmente grandi quantità di dati tramite database. Tuttavia, presentano anche sfide: sono più complessi da sviluppare e mantenere, consumano più risorse del server, e richiedono maggiore attenzione agli aspetti di sicurezza, poiché un errore nel codice server potrebbe esporre dati sensibili.

#### Domande di verifica

1. Qual è la differenza principale tra un sito web statico e un sito web dinamico?
2. Descrivi il processo completo che avviene quando un utente visita una pagina in un sito dinamico.
3. Quali sono i tre componenti principali di un'architettura di sito dinamico?
4. Perché nella maggior parte dei siti che usi quotidianamente (come i social network) è necessario usare un'architettura dinamica?
5. Quali sono i vantaggi e gli svantaggi di un sito web dinamico rispetto a uno statico?
