# La programmazione ad oggetti in Javascript

## 1. Introduzione alla programmazione ad oggetti

### 1.1 Cos'è la programmazione ad oggetti?

La programmazione ad oggetti (OOP - Object-Oriented Programming) è un paradigma di programmazione basato sul concetto di "oggetti", che possono contenere dati e codice. I dati sono sotto forma di campi (spesso noti come attributi o proprietà), e il codice è sotto forma di procedure (spesso chiamate metodi).

Caratteristiche principali:

- Organizzazione del codice in unità chiamate oggetti
- Combinazione di dati e comportamenti
- Progettazione di programmi in termini di oggetti che interagiscono tra loro

### 1.2 Vantaggi della programmazione ad oggetti

1. Modularità: Il codice per un oggetto può essere scritto e mantenuto indipendentemente dal codice di altri oggetti.

2. Riusabilità: Gli oggetti possono essere riutilizzati in diversi programmi.

3. Scalabilità e manutenibilità: I sistemi OOP sono più facili da modificare e estendere.

4. Astrazione: L'OOP permette di nascondere i dettagli implementativi e mostrare solo le funzionalità all'utente.

5. Organizzazione: Fornisce un modo chiaro di organizzare il codice in progetti complessi.

### 1.3 Concetti fondamentali: oggetti e classi

#### Oggetti

Un oggetto è un'istanza di una classe. Rappresenta un'entità del mondo reale e ha:

- Stato (attributi o proprietà)
- Comportamento (metodi o funzioni)

Esempio in JavaScript:

```javascript
let cane = {
    nome: "Fido",
    razza: "Labrador",
    abbaia: function() {
        console.log("Bau bau!");
    }
};
```

#### Classi

Una classe è un "progetto" o un "modello" per creare oggetti. Definisce:

- Attributi: le caratteristiche dell'oggetto
- Metodi: le azioni che l'oggetto può compiere

Esempio di classe in JavaScript (ES6+):

```javascript
class Cane {
    constructor(nome, razza) {
        this.nome = nome;
        this.razza = razza;
    }

    abbaia() {
        console.log("Bau bau!");
    }
}

// Creazione di un'istanza
let mioCane = new Cane("Fido", "Labrador");
mioCane.abbaia(); // Output: Bau bau!
```

## 2. Oggetti in Javascript

Gli oggetti sono il cuore della programmazione in Javascript. Possiamo pensare a un oggetto come a una sorta di contenitore che raccoglie informazioni e funzionalità correlate. Immagina di avere una scatola etichettata "gatto" - all'interno di questa scatola, potresti trovare tutte le cose che descrivono e fanno parte di un gatto.

### 2.1 Creazione di oggetti letterali

In Javascript, il modo più semplice per creare un oggetto è usando la notazione letterale. È come se stessimo scrivendo una ricetta rapida per il nostro oggetto. Vediamo un esempio:

```javascript
let mioGatto = {
    nome: "Whiskers",
    età: 3,
    colore: "tigrato"
};
```

In questo esempio, abbiamo creato un oggetto chiamato `mioGatto`. All'interno delle parentesi graffe, abbiamo definito alcune proprietà del gatto: il suo nome, la sua età e il suo colore. È come se stessimo compilando una scheda d'identità per il nostro amico felino!

### 2.2 Proprietà e metodi

Le proprietà sono le caratteristiche del nostro oggetto, come abbiamo visto nell'esempio precedente. Ma gli oggetti possono fare anche delle azioni, e queste azioni sono rappresentate dai metodi. Un metodo è semplicemente una funzione associata all'oggetto.

Aggiungiamo un metodo al nostro gatto:

```javascript
let mioGatto = {
    nome: "Whiskers",
    età: 3,
    colore: "tigrato",
    miagola: function() {
        console.log("Miao miao!");
    }
};
```

Ora il nostro gatto può miagolare! Abbiamo aggiunto un metodo chiamato `miagola` che, quando viene chiamato, farà "parlare" il nostro gatto.

### 2.3 Accesso alle proprietà e ai metodi

Per accedere alle proprietà o ai metodi di un oggetto, usiamo la notazione con il punto. È come se stessimo chiedendo all'oggetto di darci un'informazione o di fare qualcosa. Vediamo come funziona:

```javascript
console.log(mioGatto.nome);  // Stamperà: Whiskers
console.log(mioGatto.età);   // Stamperà: 3

mioGatto.miagola();  // Stamperà: Miao miao!
```

Possiamo anche modificare le proprietà di un oggetto in questo modo:

```javascript
mioGatto.età = 4;  // Il gatto ha festeggiato il compleanno!
console.log(mioGatto.età);  // Stamperà: 4
```

C'è anche un altro modo per accedere alle proprietà di un oggetto, usando le parentesi quadre. Questo metodo è particolarmente utile quando il nome della proprietà è memorizzato in una variabile o quando il nome contiene spazi o caratteri speciali:

```javascript
let proprietà = "colore";
console.log(mioGatto[proprietà]);  // Stamperà: tigrato

mioGatto["data di nascita"] = "1 Gennaio 2020";
console.log(mioGatto["data di nascita"]);  // Stamperà: 1 Gennaio 2020
```

## 3. Classi in Javascript

Abbiamo visto come creare oggetti in Javascript, ma cosa succede se vogliamo creare molti oggetti simili? È qui che entrano in gioco le classi. Pensate a una classe come a un progetto o uno stampo per creare oggetti. Se gli oggetti fossero biscotti, la classe sarebbe la forma per i biscotti!

### 3.1 Introduzione alle classi in ES6+

Javascript ha introdotto le classi con ES6 (ECMAScript 2015), rendendo più facile e intuitivo creare oggetti con strutture simili. Le classi in Javascript sono in realtà una "sintassi zuccherata" sopra il sistema di prototipi esistente, ma non preoccupatevi di questo per ora - le classi ci permettono di scrivere codice più pulito e comprensibile.

### 3.2 Dichiarazione di una classe

Dichiariamo una classe per il nostro amico felino:

```javascript
class Gatto {
    constructor(nome, età, colore) {
        this.nome = nome;
        this.età = età;
        this.colore = colore;
    }

    miagola() {
        console.log("Miao miao!");
    }
}
```

In questo esempio, abbiamo creato una classe `Gatto`. La classe ha un metodo speciale chiamato `constructor` che viene chiamato quando creiamo un nuovo gatto. Il costruttore imposta le proprietà iniziali del gatto. Abbiamo anche aggiunto un metodo `miagola`, proprio come avevamo fatto con l'oggetto letterale.

### 3.3 Il costruttore

Il costruttore è come il "momento della nascita" per i nostri oggetti gatto. È una funzione speciale che viene chiamata automaticamente quando creiamo un nuovo gatto. Nel costruttore, usiamo la parola chiave `this` per riferirci al gatto che stiamo creando.

Quando scriviamo `this.nome = nome`, stiamo dicendo "prendi il nome che mi è stato dato e assegnalo come proprietà di questo nuovo gatto".

### 3.4 Metodi di istanza

