# I File in Python
## 1. Introduzione ai File e Operazioni Base

### 1. Cosa è un File?
Un file è come una scatola dove il computer conserva le informazioni. Proprio come possiamo avere scatole per diversi tipi di oggetti (vestiti, giocattoli, libri), anche i file possono contenere diversi tipi di dati:
- Testo (come le note che scriviamo)
- Immagini
- Video
- Programmi
- ...e molto altro!

### 2. Tipi di File in Python
In Python, ci concentreremo principalmente su due tipi di file:

1. **File di testo**: Contengono caratteri leggibili dall'uomo (lettere, numeri, simboli)
   - Esempi: .txt, .csv, .py
   - Possiamo aprirli con un semplice editor di testo

2. **File binari**: Contengono dati in formato macchina
   - Esempi: .jpg, .mp3, .pdf
   - Richiedono programmi specifici per essere letti

### 3. Come Aprire un File
In Python, usiamo la funzione `open()` per aprire un file. È come aprire una porta per entrare in una stanza!

```python
# Modo base per aprire un file
file = open('mio_file.txt', 'r')
# Fare qualcosa con il file...
file.close()  # Importante: chiudere sempre il file!

# Modo migliore (consigliato):
with open('mio_file.txt', 'r') as file:
    # Fare qualcosa con il file...
    contenuto = file.read()
# Il file viene chiuso automaticamente!
```

### 4. Modalità di Apertura
Quando apriamo un file, dobbiamo dire a Python cosa vogliamo farci:

```python
# Lettura (r): per leggere il contenuto
with open('note.txt', 'r') as file:
    contenuto = file.read()

# Scrittura (w): per scrivere (attenzione: cancella il contenuto esistente!)
with open('note.txt', 'w') as file:
    file.write('Ciao mondo!')

# Append (a): per aggiungere contenuto alla fine
with open('note.txt', 'a') as file:
    file.write('\nNuova riga!')
```

### 5. Operazioni Base sui File

#### Leggere un file intero:
```python
with open('esempio.txt', 'r') as file:
    contenuto = file.read()
    print(contenuto)
```

#### Leggere una riga alla volta:
```python
with open('esempio.txt', 'r') as file:
    prima_riga = file.readline()
    print(prima_riga)
```

#### Scrivere in un file:
```python
with open('nuovo.txt', 'w') as file:
    file.write('Prima riga\n')
    file.write('Seconda riga')
```

### 6. Gestione degli Errori
È importante gestire i possibili errori quando lavoriamo con i file:

```python
try:
    with open('file_che_forse_non_esiste.txt', 'r') as file:
        contenuto = file.read()
except FileNotFoundError:
    print("Mi dispiace, il file non esiste!")
```

## Esercizi Pratici

### Esercizio 1: Il Primo File
Scrivi un programma che crea un nuovo file chiamato "diario.txt" e ci scrive dentro la data di oggi e il tuo nome.

### Esercizio 2: Il Lettore
Crea un file di testo con alcune righe di testo. Scrivi un programma che legge il file e stampa il numero totale di righe presenti.

### Esercizio 3: Il Copione
Scrivi un programma che:
1. Legge il contenuto di un file "origine.txt"
2. Crea una copia chiamata "backup.txt"
3. Aggiunge alla fine del backup la data e l'ora della copia

### Esercizio 4: L'Appendice
Scrivi un programma che chiede all'utente di inserire delle note (una alla volta) e le aggiunge in fondo a un file "note.txt". Il programma deve continuare a chiedere input finché l'utente non scrive "FINE".

### Esercizio 5: Il Contatore
Crea un programma che:
1. Legge un file di testo
2. Conta quante volte appare ogni vocale (a,e,i,o,u)
3. Salva i risultati in un nuovo file chiamato "statistiche.txt"

### Suggerimenti per gli Esercizi
- Inizia sempre testando il tuo codice con file piccoli
- Usa la struttura `with` per gestire i file
- Ricordati di gestire possibili errori con try/except
- Per l'esercizio 4, puoi usare un ciclo while
- Per l'esercizio 5, puoi usare un dizionario per tenere il conto

