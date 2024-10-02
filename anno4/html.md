# HTML

## 1. Introduzione

### Cos'è l'HTML?

HTML sta per "HyperText Markup Language", che in italiano potremmo tradurre come "Linguaggio di Marcatura per Ipertesti". Suona complicato, vero? In realtà, è più semplice di quanto sembri!

Immaginate l'HTML come il linguaggio che usiamo per "costruire" le pagine web. È come se fosse il mattone e il cemento con cui creiamo la struttura di un sito internet. Con l'HTML, diciamo al browser (come Chrome, Firefox o Safari) come deve organizzare e presentare il contenuto di una pagina web.

### A cosa serve l'HTML?

L'HTML serve principalmente a tre cose:

1. **Strutturare il contenuto**: Con l'HTML, possiamo dire al browser quali parti del nostro testo sono titoli, paragrafi, elenchi, e così via.

2. **Inserire elementi multimediali**: L'HTML ci permette di aggiungere immagini, video e altri elementi interattivi alle nostre pagine web.

3. **Creare collegamenti**: Con l'HTML, possiamo inserire link che ci permettono di saltare da una pagina all'altra o da un sito all'altro.

### Come funziona l'HTML?

L'HTML utilizza dei "tag" per marcare il contenuto. Un tag è come un'etichetta che dice al browser come trattare un determinato pezzo di contenuto. Per esempio, se volessimo creare un titolo, useremmo il tag `<h1>` in questo modo:

```html
<h1>Benvenuti nel mondo dell'HTML!</h1>
```

Non preoccupatevi se non capite ancora come funzionano i tag, li vedremo in dettaglio nei prossimi capitoli!

### Perché è importante imparare l'HTML?

Imparare l'HTML è fondamentale per chiunque voglia creare contenuti per il web. Ecco alcuni motivi per cui è importante:

1. **È la base del web**: Ogni sito che visitate è costruito, almeno in parte, con l'HTML.

2. **È relativamente facile da imparare**: A differenza di alcuni linguaggi di programmazione, l'HTML ha una struttura abbastanza intuitiva.

3. **Vi dà il controllo**: Conoscendo l'HTML, potrete personalizzare l'aspetto e la struttura delle vostre pagine web.

4. **È il punto di partenza**: L'HTML è la base su cui si costruiscono competenze più avanzate come CSS e JavaScript.

## 2. Struttura fondamentale di una pagina web

Ciao ragazzi! Benvenuti al secondo capitolo del nostro viaggio nel mondo dell'HTML. Oggi parleremo della struttura fondamentale di una pagina web. Pensate a questa struttura come allo scheletro del corpo umano: senza di essa, la nostra pagina web non starebbe in piedi!

### Le parti fondamentali di una pagina HTML

Una pagina HTML è composta da quattro parti principali:

1. La dichiarazione del DOCTYPE
2. L'elemento `<html>`
3. L'elemento `<head>`
4. L'elemento `<body>`

Vediamole una per una!

#### 1. La dichiarazione del DOCTYPE

Il DOCTYPE (Document Type Declaration) è la prima cosa che appare in un documento HTML. Serve a dire al browser che tipo di documento sta per leggere. Per l'HTML5, la versione più recente di HTML, il DOCTYPE si scrive così:

```html
<!DOCTYPE html>
```

Semplice, vero? Non dovete preoccuparvi troppo del significato di questa riga. Basta sapere che deve essere sempre la prima cosa nel vostro documento HTML.

#### 2. L'elemento `<html>`

Subito dopo il DOCTYPE, troviamo l'elemento `<html>`. Questo elemento racchiude tutto il contenuto della vostra pagina web. È come il contenitore principale di tutto ciò che vedrete sul sito. Si apre con `<html>` e si chiude con `</html>` alla fine del documento.

```html
<html>
    <!-- Tutto il contenuto della pagina va qui dentro -->
</html>
```

### 3. L'elemento `<head>`

All'interno dell'elemento `<html>`, troviamo prima di tutto l'elemento `<head>`. Questo elemento contiene informazioni sulla pagina che non vengono mostrate direttamente nel browser. Queste informazioni sono importanti per il funzionamento della pagina, ma non sono visibili agli utenti.

