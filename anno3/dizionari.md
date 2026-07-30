# Dizionari

## 1. Coppie chiave-valore

Un dizionario associa una chiave a un valore.

```python
studente = {
    "nome": "Ada",
    "classe": "3A",
    "media": 8.2
}

print(studente["nome"])
```

Le chiavi devono essere uniche.

## 2. Leggere e modificare

```python
studente["media"] = 8.5
studente["email"] = "ada@example.org"

telefono = studente.get("telefono")
print(telefono)
```

`get()` restituisce `None`, o un valore scelto, quando la chiave non esiste:

```python
telefono = studente.get("telefono", "non disponibile")
```

## 3. Attraversare

```python
for chiave, valore in studente.items():
    print(chiave, valore)
```

## 4. Dizionari e liste

```python
classe = [
    {"nome": "Ada", "voti": [8, 9, 7]},
    {"nome": "Alan", "voti": [6, 7, 6]}
]

for studente in classe:
    media = sum(studente["voti"]) / len(studente["voti"])
    print(studente["nome"], media)
```

## 5. Conteggio delle frequenze

```python
testo = "dati e algoritmi"
frequenze = {}

for carattere in testo:
    if carattere != " ":
        frequenze[carattere] = frequenze.get(carattere, 0) + 1

print(frequenze)
```

## 6. Attività

Realizza un piccolo catalogo. Ogni elemento deve avere codice, descrizione, quantità e categoria. Il programma deve permettere ricerca e aggiornamento.