### Note Finali
- Ricordati sempre di chiudere i file dopo averli usati (o usa `with`)
- Fai attenzione quando usi la modalità 'w' perché cancella il contenuto esistente
- Se il file non esiste, la modalità 'w' lo crea automaticamente
- La modalità 'a' è più sicura se vuoi preservare il contenuto esistente

## 2. Metodi di Lettura e Gestione degli Errori

### 1. I Tre Modi per Leggere un File
Python ci offre tre metodi principali per leggere i file, ognuno utile in situazioni diverse:

#### 1.1 Lettura Completa con read()
Legge tutto il file in una sola stringa:
```python
with open('libro.txt', 'r') as file:
    contenuto = file.read()  # Tutto il file in una stringa
    print(contenuto)
    
# Se vuoi leggere solo i primi N caratteri:
with open('libro.txt', 'r') as file:
    primi_10_caratteri = file.read(10)
    print(primi_10_caratteri)
```

#### 1.2 Lettura Riga per Riga con readline()
Legge una riga alla volta:
```python
with open('note.txt', 'r') as file:
    prima_riga = file.readline()    # Legge la prima riga
    seconda_riga = file.readline()  # Legge la seconda riga
    print(f"Prima riga: {prima_riga}")
    print(f"Seconda riga: {seconda_riga}")
```

#### 1.3 Lettura di Tutte le Righe con readlines()
Legge tutte le righe in una lista:
```python
with open('lista_spesa.txt', 'r') as file:
    righe = file.readlines()  # Lista dove ogni elemento è una riga
    for riga in righe:
        print(f"Devo comprare: {riga.strip()}")  # strip() rimuove \n
```

### 2. Iterazione sui File
Python permette di iterare direttamente sul file, riga per riga:

```python
# Modo efficiente per leggere file grandi
with open('file_grande.txt', 'r') as file:
    for riga in file:  # Legge una riga alla volta
        print(riga.strip())
```

### 3. Gestione degli Errori Comuni

#### 3.1 File Non Trovato
```python
try:
    with open('file_inesistente.txt', 'r') as file:
        contenuto = file.read()
except FileNotFoundError:
    print("Ops! Il file non esiste!")
```

#### 3.2 Problemi di Codifica (Encoding)
```python
# Specifichiamo l'encoding per file con caratteri speciali
try:
    with open('testo_italiano.txt', 'r', encoding='utf-8') as file:
        contenuto = file.read()
except UnicodeDecodeError:
    print("Problema con la codifica del file!")
```

### 4. Esempi Pratici

#### Esempio 1: Contare le Righe
```python
def conta_righe(nome_file):
    try:
        with open(nome_file, 'r') as file:
            return len(file.readlines())
    except FileNotFoundError:
        return "File non trovato"

numero_righe = conta_righe('poesia.txt')
print(f"Il file contiene {numero_righe} righe")
```

#### Esempio 2: Ricerca in un File
```python
def cerca_parola(nome_file, parola):
    try:
        with open(nome_file, 'r') as file:
            for numero_riga, riga in enumerate(file, 1):
                if parola in riga:
                    print(f"Trovato '{parola}' alla riga {numero_riga}")
    except FileNotFoundError:
        print("File non trovato")

cerca_parola('storia.txt', 'drago')
```

#### Esempio 3: Lettura con Buffer
```python
def leggi_a_blocchi(nome_file, dimensione_blocco=1024):
    try:
        with open(nome_file, 'r') as file:
            while True:
                blocco = file.read(dimensione_blocco)
                if not blocco:  # Fine del file
                    break
                print(f"Letto un blocco di {len(blocco)} caratteri")
    except FileNotFoundError:
        print("File non trovato")
```

## Esercizi Pratici

### Esercizio 1: L'Analizzatore
Scrivi un programma che legge un file di testo e conta:
- Il numero totale di caratteri
- Il numero di parole
- Il numero di righe
Salva queste statistiche in un nuovo file chiamato "analisi.txt"

