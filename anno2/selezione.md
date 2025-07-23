# La selezione

## 1. Principi di logica booleana

### 1.1 Valori booleani (`True`, `False`)

Immagina un interruttore della luce: può essere solo acceso o spento. In informatica, questi due stati si chiamano valori booleani: `True` (vero) e `False` (falso). Sono le fondamenta della logica nei programmi!

Esempio:

```python
luce_accesa = True
luce_spenta = False
```

### 1.2 Operatori di confronto (`>`, `<`, `>=`, `<=`, `==`, `!=`)

Gli operatori di confronto sono come le bilance: servono a confrontare due valori e rispondere con `True` o `False`.

#### **Attenzione speciale: `==` NON è `=`!**

Molti studenti confondono `==` con `=`. Sono due cose **completamente diverse**:

- `=` è l’**assegnazione**: serve per dare un valore a una variabile.
- `==` è il **confronto**: serve per verificare se due valori sono uguali.

**Esempi:**

```python
# Assegnazione
x = 5        # Qui stai dicendo: "x diventa 5"

# Confronto
print(x == 5)  # Qui stai chiedendo: "x è uguale a 5?" (Risposta: True)
```

Se usi `=` al posto di `==` in un confronto, Python ti darà errore!

**Ricorda:**  

- `=` → assegna  
- `==` → confronta

**Trucchetto per non sbagliare:**  
Quando vuoi fare una domanda ("sono uguali?"), usa **due uguali**: `==`.

Esempi di confronto:

```python
print(5 > 3)    # True
print(2 == 2)   # True
print(7 != 4)   # True
print(10 <= 5)  # False
```

### 1.3 Operatori logici (`and`, `or`, `not`)

Gli operatori logici permettono di combinare più condizioni, rendendo i controlli nei programmi molto più potenti. Vediamoli uno per uno, introducendo anche il concetto di **tabella di verità**, che mostra il risultato di ogni possibile combinazione.

#### **Operatore `and`**

`and` restituisce `True` solo se **entrambe** le condizioni sono vere.

**Tabella di verità per `and`:**

| A     | B     | A and B |
|-------|-------|---------|
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

**Esempio:**

```python
eta = 15
iscritto = True
print(eta > 14 and iscritto)  # True, perché entrambe le condizioni sono vere
```

---

#### **Operatore `or`**

`or` restituisce `True` se **almeno una** delle condizioni è vera.

**Tabella di verità per `or`:**

| A     | B     | A or B  |
|-------|-------|---------|
| True  | True  | True    |
| True  | False | True    |
| False | True  | True    |
| False | False | False   |

**Esempio:**

```python
punti = 800
bonus = True
print(punti >= 1000 or bonus)  # True, perché almeno una condizione è vera
```

---

#### **Operatore `not`**

`not` capovolge il valore di una condizione: trasforma `True` in `False` e viceversa.

**Tabella di verità per `not`:**

| A     | not A |
|-------|-------|
| True  | False |
| False | True  |

**Esempio:**

```python
is_online = False
print(not is_online)  # True, perché la condizione era False
```

---

### Approfondimento: Le leggi di De Morgan

Le **leggi di De Morgan** sono regole fondamentali della logica booleana che spiegano come negare combinazioni di condizioni. Sono molto utili in informatica, perché permettono di riscrivere espressioni logiche in modo più semplice e leggibile, evitando errori e facilitando la comprensione del codice.

#### Cosa dicono le leggi di De Morgan?

Le leggi sono due:

- `not (A and B)` è equivalente a `not A or not B`
- `not (A or B)` è equivalente a `not A and not B`

In altre parole, la negazione di una combinazione di condizioni può essere trasformata in una combinazione di negazioni.

#### Perché sono importanti?

- **Semplificazione del codice:** Permettono di riscrivere condizioni complesse in modo più chiaro.
- **Evita errori logici:** Aiutano a non confondersi quando si devono negare espressioni con più condizioni.
- **Utile nei filtri e nelle query:** Spesso, quando si lavora con dati (ad esempio, filtrando una lista), è necessario invertire condizioni multiple.

#### Esempi pratici

Supponiamo di voler selezionare gli utenti che **non** sono maggiorenni **e** **non** sono iscritti:

```python
# Versione con not (A and B)
if not (eta >= 18 and iscritto):
    print("Utente non maggiorenne o non iscritto")
```

Usando la legge di De Morgan, possiamo riscrivere così:

```python
if eta < 18 or not iscritto:
    print("Utente non maggiorenne o non iscritto")
```

Entrambe le condizioni sono equivalenti, ma la seconda è spesso più facile da leggere e da modificare.

Altro esempio con una lista di accesso:

```python
# Vogliamo negare: "l'utente è admin o è moderatore"
if not (utente == "admin" or utente == "moderatore"):
    print("Accesso negato")
```

