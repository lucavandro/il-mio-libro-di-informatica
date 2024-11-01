# 1. CSS

Il Cascading Style Sheets, comunemente noto come CSS, è un linguaggio fondamentale nel web design moderno. In questo capitolo, esploreremo cos'è il CSS, perché è così importante e come si integra con HTML per creare pagine web accattivanti e funzionali.

## 1.1 Cos'è il CSS?

CSS, acronimo di Cascading Style Sheets, è un linguaggio di stile utilizzato per descrivere la presentazione di un documento scritto in HTML o XML. Il termine "cascading" (a cascata) si riferisce al modo in cui le regole di stile vengono applicate agli elementi di una pagina web, con alcune regole che possono sovrascrivere altre in base alla loro specificità e all'ordine in cui sono dichiarate.

Il CSS controlla l'aspetto visuale di una pagina web, definendo:

- Layout e posizionamento degli elementi
- Colori e sfondi
- Dimensioni e spaziature
- Tipografia
- Animazioni e transizioni
- E molto altro ancora

## 1.2 Perché il CSS è importante?

Il CSS è cruciale nel web design per diversi motivi:

1. **Separazione di struttura e presentazione**: Il CSS permette di separare il contenuto (HTML) dalla sua presentazione, rendendo il codice più pulito, manutenibile e riutilizzabile.

2. **Consistenza del design**: Con il CSS, è possibile applicare stili coerenti a più pagine di un sito web, garantendo un'esperienza utente uniforme.

3. **Responsive design**: Il CSS facilita la creazione di layout responsivi che si adattano a diversi dispositivi e dimensioni dello schermo.

4. **Prestazioni migliorate**: Utilizzando CSS esterni, è possibile ridurre la dimensione dei file HTML e migliorare i tempi di caricamento delle pagine.

5. **Accessibilità**: Il CSS può migliorare l'accessibilità di un sito web, permettendo di adattare la presentazione per diversi tipi di utenti senza modificare il contenuto HTML.

## 1.3 Come funziona il CSS?

Il CSS funziona selezionando elementi HTML e applicando loro delle proprietà di stile. La sintassi di base del CSS è composta da:

1. **Selettore**: Indica quale elemento HTML deve essere stilizzato.
2. **Proprietà**: Specifica quale aspetto dell'elemento deve essere modificato.
3. **Valore**: Definisce il nuovo stile per la proprietà.

Ecco un esempio semplice:

```css
p {
  color: blue;
  font-size: 16px;
}
```

In questo caso, `p` è il selettore (seleziona tutti i paragrafi), `color` e `font-size` sono le proprietà, mentre `blue` e `16px` sono i rispettivi valori.

## 1.4 Come integrare CSS con HTML

Ci sono tre modi principali per incorporare CSS in una pagina HTML:

1. **CSS inline**: Utilizzando l'attributo `style` direttamente nell'elemento HTML.
2. **CSS interno**: Inserendo le regole CSS all'interno di un tag `<style>` nell'`<head>` del documento HTML.
3. **CSS esterno**: Creando un file CSS separato e collegandolo al documento HTML usando il tag `<link>`.