### Esercizio 2: Il Cercatore
Crea un programma che chiede all'utente una parola e cerca tutte le righe in un file che contengono quella parola. Deve mostrare il numero della riga e la riga stessa.

### Esercizio 3: Il Formattatore
Scrivi un programma che legge un file di testo e crea una nuova versione del file dove:
- Ogni riga è numerata
- Le righe vuote sono rimosse
- Tutto il testo è convertito in maiuscolo

### Esercizio 4: Lo Splitter
Crea un programma che legge un file di testo grande e lo divide in file più piccoli, ognuno contenente al massimo 100 righe. I nuovi file devono chiamarsi "parte1.txt", "parte2.txt", ecc.

### Esercizio 5: Il Validatore
Scrivi un programma che verifica se un file di testo contiene indirizzi email validi. Il programma deve:
- Leggere il file riga per riga
- Identificare possibili indirizzi email (usando criteri semplici come la presenza di @ e .)
- Creare due file: "email_validi.txt" e "email_non_validi.txt"

### Suggerimenti per gli Esercizi
- Usa i metodi di lettura più appropriati per ogni esercizio
- Ricordati di gestire sempre possibili errori
- Per l'esercizio 1, puoi usare len() e split()
- Per l'esercizio 2, enumerate() può essere molto utile
- Per l'esercizio 5, puoi usare le stringhe di metodo come find() o split()

### Note Finali
- read() è utile per file piccoli, ma può consumare molta memoria con file grandi
- readline() e l'iterazione diretta sono più efficienti per file grandi
- Ricordati sempre di chiudere i file o usare with
- strip() è molto utile per rimuovere spazi e newline indesiderati


## 3. Scrittura dei File e Modalità di Apertura

### 1. Le Modalità di Apertura dei File
Quando scriviamo su un file, dobbiamo scegliere la modalità giusta:

#### 1.1 Modalità 'w' (write)
Crea un nuovo file o sovrascrive quello esistente:
```python
# ATTENZIONE: cancella tutto il contenuto precedente!
with open('note.txt', 'w') as file:
    file.write('Questa è una nuova nota')
```

#### 1.2 Modalità 'a' (append)
Aggiunge contenuto alla fine del file:
```python
# Mantiene il contenuto esistente e aggiunge in fondo
with open('diario.txt', 'a') as file:
    file.write('\nOggi è stata una bella giornata')
```

#### 1.3 Modalità 'r+' (read and write)
Permette sia lettura che scrittura:
```python
with open('documento.txt', 'r+') as file:
    contenuto = file.read()     # Prima leggiamo
    file.write('Nuovo testo')   # Poi scriviamo
```

### 2. Metodi di Scrittura

#### 2.1 write() - Scrittura di stringhe
```python
with open('messaggio.txt', 'w') as file:
    file.write('Prima riga\n')  # \n per andare a capo
    file.write('Seconda riga')
```

#### 2.2 writelines() - Scrittura di liste
```python
righe = ['Riga 1\n', 'Riga 2\n', 'Riga 3\n']
with open('lista.txt', 'w') as file:
    file.writelines(righe)
```

### 3. Formattazione del Testo

#### 3.1 Andare a Capo
```python
with open('poesia.txt', 'w') as file:
    file.write('Nel mezzo del cammin\n')
    file.write('di nostra vita\n')
    
# Oppure usando un'unica stringa
with open('poesia.txt', 'w') as file:
    file.write('''Nel mezzo del cammin
di nostra vita''')
```

#### 3.2 Formattazione Avanzata
```python
nome = "Mario"
età = 25
with open('persona.txt', 'w') as file:
    # Usando f-strings
    file.write(f'Nome: {nome}\n')
    file.write(f'Età: {età} anni\n')
    
    # Usando format()
    file.write('Nome: {}\nEtà: {} anni\n'.format(nome, età))
```

### 4. Gestione degli Errori nella Scrittura

