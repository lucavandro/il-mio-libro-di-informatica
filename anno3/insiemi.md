# Gli Insiemi (Set) in Python

Gli insiemi in Python sono come quelli che studiamo in matematica: sono collezioni di elementi unici e non ordinati. Immagina di avere una scatola dove ogni oggetto può esserci una sola volta, e non importa come li sistemi dentro!

## Come creare un insieme

Per creare un insieme usiamo le parentesi graffe `{}` o la funzione `set()`:

```python
# Creare un insieme con le parentesi graffe
colori = {"rosso", "blu", "verde"}

# Creare un insieme dalla funzione set()
numeri = set([1, 2, 3, 4, 5])

# Un insieme può contenere solo valori unici!
numeri_con_duplicati = {1, 2, 2, 3, 3, 4}
print(numeri_con_duplicati)  # Stampa: {1, 2, 3, 4}
```

## Caratteristiche principali

1. **Elementi unici**: non ci possono essere duplicati
2. **Non ordinati**: non c'è un "primo" o "ultimo" elemento
3. **Elementi immutabili**: puoi inserire numeri, stringhe, tuple, ma non liste o dizionari

## Operazioni base con gli insiemi

```python
# Aggiungere un elemento
frutti = {"mela", "pera"}
frutti.add("banana")
print(frutti)  # Stampa: {"mela", "pera", "banana"}

# Rimuovere un elemento
frutti.remove("pera")
print(frutti)  # Stampa: {"mela", "banana"}

# Verificare se un elemento è presente
print("mela" in frutti)  # Stampa: True
print("arancia" in frutti)  # Stampa: False
```

## Operazioni matematiche con gli insiemi

Proprio come in matematica, possiamo fare diverse operazioni tra insiemi:

```python
squadra_A = {"Marco", "Luca", "Anna"}
squadra_B = {"Luca", "Paolo", "Sara"}

# Unione (tutti i giocatori di entrambe le squadre)
tutti = squadra_A | squadra_B
print(tutti)  # {"Marco", "Luca", "Anna", "Paolo", "Sara"}

# Intersezione (giocatori presenti in entrambe le squadre)
in_comune = squadra_A & squadra_B
print(in_comune)  # {"Luca"}

# Differenza (giocatori solo nella squadra A)
solo_A = squadra_A - squadra_B
print(solo_A)  # {"Marco", "Anna"}
```

## Un esempio pratico: gestire una classe

```python
# Studenti che fanno sport
sportivi = {"Alice", "Marco", "Elena", "Pietro"}

# Studenti che suonano uno strumento
musicisti = {"Marco", "Sofia", "Pietro", "Lucia"}

# Troviamo gli studenti che fanno entrambe le attività
tuttofare = sportivi & musicisti
print("Studenti che fanno sport e musica:", tuttofare)

# Troviamo tutti gli studenti con almeno un'attività
attivi = sportivi | musicisti
print("Studenti che fanno almeno un'attività:", attivi)

# Troviamo gli studenti che fanno solo sport
solo_sportivi = sportivi - musicisti
print("Studenti che fanno solo sport:", solo_sportivi)
```

## Casi d'uso comuni

```python
# Rimuovere duplicati da una lista
voti = [8, 7, 8, 9, 7, 6, 8]
voti_unici = set(voti)
print("Voti diversi ottenuti:", voti_unici)

# Verificare elementi comuni
amici_mario = {"Luca", "Anna", "Paolo"}
amici_giulia = {"Marco", "Anna", "Luca"}
amici_comuni = amici_mario & amici_giulia
print("Amici in comune:", amici_comuni)
```

## Esercizio pratico
Prova a creare due insiemi con:
```python
# I tuoi cibi preferiti
cibi_preferiti = {"pizza", "pasta", "gelato"}

# I cibi preferiti del tuo migliore amico
cibi_amico = {"pizza", "sushi", "hamburger"}

# Trova i cibi che piacciono a entrambi
print("Cibi che piacciono a entrambi:", cibi_preferiti & cibi_amico)
```

Gli insiemi sono molto utili quando:
1. Devi assicurarti di non avere duplicati
2. Vuoi fare operazioni matematiche tra gruppi di elementi
3. Devi verificare velocemente se un elemento è presente
