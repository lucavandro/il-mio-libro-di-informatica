# Le funzioni

## 1. Introduzione alle Funzioni in Python

### Cosa sono le Funzioni?

Immagina le funzioni come delle "macchine intelligenti" all'interno del tuo programma. Proprio come una macchina in cucina che trasforma gli ingredienti in un piatto finito, una funzione in programmazione prende alcuni input, li elabora e produce un output.

#### Perché Usare le Funzioni?

Le funzioni sono utili per diverse ragioni:
1. Riutilizzabilità del codice
2. Organizzazione del programma
3. Semplificazione di compiti complessi
4. Riduzione della ripetizione del codice

### Anatomia di una Funzione in Python

Ecco la struttura base di una funzione:

```python
def nome_funzione(parametri):
    ## Corpo della funzione
    ## Operazioni da eseguire
    return risultato
```

Scomponiamo questi elementi:
- `def`: Parola chiave per definire una funzione
- `nome_funzione`: Nome che diamo alla nostra funzione
- `parametri`: Input che la funzione può ricevere (opzionali)
- `return`: Restituisce un valore (opzionale)

#### Esempio Pratico: Funzione di Saluto

```python
def saluta_studente(nome):
    """
    Questa funzione crea un messaggio di saluto personalizzato
    """
    messaggio = f"Ciao {nome}! Benvenuto nel mondo delle funzioni!"
    return messaggio

## Chiamiamo la funzione
risultato = saluta_studente("Marco")
print(risultato)
```

In questo esempio:
- Abbiamo creato una funzione chiamata `saluta_studente`
- Accetta un parametro `nome`
- Genera un messaggio personalizzato
- Restituisce il messaggio con `return`
- Chiamiamo la funzione passando "Marco" come argomento

#### Funzioni Senza Parametri

Le funzioni non devono necessariamente avere parametri:

```python
def stampa_benvenuto():
    """Funzione che stampa un messaggio di benvenuto"""
    print("Benvenuti nel mondo della programmazione Python!")

## Chiamiamo la funzione
stampa_benvenuto()
```

#### Funzioni con Multipli Parametri

```python
def calcola_area_rettangolo(base, altezza):
    """
    Calcola l'area di un rettangolo
    """
    area = base * altezza
    return area

## Chiamiamo la funzione
risultato = calcola_area_rettangolo(5, 3)
print(f"L'area del rettangolo è: {risultato} m²")
```

### Documenti e Commenti

Notate il testo tra `"""`. Questi sono chiamati "docstring" e servono a documentare cosa fa la funzione. Sono molto importanti per rendere il codice comprensibile!

### Esercizi di Pratica

#### Esercizio 1: Funzione di Presentazione
Crea una funzione che prenda nome, età e città e restituisca una frase di presentazione.

```python
def presenta_te(nome, eta, citta):
    ## Scrivi qui il tuo codice
    pass  ## Sostituisci con la tua implementazione
```

#### Esercizio 2: Calcolatore di Medie
Scrivi una funzione che calcoli la media di tre voti.

```python
def calcola_media(voto1, voto2, voto3):
    ## Scrivi qui il tuo codice
    pass  ## Sostituisci con la tua implementazione
```

#### Esercizio 3: Convertitore di Temperature
Crea una funzione che converta i gradi Celsius in Fahrenheit.

```python
def celsius_to_fahrenheit(celsius):
    ## Scrivi qui il tuo codice
    pass  ## Sostituisci con la tua implementazione
```

#### Suggerimenti per gli Esercizi
- Prova a scrivere il codice da solo
- Usa `print()` per verificare i risultati
- Se sei bloccato, prova a pensare passo dopo passo
- Non aver paura di sbagliare, è parte dell'apprendimento!

## 2.Parametri e Argomenti in Python

### Cosa Sono i Parametri e gli Argomenti?

