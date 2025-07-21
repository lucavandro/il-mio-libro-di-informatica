
# Introduzione alla programmazione

## 1. **Introduzione a Python**

### 1.1 Cos’è la programmazione

Immagina di dover spiegare a un robot come preparare una tazza di tè: dovresti dirgli ogni singolo passaggio, dal prendere la tazza, a mettere l’acqua, fino a mescolare con il cucchiaino. La programmazione è proprio questo: scrivere una serie di istruzioni dettagliate che il computer (il nostro robot) deve seguire per svolgere un compito.

Programmare è come scrivere una ricetta: se dimentichi un passaggio, il risultato non sarà quello che ti aspetti! Con la programmazione puoi creare videogiochi, app, siti web, animazioni, strumenti utili e molto altro. È un superpotere che ti permette di trasformare le tue idee in realtà digitali.

### 1.2 Cos’è Python e perché usarlo

Python è un linguaggio di programmazione creato da Guido van Rossum nei primi anni ’90. Il nome "Python" non deriva dal serpente, ma dal gruppo comico inglese "Monty Python" che faceva ridere molto il suo inventore! Per questo, nella documentazione di Python troverai spesso esempi e battute divertenti.

Python è famoso perché è facile da leggere e da scrivere: sembra quasi inglese! È usato da studenti, scienziati, aziende e persino dalla NASA. Con Python puoi creare giochi, siti web, app, analizzare dati, fare grafica, intelligenza artificiale e molto altro.

**Curiosità:**

- Python è uno dei linguaggi più usati al mondo.
- Il logo ufficiale mostra due serpenti, ma il nome viene dai Monty Python!
- Python è spesso scelto per insegnare a programmare perché il suo codice è semplice e chiaro.

Esempio di codice Python (il classico "Hello World"):

```python
print("Ciao, mondo!")
```

**Perché il primo programma si chiama "Hello World"?**
Per tradizione, il primo programma che si scrive in un nuovo linguaggio stampa a schermo "Hello, World!". È un modo semplice per verificare che tutto funzioni e per salutare il mondo della programmazione!

### 1.3 Come si scrive ed esegue un programma Python (IDLE, editor, terminale)

Per scrivere un programma Python hai tante possibilità, proprio come per scrivere un tema puoi usare carta, penna, computer o tablet:

- **IDLE**: è l’editor che trovi già installato con Python. È semplice e perfetto per chi inizia.
- **Editor di testo**: come Visual Studio Code, Sublime Text, Atom. Questi editor offrono colori, suggerimenti e strumenti che ti aiutano a scrivere meglio.
- **Terminale/Prompt dei comandi**: puoi scrivere il codice in un file con estensione `.py` (ad esempio `programma.py`) e poi eseguirlo con il comando:

  ```bash
  python nomefile.py
  ```

**Curiosità:**
Python è multipiattaforma: puoi usarlo su Windows, Mac e Linux senza cambiare nulla nel codice!

## 2. **Input e Output**

### 2.1 La funzione `print()` per l’output

La funzione `print()` è come un megafono che permette al tuo programma di parlare con te! Serve per mostrare messaggi, risultati di calcoli o qualsiasi informazione tu voglia vedere sullo schermo.

Esempio:

```python
print("Benvenuto nel mio programma!")
```

Puoi stampare anche numeri, operazioni e più valori insieme:

```python
print("La somma di 2 e 3 è", 2 + 3)
```

### 2.2 La funzione `input()` per l’input da tastiera

La funzione `input()` è come una domanda che il computer fa a chi usa il programma. Quando la usi, il programma si ferma e aspetta che l’utente scriva qualcosa e prema Invio.

Esempio:

```python
nome = input("Come ti chiami? ")
print("Ciao,", nome)
```

**Curiosità:**
Quando usi `input()`, tutto quello che l’utente scrive viene salvato come una stringa (cioè testo).

### 2.3 Conversione dei tipi in input (`int()`, `float()`)

Quando chiedi un numero con `input()`, il risultato è sempre una stringa (testo). Se vuoi fare calcoli, devi trasformare la stringa in un numero usando `int()` per gli interi o `float()` per i decimali.

Esempio:

```python
eta = int(input("Quanti anni hai? "))
altezza = float(input("Quanto sei alto (in metri)? "))
```

Se provi a convertire una parola in numero, otterrai un errore!