I metodi di istanza sono funzioni che ogni gatto creato dalla nostra classe potrà eseguire. Nel nostro esempio, `miagola()` è un metodo di istanza. Ogni gatto che creiamo avrà la sua propria copia di questo metodo.

Ora, vediamo come usare questa classe per creare dei gatti:

```javascript
let whiskers = new Gatto("Whiskers", 3, "tigrato");
let luna = new Gatto("Luna", 2, "bianco");

console.log(whiskers.nome);  // Stamperà: Whiskers
console.log(luna.età);       // Stamperà: 2

whiskers.miagola();  // Stamperà: Miao miao!
luna.miagola();      // Stamperà: Miao miao!
```

In questo esempio, abbiamo creato due gatti diversi usando la nostra classe `Gatto`. Usiamo la parola chiave `new` per dire a Javascript di creare un nuovo oggetto basato sulla nostra classe. Passiamo i valori per nome, età e colore al costruttore.

Possiamo anche aggiungere altri metodi alla nostra classe. Per esempio, potremmo aggiungere un metodo per far invecchiare il nostro gatto:

```javascript
class Gatto {
    // ... (costruttore e metodo miagola come prima)

    compleanno() {
        this.età += 1;
        console.log(`${this.nome} ora ha ${this.età} anni!`);
    }
}

let whiskers = new Gatto("Whiskers", 3, "tigrato");
whiskers.compleanno();  // Stamperà: Whiskers ora ha 4 anni!
```

Le classi ci permettono di organizzare il nostro codice in modo più strutturato e di creare molti oggetti simili in modo efficiente. Sono un pilastro fondamentale della programmazione orientata agli oggetti in Javascript moderno.

## 4. Incapsulamento

Immaginate di avere una scatola con un lucchetto. All'interno della scatola ci sono oggetti preziosi, e solo voi avete la chiave per aprirla. Questo è essenzialmente il concetto di incapsulamento nella programmazione orientata agli oggetti. L'incapsulamento ci permette di nascondere i dettagli interni di un oggetto e di controllare come il mondo esterno può interagire con esso.

### 4.1 Concetto di incapsulamento

L'incapsulamento è uno dei principi fondamentali della programmazione orientata agli oggetti. Consiste nel raggruppare i dati (proprietà) e i metodi che operano su quei dati all'interno di un'unica unità o oggetto. Inoltre, l'incapsulamento ci permette di controllare l'accesso a questi dati, decidendo quali parti possono essere viste o modificate dall'esterno e quali no.

Torniamo al nostro esempio del gatto. Potremmo voler proteggere alcune informazioni sul gatto, come il suo numero di microchip, e permettere di modificare altre informazioni solo in modi specifici.

### 4.2 Proprietà private in Javascript (ES2022+)

Javascript ha recentemente introdotto il concetto di campi privati nelle classi, rendendoli accessibili solo all'interno della classe stessa. Questi campi sono preceduti dal simbolo #. Vediamo come potremmo usarli nella nostra classe Gatto:

```javascript
class Gatto {
    #microchip;

    constructor(nome, età, microchip) {
        this.nome = nome;
        this.età = età;
        this.#microchip = microchip;
    }

    getMicrochip() {
        return this.#microchip;
    }

    miagola() {
        console.log("Miao miao!");
    }
}

let luna = new Gatto("Luna", 2, "ABC123");
console.log(luna.nome);  // Funziona: Luna
console.log(luna.#microchip);  // Errore! Non possiamo accedere direttamente a #microchip
console.log(luna.getMicrochip());  // Funziona: ABC123
```

In questo esempio, #microchip è una proprietà privata. Non possiamo accedervi direttamente dall'esterno della classe, ma possiamo creare un metodo (getMicrochip) per leggere il suo valore quando necessario.

### 4.3 Metodi getter e setter

I metodi getter e setter sono un modo elegante per controllare l'accesso e la modifica delle proprietà di un oggetto. Sono come dei "portieri" che controllano chi entra e chi esce. Vediamo come potremmo usarli per la proprietà età del nostro gatto:

```javascript
class Gatto {
    #età;

    constructor(nome, età) {
        this.nome = nome;
        this.#età = età;
    }

    get età() {
        return this.#età;
    }

    set età(nuovaEtà) {
        if (nuovaEtà > 0) {
            this.#età = nuovaEtà;
        } else {
            console.log("L'età deve essere un numero positivo");
        }
    }

    compleanno() {
        this.età += 1;
        console.log(`${this.nome} ora ha ${this.età} anni!`);
    }
}

let whiskers = new Gatto("Whiskers", 3);
console.log(whiskers.età);  // Usa il getter: 3
whiskers.età = 4;  // Usa il setter
console.log(whiskers.età);  // 4
whiskers.età = -1;  // Usa il setter, ma non cambia l'età
console.log(whiskers.età);  // Ancora 4
whiskers.compleanno();  // Whiskers ora ha 5 anni!
```