#### 4.1 Gestione Base degli Errori
```python
try:
    with open('C:/cartella_protetta/file.txt', 'w') as file:
        file.write('Testo di prova')
except PermissionError:
    print("Non hai i permessi per scrivere in questo file!")
except IOError:
    print("Si è verificato un errore di I/O!")
```

#### 4.2 Verifica Prima della Scrittura
```python
import os

def scrivi_sicuro(nome_file, contenuto):
    if os.path.exists(nome_file):
        risposta = input(f"Il file {nome_file} esiste già. Sovrascrivere? (s/n): ")
        if risposta.lower() != 's':
            return False
            
    try:
        with open(nome_file, 'w') as file:
            file.write(contenuto)
        return True
    except Exception as e:
        print(f"Errore durante la scrittura: {e}")
        return False
```

### 5. Esempi Pratici

#### Esempio 1: Diario Digitale
```python
from datetime import datetime

def aggiungi_al_diario(testo):
    data = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
    with open('diario.txt', 'a') as file:
        file.write(f'\n[{data}]\n{testo}\n')

aggiungi_al_diario("Oggi ho imparato a scrivere sui file in Python!")
```

#### Esempio 2: Copia con Modifica
```python
def copia_maiuscolo(file_origine, file_destinazione):
    try:
        with open(file_origine, 'r') as origine:
            with open(file_destinazione, 'w') as dest:
                for riga in origine:
                    dest.write(riga.upper())
    except FileNotFoundError:
        print("File di origine non trovato!")
```

## Esercizi Pratici

### Esercizio 1: Il Registro
Crea un programma che gestisce un registro presenze. Deve:
- Chiedere nome e ora di arrivo degli studenti
- Salvare i dati in un file "registro.txt"
- Ogni nuova registrazione deve essere aggiunta in fondo
- Formattare ogni riga come: "Nome - Data/Ora - Presente"

### Esercizio 2: Il Convertitore
Scrivi un programma che:
- Legge un file di testo
- Crea una nuova versione dove ogni parola è invertita
- Mantiene la punteggiatura e gli spazi originali
Esempio: "Ciao mondo!" → "oaiC odnom!"

### Esercizio 3: L'Archivista
Crea un sistema di note dove:
- L'utente può aggiungere nuove note
- Ogni nota ha un titolo e un contenuto
- Le note vengono salvate in file separati
- Viene mantenuto un indice di tutte le note in "indice.txt"

### Esercizio 4: Il Backup
Scrivi un programma che:
- Monitora un file di testo
- Ogni volta che viene modificato, crea una nuova versione di backup
- I backup devono avere nomi come "file_backup_1.txt", "file_backup_2.txt", ecc.
- Mantiene al massimo gli ultimi 5 backup

### Esercizio 5: Il Logger
Crea un sistema di logging che:
- Registra eventi con timestamp
- Supporta diversi livelli (INFO, WARNING, ERROR)
- Scrive in file diversi basandosi sul livello
- Ruota i file quando superano una certa dimensione

### Suggerimenti per gli Esercizi
- Usa datetime per gestire date e orari
- Ricordati di gestire sempre gli errori possibili
- Per l'esercizio 2, puoi usare le funzioni di stringa
- Per l'esercizio 4, usa os.path per gestire i file
- Per l'esercizio 5, considera di creare una classe Logger

### Note Finali
- Preferisci 'a' a 'w' quando non vuoi perdere dati esistenti
- Usa sempre with per gestire l'apertura/chiusura dei file
- Verifica sempre se hai i permessi necessari
- Fai backup dei file importanti prima di modificarli

## 5. Gestione Avanzata dei File e Directory

### 1. Il Modulo os
Il modulo `os` ci permette di interagire con il sistema operativo e gestire file e cartelle.

#### 1.1 Importare il modulo
```python
import os
```

