# File, CSV e JSON

## 1. Leggere un file di testo

```python
with open("note.txt", "r", encoding="utf-8") as file:
    contenuto = file.read()

print(contenuto)
```

`with` chiude il file anche in caso di errore.

## 2. Leggere riga per riga

```python
with open("misure.txt", "r", encoding="utf-8") as file:
    for riga in file:
        valore = riga.strip()
        print(valore)
```

`strip()` elimina spazi e caratteri di fine riga alle estremità.

## 3. Scrivere

```python
righe = ["prima\n", "seconda\n"]

with open("risultati.txt", "w", encoding="utf-8") as file:
    file.writelines(righe)
```

La modalità `w` sostituisce il contenuto. La modalità `a` aggiunge in fondo.

## 4. Gestire errori

```python
try:
    with open("dati.txt", "r", encoding="utf-8") as file:
        contenuto = file.read()
except FileNotFoundError:
    print("Il file non esiste")
except PermissionError:
    print("Non hai il permesso di leggere il file")
```

## 5. Percorsi con `pathlib`

```python
from pathlib import Path

cartella = Path("dati")
percorso = cartella / "misure.csv"

if percorso.exists():
    print(percorso.resolve())
```

`pathlib` costruisce percorsi compatibili con sistemi operativi diversi.

## 6. CSV

CSV rappresenta dati tabellari.

```python
import csv

with open("misure.csv", "r", encoding="utf-8", newline="") as file:
    lettore = csv.DictReader(file)
    for riga in lettore:
        print(riga["data"], riga["temperatura"])
```

Scrittura:

```python
import csv

righe = [
    {"nome": "Ada", "voto": 8},
    {"nome": "Alan", "voto": 7}
]

with open("voti.csv", "w", encoding="utf-8", newline="") as file:
    campi = ["nome", "voto"]
    scrittore = csv.DictWriter(file, fieldnames=campi)
    scrittore.writeheader()
    scrittore.writerows(righe)
```

Il separatore può essere virgola, punto e virgola o altro. Va concordato e controllato.

## 7. JSON

JSON rappresenta numeri, stringhe, valori booleani, liste e oggetti.

```python
import json

with open("configurazione.json", "r", encoding="utf-8") as file:
    configurazione = json.load(file)

print(configurazione)
```

Scrittura:

```python
import json

dati = {"classe": "3A", "studenti": 24}

with open("classe.json", "w", encoding="utf-8") as file:
    json.dump(dati, file, ensure_ascii=False, indent=2)
```

## 8. CSV o JSON?

| Formato | Adatto a |
|---|---|
| CSV | tabelle regolari |
| JSON | dati annidati e configurazioni |

Entrambi sono leggibili e trasferibili. `pickle` non viene usato nel percorso base perché è specifico di Python e non deve essere caricato da fonti non fidate.

## 9. Progetto

Realizza un programma che importi un CSV, controlli i valori, calcoli un riepilogo e salvi i risultati in JSON.