Il metodo più comune e consigliato è l'utilizzo di un file CSS esterno, in quanto offre la massima flessibilità e riutilizzabilità. Come mostrato in questo esempio.

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    ...
</body>
</html>
```

**Nota bene**: il nome `style.css` è del tutto arbitrario. Puoi scegliere il nome che preferisci per i file css.

# Capitolo 2: Selettori CSS

I selettori sono uno degli aspetti fondamentali del CSS. Essi permettono di identificare e selezionare specifici elementi HTML a cui applicare gli stili. In questo capitolo, esploreremo i diversi tipi di selettori CSS e come utilizzarli efficacemente per creare stili precisi e mirati.

## 2.1 Cos'è un selettore CSS?

Un selettore CSS è un pattern utilizzato per selezionare e stilizzare uno o più elementi in una pagina HTML. I selettori sono la chiave per applicare stili in modo mirato e efficiente, permettendo di controllare l'aspetto di elementi specifici senza dover modificare direttamente il markup HTML.

## 2.2 Tipi di selettori base

### 2.2.1 Selettore di elemento

Il selettore di elemento seleziona tutti gli elementi di un determinato tipo.

Esempio:

```css
p {
  color: blue;
}
```

Questo seleziona tutti gli elementi `<p>` e li colora di blu.

### 2.2.2 Selettore di classe

Il selettore di classe seleziona elementi con una specifica classe CSS.

Esempio:

```css
.highlight {
  background-color: yellow;
}
```

Questo seleziona tutti gli elementi con `class="highlight"` e imposta lo sfondo giallo.

### 2.2.3 Selettore di ID

Il selettore di ID seleziona un elemento con uno specifico ID.

Esempio:

```css
#header {
  font-size: 24px;
}
```

Questo seleziona l'elemento con `id="header"` e imposta la dimensione del font a 24 pixel.

## 2.3 Selettori combinatori

### 2.3.1 Selettore discendente

Seleziona un elemento che è discendente di un altro elemento.

Esempio:

```css
article p {
  line-height: 1.5;
}
```

Questo seleziona tutti i `<p>` che sono discendenti di un elemento `<article>`.

### 2.3.2 Selettore figlio diretto

Seleziona un elemento che è figlio diretto di un altro elemento.

Esempio:

```css
ul > li {
  list-style-type: square;
}
```

Questo seleziona tutti i `<li>` che sono figli diretti di un `<ul>`.

### 2.3.3 Selettore fratello adiacente

Seleziona un elemento che è immediatamente preceduto da un altro elemento specifico.

Esempio:

```css
h1 + p {
  font-weight: bold;
}
```

Questo seleziona il primo `<p>` che viene subito dopo un `<h1>`.

## 2.4 Selettori di attributo

Selezionano elementi basati sui loro attributi o valori di attributi.

Esempio:

```css
input[type="text"] {
  border: 1px solid gray;
}
```

Questo seleziona tutti gli `<input>` con `type="text"`.

## 2.5 Pseudo-classi e pseudo-elementi

### 2.5.1 Pseudo-classi

Selezionano elementi in base a uno stato specifico.

Esempio:

```css
a:hover {
  text-decoration: underline;
}
```

Questo applica uno stile quando il mouse passa sopra un link.

### 2.5.2 Pseudo-elementi

Selezionano una parte specifica di un elemento.

Esempio:

```css
p::first-letter {
  font-size: 200%;
  font-weight: bold;
}
```

Questo stilizza la prima lettera di ogni paragrafo.

## 2.6 Specificità dei selettori

La specificità determina quale regola CSS viene applicata quando più regole si riferiscono allo stesso elemento. Comprendere la specificità è cruciale per scrivere CSS efficace e prevedibile.

Ordine di specificità (dal meno specifico al più specifico):

1. Selettori di elemento e pseudo-elementi
2. Selettori di classe, attributo e pseudo-classe
3. Selettori di ID
4. Stili inline

# Capitolo 3: Il Box Model CSS

Il Box Model è uno dei concetti fondamentali del CSS che ogni sviluppatore web deve padroneggiare. Esso descrive come gli elementi HTML vengono rappresentati come "box" nel layout di una pagina, determinando le loro dimensioni e il loro spazio occupato. In questo capitolo, esploreremo in dettaglio il Box Model e come esso influenza il design e il layout delle pagine web.

## 3.1 Cos'è il Box Model?

Il Box Model è un concetto che descrive come ogni elemento HTML è rappresentato come un rettangolo (o "box") con quattro aree principali:
![alt boxmodel](img/box-model.svg "Boxmodel")

1. **Content**: l'area che contiene il contenuto effettivo dell'elemento
2. **Padding**: lo spazio tra il contenuto e il bordo
3. **Border**: il contorno che circonda il padding e il contenuto
4. **Margin**: lo spazio esterno al bordo che separa l'elemento dagli altri elementi

## 3.2 Componenti del Box Model

### 3.2.1 Content

Il content è l'area interna del box dove viene visualizzato il contenuto dell'elemento, come testo o immagini. Le sue dimensioni sono controllate dalle proprietà `width` e `height`.

Esempio:

```css
div {
  width: 300px;
  height: 200px;
}
```

### 3.2.2 Padding

Il padding è lo spazio tra il contenuto e il bordo dell'elemento. Può essere controllato con la proprietà `padding` e le sue varianti direzionali.

Esempio:

```css
div {
  padding: 20px;
  /* oppure */
  padding-top: 10px;
  padding-right: 15px;
  padding-bottom: 10px;
  padding-left: 15px;
}
```

### 3.2.3 Border

Il border è la linea che circonda il padding e il contenuto. Può essere personalizzato in termini di stile, colore e spessore.

Esempio:

```css
div {
  border: 2px solid black;
  /* oppure */
  border-width: 2px;
  border-style: solid;
  border-color: black;
}
```

### 3.2.4 Margin

Il margin è lo spazio esterno al border che separa l'elemento dagli altri elementi circostanti.

Esempio:

```css
div {
  margin: 10px;
  /* oppure */
  margin-top: 10px;
  margin-right: 15px;
  margin-bottom: 10px;
  margin-left: 15px;
}
```

## 3.3 Box Sizing

La proprietà `box-sizing` influenza il modo in cui le dimensioni totali di un elemento vengono calcolate. Ci sono due valori principali:

1. `content-box` (default): `width` e `height` si applicano solo al contenuto
2. `border-box`: `width` e `height` includono padding e border

Esempio:

```css
div {
  box-sizing: border-box;
}
```

## 3.4 Calcolo delle dimensioni totali

Le dimensioni totali di un elemento sono la somma di:

- Content width/height
- Padding (left + right / top + bottom)
- Border width (left + right / top + bottom)
- Margin (left + right / top + bottom)

## 3.5 Collasso dei margini

Il "margin collapsing" è un comportamento del CSS dove i margini verticali di elementi adiacenti si sovrappongono, prendendo il valore del margine più grande.

Esempio:

```css
.element1 {
  margin-bottom: 20px;
}
.element2 {
  margin-top: 30px;
}
/* Lo spazio tra element1 e element2 sarà di 30px, non 50px */
```

## 3.6 Dimensionamento e posizionamento avanzato

### 3.6.1 Proprietà `min-width`, `max-width`, `min-height`, `max-height`

Queste proprietà permettono di impostare limiti alle dimensioni degli elementi, utili per il design responsive.

### 3.6.2 Overflow

La proprietà `overflow` controlla cosa succede quando il contenuto di un elemento è troppo grande per entrare nel box.

Esempio:

```css
div {
  overflow: auto; /* Aggiunge scrollbar se necessario */
}
```

## 3.7 Il Box Model e il layout responsive

Comprendere il Box Model è cruciale per creare layout responsive. Tecniche come l'uso di percentuali per width/height e l'utilizzo di `box-sizing: border-box` sono fondamentali per creare design flessibili.

# Capitolo 3: Il Box Model CSS

Il Box Model è uno dei concetti fondamentali del CSS che ogni sviluppatore web deve padroneggiare. Esso descrive come gli elementi HTML vengono rappresentati come "box" nel layout di una pagina, determinando le loro dimensioni e il loro spazio occupato. In questo capitolo, esploreremo in dettaglio il Box Model e come esso influenza il design e il layout delle pagine web.

## 3.1 Cos'è il Box Model?

Il Box Model è un concetto che descrive come ogni elemento HTML è rappresentato come un rettangolo (o "box") con quattro aree principali:

1. Content: l'area che contiene il contenuto effettivo dell'elemento
2. Padding: lo spazio tra il contenuto e il bordo
3. Border: il contorno che circonda il padding e il contenuto
4. Margin: lo spazio esterno al bordo che separa l'elemento dagli altri elementi

## 3.2 Componenti del Box Model

### 3.2.1 Content

Il content è l'area interna del box dove viene visualizzato il contenuto dell'elemento, come testo o immagini. Le sue dimensioni sono controllate dalle proprietà `width` e `height`.

Esempio:

```css
div {
  width: 300px;
  height: 200px;
}
```

### 3.2.2 Padding

Il padding è lo spazio tra il contenuto e il bordo dell'elemento. Può essere controllato con la proprietà `padding` e le sue varianti direzionali.

Esempio:

```css
div {
  padding: 20px;
  /* oppure */
  padding-top: 10px;
  padding-right: 15px;
  padding-bottom: 10px;
  padding-left: 15px;
}
```

### 3.2.3 Border

Il border è la linea che circonda il padding e il contenuto. Può essere personalizzato in termini di stile, colore e spessore.

Esempio:

```css
div {
  border: 2px solid black;
  /* oppure */
  border-width: 2px;
  border-style: solid;
  border-color: black;
}
```

### 3.2.4 Margin

Il margin è lo spazio esterno al border che separa l'elemento dagli altri elementi circostanti.

Esempio:

```css
div {
  margin: 10px;
  /* oppure */
  margin-top: 10px;
  margin-right: 15px;
  margin-bottom: 10px;
  margin-left: 15px;
}
```

## 3.3 Box Sizing

La proprietà `box-sizing` influenza il modo in cui le dimensioni totali di un elemento vengono calcolate. Ci sono due valori principali:

1. `content-box` (default): `width` e `height` si applicano solo al contenuto
2. `border-box`: `width` e `height` includono padding e border

Esempio:

```css
div {
  box-sizing: border-box;
}
```

## 3.4 Calcolo delle dimensioni totali

Le dimensioni totali di un elemento sono la somma di:

- Content width/height
- Padding (left + right / top + bottom)
- Border width (left + right / top + bottom)
- Margin (left + right / top + bottom)

## 3.5 Collasso dei margini

Il "margin collapsing" è un comportamento del CSS dove i margini verticali di elementi adiacenti si sovrappongono, prendendo il valore del margine più grande.

Esempio:

```css
.element1 {
  margin-bottom: 20px;
}
.element2 {
  margin-top: 30px;
}
/* Lo spazio tra element1 e element2 sarà di 30px, non 50px */
```

## 3.6 Dimensionamento e posizionamento avanzato

### 3.6.1 Proprietà `min-width`, `max-width`, `min-height`, `max-height`

Queste proprietà permettono di impostare limiti alle dimensioni degli elementi, utili per il design responsive.

### 3.6.2 Overflow

La proprietà `overflow` controlla cosa succede quando il contenuto di un elemento è troppo grande per entrare nel box.

Esempio:

```css
div {
  overflow: auto; /* Aggiunge scrollbar se necessario */
}
```

## 3.7 Il Box Model e il layout responsive

Comprendere il Box Model è cruciale per creare layout responsive. Tecniche come l'uso di percentuali per width/height e l'utilizzo di `box-sizing: border-box` sono fondamentali per creare design flessibili.

# Capitolo 4: Layout CSS

Il layout è uno degli aspetti più cruciali del design web. In questo capitolo, esploreremo le varie tecniche e proprietà CSS utilizzate per creare layout flessibili e responsivi. Partiremo dalle basi del flusso normale del documento, per poi approfondire metodi più avanzati di posizionamento e strutturazione del layout.

## 4.1 Flusso normale del documento

Il flusso normale del documento è il modo predefinito in cui gli elementi HTML vengono disposti nella pagina.

### 4.1.1 Block vs Inline

- Elementi block (come `<div>`, `<p>`, `<h1>`): occupano tutta la larghezza disponibile e creano una nuova riga.
- Elementi inline (come `<span>`, `<a>`, `<strong>`): occupano solo lo spazio necessario e non creano nuove righe.

Esempio:
```css
div {
  display: block; /* default per div */
}
span {
  display: inline; /* default per span */
}
```

### 4.1.2 Inline-block

Un compromesso tra block e inline, permettendo di impostare width e height mantenendo il flusso inline.

```css
.inline-block {
  display: inline-block;
  width: 100px;
  height: 100px;
}
```

## 4.2 La proprietà `position`

La proprietà `position` controlla come un elemento è posizionato nel documento.

### 4.2.1 Static

Il valore predefinito, segue il flusso normale del documento.

### 4.2.2 Relative

Posiziona l'elemento relativamente alla sua posizione normale.

```css
.relative {
  position: relative;
  top: 10px;
  left: 20px;
}
```

### 4.2.3 Absolute

Posiziona l'elemento relativamente al suo antenato posizionato più vicino.

```css
.absolute {
  position: absolute;
  top: 50px;
  left: 50px;
}
```

### 4.2.4 Fixed

Posiziona l'elemento relativamente al viewport, rimanendo fisso durante lo scroll.

```css
.fixed {
  position: fixed;
  top: 0;
  right: 0;
}
```

### 4.2.5 Sticky

Un ibrido tra relative e fixed, diventa fixed quando raggiunge una certa soglia durante lo scroll.

```css
.sticky {
  position: sticky;
  top: 20px;
}
```

## 4.3 Floating Elements

La proprietà `float` permette di posizionare un elemento a sinistra o a destra del suo contenitore, facendo fluire il testo intorno ad esso.

```css
.float-left {
  float: left;
  margin-right: 10px;
}
```

### 4.3.1 Clearing Floats

La proprietà `clear` è usata per controllare il comportamento degli elementi accanto a quelli flottanti.

```css
.clear {
  clear: both;
}
```

## 4.4 Flexbox

Flexbox è un modello di layout unidimensionale che offre grande flessibilità nella distribuzione dello spazio e nell'allineamento degli elementi.

### 4.4.1 Flex Container

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### 4.4.2 Flex Items

```css
.item {
  flex: 1;
  /* oppure */
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: auto;
}
```

## 4.5 CSS Grid

CSS Grid è un sistema di layout bidimensionale che offre un controllo preciso su righe e colonne.

### 4.5.1 Grid Container

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}
```