#### 1.2 Percorsi File
```python
# Percorso corrente
percorso_attuale = os.getcwd()  # get current working directory
print(f"Mi trovo in: {percorso_attuale}")

# Unire percorsi in modo sicuro
cartella = "documenti"
file = "note.txt"
percorso_completo = os.path.join(cartella, file)
# Risultato su Windows: "documenti\note.txt"
# Risultato su Linux/Mac: "documenti/note.txt"

# Verificare se un file esiste
if os.path.exists("documento.txt"):
    print("Il file esiste!")

# Separare nome file ed estensione
nome_file, estensione = os.path.splitext("documento.txt")
print(f"Nome: {nome_file}, Estensione: {estensione}")
```

#### 1.3 Gestione Directory
```python
# Creare una nuova directory
try:
    os.mkdir("nuova_cartella")  # Crea una singola cartella
    os.makedirs("cartella/sottocartella")  # Crea anche le cartelle intermedie
except FileExistsError:
    print("La cartella esiste già!")

# Elencare contenuto di una directory
contenuto = os.listdir(".")  # "." indica la directory corrente
for elemento in contenuto:
    print(elemento)

# Rimuovere directory
os.rmdir("cartella_vuota")  # Solo se vuota
import shutil  # Per rimuovere directory con contenuto
shutil.rmtree("cartella_piena")  # ATTENZIONE: elimina tutto!
```

### 2. Il Modulo shutil
`shutil` fornisce operazioni più avanzate sui file.

```python
import shutil

# Copiare un file
shutil.copy("origine.txt", "destinazione.txt")  # Copia il file
shutil.copy2("origine.txt", "destinazione.txt")  # Copia anche i metadati

# Copiare una directory
shutil.copytree("cartella_origine", "cartella_destinazione")

# Spostare file o directory
shutil.move("vecchia_posizione.txt", "nuova_posizione.txt")

# Ottenere spazio su disco
totale, usato, libero = shutil.disk_usage(".")
print(f"Spazio libero: {libero // (2**30)} GB")
```

### 3. Gestione Permessi e Metadati

```python
import os
from datetime import datetime

# Ottenere informazioni sul file
stat_info = os.stat("file.txt")
print(f"Dimensione: {stat_info.st_size} bytes")
print(f"Ultima modifica: {datetime.fromtimestamp(stat_info.st_mtime)}")
print(f"Ultimo accesso: {datetime.fromtimestamp(stat_info.st_atime)}")

# Modificare i permessi (su Unix/Linux)
os.chmod("file.txt", 0o755)  # rwxr-xr-x

# Modificare il proprietario (su Unix/Linux)
# os.chown("file.txt", uid, gid)  # Richiede privilegi root
```

### 4. Esempi Pratici

#### Esempio 1: Scanner di Directory
```python
def scansiona_directory(percorso):
    """Scansiona una directory e mostra la struttura."""
    for radice, directory, files in os.walk(percorso):
        livello = radice.replace(percorso, '').count(os.sep)
        indent = ' ' * 4 * livello
        print(f"{indent}{os.path.basename(radice)}/")
        sub_indent = ' ' * 4 * (livello + 1)
        for file in files:
            print(f"{sub_indent}{file}")

# Uso
scansiona_directory("progetto")
```

#### Esempio 2: Organizzatore di File
```python
def organizza_per_estensione(cartella):
    """Organizza i file in sottocartelle basate sull'estensione."""
    for file in os.listdir(cartella):
        if os.path.isfile(os.path.join(cartella, file)):
            # Ottieni l'estensione
            ext = os.path.splitext(file)[1][1:]
            if not ext:  # Se non c'è estensione
                ext = 'senza_estensione'
                
            # Crea la cartella se non esiste
            cartella_dest = os.path.join(cartella, ext)
            os.makedirs(cartella_dest, exist_ok=True)
            
            # Sposta il file
            origine = os.path.join(cartella, file)
            destinazione = os.path.join(cartella_dest, file)
            shutil.move(origine, destinazione)
```

### 5. Pattern Comuni

#### 5.1 Ricerca Ricorsiva
```python
def trova_file(nome, percorso_iniziale):
    """Cerca un file in modo ricorsivo."""
    for radice, dirs, files in os.walk(percorso_iniziale):
        if nome in files:
            return os.path.join(radice, nome)
    return None
```

