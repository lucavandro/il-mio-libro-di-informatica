# Le liste

## 1. Introduzione alle liste

Le liste in Python sono strutture dati versatili che permettono di memorizzare una sequenza ordinata di elementi. Possono contenere diversi tipi di dati (numeri, stringhe, oggetti) e sono mutabili, cioè possono essere modificate dopo la loro creazione.

Esempio di creazione di una lista:

```python
frutti = ["mela", "banana", "arancia"]
numeri = [1, 2, 3, 4, 5]
mista = [1, "due", 3.0, True]
```

Le liste possono essere stampate utilizzando la funzione print

```python
frutti = ["mela", "banana", "arancia"]
print(frutti) # Output: ["mela", "banana", "arancia"]
```

Tuttavia, se vogliamo stampare un elemento alla volta possiamo utilizzare il ciclo `for` sostituendo a range il nome della lista, come mostrato nell'esempio sottostante

```python
frutti = ["mela", "banana", "arancia"]
for elmento in frutti:
    print(elemento)
# Output:
# mela
# banana
# arancia
```

## 2. Uso degli indici

### Lettura

Gli elementi di una lista sono accessibili tramite indici. In Python, gli indici partono da 0 per il primo elemento.

Esempio:

```python
frutti = ["mela", "banana", "arancia"]
print(frutti[0])  # Output: mela
print(frutti[2])  # Output: arancia
print(frutti[-1])  # Output: arancia (indice negativo per accedere dall'ultimo elemento)
```

Se utilizziamo un ciclo for per effettuare delle operazioni su ogni elemento della lista e oltre al valore dei ogni elemento abbiamo bisogno del suo indice possiamo utilizzare la funzione `enumerate()` come mostrato nell'esempio sottostante.

```python
frutti = ["mela", "banana", "arancia"]
for indice, elmento in enumerate(frutti):
    print(indice, elemento)
# Output:
# 0 mela
# 1 banana
# 2 arancia
```

### Modifica

Per modificare un elemento, assegniamo un nuovo valore all'indice:

```python
frutti[1] = "kiwi"
print(frutti)  # Output: ["mela", "kiwi", "arancia"]
```

### Cancellazione

Per cancellare un elemento, usiamo la keyword `del`:

```python
del frutti[1]
print(frutti)  # Output: ["mela", "arancia"]
```

Ricorda: dopo la cancellazione, gli indici degli elementi successivi si spostano per riempire lo spazio vuoto.

## 3. Slicing

Lo slicing è una tecnica potente per estrarre sottoliste da una lista esistente. La sintassi generale è:

```python
lista[inizio:fine:passo]
```

Dove:

- `inizio` è l'indice da cui iniziare lo slice (incluso)
- `fine` è l'indice dove terminare lo slice (**escluso**)
- `passo` è l'incremento tra ogni elemento selezionato

Esempio:

```python
numeri = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(numeri[2:7])    # Output: [2, 3, 4, 5, 6]
print(numeri[0:3])    # Output: [0, 1, 2]
```

### Omissione degli indici

Una caratteristica molto utile dello slicing è la possibilità di omettere gli indici quando coincidono con il primo o l'ultimo elemento della lista. Vediamo alcuni esempi:

```python
numeri = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Omissione dell'indice iniziale
print(numeri[:5])  # Equivalente a numeri[0:5]
# Output: [0, 1, 2, 3, 4]

# Omissione dell'indice finale
print(numeri[5:])  # Equivalente a numeri[5:len(numeri)]
# Output: [5, 6, 7, 8, 9]

# Omissione di entrambi gli indici
print(numeri[:])  # Crea una copia dell'intera lista
# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Esempi dettagliati

1. Selezione della prima metà della lista:

   ```python
   prima_meta = numeri[:len(numeri)//2]
   print(prima_meta)  # Output: [0, 1, 2, 3, 4]
   ```

2. Selezione degli ultimi tre elementi:

   ```python
   ultimi_tre = numeri[-3:]
   print(ultimi_tre)  # Output: [7, 8, 9]
   ```

3. Inversione della lista:

   ```python
   inversa = numeri[::-1]
   print(inversa)  # Output: [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
   ```

4. Selezione di elementi pari:

   ```python
   pari = numeri[::2]
   print(pari)  # Output: [0, 2, 4, 6, 8]
   ```

5. Selezione di elementi dispari:

   ```python
   dispari = numeri[1::2]
   print(dispari)  # Output: [1, 3, 5, 7, 9]
   ```

### Considerazioni importanti

- Lo slicing crea sempre una nuova lista, non modifica quella originale.
- L'indice di fine è sempre escluso dallo slice.
- Utilizzare indici negativi può essere utile per contare dalla fine della lista.
- Omettere completamente gli indici (`lista[:]`) è un modo comune per creare una copia superficiale di una lista.

Ricorda che la padronanza dello slicing richiede pratica, ma una volta compreso, diventa uno strumento potente per manipolare le liste in Python.

## 4. Reverse di una lista

Esistono due modi principali per invertire l'ordine degli elementi in una lista: usando il metodo `reverse()` e usando lo slicing `[::-1]`. Questi metodi differiscono nel modo in cui operano sulla lista originale.

### Metodo reverse()

Il metodo `reverse()` è un metodo delle liste che inverte l'ordine degli elementi direttamente nella lista originale. Questa è un'operazione in-place, il che significa che modifica la lista esistente senza crearne una nuova.

Esempio:

```python
frutti = ["mela", "banana", "arancia"]
frutti.reverse()
print(frutti)  # Output: ["arancia", "banana", "mela"]
```

Caratteristiche del metodo `reverse()`:

- Modifica la lista originale
- Non restituisce una nuova lista (restituisce `None`)
- È un'operazione in-place, quindi usa meno memoria

### Slicing [::-1]

Lo slicing `[::-1]` crea una nuova lista con gli elementi della lista originale in ordine inverso. Questa è un'operazione out-of-place, il che significa che non modifica la lista originale ma ne crea una nuova.

Esempio:

```python
frutti = ["mela", "banana", "arancia"]
frutti_invertiti = frutti[::-1]
print(frutti_invertiti)  # Output: ["arancia", "banana", "mela"]
print(frutti)  # Output: ["mela", "banana", "arancia"]
```

Caratteristiche dello slicing `[::-1]`:

- Non modifica la lista originale
- Crea e restituisce una nuova lista
- È un'operazione out-of-place, quindi usa più memoria

### Confronto tra in-place e out-of-place

1. Operazioni in-place (come `reverse()`):
   - Modificano direttamente la struttura dati esistente
   - Sono generalmente più efficienti in termini di memoria
   - Utili quando non si ha bisogno di mantenere la versione originale della lista

2. Operazioni out-of-place (come `[::-1]`):
   - Creano una nuova struttura dati
   - Consumano più memoria poiché creano una copia
   - Utili quando si vuole mantenere la lista originale intatta

### Esempio pratico

```python
numeri = [1, 2, 3, 4, 5]

# Usando reverse() (in-place)
numeri.reverse()
print("Dopo reverse():", numeri)  # Output: [5, 4, 3, 2, 1]

# Resettando la lista
numeri = [1, 2, 3, 4, 5]

# Usando [::-1] (out-of-place)
numeri_invertiti = numeri[::-1]
print("Originale:", numeri)        # Output: [1, 2, 3, 4, 5]
print("Invertita:", numeri_invertiti)  # Output: [5, 4, 3, 2, 1]
```

In questo esempio, possiamo vedere chiaramente come `reverse()` modifica la lista originale, mentre `[::-1]` crea una nuova lista lasciando l'originale intatta.

La scelta tra questi due metodi dipende dalle esigenze specifiche del vostro programma: se avete bisogno di mantenere la lista originale, usate `[::-1]`; se volete modificare la lista esistente e risparmiare memoria, usate `reverse()`.

## 5. Popolare una lista vuota con cicli e input

Popolare una lista vuota è un'operazione comune in programmazione, specialmente quando si lavora con input dell'utente. Vediamo come farlo utilizzando cicli e la funzione `input()`.

### Utilizzo di un ciclo while

Il ciclo `while` è utile quando non sappiamo in anticipo quanti elementi l'utente vorrà inserire.

Esempio:

```python
numeri = []  # Creiamo una lista vuota

print("Inserisci dei numeri. Scrivi 'fine' per terminare.")

while True:
    valore = input("Inserisci un numero: ")
    if valore.lower() == 'fine':
        break
    numeri.append(int(valore))

print("Lista finale:", numeri)
```

In questo esempio:

1. Iniziamo con una lista vuota `numeri`.
2. Usiamo un ciclo `while True` per continuare a chiedere input all'utente.
3. Se l'utente inserisce 'fine', usciamo dal ciclo con `break`.
4. Altrimenti, convertiamo l'input in un intero e lo aggiungiamo alla lista con `append()`.

### Utilizzo di un ciclo for con range

Se sappiamo in anticipo quanti elementi vogliamo nella lista, possiamo usare un ciclo `for` con `range()`.

Esempio:

```python
n = int(input("Quanti numeri vuoi inserire? "))
numeri = []  # Creiamo una lista vuota

for i in range(n):
    valore = int(input(f"Inserisci il numero {i+1}: "))
    numeri.append(valore)

print("Lista finale:", numeri)
```

In questo esempio:

1. Chiediamo all'utente quanti numeri vuole inserire.
2. Usiamo un ciclo `for` che si ripete `n` volte.
3. Ad ogni iterazione, chiediamo un numero e lo aggiungiamo alla lista.

### List Comprehension con input

Per un approccio più conciso, possiamo usare una list comprehension:

```python
n = int(input("Quanti numeri vuoi inserire? "))
numeri = [int(input(f"Inserisci il numero {i+1}: ")) for i in range(n)]

print("Lista finale:", numeri)
```

Questo metodo crea la lista in una sola riga di codice, combinando il ciclo e l'aggiunta degli elementi.

### Gestione degli errori

È importante gestire potenziali errori, come quando l'utente inserisce un valore non valido:

```python
numeri = []

while True:
    valore = input("Inserisci un numero (o 'fine' per terminare): ")
    if valore.lower() == 'fine':
        break
    try:
        numeri.append(float(valore))
    except ValueError:
        print("Valore non valido. Inserisci un numero.")

print("Lista finale:", numeri)
```

Questo esempio usa un blocco `try-except` per gestire input non numerici, permettendo all'utente di correggere eventuali errori.

### Conclusioni

Popolare una lista vuota con input dell'utente è un'operazione versatile che può essere adattata a diverse situazioni:

- Usa il ciclo `while` per una quantità indefinita di input.
- Usa il ciclo `for` quando conosci il numero di elementi in anticipo.
- Usa le list comprehension per un codice più conciso.
- Implementa sempre la gestione degli errori per rendere il tuo programma più robusto.

Questi metodi ti permettono di creare liste dinamiche basate sull'input dell'utente, una competenza fondamentale nella programmazione Python.

## 6. Aggiungere elementi a una lista

Esistono diversi modi per aggiungere elementi a una lista in Python. Esamineremo i metodi più comuni: `append()`, `insert()`, `extend()` e l'operatore `+=`. Ognuno di questi metodi ha un uso specifico e comporta differenze importanti nel risultato.

### 1. Metodo append()

Il metodo `append()` aggiunge un singolo elemento alla fine della lista.

Esempio:

```python
frutti = ["mela", "banana"]
frutti.append("arancia")
print(frutti)  # Output: ["mela", "banana", "arancia"]
```

Caratteristiche di `append()`:

- Aggiunge un solo elemento alla volta
- L'elemento viene sempre aggiunto alla fine della lista
- Modifica la lista originale (operazione in-place)
- Restituisce `None`

### 2. Metodo insert()

Il metodo `insert()` aggiunge un elemento in una posizione specifica della lista.

Esempio:

```python
frutti = ["mela", "banana"]
frutti.insert(1, "kiwi")
print(frutti)  # Output: ["mela", "kiwi", "banana"]
```

Caratteristiche di `insert()`:

- Aggiunge un solo elemento alla volta
- Permette di specificare la posizione esatta dove inserire l'elemento
- Modifica la lista originale (operazione in-place)
- Restituisce `None`

### 3. Metodo extend()

Il metodo `extend()` aggiunge tutti gli elementi di un iterabile (come un'altra lista) alla fine della lista.

Esempio:

```python
frutti = ["mela", "banana"]
altri_frutti = ["kiwi", "arancia"]
frutti.extend(altri_frutti)
print(frutti)  # Output: ["mela", "banana", "kiwi", "arancia"]
```

Caratteristiche di `extend()`:

- Aggiunge più elementi alla volta
- Gli elementi vengono aggiunti alla fine della lista
- Modifica la lista originale (operazione in-place)
- Restituisce `None`

### 4. Operatore +=

L'operatore `+=` è un modo conciso per estendere una lista con gli elementi di un'altra lista o di un iterabile.

Esempio:

```python
frutti = ["mela", "banana"]
frutti += ["kiwi", "arancia"]
print(frutti)  # Output: ["mela", "banana", "kiwi", "arancia"]
```

Caratteristiche dell'operatore `+=`:

- Funziona in modo simile a `extend()`
- Modifica la lista originale (operazione in-place)
- Più conciso di `extend()`
- Può essere usato con qualsiasi iterabile

### Confronto e differenze chiave

1. `append()` vs `extend()`:
   - `append()` aggiunge l'argomento come un singolo elemento, anche se è un iterabile.
   - `extend()` aggiunge ogni elemento dell'iterabile separatamente.

   Esempio:

   ```python
   lista1 = [1, 2, 3]
   lista2 = [4, 5]
   
   lista1.append(lista2)
   print(lista1)  # Output: [1, 2, 3, [4, 5]]
   
   lista1 = [1, 2, 3]  # Resettiamo la lista
   lista1.extend(lista2)
   print(lista1)  # Output: [1, 2, 3, 4, 5]
   ```

2. `insert()` vs altri metodi:
   - `insert()` è l'unico metodo che permette di specificare la posizione esatta dell'inserimento.
   - Gli altri metodi aggiungono sempre alla fine della lista.

3. Operatore `+=` vs `extend()`:
   - `+=` è sostanzialmente equivalente a `extend()`, ma con una sintassi più concisa.
   - Entrambi modificano la lista originale in-place.

### Considerazioni sulla performance

- `append()` è generalmente più veloce di `insert()`, specialmente per liste lunghe, perché non richiede lo spostamento di altri elementi.
- `extend()` e `+=` sono più efficienti per aggiungere molti elementi rispetto a chiamate multiple di `append()`.

### Conclusione

La scelta del metodo dipende dal contesto specifico:

- Usa `append()` per aggiungere un singolo elemento alla fine.
- Usa `insert()` quando hai bisogno di controllo preciso sulla posizione di inserimento.
- Usa `extend()` o `+=` quando devi aggiungere molti elementi da un altro iterabile.

Comprendere le differenze tra questi metodi ti permetterà di scrivere codice più efficiente e leggibile quando lavori con le liste in Python.

## 7. Controllare la presenza di elementi in una lista

Verificare se un elemento è presente in una lista è un'operazione comune in programmazione. Python offre diversi modi per farlo, ciascuno con le proprie caratteristiche. Esamineremo gli operatori `in` e `not in`, e il metodo `index()`.

### 1. Operatore in

L'operatore `in` verifica se un elemento è presente in una lista, restituendo `True` se l'elemento viene trovato, `False` altrimenti.

Esempio:

```python
frutti = ["mela", "banana", "arancia"]
print("banana" in frutti)  # Output: True
print("kiwi" in frutti)    # Output: False
```

Caratteristiche di `in`:

- Semplice e intuitivo da usare
- Restituisce un valore booleano
- Utile in istruzioni condizionali

### 2. Operatore not in

L'operatore `not in` è l'opposto di `in`. Restituisce `True` se l'elemento non è presente nella lista, `False` altrimenti.

Esempio:

```python
frutti = ["mela", "banana", "arancia"]
print("kiwi" not in frutti)  # Output: True
print("mela" not in frutti)  # Output: False
```

Caratteristiche di `not in`:

- Complementare a `in`
- Utile quando si vuole verificare l'assenza di un elemento

### 3. Metodo index()

Il metodo `index()` restituisce l'indice della prima occorrenza dell'elemento specificato. Se l'elemento non è presente, solleva un'eccezione `ValueError`.

Esempio:

```python
frutti = ["mela", "banana", "arancia", "banana"]
print(frutti.index("banana"))  # Output: 1
# print(frutti.index("kiwi"))  # Questo solleverebbe un ValueError
```

Caratteristiche di `index()`:

- Restituisce l'indice dell'elemento
- Solleva un'eccezione se l'elemento non è presente
- Può accettare argomenti opzionali per specificare l'intervallo di ricerca

Uso avanzato di `index()`:

```python
print(frutti.index("banana", 2))  # Output: 3 (cerca a partire dall'indice 2)
```

### Confronto `in` vs `index()` e differenze chiave

1. `in` vs `index()`:
   - `in` è più semplice da usare e non solleva eccezioni
   - `index()` fornisce la posizione dell'elemento, ma può sollevare un'eccezione

2. Prestazioni:
   - `in` e `not in` sono generalmente più veloci per liste non ordinate
   - `index()` può essere più efficiente per liste ordinate, specialmente se si cerca un elemento verso l'inizio della lista

### Esempi pratici

1. Uso di `in` in un'istruzione condizionale:

   ```python
   frutti = ["mela", "banana", "arancia"]
   if "banana" in frutti:
       print("Abbiamo delle banane!")
   ```

2. Gestione sicura di `index()`:

   ```python
   frutti = ["mela", "banana", "arancia"]
   frutto_cercato = "kiwi"
   try:
       posizione = frutti.index(frutto_cercato)
       print(f"{frutto_cercato} trovato all'indice {posizione}")
   except ValueError:
       print(f"{frutto_cercato} non trovato nella lista")
   ```

### Riepilogo

- Usa `in` o `not in` per semplici controlli di presenza/assenza
- Usa `index()` quando hai bisogno di conoscere la posizione dell'elemento
- Ricorda che `index()` può sollevare un'eccezione, quindi gestiscila appropriatamente

La scelta del metodo dipende dalle tue esigenze specifiche: se hai bisogno solo di sapere se un elemento è presente, `in` è la scelta migliore. Se hai bisogno della posizione e sei sicuro che l'elemento sia presente, usa `index()`. Assicurati sempre di gestire potenziali eccezioni quando usi `index()`.

## 8. List Comprehension

Le list comprehension sono un modo conciso e potente di creare nuove liste in Python. Permettono di generare liste in una singola riga di codice, combinando un ciclo e una condizione opzionale. Sono spesso più leggibili e più veloci rispetto ai cicli tradizionali per creare liste.

### Sintassi di base

La sintassi generale di una list comprehension è:

```python
nuova_lista = [espressione for elemento in iterabile if condizione]
```

Dove:

- `espressione` è l'operazione da applicare a ogni elemento
- `elemento` è la variabile che rappresenta ogni item dell'iterabile
- `iterabile` è la sequenza su cui stiamo iterando (es. una lista, una stringa, un range)
- `if condizione` è opzionale e filtra gli elementi

### Esempi di base

1. Creazione di una lista di quadrati:

   ```python
   quadrati = [x**2 for x in range(10)]
   print(quadrati)  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
   ```

2. Filtraggio di numeri pari:

   ```python
   numeri = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
   pari = [x for x in numeri if x % 2 == 0]
   print(pari)  # Output: [2, 4, 6, 8, 10]
   ```

### Esempi avanzati

1. Combinazione di due liste:

   ```python
   frutti = ["mela", "banana", "kiwi"]
   colori = ["rosso", "giallo", "verde"]
   combinazioni = [(frutto, colore) for frutto in frutti for colore in colori]
   print(combinazioni)
   # Output: [('mela', 'rosso'), ('mela', 'giallo'), ('mela', 'verde'),
   #          ('banana', 'rosso'), ('banana', 'giallo'), ('banana', 'verde'),
   #          ('kiwi', 'rosso'), ('kiwi', 'giallo'), ('kiwi', 'verde')]
   ```

2. Appiattimento di una lista di liste:

   ```python
   matrice = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
   appiattita = [num for riga in matrice for num in riga]
   print(appiattita)  # Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```

### Vantaggi delle List Comprehension

1. Concisione: Permettono di scrivere codice più compatto.
2. Leggibilità: Spesso sono più facili da leggere rispetto ai cicli nidificati.
3. Prestazioni: Generalmente più veloci rispetto ai cicli `for` equivalenti.

### Confronto con i cicli tradizionali

List comprehension:

```python
quadrati = [x**2 for x in range(10)]
```

Equivalente con ciclo for:

```python
quadrati = []
for x in range(10):
    quadrati.append(x**2)
```

### Quando usare le List Comprehension

- Per operazioni semplici di trasformazione o filtraggio di liste
- Quando la leggibilità non viene compromessa
- Per migliorare le prestazioni in caso di liste molto grandi

### Quando evitare le List Comprehension

- Per operazioni molto complesse che richiedono più di una riga
- Quando rendono il codice meno leggibile
- Per effetti collaterali (le list comprehension dovrebbero essere usate principalmente per la creazione di nuove liste)