### 4.5.2 Grid Items

```css
.grid-item {
  grid-column: span 2;
  grid-row: 1 / 3;
}
```

## 4.6 Responsive Layout

### 4.6.1 Media Queries

Le media queries permettono di applicare stili diversi basati sulle caratteristiche del dispositivo, come la larghezza dello schermo.

```css
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

### 4.6.2 Unità responsive

Unità come `%`, `vw`, `vh`, `em`, e `rem` sono cruciali per creare layout flessibili.

```css
.responsive-element {
  width: 80%;
  max-width: 1200px;
  font-size: 1.2rem;
}
```

## 4.7 Layout Multi-colonna

La proprietà `column-count` o `column-width` permette di creare layout multi-colonna per il testo.

```css
.multi-column {
  column-count: 3;
  column-gap: 20px;
}
```

# Capitolo 5: CSS Flexbox

Flexbox, abbreviazione di Flexible Box Layout, è un potente modulo di layout CSS progettato per semplificare la creazione di strutture di pagina flessibili e responsive. In questo capitolo, esploreremo in dettaglio come Flexbox funziona e come può essere utilizzato per creare layout complessi con relativa facilità.

## 5.1 Introduzione a Flexbox

Flexbox è un modello di layout unidimensionale che offre un modo efficiente di distribuire lo spazio e allineare gli elementi in un container, anche quando le loro dimensioni sono sconosciute o dinamiche.

### 5.1.1 Concetti chiave

- **Flex container**: L'elemento genitore che ha `display: flex` o `display: inline-flex`.
- **Flex items**: Gli elementi figli diretti di un flex container.
- **Main axis**: L'asse principale lungo il quale i flex items sono disposti.
- **Cross axis**: L'asse perpendicolare al main axis.

## 5.2 Proprietà del Flex Container

### 5.2.1 display

```css
.container {
  display: flex; /* o inline-flex */
}
```

### 5.2.2 flex-direction

Definisce la direzione del main axis.

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

### 5.2.3 flex-wrap

Controlla se i flex items possono andare su più righe.

```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