Immagina una funzione come una macchina che può essere configurata in modi diversi. I parametri sono come gli "slot" che puoi riempire quando crei la macchina, mentre gli argomenti sono i valori specifici che inserisci in quegli slot.

#### Differenza tra Parametri e Argomenti

- **Parametri**: Variabili definite quando crei la funzione
- **Argomenti**: Valori concreti che passi quando chiami la funzione

### Tipi di Parametri

#### 1. Parametri Standard

```python
def saluta(nome):
    """Funzione che saluta una persona"""
    print(f"Ciao, {nome}!")

# Chiamate con argomenti
saluta("Mario")
saluta("Laura")
```

#### 2. Parametri con Valori Predefiniti

```python
def calcola_sconto(prezzo, percentuale_sconto=10):
    """
    Calcola il prezzo scontato
    - prezzo: valore originale
    - percentuale_sconto: sconto applicato (default 10%)
    """
    sconto = prezzo * (percentuale_sconto / 100)
    return prezzo - sconto

# Chiamate diverse
print(calcola_sconto(100))        # Usa sconto predefinito 10%
print(calcola_sconto(100, 20))    # Sconto personalizzato 20%
```

#### 3. Argomenti per Parola Chiave

```python
def crea_profilo(nome, eta, citta="Non specificata"):
    """Crea un profilo utente"""
    return f"Nome: {nome}, Età: {eta}, Città: {citta}"

# Chiamate flessibili
print(crea_profilo("Marco", 25))
print(crea_profilo("Giulia", 30, citta="Milano"))
print(crea_profilo(nome="Paolo", eta=40, citta="Roma"))
```

#### 4. Numero Variabile di Argomenti

##### Argomenti con *args (Numero Variabile di Argomenti Posizionali)

```python
def somma_tutto(*numeri):
    """Somma un numero qualsiasi di argomenti"""
    totale = 0
    for numero in numeri:
        totale += numero
    return totale

print(somma_tutto(1, 2, 3))
print(somma_tutto(10, 20, 30, 40, 50))
```

##### Argomenti con **kwargs (Numero Variabile di Argomenti per Parola Chiave)

```python
def stampa_info(**dettagli):
    """Stampa informazioni ricevute come dizionario"""
    for chiave, valore in dettagli.items():
        print(f"{chiave}: {valore}")

stampa_info(nome="Anna", eta=25, lavoro="Studentessa")
```

### Regole Importanti

1. I parametri con valori predefiniti devono essere sempre dopo quelli senza valori predefiniti
2. Puoi combinare diversi tipi di parametri
3. L'ordine dei parametri è importante

#### Esempio Complesso

```python
def funzione_complessa(a, b, *args, opzione=True, **kwargs):
    """
    Esempio di funzione con tutti i tipi di parametri
    - a, b: parametri obbligatori
    - *args: argomenti posizionali aggiuntivi
    - opzione: parametro con valore predefinito
    - **kwargs: argomenti per parola chiave aggiuntivi
    """
    print(f"a: {a}")
    print(f"b: {b}")
    print(f"args: {args}")
    print(f"opzione: {opzione}")
    print(f"kwargs: {kwargs}")

# Chiamata di esempio
funzione_complessa(10, 20, 30, 40, opzione=False, x=100, y=200)
```

### Esercizi di Pratica

#### Esercizio 1: Calcolatore di Medie Flessibile

Crea una funzione che calcoli la media di un numero variabile di voti, con un parametro opzionale per decidere se arrotondare.

```python
def calcola_media(arrotonda=False, *voti):
    # Implementa qui la tua soluzione
    pass
```

#### Esercizio 2: Generatore di Messaggi Personalizzati

Sviluppa una funzione che generi messaggi di auguri personalizzabili.

```python
def auguri(nome, eta=None, **dettagli):
    # Implementa qui la tua soluzione
    pass
```

#### Esercizio 3: Calcolatore di Prezzi con Sconti

Crea una funzione che calcoli il prezzo finale con possibilità di applicare sconti e tasse.

