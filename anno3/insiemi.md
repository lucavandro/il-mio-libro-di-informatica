# Insiemi

## 1. Che cos'è un insieme

Un insieme conserva valori unici e non garantisce un ordine utile.

```python
materie = {"matematica", "fisica", "informatica"}
materie.add("scienze")
```

Una lista può essere convertita per eliminare duplicati:

```python
valori = [2, 2, 5, 3, 5]
unici = set(valori)
print(unici)
```

## 2. Operazioni

```python
sport = {"Ada", "Linus", "Grace"}
musica = {"Grace", "Alan"}

print(sport | musica)
print(sport & musica)
print(sport - musica)
```

| Operatore | Operazione |
|---|---|
| `|` | unione |
| `&` | intersezione |
| `-` | differenza |
| `^` | differenza simmetrica |

## 3. Verificare l'appartenenza

```python
if "Ada" in sport:
    print("Ada pratica sport")
```

La verifica di appartenenza è normalmente molto efficiente.

## 4. Attività

Confronta gli insiemi degli studenti iscritti a due attività. Trova iscritti totali, iscritti a entrambe e iscritti soltanto alla prima.