Con De Morgan:

```python
if utente != "admin" and utente != "moderatore":
    print("Accesso negato")
```

#### Tabella di verità

Vediamo la tabella di verità per la prima legge:

| A     | B     | A and B | not (A and B) | not A | not B | not A or not B |
|-------|-------|---------|---------------|-------|-------|----------------|
| True  | True  | True    | False         | False | False | False          |
| True  | False | False   | True          | False | True  | True           |
| False | True  | False   | True          | True  | False | True           |
| False | False | False   | True          | True  | True  | True           |

Come si vede, `not (A and B)` e `not A or not B` danno sempre lo stesso risultato.

#### Casi d’uso comuni

- **Filtri su dati:** Negare condizioni di ricerca.
- **Validazione input:** Quando si vuole accettare solo chi NON soddisfa certe condizioni.
- **Controlli di sicurezza:** Negare l’accesso a chi non ha nessuno dei permessi richiesti.

#### Curiosità: Chi era Augustus De Morgan?

Augustus De Morgan (1806–1871) è stato un matematico e logico britannico, famoso per aver formalizzato queste leggi che portano il suo nome. De Morgan ha lavorato molto sulla logica matematica e sulla teoria degli insiemi, contribuendo a rendere la logica una disciplina rigorosa e applicabile anche all’informatica moderna. Era noto per il suo spirito critico e per la chiarezza delle sue spiegazioni. La sua influenza si vede ancora oggi: ogni volta che scrivi una condizione booleana in Python, stai usando le idee di De Morgan!

### 1.4 Altri operatori booleani (`in`, `not in`, `is`, `is not`)

Questi operatori permettono di fare controlli più avanzati su stringhe, liste e variabili.

#### 1.4.1 Operatori `in` e `not in`

Servono per verificare se un elemento è presente (o assente) in una sequenza (come una stringa o una lista).

Esempi:

```python
nome = "Luca"
print("a" in nome)        # True, perché "a" è presente in "Luca"
print("z" not in nome)    # True, perché "z" NON è presente in "Luca"
```

#### 1.4.2 Operatori `is` e `is not`

Questi confrontano **l'identità** degli oggetti, cioè verificano se due variabili puntano esattamente allo stesso oggetto in memoria. Non vanno confusi con `==`, che confronta solo il **valore**.

Esempi:

```python
x = "ciao"
y = "ciao"
print(x == y)    # True, stesso valore
print(x is y)    # True in questo caso, ma solo perché le stringhe uguali spesso condividono la memoria
```

**Attenzione:** Usa `is` solo per confrontare identità (ad esempio con `None`: `if x is None:`), mentre per confrontare valori usa sempre `==`.

**Curiosità:**
Il nome "booleano" viene da George Boole, un matematico che ha inventato questa logica più di 150 anni fa!
A proposito di George Boole, sai che morì in un modo...particolare? Se vuoi scoprirlo, ascolta questa puntata del podcast __Vite da logico__ 

<iframe width="560" height="315" src="https://www.youtube.com/embed/Img6rBKagCI?si=odrc2gHDKHcQol9P" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Esercizi capitolo 1

- Verifica se il numero di follower di un influencer è maggiore di 10.000.
- Controlla se il nome di un videogioco preferito contiene la lettera "a".
- Scrivi una condizione che sia vera solo se hai più di 13 anni **e** sei iscritto a una squadra sportiva.
- Verifica se la parola "Python" contiene la lettera "y".
- Controlla se due variabili che rappresentano il punteggio di due squadre sono uguali.

## 2. Indentazione in Python

### 2.1 Perché è importante l'indentazione

In Python, l’indentazione (gli spazi all’inizio della riga) è come la punteggiatura in una frase: senza, il significato si perde! Serve a dire al computer quali istruzioni appartengono allo stesso blocco, ad esempio dentro un if.

Esempio:

```python
if True:
    print("Questa riga è dentro l'if!")
print("Questa riga è fuori dall'if!")
```

### 2.2 Esempi di errore senza indentazione

Se dimentichi l’indentazione, Python si arrabbia e ti mostra un errore chiamato `IndentationError`.

Esempio:

```python
if True:
print("Errore! Questa riga non è indentata.")
```

### Esercizi capitolo 2

- Scrivi un if che stampi "Bravo!" se il punteggio è maggiore di 90, ricordandoti di indentare correttamente.
- Prova a togliere l’indentazione a una riga dentro un if e osserva l’errore che compare.
- Crea un programma che stampi un messaggio solo se una variabile è `True`.
- Scrivi un if annidato (un if dentro un altro) e spiega con un commento dove serve l’indentazione.

## 3. Uso dell’if

### 3.1 if semplice (senza else)

L’istruzione `if` è come un bivio: "Se succede questa cosa, allora fai questo". Se la condizione è vera, il blocco viene eseguito; altrimenti viene saltato.