```python
def calcola_prezzo(prezzo_base, sconto=0, iva=22, **extra):
    # Implementa qui la tua soluzione
    pass
```

### Suggerimenti di Studio

- Sperimenta combinando diversi tipi di parametri
- Usa `print()` per capire cosa succede "sotto il cofano"
- Non temere di fare errori, sono parte dell'apprendimento
- Prova a immaginare nuovi modi per usare questi concetti


## 3. Scope e Variabili Locali/Globali in Python

### Il Concetto di Scope: Un Viaggio nell'Universo delle Variabili

Immagina lo scope come un territorio dove le variabili vivono e possono essere utilizzate. Proprio come in una città, ogni "zona" ha regole specifiche su chi può entrare e uscire.

#### Tipi di Scope in Python

1. **Scope Globale**: L'intero programma
2. **Scope Locale**: All'interno di funzioni o metodi
3. **Scope di Funzione**: Interno a una specifica funzione
4. **Scope di Classe**: All'interno di una classe

### Variabili Globali: I Residenti Permanenti

```python
# Variabile globale
numero_studenti = 30

def stampa_info():
    # Posso leggere la variabile globale
    print(f"Numero di studenti: {numero_studenti}")

stampa_info()
```

#### Modificare Variabili Globali: Parola Chiave `global`

```python
contatore = 0  # Variabile globale

def incrementa():
    global contatore  # Dichiaro di voler modificare la variabile globale
    contatore += 1
    return contatore

print(incrementa())  # 1
print(incrementa())  # 2
print(contatore)     # 2
```

### Variabili Locali: Abitanti Temporanei

```python
def calcola_media():
    # Variabile locale
    voti = [7, 8, 6, 9]
    media = sum(voti) / len(voti)
    return media

risultato = calcola_media()
print(risultato)  # 7.5
# print(voti)  # Questo genererebbe un errore!
```

### Scope Nidificati: Un Condominio di Variabili

```python
x = "globale"  # Variabile globale

def esterno():
    x = "esterno"  # Variabile locale di esterno
    
    def interno():
        nonlocal x  # Modifico la variabile dello scope esterno
        x = "interno"
    
    interno()
    print(x)  # Stamperà "interno"

esterno()
```

#### Gerarchia di Ricerca delle Variabili

Python cerca le variabili nell'ordine:
1. Scope locale
2. Scope delle funzioni che contengono
3. Scope globale
4. Built-in scope di Python

### Esempio Complesso: Gestione di Scope Multipli

```python
# Variabile globale
totale_punti = 0

def gestisci_punteggio():
    # Variabile locale
    punteggio_attuale = 100
    
    def aggiungi_bonus():
        nonlocal punteggio_attuale
        global totale_punti
        
        bonus = 50
        punteggio_attuale += bonus
        totale_punti += punteggio_attuale
    
    aggiungi_bonus()
    return punteggio_attuale

risultato = gestisci_punteggio()
print(f"Punteggio: {risultato}")
print(f"Totale Punti Globale: {totale_punti}")
```

### Esercizi di Pratica

#### Esercizio 1: Contatore Globale

```python
# Implementa un contatore globale che può essere incrementato da più funzioni
# ma modificabile solo con un metodo specifico

def inizializza_contatore():
    # Codice qui
    pass

def incrementa_contatore():
    # Codice qui
    pass

def azzera_contatore():
    # Codice qui
    pass
```

#### Esercizio 2: Gestione Punteggio Studente

```python
# Crea un sistema che gestisce il punteggio di uno studente
# con funzioni che possono leggere e modificare il punteggio

def inizializza_punteggio():
    # Codice qui
    pass

def aggiungi_punti():
    # Codice qui
    pass

def sottrai_punti():
    # Codice qui
    pass
```

#### Esercizio 3: Calcolatore con Memoria

