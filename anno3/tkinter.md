# 1. Introduzione alle GUI e a Tkinter

## Che cosa sono le GUI?

GUI è l'acronimo di **Graphical User Interface**, cioè **Interfaccia Grafica per l'Uso dell'Utente**.  
A differenza dei programmi che usano solo il terminale (dove si scrive e si legge testo), una GUI permette di **interagire con il programma attraverso finestre, pulsanti, caselle di testo**, e molto altro.

Esempi di GUI che usi ogni giorno:

- La calcolatrice del tuo computer o smartphone
- Le finestre con cui salvi o apri file
- I messaggi che compaiono sullo schermo per chiederti conferma

Una GUI è composta principalmente da:

- **Finestre**: Lo spazio principale dove vengono visualizzati i contenuti dell'applicazione
- **Widget**: Elementi interattivi come pulsanti, caselle di testo, menu a tendina
- **Controlli**: Componenti che permettono di manipolare dati o navigare nell'applicazione
- **Icone e simboli**: Rappresentazioni visive di funzioni o file

Le GUI hanno rivoluzionato l'informatica rendendo i computer accessibili a tutti, non solo agli esperti che conoscono linguaggi di programmazione o comandi specifici.

## 1.2 Vantaggi delle GUI rispetto alle interfacce a riga di comando

Le interfacce grafiche offrono numerosi vantaggi rispetto alle interfacce a riga di comando (CLI - Command Line Interface):

| GUI | CLI |
|-----|-----|
| Intuitive e facili da usare | Richiedono conoscenza di comandi specifici |
| Rappresentazione visiva degli elementi | Solo testo |
| Facilità di navigazione | Necessità di memorizzare percorsi |
| Feedback immediato | Feedback principalmente testuale |
| Curva di apprendimento più breve | Curva di apprendimento più ripida |

Nonostante questi vantaggi, è importante sapere che le interfacce a riga di comando rimangono fondamentali per molti sviluppatori e per operazioni avanzate, offrendo maggiore controllo e, spesso, maggiore efficienza per gli utenti esperti.

## 1.3 Introduzione a Tkinter: la libreria standard di Python per GUI

Tkinter è la libreria standard di Python per la creazione di interfacce grafiche. Il nome "Tkinter" deriva da "Tk interface", poiché è basata sul toolkit Tk originariamente sviluppato per il linguaggio Tcl.

**Caratteristiche principali di Tkinter:**

- È inclusa nell'installazione standard di Python (non richiede installazioni aggiuntive)
- È multipiattaforma: funziona su Windows, macOS e Linux
- Offre un set completo di widget per costruire interfacce
- È relativamente semplice da imparare rispetto ad altre librerie GUI
- Ha una vasta comunità e documentazione disponibile

Tkinter non è la libreria GUI più moderna o avanzata disponibile per Python, ma la sua semplicità e il fatto che sia integrata nel linguaggio la rendono ideale per i principianti e per progetti di piccole e medie dimensioni.

---

## 1.4 Come iniziare con Tkinter

Per iniziare, apri il tuo editor Python preferito (ad esempio Visual Studio Code o IDLE) e scrivi questo:

```python
import tkinter
tkinter._test()
```

![alt text](img/tkinter/tk1.png)

Questa funzione apre una finestra di prova. Se la vedi comparire, significa che tutto funziona correttamente!

---

## 1.5 Interagire con l'utente: simpledialog e messagebox

In Tkinter possiamo **chiedere informazioni all'utente** e **mostrare messaggi** in modo semplice, grazie a due moduli:

### `tkinter.messagebox`

Questo modulo serve a **mostrare messaggi** all’utente.

Il modulo messagebox mette a disposizione la funzione showinfo che accetta due parametri:

```python
messagebox.showinfo(title=None, message=None)
```

Dove `title` e `message` parametri opzionali per impostare il titolo della finestra e il messaggio da mostrare.

Esempio:

```python
from tkinter import messagebox

messagebox.showinfo(title="Benvenuto", message="Ciao! Questo è un messaggio di benvenuto.")
```

![alt text](img/tkinter/tk2.png)

Puoi anche usare altri tipi di messaggi, ad esempio:

- `messagebox.showwarning()` – per avvisi
- `messagebox.showerror()` – per errori

---

### `tkinter.simpledialog`

Questo modulo permette di chiedere qualcosa all'utente tramite una **finestra di input**.

Per richiedere di inserire una stringa possiamo usare la funzione

```python
simpledialog.askstring(title, prompt)
```