#### 5.2 Backup di Directory
```python
def backup_directory(origine, destinazione):
    """Crea un backup con timestamp."""
    timestamp = datetime.now().strftime("%Y%m%d_%H%M%S")
    nome_backup = f"backup_{timestamp}"
    percorso_backup = os.path.join(destinazione, nome_backup)
    
    shutil.copytree(origine, percorso_backup)
    return percorso_backup
```

## Esercizi Pratici

### Esercizio 1: Il Classificatore
Crea un programma che:
- Analizza una cartella
- Identifica tutti i tipi di file presenti
- Crea un report con:
  - Lista delle estensioni trovate
  - Numero di file per ogni estensione
  - Dimensione totale occupata per tipo

### Esercizio 2: Il Pulitore
Scrivi un programma che:
- Cerca file duplicati in una directory (confrontando dimensione e contenuto)
- Mostra i duplicati trovati
- Offre l'opzione di eliminarli mantenendo una sola copia

### Esercizio 3: L'Archivista Automatico
Crea un sistema che:
- Monitora una cartella "da_archiviare"
- Sposta automaticamente i file in sottocartelle basate su:
  - Data di creazione (anno/mese)
  - Tipo di file
  - Dimensione (piccoli/medi/grandi)

### Esercizio 4: Il Backup Manager
Implementa un sistema di backup che:
- Mantiene una storia dei backup
- Permette di specificare quali cartelle includere/escludere
- Implementa backup incrementali (solo file modificati)
- Mantiene un log delle operazioni

### Esercizio 5: Lo Spazio Manager
Crea un programma che:
- Analizza lo spazio su disco
- Identifica le cartelle che occupano più spazio
- Trova file non utilizzati da molto tempo
- Genera un report dettagliato

### Suggerimenti per gli Esercizi
- Usa os.walk() per scansioni ricorsive
- Implementa controlli di sicurezza prima di eliminare
- Usa hashlib per confrontare contenuti dei file
- Mantieni log delle operazioni importanti
- Gestisci sempre le eccezioni

### Note Finali
- Testa sempre su piccole directory prima
- Fai particolare attenzione quando elimini file
- Verifica sempre i permessi necessari
- Considera le differenze tra sistemi operativi
- Usa sempre percorsi assoluti per operazioni importanti

# 6. Gestione di File CSV e JSON

### 1. File CSV (Comma-Separated Values)

#### 1.1 Il Modulo csv
```python
import csv
```

#### 1.2 Lettura di File CSV
```python
# Lettura base
with open('dati.csv', 'r', newline='') as file:
    lettore = csv.reader(file)
    for riga in lettore:
        print(riga)  # riga è una lista

# Lettura con intestazioni
with open('studenti.csv', 'r', newline='') as file:
    lettore = csv.DictReader(file)
    for riga in lettore:
        print(riga['nome'], riga['età'])  # accesso per nome colonna
```

#### 1.3 Scrittura di File CSV
```python
# Scrittura base
dati = [
    ['nome', 'età', 'città'],
    ['Mario', '25', 'Roma'],
    ['Luigi', '30', 'Milano']
]
with open('persone.csv', 'w', newline='') as file:
    scrittore = csv.writer(file)
    scrittore.writerows(dati)

# Scrittura con dizionari
studenti = [
    {'nome': 'Mario', 'età': 25, 'città': 'Roma'},
    {'nome': 'Luigi', 'età': 30, 'città': 'Milano'}
]
with open('studenti.csv', 'w', newline='') as file:
    campi = ['nome', 'età', 'città']
    scrittore = csv.DictWriter(file, fieldnames=campi)
    scrittore.writeheader()  # Scrive l'intestazione
    scrittore.writerows(studenti)
```

#### 1.4 Gestione di Dialetti CSV
```python
# Personalizzare il formato CSV
with open('dati.csv', 'w', newline='') as file:
    scrittore = csv.writer(file, delimiter=';',  # usa ; come separatore
                          quotechar='"',         # usa " per le stringhe
                          quoting=csv.QUOTE_MINIMAL)
    scrittore.writerow(['nome', 'indirizzo;con;punto e virgola'])
```