Nell'elemento `<head>` di solito troviamo:

- Il titolo della pagina (quello che appare nella scheda del browser)
- Collegamenti a file CSS per lo stile della pagina
- Meta informazioni, come la codifica dei caratteri
- Altri script o informazioni necessarie per il funzionamento della pagina

Ecco un esempio:

```html
<head>
    <meta charset="UTF-8">
    <title>La mia prima pagina web</title>
    <link rel="stylesheet" href="stile.css">
</head>
```

### 4. L'elemento `<body>`

Dopo l'elemento `<head>`, troviamo l'elemento `<body>`. Qui è dove mettiamo tutto il contenuto che vogliamo mostrare nella pagina web: testo, immagini, video, link, e così via.

```html
<body>
    <h1>Benvenuti nella mia prima pagina web!</h1>
    <p>Questo è un paragrafo di testo.</p>
    <img src="immagine.jpg" alt="Una bella immagine">
</body>
```

## Mettendo tutto insieme

Ecco come appare una pagina HTML completa con tutti questi elementi:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>La mia prima pagina web</title>
        <link rel="stylesheet" href="stile.css">
    </head>
    <body>
        <h1>Benvenuti nella mia prima pagina web!</h1>
        <p>Questo è un paragrafo di testo.</p>
        <img src="immagine.jpg" alt="Una bella immagine">
    </body>
</html>
```

Questa è la struttura di base di ogni pagina web che creerete. Può sembrare un po' complicata all'inizio, ma con la pratica diventerà naturale come scrivere una lettera!

Ricordate:

- Il DOCTYPE dice al browser che tipo di documento sta leggendo
- L'elemento `<html>` contiene tutto
- L'elemento `<head>` contiene informazioni sulla pagina
- L'elemento `<body>` contiene il contenuto visibile della pagina

## 3. Il concetto di tag e attributi dei tag

### Cos'è un tag HTML?

Immaginate i tag HTML come delle etichette che dicono al browser come deve trattare il contenuto che c'è tra di loro. I tag sono sempre racchiusi tra parentesi angolari `< >`.

La maggior parte dei tag HTML vengono usati in coppia: un tag di apertura e un tag di chiusura. Il tag di chiusura ha una barra `/` prima del nome del tag. Ecco un esempio:

```html
<p>Questo è un paragrafo.</p>
```

In questo esempio, `<p>` è il tag di apertura e `</p>` è il tag di chiusura. Tutto ciò che sta tra questi due tag viene trattato come un paragrafo.

### Tipi comuni di tag

Ci sono molti tipi diversi di tag in HTML. Ecco alcuni dei più comuni:

1. `<h1>` a `<h6>`: Per i titoli (dall'1 al 6, dove 1 è il più importante)
2. `<p>`: Per i paragrafi
3. `<a>`: Per i link
4. `<img>`: Per le immagini
5. `<ul>` e `<ol>`: Per le liste non ordinate e ordinate
6. `<li>`: Per gli elementi delle liste
7. `<div>`: Per dividere la pagina in sezioni

Ecco un esempio che usa alcuni di questi tag:

```html
<h1>Benvenuti nel mio sito</h1>
<p>Questo è un paragrafo introduttivo.</p>
<h2>Le mie cose preferite</h2>
<ul>
    <li>Pizza</li>
    <li>Musica</li>
    <li>Programmazione</li>
</ul>
```

### Tag vuoti

Alcuni tag non hanno un tag di chiusura perché non "racchiudono" del contenuto. Questi sono chiamati tag vuoti o tag auto-chiudenti. Un esempio comune è il tag `<img>` per le immagini:

```html
<img src="mia-foto.jpg" alt="Una mia foto">
```

### Cos'è un attributo?

Gli attributi forniscono informazioni aggiuntive sui tag HTML. Sono sempre specificati nel tag di apertura e di solito consistono in coppie nome/valore.

La sintassi generale per gli attributi è:

```html
<tag nome="valore">Contenuto</tag>
```

### Attributi comuni

Ci sono molti attributi diversi in HTML. Ecco alcuni dei più comuni:

1. `class`: Usato per applicare stili CSS o per identificare elementi con JavaScript
2. `id`: Usato per identificare in modo univoco un elemento
3. `src`: Usato con `<img>` per specificare il percorso dell'immagine
4. `href`: Usato con `<a>` per specificare l'URL del link
5. `alt`: Usato con `<img>` per fornire un testo alternativo per l'immagine
6. `style`: Usato per applicare stili CSS inline

Ecco alcuni esempi:

```html
<a href="https://www.esempio.it">Visita il mio sito web</a>