che ritorna la stringa inserita dall'utente.
Vediamo come utilizzarla con un esempio.

Esempio:

```python
from tkinter import simpledialog
nome = simpledialog.askstring("Domanda", "Come ti chiami?")
messagebox.showinfo("Risposta", f"Piacere di conoscerti, {nome}!")
```

> In questo programma, **non usiamo `print`**: tutto avviene con finestre grafiche!

Puoi anche usare altri metodo specifici per richiedere valori interi o float, ad esempio:

- `simpledialog.askint()` – per valori interi
- `simpledialog.askfloat()` – per valori float

---

## Esercizi (tracce)

1. Chiedi all'utente il suo colore preferito e mostra una finestra con un messaggio che lo include.
2. Chiedi due numeri all'utente e mostra la loro somma usando una `messagebox`.
3. Chiedi all'utente la sua età e mostra un messaggio diverso a seconda che abbia più o meno di 18 anni.
4. Chiedi all'utente il nome di una città e mostra un messaggio che la saluta ("Ciao, Roma!").

---

# Capitolo 2: Creazione di una finestra base

# 2.1 Introduzione
Iniziamo con il codice più semplice possibile per creare una finestra con Tkinter:

```python
from tkinter import Tk

# Creazione della finestra principale
finestra = Tk()
finestra.title("La mia prima finestra")
finestra.geometry("400x300")  # Larghezza x Altezza

# Avvio del loop principale
finestra.mainloop()
```

Analizziamo il codice:
1. `from tkinter import Tk`: Importiamo solo la classe `Tk` necessaria
2. `finestra = Tk()`: Creiamo l'oggetto finestra principale
3. `finestra.title()`: Impostiamo il titolo che apparirà nella barra della finestra
4. `finestra.geometry()`: Definiamo le dimensioni iniziali della finestra (larghezza x altezza)
5. `finestra.mainloop()`: Avviamo il "loop degli eventi", che mantiene la finestra aperta e risponde alle interazioni dell'utente

Questo codice, se eseguito, mostrerà una semplice finestra vuota con il titolo specificato.

## 2.2 La struttura di un'applicazione Tkinter

Tutte le applicazioni Tkinter seguono una struttura di base:

1. **Importazione della libreria**
  
  ```python
   from tkinter import Tk
   ```

2. **Creazione della finestra principale**
  
   ```python
   root = Tk()
   root.title("Nome Applicazione")
   root.geometry("larghezzaxaltezza")
   ```

3. **Aggiunta di widget**
  
   ```python
   from tkinter import Label, Button
   etichetta = Label(root, text="Ciao Mondo!")
   etichetta.pack()
   
   pulsante = Button(root, text="Cliccami")
   pulsante.pack()
   ```

4. **Definizione di funzioni di callback per l'interattività**
  
   ```python
   def azione_pulsante():
       print("Pulsante cliccato!")
   
   pulsante = Button(root, text="Cliccami", command=azione_pulsante)
   pulsante.pack()
   ```

5. **Avvio del loop principale**
   
   ```python
   root.mainloop()
   ```

Il `mainloop()` è cruciale: mantiene l'applicazione in esecuzione, gestisce gli eventi (come clic del mouse o pressioni di tasti) e aggiorna l'interfaccia. Senza di esso, la finestra apparirebbe e scomparirebbe immediatamente.

## 2.3 Personalizzazione della finestra

Possiamo personalizzare ulteriormente la nostra finestra base:

```python
from tkinter import Tk

# Creazione della finestra principale
finestra = Tk()
finestra.title("Finestra personalizzata")
finestra.geometry("500x400")

# Personalizzazione
finestra.configure(bg="#e0e0e0")  # Colore di sfondo
finestra.resizable(True, False)   # Ridimensionabile in larghezza ma non in altezza
finestra.minsize(300, 200)        # Dimensioni minime

# Icona della finestra (su Windows)
try:
    finestra.iconbitmap("icona.ico")  # Sostituire con il percorso di un'icona
except:
    pass  # Ignora se l'icona non è disponibile

# Avvio del loop principale
finestra.mainloop()
```

Opzioni comuni di configurazione:

- `bg` o `background`: colore di sfondo
- `resizable(width, height)`: controlla se la finestra può essere ridimensionata
- `minsize` e `maxsize`: limiti di dimensione
- `iconbitmap`: imposta l'icona della finestra

## 2.4 Esercizio guidato: creare e personalizzare una finestra

