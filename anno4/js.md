# Lezione 1: Introduzione a JavaScript e prime interazioni con la pagina web

## Cos'è JavaScript?
JavaScript è un linguaggio di programmazione che permette di rendere interattive le pagine web. Mentre l'HTML definisce il contenuto e il CSS definisce lo stile, JavaScript aggiunge il comportamento dinamico alle pagine web.

## Il Document Object Model (DOM)
Quando un browser carica una pagina web, crea una rappresentazione ad albero di tutti gli elementi HTML. Questa struttura è chiamata DOM (Document Object Model). JavaScript può interagire con questa struttura per:
- Modificare elementi HTML
- Modificare attributi HTML
- Modificare stili CSS
- Reagire a eventi
- Creare e rimuovere elementi

## Come includere JavaScript in una pagina HTML
È buona pratica inserire il codice JavaScript in un file separato con estensione `.js`. Ecco come collegarlo alla pagina HTML:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Prima lezione JavaScript</title>
</head>
<body>
    <h1 id="titolo">Benvenuti al corso di JavaScript!</h1>
    <p id="paragrafo">Questo paragrafo verrà modificato da JavaScript.</p>
    <button id="bottone">Cliccami!</button>

    <!-- Inserire lo script alla fine del body -->
    <script src="app.js"></script>
</body>
</html>
```

## Prime interazioni con il DOM
Vediamo come interagire con gli elementi della pagina utilizzando JavaScript:

```javascript
// app.js

// Selezionare un elemento tramite il suo ID
let titolo = document.getElementById('titolo');
let paragrafo = document.getElementById('paragrafo');
let bottone = document.getElementById('bottone');

// Modificare il contenuto di un elemento
titolo.innerHTML = 'Il mio primo script JavaScript!';

// Modificare il testo di un paragrafo quando si clicca un bottone
bottone.onclick = function() {
    paragrafo.innerHTML = 'Hai cliccato il bottone!';
}
```

## Le variabili in JavaScript
In JavaScript, le variabili sono contenitori per memorizzare dati. Esistono tre modi per dichiarare variabili:

```javascript
// Variabile che può essere modificata
let nome = 'Mario';

// Costante (non può essere modificata)
const piGreco = 3.14;

// Variabile con scope funzionale (meglio evitare)
var cognome = 'Rossi';  // sconsigliato nelle applicazioni moderne
```

### Regole per i nomi delle variabili:
- Devono iniziare con una lettera, $ o _
- Sono case-sensitive (nome ≠ Nome)
- Non possono usare parole riservate (come let, const, function)

## Input e Output base

### Console.log()
Utile per il debug e visualizzare valori durante lo sviluppo:
```javascript
let eta = 16;
console.log('La tua età è:', eta);
```

### Alert()
Mostra un popup con un messaggio:
```javascript
alert('Benvenuto al corso!');
```

## Esercizio pratico
Creiamo una pagina che permetta di:
1. Mostrare un messaggio di benvenuto
2. Cambiare il colore del testo al click di un bottone

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Esercizio 1</title>
</head>
<body>
    <h1 id="messaggioBenvenuto">Benvenuto!</h1>
    <button id="cambiaColore">Cambia colore</button>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
// Selezioniamo gli elementi
let messaggio = document.getElementById('messaggioBenvenuto');
let bottone = document.getElementById('cambiaColore');

// Aggiungiamo il comportamento al bottone
bottone.onclick = function() {
    messaggio.style.color = 'blue';  // Cambia il colore del testo
    messaggio.innerHTML = 'Il colore è cambiato!';  // Modifica il testo
}
```

## Esercizi proposti
1. Modifica l'esercizio precedente per far sì che il colore del testo cambi tra rosso e blu ad ogni click
2. Aggiungi un secondo bottone che, quando cliccato, cambi il testo del messaggio di benvenuto
3. Crea una pagina con tre paragrafi e un bottone che, quando cliccato, cambi il testo di tutti i paragrafi contemporaneamente

## Punti chiave della lezione
- JavaScript permette di rendere interattive le pagine web
- Il DOM è la rappresentazione degli elementi HTML della pagina
- `document.getElementById()` permette di selezionare elementi HTML
- Le variabili si dichiarano con `let` e `const`
- Gli eventi come `onclick` permettono di reagire alle azioni dell'utente

# Lezione 2: Variabili e operazioni di base

Nella lezione precedente abbiamo fatto una prima conoscenza con JavaScript e abbiamo visto come può interagire con la nostra pagina web. Oggi andremo più in profondità, esplorando i vari tipi di dati che possiamo utilizzare e come manipolarli. Sarà come imparare i mattoncini base con cui costruiremo poi strutture sempre più complesse!

## I tipi di dati in JavaScript

In JavaScript, ogni variabile che creiamo può contenere diversi tipi di dati. Immaginate questi tipi come contenitori diversi, ognuno progettato per un tipo specifico di informazione:

### 1. Numeri (Number)
I numeri in JavaScript possono essere interi o decimali:
```javascript
let eta = 16;                // numero intero
let altezza = 1.75;          // numero decimale
let temperaturaNegativa = -5; // anche i numeri negativi sono permessi
```

### 2. Testo (String)
Le stringhe sono sequenze di caratteri che mettiamo tra apici (singoli o doppi):
```javascript
let nome = "Mario";
let saluto = 'Ciao';
let frase = "L'apostrofo non è un problema se uso i doppi apici";
```

### 3. Valori booleani (Boolean)
I booleani sono semplici: possono essere solo vero o falso:
```javascript
let haCompiutoGliAnni = true;
let staStudiando = false;
```

## Operazioni con i dati

Ora che conosciamo i tipi di dati principali, vediamo come possiamo combinarli e manipolarli!

### Operazioni con i numeri
```javascript
let numero1 = 10;
let numero2 = 5;

let somma = numero1 + numero2;      // 15
let differenza = numero1 - numero2;  // 5
let prodotto = numero1 * numero2;    // 50
let divisione = numero1 / numero2;   // 2
let resto = numero1 % numero2;       // 0 (il resto della divisione)

// Possiamo anche incrementare o decrementare
numero1++;  // aumenta di 1
numero2--;  // diminuisce di 1
```

### Operazioni con le stringhe
Le stringhe hanno alcune particolarità interessanti. Possiamo unirle (concatenarle) usando il simbolo +:
```javascript
let nome = "Mario";
let cognome = "Rossi";
let nomeCompleto = nome + " " + cognome;  // "Mario Rossi"

// Un modo più moderno di concatenare le stringhe è usando i template literals:
let presentazione = `Mi chiamo ${nome} ${cognome} e ho ${eta} anni`;
```

## Conversione tra tipi di dati

A volte abbiamo bisogno di convertire un tipo di dato in un altro. JavaScript ci mette a disposizione alcuni strumenti:

```javascript
// Da stringa a numero
let numeroTestuale = "123";
let numeroVero = parseInt(numeroTestuale);    // 123 come numero
let numeroDecimale = parseFloat("123.45");    // 123.45 come numero

// Da numero a stringa
let numero = 123;
let numeroStringa = numero.toString();        // "123"
```

## Interazione con il DOM utilizzando le variabili

Vediamo come possiamo utilizzare questi concetti per interagire con la nostra pagina web:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Calcolatrice dell'età</title>
</head>
<body>
    <h1>Calcola quanti anni avrai nel 2030</h1>
    <input type="number" id="etaAttuale" placeholder="Inserisci la tua età">
    <button id="calcola">Calcola</button>
    <p id="risultato"></p>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let inputEta = document.getElementById('etaAttuale');
let bottoneCalcola = document.getElementById('calcola');
let paragrafoRisultato = document.getElementById('risultato');

bottoneCalcola.onclick = function() {
    // Prendiamo il valore dall'input e lo convertiamo in numero
    let etaAttuale = parseInt(inputEta.value);
    
    // Calcoliamo l'età nel 2030
    let etaFutura = etaAttuale + (2030 - 2024);
    
    // Creiamo un messaggio personalizzato
    let messaggio = `Nel 2030 avrai ${etaFutura} anni!`;
    
    // Mostriamo il risultato nella pagina
    paragrafoRisultato.innerHTML = messaggio;
    
    // Cambiamo il colore del testo in base all'età
    if (etaFutura >= 18) {
        paragrafoRisultato.style.color = 'green';
    } else {
        paragrafoRisultato.style.color = 'blue';
    }
}
```

## Gestire gli attributi degli elementi HTML

Oltre a modificare il contenuto e lo stile, possiamo anche modificare gli attributi degli elementi HTML:

```javascript
let immagine = document.getElementById('miaImmagine');
immagine.setAttribute('src', 'nuova-immagine.jpg');
immagine.setAttribute('alt', 'Nuova descrizione');

// Possiamo anche leggere gli attributi
let srcAttuale = immagine.getAttribute('src');
```

## Esercizio guidato: Mini Quiz

Creiamo insieme un semplice quiz che utilizza tutti i concetti che abbiamo visto:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Mini Quiz</title>
</head>
<body>
    <h1>Quiz di Matematica</h1>
    <p id="domanda">Quanto fa 7 x 8?</p>
    <input type="number" id="risposta" placeholder="Inserisci la tua risposta">
    <button id="verifica">Verifica</button>
    <p id="feedback"></p>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let inputRisposta = document.getElementById('risposta');
let bottoneVerifica = document.getElementById('verifica');
let paragrafoFeedback = document.getElementById('feedback');

bottoneVerifica.onclick = function() {
    let rispostaUtente = parseInt(inputRisposta.value);
    let rispostaCorretta = 7 * 8;
    
    if (rispostaUtente === rispostaCorretta) {
        paragrafoFeedback.innerHTML = "Bravo! La risposta è corretta! 🎉";
        paragrafoFeedback.style.color = "green";
    } else {
        paragrafoFeedback.innerHTML = "Mi dispiace, riprova! 😕";
        paragrafoFeedback.style.color = "red";
    }
}
```

## Esercizi per casa

1. **Convertitore di temperature**: Crea una pagina che converta la temperatura da Celsius a Fahrenheit (Formula: °F = °C × 9/5 + 32)

2. **Calcolatore di media**: Crea una pagina dove l'utente può inserire tre voti e il programma calcola la media

3. **Generatore di saluti**: Crea una pagina dove l'utente inserisce il suo nome e l'ora del giorno (mattina, pomeriggio, sera) e il programma genera un saluto appropriato

## Punti chiave della lezione
- I tipi di dati principali in JavaScript sono numeri, stringhe e booleani
- Possiamo convertire tra diversi tipi di dati quando necessario
- Le operazioni matematiche funzionano sui numeri
- Le stringhe possono essere concatenate con + o usando i template literals
- Possiamo leggere e modificare gli attributi degli elementi HTML


# Lezione 3: Strutture di controllo - La selezione

Nelle lezioni precedenti abbiamo imparato a memorizzare dati nelle variabili e a fare operazioni con essi. Ma un programma non è fatto solo di calcoli: deve anche prendere decisioni! Oggi impareremo come far "ragionare" il nostro codice usando le strutture di controllo.

## L'istruzione if-else

Immaginate di dover programmare un videogioco: il personaggio perde una vita se viene colpito da un nemico. In questo caso, il nostro programma deve "decidere" se il giocatore è stato colpito o no. In JavaScript, possiamo usare l'istruzione `if-else` per questi tipi di decisioni:

```javascript
let vitoRimaste = 3;
let colpito = true;

if (colpito) {
    viteRimaste = viteRimaste - 1;
    console.log("Ouch! Ti rimangono " + viteRimaste + " vite");
} else {
    console.log("L'hai scampata bella!");
}
```

### Sintassi dell'if-else
```javascript
if (condizione) {
    // codice da eseguire se la condizione è vera
} else {
    // codice da eseguire se la condizione è falsa
}
```

## Operatori di confronto

Per prendere decisioni, spesso abbiamo bisogno di confrontare valori. JavaScript ci fornisce diversi operatori di confronto:

```javascript
let età = 16;

// Maggiore di (>)
if (età > 18) {
    console.log("Sei maggiorenne");
}

// Minore di (<)
if (età < 15) {
    console.log("Sei alle medie");
}

// Maggiore o uguale (>=)
if (età >= 16) {
    console.log("Puoi prendere il motorino!");
}

// Minore o uguale (<=)
if (età <= 16) {
    console.log("Sei ancora adolescente");
}

// Uguale (===)
if (età === 16) {
    console.log("Hai esattamente 16 anni");
}

// Diverso (!==)
if (età !== 18) {
    console.log("Non hai 18 anni");
}
```

**Nota importante**: In JavaScript usiamo `===` per controllare l'uguaglianza, non `=` (che serve per assegnare valori alle variabili).

## Operatori logici

Spesso abbiamo bisogno di verificare più condizioni insieme. Gli operatori logici ci permettono di farlo:

```javascript
let età = 16;
let accompagnato = true;

// AND logico (&&) - entrambe le condizioni devono essere vere
if (età >= 14 && accompagnato) {
    console.log("Puoi vedere il film!");
}

// OR logico (||) - almeno una condizione deve essere vera
if (età >= 18 || accompagnato) {
    console.log("Puoi entrare al parco!");
}

// NOT logico (!) - inverte una condizione
if (!accompagnato) {
    console.log("Devi essere accompagnato!");
}
```

## Condizioni multiple con else if

A volte dobbiamo gestire più di due possibilità. Usiamo `else if` per questi casi:

```javascript
let voto = 7;

if (voto >= 9) {
    console.log("Eccellente!");
} else if (voto >= 7) {
    console.log("Molto bene!");
} else if (voto >= 6) {
    console.log("Sufficiente");
} else {
    console.log("Devi studiare di più");
}
```

## Switch statement

Quando abbiamo molti casi diversi da gestire, possiamo usare lo `switch`. È come un grande smistatore:

```javascript
let giorno = "Lunedì";

switch (giorno) {
    case "Lunedì":
        console.log("Inizio settimana!");
        break;
    case "Mercoledì":
        console.log("Metà settimana!");
        break;
    case "Venerdì":
        console.log("Quasi weekend!");
        break;
    case "Sabato":
    case "Domenica":
        console.log("Weekend!");
        break;
    default:
        console.log("Un altro giorno della settimana");
}
```

## Esempio pratico: Cambio stili CSS

Vediamo come usare le strutture di controllo per modificare l'aspetto della nostra pagina:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Semaforo Interattivo</title>
    <style>
        .semaforo {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            border: 2px solid black;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div id="luce" class="semaforo"></div>
    <button id="cambia">Cambia luce</button>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let luce = document.getElementById('luce');
let bottone = document.getElementById('cambia');
let stato = 'rosso';

bottone.onclick = function() {
    if (stato === 'rosso') {
        luce.style.backgroundColor = 'yellow';
        stato = 'giallo';
    } else if (stato === 'giallo') {
        luce.style.backgroundColor = 'green';
        stato = 'verde';
    } else {
        luce.style.backgroundColor = 'red';
        stato = 'rosso';
    }
}
```

## Esercizio guidato: Quiz avanzato

Creiamo un quiz più complesso che usa le strutture di controllo:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Quiz Avanzato</title>
</head>
<body>
    <div id="quiz">
        <h2>Quiz di Cultura Generale</h2>
        <p id="domanda">Qual è la capitale dell'Italia?</p>
        <input type="text" id="risposta">
        <button id="verifica">Verifica</button>
        <p id="feedback"></p>
        <p id="punteggio">Punteggio: 0</p>
    </div>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let risposta = document.getElementById('risposta');
let bottoneVerifica = document.getElementById('verifica');
let feedback = document.getElementById('feedback');
let punteggio = 0;

bottoneVerifica.onclick = function() {
    let rispostaUtente = risposta.value.toLowerCase();
    
    if (rispostaUtente === "roma") {
        feedback.style.color = "green";
        feedback.innerHTML = "Corretto! 🎉";
        punteggio += 10;
    } else if (rispostaUtente === "") {
        feedback.style.color = "orange";
        feedback.innerHTML = "Inserisci una risposta! 🤔";
    } else {
        feedback.style.color = "red";
        feedback.innerHTML = "Sbagliato, riprova! 😕";
        if (punteggio > 0) {
            punteggio -= 5;
        }
    }
    
    document.getElementById('punteggio').innerHTML = "Punteggio: " + punteggio;
}
```

## Esercizi per casa

1. **Calcolatrice del voto**: Crea una pagina dove l'utente inserisce un voto numerico (0-100) e il programma restituisce il voto in lettere (A, B, C, D, F)

2. **Verificatore di password**: Crea un form dove l'utente inserisce una password e il programma verifica se è:
   - Molto sicura (più di 12 caratteri con numeri e simboli)
   - Sicura (8-12 caratteri con numeri)
   - Debole (meno di 8 caratteri)

3. **Gioco di indovinare il numero**: Crea un gioco dove il computer "pensa" a un numero tra 1 e 100 e l'utente deve indovinarlo, ricevendo suggerimenti del tipo "troppo alto" o "troppo basso"

## Punti chiave della lezione
- Le strutture di controllo ci permettono di far prendere decisioni al nostro codice
- `if-else` è la struttura di base per la selezione
- Possiamo usare operatori di confronto (`>`, `<`, `===`, ecc.) per creare condizioni
- Gli operatori logici (`&&`, `||`, `!`) ci permettono di combinare più condizioni
- `switch` è utile quando abbiamo molti casi diversi da gestire
- Possiamo usare le strutture di controllo per modificare dinamicamente lo stile e il contenuto della pagina

# Lezione 4: I cicli

Oggi affronteremo uno degli argomenti più potenti della programmazione: i cicli. Vi è mai capitato di dover ripetere la stessa operazione più volte? Magari scrivere i numeri da 1 a 100, o inviare lo stesso messaggio a 50 persone diverse? I cicli sono proprio quello che ci serve in questi casi: ci permettono di ripetere delle operazioni senza dover riscrivere lo stesso codice più volte.

## Il ciclo while

Il ciclo `while` è il più semplice da capire: continua a ripetere un blocco di codice finché una condizione rimane vera. È come dire "mentre è vero che..., continua a fare...".

```javascript
let contatore = 1;

while (contatore <= 5) {
    console.log("Ripetizione numero " + contatore);
    contatore = contatore + 1;  // o più semplicemente: contatore++
}
```

**Attenzione!** È fondamentale che la condizione del while prima o poi diventi falsa, altrimenti il nostro programma continuerà all'infinito (ciclo infinito)!

### Esempio pratico con while: Conto alla rovescia

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Conto alla rovescia</title>
</head>
<body>
    <h1>Conto alla rovescia</h1>
    <button id="start">Inizia il conto alla rovescia</button>
    <p id="display">10</p>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let bottoneStart = document.getElementById('start');
let display = document.getElementById('display');

bottoneStart.onclick = function() {
    let secondi = 10;
    
    // Usiamo setInterval per creare un timer
    let timer = setInterval(function() {
        if (secondi > 0) {
            secondi--;
            display.innerHTML = secondi;
        } else {
            clearInterval(timer);
            display.innerHTML = "BOOM! 💥";
        }
    }, 1000);
}
```

## Il ciclo for

Il ciclo `for` è probabilmente il più utilizzato. È perfetto quando sappiamo esattamente quante volte vogliamo ripetere un'operazione. Ha una sintassi particolare che include tre parti:
1. Inizializzazione
2. Condizione
3. Incremento

```javascript
for (let i = 0; i < 5; i++) {
    console.log("Questo è il giro numero " + i);
}
```

### Esempio pratico con for: Generatore di lista

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Generatore di lista</title>
</head>
<body>
    <h1>La mia lista della spesa</h1>
    <input type="text" id="elemento" placeholder="Nuovo elemento">
    <button id="aggiungi">Aggiungi</button>
    <button id="rimuoviTutto">Rimuovi tutto</button>
    <ul id="lista"></ul>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let input = document.getElementById('elemento');
let bottoneAggiungi = document.getElementById('aggiungi');
let bottoneRimuovi = document.getElementById('rimuoviTutto');
let lista = document.getElementById('lista');
let elementi = [];

bottoneAggiungi.onclick = function() {
    if (input.value !== '') {
        elementi.push(input.value);
        aggiornaLista();
        input.value = '';
    }
}

bottoneRimuovi.onclick = function() {
    elementi = [];
    aggiornaLista();
}

function aggiornaLista() {
    lista.innerHTML = ''; // Pulisce la lista
    
    for (let i = 0; i < elementi.length; i++) {
        let li = document.createElement('li');
        li.innerHTML = elementi[i];
        lista.appendChild(li);
    }
}
```

## Iterare sugli elementi della pagina

JavaScript ci offre diversi modi per selezionare e iterare su elementi multipli della pagina:

### getElementsByClassName

```javascript
let paragrafi = document.getElementsByClassName('evidenziato');

for (let i = 0; i < paragrafi.length; i++) {
    paragrafi[i].style.backgroundColor = 'yellow';
}
```

### getElementsByTagName

```javascript
let tuttiIParagrafi = document.getElementsByTagName('p');

for (let i = 0; i < tuttiIParagrafi.length; i++) {
    tuttiIParagrafi[i].style.color = 'blue';
}
```

## Esempio avanzato: Tabella delle tabelline

Creiamo una tabella delle tabelline usando i cicli annidati (cicli dentro altri cicli):

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Tabella delle tabelline</title>
    <style>
        table { border-collapse: collapse; }
        td { 
            border: 1px solid black; 
            padding: 8px;
            text-align: center;
        }
        .header {
            background-color: #f0f0f0;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Tabella delle tabelline</h1>
    <div id="tabelline"></div>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
let container = document.getElementById('tabelline');
let table = document.createElement('table');

// Creiamo la prima riga con i numeri da 1 a 10
let headerRow = document.createElement('tr');
headerRow.innerHTML = '<td class="header">×</td>';

for (let i = 1; i <= 10; i++) {
    let th = document.createElement('td');
    th.className = 'header';
    th.innerHTML = i;
    headerRow.appendChild(th);
}
table.appendChild(headerRow);

// Creiamo le altre righe con i risultati
for (let i = 1; i <= 10; i++) {
    let row = document.createElement('tr');
    
    // Prima colonna con il numero della tabellina
    let th = document.createElement('td');
    th.className = 'header';
    th.innerHTML = i;
    row.appendChild(th);
    
    // Colonne con i risultati
    for (let j = 1; j <= 10; j++) {
        let td = document.createElement('td');
        td.innerHTML = i * j;
        // Coloriamo le celle con i numeri pari
        if ((i * j) % 2 === 0) {
            td.style.backgroundColor = '#e6f3ff';
        }
        row.appendChild(td);
    }
    
    table.appendChild(row);
}

container.appendChild(table);
```

## Break e Continue

A volte potremmo voler interrompere un ciclo prima della sua conclusione naturale (`break`) o saltare alcune iterazioni (`continue`):

```javascript
// Break: esce dal ciclo
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        break;  // Il ciclo si ferma a 4
    }
    console.log(i);
}

