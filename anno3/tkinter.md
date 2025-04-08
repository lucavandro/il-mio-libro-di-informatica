# Tkinter
Ecco il primo capitolo in formato **Markdown**, pensato per una **dispensa introduttiva su Tkinter** adatta a studenti delle scuole superiori:

---

# Capitolo 1: Introduzione alle GUI e a Tkinter

## Che cosa sono le GUI?

GUI è l'acronimo di **Graphical User Interface**, cioè **Interfaccia Grafica per l'Uso dell'Utente**.  
A differenza dei programmi che usano solo il terminale (dove si scrive e si legge testo), una GUI permette di **interagire con il programma attraverso finestre, pulsanti, caselle di testo**, e molto altro.

Esempi di GUI che usi ogni giorno:
- La calcolatrice del tuo computer o smartphone
- Le finestre con cui salvi o apri file
- I messaggi che compaiono sullo schermo per chiederti conferma

## Perché usare Tkinter?

Python mette a disposizione diverse librerie per creare GUI.  
**Tkinter** è una delle più semplici e fa già parte della libreria standard di Python: non serve installarla!  
È perfetta per imparare le basi della programmazione grafica.

---

## Come iniziare con Tkinter

Per iniziare, apri il tuo editor Python preferito (ad esempio Thonny o IDLE) e scrivi questo:

```python
import tkinter
tkinter._test()
```
![alt text](img/tkinter/tk1.png)
Questa funzione apre una finestra di prova. Se la vedi comparire, significa che tutto funziona correttamente!

---

## Interagire con l'utente: simpledialog e messagebox

In Tkinter possiamo **chiedere informazioni all'utente** e **mostrare messaggi** in modo semplice, grazie a due moduli:

### `tkinter.simpledialog`

Questo modulo permette di chiedere qualcosa all'utente tramite una **finestra di input**.

Esempio:

```python
import tkinter as tk
from tkinter import simpledialog

finestra = tk.Tk()
finestra.withdraw()  # Nasconde la finestra principale

nome = simpledialog.askstring("Domanda", "Come ti chiami?")
```

### `tkinter.messagebox`

Questo modulo serve a **mostrare messaggi** all’utente.

Esempio:

```python
import tkinter as tk
from tkinter import messagebox

finestra = tk.Tk()
finestra.withdraw()

messagebox.showinfo("Benvenuto", "Ciao! Questo è un messaggio di benvenuto.")
```

Puoi anche usare altri tipi di messaggi, ad esempio:
- `messagebox.showwarning()` – per avvisi
- `messagebox.showerror()` – per errori

---

## Un esempio completo

```python
import tkinter as tk
from tkinter import simpledialog, messagebox

finestra = tk.Tk()
finestra.withdraw()

nome = simpledialog.askstring("Domanda", "Come ti chiami?")
messagebox.showinfo("Risposta", f"Piacere di conoscerti, {nome}!")
```

> In questo programma, **non usiamo `print`**: tutto avviene con finestre grafiche!

---

## Esercizi (tracce)

1. Chiedi all'utente il suo colore preferito e mostra una finestra con un messaggio che lo include.
2. Chiedi due numeri all'utente e mostra la loro somma usando una `messagebox`.
3. Chiedi all'utente la sua età e mostra un messaggio diverso a seconda che abbia più o meno di 18 anni.
4. Chiedi all'utente il nome di una città e mostra un messaggio che la saluta ("Ciao, Roma!").

---

