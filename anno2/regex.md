# Espressioni regolari: laboratorio facoltativo

## 1. Che cosa sono

Un'espressione regolare descrive una forma che un testo deve rispettare. È utile per cercare dati o controllare formati semplici.

Non garantisce che l'informazione sia vera. Una stringa può avere la forma di un indirizzo email senza corrispondere a una casella esistente.

## 2. Modulo `re`

```python
import re

testo = "La temperatura è 23 gradi"
risultato = re.search(r"\d+", testo)

if risultato:
    print(risultato.group())
```

## 3. Simboli essenziali

| Simbolo | Significato |
|---|---|
| `\d` | cifra |
| `\w` | carattere alfanumerico o underscore |
| `.` | un carattere |
| `+` | una o più ripetizioni |
| `*` | zero o più ripetizioni |
| `{n}` | esattamente `n` ripetizioni |
| `^` | inizio |
| `$` | fine |

## 4. Esempio

Controllo di un codice formato da due lettere e tre cifre:

```python
import re

codice = input("Codice: ")
modello = r"^[A-Z]{2}\d{3}$"

if re.fullmatch(modello, codice):
    print("Formato valido")
else:
    print("Formato non valido")
```

## 5. Attività

1. Trova tutti i numeri in una frase.
2. Verifica un codice postale di cinque cifre.
3. Verifica una targa didattica formata da due lettere, tre cifre e due lettere.
4. Spiega perché controllare il formato non basta a dimostrare la validità del dato.