// Continue: salta all'iterazione successiva
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;  // Salta il numero 3
    }
    console.log(i);
}
```

## Esercizi per casa

1. **Generatore di tabella**: Crea una pagina dove l'utente può specificare il numero di righe e colonne, e il programma genera una tabella HTML con numeri progressivi

2. **Lista di todo**: Crea una lista di todo dove l'utente può:
   - Aggiungere elementi
   - Rimuovere elementi singolarmente
   - Segnare gli elementi come completati
   - Filtrare gli elementi (tutti/completati/da fare)

3. **Gioco del FizzBuzz**: Scrivi un programma che stampi i numeri da 1 a 100, ma:
   - Per i multipli di 3 stampi "Fizz"
   - Per i multipli di 5 stampi "Buzz"
   - Per i numeri che sono multipli sia di 3 che di 5 stampi "FizzBuzz"

## Punti chiave della lezione
- I cicli ci permettono di ripetere del codice più volte
- `while` continua finché una condizione è vera
- `for` è utile quando sappiamo quante iterazioni vogliamo fare
- Possiamo usare i cicli per manipolare elementi multipli della pagina
- `break` interrompe un ciclo
- `continue` salta alla prossima iterazione
- I cicli annidati ci permettono di lavorare con strutture dati bidimensionali

Nella prossima lezione parleremo delle funzioni, che ci permetteranno di organizzare meglio il nostro codice e riutilizzarlo più facilmente. Non dimenticate di esercitarvi con i cicli: sono uno strumento fondamentale nella programmazione!

# Lezione 5: Le funzioni

Pensate alle funzioni come a delle "ricette": invece di scrivere ogni volta tutti i passaggi per preparare un piatto, scriviamo la ricetta una volta sola e poi la riutilizziamo quando serve. Le funzioni funzionano allo stesso modo: ci permettono di raggruppare del codice che vogliamo riutilizzare.

## Cos'è una funzione?

Una funzione è un blocco di codice che:
1. Ha un nome (come `calcolaMedia` o `saluta`)
2. Può ricevere dei dati in input (chiamati parametri)
3. Può restituire un risultato
4. Può essere riutilizzata tutte le volte che vogliamo

## Dichiarazione di una funzione

Ci sono diversi modi per creare una funzione. Vediamoli:

### Metodo tradizionale
```javascript
function saluta(nome) {
    return "Ciao " + nome + "!";
}

// Utilizzo
let messaggio = saluta("Mario");  // messaggio contiene "Ciao Mario!"
```

### Function expression
```javascript
let saluta = function(nome) {
    return "Ciao " + nome + "!";
}

// Utilizzo identico
let messaggio = saluta("Mario");
```

### Arrow function (funzione freccia)
```javascript
let saluta = (nome) => {
    return "Ciao " + nome + "!";
}

// Versione ancora più corta per funzioni semplici
let saluta = nome => "Ciao " + nome + "!";
```

## Parametri e valori di ritorno

Le funzioni possono ricevere più parametri e fare calcoli complessi:

```javascript
function calcolaMedia(numeri) {
    let somma = 0;
    for (let i = 0; i < numeri.length; i++) {
        somma += numeri[i];
    }
    return somma / numeri.length;
}

// Utilizzo
let voti = [6, 7, 8, 7, 9];
let media = calcolaMedia(voti);
```

### Parametri opzionali

Possiamo definire dei valori predefiniti per i parametri:

```javascript
function saluta(nome = "Anonimo", ora = "giorno") {
    return `Buon${ora} ${nome}!`;
}

console.log(saluta());                // "Buongiorno Anonimo!"
console.log(saluta("Mario"));         // "Buongiorno Mario!"
console.log(saluta("Mario", "asera")); // "Buonasera Mario!"
```

## Scope delle variabili

Lo "scope" è l'area del codice dove una variabile è visibile e utilizzabile. È importante capire come funziona per evitare errori:

```javascript
let variabileGlobale = "Sono visibile ovunque";