Esempio:

```python
eta = 16
if eta >= 14:
    print("Puoi iscriverti al torneo!")
```

### 3.2 if con else

`else` è il "piano B": se la condizione dell’if non è vera, allora si esegue il blocco dell’else.

Esempio:

```python
livello = 5
if livello > 10:
    print("Hai sbloccato il boss segreto!")
else:
    print("Continua a giocare per salire di livello!")
```

### 3.3 if con elif

`elif` significa "altrimenti, se...". Serve quando ci sono più di due possibilità.

Esempio:

```python
voto = 7
if voto >= 9:
    print("Ottimo!")
elif voto >= 6:
    print("Sufficiente")
else:
    print("Da migliorare")
```

### 3.4 Annidamento di if

Puoi mettere un if dentro un altro if, come le scatole cinesi. Serve per controllare condizioni più complesse.

Esempio:

```python
utente = "admin"
password = "1234"
if utente == "admin":
    if password == "1234":
        print("Accesso consentito")
    else:
        print("Password errata")
else:
    print("Utente sconosciuto")
```

### Esercizi capitolo 3

- Scrivi un programma che controlla se la temperatura è sotto zero e stampa un messaggio di allerta.
- Crea un quiz che stampa "Risposta esatta!" se l’utente inserisce la risposta giusta, altrimenti "Ritenta".
- Simula un controllo di età per l’accesso a un social network.
- Scrivi un programma che assegna un giudizio ("Ottimo", "Buono", "Sufficiente", "Insufficiente") in base al voto inserito.
- Crea un sistema di login che controlla utente e password.

## 4. Costrutto pass

### 4.1 Quando serve e perché

A volte vuoi scrivere un if (o un altro blocco) ma non sai ancora cosa metterci dentro. In questi casi puoi usare `pass`, che dice a Python di non fare nulla, ma senza generare errori. È come mettere un segnaposto!

Esempio:

```python
if True:
    pass  # Da completare in futuro
```

**Curiosità:**
`pass` si usa spesso quando stai progettando il programma e vuoi "riservare" uno spazio per il codice che scriverai dopo.

### Esercizi capitolo 4

- Scrivi un if che controlla se un giocatore ha vinto, ma lascia il blocco vuoto usando `pass`.
- Crea una funzione che per ora non fa nulla, usando `pass`.
- Progetta un menu di un videogioco con le voci principali, ma lascia alcune opzioni vuote con `pass`.

## 5. Operatore ternario

### 5.1 Sintassi e semplici esempi

L’operatore ternario è un modo compatto per scrivere un if-else in una sola riga. È come una scorciatoia!

Esempio:

```python
eta = 18
messaggio = "Maggiorenne" if eta >= 18 else "Minorenne"
print(messaggio)
```

**Curiosità:**
Si chiama "ternario" perché coinvolge tre elementi: la condizione, il valore se vero, il valore se falso.

### Esercizi capitolo 5

- Scrivi un programma che stampa "Pari" o "Dispari" usando l’operatore ternario.
- Crea una variabile che contiene "Promosso" o "Bocciato" in base al voto inserito.
- Usa l’operatore ternario per scegliere tra due squadre vincitrici in una partita.

## 6. Confronto tra valori e variabili

### 6.1 Confronto tra numeri

Puoi confrontare numeri per sapere chi ha vinto una gara, chi ha segnato più punti, chi è più veloce…

Esempio:

```python
tempo_gara1 = 12.5
tempo_gara2 = 11.8
if tempo_gara1 < tempo_gara2:
    print("La prima gara è stata più lenta")
else:
    print("La seconda gara è stata più lenta")
```

### 6.2 Confronto tra stringhe

Anche le stringhe si possono confrontare: ad esempio, per vedere se due nomi sono uguali o se una parola viene prima di un’altra in ordine alfabetico.

Esempio:

```python
nome1 = "Anna"
nome2 = "Luca"
if nome1 < nome2:
    print(f"{nome1} viene prima di {nome2}")
```

### 6.3 Confronto tra variabili

Puoi confrontare qualsiasi tipo di variabile, purché abbia senso (ad esempio, non puoi confrontare direttamente un numero e una stringa).

Esempio:

```python
livello1 = 5
livello2 = 7
if livello1 == livello2:
    print("I due giocatori sono allo stesso livello")
else:
    print("I livelli sono diversi")
```

### Esercizi capitolo 6

- Confronta il numero di like di due post su un social e stampa quale ha più successo.
- Scrivi un programma che controlla se due nomi di attori sono uguali.
- Crea un quiz che chiede all’utente di indovinare se un numero segreto è maggiore o minore di un valore dato.
- Confronta i punteggi di due squadre di calcio e stampa chi ha vinto o se c’è pareggio.