```python
# Sviluppa una calcolatrice che mantiene traccia delle operazioni precedenti
# utilizzando variabili globali e locali

def calcola():
    # Implementa operazioni matematiche
    # con memoria delle operazioni precedenti
    pass
```

### Suggerimenti di Approfondimento

- Usa `print()` per tracciare il comportamento delle variabili
- Sperimenta con scope diversi
- Ricorda: meno variabili globali usi, più il codice è pulito
- Pensa sempre alla "visibilità" delle tue variabili

#### Alcuni consigli aggiuntivi per comprendere a fondo questo concetto:

1. Considera lo scope come i "confini" entro cui una variabile può essere vista e modificata
2. Usa `global` e `nonlocal` con parsimonia
3. Cerca sempre di limitare la visibilità delle variabili
4. Pensa alle variabili come a oggetti con dei "permessi" di accesso

## 4. Funzioni con Restituzione Multipla e Ricorsive in Python

### Il Viaggio nel Mondo delle Funzioni Avanzate

Immagina le funzioni come degli "assembler" intelligenti capaci di restituire più oggetti contemporaneamente e di richiamarsi da sole per risolvere problemi complessi.

### Funzioni con Restituzione Multipla

#### Concetto Base

In Python, una funzione può restituire più valori semplicemente separandoli con una virgola.

```python
def analizza_numero(x):
    """
    Funzione che restituisce multiple informazioni su un numero
    """
    # Verifica se il numero è pari
    pari = x % 2 == 0
    
    # Calcola quadrato e cubo
    quadrato = x ** 2
    cubo = x ** 3
    
    # Restituisce multipli valori
    return pari, quadrato, cubo

# Utilizzo della funzione
is_even, square, cube = analizza_numero(4)
print(f"Pari: {is_even}")
print(f"Quadrato: {square}")
print(f"Cubo: {cube}")
```

#### Casi d'Uso Reali

```python
def estrai_info_studente(record):
    """
    Estrae informazioni da un record studente
    """
    nome = record.split(',')[0]
    voto = int(record.split(',')[1])
    promosso = voto >= 6
    
    return nome, voto, promosso

# Esempio
risultato = estrai_info_studente("Marco Rossi,7")
print(risultato)
```

### Funzioni Ricorsive: L'Arte di Richiamarsi

#### Concetto di Ricorsione

Una funzione ricorsiva è una funzione che chiama se stessa per risolvere un problema più piccolo.

##### Esempio Classico: Fattoriale

```python
def fattoriale(n):
    """
    Calcola il fattoriale di un numero usando ricorsione
    """
    # Caso base: fattoriale di 0 o 1 è 1
    if n == 0 or n == 1:
        return 1
    
    # Caso ricorsivo: n! = n * (n-1)!
    return n * fattoriale(n - 1)

# Esempi
print(fattoriale(5))  # 120
print(fattoriale(0))  # 1
```

#### Ricorsione con Fibonacci

```python
def fibonacci(n):
    """
    Calcola il numero di Fibonacci ricorsivamente
    """
    # Casi base
    if n <= 1:
        return n
    
    # Caso ricorsivo
    return fibonacci(n-1) + fibonacci(n-2)

# Calcolo dei primi numeri di Fibonacci
for i in range(10):
    print(f"Fibonacci({i}) = {fibonacci(i)}")
```

#### Strutture Ricorsive: Alberi e Liste Annidate

```python
def somma_lista_ricorsiva(lista):
    """
    Somma elementi in una lista annidata ricorsivamente
    """
    totale = 0
    for elemento in lista:
        # Se l'elemento è una lista, ricorsione
        if isinstance(elemento, list):
            totale += somma_lista_ricorsiva(elemento)
        else:
            totale += elemento
    return totale

# Esempio
lista_nidificata = [1, 2, [3, 4, [5, 6]], 7]
print(somma_lista_ricorsiva(lista_nidificata))  # 28
```

### Esercizi di Pratica

#### Esercizio 1: Restituzione Multipla

