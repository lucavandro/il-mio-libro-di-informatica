# I Dizionari in Python

I dizionari sono come dei "contenitori" dove ogni elemento ha una sua etichetta (chiamata chiave). Pensa ad una rubrica telefonica: ogni numero (valore) è associato a un nome (chiave)!

## Come creare un dizionario

Per creare un dizionario usiamo le parentesi graffe `{}` con il formato `chiave: valore`:

```python
# Dizionario semplice
studente = {
    "nome": "Mario",
    "età": 15,
    "classe": "3A"
}

# Dizionario con diversi tipi di valori
persona = {
    "nome": "Laura",
    "hobby": ["calcio", "pittura"],
    "voti": (8, 7, 9),
    "ha_fratelli": True
}
```

## Come accedere e modificare i valori

```python
# Leggere un valore
print(studente["nome"])  # Stampa: Mario

# Modificare un valore
studente["età"] = 16
print(studente["età"])  # Stampa: 16

# Aggiungere una nuova coppia chiave-valore
studente["sport"] = "nuoto"

# Rimuovere una coppia chiave-valore
del studente["sport"]
```

## Metodi sicuri per accedere ai valori

```python
# Usando get() per evitare errori
voto = studente.get("voto_matematica", "Non disponibile")
print(voto)  # Stampa: Non disponibile

# Verificare se una chiave esiste
if "nome" in studente:
    print("Il nome è:", studente["nome"])
```

## Operazioni comuni con i dizionari

```python
# Ottenere tutte le chiavi
print(studente.keys())  # ["nome", "età", "classe"]

# Ottenere tutti i valori
print(studente.values())  # ["Mario", 16, "3A"]

# Ottenere coppie chiave-valore
print(studente.items())  # [("nome", "Mario"), ("età", 16), ("classe", "3A")]

# Numero di elementi nel dizionario
print(len(studente))  # 3
```

## Un esempio pratico: registro di classe

```python
registro = {
    "Mario Rossi": {
        "voti": [8, 7, 9],
        "assenze": 3,
        "materia_preferita": "matematica"
    },
    "Laura Bianchi": {
        "voti": [9, 9, 8],
        "assenze": 1,
        "materia_preferita": "italiano"
    }
}

# Stampare i voti di uno studente
print(f"Voti di Mario: {registro['Mario Rossi']['voti']}")

# Calcolare la media dei voti
voti_mario = registro["Mario Rossi"]["voti"]
media = sum(voti_mario) / len(voti_mario)
print(f"Media di Mario: {media}")
```

## Cicli con i dizionari

```python
# Dizionario con materie e voti
pagella = {
    "Matematica": 8,
    "Italiano": 7,
    "Storia": 9,
    "Inglese": 8
}

# Ciclo sulle chiavi
for materia in pagella:
    print(f"In {materia} ho preso: {pagella[materia]}")

# Ciclo su chiavi e valori insieme
for materia, voto in pagella.items():
    print(f"In {materia} ho preso: {voto}")
```

## Un esempio con i giochi

```python
# Dizionario di giochi e punteggi
videogiochi = {
    "Minecraft": {
        "ore_giocate": 50,
        "livello": "esperto",
        "achievements": ["costruttore", "esploratore"]
    },
    "Fortnite": {
        "ore_giocate": 30,
        "livello": "principiante",
        "achievements": ["sopravvissuto"]
    }
}

# Stampare informazioni sui giochi
for gioco, info in videogiochi.items():
    print(f"\nGioco: {gioco}")
    print(f"Ore giocate: {info['ore_giocate']}")
    print(f"Livello: {info['livello']}")
    print(f"Achievement ottenuti: {', '.join(info['achievements'])}")
```

## Esercizio pratico
Crea un dizionario con le tue informazioni:

```python
io = {
    "nome": "Il tuo nome",
    "età": 15,
    "hobby": ["hobby1", "hobby2"],
    "materie_preferite": {
        "prima": "materia1",
        "seconda": "materia2"
    }
}

# Stampa alcune informazioni
print(f"Mi chiamo {io['nome']} e ho {io['età']} anni")
print(f"I miei hobby sono: {', '.join(io['hobby'])}")
```

## Quando usare i dizionari?
1. Quando hai bisogno di associare valori a delle etichette (chiavi)
2. Quando vuoi organizzare dati in modo strutturato
3. Quando hai bisogno di cercare velocemente dei valori
4. Quando hai dati che possono essere organizzati in coppie chiave-valore

I dizionari sono molto potenti e vengono usati spesso nella programmazione reale. Per esempio:
- Per gestire dati di utenti
- Per configurare programmi
- Per memorizzare punteggi di giochi
- Per organizzare dati complessi