<img src="cane.jpg" alt="Il mio cane" class="foto-animale">

<p id="intro" style="color: blue;">Questo è un paragrafo blu.</p>
```

### L'importanza della sintassi corretta

È importante ricordare che HTML è molto particolare sulla sintassi. Se dimenticate di chiudere un tag o scrivete male un attributo, la vostra pagina potrebbe non funzionare come previsto. Ecco alcuni punti da ricordare:

1. I tag di apertura e chiusura devono corrispondere esattamente
2. Gli attributi vanno sempre nel tag di apertura
3. I valori degli attributi devono essere racchiusi tra virgolette (singole o doppie)
4. I tag vuoti non hanno bisogno di un tag di chiusura

I tag e gli attributi sono i mattoncini con cui costruirete le vostre pagine web. Con la pratica, diventerete sempre più abili nel loro utilizzo.

Ricordate:

- I tag dicono al browser come trattare il contenuto
- Gli attributi forniscono informazioni aggiuntive sui tag
- La sintassi corretta è fondamentale per il funzionamento della vostra pagina

## 4. I tag per il testo

Ciao ragazzi! Benvenuti al quarto capitolo del nostro viaggio nel mondo dell'HTML. Oggi parleremo dei tag specifici per il testo. Questi tag sono fondamentali per strutturare e formattare il contenuto delle vostre pagine web. Vedrete come potrete dare vita ai vostri testi e renderli più interessanti e leggibili!

### I tag per i titoli: h1, h2, h3, h4, h5, h6

In HTML, abbiamo sei livelli di titoli, dal più importante (h1) al meno importante (h6). Questi tag sono utilizzati per creare una gerarchia nel vostro contenuto e aiutare i motori di ricerca a capire la struttura della vostra pagina.

Ecco un esempio di come si usano:

```html
<h1>Questo è il titolo principale della pagina</h1>
<h2>Questo è un sottotitolo</h2>
<h3>Questo è un sottotitolo di livello inferiore</h3>
<h4>E così via...</h4>
<h5>Fino ad arrivare...</h5>
<h6>Al titolo più piccolo</h6>
```

Ricordate: è buona pratica avere un solo `<h1>` per pagina, che rappresenta il titolo principale del contenuto.

### Il tag per i paragrafi: p

Il tag `<p>` è usato per creare paragrafi di testo. È uno dei tag più comuni che utilizzerete. Ecco un esempio:

```html
<p>Questo è un paragrafo. Può contenere diverse frasi e andrà a capo automaticamente quando raggiunge il bordo della pagina.</p>

<p>Questo è un altro paragrafo. Notate come viene creato uno spazio tra i paragrafi.</p>
```

### Il tag article

Il tag `<article>` è usato per raggruppare contenuti indipendenti e autonomi. È perfetto per blog post, articoli di giornale, o qualsiasi contenuto che potrebbe stare da solo. Ecco un esempio:

```html
<article>
    <h2>Titolo dell'articolo</h2>
    <p>Questo è il primo paragrafo dell'articolo.</p>
    <p>Questo è il secondo paragrafo dell'articolo.</p>
</article>
```

### Altri tag utili per il testo

Ci sono molti altri tag utili per formattare il testo. Ecco alcuni dei più comuni:

#### Tag `<strong>` e `<em>`

- `<strong>` è usato per indicare testo importante, di solito viene visualizzato in grassetto.
- `<em>` è usato per enfatizzare il testo, di solito viene visualizzato in corsivo.

```html
<p>Questa frase contiene <strong>testo importante</strong> e <em>testo enfatizzato</em>.</p>
```

#### Tag `<br>`

Il tag `<br>` è usato per creare un'interruzione di riga. È un tag vuoto, quindi non ha un tag di chiusura.

```html
<p>Questa è la prima riga.<br>E questa è la seconda riga.</p>
```

#### Tag `<blockquote>`

Il tag `<blockquote>` è usato per le citazioni lunghe. Di solito, il browser indenta il testo all'interno di questo tag.

```html
<blockquote>
    <p>Essere o non essere, questo è il dilemma.</p>