```python
def analizza_stringa(testo):
    """
    Crea una funzione che restituisca:
    - Lunghezza della stringa
    - Numero di vocali
    - Se è palindroma
    """
    # Implementa qui la soluzione
    pass
```

#### Esercizio 2: Ricorsione - Somma Progressiva

```python
def somma_progressiva(n):
    """
    Calcola la somma dei primi n numeri ricorsivamente
    """
    # Implementa qui la soluzione
    pass
```

#### Esercizio 3: Ricorsione - Potenza

```python
def potenza_ricorsiva(base, esponente):
    """
    Calcola la potenza usando ricorsione
    Suggerimento: usa casi base e ricorsivi
    """
    # Implementa qui la soluzione
    pass
```

### Consigli di Approfondimento

1. La ricorsione ha un "costo" in termini di memoria
2. Ogni funzione ricorsiva deve avere:
   - Un caso base (per fermarsi)
   - Un caso ricorsivo (per continuare)
3. Non sempre la ricorsione è la soluzione migliore
4. Alcune linguaggi ottimizzano meglio la ricorsione di altri

### Avvertenze Importanti

- La ricorsione può causare "stack overflow" se non gestita correttamente
- Preferisci iterazioni quando possibile
- Usa la ricorsione per problemi che si prestano naturalmente a questo approccio


#### Alcuni suggerimenti mentali per comprendere meglio:
- Pensa alla ricorsione come a una scala: ogni gradino risolve una parte del problema
- Disegna l'albero di ricorsione per visualizzare cosa succede
- Pratica, pratica, pratica!


## 5. Funzioni Lambda e Funzioni di Ordine Superiore in Python

### Viaggio nel Mondo delle Funzioni Eleganti

Immagina le funzioni lambda come piccoli strumenti veloci e versatili, e le funzioni di ordine superiore come macchine intelligenti che possono manipolare altri strumenti. Insieme, creano una programmazione più dinamica e concisa.

### Funzioni Lambda: Funzioni Monouso Istantanee

#### Cosa Sono le Lambda?

Le funzioni lambda sono funzioni "usa e getta", create in una sola riga, perfette per operazioni semplici e immediate.

```python
# Sintassi base
# lambda parametri: espressione

# Esempio di funzione lambda per elevare al quadrato
quadrato = lambda x: x ** 2

print(quadrato(5))  # Output: 25

# Confronto con funzione tradizionale
def quadrato_standard(x):
    return x ** 2

print(quadrato_standard(5))  # Stesso risultato
```

#### Esempi Pratici di Lambda

```python
# Ordinamento con lambda
studenti = [
    {"nome": "Marco", "voto": 8},
    {"nome": "Giulia", "voto": 9},
    {"nome": "Luca", "voto": 7}
]

# Ordinamento per voto
studenti_ordinati = sorted(studenti, key=lambda studente: studente["voto"])
print(studenti_ordinati)
```

### Funzioni di Ordine Superiore

Funzioni che possono accettare altre funzioni come argomenti o restituirle.

#### Map(): Trasformazione di Collezioni

```python
# Raddoppia ogni numero in una lista
numeri = [1, 2, 3, 4, 5]
doppi = list(map(lambda x: x * 2, numeri))
print(doppi)  # [2, 4, 6, 8, 10]

# Map con funzione tradizionale
def raddoppia(x):
    return x * 2

doppi_standard = list(map(raddoppia, numeri))
print(doppi_standard)
```

#### Filter(): Selezione Condizionale

```python
# Filtra numeri pari
numeri = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
pari = list(filter(lambda x: x % 2 == 0, numeri))
print(pari)  # [2, 4, 6, 8, 10]
```

#### Reduce(): Aggregazione di Collezioni

```python
from functools import reduce

# Calcolo del prodotto di tutti i numeri
numeri = [1, 2, 3, 4, 5]
prodotto = reduce(lambda x, y: x * y, numeri)
print(prodotto)  # 120
```