function esempio() {
    let variabileLocale = "Sono visibile solo dentro la funzione";
    console.log(variabileGlobale);      // Funziona!
    console.log(variabileLocale);       // Funziona!
}

console.log(variabileGlobale);          // Funziona!
console.log(variabileLocale);           // ERRORE! Non è definita qui
```

## Funzioni come gestori di eventi

Le funzioni sono perfette per gestire gli eventi nella nostra pagina web:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Calcolatrice</title>
</head>
<body>
    <input type="number" id="numero1" placeholder="Primo numero">
    <input type="number" id="numero2" placeholder="Secondo numero">
    <button onclick="somma()">+</button>
    <button onclick="sottrai()">-</button>
    <button onclick="moltiplica()">×</button>
    <button onclick="dividi()">÷</button>
    <p id="risultato"></p>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
function leggiNumeri() {
    let n1 = parseFloat(document.getElementById('numero1').value) || 0;
    let n2 = parseFloat(document.getElementById('numero2').value) || 0;
    return [n1, n2];
}

function mostraRisultato(risultato) {
    document.getElementById('risultato').innerHTML = 
        "Risultato: " + risultato;
}

function somma() {
    let [n1, n2] = leggiNumeri();
    mostraRisultato(n1 + n2);
}

function sottrai() {
    let [n1, n2] = leggiNumeri();
    mostraRisultato(n1 - n2);
}

function moltiplica() {
    let [n1, n2] = leggiNumeri();
    mostraRisultato(n1 * n2);
}

function dividi() {
    let [n1, n2] = leggiNumeri();
    if (n2 === 0) {
        mostraRisultato("Non si può dividere per zero!");
    } else {
        mostraRisultato(n1 / n2);
    }
}
```

## Arrow Functions e Event Listeners

Un modo moderno di gestire gli eventi è usando addEventListener con arrow functions:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Todo List</title>
</head>
<body>
    <input type="text" id="nuovoTodo" placeholder="Nuovo todo">
    <button id="aggiungi">Aggiungi</button>
    <ul id="lista"></ul>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
const aggiungiTodo = () => {
    let input = document.getElementById('nuovoTodo');
    let testo = input.value.trim();
    
    if (testo !== '') {
        let lista = document.getElementById('lista');
        let nuovoElemento = document.createElement('li');
        
        // Creiamo il testo del todo
        nuovoElemento.innerHTML = testo;
        
        // Aggiungiamo un bottone per eliminare
        let bottoneElimina = document.createElement('button');
        bottoneElimina.innerHTML = '❌';
        bottoneElimina.onclick = () => nuovoElemento.remove();
        
        nuovoElemento.appendChild(bottoneElimina);
        lista.appendChild(nuovoElemento);
        input.value = '';
    }
};

document.getElementById('aggiungi')
    .addEventListener('click', aggiungiTodo);

// Bonus: aggiungiamo anche con il tasto Invio
document.getElementById('nuovoTodo')
    .addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            aggiungiTodo();
        }
    });
```

## Esempio avanzato: Form di registrazione con validazione

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Registrazione</title>
    <style>
        .errore { color: red; }
        .successo { color: green; }
    </style>
</head>
<body>
    <form id="formRegistrazione">
        <div>
            <label>Email:</label>
            <input type="email" id="email">
            <span id="emailError"></span>
        </div>
        <div>
            <label>Password:</label>
            <input type="password" id="password">
            <span id="passwordError"></span>
        </div>
        <div>
            <label>Conferma Password:</label>
            <input type="password" id="confermaPassword">
            <span id="confermaError"></span>
        </div>
        <button type="submit">Registrati</button>
    </form>
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
const validaEmail = (email) => {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email);
};

const validaPassword = (password) => {
    return password.length >= 8 &&  // almeno 8 caratteri
           /[A-Z]/.test(password) &&  // almeno una maiuscola
           /[0-9]/.test(password);    // almeno un numero
};

const mostraErrore = (elementId, messaggio) => {
    document.getElementById(elementId).innerHTML = messaggio;
    document.getElementById(elementId).className = 'errore';
};

const pulisciErrore = (elementId) => {
    document.getElementById(elementId).innerHTML = '';
};

document.getElementById('formRegistrazione').addEventListener('submit', (e) => {
    e.preventDefault();  // impedisce l'invio del form
    
    let email = document.getElementById('email').value;
    let password = document.getElementById('password').value;
    let conferma = document.getElementById('confermaPassword').value;
    let tuttoOk = true;
    
    // Puliamo i messaggi di errore precedenti
    pulisciErrore('emailError');
    pulisciErrore('passwordError');
    pulisciErrore('confermaError');
    
    // Validazione email
    if (!validaEmail(email)) {
        mostraErrore('emailError', 'Email non valida');
        tuttoOk = false;
    }
    
    // Validazione password
    if (!validaPassword(password)) {
        mostraErrore('passwordError', 
            'La password deve contenere almeno 8 caratteri, ' +
            'una maiuscola e un numero');
        tuttoOk = false;
    }
    
    // Validazione conferma password
    if (password !== conferma) {
        mostraErrore('confermaError', 'Le password non coincidono');
        tuttoOk = false;
    }
    
    if (tuttoOk) {
        alert('Registrazione completata con successo!');
        // Qui normalmente invieresti i dati al server
    }
});
```

## Esercizi per casa

1. **Libreria di utilità**: Crea un file di funzioni utili che includano:
   - `capitalizza(stringa)` → converte la prima lettera in maiuscolo
   - `inverti(stringa)` → inverte una stringa
   - `contaVocali(stringa)` → conta le vocali in una stringa

2. **Convertitore di temperature**: Crea una pagina con funzioni per convertire:
   - Da Celsius a Fahrenheit
   - Da Fahrenheit a Celsius
   - Da Celsius a Kelvin
   - Da Kelvin a Celsius

3. **Validatore di form**: Crea un form con validazione per:
   - Numero di telefono (formato italiano)
   - Codice fiscale
   - Data di nascita (deve essere maggiorenne)

## Punti chiave della lezione
- Le funzioni sono blocchi di codice riutilizzabili
- Possono ricevere parametri e restituire valori
- Esistono diversi modi di scrivere funzioni (tradizionale, expression, arrow)
- Le variabili hanno uno scope che determina dove sono utilizzabili
- Le funzioni sono perfette per gestire eventi
- La modularizzazione del codice rende il programma più organizzato e mantenibile

# Lezione 6: Eventi - Parte 1

## Introduzione agli Eventi
Gli eventi sono azioni o occorrenze che si verificano nel browser, come il click di un utente, il movimento del mouse, il caricamento di una pagina o la pressione di un tasto. JavaScript ci permette di "ascoltare" questi eventi e reagire di conseguenza, rendendo le nostre pagine web interattive.