## 3. **Scrivere codice leggibile**

### 3.1 **Commenti nel codice**

I commenti sono come le note che lasci a te stesso o ai tuoi amici su un quaderno: spiegano cosa fa il codice, ma il computer li ignora completamente. Sono fondamentali per capire il programma anche dopo mesi, o per aiutare chi leggerà il tuo codice.

**Curiosità:**
Spesso nei libri di programmazione troverai variabili chiamate `foo`, `bar` o `baz`. Sono nomi "segnaposto" usati dagli informatici per esempio, un po' come "Tizio, Caio e Sempronio" nei problemi di matematica!

### 3.2 Commenti su una riga (`#`)

Un commento su una riga inizia con il simbolo `#`. Tutto quello che scrivi dopo il `#` non viene eseguito.
  
**Come scrivere il simbolo `#` sulla tastiera italiana**

Sulla tastiera italiana, il simbolo `#` non si trova direttamente tra i tasti principali. Per scriverlo, devi premere la combinazione di tasti:

- <kbd>AltGr</kbd>(il tasto a destra della barra spaziatrice) **+** il tasto <kbd>ò</kbd>

Quindi, tieni premuto <kbd>AltGr</kbd> e poi premi <kbd>ò</kbd>: apparirà il simbolo `#`.

Esempio:

```python
# Questo è un commento su una riga
print("Ciao!")  # Questo commento spiega la riga
```

### 3.3 Commenti multilinea (`''' ... '''` oppure `""" ... """`)

Se vuoi scrivere un commento su più righe, puoi usare tre apici singoli (`''' ... '''`) o tre doppi (`""" ... """`). È come scrivere un paragrafo di spiegazione!

Esempio:

```python
'''
Questo è un commento
su più righe
'''
print("Esempio di commento multilinea")
```

## 4. **Tipi di variabili e valori**

### 4.1 Numeri interi (`int`)

I numeri interi sono numeri senza la virgola, come 5, -3, 100.

Esempio:

```python
eta = 15
```

Quando devi scrivere numeri molto grandi, puoi usare il carattere underscore (`_`) per separare le cifre a gruppi, rendendo il numero più facile da leggere. Ad esempio, invece di scrivere `1000000`, puoi scrivere:

```python
milione = 1_000_000
```

Python ignora gli underscore: il valore della variabile sarà comunque un milione. Questo modo di scrivere non è obbligatorio, ma aiuta molto la leggibilità, soprattutto quando lavori con numeri grandi.

Altri esempi:

```python
popolazione_italia = 59_000_000
numero_di_byte = 4_294_967_296
```

Puoi usare gli underscore dove vuoi tra le cifre, anche ogni tre cifre come nelle notazioni internazionali. È una buona abitudine per evitare errori di lettura o di scrittura nei numeri lunghi!

### 4.2 Numeri decimali (`float`)

I numeri decimali sono quelli che noi chiamiamo _"numeri con la virgola"_.

In informatica questi numeri vengono chiamati _float_ e vengono scritti utilizzando non la virgola ```,``` ma il punto ```.```.

Esempio:

```python
altezza = 1.75
```

**Curiosità:**

- **Perché si usa il punto e non la virgola?**  
    Nei computer, il punto viene usato per separare la parte intera da quella decimale perché è lo standard internazionale (chiamato "notazione anglosassone"). Questo evita confusione tra i diversi paesi: così, in tutto il mondo, `3.14` significa sempre "tre e quattordici", mentre la virgola viene usata solo in alcune lingue come l’italiano.

- **Perché si chiamano "float"?**  
    Il nome _float_ viene da "floating point", cioè "virgola mobile". Questo significa che la posizione della virgola (o meglio, del punto) può "spostarsi" per rappresentare numeri molto grandi o molto piccoli. È come se la virgola potesse galleggiare (float) avanti e indietro per adattarsi al numero che vuoi scrivere!

- **Attenzione agli errori!**  
    Se provi a scrivere `altezza = 1,75` in Python, otterrai un errore, perché Python pensa che tu stia scrivendo due numeri separati da una virgola. Ricorda: per i decimali, usa sempre il punto!

### 4.3 Stringhe (`str`)

Le stringhe sono come collane di lettere: una sequenza di caratteri racchiusa tra virgolette. Puoi scrivere parole, frasi, numeri (come testo), simboli… tutto quello che vuoi!