Ora proviamo a creare una finestra personalizzata con una semplice etichetta:

```python
from tkinter import Tk, Label
from tkinter import messagebox

# Creazione della finestra
finestra = Tk()
finestra.title("La mia applicazione")
finestra.geometry("500x300")
finestra.configure(bg="#f0f0f0")

# Aggiunta di un'etichetta con testo
etichetta = Label(
    finestra, 
    text="Benvenuto in Tkinter!",
    font=("Arial", 24),
    bg="#f0f0f0",
    fg="#333333"
)
etichetta.pack(pady=50)  # Aggiunge un po' di spazio sopra e sotto

# Funzione che verrà chiamata quando si chiude la finestra
def conferma_uscita():
    if messagebox.askokcancel("Uscita", "Vuoi davvero uscire?"):
        finestra.destroy()

# Gestione dell'evento di chiusura
finestra.protocol("WM_DELETE_WINDOW", conferma_uscita)

# Avvio del loop principale
finestra.mainloop()
```

Per utilizzare `messagebox`, dobbiamo aggiungere questo import all'inizio:

```python
from tkinter import messagebox
```

### Esercizi da svolgere

1. **Modifica base**: Cambia il titolo della finestra e il testo dell'etichetta.
2. **Personalizzazione**: Cambia il colore di sfondo, il tipo di carattere e le dimensioni della finestra.
3. **Aggiunta**: Inserisci una seconda etichetta sotto la prima con un testo diverso.
4. **Sfida**: Aggiungi un pulsante con la scritta "Esci" che chiuda la finestra quando viene cliccato.

## 2.5 Riepilogo della lezione

In questa prima lezione abbiamo:

- Compreso cosa sono le GUI e i loro vantaggi
- Introdotto Tkinter come libreria standard per GUI in Python
- Creato una finestra di base
- Appreso la struttura fondamentale di un'applicazione Tkinter
- Esplorato alcune opzioni di personalizzazione delle finestre
- Realizzato un semplice esercizio con un'etichetta

Nella prossima lezione, esploreremo i widget fondamentali di Tkinter che ci permetteranno di creare interfacce più interattive e funzionali.

## 2.6 Attività per casa

