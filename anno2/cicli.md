
# I Cicli 🔁

## 1. Introduzione al concetto di ciclo

### 1.1 Cos’è un ciclo e a cosa serve

Immagina di dover fare dieci flessioni 🏋️, oppure di contare le stelle cadenti 🌠 in una notte d’estate: ripeti la stessa azione più volte. In informatica, questa ripetizione si chiama **ciclo**. I cicli permettono al computer di eseguire una serie di istruzioni più volte, senza doverle scrivere una per una.

Un ciclo è come un DJ 🎧 che mette in loop la tua canzone preferita: la musica riparte ogni volta che finisce, finché non decidi di fermarla!

**Esempio pratico:**
Stampare i numeri da 1 a 5 senza ciclo:

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

Con un ciclo:

```python
for i in range(1, 6):
    print(i)
```

### Esercizi sezione 1

- E1.1 Scrivi un programma che stampa il tuo nome 10 volte. 📝
- E1.2 Simula il conteggio dei passi fatti in una giornata. 🚶‍♂️
- E1.3 Stampa i numeri da 1 a 100 come se fossero i secondi di una gara di atletica. 🏃‍♀️
- E1.4 Scrivi un programma che ripete un messaggio motivazionale per ogni giorno della settimana. 💪

## 2. Il ciclo while

### 2.1 Funzionamento del ciclo while

Il ciclo `while` è come una ruota che gira finché una condizione è vera. Immagina di pedalare su una cyclette 🚴: continui finché non ti stanchi!

**Sintassi:**

```python
while condizione:
    # istruzioni da ripetere
```

**Esempio:**

```python
contatore = 1
while contatore <= 5:
    print(contatore)
    contatore += 1
```

Questo programma stampa i numeri da 1 a 5.

> 💡 **Nota di traduzione:**  
Molto spesso la parola `while` viene tradotta con “mentre”, ma si tratta di una traduzione fuorviante. Il mio consiglio è di tradurre `while` con la locuzione “fintanto che...”.

**Esempio per chiarire il concetto:**

Immagina di dire:  

- “Mentre piove, resto in casa.”  
Questo suggerisce che stai facendo due cose contemporaneamente.

In informatica, invece, il ciclo `while` funziona così:  

- “Fintanto che piove, resto in casa.”  
Qui il programma controlla se sta piovendo e, solo se la condizione è vera, ripete l’azione di restare in casa.

**Tradotto in Python:**

```python
piove = True
while piove:  # Fintanto che piove...
    print("Resto in casa")
    # Immagina che a un certo punto smetta di piovere
    piove = False
```

In questo esempio, l’azione si ripete solo “fintanto che” la condizione è vera, non “mentre” accade qualcos’altro.

### 2.2 Variabile di controllo

La variabile di controllo è come il cronometro di una gara: tiene il conto di quante volte hai ripetuto l’azione. Se dimentichi di aggiornarla, rischi di non fermarti mai!

**Esempio:**

```python
energia = 10
while energia > 0:
    print("Salto!")
    energia -= 2
```

### 2.3 Cicli infiniti

Un ciclo infinito è come una canzone che non finisce mai. Succede quando la condizione del ciclo è sempre vera.

**Esempio:**

```python
while True:
    print("Questa frase si ripete all’infinito!")
```

**Curiosità:**
I cicli infiniti sono utili nei videogiochi 🎮, dove il programma deve continuare a controllare gli input finché il giocatore non esce.

### 2.4 break e continue nel ciclo while

`break` serve per interrompere il ciclo prima che la condizione diventi falsa, come premere il pulsante STOP 🛑. `continue` invece salta il resto delle istruzioni e riparte subito dal prossimo giro ⏭️.

**Esempio con break:**

```python
tentativi = 0
while True:
    tentativi += 1
    if tentativi == 3:
        print("Hai raggiunto il limite di tentativi!")
        break
    print("Tentativo", tentativi)
```

**Esempio con continue:**

```python
numero = 0
while numero < 5:
    numero += 1
    if numero == 3:
        continue
    print(numero)
# Stampa 1, 2, 4, 5 (salta il 3)
```

### Esercizi sezione 2

- E2.1 Simula il countdown di un razzo 🚀 che parte da 10 e arriva a 0.
- E2.2 Scrivi un ciclo che chiede all’utente di indovinare una password 🔒, interrompendosi con break quando la indovina.
- E2.3 Conta quante volte un giocatore può saltare prima che finisca l’energia. 🦘
- E2.4 Stampa tutti i numeri da 1 a 20, saltando i multipli di 5 usando continue. 🔢

## 3. Il ciclo for

### 3.1 Funzionamento del ciclo for

