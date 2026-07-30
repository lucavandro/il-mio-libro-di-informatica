# Analizzare e rappresentare dati con Python

## 1. Dal dato alla conclusione

```mermaid
flowchart LR
    D["Raccolta"] --> C["Controllo"]
    C --> E["Elaborazione"]
    E --> G["Grafico"]
    G --> I["Interpretazione"]
```

Un grafico non sostituisce il controllo dei dati.

## 2. Leggere un CSV

```python
import csv

temperature = []

with open("temperature.csv", encoding="utf-8", newline="") as file:
    lettore = csv.DictReader(file)
    for riga in lettore:
        try:
            temperature.append(float(riga["temperatura"]))
        except ValueError:
            print("Valore ignorato:", riga["temperatura"])
```

## 3. Indicatori

```python
from statistics import mean, median

print("Media:", mean(temperature))
print("Mediana:", median(temperature))
print("Minimo:", min(temperature))
print("Massimo:", max(temperature))
```

La media è influenzata dai valori estremi. La mediana descrive il valore centrale dopo l'ordinamento.

## 4. Grafici

```python
import matplotlib.pyplot as plt

giorni = list(range(1, len(temperature) + 1))
plt.plot(giorni, temperature, marker="o")
plt.xlabel("Giorno")
plt.ylabel("Temperatura (°C)")
plt.title("Temperature rilevate")
plt.grid(True)
plt.show()
```

## 5. Correlazione e causalità

Due valori possono variare insieme senza che uno causi l'altro. Prima di formulare una conclusione si cercano spiegazioni alternative e si controlla il metodo di raccolta.

## 6. Progetto

Scegli un piccolo dataset scientifico. Consegna:

- file originale;
- programma;
- descrizione della pulizia;
- almeno tre indicatori;
- due grafici;
- interpretazione;
- limiti dell'analisi.