### Struttura HTML di Base
```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Eventi in JavaScript</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="menu">
        <button id="btnTest">Cliccami!</button>
        <div id="hoverArea">Passa il mouse qui sopra</div>
        <ul id="menuItems" class="hidden">
            <li>Opzione 1</li>
            <li>Opzione 2</li>
            <li>Opzione 3</li>
        </ul>
    </div>

    <script src="app.js"></script>
</body>
</html>
```

### CSS di Base
```css
.hidden {
    display: none;
}

#hoverArea {
    padding: 20px;
    background-color: #f0f0f0;
    margin: 20px 0;
    cursor: pointer;
}

#hoverArea:hover {
    background-color: #e0e0e0;
}
```

## 1. Eventi onClick e onMouseOver
Gli eventi più comuni sono quelli legati al mouse. Vediamo come gestirli:

```javascript
// Metodo 1: Gestione diretta nell'HTML (sconsigliato)
// <button onclick="saluta()">Cliccami</button>

// Metodo 2: Assegnazione tramite proprietà (migliore)
const btnTest = document.getElementById('btnTest');
btnTest.onclick = function() {
    alert('Hai cliccato il pulsante!');
};

const hoverArea = document.getElementById('hoverArea');
hoverArea.onmouseover = function() {
    this.style.backgroundColor = '#cccccc';
};

hoverArea.onmouseout = function() {
    this.style.backgroundColor = '#f0f0f0';
};
```

## 2. addEventListener()
Il metodo più moderno e flessibile per gestire gli eventi è `addEventListener()`. Permette di:
- Aggiungere più gestori per lo stesso evento
- Rimuovere gestori quando non servono più
- Maggior controllo sulla propagazione degli eventi

```javascript
// Sintassi base
// elemento.addEventListener(evento, funzione, useCapture)

const btn = document.getElementById('btnTest');

btn.addEventListener('click', function() {
    console.log('Click rilevato!');
});

// Con arrow function
btn.addEventListener('click', () => {
    alert('Altro gestore per lo stesso pulsante');
});

// Con funzione nominata
function gestioneHover() {
    const menu = document.getElementById('menuItems');
    menu.classList.toggle('hidden');
}

const hoverArea = document.getElementById('hoverArea');
hoverArea.addEventListener('mouseover', gestioneHover);
```

## 3. L'Oggetto Event
Quando si verifica un evento, JavaScript crea un oggetto `Event` che contiene informazioni dettagliate sull'evento stesso. Quest'oggetto viene passato automaticamente alla funzione gestore.

```javascript
btnTest.addEventListener('click', function(event) {
    // Informazioni sull'evento
    console.log('Tipo di evento:', event.type);
    console.log('Elemento target:', event.target);
    console.log('Coordinate del click:', event.clientX, event.clientY);
    
    // Fermare la propagazione dell'evento
    event.stopPropagation();
});
```

## 4. Esempio Pratico: Menu Interattivo
Creiamo un menu che si apre al click e si chiude cliccando fuori:

```javascript
document.addEventListener('DOMContentLoaded', () => {
    const menuButton = document.getElementById('btnTest');
    const menuItems = document.getElementById('menuItems');
    let menuOpen = false;

    // Apre/chiude il menu al click del pulsante
    menuButton.addEventListener('click', (e) => {
        menuItems.classList.toggle('hidden');
        menuOpen = !menuOpen;
        e.stopPropagation(); // Previene la chiusura immediata
    });

    // Chiude il menu cliccando fuori
    document.addEventListener('click', (e) => {
        if (menuOpen && !menuItems.contains(e.target) && e.target !== menuButton) {
            menuItems.classList.add('hidden');
            menuOpen = false;
        }
    });
});
```

## Esercizi Proposti

1. **Menu Dropdown**
   Modifica l'esempio del menu per:
   - Aggiungere una transizione di apertura/chiusura
   - Cambiare il testo del pulsante quando il menu è aperto
   - Aggiungere un'animazione al passaggio del mouse sulle voci

2. **Galleria di Immagini**
   Crea una galleria che:
   - Mostri un'immagine principale
   - Abbia miniature cliccabili
   - Cambi l'immagine principale al click sulle miniature
   - Aggiunga un effetto hover sulle miniature

3. **Sistema di Notifiche**
   Implementa un sistema che:
   - Mostri notifiche in un angolo della pagina
   - Le faccia scomparire dopo alcuni secondi
   - Permetta di chiuderle manualmente

## Punti Chiave da Ricordare
- Preferire sempre `addEventListener()` rispetto agli attributi HTML o alle proprietà on*
- Utilizzare la delega degli eventi per gestire elementi dinamici
- Ricordarsi di gestire la pulizia degli event listener quando non servono più
- Fare attenzione alla propagazione degli eventi
- Considerare sempre l'accessibilità quando si implementano interazioni

# Lezione 7: Eventi - Parte 2 e Gestione Form

## Struttura HTML di Base
```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Gestione Form con JavaScript</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <form id="registrationForm">
            <h2>Modulo di Registrazione</h2>
            
            <div class="form-group">
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>
                <span class="error" id="usernameError"></span>
            </div>

            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <span class="error" id="emailError"></span>
            </div>

            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>
                <span class="error" id="passwordError"></span>
            </div>

            <div class="form-group">
                <label for="interessi">Interessi:</label>
                <select id="interessi" name="interessi" multiple>
                    <option value="sport">Sport</option>
                    <option value="musica">Musica</option>
                    <option value="tecnologia">Tecnologia</option>
                </select>
            </div>

            <div class="form-group">
                <label>
                    <input type="checkbox" id="privacy" name="privacy" required>
                    Accetto i termini e le condizioni
                </label>
            </div>

            <button type="submit">Registrati</button>
        </form>

        <div id="confirmation" class="hidden">
            Registrazione completata con successo!
        </div>
    </div>

    <script src="app.js"></script>
</body>
</html>
```

### CSS di Base
```css
.container {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
}

.form-group {
    margin-bottom: 15px;
}

.form-group label {
    display: block;
    margin-bottom: 5px;
}

.form-group input,
.form-group select {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
}

.error {
    color: red;
    font-size: 0.8em;
    display: block;
    margin-top: 5px;
}

.hidden {
    display: none;
}

.invalid {
    border-color: red !important;
}

.valid {
    border-color: green !important;
}
```

## 1. Eventi dei Form
```javascript
// Otteniamo riferimenti agli elementi del form
const form = document.getElementById('registrationForm');
const username = document.getElementById('username');
const email = document.getElementById('email');
const password = document.getElementById('password');
const privacy = document.getElementById('privacy');

// Eventi principali dei form
form.addEventListener('submit', handleSubmit);
username.addEventListener('change', validateUsername);
email.addEventListener('input', validateEmail);
password.addEventListener('focus', showPasswordRequirements);
password.addEventListener('blur', hidePasswordRequirements);
```