### 5.2.4 justify-content

Allinea i flex items lungo il main axis.

```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

### 5.2.5 align-items

Allinea i flex items lungo il cross axis.

```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

### 5.2.6 align-content

Allinea le linee di flex items quando c'è spazio extra nel cross axis.

```css
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

## 5.3 Proprietà dei Flex Items

### 5.3.1 order

Controlla l'ordine in cui i flex items appaiono nel container.

```css
.item {
  order: 2; /* default è 0 */
}
```

### 5.3.2 flex-grow

Definisce la capacità di un flex item di crescere se necessario.

```css
.item {
  flex-grow: 1; /* default è 0 */
}
```

### 5.3.3 flex-shrink

Definisce la capacità di un flex item di restringersi se necessario.

```css
.item {
  flex-shrink: 1; /* default è 1 */
}
```

### 5.3.4 flex-basis

Definisce la dimensione di default di un elemento prima che lo spazio rimanente venga distribuito.

```css
.item {
  flex-basis: auto | <length>;
}
```

### 5.3.5 flex

Shorthand per flex-grow, flex-shrink e flex-basis.

```css
.item {
  flex: 0 1 auto; /* default */
  /* o */
  flex: 1; /* equivalente a 1 1 0% */
}
```

### 5.3.6 align-self

Permette di sovrascrivere l'allineamento specificato da align-items.

```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