</blockquote>
```

#### Tag `<pre>`

Il tag `<pre>` è usato per testo preformattato. Mantiene gli spazi e le interruzioni di riga esattamente come sono scritte nel codice HTML.

```html
<pre>
    Questo testo
        mantiene la sua
    formattazione
        esattamente come
    l'abbiamo scritta.
</pre>
```

### Combinare i tag

Potete combinare questi tag per creare strutture di testo più complesse. Ecco un esempio che mette insieme molti dei tag che abbiamo visto:

```html
<article>
    <h1>Il mio primo articolo HTML</h1>
    
    <p>Benvenuti nel mio <strong>primo articolo HTML</strong>! Qui impareremo come usare i <em>tag per il testo</em>.</p>
    
    <h2>Perché HTML è importante</h2>
    
    <p>HTML è importante perché:<br>
    1. Struttura il contenuto web<br>
    2. È facile da imparare<br>
    3. È il fondamento del web design</p>
    
    <h3>Una citazione ispiratrice</h3>
    
    <blockquote>
        <p>Il web è più un'innovazione sociale che un'innovazione tecnica.</p>
    </blockquote>
    
    <pre>
        HTML
          È
            Fantastico!
    </pre>
</article>
```

### Conclusione

I tag per il testo sono fondamentali per strutturare e formattare il contenuto delle vostre pagine web. Con questi tag, potete creare titoli, paragrafi, enfatizzare parti importanti del testo e molto altro.

Ricordate:

- Usate i tag `<h1>` a `<h6>` per creare una gerarchia nei vostri titoli
- Il tag `<p>` è il vostro migliore amico per creare paragrafi
- Il tag `<article>` è perfetto per contenuti autonomi
- Ci sono molti altri tag per formattare il testo in modi specifici

## 5. Le liste

Le liste sono uno strumento potente e versatile per organizzare le informazioni nelle vostre pagine web. Le liste sono fantastiche per presentare dati in modo chiaro e strutturato, che si tratti di un elenco della spesa o di una serie di istruzioni complesse.

### Tipi di liste in HTML

In HTML, abbiamo tre tipi principali di liste:

1. Liste non ordinate (Unordered Lists)
2. Liste ordinate (Ordered Lists)
3. Liste di definizioni (Definition Lists)

Vediamole una per una!

### 1. Liste non ordinate (Unordered Lists)

Le liste non ordinate sono utilizzate quando l'ordine degli elementi non è importante. Ogni elemento della lista è preceduto da un punto elenco (bullet point). In HTML, usiamo il tag `<ul>` (unordered list) per creare la lista, e il tag `<li>` (list item) per ogni elemento della lista.

Ecco un esempio:

```html
<h3>La mia lista della spesa:</h3>
<ul>
    <li>Pane</li>
    <li>Latte</li>
    <li>Uova</li>
    <li>Frutta</li>
</ul>
```

Questo codice produrrà una lista come questa:

- Pane
- Latte
- Uova
- Frutta

### 2. Liste ordinate (Ordered Lists)

Le liste ordinate sono utilizzate quando l'ordine degli elementi è importante. Ogni elemento della lista è preceduto da un numero o una lettera. In HTML, usiamo il tag `<ol>` (ordered list) per creare la lista, e ancora il tag `<li>` per ogni elemento.

Ecco un esempio:

```html
<h3>Come preparare un sandwich:</h3>
<ol>
    <li>Prendi due fette di pane</li>
    <li>Spalma il burro su entrambe le fette</li>
    <li>Aggiungi il formaggio e il prosciutto</li>
    <li>Chiudi il sandwich con l'altra fetta di pane</li>