1. Installa Python e verifica che Tkinter sia incluso (prova a eseguire l'esempio della finestra base).
2. Sperimenta con diverse combinazioni di colori e dimensioni per la finestra.
3. Prova a creare una finestra con il tuo nome come titolo e una breve descrizione di te stesso nell'etichetta.
4. Cerca online esempi di applicazioni Tkinter per farti un'idea di cosa potrai costruire al termine del corso.

# 3. Widget fondamentali

## 3.1 Concetto di widget in Tkinter

I **widget** sono i componenti base che costituiscono un'interfaccia grafica in Tkinter. Ogni elemento visibile e interattivo che vediamo in una finestra è un widget: pulsanti, etichette, campi di testo, ecc.

Possiamo pensare ai widget come ai "mattoncini LEGO" dell'interfaccia grafica: combinandoli insieme possiamo costruire applicazioni complesse e funzionali.

Caratteristiche comuni dei widget in Tkinter:
- Ogni widget ha un **widget genitore** (parent) a cui appartiene
- Ogni widget ha proprietà personalizzabili (colori, dimensioni)
- I widget possono rispondere a eventi (clic, pressioni di tasti)

In questa lezione esploreremo i widget fondamentali: Label, Button ed Entry.

## 3.2 Widget Label: mostrare testo

Il widget **Label** (etichetta) è uno dei più semplici in Tkinter. Serve principalmente per visualizzare testo non interattivo.

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Widget Label")
finestra.geometry("300x200")

# Creazione di una semplice etichetta
etichetta1 = tk.Label(finestra, text="Questa è un'etichetta di base")
etichetta1.pack(pady=10)

# Etichetta con formattazione base
etichetta2 = tk.Label(
    finestra,
    text="Etichetta personalizzata",
    font=("Arial", 14),
    fg="blue"  # Colore del testo
)
etichetta2.pack(pady=10)

# Etichetta multilinea
etichetta3 = tk.Label(
    finestra,
    text="Questa è un'etichetta\nsu più righe"
)
etichetta3.pack(pady=10)

finestra.mainloop()
```

## 3.3 Widget Button: creare pulsanti interattivi

I **Button** (pulsanti) sono elementi interattivi che eseguono un'azione quando vengono cliccati.

```python
import tkinter as tk
from tkinter import messagebox

finestra = tk.Tk()
finestra.title("Widget Button")
finestra.geometry("300x200")

# Funzione per gestire l'evento del pulsante
def saluta():
    messagebox.showinfo("Saluto", "Ciao, benvenuto in Tkinter!")

# Pulsante base
pulsante1 = tk.Button(finestra, text="Saluta", command=saluta)
pulsante1.pack(pady=10)

# Pulsante che cambia il proprio testo
def cambia_testo():
    if pulsante2["text"] == "Cliccami":
        pulsante2["text"] = "Sono stato cliccato!"
    else:
        pulsante2["text"] = "Cliccami"

pulsante2 = tk.Button(finestra, text="Cliccami", command=cambia_testo)
pulsante2.pack(pady=10)

# Pulsante per uscire
pulsante_esci = tk.Button(
    finestra,
    text="Esci",
    command=finestra.destroy  # Chiude la finestra
)
pulsante_esci.pack(pady=10)

finestra.mainloop()
```

## 3.4 Widget Entry: campi di input

Il widget **Entry** permette di raccogliere input di testo dagli utenti.

```python
import tkinter as tk
from tkinter import messagebox

finestra = tk.Tk()
finestra.title("Widget Entry")
finestra.geometry("300x200")

# Funzione per recuperare il testo dal campo Entry
def mostra_input():
    nome = campo_nome.get()
    if nome:
        messagebox.showinfo("Input", f"Hai inserito: {nome}")
    else:
        messagebox.showwarning("Attenzione", "Campo vuoto")

# Etichetta e campo per il nome
tk.Label(finestra, text="Nome:").pack(pady=(10, 0))
campo_nome = tk.Entry(finestra, width=30)
campo_nome.pack(pady=5)

# Campo password (nasconde i caratteri)
tk.Label(finestra, text="Password:").pack(pady=(10, 0))
campo_password = tk.Entry(finestra, width=30, show="*")  # show="*" nasconde i caratteri
campo_password.pack(pady=5)

# Pulsante per inviare
pulsante_invia = tk.Button(
    finestra,
    text="Invia",
    command=mostra_input
)
pulsante_invia.pack(pady=10)

finestra.mainloop()
```

## 3.5 Posizionamento con il metodo pack()

Il gestore di layout `pack()` è il modo più semplice per posizionare widget in Tkinter.

Opzioni base di pack():
- `side`: Specifica il lato a cui attaccare il widget (tk.TOP, tk.BOTTOM, tk.LEFT, tk.RIGHT)
- `padx`, `pady`: Aggiungono spazio esterno orizzontale e verticale

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Layout con pack()")
finestra.geometry("300x200")

# Widget posizionati con side=tk.TOP (default)
tk.Label(finestra, text="Widget in alto").pack(pady=5)

# Widget posizionati orizzontalmente
frame = tk.Frame(finestra)
frame.pack(pady=10)

tk.Button(frame, text="Sinistra").pack(side=tk.LEFT, padx=5)
tk.Button(frame, text="Centro").pack(side=tk.LEFT, padx=5)
tk.Button(frame, text="Destra").pack(side=tk.LEFT, padx=5)

# Widget in basso
tk.Label(finestra, text="Widget in basso").pack(pady=5)

finestra.mainloop()
```

## 3.6 Esercizio pratico: creazione di un semplice form

Mettiamo insieme quanto appreso per creare un semplice form:

```python
import tkinter as tk
from tkinter import messagebox

def invia_dati():
    nome = campo_nome.get().strip()
    cognome = campo_cognome.get().strip()
    
    if nome and cognome:
        messagebox.showinfo("Dati", f"Nome: {nome}\nCognome: {cognome}")
    else:
        messagebox.showerror("Errore", "Compila tutti i campi")

# Creazione della finestra principale
finestra = tk.Tk()
finestra.title("Form Semplice")
finestra.geometry("300x200")

# Titolo
titolo = tk.Label(finestra, text="Dati Personali", font=("Arial", 12))
titolo.pack(pady=10)

# Campo Nome
tk.Label(finestra, text="Nome:").pack()
campo_nome = tk.Entry(finestra)
campo_nome.pack(pady=5)

# Campo Cognome
tk.Label(finestra, text="Cognome:").pack()
campo_cognome = tk.Entry(finestra)
campo_cognome.pack(pady=5)

# Pulsante
pulsante_invia = tk.Button(finestra, text="Invia", command=invia_dati)
pulsante_invia.pack(pady=10)

# Avvio dell'applicazione
finestra.mainloop()
```

## 3.7 Riepilogo della lezione

In questa lezione abbiamo esplorato:

1. **Il concetto di widget** come componenti fondamentali delle interfacce Tkinter
2. **Label**: per visualizzare testo
3. **Button**: per creare elementi interattivi
4. **Entry**: per raccogliere input di testo dagli utenti
5. **Posizionamento con pack()**: per organizzare i widget nella finestra
6. **Applicazione pratica**: creazione di un form semplice

Questi tre widget costituiscono la base di molte applicazioni Tkinter. Padroneggiarli ti permetterà di creare interfacce funzionali e intuitive.

## 3.8 Esercizi da svolgere

1. Crea una semplice calcolatrice con due campi di input e un pulsante che mostri il risultato della somma.
2. Realizza un'applicazione che converta metri in centimetri quando l'utente inserisce un valore e preme un pulsante.
3. Progetta una schermata di login con campi per username e password e un pulsante per l'accesso.

# 4. Interattività e gestione degli eventi

## 4.1 Concetto di eventi e callback

Le interfacce grafiche sono basate sul concetto di **eventi**, che sono azioni dell'utente come click del mouse, pressioni di tasti o movimenti. In Tkinter, questi eventi vengono gestiti attraverso **funzioni di callback**, che vengono eseguite quando si verifica un determinato evento.

Un **callback** è una funzione che viene "chiamata indietro" (richiamata) dal sistema quando accade qualcosa. È il modo principale per rendere interattiva la tua applicazione.

## 4.2 Collegare funzioni agli eventi (bind)

Esistono due modi principali per collegare gli eventi alle funzioni in Tkinter:

1. Usando l'opzione `command` per widget interattivi come i pulsanti
2. Usando il metodo `bind()` per gestire eventi più specifici

### 4.2.1 Opzione command

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Eventi con command")
finestra.geometry("300x200")

# Funzione di callback
def azione_pulsante():
    etichetta.config(text="Hai cliccato il pulsante!")

# Etichetta che cambierà
etichetta = tk.Label(finestra, text="Clicca il pulsante")
etichetta.pack(pady=20)

# Pulsante con comando
pulsante = tk.Button(finestra, text="Cliccami", command=azione_pulsante)
pulsante.pack()

finestra.mainloop()
```

### 4.2.2 Metodo bind()

Il metodo `bind()` permette di collegare qualsiasi evento a una funzione:

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Eventi con bind")
finestra.geometry("300x200")

# Funzione che gestisce l'evento
def su_click(evento):
    etichetta.config(text=f"Hai cliccato alle coordinate: {evento.x}, {evento.y}")

# Etichetta che mostrerà informazioni
etichetta = tk.Label(finestra, text="Clicca ovunque nella finestra")
etichetta.pack(pady=20)

# Collega l'evento di click alla finestra
finestra.bind("<Button-1>", su_click)  # Button-1 è il click sinistro del mouse

finestra.mainloop()
```

## 4.3 Gestire click del mouse e input da tastiera

### 4.3.1 Eventi del mouse

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Eventi del mouse")
finestra.geometry("300x200")

# Creiamo un'area di disegno (un canvas)
canvas = tk.Canvas(finestra, bg="white")
canvas.pack(fill=tk.BOTH, expand=True, padx=10, pady=10)

# Etichetta per mostrare le coordinate
info = tk.Label(finestra, text="Muovi il mouse o clicca sul canvas")
info.pack(pady=5)

# Funzioni per gli eventi del mouse
def su_movimento(evento):
    info.config(text=f"Posizione: {evento.x}, {evento.y}")

def su_click(evento):
    # Disegna un piccolo cerchio dove l'utente ha cliccato
    canvas.create_oval(evento.x-5, evento.y-5, evento.x+5, evento.y+5, fill="blue")
    info.config(text=f"Click alle coordinate: {evento.x}, {evento.y}")

# Collegamento degli eventi
canvas.bind("<Motion>", su_movimento)  # Movimento del mouse
canvas.bind("<Button-1>", su_click)    # Click sinistro

finestra.mainloop()
```

### 4.3.2 Eventi della tastiera

```python
import tkinter as tk

finestra = tk.Tk()
finestra.title("Eventi della tastiera")
finestra.geometry("300x200")

# Etichetta per le istruzioni
tk.Label(finestra, text="Premi qualsiasi tasto").pack(pady=10)

# Etichetta per mostrare il tasto premuto
info = tk.Label(finestra, text="", font=("Arial", 14))
info.pack(pady=20)

# Campo di input per dimostrare gli eventi da tastiera
campo = tk.Entry(finestra)
campo.pack(pady=10)
campo.focus()  # Mette il focus sul campo di input

# Funzione per gestire la pressione di un tasto
def su_tastiera(evento):
    info.config(text=f"Hai premuto: {evento.char} (codice: {evento.keycode})")

# Collegamento dell'evento
finestra.bind("<Key>", su_tastiera)

finestra.mainloop()
```

## 4.4 Messaggi e finestre di dialogo

Tkinter offre finestre di dialogo predefinite per interagire con l'utente:

```python
import tkinter as tk
from tkinter import messagebox

finestra = tk.Tk()
finestra.title("Finestre di dialogo")
finestra.geometry("300x250")

# Funzioni per mostrare diverse finestre di dialogo
def mostra_info():
    messagebox.showinfo("Informazione", "Questa è una finestra informativa.")

def mostra_errore():
    messagebox.showerror("Errore", "Si è verificato un errore.")

def mostra_avviso():
    messagebox.showwarning("Avviso", "Questa è un'operazione rischiosa.")

def chiedi_si_no():
    risposta = messagebox.askyesno("Domanda", "Vuoi continuare?")
    if risposta:
        etichetta.config(text="Hai scelto: Sì")
    else:
        etichetta.config(text="Hai scelto: No")

# Etichetta per mostrare i risultati
etichetta = tk.Label(finestra, text="Scegli un tipo di messaggio")
etichetta.pack(pady=10)

# Pulsanti per i vari tipi di messaggi
tk.Button(finestra, text="Informazione", command=mostra_info).pack(pady=5)
tk.Button(finestra, text="Errore", command=mostra_errore).pack(pady=5)
tk.Button(finestra, text="Avviso", command=mostra_avviso).pack(pady=5)
tk.Button(finestra, text="Domanda Sì/No", command=chiedi_si_no).pack(pady=5)

finestra.mainloop()
```

## 4.5 Esercizio pratico: creazione di un convertitore di unità di misura

Creiamo una semplice applicazione per convertire chilometri in miglia:

```python
import tkinter as tk
from tkinter import messagebox

# Funzione di conversione
def converti():
    try:
        km = float(input_km.get())
        miglia = km * 0.621371
        risultato.config(text=f"{km} km = {miglia:.2f} miglia")
    except ValueError:
        messagebox.showerror("Errore", "Inserisci un numero valido")

# Creazione della finestra
finestra = tk.Tk()
finestra.title("Convertitore km → miglia")
finestra.geometry("300x200")
finestra.resizable(False, False)

# Titolo
tk.Label(finestra, text="Convertitore di distanza", font=("Arial", 12)).pack(pady=10)

# Area di input
frame_input = tk.Frame(finestra)
frame_input.pack(pady=10)

tk.Label(frame_input, text="Chilometri:").pack(side=tk.LEFT)
input_km = tk.Entry(frame_input, width=10)
input_km.pack(side=tk.LEFT, padx=5)
input_km.focus()

# Associare l'evento Enter al campo di input
input_km.bind("<Return>", lambda event: converti())

# Pulsante di conversione
tk.Button(finestra, text="Converti", command=converti).pack(pady=10)

# Risultato
risultato = tk.Label(finestra, text="")
risultato.pack(pady=10)

finestra.mainloop()
```

## 4.6 Riepilogo della lezione

In questa lezione abbiamo esplorato:

1. Il concetto di **eventi** e **callback** in Tkinter
2. Due modi per collegare gli eventi alle funzioni:
   - L'opzione `command` per widget interattivi
   - Il metodo `bind()` per eventi più specifici
3. Come gestire gli eventi del **mouse** e della **tastiera**
4. Come utilizzare le **finestre di dialogo** per comunicare con l'utente
5. Come applicare questi concetti in un semplice **convertitore di unità**

Gli eventi sono fondamentali per creare applicazioni interattive. Con la gestione degli eventi, le tue applicazioni Tkinter possono rispondere alle azioni dell'utente in modo dinamico.

## 4.7 Esercizi da svolgere

1. Crea un'applicazione con un campo di testo che mostri i caratteri digitati in maiuscolo mentre l'utente scrive.
2. Realizza un semplice disegnatore in cui l'utente può disegnare linee tenendo premuto il mouse e trascinandolo.
3. Sviluppa un'applicazione che mostri le coordinate x,y del mouse quando si muove sopra una finestra.