## 5.4 Esempi pratici di layout con Flexbox

### 5.4.1 Layout a colonne di uguale altezza

```css
.container {
  display: flex;
}
.column {
  flex: 1;
}
```

### 5.4.2 Navigazione responsive

```css
.nav {
  display: flex;
  justify-content: space-between;
}
@media (max-width: 600px) {
  .nav {
    flex-direction: column;
  }
}
```

### 5.4.3 Centrare un elemento verticalmente e orizzontalmente

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

## 5.5 Flexbox vs Grid

Mentre Flexbox è ottimo per layout unidimensionali, CSS Grid è più adatto per layout bidimensionali. Spesso, i due possono essere usati insieme per creare layout complessi e flessibili.

## 5.6 Considerazioni sulla compatibilità dei browser

Flexbox è ampiamente supportato nei browser moderni, ma potrebbero essere necessari alcuni prefissi per versioni più vecchie.

## 5.7 Best practices e pattern comuni

- Usa `flex: 1` per distribuire lo spazio equamente tra i flex items.
- Combina `flex-direction: column` con `height: 100vh` per layout a pagina intera.
- Usa `margin-left: auto` su un flex item per spingerlo all'estrema destra.

# Capitolo 6: CSS Grid

CSS Grid è un potente sistema di layout bidimensionale che offre un controllo preciso sulla disposizione degli elementi in righe e colonne. In questo capitolo, esploreremo in dettaglio come CSS Grid funziona e come può essere utilizzato per creare layout complessi e responsivi.