</ol>
```

Questo codice produrrà una lista come questa:

1. Prendi due fette di pane
2. Spalma il burro su entrambe le fette
3. Aggiungi il formaggio e il prosciutto
4. Chiudi il sandwich con l'altra fetta di pane

#### Attributi delle liste ordinate

Le liste ordinate hanno alcuni attributi interessanti che potete utilizzare:

- `type`: Specifica il tipo di numerazione. Può essere "1" (numeri), "A" (lettere maiuscole), "a" (lettere minuscole), "I" (numeri romani maiuscoli), o "i" (numeri romani minuscoli).
- `start`: Specifica il numero di partenza della lista.
- `reversed`: Se presente, inverte l'ordine della numerazione.

Ecco un esempio che utilizza questi attributi:

```html
<ol type="A" start="3" reversed>
    <li>Questo sarà C</li>
    <li>Questo sarà B</li>
    <li>Questo sarà A</li>
</ol>
```

### 3. Liste di definizioni (Definition Lists)

Le liste di definizioni sono utilizzate per creare un elenco di termini e le loro definizioni. Usiamo tre tag per queste liste:

- `<dl>`: Definition List, racchiude l'intera lista
- `<dt>`: Definition Term, per il termine da definire
- `<dd>`: Definition Description, per la definizione del termine

Ecco un esempio:

```html
<h3>Glossario HTML:</h3>
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language, il linguaggio standard per creare pagine web.</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets, utilizzato per definire lo stile di un documento HTML.</dd>
    
    <dt>JavaScript</dt>
    <dd>Un linguaggio di programmazione che permette di creare contenuti interattivi su una pagina web.</dd>
</dl>
```

### Liste annidate

Potete anche creare liste all'interno di altre liste. Questo è utile quando avete bisogno di creare sottocategorie o elenchi più complessi.

Ecco un esempio:

```html
<h3>Le mie attività preferite:</h3>
<ul>
    <li>Sport
        <ol>
            <li>Calcio</li>
            <li>Nuoto</li>
            <li>Basket</li>
        </ol>
    </li>
    <li>Lettura
        <ul>
            <li>Romanzi</li>
            <li>Fumetti</li>
            <li>Riviste scientifiche</li>
        </ul>
    </li>
    <li>Programmazione
        <ol type="a">
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ol>
    </li>
