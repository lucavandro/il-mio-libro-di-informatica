# Introduzione alla programmazione con Python

## 1. Programmi e linguaggi

Un programma è una sequenza di istruzioni eseguite da un computer. Python è un linguaggio ad alto livello: usa parole e strutture più vicine al modo in cui descriviamo un procedimento.

Primo programma:

```python
print("Ciao, mondo!")
```

## 2. Variabili

Una variabile associa un nome a un valore.

```python
nome = "Ada"
eta = 15
altezza = 1.68
```

Nomi chiari rendono il programma più facile da leggere:

```python
prezzo_finale = 24.50
```

È meno chiaro:

```python
x = 24.50
```

## 3. Tipi fondamentali

| Tipo | Esempio | Significato |
|---|---|---|
| `int` | `18` | numero intero |
| `float` | `3.14` | numero con parte decimale |
| `str` | `"ciao"` | testo |
| `bool` | `True` | valore logico |

La funzione `type()` mostra il tipo:

```python
valore = 10
print(type(valore))
```

## 4. Input e conversione

`input()` restituisce sempre una stringa:

```python
nome = input("Come ti chiami? ")
print(f"Ciao, {nome}!")
```

Per eseguire calcoli occorre convertire:

```python
eta = int(input("Quanti anni hai? "))
print(f"Tra un anno avrai {eta + 1} anni.")
```

Con numeri decimali si usa `float()`:

```python
base = float(input("Base: "))
altezza = float(input("Altezza: "))
area = base * altezza / 2
print(f"Area: {area:.2f}")
```

## 5. Operatori

| Operatore | Operazione |
|---|---|
| `+` | somma |
| `-` | sottrazione |
| `*` | moltiplicazione |
| `/` | divisione |
| `//` | divisione intera |
| `%` | resto |
| `**` | potenza |

Esempio:

```python
secondi = 3672
ore = secondi // 3600
resto = secondi % 3600
minuti = resto // 60
secondi_rimanenti = resto % 60
print(ore, minuti, secondi_rimanenti)
```

## 6. Stringhe

Le stringhe possono essere unite e misurate:

```python
nome = "Galileo"
cognome = "Galilei"
completo = nome + " " + cognome
print(completo)
print(len(completo))
```

Le f-string inseriscono valori nel testo:

```python
temperatura = 21.456
print(f"Temperatura: {temperatura:.1f} °C")
```

## 7. Numeri casuali

```python
import random

dado = random.randint(1, 6)
print(dado)
```

Il risultato è pseudocasuale: viene prodotto da un algoritmo e non è adatto automaticamente a usi crittografici.

## 8. Errori

Tre categorie utili:

- **errore sintattico**: il codice non rispetta la grammatica;
- **errore di esecuzione**: il problema appare mentre il programma funziona;
- **errore logico**: il programma termina ma produce un risultato sbagliato.

Esempio volutamente errato:

```text
print("Ciao"
```

Il messaggio di errore indica normalmente tipo, file e riga. Va letto dal basso verso l'alto, partendo dall'ultima riga.

## 9. Esercizi

1. Calcola area e perimetro di un rettangolo.
2. Converti una temperatura da Celsius a Fahrenheit.
3. Converti una durata in ore, minuti e secondi.
4. Simula il lancio di due dadi e stampa la somma.
5. Chiedi nome e anno di nascita e costruisci una frase completa.