### 2. File JSON (JavaScript Object Notation)

#### 2.1 Il Modulo json
```python
import json
```

#### 2.2 Lettura di File JSON
```python
# Lettura base
with open('config.json', 'r') as file:
    dati = json.load(file)
    print(dati)  # dati è un dizionario Python

# Gestione di JSON complessi
with open('dati_annidati.json', 'r') as file:
    dati = json.load(file)
    print(dati['utenti'][0]['indirizzo']['città'])
```

#### 2.3 Scrittura di File JSON
```python
# Scrittura base
dati = {
    'nome': 'Mario',
    'età': 25,
    'città': 'Roma'
}
with open('persona.json', 'w') as file:
    json.dump(dati, file)

# Scrittura formattata (pretty print)
with open('persona_formattata.json', 'w') as file:
    json.dump(dati, file, indent=4)
```

#### 2.4 Conversione tra Stringhe e JSON
```python
# Da stringa a JSON
stringa_json = '{"nome": "Mario", "età": 25}'
dati = json.loads(stringa_json)
print(dati['nome'])

# Da Python a stringa JSON
dati = {'nome': 'Mario', 'età': 25}
stringa_json = json.dumps(dati)
print(stringa_json)
```

### 3. Esempi Pratici

#### Esempio 1: Convertitore CSV-JSON
```python
def csv_to_json(file_csv, file_json):
    """Converte un file CSV in JSON."""
    dati = []
    with open(file_csv, 'r', newline='') as file_in:
        lettore = csv.DictReader(file_in)
        for riga in lettore:
            dati.append(riga)
    
    with open(file_json, 'w') as file_out:
        json.dump(dati, file_out, indent=4)
```

#### Esempio 2: Analisi Dati CSV
```python
def analizza_vendite(file_csv):
    """Analizza un file CSV di vendite."""
    totale_vendite = 0
    prodotti = {}
    
    with open(file_csv, 'r', newline='') as file:
        lettore = csv.DictReader(file)
        for riga in lettore:
            prezzo = float(riga['prezzo'])
            quantità = int(riga['quantità'])
            prodotto = riga['prodotto']
            
            vendita = prezzo * quantità
            totale_vendite += vendita
            
            if prodotto in prodotti:
                prodotti[prodotto] += vendita
            else:
                prodotti[prodotto] = vendita
    
    return totale_vendite, prodotti
```

### 4. Best Practices

#### 4.1 Gestione degli Errori
```python
def leggi_json_sicuro(percorso):
    try:
        with open(percorso, 'r') as file:
            return json.load(file)
    except FileNotFoundError:
        print(f"File {percorso} non trovato")
        return None
    except json.JSONDecodeError:
        print(f"Errore nella decodifica del JSON in {percorso}")
        return None
```

#### 4.2 Validazione CSV
```python
def valida_csv(percorso, colonne_attese):
    try:
        with open(percorso, 'r', newline='') as file:
            lettore = csv.reader(file)
            intestazioni = next(lettore)
            return set(intestazioni) == set(colonne_attese)
    except Exception as e:
        print(f"Errore durante la validazione: {e}")
        return False
```

## Esercizi Pratici

### Esercizio 1: Il Gestore di Rubrica
Crea un programma che:
- Gestisce una rubrica di contatti
- Permette di aggiungere/modificare/eliminare contatti
- Salva i dati sia in CSV che in JSON
- Implementa la ricerca dei contatti

### Esercizio 2: L'Analizzatore di Dati Meteo
Scrivi un programma che:
- Legge un file CSV con dati meteo (data, temperatura, umidità, pioggia)
- Calcola statistiche mensili
- Genera un report in JSON
- Crea grafici delle tendenze

### Esercizio 3: Il Convertitore di Formati
Crea un sistema che:
- Converte tra diversi formati di file (CSV, JSON, XML)
- Gestisce diverse codifiche di caratteri
- Permette di specificare il formato di output
- Mantiene un log delle conversioni

