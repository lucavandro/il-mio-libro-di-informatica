# Calcolo scientifico con GNU Octave

> Questo modulo è alternativo al percorso con R. Octave è consigliato quando si vuole dare priorità ad algebra lineare, sistemi e calcolo numerico.

## 1. Programma di 18 ore

| Unità | Ore |
|---|---:|
| ambiente, vettori e matrici | 3 |
| operazioni matriciali | 3 |
| sistemi lineari | 3 |
| grafici | 3 |
| interpolazione ed errori | 3 |
| progetto scientifico | 3 |
| **Totale** | **18** |

## 2. Vettori e matrici

```octave
v = [1, 2, 3, 4];
A = [2, 1; 3, 4];
b = [5; 6];
```

Il punto e virgola separa le righe.

```octave
size(A)
length(v)
```

## 3. Operazioni

```octave
A + A
2 * A
A'
A * b
```

Gli operatori con il punto lavorano elemento per elemento:

```octave
v .^ 2
v .* v
```

`A * B` è il prodotto matriciale; `A .* B` moltiplica elementi corrispondenti.

## 4. Sistemi lineari

Per risolvere:

```text
Ax = b
```

si usa:

```octave
x = A \ b;
```

È preferibile a calcolare esplicitamente `inv(A) * b`.

```octave
residuo = A * x - b;
norm(residuo)
```

Il residuo misura quanto la soluzione numerica soddisfa il sistema.

## 5. Grafici

```octave
x = linspace(0, 2*pi, 200);
y = sin(x);

plot(x, y, "LineWidth", 2);
xlabel("x");
ylabel("sin(x)");
title("Funzione seno");
grid on;
```

## 6. Interpolazione

```octave
x = [0, 1, 2, 3];
y = [1.0, 2.1, 3.9, 6.2];
nuovi_x = linspace(0, 3, 100);
nuovi_y = interp1(x, y, nuovi_x, "linear");

plot(x, y, "o", nuovi_x, nuovi_y, "-");
legend("dati", "interpolazione");
```

L'interpolazione stima valori tra misure note. Non garantisce previsioni corrette fuori dall'intervallo osservato.

## 7. Progetto

Scegli un problema scientifico basato su:

- sistema lineare;
- interpolazione;
- andamento di una funzione;
- confronto tra dati e modello.

Consegna codice, grafici, spiegazione, controllo dell'errore e limiti.

## 8. Rendere il calcolo verificabile

Prima di accettare un risultato:

1. controlla dimensioni di vettori e matrici;
2. prova un caso di cui conosci la soluzione;
3. calcola un residuo, quando possibile;
4. confronta il risultato con ordine di grandezza e unità attese;
5. modifica leggermente i dati e osserva la stabilità.

Per un sistema `A * x = b`, il residuo `norm(A * x - b)` dovrebbe essere piccolo.
Un residuo piccolo non garantisce però che dati imprecisi producano una soluzione
stabile.

## 9. Errori frequenti

- confondere `*` con `.*` e `/` con `./`;
- usare matrici con dimensioni incompatibili;
- estrapolare un'interpolazione fuori dall'intervallo;
- mostrare molte cifre senza considerare l'errore dei dati;
- affidarsi al grafico senza un controllo numerico.

## 10. Verifica

1. Qual è la differenza tra operazione matriciale ed elemento per elemento?
2. Come si controlla la soluzione di un sistema lineare?
3. Perché interpolazione ed estrapolazione non sono equivalenti?
4. Quali informazioni rendono riproducibile un esperimento numerico?