## 6.1 Introduzione a CSS Grid

CSS Grid è un modello di layout che permette di definire griglie flessibili per organizzare il contenuto. A differenza di Flexbox, che è principalmente unidimensionale, Grid offre controllo sia sulle righe che sulle colonne.

### 6.1.1 Concetti chiave

- **Grid Container**: L'elemento genitore che ha `display: grid`.
- **Grid Items**: Gli elementi figli diretti di un grid container.
- **Grid Lines**: Le linee divisorie che formano la struttura della griglia.
- **Grid Tracks**: Gli spazi tra le grid lines (righe o colonne).
- **Grid Cell**: L'unità più piccola della griglia, l'intersezione tra una riga e una colonna.
- **Grid Area**: Qualsiasi area rettangolare delimitata da quattro grid lines.

## 6.2 Proprietà del Grid Container

### 6.2.1 display

```css
.container {
  display: grid;
}
```

### 6.2.2 grid-template-columns e grid-template-rows

Definiscono la struttura delle colonne e delle righe della griglia.

```css
.container {
  grid-template-columns: 100px 1fr 2fr;
  grid-template-rows: auto 100px 1fr;
}
```

### 6.2.3 grid-template-areas

Definisce un template di aree nominative per la griglia.

```css
.container {
  grid-template-areas: 
    "header header header"
    "sidebar main main"
    "footer footer footer";
}
```