</ul>
```

Questo creerà una lista complessa con sottoliste sia ordinate che non ordinate.

Le liste sono uno strumento potente in HTML per organizzare e presentare informazioni in modo chiaro e strutturato. Che si tratti di elenchi semplici o di strutture più complesse con liste annidate, ora avete gli strumenti per creare liste efficaci nelle vostre pagine web.

Ricordate:

- Usate `<ul>` per liste non ordinate
- Usate `<ol>` per liste ordinate
- Usate `<dl>`, `<dt>` e `<dd>` per liste di definizioni
- Potete annidare le liste per creare strutture più complesse

## 6. I link

I link sono ciò che rende il web "interconnesso", permettendoci di saltare da una pagina all'altra con un semplice clic. Senza link, ogni pagina web sarebbe un'isola isolata nell'oceano di Internet!

### Cos'è un link?

Un link, o collegamento ipertestuale, è un elemento che permette agli utenti di navigare da una pagina web a un'altra (o a una specifica sezione della stessa pagina) cliccando su di esso. In HTML, creiamo i link usando il tag `<a>`, che sta per "anchor" (ancora).

### Anatomia di un link

Ecco la struttura di base di un link in HTML:

```html
<a href="URL">Testo del link</a>
```

Analizziamo le parti di questo tag:

- `<a>`: Questo è il tag di apertura per il link.
- `href`: Questo è un attributo che specifica la destinazione del link. "href" sta per "hypertext reference".
- `"URL"`: Questo è il valore dell'attributo href, ovvero l'indirizzo della pagina a cui il link conduce.
- `Testo del link`: Questo è il testo che l'utente vedrà e su cui potrà cliccare.
- `</a>`: Questo è il tag di chiusura del link.

### Tipi di link

Esistono diversi tipi di link che potete creare in HTML. Vediamone alcuni:

#### 1. Link a pagine esterne

Questi link portano a pagine su altri siti web. Ecco un esempio:

```html
<p>Visita <a href="https://www.example.com">il mio sito web preferito</a>!</p>
```

#### 2. Link a pagine interne del vostro sito

Questi link portano ad altre pagine del vostro stesso sito web. In questo caso, potete usare un percorso relativo:

```html
<p>Vai alla <a href="pagina2.html">seconda pagina</a> del mio sito.</p>
```

#### 3. Link a una specifica sezione della stessa pagina

Potete creare link che portano a una specifica sezione della stessa pagina. Per farlo, dovete prima assegnare un ID all'elemento di destinazione, e poi usare quell'ID nel link preceduto da un cancelletto (#):

```html
<h2 id="sezione2">Sezione 2</h2>
...
<p>Torna alla <a href="#sezione2">Sezione 2</a>.</p>
```

#### 4. Link per inviare email

Potete creare link che, quando cliccati, aprono il client di posta elettronica dell'utente con un nuovo messaggio pronto. Usate "mailto:" seguito dall'indirizzo email:

```html
<p>Contattami via <a href="mailto:mio@email.com">email</a>.</p>
```

#### 5. Link per scaricare file

Per creare un link che permette di scaricare un file, usate l'attributo `download`:

```html
<a href="miofile.pdf" download>Scarica il PDF</a>
```

### Attributi aggiuntivi per i link

Oltre a `href`, ci sono altri attributi utili che potete usare con i link:

#### target

L'attributo `target` specifica dove aprire il documento collegato. I valori più comuni sono:

- `_self`: Apre il documento nello stesso frame/finestra (default)
- `_blank`: Apre il documento in una nuova finestra o tab

Esempio:

```html
<a href="https://www.example.com" target="_blank">Apri in una nuova tab</a>
```

#### title

L'attributo `title` specifica informazioni aggiuntive sul link. Il testo appare come un tooltip quando il mouse passa sopra il link:

```html
<a href="https://www.example.com" title="Visita il sito Example">Example</a>
```

### Stili dei link

Di default, i browser applicano alcuni stili ai link:

- I link non visitati sono generalmente blu e sottolineati
- I link visitati sono generalmente viola e sottolineati
- I link attivi (mentre vengono cliccati) sono generalmente rossi

Potete modificare questi stili usando CSS, ma ne parleremo in un altro capitolo!

### Link e accessibilità

Quando create dei link, è importante pensare all'accessibilità. Ecco alcuni consigli:

1. Usate testo descrittivo per i link. Evitate frasi come "clicca qui" o "leggi di più".
2. Se il link apre in una nuova finestra, è buona pratica informare l'utente:

```html
<a href="https://www.example.com" target="_blank">Visita Example (si apre in una nuova finestra)</a>
```

3. Se il link porta a un file scaricabile, è utile specificare il tipo di file e la dimensione:

```html
<a href="report.pdf" download>Scarica il report (PDF, 2.5MB)</a>
```

### Esempio completo

Ecco un esempio che mette insieme molti dei concetti che abbiamo visto:

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>La mia pagina dei link</title>
</head>
<body>
    <h1>Benvenuti nella mia pagina dei link</h1>
    
    <h2 id="linkesterni">Link esterni</h2>
    <ul>
        <li><a href="https://www.example.com" target="_blank" title="Visita Example">Example</a> (si apre in una nuova finestra)</li>
        <li><a href="https://www.google.com">Google</a></li>
    </ul>
    
    <h2 id="linkinterni">Link interni</h2>
    <ul>
        <li><a href="pagina2.html">Vai alla pagina 2</a></li>
        <li><a href="#linkesterni">Torna ai link esterni</a></li>
    </ul>
    
    <h2>Altri tipi di link</h2>
    <ul>
        <li><a href="mailto:mio@email.com">Contattami via email</a></li>
        <li><a href="documento.pdf" download>Scarica il documento (PDF, 1.2MB)</a></li>
    </ul>
</body>
</html>
```

I link sono fondamentali per la navigazione web. Con il tag `<a>` e i suoi vari attributi, potete creare collegamenti a pagine esterne, a sezioni della stessa pagina, a indirizzi email e persino a file da scaricare.