In questo esempio, abbiamo reso la proprietà età privata (#età) e abbiamo creato un getter e un setter per controllarla. Il getter ci permette di leggere l'età, mentre il setter ci permette di cambiarla, ma solo se il nuovo valore è positivo. Questo ci dà un controllo molto più fine su come la proprietà può essere modificata.

L'incapsulamento ci aiuta a mantenere il nostro codice più organizzato e sicuro. Ci permette di nascondere i dettagli di implementazione che non devono essere accessibili dall'esterno e di controllare come le proprietà dei nostri oggetti possono essere lette o modificate. Questo rende il nostro codice più robusto e meno soggetto a errori, perché possiamo assicurarci che i nostri oggetti siano sempre in uno stato valido.

Nel prossimo capitolo, vedremo come l'incapsulamento si lega al concetto di information hiding, che ci aiuterà a creare interfacce ancora più pulite e facili da usare per i nostri oggetti!

## 5. Information Hiding

Immaginate di essere in un ristorante. Ordinate il vostro piatto preferito e, dopo un po', il cameriere ve lo porta, perfettamente preparato. Non avete bisogno di sapere esattamente come lo chef l'ha cucinato, quali utensili ha usato o come è organizzata la cucina. Tutto ciò che vi interessa è il risultato finale: un piatto delizioso. Questo è essenzialmente il concetto di information hiding nella programmazione.

### 5.1 Concetto di information hiding

L'information hiding, o "nascondere le informazioni", è un principio della programmazione orientata agli oggetti strettamente legato all'incapsulamento. Mentre l'incapsulamento si concentra sul raggruppamento di dati e metodi correlati, l'information hiding si concentra sul nascondere i dettagli interni di implementazione di un oggetto e fornire solo un'interfaccia pubblica per interagire con esso.

L'idea è di mostrare solo ciò che è necessario e nascondere tutto il resto. Questo rende il nostro codice più facile da usare, più facile da mantenere e più resistente ai cambiamenti.

### 5.2 Implementazione in Javascript

In Javascript, possiamo implementare l'information hiding usando una combinazione di proprietà private, metodi privati e un'interfaccia pubblica ben definita. Vediamo come potremmo applicare questo concetto alla nostra classe Gatto:

```javascript
class Gatto {
    #nome;
    #età;
    #livelloFame;

    constructor(nome, età) {
        this.#nome = nome;
        this.#età = età;
        this.#livelloFame = 5; // Su una scala da 0 a 10
    }

    get nome() {
        return this.#nome;
    }

    get età() {
        return this.#età;
    }

    #aumentaFame() {
        if (this.#livelloFame < 10) {
            this.#livelloFame++;
        }
    }

    #diminuisciFame() {
        if (this.#livelloFame > 0) {
            this.#livelloFame--;
        }
    }

    miagola() {
        console.log(`${this.#nome} dice: Miao!`);
        this.#aumentaFame();
    }

    mangia() {
        console.log(`${this.#nome} sta mangiando.`);
        this.#diminuisciFame();
    }

    statoFame() {
        let stato;
        if (this.#livelloFame <= 3) stato = "affamato";
        else if (this.#livelloFame <= 7) stato = "soddisfatto";
        else stato = "molto sazio";
        
        console.log(`${this.#nome} è ${stato}.`);
    }
}

let luna = new Gatto("Luna", 2);
luna.miagola();  // Luna dice: Miao!
luna.mangia();   // Luna sta mangiando.
luna.statoFame();  // Luna è soddisfatta.
```

In questo esempio, abbiamo nascosto molti dettagli interni della nostra classe Gatto:

1. Le proprietà #nome, #età e #livelloFame sono private. Non possiamo accedervi direttamente dall'esterno della classe.

2. I metodi #aumentaFame() e #diminuisciFame() sono privati. Sono usati internamente dalla classe, ma non sono accessibili dall'esterno.

3. Forniamo un'interfaccia pubblica semplice con i metodi miagola(), mangia() e statoFame(). Questi metodi nascondono la complessità interna della gestione del livello di fame.

L'utente della classe non ha bisogno di sapere come viene gestito il livello di fame internamente. Tutto ciò che deve sapere è che può far miagolare il gatto, dargli da mangiare e controllare il suo stato di fame. Questo è l'essenza dell'information hiding.

### 5.3 Symbol per proprietà private (pre-ES2022)

Prima dell'introduzione delle proprietà private con #, Javascript utilizzava i Symbol per creare proprietà "semi-private". Anche se non sono completamente privati, i Symbol offrono un modo per creare proprietà uniche che non sono facilmente accessibili dall'esterno. Ecco come potremmo usarli:

```javascript
const nome = Symbol('nome');
const età = Symbol('età');

class Gatto {
    constructor(n, e) {
        this[nome] = n;
        this[età] = e;
    }

    descriviti() {
        console.log(`Sono ${this[nome]} e ho ${this[età]} anni.`);
    }
}

let whiskers = new Gatto("Whiskers", 3);
whiskers.descriviti();  // Sono Whiskers e ho 3 anni.
console.log(whiskers[nome]);  // undefined (non possiamo accedere direttamente al Symbol)
```

Anche se i Symbol non offrono una vera privacy come le proprietà private con #, sono ancora utili in molte situazioni e sono supportati in versioni più vecchie di Javascript.

L'information hiding ci aiuta a creare codice più pulito, più facile da usare e più facile da mantenere. Nascondendo i dettagli interni e fornendo un'interfaccia pubblica ben definita, possiamo creare oggetti che sono più facili da capire e da usare correttamente. Questo ci permette di modificare l'implementazione interna senza influenzare il codice che usa i nostri oggetti, rendendo il nostro software più flessibile e resistente ai cambiamenti.

## 6. Ereditarietà

Immaginate una famiglia. I figli ereditano alcune caratteristiche dai genitori: potrebbero avere gli occhi della mamma o il naso del papà. Allo stesso tempo, hanno le loro caratteristiche uniche. Nell'ambito della programmazione, l'ereditarietà funziona in modo simile. Ci permette di creare nuove classi basate su classi esistenti, ereditando le loro caratteristiche e aggiungendone di nuove.

### 6.1 Concetto di ereditarietà

L'ereditarietà è un principio fondamentale della programmazione orientata agli oggetti che ci permette di definire una nuova classe basata su una classe esistente. La nuova classe (chiamata classe figlia o sottoclasse) eredita proprietà e metodi dalla classe esistente (chiamata classe genitore o superclasse). Questo ci permette di riutilizzare il codice e creare una gerarchia di classi.

### 6.2 Estensione di classi in Javascript

In Javascript, usiamo la parola chiave `extends` per creare una classe che eredita da un'altra. Vediamo come potremmo usare l'ereditarietà con i nostri gatti:

```javascript
class Animale {
    constructor(nome) {
        this.nome = nome;
    }

    mangia() {
        console.log(`${this.nome} sta mangiando.`);
    }

    dorme() {
        console.log(`${this.nome} sta dormendo.`);
    }
}

class Gatto extends Animale {
    constructor(nome, razza) {
        super(nome);  // Chiama il costruttore della classe genitore
        this.razza = razza;
    }

    miagola() {
        console.log(`${this.nome} fa miao!`);
    }
}

let luna = new Gatto("Luna", "Siamese");
luna.mangia();   // Luna sta mangiando.
luna.dorme();    // Luna sta dormendo.
luna.miagola();  // Luna fa miao!
console.log(luna.razza);  // Siamese
```

In questo esempio, abbiamo una classe base `Animale` con alcune proprietà e metodi comuni a tutti gli animali. Poi abbiamo creato una classe `Gatto` che estende `Animale`. La classe `Gatto` eredita tutti i metodi di `Animale` (`mangia` e `dorme`), ma aggiunge anche un suo metodo specifico (`miagola`) e una nuova proprietà (`razza`).

### 6.3 La parola chiave `super`

Avete notato la parola `super` nel costruttore di `Gatto`? Questa è una parola chiave speciale che ci permette di chiamare il costruttore della classe genitore. È come dire "Ehi, genitore! Fai la tua parte prima che io faccia la mia".

Possiamo usare `super` anche per chiamare metodi della classe genitore. Per esempio:

```javascript
class Gatto extends Animale {
    // ... altri metodi ...

    mangia() {
        super.mangia();  // Chiama il metodo mangia di Animale
        console.log(`${this.nome} fa le fusa di contentezza.`);
    }
}

luna.mangia();
// Output:
// Luna sta mangiando.
// Luna fa le fusa di contentezza.
```

In questo caso, abbiamo "esteso" il comportamento del metodo `mangia` aggiungendo un'azione specifica del gatto dopo aver chiamato il metodo della classe genitore.

### 6.4 Overriding di metodi

A volte, potremmo voler cambiare completamente il comportamento di un metodo ereditato. Questo si chiama "overriding" o sovrascrittura. Ecco un esempio:

```javascript
class Pesce extends Animale {
    dorme() {
        console.log(`${this.nome} riposa con gli occhi aperti.`);
    }
}

let nemo = new Pesce("Nemo");
nemo.dorme();  // Nemo riposa con gli occhi aperti.
```

In questo caso, abbiamo completamente sostituito il metodo `dorme` per la classe `Pesce`, perché i pesci dormono in modo diverso dagli altri animali.

L'ereditarietà è un potente strumento che ci permette di organizzare il nostro codice in modo logico e riutilizzabile. Ci consente di creare gerarchie di classi che riflettono le relazioni nel mondo reale, rendendo il nostro codice più intuitivo e facile da gestire.

Tuttavia, è importante usare l'ereditarietà con saggezza. A volte, una gerarchia di classi troppo profonda può rendere il codice difficile da capire e mantenere. Nel prossimo capitolo, esploreremo il concetto di polimorfismo, che ci darà ancora più flessibilità nel lavorare con oggetti di classi diverse!

## 7. Polimorfismo

Immaginate di avere un telecomando universale. Con lo stesso pulsante "accendi", potete accendere la TV, la radio o il condizionatore. Ogni dispositivo risponde allo stesso comando, ma in modo diverso. Questo è essenzialmente il concetto di polimorfismo nella programmazione: la capacità di oggetti di classi diverse di rispondere allo stesso messaggio in modi diversi.

### 7.1 Concetto di polimorfismo

Il termine "polimorfismo" deriva dal greco e significa "molte forme". Nella programmazione orientata agli oggetti, il polimorfismo ci permette di utilizzare un'interfaccia comune per tipi (classi) diversi. Questo rende il nostro codice più flessibile e più facile da estendere.

### 7.2 Implementazione del polimorfismo in Javascript

In Javascript, il polimorfismo si manifesta principalmente in due modi: attraverso l'ereditarietà (che abbiamo visto nel capitolo precedente) e attraverso le interfacce (che in Javascript sono più un concetto che una struttura formale del linguaggio).

Vediamo un esempio di polimorfismo basato sull'ereditarietà, espandendo il nostro esempio di animali:

```javascript
class Animale {
    constructor(nome) {
        this.nome = nome;
    }

    faiVerso() {
        console.log("L'animale fa un verso");
    }
}

class Gatto extends Animale {
    faiVerso() {
        console.log(`${this.nome} fa miao!`);
    }
}

class Cane extends Animale {
    faiVerso() {
        console.log(`${this.nome} fa bau!`);
    }
}

class Mucca extends Animale {
    faiVerso() {
        console.log(`${this.nome} fa muu!`);
    }
}

// Funzione che utilizza il polimorfismo
function faiParlareAnimale(animale) {
    animale.faiVerso();
}

let luna = new Gatto("Luna");
let fido = new Cane("Fido");
let bella = new Mucca("Bella");

faiParlareAnimale(luna);  // Luna fa miao!
faiParlareAnimale(fido);  // Fido fa bau!
faiParlareAnimale(bella); // Bella fa muu!
```

In questo esempio, abbiamo una classe base `Animale` con un metodo `faiVerso()`. Ogni classe derivata (`Gatto`, `Cane`, `Mucca`) sovrascrive questo metodo con la propria implementazione specifica.

La funzione `faiParlareAnimale()` è un esempio perfetto di polimorfismo in azione. Questa funzione accetta un oggetto di tipo `Animale` (o qualsiasi classe che estende `Animale`) e chiama il metodo `faiVerso()`. Non sa e non ha bisogno di sapere con quale tipo specifico di animale sta lavorando. Semplicemente chiama il metodo `faiVerso()`, e l'oggetto risponde nel modo appropriato per la sua classe.

Questo è potente perché ci permette di aggiungere nuovi tipi di animali senza dover modificare la funzione `faiParlareAnimale()`. Se domani volessimo aggiungere una classe `Pecora`, dovremmo solo assicurarci che abbia un metodo `faiVerso()`, e funzionerebbe immediatamente con il nostro codice esistente.

Ecco un altro esempio che mostra come il polimorfismo possa rendere il nostro codice più flessibile:

```javascript
class Forma {
    area() {
        return 0;
    }
}

class Rettangolo extends Forma {
    constructor(larghezza, altezza) {
        super();
        this.larghezza = larghezza;
        this.altezza = altezza;
    }

    area() {
        return this.larghezza * this.altezza;
    }
}

class Cerchio extends Forma {
    constructor(raggio) {
        super();
        this.raggio = raggio;
    }

    area() {
        return Math.PI * this.raggio * this.raggio;
    }
}

function calcolaAreaTotale(forme) {
    return forme.reduce((totale, forma) => totale + forma.area(), 0);
}

let rettangolo = new Rettangolo(5, 3);
let cerchio = new Cerchio(2);

console.log(calcolaAreaTotale([rettangolo, cerchio]));
// Output: 27.566370614359172 (15 + 12.566370614359172)
```

In questo esempio, la funzione `calcolaAreaTotale()` può lavorare con qualsiasi array di oggetti che hanno un metodo `area()`, indipendentemente dalla loro classe specifica. Questo è il polimorfismo in azione.

Il polimorfismo ci permette di scrivere codice più generico e riutilizzabile. Invece di scrivere funzioni separate per ogni tipo di oggetto, possiamo scrivere una singola funzione che lavora con un'interfaccia comune. Questo rende il nostro codice più flessibile, più facile da mantenere e più facile da estendere.

## 8. Composizione vs Ereditarietà

Immaginate di voler costruire una casa. Potreste farlo in due modi: potreste partire da una casa esistente e modificarla (questo sarebbe come l'ereditarietà), oppure potreste costruire la vostra casa da zero, utilizzando mattoni, travi e altri componenti (questo sarebbe come la composizione). Entrambi gli approcci hanno i loro vantaggi, e in programmazione, abbiamo una scelta simile tra ereditarietà e composizione.

### 8.1 Differenze tra composizione ed ereditarietà

L'ereditarietà, come abbiamo visto, ci permette di creare nuove classi basate su classi esistenti. È come dire "un gatto è un tipo di animale". La composizione, d'altra parte, ci permette di costruire oggetti complessi combinando oggetti più semplici. È come dire "un'auto ha un motore".

Mentre l'ereditarietà crea una relazione "è un", la composizione crea una relazione "ha un". Vediamo un esempio per chiarire questa differenza:

```javascript
// Approccio con ereditarietà
class Veicolo {
    constructor(velocitàMassima) {
        this.velocitàMassima = velocitàMassima;
    }

    muovi() {
        console.log(`Mi muovo a una velocità massima di ${this.velocitàMassima} km/h`);
    }
}

class Auto extends Veicolo {
    constructor(velocitàMassima, numeroPosti) {
        super(velocitàMassima);
        this.numeroPosti = numeroPosti;
    }
}

// Approccio con composizione
class Motore {
    constructor(potenza) {
        this.potenza = potenza;
    }

    avvia() {
        console.log(`Motore avviato con potenza ${this.potenza} CV`);
    }
}

class AutoComposta {
    constructor(motore, numeroPosti) {
        this.motore = motore;
        this.numeroPosti = numeroPosti;
    }

    avvia() {
        this.motore.avvia();
        console.log(`Auto avviata con ${this.numeroPosti} posti`);
    }
}

// Uso
let autoEreditarietà = new Auto(200, 5);
autoEreditarietà.muovi();  // Mi muovo a una velocità massima di 200 km/h

let motore = new Motore(150);
let autoComposizione = new AutoComposta(motore, 5);
autoComposizione.avvia();  
// Motore avviato con potenza 150 CV
// Auto avviata con 5 posti
```

In questo esempio, l'approccio con ereditarietà crea una relazione rigida tra `Veicolo` e `Auto`. L'approccio con composizione, invece, ci permette di costruire un'`AutoComposta` utilizzando un oggetto `Motore` separato.

### 8.2 Quando usare la composizione

La composizione è spesso preferita all'ereditarietà perché offre maggiore flessibilità. Ecco alcuni scenari in cui la composizione potrebbe essere la scelta migliore:

1. Quando volete combinare funzionalità da più sorgenti. Ad esempio, un'auto potrebbe avere un motore, un sistema di navigazione e un sistema audio, tutti oggetti separati.

2. Quando volete cambiare il comportamento a runtime. Con la composizione, potete facilmente sostituire un componente con un altro.

3. Quando la relazione tra le classi non è veramente "è un". Ad esempio, un'anatra può nuotare, ma non è corretto dire che "un'anatra è un nuotatore". In questo caso, potremmo usare la composizione per aggiungere la capacità di nuotare.

### 8.3 Implementazione della composizione in Javascript

Vediamo un esempio più elaborato di composizione:

```javascript
class SistemaDiNavigazione {
    navigate(destinazione) {
        console.log(`Navigando verso ${destinazione}`);
    }
}

class SistemaAudio {
    riproduce(canzone) {
        console.log(`Riproducendo ${canzone}`);
    }
}

class Auto {
    constructor(motore, navigazione, audio) {
        this.motore = motore;
        this.navigazione = navigazione;
        this.audio = audio;
    }

    avvia() {
        this.motore.avvia();
    }

    navigaVerso(destinazione) {
        this.navigazione.navigate(destinazione);
    }

    riproduciMusica(canzone) {
        this.audio.riproduce(canzone);
    }
}

let miaAuto = new Auto(
    new Motore(200),
    new SistemaDiNavigazione(),
    new SistemaAudio()
);

miaAuto.avvia();  // Motore avviato con potenza 200 CV
miaAuto.navigaVerso("Roma");  // Navigando verso Roma
miaAuto.riproduciMusica("Highway to Hell");  // Riproducendo Highway to Hell
```

In questo esempio, l'`Auto` è composta da diversi componenti indipendenti. Questo approccio offre diversi vantaggi:

1. Flessibilità: Possiamo facilmente aggiungere o rimuovere componenti senza influenzare il resto del sistema.
2. Riusabilità: Possiamo riutilizzare questi componenti in altri contesti. Ad esempio, potremmo usare lo stesso `SistemaAudio` in una classe `CasaIntelligente`.
3. Testabilità: È più facile testare componenti più piccoli e indipendenti.

Ricordate, non c'è una regola fissa su quando usare l'ereditarietà o la composizione. Spesso, la scelta migliore dipende dal contesto specifico del vostro problema. Una buona regola pratica è "componi quando puoi, eredita quando devi".

## 9. Prototipi in Javascript

Immaginate di essere in una grande famiglia. Quando avete bisogno di qualcosa, prima controllate se ce l'avete voi. Se non ce l'avete, chiedete a vostra madre. Se neanche lei ce l'ha, chiedete a vostra nonna. Questo processo continua finché non trovate ciò che cercate o arrivate al capostipite della famiglia che non ha nessuno a cui chiedere. Questo è essenzialmente il modo in cui funzionano i prototipi in Javascript!

### 9.1 Il sistema dei prototipi

Javascript è un linguaggio basato sui prototipi. Questo significa che l'ereditarietà in Javascript è implementata attraverso oggetti che fanno riferimento ad altri oggetti, chiamati prototipi. Ogni oggetto in Javascript ha un collegamento interno ad un altro oggetto, il suo prototipo. Quando cerchiamo una proprietà su un oggetto, se non la troviamo, Javascript la cerca nel prototipo dell'oggetto, poi nel prototipo del prototipo, e così via, fino a raggiungere la fine della catena dei prototipi.

Vediamo un esempio semplice:

```javascript
let animale = {
    mangia: function() {
        console.log("L'animale sta mangiando");
    }
};

let gatto = Object.create(animale);
gatto.miagola = function() {
    console.log("Miao!");
};

gatto.miagola();  // Miao!
gatto.mangia();   // L'animale sta mangiando
```

In questo esempio, `gatto` è un oggetto che ha `animale` come suo prototipo. Quando chiamiamo `gatto.mangia()`, Javascript prima cerca la funzione `mangia` in `gatto`. Non trovandola, la cerca nel prototipo di `gatto`, che è `animale`, e la trova lì.

### 9.2 Catena dei prototipi

La catena dei prototipi può essere più lunga di un solo livello. Ogni oggetto in Javascript ha un prototipo, tranne l'oggetto radice `Object.prototype`, che è il capostipite di tutti gli oggetti.

Vediamo un esempio più complesso:

```javascript
let animale = {
    respira: function() {
        console.log("L'animale sta respirando");
    }
};

let mammifero = Object.create(animale);
mammifero.allatta = function() {
    console.log("Il mammifero sta allattando");
};

let gatto = Object.create(mammifero);
gatto.miagola = function() {
    console.log("Miao!");
};

gatto.miagola();  // Miao!
gatto.allatta();  // Il mammifero sta allattando
gatto.respira();  // L'animale sta respirando
```

In questo esempio, abbiamo una catena di prototipi: `gatto` -> `mammifero` -> `animale`. Quando chiamiamo `gatto.respira()`, Javascript cerca la funzione `respira` prima in `gatto`, poi in `mammifero`, e infine la trova in `animale`.

### 9.3 Ereditarietà basata sui prototipi

L'ereditarietà in Javascript è implementata attraverso questa catena di prototipi. Quando definiamo una classe in Javascript (usando la sintassi delle classi introdotta in ES6), dietro le quinte Javascript sta ancora usando i prototipi.

Vediamo come funziona l'ereditarietà con le classi:

```javascript
class Animale {
    constructor(nome) {
        this.nome = nome;
    }

    respira() {
        console.log(`${this.nome} sta respirando`);
    }
}

class Gatto extends Animale {
    constructor(nome) {
        super(nome);
    }

    miagola() {
        console.log(`${this.nome} fa miao!`);
    }
}

let luna = new Gatto("Luna");
luna.miagola();  // Luna fa miao!
luna.respira();  // Luna sta respirando
```

Dietro le quinte, Javascript sta creando una catena di prototipi. Il prototipo di `luna` è `Gatto.prototype`, e il prototipo di `Gatto.prototype` è `Animale.prototype`.

Possiamo vedere questa catena di prototipi usando `Object.getPrototypeOf()`:

```javascript
console.log(Object.getPrototypeOf(luna) === Gatto.prototype);  // true
console.log(Object.getPrototypeOf(Gatto.prototype) === Animale.prototype);  // true
```

Comprendere i prototipi è fondamentale per capire come funziona Javascript sotto il cofano. Anche se nella programmazione quotidiana potreste non lavorare direttamente con i prototipi, questa conoscenza vi aiuterà a comprendere meglio il comportamento del vostro codice e a risolvere eventuali problemi.

Nel prossimo capitolo, esploreremo alcuni pattern di progettazione orientati agli oggetti comuni in Javascript. Questi pattern sfruttano spesso i concetti che abbiamo visto finora, inclusi i prototipi, per creare strutture di codice robuste e riutilizzabili!

## 10. Pattern di progettazione orientati agli oggetti in Javascript

Immaginate di essere un architetto. Quando progettate una casa, non partite sempre da zero. Avete un repertorio di soluzioni consolidate per problemi comuni: come progettare una cucina funzionale, come organizzare gli spazi, come gestire l'illuminazione. Allo stesso modo, nella programmazione orientata agli oggetti, abbiamo dei "progetti" collaudati per risolvere problemi ricorrenti. Questi sono i pattern di progettazione.

I pattern di progettazione sono soluzioni generali a problemi comuni nello sviluppo del software. Non sono codice pronto all'uso, ma piuttosto linee guida su come affrontare certi problemi. In questa sezione, esploreremo tre pattern di progettazione molto utilizzati in Javascript: Singleton, Factory e Observer.

### 10.1 Singleton

Il pattern Singleton garantisce che una classe abbia una sola istanza e fornisce un punto di accesso globale a questa istanza. È utile quando vogliamo avere un'unica copia di un oggetto in tutta la nostra applicazione.

Immaginate di avere un'applicazione con un unico database di configurazione. Non volete creare multiple istanze di questo database, ma volete assicurarvi che tutti i componenti dell'applicazione stiano accedendo alla stessa configurazione.

Ecco come potremmo implementare un Singleton in Javascript:

```javascript
class ConfigDatabase {
    constructor() {
        if (ConfigDatabase.instance) {
            return ConfigDatabase.instance;
        }
        this.config = {};
        ConfigDatabase.instance = this;
    }

    setConfig(key, value) {
        this.config[key] = value;
    }

    getConfig(key) {
        return this.config[key];
    }
}

// Uso
const config1 = new ConfigDatabase();
config1.setConfig('theme', 'dark');

const config2 = new ConfigDatabase();
console.log(config2.getConfig('theme'));  // Output: 'dark'

console.log(config1 === config2);  // Output: true
```

In questo esempio, non importa quante volte creiamo una nuova istanza di `ConfigDatabase`, otterremo sempre la stessa istanza. Questo ci assicura che tutte le parti della nostra applicazione stiano lavorando con la stessa configurazione.

### 10.2 Factory

Il pattern Factory ci fornisce un modo per creare oggetti senza specificare esattamente la classe dell'oggetto che verrà creato. È utile quando la creazione di un oggetto è complessa o quando la decisione su quale tipo di oggetto creare dipende da qualche condizione.

Immaginate di avere un'applicazione che lavora con diversi tipi di veicoli. A seconda dell'input dell'utente, potremmo dover creare un'auto, una moto o una bicicletta.

Ecco come potremmo implementare un Factory in Javascript:

```javascript
class Auto {
    guidare() {
        console.log("Sto guidando un'auto");
    }
}

class Moto {
    guidare() {
        console.log("Sto guidando una moto");
    }
}

class Bicicletta {
    guidare() {
        console.log("Sto pedalando una bicicletta");
    }
}

class VeicoloFactory {
    creaVeicolo(tipo) {
        switch(tipo) {
            case 'auto':
                return new Auto();
            case 'moto':
                return new Moto();
            case 'bicicletta':
                return new Bicicletta();
            default:
                throw new Error('Tipo di veicolo non supportato');
        }
    }
}

// Uso
const factory = new VeicoloFactory();
const auto = factory.creaVeicolo('auto');
const moto = factory.creaVeicolo('moto');

auto.guidare();  // Output: Sto guidando un'auto
moto.guidare();  // Output: Sto guidando una moto
```

In questo esempio, `VeicoloFactory` si occupa di creare l'oggetto appropriato basandosi sul tipo fornito. Il codice che usa la factory non deve preoccuparsi dei dettagli di come vengono creati i diversi tipi di veicoli.

### 10.3 Observer

Il pattern Observer definisce una dipendenza uno-a-molti tra oggetti, in modo che quando un oggetto cambia stato, tutti i suoi dipendenti vengono notificati e aggiornati automaticamente. È molto utile quando abbiamo un oggetto che deve comunicare cambiamenti a molti altri oggetti.

Immaginate un'app meteo dove molti componenti dell'interfaccia utente devono essere aggiornati quando cambiano i dati meteorologici.

Ecco come potremmo implementare un Observer in Javascript:

```javascript
class WeatherStation {
    constructor() {
        this.observers = [];
        this.temperature = 0;
    }

    addObserver(observer) {
        this.observers.push(observer);
    }

    removeObserver(observer) {
        const index = this.observers.indexOf(observer);
        if (index > -1) {
            this.observers.splice(index, 1);
        }
    }

    setTemperature(temp) {
        console.log('WeatherStation: nuova temperatura misurata: ' + temp);
        this.temperature = temp;
        this.notifyObservers();
    }

    notifyObservers() {
        for (let observer of this.observers) {
            observer.update(this.temperature);
        }
    }
}

class TemperatureDisplay {
    constructor(name) {
        this.name = name;
    }

    update(temperature) {
        console.log(`${this.name}: La temperatura è ${temperature}°C`);
    }
}

// Uso
const weatherStation = new WeatherStation();

const display1 = new TemperatureDisplay('Display 1');
const display2 = new TemperatureDisplay('Display 2');

weatherStation.addObserver(display1);
weatherStation.addObserver(display2);

weatherStation.setTemperature(25);
// Output:
// WeatherStation: nuova temperatura misurata: 25
// Display 1: La temperatura è 25°C
// Display 2: La temperatura è 25°C
```

In questo esempio, `WeatherStation` è l'oggetto osservato, e i `TemperatureDisplay` sono gli osservatori. Quando la temperatura cambia, tutti i display vengono automaticamente aggiornati.

Questi pattern di progettazione sono strumenti potenti nel vostro arsenale di sviluppatori. Vi aiutano a strutturare il vostro codice in modi che sono stati provati e testati da molti sviluppatori nel corso degli anni. Tuttavia, ricordate che non sono soluzioni universali. Usateli quando hanno senso per il vostro specifico problema, non forzateli in ogni situazione.

## 11. Best practices e convenzioni

Immaginate di entrare in una cucina ben organizzata. Ogni utensile ha il suo posto, gli ingredienti sono etichettati chiaramente, e c'è un sistema logico per tutto. Lavorare in una cucina del genere è un piacere, vero? Lo stesso vale per il codice ben scritto. Seguire le best practices e le convenzioni nella programmazione orientata agli oggetti in Javascript è come mantenere una cucina ben organizzata: rende il vostro codice più facile da leggere, capire e mantenere, sia per voi che per gli altri sviluppatori.

### 11.1 Naming conventions per classi e metodi

Una delle prime cose che noterete in un codice ben scritto sono i nomi significativi e coerenti. In Javascript, abbiamo alcune convenzioni che è bene seguire:

1. I nomi delle classi dovrebbero iniziare con una lettera maiuscola e usare il PascalCase. Ad esempio:

```javascript
class AutoElettica {}
class GestoreDatabase {}
class InterfacciaUtente {}
```

2. I nomi dei metodi e delle proprietà dovrebbero iniziare con una lettera minuscola e usare il camelCase. Ad esempio:

```javascript
class Auto {
    accelera() {}
    frena() {}
    get velocitàAttuale() {}
    set velocitàMassima(valore) {}
}
```

3. Le costanti dovrebbero essere in maiuscolo con underscore tra le parole:

```javascript
const VELOCITA_MASSIMA = 200;
const LIVELLO_BATTERIA_CRITICO = 10;
```

Usare nomi descrittivi è cruciale. Un nome dovrebbe dire chiaramente cosa fa una classe o un metodo. Confrontate questi due esempi:

```javascript
// Poco chiaro
class X {
    y() {}
}

// Chiaro e descrittivo
class GestoreFile {
    salvaFile() {}
}
```

### 11.2 Principi SOLID applicati a Javascript

I principi SOLID sono linee guida fondamentali nella programmazione orientata agli oggetti. Vediamo come possiamo applicarli in Javascript:

1. Single Responsibility Principle (Principio di Responsabilità Singola): Una classe dovrebbe avere una sola ragione per cambiare. In altre parole, una classe dovrebbe fare una cosa sola e farla bene.

```javascript
// Non ottimale: questa classe fa troppe cose
class Utente {
    constructor(nome) {
        this.nome = nome;
    }

    salvasuDatabase() {}
    inviaEmail() {}
    generaReport() {}
}

// Meglio: separiamo le responsabilità
class Utente {
    constructor(nome) {
        this.nome = nome;
    }
}

class UtenteDatabase {
    salvaUtente(utente) {}
}

class EmailService {
    inviaEmail(utente, messaggio) {}
}

class ReportGenerator {
    generaReport(utente) {}
}
```

2. Open/Closed Principle (Principio Aperto/Chiuso): Le entità software dovrebbero essere aperte per l'estensione, ma chiuse per la modifica.

```javascript
class Forma {
    area() {
        throw new Error("Il metodo area deve essere implementato");
    }
}

class Rettangolo extends Forma {
    constructor(larghezza, altezza) {
        super();
        this.larghezza = larghezza;
        this.altezza = altezza;
    }

    area() {
        return this.larghezza * this.altezza;
    }
}

class Cerchio extends Forma {
    constructor(raggio) {
        super();
        this.raggio = raggio;
    }

    area() {
        return Math.PI * this.raggio ** 2;
    }
}

function calcolaAreaTotale(forme) {
    return forme.reduce((somma, forma) => somma + forma.area(), 0);
}
```

In questo esempio, possiamo aggiungere nuove forme senza modificare la funzione `calcolaAreaTotale`.

3. Liskov Substitution Principle (Principio di Sostituzione di Liskov): Gli oggetti di una superclasse dovrebbero essere sostituibili con oggetti delle sue sottoclassi senza alterare la correttezza del programma.

```javascript
class Uccello {
    vola() {
        return "Sto volando";
    }
}

class Pinguino extends Uccello {
    vola() {
        throw new Error("I pinguini non possono volare");
    }
}

// Questo viola il principio di Liskov
function faiVolare(uccello) {
    return uccello.vola();
}

// Meglio: ridefiniamo la gerarchia
class Animale {
    muovi() {
        return "Mi sto muovendo";
    }
}

class UccelloVolante extends Animale {
    vola() {
        return "Sto volando";
    }
}

class Pinguino extends Animale {
    nuota() {
        return "Sto nuotando";
    }
}
```

4. Interface Segregation Principle (Principio di Segregazione dell'Interfaccia): Un client non dovrebbe essere forzato a dipendere da interfacce che non usa.

JavaScript non ha interfacce native, ma possiamo applicare questo principio usando classi astratte o semplicemente dividendo le nostre classi in parti più piccole e specifiche.

```javascript
// Non ottimale
class Stampante {
    stampa() {}
    scansiona() {}
    inviafax() {}
}

// Meglio
class Stampante {
    stampa() {}
}

class Scanner {
    scansiona() {}
}

class FaxMachine {
    inviafax() {}
}

class StampanteMultifunzione extends Stampante {
    scansiona() {}
    inviafax() {}
}
```

5. Dependency Inversion Principle (Principio di Inversione delle Dipendenze): I moduli di alto livello non dovrebbero dipendere da moduli di basso livello. Entrambi dovrebbero dipendere da astrazioni.

```javascript
// Non ottimale
class EmailService {
    inviaEmail(messaggio) {
        // logica per inviare email
    }
}

class Notificatore {
    constructor() {
        this.emailService = new EmailService();
    }

    inviaNotifica(messaggio) {
        this.emailService.inviaEmail(messaggio);
    }
}

// Meglio
class MessaggioService {
    invia(messaggio) {
        throw new Error("Il metodo invia deve essere implementato");
    }
}

class EmailService extends MessaggioService {
    invia(messaggio) {
        // logica per inviare email
    }
}

class SMSService extends MessaggioService {
    invia(messaggio) {
        // logica per inviare SMS
    }
}

class Notificatore {
    constructor(messaggioService) {
        this.messaggioService = messaggioService;
    }

    inviaNotifica(messaggio) {
        this.messaggioService.invia(messaggio);
    }
}

// Uso
const notificatoreEmail = new Notificatore(new EmailService());
const notificatoreSMS = new Notificatore(new SMSService());
```

Seguire queste best practices e convenzioni richiede un po' di pratica e riflessione, ma alla lunga rende il vostro codice molto più robusto, flessibile e facile da mantenere. Ricordate, scrivere codice non è solo farlo funzionare, ma farlo funzionare in modo che sia comprensibile e modificabile nel tempo.

## 12. Esercizi e progetti pratici

Ora che abbiamo esplorato i concetti fondamentali della programmazione orientata agli oggetti in Javascript, è tempo di mettere in pratica ciò che abbiamo imparato. Come si dice, la pratica rende perfetti! In questa sezione, affronteremo alcuni esercizi e progetti pratici che vi aiuteranno a consolidare la vostra comprensione e a sviluppare le vostre capacità di programmazione orientata agli oggetti.

### 12.1 Creazione di una semplice gerarchia di classi

Per il nostro primo esercizio, creeremo una semplice gerarchia di classi per un sistema di gestione di una biblioteca. Questo ci permetterà di mettere in pratica i concetti di ereditarietà e polimorfismo.

```javascript
class MediaItem {
    constructor(titolo, anno) {
        this.titolo = titolo;
        this.anno = anno;
        this.prestato = false;
    }

    presta() {
        if (this.prestato) {
            console.log(`${this.titolo} è già in prestito.`);
        } else {
            this.prestato = true;
            console.log(`${this.titolo} è stato prestato.`);
        }
    }

    restituisci() {
        if (this.prestato) {
            this.prestato = false;
            console.log(`${this.titolo} è stato restituito.`);
        } else {
            console.log(`${this.titolo} non era in prestito.`);
        }
    }

    mostraInfo() {
        console.log(`Titolo: ${this.titolo}, Anno: ${this.anno}, In prestito: ${this.prestato}`);
    }
}

class Libro extends MediaItem {
    constructor(titolo, anno, autore, numeroPagine) {
        super(titolo, anno);
        this.autore = autore;
        this.numeroPagine = numeroPagine;
    }

    mostraInfo() {
        super.mostraInfo();
        console.log(`Autore: ${this.autore}, Pagine: ${this.numeroPagine}`);
    }
}

class DVD extends MediaItem {
    constructor(titolo, anno, regista, durata) {
        super(titolo, anno);
        this.regista = regista;
        this.durata = durata;
    }

    mostraInfo() {
        super.mostraInfo();
        console.log(`Regista: ${this.regista}, Durata: ${this.durata} minuti`);
    }
}

// Uso
const libro1 = new Libro("Il Signore degli Anelli", 1954, "J.R.R. Tolkien", 1178);
const dvd1 = new DVD("Inception", 2010, "Christopher Nolan", 148);

libro1.mostraInfo();
libro1.presta();
libro1.presta();
libro1.restituisci();

dvd1.mostraInfo();
dvd1.presta();
dvd1.restituisci();
```

In questo esercizio, abbiamo creato una classe base `MediaItem` e due classi derivate `Libro` e `DVD`. Questo ci permette di gestire diversi tipi di media in modo uniforme, dimostrando i principi di ereditarietà e polimorfismo.

### 12.2 Implementazione di un sistema di gestione studenti

Per il nostro secondo esercizio, implementeremo un semplice sistema di gestione studenti. Questo ci permetterà di mettere in pratica l'incapsulamento e l'uso dei getter e setter.

```javascript
class Studente {
    #nome;
    #cognome;
    #voti;

    constructor(nome, cognome) {
        this.#nome = nome;
        this.#cognome = cognome;
        this.#voti = [];
    }

    get nomeCompleto() {
        return `${this.#nome} ${this.#cognome}`;
    }

    aggiungiVoto(voto) {
        if (voto >= 0 && voto <= 30) {
            this.#voti.push(voto);
        } else {
            console.log("Voto non valido. Deve essere compreso tra 0 e 30.");
        }
    }

    get mediaVoti() {
        if (this.#voti.length === 0) return 0;
        const somma = this.#voti.reduce((acc, voto) => acc + voto, 0);
        return somma / this.#voti.length;
    }

    mostraInfo() {
        console.log(`Studente: ${this.nomeCompleto}`);
        console.log(`Media voti: ${this.mediaVoti.toFixed(2)}`);
    }
}

class Corso {
    constructor(nome) {
        this.nome = nome;
        this.studenti = [];
    }

    aggiungiStudente(studente) {
        this.studenti.push(studente);
    }

    mostraInfoCorso() {
        console.log(`Corso: ${this.nome}`);
        console.log(`Numero di studenti: ${this.studenti.length}`);
        this.studenti.forEach(studente => studente.mostraInfo());
    }
}

// Uso
const studente1 = new Studente("Mario", "Rossi");
studente1.aggiungiVoto(28);
studente1.aggiungiVoto(30);
studente1.aggiungiVoto(26);

const studente2 = new Studente("Laura", "Bianchi");
studente2.aggiungiVoto(29);
studente2.aggiungiVoto(27);
studente2.aggiungiVoto(30);

const corso = new Corso("Programmazione Avanzata");
corso.aggiungiStudente(studente1);
corso.aggiungiStudente(studente2);

corso.mostraInfoCorso();
```

In questo esercizio, abbiamo creato una classe `Studente` che usa proprietà private (indicate dal simbolo #) per incapsulare i dati dello studente. Abbiamo anche implementato getter per accedere in modo controllato a questi dati. La classe `Corso` dimostra come possiamo lavorare con una collezione di oggetti `Studente`.

### 12.3 Sviluppo di un gioco semplice orientato agli oggetti

Per il nostro ultimo progetto, svilupperemo un semplice gioco di carte. Questo ci permetterà di mettere in pratica molti dei concetti che abbiamo imparato, inclusi l'uso di classi, l'incapsulamento, e la composizione.

```javascript
class Carta {
    constructor(seme, valore) {
        this.seme = seme;
        this.valore = valore;
    }

    toString() {
        return `${this.valore} di ${this.seme}`;
    }
}

class Mazzo {
    constructor() {
        this.carte = [];
        const semi = ['Cuori', 'Quadri', 'Fiori', 'Picche'];
        const valori = ['Asso', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'Jack', 'Regina', 'Re'];

        for (let seme of semi) {
            for (let valore of valori) {
                this.carte.push(new Carta(seme, valore));
            }
        }
    }

    mescola() {
        for (let i = this.carte.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [this.carte[i], this.carte[j]] = [this.carte[j], this.carte[i]];
        }
    }

    pescaCarta() {
        return this.carte.pop();
    }
}

class Giocatore {
    constructor(nome) {
        this.nome = nome;
        this.mano = [];
    }

    pescaCarta(mazzo) {
        const carta = mazzo.pescaCarta();
        this.mano.push(carta);
        return carta;
    }

    mostraMano() {
        console.log(`${this.nome} ha in mano:`);
        this.mano.forEach(carta => console.log(carta.toString()));
    }
}

class GiocoCarte {
    constructor() {
        this.mazzo = new Mazzo();
        this.giocatori = [];
    }

    aggiungiGiocatore(nome) {
        this.giocatori.push(new Giocatore(nome));
    }

    iniziaGioco(numeroCarte) {
        this.mazzo.mescola();
        for (let i = 0; i < numeroCarte; i++) {
            for (let giocatore of this.giocatori) {
                giocatore.pescaCarta(this.mazzo);
            }
        }
    }

    mostraManoDiTutti() {
        for (let giocatore of this.giocatori) {
            giocatore.mostraMano();
            console.log('--------------------');
        }
    }
}

// Uso del gioco
const gioco = new GiocoCarte();
gioco.aggiungiGiocatore("Alice");
gioco.aggiungiGiocatore("Bob");
gioco.iniziaGioco(5);
gioco.mostraManoDiTutti();
```

In questo progetto, abbiamo creato diverse classi (`Carta`, `Mazzo`, `Giocatore`, `GiocoCarte`) che lavorano insieme per implementare un semplice gioco di carte. Questo esempio dimostra l'uso della composizione (la classe `GiocoCarte` contiene un `Mazzo` e dei `Giocatore`), l'incapsulamento (ogni classe gestisce il proprio stato interno), e come diversi oggetti possono interagire tra loro in un sistema più complesso.

Questi esercizi e progetti vi danno l'opportunità di mettere in pratica i concetti che abbiamo discusso nei capitoli precedenti. Vi incoraggiamo a sperimentare con questi esempi: provate a estenderli, aggiungere nuove funzionalità, o persino a creare i vostri progetti basati su questi concetti. Ricordate, la programmazione è una competenza che si affina con la pratica, quindi più codice scrivete, migliori diventerete!
