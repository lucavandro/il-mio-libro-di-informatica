# Algoritmi genetici

## 1. Idea generale

Un algoritmo genetico cerca buone soluzioni ispirandosi in modo semplificato alla selezione naturale.

È utile quando lo spazio delle soluzioni è grande e non serve garantire l'ottimo assoluto.

## 2. Componenti

- **individuo**: una soluzione candidata;
- **popolazione**: insieme di candidati;
- **gene**: parte della rappresentazione;
- **fitness**: misura della qualità;
- **selezione**: scelta dei genitori;
- **crossover**: combinazione;
- **mutazione**: modifica casuale.

```mermaid
flowchart LR
    P["Popolazione"] --> F["Valuta fitness"]
    F --> S["Seleziona"]
    S --> C["Crossover"]
    C --> M["Mutazione"]
    M --> N["Nuova popolazione"]
    N --> F
```

## 3. Problema dello zaino

Ogni oggetto ha peso e valore. Si cerca una combinazione che massimizzi il valore senza superare la capacità.

Un individuo può essere una sequenza di bit:

```text
1 0 1 1 0
```

`1` indica un oggetto scelto.

## 4. Fitness

```python
def fitness(individuo, pesi, valori, capacita):
    peso = sum(
        gene * peso
        for gene, peso in zip(individuo, pesi)
    )
    valore = sum(
        gene * valore
        for gene, valore in zip(individuo, valori)
    )

    if peso > capacita:
        return 0
    return valore
```

La funzione di fitness deve rappresentare l'obiettivo reale. Una misura progettata male può premiare soluzioni inutili.

## 5. Limiti

Un algoritmo genetico:

- non garantisce sempre l'ottimo;
- può convergere troppo presto;
- dipende da rappresentazione e parametri;
- può richiedere molte valutazioni;
- va confrontato con metodi più semplici.

## 6. Laboratorio

Realizza o completa un algoritmo genetico per una funzione semplice o per lo zaino. Confronta più esecuzioni e documenta qualità, tempo e variabilità.