Il ciclo `for` è come una lista di cose da fare 📋: il computer le esegue una dopo l’altra. In Python, il ciclo for è molto potente perché può scorrere numeri, lettere, parole e molto altro.

**Sintassi:**

```python
for variabile in sequenza:
    # istruzioni da ripetere
```

**Esempio:**

```python
for giorno in ["Lunedì", "Martedì", "Mercoledì"]:
    print("Oggi è", giorno)
```

### 3.2 Uso di range

`range` è come un distributore di numeri 🎰: genera una sequenza di valori da usare nel ciclo for.

**Esempio:**

```python
for i in range(5):
    print(i)
# Stampa 0, 1, 2, 3, 4
```

Puoi anche specificare da dove partire e dove finire:

```python
for i in range(3, 8):
    print(i)
# Stampa 3, 4, 5, 6, 7
```

### 3.3 break e continue nel ciclo for

Funzionano come nel ciclo while: `break` interrompe il ciclo 🛑, `continue` salta al prossimo giro ⏭️.

**Esempio:**

```python
for film in ["Matrix", "Avatar", "Titanic"]:
    if film == "Avatar":
        continue
    print("Sto guardando", film)
# Salta "Avatar"
```

### 3.4 Cicli annidati

Un ciclo dentro un altro è come una gara a tappe 🏁: per ogni tappa, si fanno più giri. Si usano per lavorare con tabelle, griglie, o per simulare partite di campionato.

**Esempio:**

```python
for squadra in ["Azzurri", "Rossi"]:
    for partita in range(1, 4):
        print(squadra, "gioca la partita", partita)
```

### 3.5 Iterazione su stringhe

Puoi usare il ciclo for per scorrere ogni lettera di una parola, come se stessi leggendo una frase lettera per lettera 🔤.

**Esempio:**

```python
parola = "Python"
for lettera in parola:
    print(lettera)
```

### Esercizi sezione 3

- E3.1 Stampa ogni lettera del tuo nome su una riga diversa. 🧑‍💻
- E3.2 Simula il calendario di una settimana stampando ogni giorno. 📅
- E3.3 Conta da 100 a 0 a ritroso usando range. ⏳
- E3.4 Simula una tabella delle partite di calcio tra 3 squadre usando cicli annidati. ⚽
- E3.5 Stampa tutti i numeri pari da 2 a 20. 🔢

## 4. Equivalenza tra ciclo `while` e ciclo `for`

### 4.1 Risolvere lo stesso problema con while e for

Spesso puoi risolvere lo stesso problema sia con il ciclo while che con il ciclo for. È come scegliere se andare in bicicletta 🚴 o a piedi 🚶: entrambi ti portano a destinazione, ma il percorso è diverso.

#### Esempio: stampare i numeri da 1 a 5

Con while:

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

Con for:

```python
for i in range(1, 6):
    print(i)
```

### Esercizi sezione 4

- E4.1 Stampa i numeri da 1 a 10 sia con while che con for. 🔁
- E4.2 Simula il conteggio dei punti di una partita con entrambi i cicli. 🏆
- E4.3 Scrivi un programma che chiede all’utente di inserire 5 voti e li stampa, usando prima while e poi for. 📝

## 5. Accenno al ciclo foreach

### 5.1 Il ciclo for come foreach in Python

In Python, il ciclo for può essere usato come un ciclo "foreach", cioè per scorrere tutti gli elementi di una collezione (come una lista o una stringa). È come passare in rassegna tutti i post di un social network 📱!

**Esempio:**

```python
for post in ["Foto", "Video", "Storia"]:
    print("Sto guardando il post:", post)
```

### 5.2 Anticipazione sulle liste (approfondimento nel prossimo capitolo)

Le liste sono come scatole che contengono tanti valori. Il ciclo for permette di "aprire" ogni scatola e vedere cosa c’è dentro. Approfondiremo le liste nel prossimo capitolo!

**Curiosità:**
Il ciclo for in Python è molto più flessibile rispetto ad altri linguaggi, perché può scorrere qualsiasi oggetto "iterabile" 🔄.

### Esercizi sezione 5

- E5.1 Stampa tutti i titoli di una playlist musicale. 🎵
- E5.2 Simula la lettura di tutti i commenti di un post usando il ciclo for. 💬
- E5.3 Stampa ogni carattere di una parola scelta dall’utente. 🔤

## 6. Riepilogo generale sui cicli

I cicli sono uno strumento fondamentale per automatizzare le ripetizioni nei programmi. Saperli usare ti permette di risolvere problemi complessi in modo semplice e veloce, come contare, simulare gare, analizzare dati o gestire le attività di tutti i giorni. Ricorda: la chiave è capire quando fermarsi 🛑 e come controllare il flusso del ciclo!