## 2. Validazione Base dei Form
```javascript
function validateUsername(e) {
    const value = e.target.value;
    const errorElement = document.getElementById('usernameError');
    
    if (value.length < 3) {
        errorElement.textContent = 'Lo username deve contenere almeno 3 caratteri';
        e.target.classList.add('invalid');
        e.target.classList.remove('valid');
        return false;
    } else {
        errorElement.textContent = '';
        e.target.classList.remove('invalid');
        e.target.classList.add('valid');
        return true;
    }
}

function validateEmail(e) {
    const value = e.target.value;
    const errorElement = document.getElementById('emailError');
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    
    if (!emailRegex.test(value)) {
        errorElement.textContent = 'Inserisci un indirizzo email valido';
        e.target.classList.add('invalid');
        e.target.classList.remove('valid');
        return false;
    } else {
        errorElement.textContent = '';
        e.target.classList.remove('invalid');
        e.target.classList.add('valid');
        return true;
    }
}

function validatePassword(e) {
    const value = e.target.value;
    const errorElement = document.getElementById('passwordError');
    
    const hasUpperCase = /[A-Z]/.test(value);
    const hasLowerCase = /[a-z]/.test(value);
    const hasNumbers = /\d/.test(value);
    const hasMinLength = value.length >= 8;
    
    let errorMessage = '';
    if (!hasMinLength) errorMessage += 'Minimo 8 caratteri. ';
    if (!hasUpperCase) errorMessage += 'Almeno una maiuscola. ';
    if (!hasLowerCase) errorMessage += 'Almeno una minuscola. ';
    if (!hasNumbers) errorMessage += 'Almeno un numero. ';
    
    errorElement.textContent = errorMessage;
    
    if (errorMessage === '') {
        e.target.classList.remove('invalid');
        e.target.classList.add('valid');
        return true;
    } else {
        e.target.classList.add('invalid');
        e.target.classList.remove('valid');
        return false;
    }
}
```

## 3. Gestione dell'Evento Submit
```javascript
function handleSubmit(e) {
    e.preventDefault(); // Previene l'invio automatico del form
    
    // Validazione di tutti i campi
    const isUsernameValid = validateUsername({ target: username });
    const isEmailValid = validateEmail({ target: email });
    const isPasswordValid = validatePassword({ target: password });
    
    if (!privacy.checked) {
        alert('Devi accettare i termini e le condizioni');
        return;
    }
    
    // Se tutti i campi sono validi
    if (isUsernameValid && isEmailValid && isPasswordValid) {
        // Raccogliamo i dati del form
        const formData = new FormData(form);
        const data = Object.fromEntries(formData.entries());
        
        // Qui normalmente invieremo i dati al server
        console.log('Dati del form:', data);
        
        // Mostriamo il messaggio di conferma
        const confirmation = document.getElementById('confirmation');
        confirmation.classList.remove('hidden');
        form.classList.add('hidden');
    }
}
```

## 4. Validazione in Tempo Reale
```javascript
// Validazione mentre l'utente digita
const inputs = form.querySelectorAll('input[required]');

inputs.forEach(input => {
    input.addEventListener('input', function(e) {
        // Rimuoviamo eventuali messaggi di errore quando l'utente inizia a digitare
        const errorElement = document.getElementById(`${e.target.id}Error`);
        if (errorElement) {
            errorElement.textContent = '';
        }
        
        // Rimuoviamo le classi di validazione
        e.target.classList.remove('valid', 'invalid');
    });
});

// Validazione quando l'utente esce dal campo
inputs.forEach(input => {
    input.addEventListener('blur', function(e) {
        switch(e.target.id) {
            case 'username':
                validateUsername(e);
                break;
            case 'email':
                validateEmail(e);
                break;
            case 'password':
                validatePassword(e);
                break;
        }
    });
});
```

## 5. Miglioramenti per l'Accessibilità
```javascript
// Aggiunta di ARIA attributes per l'accessibilità
function updateAriaAttributes(input, isValid) {
    input.setAttribute('aria-invalid', !isValid);
    const errorId = `${input.id}Error`;
    input.setAttribute('aria-describedby', errorId);
}

// Gestione del focus
inputs.forEach(input => {
    input.addEventListener('focus', function(e) {
        // Aggiunge un outline visibile per il focus
        e.target.style.outline = '2px solid #007bff';
    });
    
    input.addEventListener('blur', function(e) {
        // Rimuove l'outline quando si perde il focus
        e.target.style.outline = '';
    });
});
```

## Esercizi Proposti

1. **Form Multi-Step**
   Crea un form di registrazione diviso in più passaggi:
   - Dati personali
   - Preferenze
   - Conferma

2. **Validazione Avanzata**
   Aggiungi validazioni per:
   - Numero di telefono (formato italiano)
   - Codice fiscale
   - Data di nascita (con controllo età minima)

3. **Form Dinamico**
   Implementa un form che:
   - Aggiunge/rimuove campi dinamicamente
   - Salva i dati in localStorage
   - Ripristina i dati salvati al caricamento

## Punti Chiave da Ricordare
- Sempre prevenire l'invio del form con `preventDefault()`
- Validare sia lato client che lato server
- Fornire feedback immediato all'utente
- Gestire tutti gli stati del form (vuoto, valido, non valido, in attesa)
- Considerare l'accessibilità
- Gestire correttamente gli errori
- Salvare i dati temporaneamente in caso di errori

# Lezione 8: Manipolazione avanzata del DOM e Progetto Todo List

## Struttura HTML di Base
```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Todo List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>La Mia Todo List</h1>
        
        <!-- Form per aggiungere task -->
        <div class="todo-input">
            <input type="text" id="taskInput" placeholder="Aggiungi un nuovo task">
            <button id="addTask">Aggiungi</button>
        </div>

        <!-- Filtri -->
        <div class="filters">
            <button class="filter active" data-filter="all">Tutti</button>
            <button class="filter" data-filter="active">Attivi</button>
            <button class="filter" data-filter="completed">Completati</button>
        </div>

        <!-- Lista dei task -->
        <ul id="todoList"></ul>

        <!-- Counter -->
        <div class="todo-count">
            Task rimanenti: <span id="taskCount">0</span>
        </div>
    </div>

    <script src="app.js"></script>
</body>
</html>
```

### CSS di Base
```css
.container {
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.todo-input {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
}

.todo-input input {
    flex: 1;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
}

button {
    padding: 8px 16px;
    background: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background: #45a049;
}

.filters {
    margin-bottom: 20px;
}

.filter {
    background: #f1f1f1;
    color: #333;
}

.filter.active {
    background: #666;
    color: white;
}

#todoList {
    list-style: none;
    padding: 0;
}

.todo-item {
    display: flex;
    align-items: center;
    padding: 10px;
    background: #f9f9f9;
    margin-bottom: 5px;
    border-radius: 4px;
}

.todo-item.completed {
    background: #e0e0e0;
    text-decoration: line-through;
    color: #666;
}

.todo-item .delete {
    margin-left: auto;
    background: #ff4444;
}

.completed-checkbox {
    margin-right: 10px;
}
```