Ricordate:

- Usate l'attributo `href` per specificare la destinazione del link
- Pensate all'accessibilità quando create i vostri link
- Potete usare attributi come `target` e `title` per aggiungere funzionalità ai vostri link

## 7. Le immagini

Ciao ragazzi! Benvenuti al settimo capitolo del nostro viaggio nel mondo dell'HTML. Oggi parleremo delle immagini, un elemento fondamentale per rendere le vostre pagine web più attraenti e informative. Le immagini possono catturare l'attenzione dei vostri visitatori, illustrare concetti e aggiungere personalità al vostro sito.

### Il tag `<img>`

In HTML, usiamo il tag `<img>` per inserire immagini nelle nostre pagine web. Questo è un tag vuoto, il che significa che non ha un tag di chiusura. Ecco la struttura di base:

```html
<img src="percorso-dell-immagine.jpg" alt="Descrizione dell'immagine">
```

Analizziamo gli attributi principali del tag `<img>`:

#### 1. src (source)

L'attributo `src` specifica il percorso dell'immagine. Può essere un URL completo per immagini su altri siti web, o un percorso relativo per immagini sul vostro sito.

Esempi:

```html
<img src="https://www.example.com/images/foto.jpg">
<img src="images/mia-foto.png">
<img src="../immagini/logo.gif">
```

#### 2. alt (alternative text)

L'attributo `alt` fornisce un testo alternativo per l'immagine. Questo testo viene visualizzato se l'immagine non può essere caricata, ed è letto dagli screen reader per gli utenti ipovedenti. È molto importante per l'accessibilità del vostro sito.

```html
<img src="gatto.jpg" alt="Un gatto soriano che dorme su un cuscino blu">
```

### Formati di immagine comuni

I formati di immagine più comuni sul web sono:

1. **JPEG (.jpg, .jpeg)**: Ideale per fotografie e immagini con molti colori.
2. **PNG (.png)**: Ottimo per immagini con sfondo trasparente o con testo.
3. **GIF (.gif)**: Usato per animazioni semplici e immagini con pochi colori.
4. **SVG (.svg)**: Per grafica vettoriale scalabile, ideale per loghi e icone.
5. **WebP (.webp)**: Un formato moderno che offre buona compressione e qualità.

### Dimensioni delle immagini

Potete specificare le dimensioni di un'immagine usando gli attributi `width` e `height`. Questi valori sono espressi in pixel.

```html
<img src="logo.png" alt="Logo aziendale" width="200" height="100">
```

È una buona pratica specificare sempre le dimensioni delle immagini, in quanto aiuta il browser a riservare lo spazio corretto nella pagina prima che l'immagine sia caricata, riducendo lo spostamento del layout durante il caricamento.

### Immagini come link

Potete trasformare un'immagine in un link racchiudendola in un tag `<a>`:

```html
<a href="https://www.example.com">
    <img src="banner.jpg" alt="Clicca qui per visitare Example.com">
</a>
```

### Ottimizzazione delle immagini

Quando lavorate con le immagini sul web, è importante ottimizzarle per ridurre i tempi di caricamento:

1. Scegliete il formato giusto (JPEG per foto, PNG per grafica con testo, ecc.)
2. Ridimensionate le immagini alle dimensioni effettive in cui verranno visualizzate
3. Comprimete le immagini per ridurne le dimensioni del file
4. Usate strumenti di ottimizzazione delle immagini

### Accessibilità delle immagini

Per rendere le vostre immagini accessibili:

1. Usate sempre l'attributo `alt` con una descrizione significativa
2. Per immagini puramente decorative, usate un `alt` vuoto (`alt=""`)
3. Evitate di inserire testo importante come parte dell'immagine
4. Assicuratevi che ci sia sufficiente contrasto tra il testo e lo sfondo

Le immagini sono un elemento fondamentale del web design moderno. Con il tag `<img>` e i suoi vari attributi, potete aggiungere immagini alle vostre pagine web, renderle responsive e accessibili.

Ricordate:

- Usate sempre l'attributo `alt` per la descrizione delle immagini
- Ottimizzate le vostre immagini per il web