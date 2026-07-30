# IA opzionale: reti neurali e IA generativa

## 1. Programma di 33 ore

| Unità | Ore |
|---|---:|
| percettrone e rete neurale | 6 |
| addestramento ed errore | 5 |
| immagini o testi come numeri | 5 |
| modelli linguistici | 5 |
| recupero di informazioni da fonti | 4 |
| bias, spiegabilità e sicurezza | 4 |
| progetto finale | 4 |
| **Totale** | **33** |

## 2. Dal neurone alla rete

Un'unità artificiale combina input e pesi, aggiunge un termine e applica una funzione.

```mermaid
flowchart LR
    X1["x₁"] --> N(("somma e attivazione"))
    X2["x₂"] --> N
    B["bias"] --> N
    N --> Y["output"]
```

Una rete contiene molti parametri. Addestrarla significa modificarli per ridurre una funzione di errore.

## 3. Dati numerici

Immagini e testi devono essere trasformati in numeri:

- pixel per immagini;
- token per testi;
- vettori per caratteristiche.

La trasformazione influenza ciò che il modello può apprendere.

## 4. Modelli linguistici

Un modello linguistico stima continuazioni probabili. Non conserva automaticamente un archivio di fatti verificati e può produrre informazioni false.

## 5. Recupero da fonti

```mermaid
flowchart LR
    Q["Domanda"] --> R["Ricerca nei documenti"]
    R --> C["Contesto selezionato"]
    C --> M["Modello"]
    M --> A["Risposta con fonti"]
```

Fornire documenti riduce alcuni errori, ma non elimina il bisogno di verificare.

## 6. Sicurezza

- non inserire dati riservati;
- trattare l'output come non verificato;
- controllare prompt e documenti provenienti dall'esterno;
- limitare strumenti e permessi;
- registrare le fonti;
- prevedere controllo umano.

## 7. Progetto

Realizza un prototipo circoscritto: classificatore di immagini, analisi di testi o assistente basato su documenti. Documenta dati, metriche, errori e rischi.