### 6.2.4 gap, column-gap, row-gap

Specificano lo spazio tra le righe e le colonne della griglia.

```css
.container {
  gap: 20px;
  /* o */
  column-gap: 20px;
  row-gap: 10px;
}
```

### 6.2.5 justify-items e align-items

Allineano gli elementi all'interno delle loro celle.

```css
.container {
  justify-items: start | end | center | stretch;
  align-items: start | end | center | stretch;
}
```

### 6.2.6 justify-content e align-content

Allineano l'intera griglia all'interno del container.

```css
.container {
  justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
  align-content: start | end | center | stretch | space-around | space-between | space-evenly;
}
```

## 6.3 Proprietà dei Grid Items

### 6.3.1 grid-column e grid-row

Specificano la posizione e l'estensione di un elemento nella griglia.

```css
.item {
  grid-column: 1 / 3;
  grid-row: 2 / 4;
}
```

### 6.3.2 grid-area

Assegna un nome all'area occupata dall'elemento o specifica la sua posizione.

```css
.item {
  grid-area: header;
  /* o */
  grid-area: 1 / 1 / 3 / 4;
}
```

### 6.3.3 justify-self e align-self

Allineano l'elemento all'interno della sua cella.

```css
.item {
  justify-self: start | end | center | stretch;
  align-self: start | end | center | stretch;
}
```

## 6.4 Funzioni e unità speciali di Grid

### 6.4.1 repeat()

```css
.container {
  grid-template-columns: repeat(3, 1fr);
}
```

### 6.4.2 minmax()

```css
.container {
  grid-template-columns: minmax(100px, 1fr) 2fr 1fr;
}
```

### 6.4.3 fr (fraction unit)

```css
.container {
  grid-template-columns: 1fr 2fr 1fr;
}
```

## 6.5 Layout responsivo con Grid

### 6.5.1 Grid auto-fill e auto-fit

