# Crittografia

## 📖 **Modulo 1: Introduzione alla Crittografia**

### 1.1 Che cos'è la Crittografia? 🕵️‍♂️

La crittografia è l'arte e la scienza di proteggere le informazioni trasformandole in una forma incomprensibile per chi non possiede la chiave per decifrarle. Il termine deriva dal greco "kryptós" (nascosto) e "gráphein" (scrivere), letteralmente "scrittura nascosta". Ma la crittografia moderna va ben oltre il semplice nascondere messaggi: è diventata il fondamento della sicurezza digitale che protegge ogni aspetto della nostra vita online.

Immaginate di voler inviare una lettera d'amore segreta al vostro partner, ma sapete che altre persone potrebbero leggerla lungo il percorso. La crittografia è come avere un codice segreto che solo voi due conoscete: trasformate le parole d'amore in simboli apparentemente senza senso, ma che il destinatario può facilmente riconvertire nel messaggio originale. Questo è esattamente ciò che accade ogni volta che inviate un messaggio su WhatsApp, fate un acquisto online o accedete al vostro conto bancario.

La crittografia moderna si basa su tre pilastri fondamentali: la confidenzialità (assicurare che solo le persone autorizzate possano leggere l'informazione), l'integrità (garantire che l'informazione non sia stata modificata durante la trasmissione) e l'autenticazione (verificare che il mittente sia realmente chi dice di essere). Questi principi sono cruciali in un mondo dove miliardi di informazioni sensibili viaggiano quotidianamente attraverso reti potenzialmente insicure.

Una curiosità affascinante: la crittografia non è un'invenzione moderna! Gli antichi Egizi usavano geroglifici modificati per proteggere i segreti dei faraoni, e Giulio Cesare inventò un cifrario che porta ancora il suo nome. Tuttavia, mentre i metodi antichi si basavano principalmente sul mantenere segreto l'algoritmo stesso, la crittografia moderna segue il principio opposto: gli algoritmi sono pubblici e tutta la sicurezza risiede nella chiave segreta. Questo approccio, paradossalmente, rende i sistemi molto più sicuri perché permette a migliaia di esperti di tutto il mondo di esaminare e migliorare continuamente gli algoritmi.

### 1.2 Storia della Crittografia: Dai Greci ad Enigma 📜

#### 1.2.1 Scitala spartana e cifrario di Cesare

La storia della crittografia inizia nell'antica Grecia con uno strumento apparentemente semplice ma geniale: la scitala spartana. Immaginate un bastone di legno intorno al quale viene avvolto un nastro di cuoio, come se fosse un moderno nastro adesivo. Il messaggio segreto veniva scritto lungo il nastro mentre era avvolto sul bastone, ma una volta srotolato, le lettere apparivano in ordine casuale e incomprensibile. Solo chi possedeva un bastone della stessa circonferenza poteva rileggere il messaggio originale riavvolgendolo correttamente.

Ma è con Giulio Cesare che nasce quello che molti considerano il primo vero cifrario sistematico della storia occidentale. Il cifrario di Cesare funziona con una logica matematica sorprendentemente moderna: ogni lettera dell'alfabeto viene sostituita con quella che si trova un numero fisso di posizioni più avanti. Se scegliamo uno spostamento di 3 posizioni, la A diventa D, la B diventa E, e così via. Questo metodo era così efficace per l'epoca che Cesare lo usava per comunicare con i suoi generali durante le campagne militari in Gallia.

La genialità del cifrario di Cesare sta nella sua semplicità matematica: utilizzando l'aritmetica modulare (che imparerete meglio negli studi universitari), possiamo rappresentare ogni lettera con un numero da 0 a 25, e la cifratura diventa una semplice addizione. Questa idea di trasformare lettere in numeri e applicare operazioni matematiche è alla base di tutta la crittografia moderna. Una curiosità divertente: secondo lo storico Svetonio, Cesare usava uno spostamento di 3 posizioni per i messaggi militari, ma uno spostamento di 1 posizione per la corrispondenza privata. Già allora si capiva l'importanza di usare chiavi diverse per diversi livelli di sicurezza!

#### 1.2.2 La macchina Enigma e la Seconda Guerra Mondiale

La macchina Enigma rappresenta probabilmente il capitolo più drammatico e affascinante della storia della crittografia. Sviluppata negli anni '20 dalla ditta tedesca Scherbius & Ritter, questa macchina elettromeccanica sembrava dall'esterno una normale macchina da scrivere, ma nascondeva al suo interno un sistema crittografico di complessità inaudita per l'epoca. Quando un operatore premeva un tasto, la corrente elettrica passava attraverso una serie di rotori che ruotavano continuamente, creando una sostituzione diversa per ogni singola lettera digitata.

Il punto di forza di Enigma era la sua variabilità: i tedeschi calcolavano che esistessero più di 150 trilioni di combinazioni possibili per configurare la macchina. Ogni giorno, gli operatori ricevevano nuove impostazioni segrete che determinavano la posizione iniziale dei rotori e la configurazione del pannello di collegamento. Per fare un paragone moderno, era come se ogni giorno cambiasse completamente la password di accesso a tutti i sistemi informatici del Reich tedesco. I nazisti erano così convinti dell'inviolabilità di Enigma che la utilizzavano per coordinare attacchi di sottomarini, movimenti di truppe e persino i piani per l'Olocausto.

Tuttavia, la macchina aveva alcune debolezze che si rivelarono fatali. La più importante era che una lettera non poteva mai essere cifrata con se stessa: se premevate A, non poteva mai uscire A. Questo difetto, apparentemente insignificante, fornì agli alleati un punto di attacco cruciale. Inoltre, i tedeschi utilizzavano spesso formule standard per iniziare i messaggi, come previsioni meteorologiche stereotipate o formule di cortesia militari. Gli esperti di Bletchley Park impararono a sfruttare queste "parole probabili" per attaccare il codice. La decifrazione di Enigma non fu solo un trionfo della matematica, ma anche della psicologia umana e dell'analisi delle abitudini comunicative.

#### 1.2.3 Alan Turing e la nascita dell'informatica moderna

Alan Turing non era solo un matematico geniale, ma un visionario che riuscì a immaginare il futuro dell'informatica quando i computer non esistevano ancora. Arrivato a Bletchley Park nel 1939, Turing portò con sé un approccio completamente nuovo alla crittanalisi: invece di tentare di decifrare i messaggi uno alla volta, decise di costruire una macchina che potesse automatizzare il processo di ricerca della configurazione giornaliera di Enigma. Nacque così la "Bomba", un gigantesco dispositivo elettromeccanico che poteva testare migliaia di combinazioni in poche ore.

La Bomba di Turing era essenzialmente il primo computer specializzato della storia, anche se allora nessuno usava ancora questa parola. Il suo funzionamento si basava su un principio che oggi chiamiamo "forza bruta intelligente": invece di provare tutte le possibili combinazioni in modo casuale, la macchina utilizzava la logica matematica per escludere rapidamente le configurazioni impossibili e concentrarsi su quelle promettenti. Questo approccio ridusse il tempo necessario per trovare la chiave giornaliera da anni a poche ore.

Ma l'impatto di Turing va ben oltre la Seconda Guerra Mondiale. Le sue idee sulla "macchina universale" (quello che oggi chiamiamo computer) e sui test per l'intelligenza artificiale hanno gettato le basi teoriche dell'era digitale. La sua definizione di algoritmo e il concetto di macchina che può simulare qualunque altra macchina sono ancora oggi il fondamento teorico di ogni smartphone, computer e server che utilizzate. Una delle frasi più famose di Turing era: "Possiamo vedere solo poco del futuro, ma abbastanza per realizzare che c'è molto da fare". Aveva ragione: il suo lavoro sulla crittografia ha contribuito ad accorciare la guerra di almeno due anni, salvando milioni di vite, e contemporaneamente ha posto le basi per la rivoluzione digitale che stiamo vivendo ancora oggi.

### 1.3 Principi Fondamentali 🧩

#### 1.3.1 Confidenzialità, integrità e autenticazione

Quando parliamo di crittografia moderna, dobbiamo comprendere tre concetti fondamentali che rappresentano i pilastri della sicurezza informatica: confidenzialità, integrità e autenticazione. Questi tre elementi, spesso chiamati "triade CIA" (Confidentiality, Integrity, Authentication), lavorano insieme per garantire che le nostre comunicazioni digitali siano sicure e affidabili.

La confidenzialità è probabilmente il concetto più intuitivo: significa che solo le persone autorizzate possono leggere un messaggio. È come avere una conversazione privata in una stanza chiusa a chiave. Nella pratica digitale, questo significa che quando inviate un messaggio WhatsApp, solo voi e il destinatario potete leggerne il contenuto, anche se il messaggio passa attraverso i server di Meta. La crittografia garantisce che anche se qualcuno intercettasse il messaggio durante il trasporto, vedrebbe solo una sequenza incomprensibile di caratteri casuali.

L'integrità, invece, assicura che il messaggio non sia stato modificato durante il trasporto. Immaginate di inviare l'SMS "Ci vediamo alle 18" e che il destinatario riceva "Ci vediamo alle 8". Anche se il messaggio è ancora leggibile, la modifica potrebbe creare grossi problemi! I sistemi crittografici moderni utilizzano tecniche matematiche sofisticate per creare una sorta di "impronta digitale" del messaggio originale. Se anche un solo bit viene modificato, l'impronta cambia completamente, permettendo di rilevare immediatamente la manomissione.

L'autenticazione garantisce che il mittente sia veramente chi dice di essere. È il equivalente digitale di verificare la firma su un documento importante. Quando ricevete un messaggio apparentemente dalla vostra banca, come fate a essere sicuri che provenga davvero dalla banca e non da un truffatore? I sistemi di autenticazione crittografica utilizzano firme digitali che sono praticamente impossibili da falsificare. Una curiosità interessante: molti sistemi aggiungono anche il "non-ripudio", che impedisce al mittente di negare di aver inviato un messaggio una volta che l'ha spedito.

#### 1.3.2 Chiavi segrete e algoritmi pubblici

Uno dei principi più controintuitivi della crittografia moderna è che la sicurezza non dipende dal tenere segreto l'algoritmo di cifratura, ma dalla protezione delle chiavi. Questo concetto rivoluzionario ha cambiato completamente il modo di progettare sistemi sicuri e rappresenta una delle differenze fondamentali tra la crittografia antica e quella moderna.

Nell'antichità, la sicurezza di un sistema crittografico dipendeva dal mantenere segreto il metodo di cifratura stesso. Se i nemici scoprivano come funzionava la scitala spartana o il cifrario di Cesare, l'intero sistema diventava inutile. Questo approccio, chiamato "security through obscurity" (sicurezza attraverso l'oscurità), si è dimostrato estremamente fragile: basta che una sola persona riveli il segreto per compromettere l'intero sistema.

La crittografia moderna funziona invece come una cassaforte: tutti sanno come è costruita e come funziona il meccanismo, ma solo chi possiede la combinazione giusta può aprirla. Gli algoritmi crittografici moderni come AES o RSA sono completamente pubblici: potete scaricare gratuitamente da internet il codice sorgente completo e studiare ogni singolo dettaglio del loro funzionamento. Migliaia di matematici e informatici di tutto il mondo li analizzano continuamente, cercando possibili debolezze. Questo processo di verifica collettiva rende gli algoritmi molto più robusti di qualunque sistema segreto.

La chiave, invece, deve rimanere assolutamente segreta. È un numero (spesso molto grande) che determina esattamente come l'algoritmo trasformerà il messaggio originale. Anche se due persone usano lo stesso algoritmo, avranno chiavi diverse e quindi i loro messaggi cifrati saranno completamente diversi. La forza di questo approccio sta nel fatto che anche se un nemico conosce perfettamente l'algoritmo, senza la chiave corretta dovrebbe provare miliardi di miliardi di combinazioni per decifrare un singolo messaggio. Una curiosità affascinante: le chiavi moderne sono così lunghe che anche utilizzando tutti i computer del mondo, servirebbe più tempo dell'età dell'universo per provarle tutte!

#### 1.3.3 Il principio di Kerckhoffs

Il principio di Kerckhoffs, formulato dal crittologo olandese Auguste Kerckhoffs nel 1883, rappresenta uno dei fondamenti teorici più importanti della crittografia moderna. Questo principio afferma che un sistema crittografico deve rimanere sicuro anche quando tutto del sistema è pubblicamente conosciuto, eccetto la chiave segreta. In altre parole, la sicurezza deve dipendere solo dalla segretezza della chiave, non dalla segretezza dell'algoritmo.

Kerckhoffs era in anticipo sui tempi quando formulò questo principio. Nell'Ottocento, la maggior parte dei sistemi crittografici si basava ancora sul mantenere segreti i metodi di cifratura. Ma Kerckhoffs aveva capito una verità fondamentale: è molto più facile mantenere segreta una singola chiave che può essere cambiata frequentemente, piuttosto che mantenere segreto un intero algoritmo che potrebbe essere scoperto attraverso l'analisi di molti messaggi cifrati o attraverso spionaggio industriale.

Il principio di Kerckhoffs ha sei punti, ma il più famoso e importante è il secondo: "Il sistema deve essere praticamente, se non matematicamente, indecifrabile". Questo significa che anche se il nemico conosce l'algoritmo e possiede una grande quantità di testi cifrati, deve essere computazionalmente impossibile (o almeno estremamente difficile) recuperare la chiave o decifrare i messaggi. Per "computazionalmente impossibile" intendiamo che anche con i computer più potenti disponibili, il tempo necessario per rompere il sistema sarebbe superiore alla durata dell'universo.

Oggi, questo principio è più rilevante che mai. Tutti i principali algoritmi crittografici (AES, RSA, ECC) sono completamente pubblici e sottoposti a continua analisi da parte della comunità scientifica internazionale. Aziende come Google, Apple e Microsoft pubblicano regolarmente dettagli tecnici sui loro sistemi di sicurezza, seguendo proprio il principio di Kerckhoffs. Questa trasparenza non solo rende i sistemi più sicuri, ma crea anche fiducia negli utenti, che possono verificare indipendentemente la robustezza delle protezioni. Una curiosità moderna: quando nel 2013 Edward Snowden rivelò i programmi di sorveglianza della NSA, uno dei problemi maggiori fu proprio che alcuni algoritmi "segreti" dell'agenzia si rivelarono avere vulnerabilità intenzionali!

### 1.4 Crittografia nella Vita Quotidiana 📱

#### 1.4.1 WhatsApp, banche online e shopping digitale

La crittografia è così integrata nella nostra vita quotidiana che spesso non ci rendiamo nemmeno conto di utilizzarla. Ogni volta che aprite WhatsApp per inviare un messaggio, state utilizzando uno dei sistemi crittografici più avanzati al mondo. Il protocollo Signal, che WhatsApp ha adottato nel 2016, implementa quella che viene chiamata "crittografia end-to-end": questo significa che il vostro messaggio viene cifrato sul vostro telefono e può essere decifrato solo sul telefono del destinatario. Nemmeno WhatsApp stesso può leggere i vostri messaggi!

Ma come funziona tecnicamente? Quando installate WhatsApp, l'applicazione genera automaticamente una coppia di chiavi crittografiche uniche per il vostro dispositivo. Quando inviate un messaggio, questo viene cifrato usando una chiave temporanea che viene creata appositamente per quella conversazione e che cambia continuamente. È come se ogni messaggio viaggiasse in una cassaforte con una combinazione diversa e irripetibile. Questa tecnologia è così robusta che persino se un hacker riuscisse a intercettare tutti i vostri messaggi, vedrebbe solo sequenze casuali di numeri e lettere senza alcun significato.

Lo stesso livello di protezione si applica quando fate acquisti online o accedete al vostro conto bancario. Avete mai notato quel piccolo lucchetto nella barra degli indirizzi del browser quando navigate su siti come Amazon o sulla home banking? Quel simbolo indica che state utilizzando HTTPS, un protocollo che cifra automaticamente tutti i dati che inviate e ricevete. Quando inserite il numero della vostra carta di credito per un acquisto online, quell'informazione viene immediatamente trasformata in codice prima di lasciare il vostro computer.

Una curiosità sorprendente: ogni giorno, senza accorgervene, inviate e ricevete migliaia di chiavi crittografiche. Il vostro smartphone negozia continuamente nuove chiavi con i server di Google, Apple, Facebook e centinaia di altri servizi. È come se il vostro telefono fosse impegnato in una danza segreta continua con il resto di internet, scambiando continuamente nuove combinazioni per mantenere sicure le vostre informazioni. Tutto questo avviene in millisecondi, completamente trasparente per voi, ma rappresenta una delle meraviglie tecnologiche più sofisticate della nostra epoca.

#### 1.4.2 Password e autenticazione a due fattori

Le password rappresentano la forma più comune di crittografia applicata nella vita quotidiana, anche se molte persone non se ne rendono conto. Quando create una password per il vostro account social, quella password non viene mai memorizzata in forma leggibile sui server dell'azienda. Invece, viene processata attraverso una funzione matematica speciale chiamata "hash" che la trasforma in una sequenza apparentemente casuale di caratteri. È come se la vostra password venisse tritata in un frullatore matematico: il risultato finale non assomiglia per niente all'originale, ma è sempre identico se si parte dalla stessa password.

Il processo di hashing ha una caratteristica fondamentale: è praticamente impossibile fare il percorso inverso. Se un hacker riuscisse a rubare il database delle password di un sito web, troverebbe solo queste sequenze "frullate" e non potrebbe risalire alle password originali. Per verificare la vostra identità quando fate login, il sistema semplicemente "frulla" di nuovo la password che avete inserito e controlla se il risultato corrisponde a quello memorizzato. È un po' come riconoscere una persona dal suono della sua voce al telefono: non vedete la persona, ma il "suono" della password è inconfondibile.

Tuttavia, le password da sole non bastano più per garantire una sicurezza adeguata. Ecco perché è nata l'autenticazione a due fattori (2FA), che aggiunge un secondo livello di protezione. Il principio è semplice: anche se qualcuno scopre la vostra password, ha comunque bisogno di un secondo elemento che solo voi possedete. Questo secondo fattore può essere il vostro telefono (che riceve un SMS con un codice), un'app authenticator che genera codici temporanei, o addirittura la vostra impronta digitale.

Una curiosità interessante: gli algoritmi che generano i codici temporanei nelle app come Google Authenticator o Authy sono sincronizzati con orologi atomici! Ogni 30 secondi, il vostro telefono e i server del servizio che state utilizzando generano lo stesso numero utilizzando l'ora esatta come ingrediente segreto. È come se voi e il server faceste parte di un club esclusivo che cambia la parola d'ordine ogni mezzo minuto, basandosi sull'ora universale. Questo sistema è così preciso che anche se il vostro telefono è offline, può comunque generare il codice corretto fintanto che l'orologio interno è sincronizzato.

#### 1.4.3 Blockchain e criptovalute

Le criptovalute come Bitcoin ed Ethereum rappresentano una delle applicazioni più rivoluzionarie della crittografia moderna. A differenza delle valute tradizionali, che dipendono da banche centrali e governi per garantirne il valore, le criptovalute utilizzano la matematica e la crittografia per creare un sistema monetario completamente decentralizzato. È come se invece di affidarsi a una banca per tenere traccia dei vostri soldi, affidaste questo compito a migliaia di computer in tutto il mondo che collaborano utilizzando regole matematiche inviolabili.

Il cuore del sistema è la blockchain, che potete immaginare come un libro mastro digitale distribuito. Ogni transazione viene registrata in "blocchi" di dati che sono collegati tra loro attraverso complessi calcoli crittografici. Ogni blocco contiene l'impronta digitale (hash) del blocco precedente, creando una catena ininterrotta di informazioni. Se qualcuno tentasse di modificare una transazione passata, dovrebbe ricalcolare tutti i blocchi successivi, ma questo richiederebbe una potenza di calcolo maggiore di quella di tutti gli altri partecipanti alla rete messi insieme.

La genialità del sistema sta nel fatto che non serve fidarsi di nessuna autorità centrale: la matematica stessa garantisce l'integrità del sistema. Quando fate una transazione in Bitcoin, state utilizzando una forma sofisticata di crittografia a chiave pubblica per firmare digitalmente il trasferimento. È come se ogni moneta digitale avesse una firma impossibile da falsificare che prova che siete realmente voi a volerla spendere. La rete verifica automaticamente la validità di ogni transazione usando algoritmi crittografici, senza bisogno di banche o intermediari.

Una curiosità affascinante: il consumo energetico del Bitcoin, spesso criticato, è in realtà il costo della sicurezza crittografica. I "minatori" utilizzano enormi quantità di energia per risolvere complessi puzzle matematici che rendono la rete sempre più sicura. È come se la sicurezza della valuta fosse letteralmente alimentata dall'elettricità: più energia viene spesa, più diventa difficile per un attaccante compromettere il sistema. Questo meccanismo, chiamato "Proof of Work", trasforma l'energia fisica in sicurezza digitale, creando un ponte tra il mondo fisico e quello virtuale che è unico nella storia della tecnologia.

### 🤔 **Domande di Verifica Modulo 1**

1. Spiegate la differenza tra confidenzialità, integrità e autenticazione fornendo un esempio pratico per ciascuno.

2. Perché il principio di Kerckhoffs afferma che la sicurezza deve dipendere dalla chiave e non dall'algoritmo? Quali vantaggi offre questo approccio?

3. Descrivi come funziona la crittografia end-to-end in WhatsApp e perché è importante per la privacy.

4. Quale era il difetto principale della macchina Enigma che permise agli Alleati di decifrarla?

5. Spiegate il concetto di hashing delle password e perché è più sicuro memorizzare hash piuttosto che password in chiaro.

6. Come funziona l'autenticazione a due fattori e perché è più sicura delle sole password?

7. In che modo la blockchain utilizza la crittografia per garantire la sicurezza delle transazioni?

8. Perché Alan Turing è considerato un pioniere sia della crittografia che dell'informatica moderna?

---

## 🔤 **Modulo 2: Crittografia Classica**

### 2.1 Cifrari a Sostituzione 🔄

#### 2.1.1 Il cifrario di Cesare: matematica modulare

Il cifrario di Cesare rappresenta il punto di partenza perfetto per comprendere i principi matematici che stanno alla base di tutta la crittografia moderna. Questo sistema, utilizzato da Giulio Cesare per proteggere le comunicazioni militari, introduce concetti che ritroverete anche negli algoritmi più sofisticati di oggi. Il principio è apparentemente semplice: ogni lettera dell'alfabeto viene sostituita con quella che si trova un numero fisso di posizioni più avanti. Ma dietro questa semplicità si nasconde una matematica elegante e potente.

Per comprendere veramente il cifrario di Cesare, dobbiamo introdurre il concetto di aritmetica modulare, che è come l'aritmetica normale ma "circolare". Immaginate l'alfabeto disposto su un orologio: dopo la Z, si ricomincia dalla A. Se vogliamo cifrare la lettera X con uno spostamento di 5 posizioni, otteniamo C (X+5 = C, dove dopo Z viene A). Matematicamente, assegniamo a ogni lettera un numero (A=0, B=1, C=2, ..., Z=25) e applichiamo la formula: lettera_cifrata = (lettera_originale + chiave) mod 26.

La forza didattica del cifrario di Cesare sta nel fatto che permette di sperimentare immediatamente con concetti fondamentali come chiave di cifratura, spazio delle chiavi e vulnerabilità crittografiche. Con un alfabeto di 26 lettere, esistono solo 25 chiavi possibili (escludiamo lo spostamento di 0 che lascerebbe il testo invariato). Questo numero limitato rende il cifrario vulnerabile a un attacco di "forza bruta": un computer moderno può provare tutte le combinazioni in meno di un secondo.

Una curiosità storica affascinante: Cesare utilizzava prevalentemente uno spostamento di 3 posizioni, ma variava la chiave a seconda del tipo di messaggio. Per le comunicazioni militari urgenti usava +3, per la corrispondenza amministrativa +1, e per i messaggi personali talvolta utilizzava sistemi più complessi. Questo approccio anticipava di duemila anni il principio moderno di utilizzare chiavi diverse per diversi livelli di sicurezza. Inoltre, il cifrario di Cesare ha una proprietà matematica interessante: cifrare due volte con chiavi diverse è equivalente a cifrare una sola volta con la somma delle due chiavi. Questa proprietà additiva si ritrova in molti algoritmi moderni e dimostra come principi matematici antichi possano essere ancora rilevanti oggi.

#### 2.1.2 Cifrario di Vigenère: la chiave che si ripete

Il cifrario di Vigenère, sviluppato nel XVI secolo dal diplomatico francese Blaise de Vigenère, rappresenta un salto evolutivo gigantesco rispetto al semplice cifrario di Cesare. Mentre Cesare utilizzava una singola chiave per tutto il messaggio, Vigenère introdusse il concetto rivoluzionario di chiave variabile: ogni lettera del messaggio viene cifrata con una chiave diversa, seguendo un pattern che si ripete. È come se invece di usare una singola "rotazione" dell'alfabeto, utilizzassimo una sequenza di rotazioni diverse che si alternano ciclicamente.

Il funzionamento è elegante nella sua semplicità: scegliete una parola chiave, ad esempio "CRYPTO", e la ripetete sotto il messaggio da cifrare fino a coprirlo completamente. Se il messaggio è "HELLO WORLD", la chiave ripetuta diventa "CRYPT OCRYP". Ogni lettera del messaggio viene quindi cifrata utilizzando come spostamento la lettera corrispondente della chiave: H con C (spostamento 2), E con R (spostamento 17), e così via. Il risultato è che la stessa lettera nel messaggio originale può essere cifrata in modi diversi a seconda della sua posizione.

La genialità di questo sistema sta nel fatto che elimina uno dei punti deboli principali dei cifrari a sostituzione semplice: l'analisi delle frequenze. In italiano, la lettera E appare circa il 11% delle volte, mentre la lettera Z meno dell'1%. Nel cifrario di Cesare, tutte le E diventano sempre la stessa lettera cifrata, rendendo possibile identificare la chiave analizzando le frequenze. Nel cifrario di Vigenère, invece, le E vengono cifrate con lettere diverse ogni volta, "spalmando" la loro frequenza su più simboli e rendendo l'analisi molto più difficile.

Per quasi tre secoli, il cifrario di Vigenère fu considerato inviolabile e venne soprannominato "le chiffre indéchiffrable" (il cifrario indecifrabile). Solo nell'Ottocento, il matematico Friedrich Kasiski scoprì come attaccarlo sistematicamente. Il punto debole era proprio la ripetizione della chiave: se la stessa sequenza di lettere appariva due volte nel messaggio originale alla stessa distanza relativa nella chiave, produceva la stessa sequenza cifrata. Analizzando queste ripetizioni, era possibile dedurre la lunghezza della chiave e poi attaccare ogni "colonna" separatamente come se fosse un cifrario di Cesare. Una curiosità interessante: durante la Guerra Civile Americana, l'Unione utilizzava spesso il cifrario di Vigenère con chiavi molto lunghe, talvolta intere poesie, rendendo la crittanalisi estremamente difficile per i Confederati.

#### 2.1.3 Analisi delle frequenze: come rompere i codici

L'analisi delle frequenze rappresenta una delle tecniche di crittanalisi più eleganti e potenti mai sviluppate, e costituisce il primo esempio storico di applicazione sistematica della statistica alla sicurezza informatica. Questa tecnica si basa su una caratteristica fondamentale di tutte le lingue naturali: le lettere non appaiono con la stessa frequenza. In italiano, alcune lettere come E, A, I sono molto comuni, mentre altre come K, W, Y sono rarissime. Questa "impronta statistica" rimane visibile anche dopo la cifratura con sistemi a sostituzione semplice, fornendo un punto di attacco per decifrare i messaggi.

Il primo a formalizzare questa tecnica fu il matematico arabo Al-Kindi nel IX secolo, anticipando di molti secoli gli sviluppi europei. Al-Kindi osservò che se si sostituisce ogni lettera con un simbolo fisso (come nel cifrario di Cesare), la distribuzione delle frequenze rimane immutata: la lettera più frequente nel testo cifrato corrisponderà probabilmente alla E, la seconda più frequente alla A, e così via. Questo approccio statistico rivoluzionò la crittanalisi e rese obsoleti tutti i cifrari a sostituzione semplice.

La procedura pratica è affascinante nella sua sistematicità: per prima cosa si conta la frequenza di ogni simbolo nel testo cifrato e si costruisce un istogramma. Poi si confronta questa distribuzione con quella tipica della lingua italiana. Le corrispondenze più probabili suggeriscono le prime sostituzioni, che vengono testate inserendole nel testo. Man mano che si identificano più lettere, emergono frammenti di parole che permettono di indovinare altre sostituzioni attraverso il contesto. È un processo iterativo che combina matematica, linguistica e intuizione.

Una curiosità affascinante è che l'analisi delle frequenze funziona anche a livello di bigrammi (coppie di lettere) e trigrammi. In italiano, combinazioni come "CH", "GH", "SCH" sono molto caratteristiche, così come terminazioni comuni come "-IONE", "-MENTE", "-EZZA". Questo permette di attaccare anche cifrari più sofisticati che potrebbero nascondere le frequenze delle singole lettere. Durante la Seconda Guerra Mondiale, i crittanalisti utilizzavano enormi tabelle di frequenze specifiche per diversi tipi di testo: i rapporti militari avevano distribuzioni diverse dalle lettere personali, e persino l'analisi delle preposizioni più comuni poteva fornire indizi cruciali. Un aspetto sorprendente è che ogni lingua ha una sua "firma" statistica unica: è possibile identificare la lingua di un testo cifrato anche senza decifrarlo, semplicemente analizzando le frequenze!

### 2.2 Cifrari a Trasposizione 🔀

#### 2.2.1 Scitala spartana e cifrario a colonne

I cifrari a trasposizione rappresentano un approccio completamente diverso rispetto a quelli a sostituzione: invece di sostituire le lettere con altri simboli, ne cambiano semplicemente l'ordine secondo uno schema prestabilito. È come se prendeste le lettere di un messaggio e le rimescolaste seguendo una ricetta matematica precisa. Questo approccio, apparentemente più semplice della sostituzione, in realtà introduce concetti geometrici e combinatoriali che sono alla base di molte tecniche crittografiche moderne.

La scitala spartana, che abbiamo già incontrato, è il primo esempio documentato di cifrario a trasposizione. Il meccanismo è ingeniosamente semplice: un nastro di cuoio viene avvolto a spirale attorno a un bastone di legno di diametro specifico, il messaggio viene scritto lungo il nastro seguendo le righe del bastone, poi il nastro viene srotolato. Le lettere del messaggio originale rimangono tutte presenti, ma il loro ordine è completamente cambiato secondo uno schema che dipende dalla circonferenza del bastone. Solo chi possiede un bastone identico può riavvolgere il nastro e leggere il messaggio nella sequenza corretta.

Il cifrario a colonne rappresenta l'evoluzione naturale di questo principio e introduce il concetto di matrice crittografica. Il messaggio viene scritto riga per riga in una griglia rettangolare, ma viene letto colonna per colonna secondo un ordine determinato da una chiave numerica. Ad esempio, con la chiave "3142", prima si legge la colonna 3, poi la 1, poi la 4, e infine la 2. È come se il messaggio fosse scritto su una scacchiera e poi "estratto" seguendo un percorso segreto che solo mittente e destinatario conoscono.

Una curiosità affascinante è che la scitala spartana anticipava di oltre duemila anni principi che ritroviamo nella crittografia moderna. Il concetto di "periodo" (il numero di lettere dopo cui il pattern si ripete) è fondamentale anche negli algoritmi contemporanei. Inoltre, la scitala introduce l'idea di "chiave fisica": la sicurezza dipende non da una formula segreta, ma dal possesso di un oggetto specifico. Questo concetto si è evoluto nelle moderne smart card e nei token hardware che usiamo per l'autenticazione bancaria. Durante le guerre del Peloponneso, gli Spartani svilupparono persino un sistema di "multi-scitala": messaggi particolarmente importanti venivano cifrati usando successivamente bastoni di diametri diversi, creando un sistema a trasposizione multipla che anticipava i moderni algoritmi a più stadi.

#### 2.2.2 Route cipher e cifrari geometrici

I route cipher (cifrari di percorso) rappresentano un'evoluzione sofisticata dei cifrari a trasposizione che introduce elementi di geometria e topologia nella crittografia. L'idea base è scrivere il messaggio in una griglia seguendo un percorso specifico (ad esempio a spirale, a zigzag, o seguendo pattern geometrici complessi) e poi leggerlo seguendo un percorso completamente diverso. È come se il messaggio fosse nascosto in un labirinto di lettere e solo chi conosce il "filo di Arianna" giusto possa ritrovare la strada.

Uno dei route cipher più eleganti è quello a spirale: il messaggio viene scritto in una griglia quadrata procedendo dall'esterno verso l'interno in senso orario, ma viene letto procedendo dall'interno verso l'esterno in senso antiorario. Questo crea una trasposizione complessa che mescola le lettere in modo apparentemente casuale ma completamente reversibile. La bellezza di questo sistema sta nel fatto che la chiave può essere descritta semplicemente come "spirale oraria-in, antioraria-out", rendendo facile la memorizzazione ma difficile la decrittazione senza conoscere il metodo.

I cifrari geometrici spingono questo concetto ancora più in là, utilizzando forme matematiche come base per la trasposizione. Un esempio affascinante è il cifrario del "serpente": il messaggio viene scritto seguendo un percorso a zigzag (su e giù alternati) su una griglia, ma letto in ordine colonnare normale. Oppure il cifrario "a diamante", dove le lettere vengono disposte seguendo i vertici e i lati di forme geometriche regolari. Questi sistemi erano particolarmente popolari durante il Rinascimento, quando matematici come Leon Battista Alberti sperimentavano con l'applicazione della geometria euclidea alla crittografia.

Una caratteristica interessante dei route cipher è che possono essere combinati con i cifrari a sostituzione per creare sistemi ibridi estremamente robusti. Durante la Prima Guerra Mondiale, l'esercito tedesco utilizzava un sistema che combinava sostituzione polialfabetica con trasposizione geometrica: prima ogni lettera veniva sostituita secondo un cifrario di Vigenère, poi il risultato veniva sottoposto a trasposizione seguendo pattern geometrici che cambiavano ogni settimana. Questo approccio "difesa in profondità" anticipava i principi dei moderni algoritmi a blocchi, dove i dati vengono processati attraverso multiple fasi di sostituzione e trasposizione. Una curiosità divertente: alcuni route cipher erano così complessi geometricamente che richiedevano strumenti fisici per essere applicati correttamente, come maschere di cartone con fori che guidavano la scrittura e la lettura secondo percorsi prestabiliti.

#### 2.2.3 Combinazioni di sostituzione e trasposizione

La vera rivoluzione nella crittografia classica avvenne quando i crittografi iniziarono a combinare sistematicamente tecniche di sostituzione e trasposizione, creando sistemi che erano molto più resistenti degli attacchi di quanto non fossero le tecniche singole. Questo approccio, chiamato "confusione e diffusione" da Claude Shannon negli anni '40, è ancora oggi il principio fondamentale su cui si basano tutti gli algoritmi crittografici moderni. La sostituzione crea "confusione" (rende complessa la relazione tra chiave e testo cifrato), mentre la trasposizione crea "diffusione" (sparge l'influenza di ogni bit di input su molti bit di output).

Un sistema classico che esemplifica perfettamente questo principio è il cifrario a griglia bifase utilizzato dall'esercito francese durante la Prima Guerra Mondiale. Il processo prevedeva tre fasi: prima il messaggio veniva cifrato con un cifrario di Vigenère usando una chiave alfabetica, poi il risultato veniva scritto in una griglia e sottoposto a trasposizione colonnare usando una chiave numerica, infine veniva applicata una seconda sostituzione usando un alfabeto mischiato. Questo triplo strato di protezione rendeva la crittanalisi estremamente difficile con gli strumenti dell'epoca.

La forza dei sistemi combinati sta nel fatto che gli attacchi efficaci contro un singolo componente diventano inutili contro il sistema completo. L'analisi delle frequenze, devastante contro i cifrari a sostituzione semplice, perde efficacia quando viene applicata la trasposizione finale che "spalma" le frequenze su tutto il testo. Allo stesso modo, gli attacchi geometrici contro i cifrari a trasposizione falliscono quando il testo è già stato "scrambled" da una sostituzione iniziale. È come avere una cassaforte protetta sia da una combinazione numerica che da una chiave fisica: anche se un ladro scopre uno dei due segreti, non può ancora aprire la cassaforte.

Durante la Seconda Guerra Mondiale, questo principio raggiunse la sua massima espressione nei sistemi di cifratura meccanici. La macchina Enigma, ad esempio, combinava sostituzione polialfabetica (attraverso i rotori) con una forma di trasposizione (attraverso il riflettore e il percorso di ritorno). Macchine ancora più sofisticate come la Lorenz SZ-40 utilizzata per i messaggi di massima segretezza del Reich, implementavano multiple fasi di sostituzione XOR combinate con pattern di trasposizione che cambiavano continuamente. Una curiosità affascinante è che alcuni sistemi manuali dell'epoca erano così complessi che richiedevano squadre di operatori specializzati: una persona si occupava della sostituzione iniziale, un'altra della trasposizione, e una terza della sostituzione finale, garantendo che nessun singolo individuo conoscesse l'intero processo e potesse quindi comprometterlo se catturato dal nemico.

### 2.3 Laboratorio Pratico: Decifrare Messaggi Segreti 🔍

#### 2.3.1 Implementazione del cifrario di Cesare in Python

La programmazione del cifrario di Cesare rappresenta il perfetto punto di ingresso nel mondo della crittografia applicata, combinando concetti matematici, logica di programmazione e principi di sicurezza in un progetto accessibile ma significativo. Attraverso questo esercizio pratico, non solo imparerete a implementare un algoritmo crittografico, ma comprenderete anche le basi dell'aritmetica modulare e dell'analisi della complessità algoritmica che sono fondamentali in tutta l'informatica moderna.

Iniziamo con l'implementazione base. Il cuore dell'algoritmo è la trasformazione di ogni carattere: dobbiamo convertire la lettera in un numero (A=0, B=1, ..., Z=25), aggiungere la chiave di spostamento, applicare l'operazione modulo 26 per gestire il "wraparound" dell'alfabeto, e riconvertire il numero in lettera. Ecco il codice:

```python
def cifra_cesare(testo, chiave):
    """
    Cifra un testo usando il cifrario di Cesare
    testo: stringa da cifrare
    chiave: numero di posizioni di spostamento
    """
    risultato = ""
    
    for carattere in testo:
        if carattere.isalpha():  # Solo lettere dell'alfabeto
            # Determina se è maiuscola o minuscola
            base = ord('A') if carattere.isupper() else ord('a')
            # Converte in numero, applica la chiave, riconverte in lettera
            numero = ord(carattere) - base
            numero_cifrato = (numero + chiave) % 26
            carattere_cifrato = chr(numero_cifrato + base)
            risultato += carattere_cifrato
        else:
            # Mantieni spazi, punteggiatura, numeri
            risultato += carattere
    
    return risultato

def decifra_cesare(testo_cifrato, chiave):
    """
    Decifra un testo cifrato con Cesare
    """
    return cifra_cesare(testo_cifrato, -chiave)
```

Ma il vero apprendimento inizia quando iniziamo a sperimentare e migliorare il codice. Una prima estensione interessante è implementare un attacco di forza bruta che prova tutte le 25 chiavi possibili. Questo ci insegna sia l'importanza della dimensione dello spazio delle chiavi sia i principi base della crittanalisi automatizzata. Inoltre, possiamo aggiungere funzionalità per calcolare l'indice di coincidenza (una misura statistica che indica quanto un testo assomiglia alla lingua italiana) per identificare automaticamente la chiave più probabile.

Una curiosità interessante è che implementando il cifrario di Cesare scoprirete naturalmente molti principi della programmazione sicura. Ad esempio, è importante gestire correttamente i caratteri non alfabetici, validare l'input (cosa succede se la chiave è negativa o molto grande?), e considerare la sicurezza della memoria (in linguaggi come C++, bisogna fare attenzione a non lasciare tracce della chiave in memoria). Questo esercizio apparentemente semplice introduce quindi concetti che ritroverete in tutti i sistemi crittografici moderni, dalla gestione sicura delle chiavi alla validazione robusta dell'input.

#### 2.3.2 Cripto-analisi con l'analisi delle frequenze

L'implementazione di un sistema automatico di analisi delle frequenze rappresenta un salto qualitativo nell'apprendimento della crittanalisi, introducendo concetti di statistica computazionale, elaborazione del linguaggio naturale e teoria dell'informazione. Questo laboratorio vi permetterà di "pensare come un crittanalista" e di comprendere perché certi sistemi crittografici che sembrano sicuri sono in realtà vulnerabili a attacchi statistici sofisticati.

Il primo passo è creare una funzione che calcoli la distribuzione delle frequenze in un testo. Questo richiede di attraversare tutto il testo, contare ogni carattere, e normalizzare i risultati per ottenere percentuali. Ma la vera sfida sta nell'interpretare questi dati: come si confronta una distribuzione osservata con quella teorica dell'italiano? Come si gestiscono testi brevi dove le fluttuazioni statistiche sono significative?

```python
def analisi_frequenze(testo):
    """
    Calcola la frequenza di ogni lettera nel testo
    """
    # Frequenze teoriche dell'italiano (approssimate)
    freq_italiano = {
        'A': 11.74, 'B': 0.92, 'C': 4.50, 'D': 3.73, 'E': 11.79,
        'F': 0.95, 'G': 1.64, 'H': 0.64, 'I': 10.14, 'J': 0.00,
        'K': 0.00, 'L': 6.51, 'M': 2.51, 'N': 6.88, 'O': 9.83,
        'P': 3.05, 'Q': 0.51, 'R': 6.37, 'S': 4.98, 'T': 5.62,
        'U': 3.01, 'V': 2.10, 'W': 0.00, 'X': 0.00, 'Y': 0.00,
        'Z': 0.49
    }
    
    # Conta le lettere nel testo
    conteggi = {}
    totale_lettere = 0
    
    for char in testo.upper():
        if char.isalpha():
            conteggi[char] = conteggi.get(char, 0) + 1
            totale_lettere += 1
    
    # Calcola le percentuali
    frequenze_osservate = {}
    for lettera in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ':
        freq = (conteggi.get(lettera, 0) / totale_lettere) * 100
        frequenze_osservate[lettera] = freq
    
    return frequenze_osservate, freq_italiano

def calcola_chi_quadro(freq_osservate, freq_teoriche):
    """
    Calcola il test chi-quadro per confrontare due distribuzioni
    """
    chi_quadro = 0
    for lettera in freq_teoriche:
        teorica = freq_teoriche[lettera]
        osservata = freq_osservate[lettera]
        if teorica > 0:
            chi_quadro += ((osservata - teorica) ** 2) / teorica
    return chi_quadro
```

Il test chi-quadro è uno strumento statistico potente che ci permette di quantificare quanto due distribuzioni di frequenza siano simili. Valori bassi indicano grande somiglianza, valori alti indicano distribuzioni molto diverse. Questo ci permette di automatizzare il processo di identificazione della chiave più probabile in un cifrario di Cesare: proviamo tutte le 25 chiavi, calcoliamo il chi-quadro per ogni decrittazione, e scegliamo quella con il valore più basso.

Una scoperta affascinante che emergerà dai vostri esperimenti è che l'analisi delle frequenze funziona sorprendentemente bene anche su testi relativamente brevi (100-200 caratteri), ma la sua efficacia dipende fortemente dal tipo di testo. Testi tecnici, nomi propri, o messaggi in lingue straniere possono produrre distribuzioni anomale che ingannano l'algoritmo. Questo introduce il concetto fondamentale di "robustezza" degli algoritmi crittanalitici: un buon sistema deve funzionare su una varietà di input reali, non solo su esempi teorici perfetti.

#### 2.3.3 Sfide di decrittazione

Le sfide di decrittazione rappresentano il momento più emozionante e formativo del laboratorio, dove teoria e pratica si incontrano in enigmi concreti che richiedono creatività, logica e perseveranza. Attraverso una serie progressiva di messaggi cifrati di difficoltà crescente, svilupperete l'intuizione crittanalitica e imparerete ad applicare le tecniche studiate a situazioni realistiche che richiedono adattamenti e innovazioni.

La prima categoria di sfide riguarda i cifrari di Cesare "travestiti": messaggi dove la chiave non è uniforme su tutto il testo, o dove sono stati introdotti caratteri di disturbo, o dove il testo originale non è in italiano standard. Ad esempio, un messaggio potrebbe utilizzare chiavi diverse per le prime e seconde metà, o potrebbe includere numeri cifrati con una logica diversa dalle lettere. Queste variazioni vi insegneranno a non accettare mai le prime conclusioni dell'analisi automatica, ma a verificare sempre i risultati e a cercare pattern alternativi.

La seconda categoria introduce i cifrari polialfabetici semplificati: messaggi cifrati con Vigenère usando chiavi molto corte (2-4 caratteri) che possono essere attaccati dividendo il testo in colonne e applicando l'analisi delle frequenze a ogni colonna separatamente. Questo tipo di sfida introduce concetti avanzati come l'analisi dell'indice di coincidenza per determinare la lunghezza della chiave, e il metodo di Kasiski per identificare ripetizioni significative.

```python
def trova_ripetizioni(testo, min_lunghezza=3):
    """
    Trova sequenze ripetute nel testo cifrato (metodo di Kasiski)
    """
    ripetizioni = {}
    lunghezza = len(testo)
    
    for i in range(lunghezza - min_lunghezza):
        for j in range(i + min_lunghezza, lunghezza - min_lunghezza):
            # Cerca sequenze di lunghezza variabile
            for lung in range(min_lunghezza, min(lunghezza - j, 8)):
                seq1 = testo[i:i+lung]
                seq2 = testo[j:j+lung]
                if seq1 == seq2 and seq1.isalpha():
                    distanza = j - i
                    if seq1 not in ripetizioni:
                        ripetizioni[seq1] = []
                    ripetizioni[seq1].append(distanza)
    
    return ripetizioni

def calcola_mcd_distanze(ripetizioni):
    """
    Calcola il MCD delle distanze per stimare la lunghezza della chiave
    """
    import math
    tutte_distanze = []
    for seq in ripetizioni:
        tutte_distanze.extend(ripetizioni[seq])
    
    if len(tutte_distanze) < 2:
        return None
    
    mcd = tutte_distanze[0]
    for distanza in tutte_distanze[1:]:
        mcd = math.gcd(mcd, distanza)
    
    return mcd
```

La terza categoria di sfide introduce elementi di "crittografia mista": messaggi che combinano diversi tipi di cifrari o che utilizzano chiavi non standard. Ad esempio, potreste incontrare un messaggio cifrato prima con Cesare e poi con trasposizione colonnare, o un sistema dove la chiave di Vigenère cambia a metà messaggio. Queste sfide vi insegneranno a riconoscere i "segnali" che indicano la presenza di più livelli di cifratura e a sviluppare strategie sistematiche per "sbucciare" i diversi strati di protezione.

Una caratteristica particolarmente formativa di queste sfide è che spesso non hanno una soluzione unica o un percorso risolutivo lineare. Potreste scoprire che un approccio che funziona perfettamente su un messaggio fallisce completamente sul successivo, costringendovi a ripensare le vostre assunzioni e a sviluppare nuove strategie. Questo rispecchia fedelmente la realtà della crittanalisi professionale, dove ogni nuovo sistema richiede creatività e adattamento. Una curiosità interessante è che molte delle tecniche che svilupperete intuitivamente durante queste sfide sono state "riscoperte" indipendentemente da crittanalisti professionali nel corso della storia, dimostrando come certe intuizioni logiche siano universali e senza tempo.

### 🤔 **Domande di Verifica Modulo 2**

1. Spiegate la differenza fondamentale tra cifrari a sostituzione e cifrari a trasposizione, fornendo un esempio pratico per ciascuno.

2. Perché il cifrario di Vigenère fu considerato "indecifrabile" per tre secoli? Quale fu la chiave per romperlo?

3. Implementate a mano il cifrario di Cesare per cifrare la parola "SEGRETO" con chiave 7.

4. Come funziona l'analisi delle frequenze e perché è efficace contro i cifrari a sostituzione semplice?

5. Descrivi il metodo di Kasiski per attaccare il cifrario di Vigenère.

6. Perché combinare sostituzione e trasposizione rende un sistema crittografico più sicuro?

7. Quale proprietà matematica rende il cifrario di Cesare vulnerabile agli attacchi di forza bruta?

8. Spiegate come la scitala spartana anticipava principi della crittografia moderna.

---

## 🖥️ **Modulo 3: Crittografia Moderna** 

### 3.1 Crittografia a Chiave Simmetrica 🔑

#### 3.1.1 Advanced Encryption Standard (AES)

L'Advanced Encryption Standard (AES) rappresenta il culmine dell'evoluzione della crittografia simmetrica e costituisce oggi lo standard de facto per la protezione dei dati in tutto il mondo. Adottato dal NIST (National Institute of Standards and Technology) americano nel 2001 dopo un rigoroso processo di selezione durato cinque anni, AES ha sostituito il precedente DES diventando il sistema crittografico più utilizzato al mondo. Ogni volta che navigate su un sito HTTPS, inviate un messaggio WhatsApp o accedete al vostro home banking, molto probabilmente state utilizzando AES.

La genesi di AES è una storia affascinante di competizione scientifica e trasparenza democratica. Nel 1997, il NIST lanciò un concorso pubblico per selezionare il nuovo standard crittografico americano, invitando crittografi di tutto il mondo a sottoporre i loro algoritmi. Quindici proposte furono accettate e sottoposte a anni di analisi intensiva da parte della comunità crittografica internazionale. Il vincitore fu Rijndael, sviluppato dai crittografi belgi Vincent Rijmen e Joan Daemen, che riuscì a combinare eccellente sicurezza, alta velocità e implementazione efficiente sia in software che in hardware.

Il cuore di AES è un processo chiamato "rete di sostituzione-permutazione" che elabora i dati attraverso molteplici round di trasformazioni matematiche. A differenza dei cifrari classici che abbiamo studiato, AES non lavora su lettere ma su blocchi di 128 bit (16 byte) alla volta. Ogni blocco viene sottoposto a una sequenza di quattro operazioni fondamentali: SubBytes (sostituzione non lineare), ShiftRows (trasposizione delle righe), MixColumns (mescolamento delle colonne) e AddRoundKey (combinazione con la chiave di round). Queste operazioni vengono ripetute 10, 12 o 14 volte a seconda della lunghezza della chiave (128, 192 o 256 bit).

La bellezza matematica di AES sta nella sua costruzione su campi finiti, strutture algebriche che garantiscono che ogni operazione sia perfettamente reversibile e che non esistano valori "deboli" che potrebbero compromettere la sicurezza. L'operazione SubBytes, ad esempio, utilizza l'inverso moltiplicativo nel campo di Galois GF(2^8), seguita da una trasformazione affine che elimina simmetrie indesiderate. Questo livello di sofisticazione matematica rende AES praticamente immune agli attacchi classici di crittanalisi, richiedendo ai potenziali attaccanti di considerare tutte le 2^128, 2^192 o 2^256 possibili chiavi – numeri così grandi che superano il numero di atomi nell'universo osservabile. Una curiosità interessante: AES è così efficiente che processori moderni includono istruzioni hardware specifiche (AES-NI) che permettono di cifrare dati alla velocità di diversi gigabyte al secondo.

#### 3.1.2 Data Encryption Standard (DES) e la sua evoluzione

Il Data Encryption Standard (DES) occupa un posto unico nella storia della crittografia moderna, rappresentando il primo algoritmo crittografico sviluppato sotto l'egida di un'agenzia governativa e reso pubblico per uso commerciale. Adottato come standard federale americano nel 1977, DES ha dominato la crittografia commerciale per oltre vent'anni, ma la sua storia è anche ricca di controversie, sospetti e scoperte che hanno cambiato per sempre il modo di concepire la sicurezza informatica.

DES nacque da un progetto IBM chiamato Lucifer, sviluppato nel 1971 da Horst Feistel. Quando IBM sottopose Lucifer al National Bureau of Standards per la standardizzazione, la NSA (National Security Agency) intervenne nel processo di revisione, apportando modifiche significative che suscitarono immediate controversie. La più discussa fu la riduzione della lunghezza della chiave da 128 a 56 bit, una decisione che molti crittografi accademici interpretarono come un tentativo deliberato di indebolire l'algoritmo per renderlo attaccabile dalle agenzie di intelligence.

La struttura di DES si basa sulla "rete di Feistel", un'architettura elegante che divide il blocco di dati in due metà e le elabora attraverso 16 round di trasformazioni. In ogni round, una metà viene processata attraverso una funzione complessa che dipende dalla chiave, e il risultato viene combinato con l'altra metà attraverso un'operazione XOR. La genialità di questa struttura sta nel fatto che la stessa operazione può essere utilizzata sia per cifrare che per decifrare, semplicemente applicando le chiavi di round in ordine inverso.

Tuttavia, il vero dramma di DES iniziò negli anni '90 quando divenne chiaro che la lunghezza della chiave di 56 bit era inadeguata per l'era dei computer moderni. Nel 1998, la Electronic Frontier Foundation costruì una macchina specializzata chiamata "DES Cracker" che riuscì a rompere una chiave DES in meno di tre giorni, dimostrando pubblicamente la vulnerabilità dell'algoritmo. Questo evento segnò la fine dell'era DES e accelerò lo sviluppo di AES. Una conseguenza interessante fu la nascita di 3DES (Triple DES), che applica DES tre volte consecutive con chiavi diverse, aumentando effettivamente la sicurezza ma triplicando anche il tempo di elaborazione. Nonostante le sue limitazioni, DES ha lasciato un'eredità duratura: molti dei principi di design e delle tecniche di analisi sviluppate per DES sono ancora utilizzate negli algoritmi moderni, e la sua struttura di Feistel rimane uno dei paradigmi fondamentali della crittografia simmetrica.

#### 3.1.3 Modalità di cifratura: ECB, CBC, CTR

Le modalità di cifratura rappresentano uno degli aspetti più sottovalutati ma cruciali della crittografia pratica. Mentre algoritmi come AES definiscono come cifrare singoli blocchi di dati, le modalità di cifratura determinano come questi blocchi vengono combinati per proteggere messaggi di lunghezza arbitraria. La scelta della modalità sbagliata può compromettere completamente la sicurezza di un sistema, anche quando si utilizza un algoritmo crittografico robusto. È come avere una porta blindata eccellente ma installarla male: il risultato finale può essere disastroso.

La modalità ECB (Electronic CodeBook) è la più semplice e intuitiva: ogni blocco di dati viene cifrato indipendentemente utilizzando la stessa chiave. È come tradurre un libro utilizzando un dizionario fisso: ogni parola viene sempre tradotta nello stesso modo. Questa semplicità, però, nasconde vulnerabilità gravi. Poiché blocchi identici nel testo originale producono sempre blocchi identici nel testo cifrato, emergono pattern visibili che possono rivelare informazioni sul contenuto originale. Il famoso esempio è l'immagine del pinguino Tux di Linux: quando viene cifrata in modalità ECB, la silhouette rimane chiaramente visibile nel risultato cifrato.

La modalità CBC (Cipher Block Chaining) risolve i problemi di ECB introducendo dipendenza tra i blocchi consecutivi. Prima di essere cifrato, ogni blocco viene combinato tramite XOR con il risultato della cifratura del blocco precedente. Per il primo blocco, si utilizza un "vettore di inizializzazione" (IV) casuale. È come se ogni parola del nostro libro venisse modificata in base alla traduzione della parola precedente, creando un effetto a catena che si propaga attraverso tutto il messaggio. Questo elimina i pattern visibili e garantisce che testi identici producano sempre risultati cifrati diversi, purché si utilizzino IV diversi.

La modalità CTR (Counter) rappresenta un approccio completamente diverso che trasforma un cifrario a blocchi in un cifrario a flusso. Invece di cifrare direttamente i dati, CTR cifra una sequenza di contatori incrementali e poi combina il risultato con il testo originale tramite XOR. È come generare una sequenza di "maschere" casuali che vengono applicate ai dati originali. Questa modalità offre vantaggi unici: permette la cifratura parallela (ogni blocco può essere processato indipendentemente), consente l'accesso casuale ai dati cifrati (si può decifrare solo una parte del file senza dover decifrare tutto), e trasforma errori di trasmissione in errori locali senza compromettere il resto del messaggio.

Una curiosità affascinante è che la scelta della modalità può influenzare drammaticamente le prestazioni oltre alla sicurezza. CTR è particolarmente adatto per applicazioni ad alta velocità perché può sfruttare al massimo processori multi-core, mentre CBC è intrinsecamente sequenziale. Inoltre, alcune modalità moderne come GCM (Galois/Counter Mode) combinano cifratura e autenticazione in un'unica operazione, fornendo sia confidenzialità che verifica dell'integrità con overhead computazionale minimo. Questo è particolarmente importante in applicazioni come le VPN e il cloud computing, dove miliardi di operazioni crittografiche devono essere eseguite ogni secondo mantenendo latenze bassissime.

### 3.2 Crittografia a Chiave Pubblica 🗝️🗝️

#### 3.2.1 Il problema dello scambio delle chiavi

Il problema dello scambio delle chiavi ha tormentato la crittografia per millenni e rappresenta forse la sfida più fondamentale nella progettazione di sistemi di comunicazione sicura. Immaginate di voler stabilire una comunicazione segreta con qualcuno che non avete mai incontrato, utilizzando un canale di comunicazione completamente pubblico e potenzialmente sorvegliato. Come fate a concordare una chiave segreta senza che questa venga intercettata da potenziali spie? Questo paradosso apparentemente irrisolvibile ha limitato l'uso della crittografia per secoli, confinandola principalmente a organizzazioni militari e diplomatiche che potevano permettersi complesse reti di corrieri e incontri segreti.

Nella crittografia simmetrica tradizionale, mittente e destinatario devono condividere la stessa chiave segreta sia per cifrare che per decifrare i messaggi. Questo crea un circolo vizioso: per comunicare in modo sicuro, devo prima comunicare in modo sicuro per scambiare la chiave! Il problema diventa ancora più complesso quando consideriamo le comunicazioni moderne: come fa Amazon a stabilire una connessione sicura con milioni di clienti che non ha mai incontrato fisicamente? Come fanno due smartphone a creare un canale sicuro per trasferire file senza aver mai comunicato prima?

Storicamente, questo problema è stato risolto attraverso elaborate infrastrutture di distribuzione delle chiavi. Durante la Guerra Fredda, ambasciate e basi militari ricevevano regolarmente "libri di codici" trasportati da corrieri diplomatici, contenenti chiavi pre-condivise per ogni giorno dell'anno. Le aziende utilizzavano servizi specializzati di corriere per trasportare fisicamente dispositivi contenenti chiavi crittografiche. Ma questi approcci erano costosi, lenti, e fondamentalmente non scalabili per l'era di Internet dove miliardi di dispositivi devono stabilire connessioni sicure istantaneamente.

Il breakthrough arrivò negli anni '70 con una scoperta rivoluzionaria che sembrò violare le leggi fondamentali della logica: era possibile creare sistemi crittografici dove la chiave per cifrare fosse diversa da quella per decifrare, e soprattutto, dove una delle due chiavi potesse essere resa completamente pubblica senza compromettere la sicurezza del sistema. Questa idea, così controintuitiva da essere inizialmente accolta con scetticismo, avrebbe trasformato non solo la crittografia ma l'intera società digitale. Una curiosità affascinante è che il concetto di crittografia a chiave pubblica fu scoperto indipendentemente in tre luoghi diversi: dai ricercatori Diffie e Hellman alla Stanford University nel 1976, da Ron Rivest, Adi Shamir e Leonard Adleman al MIT nel 1977, e segretamente dal matematico britannico Clifford Cocks al GCHQ nel 1973, anche se quest'ultima scoperta rimase classificata per decenni.

#### 3.2.2 RSA: matematica dei numeri primi

L'algoritmo RSA, dal nome dei suoi inventori Ron Rivest, Adi Shamir e Leonard Adleman, rappresenta uno dei trionfi più eleganti della matematica applicata alla sicurezza informatica. La sua genialità sta nell'utilizzare un problema matematico antico e apparentemente astratto – la fattorizzazione di numeri molto grandi – per creare un sistema crittografico praticamente inviolabile. È un esempio perfetto di come la matematica pura possa trovare applicazioni inaspettate e rivoluzionarie nella tecnologia moderna.

Il cuore di RSA risiede in un fatto matematico sorprendente: mentre è relativamente facile moltiplicare due numeri primi molto grandi per ottenere il loro prodotto, è estremamente difficile fare il percorso inverso, cioè trovare i fattori primi di un numero molto grande. Ad esempio, moltiplicare 1.229 × 1.231 = 1.513.199 richiede pochi millisecondi, ma se vi do solo il numero 1.513.199 e vi chiedo di trovare i suoi fattori primi, potreste impiegare molto tempo anche con un computer potente. Ora immaginate di fare questa operazione con numeri primi di 1024 bit (circa 300 cifre decimali): la moltiplicazione richiede frazioni di secondo, ma la fattorizzazione richiederebbe miliardi di anni anche ai computer più potenti attualmente esistenti.

Il processo di generazione delle chiavi RSA è un capolavoro di eleganza matematica. Prima si scelgono due numeri primi molto grandi, chiamiamoli p e q, e si calcola n = p × q. Questo numero n diventerà parte della chiave pubblica. Poi si calcola φ(n) = (p-1) × (q-1), che rappresenta il numero di interi minori di n che sono coprimi con n (questa è la funzione di Eulero). Si sceglie quindi un numero e relativamente primo con φ(n), tipicamente 65537 per ragioni di efficienza. Infine, si calcola d, l'inverso moltiplicativo di e modulo φ(n), utilizzando l'algoritmo esteso di Euclide. La chiave pubblica è la coppia (n, e), mentre la chiave privata è la coppia (n, d).

Il processo di cifratura e decifratura utilizza l'aritmetica modulare in modo brillante. Per cifrare un messaggio m, si calcola c = m^e mod n. Per decifrare, si calcola m = c^d mod n. La magia matematica sta nel fatto che questi due processi sono l'uno l'inverso dell'altro grazie al piccolo teorema di Fermat e al teorema di Eulero. Quello che rende RSA sicuro è che, conoscendo solo n ed e (la chiave pubblica), è computazionalmente impossibile calcolare d senza conoscere la fattorizzazione di n in p e q.

Una curiosità affascinante è che RSA fu quasi scoperto vent'anni prima della sua pubblicazione ufficiale. Nel 1973, il matematico britannico Clifford Cocks, che lavorava per l'agenzia di intelligence GCHQ, aveva sviluppato un sistema quasi identico, ma la sua scoperta rimase classificata fino al 1997. Questo episodio illustra perfettamente come la ricerca in crittografia sia sempre stata divisa tra il mondo accademico aperto e quello segreto delle agenzie di intelligence. Oggi, RSA è utilizzato quotidianamente da miliardi di persone: ogni volta che vedete il lucchetto verde nel vostro browser web, molto probabilmente state utilizzando RSA per stabilire una connessione sicura.

#### 3.2.3 Diffie-Hellman: accordo di chiavi su canale insicuro

L'algoritmo di scambio di chiavi Diffie-Hellman rappresenta forse la più elegante soluzione al problema dello scambio di chiavi mai escogitata, e la sua scoperta nel 1976 ha letteralmente reso possibile l'esistenza di Internet sicuro. L'idea alla base è così controintuitiva da sembrare magica: due persone che non si sono mai incontrate possono concordare una chiave segreta comunicando esclusivamente attraverso un canale pubblico completamente sorvegliato, senza mai trasmettere informazioni che permettano a un osservatore di ricostruire la chiave.

L'analogia più famosa per spiegare Diffie-Hellman è quella dei colori di vernice. Immaginate che Alice e Bob vogliano concordare un colore segreto. Prima concordano pubblicamente un colore di base, diciamo il giallo. Poi ciascuno sceglie segretamente un colore personale: Alice sceglie il rosso, Bob sceglie il blu. Alice mescola il giallo con il rosso ottenendo l'arancione e lo invia pubblicamente a Bob. Bob mescola il giallo con il blu ottenendo il verde e lo invia pubblicamente ad Alice. Ora Alice mescola il verde ricevuto con il suo rosso segreto, ottenendo un colore finale. Bob mescola l'arancione ricevuto con il suo blu segreto. Sorprendentemente, entrambi ottengono lo stesso colore finale! Un osservatore che ha visto solo giallo, arancione e verde non può ricostruire il colore finale senza conoscere i colori segreti di Alice e Bob.

Matematicamente, l'algoritmo si basa sulla difficoltà del problema del logaritmo discreto in campi finiti. Alice e Bob concordano pubblicamente un numero primo grande p e un generatore g. Alice sceglie segretamente un numero a e calcola A = g^a mod p, che invia a Bob. Bob sceglie segretamente un numero b e calcola B = g^b mod p, che invia ad Alice. Alice calcola la chiave condivisa come K = B^a mod p, mentre Bob la calcola come K = A^b mod p. Grazie alle proprietà dell'aritmetica modulare, entrambi ottengono lo stesso risultato: K = g^(ab) mod p.

La sicurezza di Diffie-Hellman si basa sul fatto che, anche conoscendo p, g, A e B, è computazionalmente impossibile calcolare g^(ab) mod p senza conoscere né a né b. Questo è il "problema Diffie-Hellman computazionale", che si ritiene essere tanto difficile quanto il problema del logaritmo discreto. Per numeri sufficientemente grandi (tipicamente 2048 bit o più), questo problema richiede un tempo computazionale che supera l'età dell'universo anche utilizzando i computer più potenti esistenti.

Una delle caratteristiche più affascinanti di Diffie-Hellman è la sua "perfect forward secrecy": anche se in futuro un attaccante riuscisse a compromettere le chiavi private a lungo termine di Alice e Bob, non potrebbe comunque decifrare le comunicazioni passate, perché ogni sessione utilizza valori a e b temporanei che vengono scartati dopo l'uso. Questa proprietà è cruciale in applicazioni moderne come TLS, dove garantisce che la compromissione di un server non esponga retroattivamente tutte le comunicazioni precedenti. Una curiosità interessante è che Whitfield Diffie e Martin Hellman furono ispirati dal lavoro di Ralph Merkle sui "puzzle crittografici", e inizialmente il loro algoritmo era noto come "Diffie-Hellman-Merkle". Oggi, varianti moderne di Diffie-Hellman basate su curve ellittiche permettono di ottenere la stessa sicurezza con chiavi molto più corte, rendendo l'algoritmo adatto anche a dispositivi con risorse computazionali limitate come smartphone e oggetti IoT.

### 3.3 Funzioni Hash e Firme Digitali ✍️

#### 3.3.1 Cosa sono le funzioni di hash e a cosa servono

Le funzioni di hash crittografiche rappresentano uno degli strumenti più versatili e fondamentali della crittografia moderna, paragonabili alle impronte digitali nel mondo fisico. Proprio come ogni persona ha impronte digitali uniche che la identificano in modo inequivocabile, ogni file, messaggio o sequenza di dati può essere "identificato" da una funzione hash attraverso una stringa di caratteri apparentemente casuali ma matematicamente deterministica. Questa "impronta digitale" ha proprietà straordinarie che la rendono indispensabile in innumerevoli applicazioni informatiche.

Il concetto di base è deceptivamente semplice: una funzione hash prende in input una quantità arbitraria di dati (da un singolo carattere a file di terabyte) e produce sempre un output di lunghezza fissa, tipicamente 256 o 512 bit. È come avere una macchina magica che, non importa cosa ci inseriate dentro – una poesia, un film, o l'intera Wikipedia – produce sempre un numero di esattamente 64 caratteri esadecimali. Ma la vera magia sta nelle proprietà matematiche di questa trasformazione: è completamente deterministica (lo stesso input produce sempre lo stesso output), è praticamente impossibile da invertire (dall'output non si può risalire all'input), e anche un cambiamento minuscolo nell'input produce un output completamente diverso.

Quest'ultima proprietà, chiamata "effetto valanga", è particolarmente affascinante. Se cambiate anche solo una virgola in un documento di mille pagine, l'hash risultante sarà completamente diverso, senza alcuna somiglianza apparente con quello originale. È come se l'intera "identità matematica" del documento cambiasse completamente per la modifica di un singolo bit. Questa sensibilità estrema rende le funzioni hash perfette per rilevare anche le più piccole modifiche accidentali o intenzionali nei dati.

Le applicazioni pratiche sono innumerevoli e spesso invisibili agli utenti. Ogni volta che scaricate un file da Internet e il sistema verifica automaticamente che il download sia avvenuto correttamente, sta comparando l'hash del file scaricato con quello fornito dal server. Quando fate login a un sito web, la vostra password non viene mai memorizzata in chiaro: viene invece conservato solo il suo hash, e ogni volta che inserite la password, il sistema ne calcola l'hash e lo confronta con quello memorizzato. Anche la blockchain di Bitcoin si basa interamente su funzioni hash: ogni blocco è identificato dal hash del suo contenuto, e i "minatori" competono per trovare un numero che, aggiunto al blocco, produca un hash con specifiche caratteristiche matematiche.

Una curiosità affascinante è che le funzioni hash hanno rivoluzionato anche settori completamente esterni all'informatica. In campo forense, vengono utilizzate per garantire l'integrità delle prove digitali: l'hash di un hard disk viene calcolato al momento del sequestro e poi verificato durante il processo per dimostrare che i dati non sono stati alterati. Nel mondo dell'arte, alcune case d'aste utilizzano hash per creare "certificati di autenticità digitale" per opere d'arte, creando un legame matematico indissolubile tra l'opera fisica e la sua rappresentazione digitale. Perfino in biologia, le funzioni hash vengono utilizzate per confrontare rapidamente sequenze genetiche, permettendo di identificare somiglianze tra DNA di specie diverse in modo molto più efficiente rispetto ai metodi tradizionali.

#### 3.3.2 SHA-256 e l'integrità dei dati

SHA-256 (Secure Hash Algorithm 256-bit) rappresenta il gold standard delle funzioni hash crittografiche moderne e costituisce la spina dorsale di innumerevoli sistemi di sicurezza in tutto il mondo. Sviluppato dalla NSA e pubblicato dal NIST nel 2001 come parte della famiglia SHA-2, questo algoritmo ha resistito a oltre vent'anni di analisi intensiva da parte della comunità crittografica mondiale, consolidando la sua reputazione come uno degli algoritmi più sicuri e affidabili mai creati.

La struttura interna di SHA-256 è un capolavoro di ingegneria crittografica che combina principi matematici sofisticati con un'implementazione efficiente. L'algoritmo elabora i dati in blocchi di 512 bit attraverso 64 round di trasformazioni complesse, utilizzando otto registri a 32 bit che vengono continuamente modificati attraverso operazioni logiche, aritmetiche e di rotazione. Ogni round utilizza una costante diversa derivata dalle radici cubiche dei primi 64 numeri primi, garantendo che non esistano pattern nascosti o backdoor nell'algoritmo. Il risultato finale è un hash di esattamente 256 bit che rappresenta una "firma" unica e praticamente infalsificabile del contenuto originale.

La forza di SHA-256 sta nella sua resistenza a tutti i tipi di attacco crittografico conosciuti. È resistente alle collisioni (è computazionalmente impossibile trovare due input diversi che producano lo stesso hash), alle pre-immagini (dato un hash, è impossibile trovare un input che lo produca) e alle seconde pre-immagini (dato un input e il suo hash, è impossibile trovare un secondo input diverso che produca lo stesso hash). Queste proprietà sono cruciali per l'integrità dei dati: se anche un singolo bit viene modificato in un file, l'hash SHA-256 cambia completamente, rendendo la manomissione immediatamente detectabile.

Un esempio pratico della potenza di SHA-256 si trova nella verifica dell'integrità del software. Quando scaricate un programma importante come un sistema operativo o un'applicazione di sicurezza, spesso il sito web fornisce anche l'hash SHA-256 del file. Dopo il download, potete calcolare l'hash del file scaricato e confrontarlo con quello fornito: se corrispondono, avete la garanzia matematica che il file non è stato alterato durante il trasferimento e che corrisponde esattamente a quello originale pubblicato dal sviluppatore. Questa verifica è così importante che molti sistemi operativi moderni la eseguono automaticamente prima di installare aggiornamenti di sistema.

SHA-256 è anche il cuore del sistema di "proof of work" utilizzato da Bitcoin e molte altre criptovalute. I minatori competono per trovare un numero (chiamato "nonce") che, aggiunto ai dati del blocco, produca un hash SHA-256 che inizia con un numero specifico di zeri. Questa ricerca richiede miliardi di tentativi e una quantità enorme di energia computazionale, ma una volta trovato il nonce giusto, chiunque può verificare immediatamente la validità del risultato calcolando un singolo hash SHA-256. È un esempio brillante di come un problema matematicamente difficile da risolvere possa essere facilmente verificabile, creando un sistema di consenso distribuito che non richiede autorità centrali. Una curiosità interessante è che la rete Bitcoin calcola collettivamente oltre 100 quintilioni (10^20) di hash SHA-256 al secondo, un numero così grande che se ogni hash fosse un granello di sabbia, formerebbe una sfera più grande della Terra ogni secondo.

#### 3.3.3 Firme digitali e firme elettroniche

Le firme digitali rappresentano l'equivalente elettronico delle firme autografe, ma con caratteristiche di sicurezza che superano di gran lunga quelle delle firme tradizionali. Mentre una firma su carta può essere falsificata da un abile falsario e può essere copiata e incollata su documenti diversi, una firma digitale è matematicamente legata al contenuto specifico del documento e alla chiave privata del firmatario in modo che sia praticamente impossibile da falsificare o trasferire su altri documenti.

Il processo di creazione di una firma digitale è un elegante esempio di come la crittografia a chiave pubblica possa essere utilizzata in modo "inverso" rispetto alla cifratura normale. Invece di utilizzare la chiave pubblica per cifrare e quella privata per decifrare, nelle firme digitali si utilizza la chiave privata per "firmare" e quella pubblica per "verificare". Il processo inizia calcolando l'hash crittografico del documento da firmare, poi questo hash viene "cifrato" con la chiave privata del firmatario utilizzando algoritmi come RSA o DSA. Il risultato è la firma digitale, che viene allegata al documento originale.

La verifica della firma è altrettanto elegante: chiunque può utilizzare la chiave pubblica del presunto firmatario per "decifrare" la firma, ottenendo l'hash originale. Poi calcola indipendentemente l'hash del documento ricevuto e lo confronta con quello estratto dalla firma. Se i due hash corrispondono, la firma è valida e questo prova due cose fondamentali: primo, che il documento è stato effettivamente firmato da chi possiede la chiave privata corrispondente a quella chiave pubblica (autenticazione), e secondo, che il documento non è stato modificato dopo la firma (integrità).

È importante distinguere tra "firme digitali" e "firme elettroniche", termini spesso confusi ma tecnicamente diversi. Le firme elettroniche sono un concetto giuridico ampio che include qualsiasi metodo elettronico per indicare l'accettazione di un documento: può essere un semplice click su "Accetto", la digitazione del proprio nome, o l'uso di un tablet per tracciare una firma calligrafica. Le firme digitali, invece, sono una specifica implementazione tecnologica delle firme elettroniche che utilizza la crittografia a chiave pubblica per garantire autenticazione, integrità e non-ripudio.

Il non-ripudio è una proprietà unica delle firme digitali che non ha equivalenti nel mondo fisico: una volta che avete firmato digitalmente un documento, non potete successivamente negare di averlo fatto, purché la vostra chiave privata non sia stata compromessa. Questo è possibile perché la firma può essere stata creata solo da chi possiede la chiave privata, e la matematica della crittografia rende impossibile che qualcun altro abbia potuto generare quella specifica firma per quel specifico documento. Questa proprietà ha rivoluzionato settori come il banking online, il commercio elettronico e la pubblica amministrazione digitale. Una curiosità interessante è che alcune giurisdizioni riconoscono alle firme digitali basate su crittografia a chiave pubblica un valore legale superiore rispetto alle firme autografe tradizionali, proprio grazie alla loro resistenza alla falsificazione e alla capacità di garantire l'integrità del documento firmato.

#### 3.3.4 Certificati digitali e PKI

L'infrastruttura a chiave pubblica (PKI - Public Key Infrastructure) rappresenta la soluzione al problema fondamentale della crittografia a chiave pubblica: come fare a sapere se una chiave pubblica appartiene veramente alla persona che dice di essere? È come il problema delle carte d'identità nel mondo fisico: una carta d'identità ha valore solo se è stata emessa da un'autorità riconosciuta e fidata. Allo stesso modo, i certificati digitali sono "carte d'identità" elettroniche che legano una chiave pubblica all'identità del suo proprietario attraverso la firma di un'autorità di certificazione (CA) fidata.

Un certificato digitale è essenzialmente un documento elettronico che contiene la chiave pubblica di un individuo o organizzazione insieme alle informazioni che lo identificano (nome, organizzazione, indirizzo email, ecc.) e la firma digitale di una Certificate Authority che garantisce l'autenticità di queste informazioni. È come se la CA dicesse: "Io, autorità fidata, certifico che questa chiave pubblica appartiene realmente a questa persona/organizzazione, e lo garantisco con la mia firma digitale".

Il processo di ottenimento di un certificato è rigoroso e varia a seconda del livello di sicurezza richiesto. Per i certificati di base (Domain Validated), è sufficiente dimostrare il controllo di un dominio web. Per i certificati di livello superiore (Organization Validated o Extended Validation), sono necessarie verifiche approfondite dell'identità legale dell'organizzazione, inclusi controlli su registri commerciali, verifiche telefoniche e talvolta visite fisiche. Le CA più prestigiose mantengono standard di sicurezza fisica e procedurale che superano quelli delle banche: i loro sistemi di firma sono custoditi in bunker sotterranei con controlli biometrici, e le operazioni più critiche richiedono la presenza simultanea di più operatori autorizzati.

La struttura gerarchica delle PKI è progettata per distribuire la fiducia in modo scalabile e sicuro. Al vertice ci sono le "Root CA", le cui chiavi private sono gelosamente protette e utilizzate molto raramente. Queste firmano i certificati delle "Intermediate CA", che a loro volta firmano i certificati degli utenti finali. Questa struttura a catena permette di revocare certificati compromessi senza dover ricostruire l'intera infrastruttura, e di distribuire il carico di lavoro su molte CA intermedie mantenendo al sicuro le chiavi radice più preziose.

Quando navigate su un sito HTTPS, il vostro browser esegue automaticamente una complessa verifica della catena di certificati: controlla che il certificato del sito sia firmato da una CA intermedia fidata, che questa sia a sua volta firmata da una Root CA presente nel browser, che i certificati non siano scaduti o revocati, e che il nome del sito corrisponda a quello nel certificato. Tutto questo avviene in pochi millisecondi, ma dietro le quinte si svolge una danza crittografica sofisticata che coinvolge verifiche di firme digitali, controlli di revoca attraverso protocolli come OCSP, e validazioni della catena di fiducia.

Una delle sfide più interessanti delle PKI moderne è la gestione della revoca dei certificati. Cosa succede se la chiave privata di qualcuno viene compromessa? Come si fa a "invalidare" un certificato già emesso? La soluzione tradizionale sono le Certificate Revocation Lists (CRL) e il protocollo OCSP (Online Certificate Status Protocol), ma questi approcci hanno limitazioni di scalabilità e privacy. Recentemente sono stati sviluppati sistemi più avanzati come Certificate Transparency, che mantiene log pubblici e verificabili di tutti i certificati emessi, permettendo di detectare rapidamente certificati fraudolenti. Una curiosità affascinante è che tutto l'ecosistema HTTPS del web si basa sulla fiducia verso un numero relativamente piccolo di Root CA (meno di 200), le cui chiavi sono letteralmente "i segreti più preziosi di Internet": se anche una sola di queste chiavi venisse compromessa, un attaccante potrebbe creare certificati validi per qualsiasi sito web del mondo.

### 3.4 Laboratorio: Crittografia con Python 💻

#### 3.4.1 Uso di librerie crittografiche

L'implementazione pratica di algoritmi crittografici moderni richiede l'uso di librerie specializzate che garantiscano non solo la correttezza matematica degli algoritmi, ma anche la sicurezza dell'implementazione contro attacchi sofisticati come quelli basati su analisi dei tempi di esecuzione o del consumo energetico. In Python, la libreria `cryptography` rappresenta lo standard de facto per applicazioni crittografiche professionali, fornendo un'interfaccia sicura e ben documentata per tutti i principali algoritmi crittografici.

Prima di iniziare a sperimentare, è fondamentale comprendere che la crittografia pratica è molto più complessa della semplice applicazione di formule matematiche. Una implementazione corretta deve gestire la generazione sicura di numeri casuali, la gestione sicura delle chiavi in memoria, la prevenzione di attacchi temporali, e la validazione rigorosa di tutti gli input. Le librerie professionali come `cryptography` incorporano decenni di esperienza e best practices della comunità crittografica mondiale.

Iniziamo con un esempio di cifratura simmetrica usando AES:

```python
from cryptography.fernet import Fernet
from cryptography.hazmat.primitives import hashes
from cryptography.hazmat.primitives.kdf.pbkdf2 import PBKDF2HMAC
import os
import base64

def genera_chiave_da_password(password, salt=None):
    """
    Genera una chiave AES sicura da una password utilizzando PBKDF2
    """
    if salt is None:
        salt = os.urandom(16)  # 16 byte casuali per il salt
    
    kdf = PBKDF2HMAC(
        algorithm=hashes.SHA256(),
        length=32,  # 32 byte = 256 bit per AES-256
        salt=salt,
        iterations=100000,  # 100.000 iterazioni per rallentare attacchi brute force
    )
    
    chiave = base64.urlsafe_b64encode(kdf.derive(password.encode()))
    return chiave, salt

def cifra_messaggio(messaggio, password):
    """
    Cifra un messaggio usando AES con chiave derivata da password
    """
    chiave, salt = genera_chiave_da_password(password)
    f = Fernet(chiave)
    
    messaggio_cifrato = f.encrypt(messaggio.encode())
    
    # Restituiamo sia il messaggio cifrato che il salt (necessario per decifrare)
    return messaggio_cifrato, salt

def decifra_messaggio(messaggio_cifrato, password, salt):
    """
    Decifra un messaggio utilizzando la password e il salt originali
    """
    chiave, _ = genera_chiave_da_password(password, salt)
    f = Fernet(chiave)
    
    try:
        messaggio_originale = f.decrypt(messaggio_cifrato)
        return messaggio_originale.decode()
    except:
        return "Errore: password incorretta o messaggio corrotto"

# Esempio di utilizzo
messaggio = "Questo è un messaggio segreto!"
password = "password_super_sicura_123!"

print(f"Messaggio originale: {messaggio}")

# Cifratura
cifrato, salt = cifra_messaggio(messaggio, password)
print(f"Messaggio cifrato: {cifrato}")
print(f"Salt utilizzato: {base64.b64encode(salt).decode()}")

# Decifratura
decifrato = decifra_messaggio(cifrato, password, salt)
print(f"Messaggio decifrato: {decifrato}")
```

Questo esempio introduce diversi concetti fondamentali della crittografia applicata. PBKDF2 (Password-Based Key Derivation Function 2) è uno standard che trasforma password umane in chiavi crittografiche robuste, utilizzando un "salt" casuale e molte iterazioni per rendere costosi gli attacchi di dizionario. Il salt impedisce gli attacchi con rainbow table, mentre le 100.000 iterazioni rallentano significativamente i tentativi di brute force.

Un aspetto cruciale spesso trascurato è la gestione sicura delle chiavi in memoria. Le librerie professionali utilizzano tecniche speciali per minimizzare il tempo di permanenza delle chiavi in memoria e per "zerizzare" le aree di memoria contenenti materiale crittografico sensibile dopo l'uso. Questo previene attacchi sofisticati che potrebbero estrarre chiavi dalla memoria RAM anche dopo che il programma è terminato.

#### 3.4.2 Creazione di un sistema di messaggistica sicura

La creazione di un sistema di messaggistica sicura end-to-end rappresenta un progetto complesso che integra tutti i concetti crittografici studiati: crittografia simmetrica per l'efficienza, crittografia asimmetrica per lo scambio di chiavi, funzioni hash per l'integrità, e firme digitali per l'autenticazione. Questo laboratorio vi permetterà di comprendere le sfide reali che affrontano sviluppatori di applicazioni come Signal, WhatsApp o Telegram.

Il nostro sistema implementerà una versione semplificata del protocollo Double Ratchet utilizzato da Signal, considerato il gold standard per la messaggistica sicura. L'idea centrale è che ogni messaggio viene cifrato con una chiave diversa e temporanea, che viene immediatamente scartata dopo l'uso. Questo garantisce la "perfect forward secrecy": anche se un attaccante compromette il sistema, non può decifrare i messaggi precedenti.

```python
from cryptography.hazmat.primitives.asymmetric import rsa, padding
from cryptography.hazmat.primitives import serialization, hashes
from cryptography.fernet import Fernet
import json
import base64
import os

class MessaggisticaSicura:
    def __init__(self, nome_utente):
        self.nome_utente = nome_utente
        self.chiave_privata = None
        self.chiave_pubblica = None
        self.chiavi_pubbliche_contatti = {}
        self.genera_coppia_chiavi()
    
    def genera_coppia_chiavi(self):
        """Genera una nuova coppia di chiavi RSA per l'utente"""
        self.chiave_privata = rsa.generate_private_key(
            public_exponent=65537,
            key_size=2048
        )
        self.chiave_pubblica = self.chiave_privata.public_key()
        print(f"🔑 Chiavi generate per {self.nome_utente}")
    
    def esporta_chiave_pubblica(self):
        """Esporta la chiave pubblica in formato condivisibile"""
        pem = self.chiave_pubblica.public_key_bytes(
            encoding=serialization.Encoding.PEM,
            format=serialization.PublicFormat.SubjectPublicKeyInfo
        )
        return base64.b64encode(pem).decode()
    
    def importa_chiave_pubblica_contatto(self, nome_contatto, chiave_pubblica_pem):
        """Importa la chiave pubblica di un contatto"""
        try:
            pem_bytes = base64.b64decode(chiave_pubblica_pem.encode())
            chiave_pubblica = serialization.load_pem_public_key(pem_bytes)
            self.chiavi_pubbliche_contatti[nome_contatto] = chiave_pubblica
            print(f"✅ Chiave pubblica di {nome_contatto} importata correttamente")
            return True
        except Exception as e:
            print(f"❌ Errore nell'importazione della chiave: {e}")
            return False
    
    def cifra_messaggio(self, destinatario, messaggio):
        """
        Cifra un messaggio per un destinatario specifico usando crittografia ibrida
        """
        if destinatario not in self.chiavi_pubbliche_contatti:
            raise ValueError(f"Chiave pubblica di {destinatario} non disponibile")
        
        # Genera una chiave simmetrica temporanea per questo messaggio
        chiave_simmetrica = Fernet.generate_key()
        f = Fernet(chiave_simmetrica)
        
        # Cifra il messaggio con la chiave simmetrica (veloce)
        messaggio_cifrato = f.encrypt(messaggio.encode())
        
        # Cifra la chiave simmetrica con la chiave pubblica del destinatario (sicuro)
        chiave_pubblica_dest = self.chiavi_pubbliche_contatti[destinatario]
        chiave_cifrata = chiave_pubblica_dest.encrypt(
            chiave_simmetrica,
            padding.OAEP(
                mgf=padding.MGF1(algorithm=hashes.SHA256()),
                algorithm=hashes.SHA256(),
                label=None
            )
        )
        
        # Calcola l'hash del messaggio per verifica dell'integrità
        digest = hashes.Hash(hashes.SHA256())
        digest.update(messaggio.encode())
        hash_messaggio = digest.finalize()
        
        # Firma l'hash con la nostra chiave privata per autenticazione
        firma = self.chiave_privata.sign(
            hash_messaggio,
            padding.PSS(
                mgf=padding.MGF1(hashes.SHA256()),
                salt_length=padding.PSS.MAX_LENGTH,
            ),
            hashes.SHA256()
        )
        
        # Pacchetto finale contenente tutti i componenti
        pacchetto = {
            'mittente': self.nome_utente,
            'destinatario': destinatario,
            'messaggio_cifrato': base64.b64encode(messaggio_cifrato).decode(),
            'chiave_cifrata': base64.b64encode(chiave_cifrata).decode(),
            'hash_messaggio': base64.b64encode(hash_messaggio).decode(),
            'firma': base64.b64encode(firma).decode(),
            'timestamp': __import__('time').time()
        }
        
        return json.dumps(pacchetto, indent=2)
    
    def decifra_messaggio(self, pacchetto_json):
        """
        Decifra un messaggio ricevuto e verifica autenticità e integrità
        """
        try:
            pacchetto = json.loads(pacchetto_json)
            mittente = pacchetto['mittente']
            
            if mittente not in self.chiavi_pubbliche_contatti:
                return "❌ Errore: chiave pubblica del mittente non disponibile"
            
            # Decodifica i componenti
            messaggio_cifrato = base64.b64decode(pacchetto['messaggio_cifrato'])
            chiave_cifrata = base64.b64decode(pacchetto['chiave_cifrata'])
            hash_atteso = base64.b64decode(pacchetto['hash_messaggio'])
            firma = base64.b64decode(pacchetto['firma'])
            
            # Decifra la chiave simmetrica con la nostra chiave privata
            chiave_simmetrica = self.chiave_privata.decrypt(
                chiave_cifrata,
                padding.OAEP(
                    mgf=padding.MGF1(algorithm=hashes.SHA256()),
                    algorithm=hashes.SHA256(),
                    label=None
                )
            )
            
            # Decifra il messaggio con la chiave simmetrica
            f = Fernet(chiave_simmetrica)
            messaggio_originale = f.decrypt(messaggio_cifrato).decode()
            
            # Verifica l'integrità calcolando l'hash del messaggio decifrato
            digest = hashes.Hash(hashes.SHA256())
            digest.update(messaggio_originale.encode())
            hash_calcolato = digest.finalize()
            
            if hash_calcolato != hash_atteso:
                return "❌ Errore: il messaggio è stato modificato!"
            
            # Verifica l'autenticità verificando la firma
            chiave_pubblica_mittente = self.chiavi_pubbliche_contatti[mittente]
            try:
                chiave_pubblica_mittente.verify(
                    firma,
                    hash_atteso,
                    padding.PSS(
                        mgf=padding.MGF1(hashes.SHA256()),
                        salt_length=padding.PSS.MAX_LENGTH,
                    ),
                    hashes.SHA256()
                )
                print("✅ Firma verificata: il messaggio è autentico")
            except:
                return "❌ Errore: firma non valida!"
            
            return f"📨 Messaggio da {mittente}: {messaggio_originale}"
            
        except Exception as e:
            return f"❌ Errore nella decifratura: {e}"

# Esempio di utilizzo del sistema
print("🚀 Creazione sistema di messaggistica sicura\n")

# Alice e Bob creano i loro account
alice = MessaggisticaSicura("Alice")
bob = MessaggisticaSicura("Bob")

# Scambio delle chiavi pubbliche (simula una fase di "pairing")
alice_pub = alice.esporta_chiave_pubblica()
bob_pub = bob.esporta_chiave_pubblica()

bob.importa_chiave_pubblica_contatto("Alice", alice_pub)
alice.importa_chiave_pubblica_contatto("Bob", bob_pub)

print("\n💬 Test di invio messaggio sicuro:")

# Alice invia un messaggio a Bob
messaggio_segreto = "Ciao Bob! Questo è un messaggio super segreto 🔐"
pacchetto_cifrato = alice.cifra_messaggio("Bob", messaggio_segreto)

print(f"\n📤 Alice invia (pacchetto cifrato):")
print(pacchetto_cifrato[:200] + "..." if len(pacchetto_cifrato) > 200 else pacchetto_cifrato)

# Bob riceve e decifra il messaggio
risultato = bob.decifra_messaggio(pacchetto_cifrato)
print(f"\n📥 Bob riceve:")
print(risultato)
```

Questo sistema implementa quello che viene chiamato "crittografia ibrida": combina la velocità della crittografia simmetrica (per cifrare il messaggio) con la sicurezza della crittografia asimmetrica (per cifrare la chiave simmetrica). Inoltre, integra firme digitali per garantire autenticazione e funzioni hash per verificare l'integrità.

Una caratteristica fondamentale del nostro sistema è che ogni messaggio utilizza una chiave simmetrica diversa e temporanea. Questo significa che anche se un attaccante compromette una chiave, può decifrare solo un singolo messaggio, non l'intera conversazione. Nei sistemi reali come Signal, questo concetto viene esteso ulteriormente con il "Double Ratchet Algorithm", che aggiorna continuamente le chiavi utilizzando funzioni crittografiche unidirezionali.

Il sistema include anche protezioni contro attacchi sofisticati: le firme digitali prevengono attacchi "man-in-the-middle" dove qualcuno potrebbe intercettare e modificare i messaggi, mentre la verifica dell'hash garantisce che i dati non siano stati corrotti durante la trasmissione. Una curiosità interessante è che la dimensione del pacchetto cifrato è significativamente più grande del messaggio originale a causa di tutti questi livelli di protezione, ma questo overhead è il prezzo da pagare per una sicurezza robusta.

### 🤔 **Domande di Verifica Modulo 3**

1. Spiegate le differenze principali tra AES e DES, e perché AES è considerato più sicuro.

2. Perché è importante utilizzare modalità di cifratura come CBC invece di ECB? Fornite un esempio pratico.

3. Come risolve la crittografia a chiave pubblica il problema dello scambio delle chiavi?

4. Spiegate il principio matematico su cui si basa la sicurezza di RSA.

5. Che cos'è l'effetto valanga nelle funzioni hash e perché è importante?

6. Qual è la differenza tra firme digitali e firme elettroniche?

7. Come funziona una Certificate Authority e perché è necessaria nelle PKI?

8. Perché nei sistemi di messaggistica moderni si utilizzano chiavi temporanee per ogni messaggio?

9. Spiegate il concetto di "perfect forward secrecy" e la sua importanza.

10. Come si combina crittografia simmetrica e asimmetrica nei sistemi ibridi?