### Esercizio 4: Il Sistema di Configurazione
Implementa un sistema che:
- Legge configurazioni da JSON
- Permette di modificare le impostazioni
- Valida i dati prima del salvataggio
- Mantiene un backup delle configurazioni precedenti

### Esercizio 5: L'Aggregatore di Dati
Crea un programma che:
- Legge dati da multiple fonti (CSV e JSON)
- Combina i dati in base a chiavi comuni
- Genera report aggregati
- Esporta i risultati in entrambi i formati

### Suggerimenti per gli Esercizi
- Usa le classi per organizzare il codice
- Implementa controlli di validazione
- Gestisci sempre le eccezioni
- Documenta le funzioni principali
- Usa typing per annotare i tipi

### Note Finali
- CSV è ottimo per dati tabulari semplici
- JSON è migliore per dati strutturati e annidati
- Controlla sempre l'encoding dei file
- Fai backup prima di modificare i file
- Valida sempre i dati in input

```markdown
# Capitolo 7: Salvare dati con la libreria Pickle in Python

**Pickle** è una libreria Python che permette di salvare e caricare strutture dati (liste, dizionari, oggetti, ecc.) in file binari. È utile per conservare dati tra diverse esecuzioni di un programma.

## 1. Come funziona Pickle?

Pickle converte ("serializza") un oggetto Python in una sequenza di byte che può essere salvata su disco. Successamente, questi byte possono essere letti e riconvertiti ("deserializzati") nell'oggetto originale.

## 2. Salvare dati con `pickle.dump()`

Per salvare un oggetto in un file:

```python
import pickle

dati = {"nome": "Mario", "punteggio": 85, "livello": 3}

with open("salvataggio.pkl", "wb") as file:  # 'wb' = write binary
    pickle.dump(dati, file)
```

## 3. Caricare dati con `pickle.load()`

Per rileggere i dati salvati:

```python
import pickle

with open("salvataggio.pkl", "rb") as file:  # 'rb' = read binary
    dati_caricati = pickle.load(file)

print(dati_caricati)  # Output: {'nome': 'Mario', 'punteggio': 85, 'livello': 3}
```

## 4. Esempio con una lista di studenti

```python
import pickle

studenti = [
    {"nome": "Anna", "voti": [7, 8, 6]},
    {"nome": "Luigi", "voti": [6, 7, 5]}
]

# Salvataggio
with open("studenti.pkl", "wb") as file:
    pickle.dump(studenti, file)

# Caricamento
with open("studenti.pkl", "rb") as file:
    studenti_caricati = pickle.load(file)

for studente in studenti_caricati:
    print(f"{studente['nome']}: {studente['voti']}")
```

## 5. Avvertenze importanti

- **Sicurezza**: Non caricare file Pickle da fonti sconosciute (potrebbero contenere codice malevolo).
- **Compatibilità**: I file Pickle sono specifici per Python e potrebbero non essere compatibili tra diverse versioni.

## Esercizi

1. **Salvataggio di una lista**  
   Crea una lista di numeri preferiti (es. `[7, 3, 22]`), salvala in un file Pickle e poi ricaricala per stamparla.

2. **Rubrica telefonica**  
   Crea un dizionario `rubrica` con nomi e numeri di telefono (es. `{"Mario": "123456", "Luigi": "654321"}`), salvalo e poi caricalo per modificare un contatto.

3. **Gestione di un inventario**  
   Crea una lista di dizionari `inventario` dove ogni dizionario rappresenta un oggetto con `nome`, `quantità` e `prezzo`. Salva l'inventario e implementa un menu per aggiungere nuovi oggetti.

4. **Sfida - Dati di gioco**  
   Simula un gioco con `{"livello": 1, "punti": 0, "nome_giocatore": "..."}`. Salva lo stato del gioco, poi caricalo e aggiorna i punti prima di risalvare.

5. **Errore controllato**  
   Scrivi un programma che tenti di caricare un file Pickle inesistente gestendo l'eccezione `FileNotFoundError` con un messaggio amichevole.
```