## 1. Creazione e Aggiunta di Elementi
```javascript
// Funzione per creare un nuovo elemento todo
function createTodoElement(todoText) {
    // Creazione degli elementi
    const li = document.createElement('li');
    const checkbox = document.createElement('input');
    const span = document.createElement('span');
    const deleteBtn = document.createElement('button');

    // Configurazione checkbox
    checkbox.type = 'checkbox';
    checkbox.className = 'completed-checkbox';

    // Configurazione span
    span.textContent = todoText;
    span.className = 'todo-text';

    // Configurazione pulsante elimina
    deleteBtn.textContent = '×';
    deleteBtn.className = 'delete';

    // Configurazione elemento li
    li.className = 'todo-item';
    
    // Assemblaggio dell'elemento
    li.appendChild(checkbox);
    li.appendChild(span);
    li.appendChild(deleteBtn);

    return li;
}

// Funzione per aggiungere un todo alla lista
function addTodoToList(todoText) {
    const todoList = document.getElementById('todoList');
    const todoElement = createTodoElement(todoText);
    todoList.appendChild(todoElement);
    updateTaskCount();
}
```

## 2. Rimozione di Elementi
```javascript
// Funzione per rimuovere un todo
function removeTodo(todoElement) {
    // Animazione di fade out
    todoElement.style.opacity = '0';
    todoElement.style.transition = 'opacity 0.3s ease';

    // Rimozione effettiva dopo l'animazione
    setTimeout(() => {
        todoElement.remove();
        updateTaskCount();
    }, 300);
}

// Event delegation per il pulsante elimina
document.getElementById('todoList').addEventListener('click', (e) => {
    if (e.target.className === 'delete') {
        const todoItem = e.target.parentElement;
        removeTodo(todoItem);
    }
});
```

## 3. Navigazione del DOM
```javascript
// Funzione per trovare tutti i task completati
function getCompletedTasks() {
    const todos = document.querySelectorAll('.todo-item');
    return Array.from(todos).filter(todo => 
        todo.querySelector('.completed-checkbox').checked
    );
}

// Funzione per trovare il parent più vicino con una classe
function closest(element, className) {
    while (element) {
        if (element.classList.contains(className)) {
            return element;
        }
        element = element.parentElement;
    }
    return null;
}

// Funzione per trovare i siblings
function getSiblings(element) {
    return Array.from(element.parentNode.children)
        .filter(child => child !== element);
}
```

## 4. Gestione delle Classi CSS
```javascript
// Toggle dello stato completato
function toggleTodoComplete(todoItem) {
    const checkbox = todoItem.querySelector('.completed-checkbox');
    
    if (checkbox.checked) {
        todoItem.classList.add('completed');
    } else {
        todoItem.classList.remove('completed');
    }
    
    updateTaskCount();
}

// Event listener per i checkbox
document.getElementById('todoList').addEventListener('change', (e) => {
    if (e.target.className === 'completed-checkbox') {
        const todoItem = e.target.closest('.todo-item');
        toggleTodoComplete(todoItem);
    }
});
```

## 5. Implementazione dei Filtri
```javascript
// Funzione per filtrare i todo
function filterTodos(filterType) {
    const todos = document.querySelectorAll('.todo-item');
    
    todos.forEach(todo => {
        const isCompleted = todo.classList.contains('completed');
        
        switch(filterType) {
            case 'all':
                todo.style.display = '';
                break;
            case 'active':
                todo.style.display = !isCompleted ? '' : 'none';
                break;
            case 'completed':
                todo.style.display = isCompleted ? '' : 'none';
                break;
        }
    });
}

// Event listeners per i filtri
document.querySelector('.filters').addEventListener('click', (e) => {
    if (e.target.classList.contains('filter')) {
        // Aggiorna classe active
        document.querySelectorAll('.filter').forEach(btn => 
            btn.classList.remove('active')
        );
        e.target.classList.add('active');
        
        // Applica il filtro
        filterTodos(e.target.dataset.filter);
    }
});
```

## 6. Gestione dello Stato
```javascript
// Funzione per aggiornare il contatore
function updateTaskCount() {
    const totalTasks = document.querySelectorAll('.todo-item').length;
    const completedTasks = document.querySelectorAll('.todo-item.completed').length;
    const remainingTasks = totalTasks - completedTasks;
    
    document.getElementById('taskCount').textContent = remainingTasks;
}

// Salvataggio in localStorage
function saveTodos() {
    const todos = Array.from(document.querySelectorAll('.todo-item')).map(todo => ({
        text: todo.querySelector('.todo-text').textContent,
        completed: todo.classList.contains('completed')
    }));
    
    localStorage.setItem('todos', JSON.stringify(todos));
}

// Caricamento da localStorage
function loadTodos() {
    const todos = JSON.parse(localStorage.getItem('todos') || '[]');
    todos.forEach(todo => {
        const todoElement = createTodoElement(todo.text);
        if (todo.completed) {
            todoElement.classList.add('completed');
            todoElement.querySelector('.completed-checkbox').checked = true;
        }
        document.getElementById('todoList').appendChild(todoElement);
    });
    updateTaskCount();
}
```

## 7. Inizializzazione dell'Applicazione
```javascript
// Funzione di inizializzazione
function initTodoApp() {
    const addButton = document.getElementById('addTask');
    const taskInput = document.getElementById('taskInput');

    // Event listener per aggiungere task
    addButton.addEventListener('click', () => {
        const todoText = taskInput.value.trim();
        if (todoText) {
            addTodoToList(todoText);
            taskInput.value = '';
            saveTodos();
        }
    });

    // Event listener per il tasto Enter
    taskInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            addButton.click();
        }
    });

    // Carica i todos salvati
    loadTodos();
}

// Avvio dell'applicazione quando il DOM è caricato
document.addEventListener('DOMContentLoaded', initTodoApp);
```

## Esercizi Proposti

1. **Estensione Todo List**
   - Aggiungi la possibilità di modificare i task esistenti
   - Implementa il drag and drop per riordinare i task
   - Aggiungi categorie o tag ai task

2. **Sistema di Note**
   - Crea un sistema di note con rich text
   - Implementa la possibilità di aggiungere immagini
   - Aggiungi un sistema di ricerca

3. **Lista della Spesa**
   - Implementa categorie di prodotti
   - Aggiungi quantità e prezzi
   - Calcola il totale della spesa

## Punti Chiave da Ricordare
- Utilizzare `createElement()` per creare nuovi elementi
- Gestire correttamente gli eventi con la delegation
- Manipolare le classi CSS per le animazioni
- Salvare lo stato dell'applicazione
- Mantenere il codice organizzato e modulare
- Considerare l'accessibilità
- Gestire correttamente la memoria