### Combinazione Potente: Lambda e Funzioni di Ordine Superiore

```python
# Esempio complesso: elaborazione dati studenti
studenti = [
    {"nome": "Marco", "voti": [7, 8, 6]},
    {"nome": "Giulia", "voti": [9, 8, 10]},
    {"nome": "Luca", "voti": [6, 7, 5]}
]

# Calcola media voti e filtra studenti promossi
medie = list(map(lambda s: {
    "nome": s["nome"], 
    "media": sum(s["voti"]) / len(s["voti"])
}, studenti))

promossi = list(filter(lambda s: s["media"] >= 6, medie))
print(promossi)
```

### Esercizi di Pratica

#### Esercizio 1: Lambda per Trasformazioni

```python
# Crea funzioni lambda per:
# 1. Convertire temperatura da Celsius a Fahrenheit
# 2. Calcolare il cubo di un numero
# 3. Verificare se una stringa inizia con una vocale
```

#### Esercizio 2: Elaborazione Liste con Funzioni di Ordine Superiore

```python
# Data una lista di numeri:
# 1. Filtra solo i numeri positivi
# 2. Eleva al quadrato i numeri filtrati
# 3. Calcola la somma dei risultati
def elabora_numeri(lista):
    # Implementa qui la soluzione
    pass
```

#### Esercizio 3: Gestione Dati Complessi

```python
# Data una lista di dizionari con informazioni prodotti:
# {"nome": "Laptop", "prezzo": 1000, "categoria": "Elettronica"}
# 1. Filtra prodotti per categoria
# 2. Applica sconto del 10%
# 3. Ordina per prezzo scontato
def processa_prodotti(prodotti):
    # Implementa qui la soluzione
    pass
```

### Consigli di Approfondimento

1. Lambda sono ideali per operazioni semplici e immediate
2. Preferisci funzioni standard per logiche più complesse
3. Combina funzioni di ordine superiore per operazioni potenti
4. Leggi il codice da destra a sinistra per capire l'ordine di esecuzione

### Avvertenze Importanti

- Non appesantire il codice con lambda troppo complesse
- Mantieni la leggibilità del codice
- Usa commenti per spiegare logiche non immediate

**Buona Esplorazione delle Funzioni Dinamiche!** 🚀🐍

#### Suggerimenti per apprendimento:
- Disegna diagrammi di flusso per visualizzare le trasformazioni
- Sperimenta con dati diversi
- Prova a "decomporre" codici complessi in passaggi semplici

## 6. Decoratori in Python - Modificare e Potenziare le Funzioni

### Il Concetto di Decoratore: Un Superpotere per le Funzioni

Immagina i decoratori come degli "amplificatori di funzioni": strumenti magici che possono aggiungere nuove capacità a funzioni esistenti senza modificarne il codice interno. È come dare a una macchina nuove funzionalità semplicemente aggiungendo accessori.

### Anatomia di un Decoratore Base

```python
# Struttura base di un decoratore
def decoratore(funzione_originale):
    def wrapper(*args, **kwargs):
        # Codice da eseguire PRIMA della funzione
        print("Inizio esecuzione")
        
        # Chiamata alla funzione originale
        risultato = funzione_originale(*args, **kwargs)
        
        # Codice da eseguire DOPO la funzione
        print("Fine esecuzione")
        
        return risultato
    
    return wrapper

# Applicazione del decoratore
@decoratore
def saluta(nome):
    print(f"Ciao, {nome}!")

saluta("Marco")
```

### Tipi di Decoratori

#### 1. Decoratori Senza Argomenti

```python
def misura_tempo(funzione):
    """Decoratore che calcola il tempo di esecuzione"""
    import time
    
    def wrapper(*args, **kwargs):
        inizio = time.time()
        risultato = funzione(*args, **kwargs)
        fine = time.time()
        
        print(f"Tempo di esecuzione: {fine - inizio} secondi")
        return risultato
    
    return wrapper

@misura_tempo
def calcolo_lento():
    import time
    time.sleep(2)
    print("Calcolo completato")

calcolo_lento()
```

