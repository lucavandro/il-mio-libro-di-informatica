# Le liste

## 1. Creare e leggere una lista

Una lista conserva più valori in ordine.

```python
temperature = [18.5, 20.0, 19.2, 21.1]
print(temperature[0])
print(temperature[-1])
```

Gli indici partono da zero. Un indice negativo conta dalla fine.

## 2. Modificare una lista

```python
studenti = ["Ada", "Linus"]
studenti.append("Grace")
studenti[1] = "Alan"
studenti.remove("Ada")
print(studenti)
```

Metodi essenziali:

| Metodo | Effetto |
|---|---|
| `append(x)` | aggiunge in fondo |
| `insert(i, x)` | inserisce in una posizione |
| `remove(x)` | rimuove il primo valore uguale |
| `pop()` | rimuove e restituisce un elemento |
| `sort()` | ordina la lista |
| `reverse()` | inverte l'ordine |

## 3. Attraversare una lista

```python
voti = [7, 8, 6, 9]

for voto in voti:
    print(voto)
```

Con indice:

```python
for indice, voto in enumerate(voti):
    print(indice, voto)
```

## 4. Aggregare valori

```python
misure = [12.2, 11.8, 12.5, 12.0]

media = sum(misure) / len(misure)
print(min(misure))
print(max(misure))
print(media)
```

Prima di dividere per `len()` si controlla che la lista non sia vuota.

## 5. Slicing

```python
numeri = [0, 1, 2, 3, 4, 5]
print(numeri[1:4])
print(numeri[:3])
print(numeri[3:])
```

Lo slicing produce una nuova lista. Il limite finale non viene incluso.

## 6. Comprensioni semplici

```python
quadrati = [numero ** 2 for numero in range(1, 6)]
pari = [numero for numero in range(20) if numero % 2 == 0]
```

Una comprensione è utile quando rimane breve. Per trasformazioni complesse è più leggibile un ciclo normale.

## 7. Copie e riferimenti

```python
originale = [1, 2, 3]
copia = originale.copy()
copia.append(4)

print(originale)
print(copia)
```

Con `copia = originale`, entrambi i nomi indicherebbero la stessa lista.

## 8. Laboratorio

Realizza un programma che:

1. legge una serie di misure;
2. rifiuta valori non validi;
3. calcola minimo, massimo e media;
4. conta i valori superiori alla media;
5. stampa la lista ordinata.