```css
.container {
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

### 6.5.2 Media queries con Grid

```css
@media (max-width: 600px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

## 6.6 Esempi pratici di layout con Grid

### 6.6.1 Layout a 12 colonne

```css
.container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 20px;
}
```

### 6.6.2 Layout "Holy Grail"

```css
.container {
  display: grid;
  grid-template: 
    "header header header" auto
    "nav    main   aside" 1fr
    "footer footer footer" auto
    / 200px 1fr 200px;
}
```

## 6.7 Grid vs Flexbox

Mentre Grid è ideale per layout bidimensionali complessi, Flexbox eccelle in scenari unidimensionali. Spesso, i due possono essere usati insieme per creare layout sofisticati e flessibili.

## 6.8 Considerazioni sulla compatibilità dei browser

CSS Grid è supportato in tutti i browser moderni, ma potrebbe richiedere fallback per browser più vecchi.

## 6.9 Best practices e pattern comuni

- Usa `grid-template-areas` per layout semantici e facili da leggere.
- Combina unità fisse e flessibili per layout responsivi.
- Utilizza Grid per il layout generale della pagina e Flexbox per componenti più piccoli.

# 7. Responsive Design con CSS

Il responsive design è un approccio allo sviluppo web che mira a creare siti che si adattano automaticamente a diversi dispositivi e dimensioni dello schermo. In questo capitolo, esploreremo le tecniche CSS fondamentali per creare layout responsivi e flessibili.

## 7.1 Introduzione al Responsive Design

Il responsive design si basa su tre principi fondamentali:
1. Layout flessibile
2. Immagini e media flessibili
3. Media queries

L'obiettivo è creare un'esperienza utente ottimale su una vasta gamma di dispositivi, dal desktop ai telefoni mobili.

## 7.2 Viewport

Il viewport è l'area visibile di una pagina web su un dispositivo.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Questa meta tag assicura che la larghezza del viewport corrisponda alla larghezza del dispositivo e che la scala iniziale sia 1:1.

## 7.3 Unità Responsive

### 7.3.1 Unità relative

- `em`: Relativa alla dimensione del font dell'elemento genitore
- `rem`: Relativa alla dimensione del font dell'elemento radice (html)
- `vw`: 1% della larghezza del viewport
- `vh`: 1% dell'altezza del viewport
- `%`: Percentuale relativa all'elemento genitore

Esempio:
```css
.container {
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
}

.text {
  font-size: 1rem;
  line-height: 1.5;
}
```

## 7.4 Media Queries

Le media queries permettono di applicare stili CSS basati sulle caratteristiche del dispositivo, come la larghezza dello schermo.

```css
@media screen and (max-width: 600px) {
  .container {
    width: 100%;
    padding: 0 15px;
  }
}
```

### 7.4.1 Breakpoints comuni

- Mobile: 320px - 480px
- Tablet: 481px - 768px
- Desktop: 769px e oltre

```css
/* Mobile */
@media (max-width: 480px) { ... }

/* Tablet */
@media (min-width: 481px) and (max-width: 768px) { ... }

/* Desktop */
@media (min-width: 769px) { ... }
```

## 7.5 Immagini Responsive

### 7.5.1 max-width

```css
img {
  max-width: 100%;
  height: auto;
}
```

### 7.5.2 Picture element

```html
<picture>
  <source srcset="img-large.jpg" media="(min-width: 800px)">
  <source srcset="img-medium.jpg" media="(min-width: 480px)">
  <img src="img-small.jpg" alt="Responsive Image">
</picture>
```

## 7.6 Flexbox per layout responsivi

Flexbox è particolarmente utile per creare layout responsivi.

```css
.container {
  display: flex;
  flex-wrap: wrap;
}

.item {
  flex: 1 1 200px;
}

@media (max-width: 600px) {
  .item {
    flex: 1 1 100%;
  }
}
```

## 7.7 CSS Grid per layout responsivi

CSS Grid offre potenti capacità per layout responsivi.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}
```

## 7.8 Typography Responsive

```css
html {
  font-size: 16px;
}

@media (max-width: 600px) {
  html {
    font-size: 14px;
  }
}

h1 {
  font-size: 2rem;
}

p {
  font-size: 1rem;
  line-height: 1.5;
}
```

## 7.9 Mobile-First vs Desktop-First

### 7.9.1 Mobile-First

Inizia con stili per dispositivi mobili e poi usa media queries per schermi più grandi.

```css
/* Stili di base per mobile */
.element { ... }

/* Tablet */
@media (min-width: 768px) { ... }

/* Desktop */
@media (min-width: 1024px) { ... }
```

### 7.9.2 Desktop-First

Inizia con stili per desktop e poi usa media queries per schermi più piccoli.

```css
/* Stili di base per desktop */
.element { ... }

/* Tablet */
@media (max-width: 1023px) { ... }

/* Mobile */
@media (max-width: 767px) { ... }
```

## 7.10 Performance Considerations

- Usa CSS Flexbox e Grid invece di float per layout responsivi
- Ottimizza le immagini per diverse dimensioni dello schermo
- Minimizza l'uso di media queries per migliorare le prestazioni

## 7.11 Testing

- Usa strumenti come Chrome DevTools per testare il design su diverse dimensioni dello schermo
- Testa su dispositivi reali quando possibile
- Considera l'uso di servizi di testing cross-browser

## 7.12 Accessibilità nel Responsive Design

- Assicurati che il contenuto sia leggibile su tutti i dispositivi
- Mantieni una gerarchia di contenuti coerente
- Usa dimensioni di font e spaziatura adeguate per la leggibilità