#### 2. Decoratori con Argomenti

```python
def ripeti(volte):
    """Decoratore che ripete l'esecuzione di una funzione"""
    def decorator(funzione):
        def wrapper(*args, **kwargs):
            for _ in range(volte):
                risultato = funzione(*args, **kwargs)
            return risultato
        return wrapper
    return decorator

@ripeti(3)
def stampa_messaggio(msg):
    print(msg)

stampa_messaggio("Ciao mondo!")
```

#### 3. Decoratori per la Validazione

```python
def valida_tipo(tipo_atteso):
    """Decoratore per la validazione del tipo di ritorno"""
    def decorator(funzione):
        def wrapper(*args, **kwargs):
            risultato = funzione(*args, **kwargs)
            
            if not isinstance(risultato, tipo_atteso):
                raise TypeError(f"Atteso {tipo_atteso}, ricevuto {type(risultato)}")
            
            return risultato
        return wrapper
    return decorator

@valida_tipo(int)
def calcola_eta(anno_nascita):
    from datetime import datetime
    return datetime.now().year - anno_nascita

print(calcola_eta(2000))
```

#### 4. Decoratori di Classe

```python
def singleton(cls):
    """Decoratore che garantisce una sola istanza di una classe"""
    istanze = {}
    def get_instance(*args, **kwargs):
        if cls not in istanze:
            istanze[cls] = cls(*args, **kwargs)
        return istanze[cls]
    return get_instance

@singleton
class Database:
    def __init__(self):
        self.connessione = "Connesso"

# Sempre la stessa istanza
db1 = Database()
db2 = Database()
print(db1 is db2)  # True
```

### Esercizi di Pratica

#### Esercizio 1: Decoratore di Logging

```python
def log_chiamata(funzione):
    """
    Crea un decoratore che:
    - Stampi il nome della funzione chiamata
    - Registri gli argomenti passati
    - Registri il risultato
    """
    # Implementa qui la soluzione
    pass
```

#### Esercizio 2: Decoratore di Cache

```python
def cache_risultati(funzione):
    """
    Implementa un decoratore che:
    - Memorizzi i risultati di funzioni già chiamate
    - Restituisca il risultato cached se gli argomenti sono gli stessi
    """
    # Implementa qui la soluzione
    pass
```

#### Esercizio 3: Decoratore di Autorizzazione

```python
def richiedi_autorizzazione(ruolo_richiesto):
    """
    Crea un decoratore che:
    - Verifichi il ruolo dell'utente prima di eseguire una funzione
    - Blocchi l'esecuzione se il ruolo non è autorizzato
    """
    # Implementa qui la soluzione
    pass
```

### Consigli di Approfondimento

1. I decoratori sono potenti ma possono rendere il codice complesso
2. Usa i decoratori per aspetti trasversali (logging, timing, validazione)
3. Mantieni i decoratori semplici e con un unico scopo
4. Usa `functools.wraps` per preservare i metadati delle funzioni originali

### Cosa Fare e Cosa Evitare

✅ Usa i decoratori per:
- Logging
- Misurazione delle prestazioni
- Validazione
- Gestione delle eccezioni

❌ Evita di usare i decoratori per:
- Logica di business complessa
- Modifiche sostanziali al comportamento delle funzioni

**Buona Esplorazione dei Decoratori!** 🎨🐍

### Suggerimenti per Apprendimento Profondo

- Disegna diagrammi che mostrano il flusso di esecuzione dei decoratori
- Sperimenta combinando più decoratori
- Rifletti su come i decoratori possono semplificare il tuo codice
- Pensa ai decoratori come a "filtri" o "wrapper" che aggiungono funzionalità

Ricorda: un buon decoratore è come un accessorio che migliora una macchina senza modificarne il motore interno.