# Tuple

## 1. Che cos'è una tupla

Una tupla è una sequenza ordinata che non può essere modificata dopo la creazione.

```python
punto = (3, 5)
print(punto[0])
print(punto[1])
```

## 2. Quando usarla

Una tupla è utile quando i valori formano un'unica informazione e non devono cambiare:

- coordinate;
- colore RGB;
- data;
- dimensioni.

```python
colore = (255, 120, 0)
larghezza, altezza = (1920, 1080)
```

## 3. Liste di tuple

```python
punti = [(0, 0), (2, 3), (4, 1)]

for x, y in punti:
    print(f"x={x}, y={y}")
```

## 4. Attività

Rappresenta con tuple cinque punti del piano e calcola la distanza di ciascuno dall'origine.