Esempio:

```python
nome = "Luca"
messaggio = 'Ciao!'
```

### 4.4 Assegnazione di variabili

Una variabile è come una scatola con un’etichetta: puoi metterci dentro un valore e dargli un nome per ritrovarlo facilmente. Per salvare un valore in una variabile basta scrivere:

```python
colore = "blu"
numero = 7
```

### 4.5 Convenzioni di denominazione delle variabili

Quando scegli il nome di una variabile, pensa a una parola che ti aiuti a ricordare cosa contiene quella "scatola". Le regole sono:

- Niente spazi (usa `_` per separare le parole)
- Solo lettere, numeri e `_`
- Non può iniziare con un numero

Esempio:

```python
nome_utente = "Anna"
eta2 = 16
```

**Curiosità:**
Spesso nei manuali si usano nomi come `foo`, `bar` e `baz` per le variabili. Sono nomi "a caso" usati dagli informatici per esempio, un po' come "Tizio, Caio e Sempronio" nei problemi di matematica. Ma tu scegli nomi che abbiano senso per il tuo programma!

### 4.6 **Uso della funzione `type()`** per riconoscere il tipo di una variabile

Ogni variabile in Python ha un "tipo", cioè una categoria che dice al computer che cosa contiene (numero, testo, ecc.). La funzione `type()` è come una lente d’ingrandimento che ti permette di vedere il tipo di una variabile.

Esempio:

```python
print(type(5))        # <class 'int'>
print(type(3.14))     # <class 'float'>
print(type("ciao"))  # <class 'str'>
```

## 5. **Operazioni aritmetiche fondamentali**

### 5.1 Addizione, sottrazione, moltiplicazione, divisione

Le operazioni aritmetiche sono come le operazioni che fai ogni giorno: contare le caramelle, dividere una pizza, moltiplicare i punti di un gioco. In Python puoi usare i simboli `+`, `-`, `*`, `/` per fare calcoli.

Esempi:

```python
somma = 5 + 3        # 8
diff = 10 - 4        # 6
prodotto = 2 * 6     # 12
divisione = 8 / 2    # 4.0
```

### 5.2 Divisione intera (`//`)

La divisione intera è come dividere le caramelle tra amici e ignorare gli avanzi: ti interessa solo quante caramelle riceve ciascuno, non il resto.

```python
print(7 // 2)   # 3
```

### 5.3 Modulo (`%`)

Il modulo (`%`) restituisce il resto della divisione. È come vedere quante caramelle avanzano dopo averle divise tra gli amici.

```python
print(7 % 2)    # 1
```

### 5.4 Elevamento a potenza (`**`)

Per elevare un numero a potenza (ad esempio 2 alla terza), usa `**`.

```python
print(2 ** 3)   # 8
```

Puoi usare lo stesso operatore anche per calcolare le radici. Ad esempio, la radice quadrata di un numero si ottiene elevandolo alla potenza `0.5` (cioè alla "mezzo"):

```python
print(9 ** 0.5)   # 3.0
print(16 ** 0.5)  # 4.0
```

Allo stesso modo, la radice cubica si calcola con l’esponente `1/3`:

```python
print(27 ** (1/3))  # 3.0
```

Un altro modo per calcolare la radice quadrata è usare la funzione `sqrt` del modulo `math`. Prima devi importare il modulo:

```python
from math import sqrt
print(sqrt(9))   # 3.0
```

**Differenze tra `**` e `math.sqrt`:**

- L’operatore `**` è più generico: puoi usarlo per qualsiasi potenza o radice.
- `sqrt` è specifico per la radice quadrata e può essere più leggibile quando vuoi solo quella.

Scegli il metodo che ti sembra più chiaro per il tuo programma!
**Curiosità:**  
Il nome `sqrt` è l'abbreviazione di "square root", che in inglese significa "radice quadrata". In matematica, la radice quadrata di un numero è il valore che, moltiplicato per sé stesso, dà quel numero. Ad esempio, la radice quadrata di 9 è 3, perché 3 × 3 = 9. Quindi, la funzione `sqrt` serve proprio a calcolare la radice quadrata di un numero!

### 5.5 Incremento e decremento di una variabile (`x = x + 1`, `x += 1`, ecc.)

Per aumentare o diminuire il valore di una variabile puoi usare queste scorciatoie:

```python
x = 5
x = x + 1   # x ora vale 6
x += 1      # x ora vale 7
x -= 2      # x ora vale 5
```

Questa tecnica non si usa solo per sommare o sottrarre, ma funziona con tutte le operazioni matematiche di base. Basta cambiare il simbolo:

- **Addizione:** `x += numero` (aggiunge un valore)
- **Sottrazione:** `x -= numero` (sottrae un valore)
- **Moltiplicazione:** `x *= numero` (moltiplica per un valore)
- **Divisione:** `x /= numero` (divide per un valore)
- **Divisione intera:** `x //= numero` (divide interamente per un valore)
- **Modulo:** `x %= numero` (assegna il resto della divisione)
- **Potenza:** `x **= numero` (eleva a potenza)

Esempi pratici:

```python
punteggio = 10
punteggio += 5   # punteggio ora vale 15

monete = 20
monete -= 3      # monete ora vale 17

distanza = 8
distanza *= 2    # distanza ora vale 16

tempo = 60
tempo /= 4       # tempo ora vale 15.0

numero = 7
numero %= 3      # numero ora vale 1 (perché 7 diviso 3 dà resto 1)
```

Questi operatori rendono il codice più corto e facile da leggere!

### 5.6 **Uso della funzione `abs()`** per il valore assoluto

La funzione `abs()` restituisce il valore assoluto di un numero, cioè quanto è "lontano da zero" senza considerare il segno. È utile per sapere la distanza tra due numeri, anche se uno è negativo.

```python
print(abs(-10))   # 10
```

## 6. **Stringhe e formattazione**

### 6.1 Concatenazione di stringhe

Unire due o più stringhe si chiama concatenazione.

```python
nome = "Luca"
saluto = "Ciao, " + nome
print(saluto)   # Ciao, Luca
```

### 6.2 f-string per la formattazione dell’output

Le f-string sono un modo moderno e pratico per "infilare" il valore delle variabili dentro una stringa, senza doverle concatenare. Basta mettere una `f` davanti alle virgolette e racchiudere le variabili tra parentesi graffe `{}`.

Esempio:

```python
nome = "Anna"
eta = 16
print(f"Ciao {nome}, hai {eta} anni.")
```

### 6.3 **Uso della funzione `len()`** per la lunghezza delle stringhe

La funzione `len()` conta quanti caratteri ci sono in una stringa, proprio come contare le lettere di una parola o i mattoncini di una torre.

```python
testo = "Python"
print(len(testo))   # 6
```

## 7. **Generazione di numeri casuali**

### 7.1 Importazione del modulo `random`

Per generare numeri casuali (come tirare un dado o scegliere una carta a caso) bisogna importare il modulo `random`, che contiene tante funzioni utili per la "casualità".

```python
import random
```

### 7.2 Uso di `random.randint()` e funzioni simili

`random.randint(a, b)` restituisce un numero intero casuale tra `a` e `b` (inclusi). È come estrarre un biglietto da un sacchetto!

Esempio:

```python
import random
numero = random.randint(1, 10)
print("Numero casuale:", numero)
```

## 8. **Strumenti di supporto e debugging**

### 8.1 **Errori comuni e debugging di base**

Quando scrivi codice, può capitare di fare errori (bug). Un bug è come un sassolino nella scarpa: ti impedisce di andare avanti finché non lo togli! Python ti mostra un messaggio di errore che ti aiuta a capire dove hai sbagliato. Se il programma non funziona, leggi con attenzione il messaggio e prova a correggere il codice.

Esempio di errore:

```python
print("Ciao"
# Manca la parentesi finale!
```

**Curiosità:**
Il termine "bug" viene da un vero insetto (bug in inglese) trovato dentro un vecchio computer negli anni '40!

### 8.2 **Accenno alla documentazione e all’aiuto in Python**  (`help()`, docstring)

Python ha una documentazione molto ricca, come un grande manuale delle istruzioni. Puoi usare la funzione `help()` per scoprire come funziona una funzione o un oggetto.

Esempio:

```python
help(print)
```

Molte funzioni e oggetti hanno una "docstring", cioè una breve descrizione che puoi leggere con `help()` o passando il mouse sopra il nome della funzione nell’editor. Imparare a leggere la documentazione ti renderà sempre più autonomo!
