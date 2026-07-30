# Analisi dei dati con R

> Questo modulo è alternativo a GNU Octave. R è consigliato quando si vuole dare priorità a dati, statistica e grafici.

## 1. Programma di 18 ore

| Unità | Ore |
|---|---:|
| ambiente, script e oggetti | 2 |
| vettori e data frame | 3 |
| importazione e pulizia | 3 |
| statistica descrittiva | 3 |
| grafici | 3 |
| relazione tra variabili | 2 |
| progetto | 2 |
| **Totale** | **18** |

## 2. Vettori

```r
temperature <- c(18.2, 19.1, 20.0, 18.8)

mean(temperature)
median(temperature)
min(temperature)
max(temperature)
sd(temperature)
```

## 3. Data frame

```r
dati <- data.frame(
  giorno = c("lun", "mar", "mer", "gio"),
  temperatura = c(18.2, 19.1, 20.0, 18.8)
)

str(dati)
summary(dati)
```

## 4. Importare CSV

```r
dati <- read.csv("misure.csv")
head(dati)
```

Valori mancanti:

```r
sum(is.na(dati))
dati_completi <- na.omit(dati)
```

Prima di eliminarli si deve capire perché manchino.

## 5. Grafici

```r
plot(
  dati$giorno,
  dati$temperatura,
  type = "b",
  xlab = "Giorno",
  ylab = "Temperatura (°C)",
  main = "Temperature rilevate"
)
```

Distribuzione:

```r
hist(
  dati$temperatura,
  xlab = "Temperatura (°C)",
  main = "Distribuzione delle temperature"
)
```

## 6. Relazione tra variabili

```r
modello <- lm(periodo ~ lunghezza, data = dati)
summary(modello)
plot(dati$lunghezza, dati$periodo)
abline(modello, col = "blue")
```

Una relazione statistica non dimostra automaticamente un rapporto di causa.

## 7. Progetto

Analizza un dataset scientifico:

1. descrivi provenienza e variabili;
2. controlla valori mancanti o anomali;
3. calcola indicatori;
4. produci almeno due grafici;
5. costruisci, se adatto, un modello semplice;
6. discuti limiti e possibili spiegazioni.
