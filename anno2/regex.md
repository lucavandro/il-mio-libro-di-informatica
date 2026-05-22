Le Espressioni Regolari in Python

In questo capitolo esploreremo uno strumento che molti programmatori considerano quasi magico: le **Espressioni Regolari**, spesso abbreviate come **Regex**. Sebbene a prima vista possano sembrare una sequenza caotica di simboli, esse rappresentano in realtà uno strumento estremamente potente e preciso per caratterizzare e manipolare stringhe di testo. Impareremo come Python, attraverso il suo modulo dedicato, ci permetta di trasformare compiti di ricerca complessi in poche righe di codice eleganti.

---

## 1. Introduzione al Pattern Matching

### 1.1 Che cos'è una Regex e la sua storia
L'idea alla base delle espressioni regolari non è nata con l'informatica moderna, ma ha radici profonde nella teoria matematica. Questo linguaggio è stato formalizzato per la prima volta nel 1956 da un matematico di nome **Stephen Kleene**, che gettò le basi per quella che oggi chiamiamo teoria dei linguaggi regolari. In termini semplici, una Regex è una sequenza di caratteri che definisce uno "schema" (o **pattern**) di testo. Immaginate di dover cercare in un libro non una parola specifica come "ciao", ma tutte le date scritte nel formato "giorno/mese/anno". Fare questo con una ricerca normale sarebbe impossibile, ma con le Regex possiamo descrivere la "forma" di una data e chiedere al computer di trovarla ovunque appaia.

### 1.2 Perché usare le Regex in Python
Nella vita quotidiana di un programmatore, ci si trova costantemente a dover verificare se i dati inseriti dagli utenti sono corretti. Pensate a un modulo di iscrizione online: come facciamo a sapere se l'indirizzo e-mail inserito è scritto correttamente o se un numero di telefono ha il giusto numero di cifre? Le Regex sono lo strumento ideale per queste operazioni di **convalida** e per compiti di "parsing", ovvero l'estrazione di informazioni specifiche da grandi blocchi di testo. Python integra perfettamente queste funzionalità attraverso il modulo `re`, rendendo accessibile a chiunque la capacità di analizzare testi complessi, file digitali o intere pagine web in modo efficiente e veloce.

---

## 2. Fondamenti del Modulo `re`

### 2.1 Configurazione e la funzione `search`
Per iniziare a usare le Regex in Python, il primo passo fondamentale è importare il modulo integrato scrivendo `import re` all'inizio del nostro script. Una delle funzioni più comuni che utilizzeremo è `re.search(pattern, stringa)`. Questa funzione analizza la stringa da sinistra a destra cercando la prima occorrenza che corrisponde allo schema fornito. Se la ricerca ha successo, Python restituisce un "oggetto di corrispondenza" (match object); in caso contrario, restituisce `None`. Una curiosità tecnica importante è l'uso della lettera **'r'** prima della stringa del pattern (es. `r'\d'`). Questa 'r' indica una stringa "grezza" (raw string), che dice a Python di ignorare i significati speciali delle barre rovesciate, facilitando enormemente la scrittura delle Regex.

```python
import re

testo = "Il mio numero fortunato è il 7"
# Cerchiamo se nel testo è presente una cifra numerica
match = re.search(r'\d', testo)

if match:
    print("Corrispondenza trovata:", match.group())
else:
    print("Nessuna cifra trovata.")
```

### 2.2 Trovare tutte le corrispondenze con `findall`
Mentre `re.search` si ferma alla prima corrispondenza, spesso abbiamo bisogno di estrarre *tutti* gli elementi che seguono un certo schema in un intero documento. In questo caso, la funzione più potente è senza dubbio `re.findall()`. Questa funzione setaccia l'intero testo e restituisce una **lista di stringhe** contenente tutte le parti che hanno soddisfatto il nostro pattern. Se, ad esempio, volessimo estrarre tutti i prezzi in euro da un catalogo, `findall` ci restituirebbe un elenco pulito di ogni occorrenza trovata. È uno strumento incredibilmente utile per l'analisi dei dati, poiché evita di dover scrivere complessi cicli "for" per scorrere manualmente ogni riga di un file.

---

## 3. L'Alfabeto delle Espressioni Regolari

### 3.1 Caratteri Speciali e Classi di Caratteri
Nelle Regex, alcuni caratteri non rappresentano se stessi ma hanno poteri speciali. Ad esempio, il punto `.` è un carattere jolly che corrisponde a **qualsiasi carattere singolo**, eccetto il ritorno a capo. Se vogliamo essere più specifici, usiamo le **parentesi quadre** `[]` per definire un set di caratteri: `[abc]` cercherà solo 'a', 'b' o 'c'. Esistono anche abbreviazioni molto comode chiamate metassequenze: `\d` trova qualsiasi cifra da 0 a 9, `\w` trova qualsiasi carattere alfanumerico (lettere o numeri) e `\s` identifica gli spazi bianchi come spazi o tabulazioni. Ricordate che le Regex sono solitamente **case sensitive**, quindi 'A' è diverso da 'a', a meno di non usare istruzioni specifiche.

### 3.2 Ancore e Confini
A volte non ci interessa solo *cosa* stiamo cercando, ma anche *dove* si trova all'interno del testo. Le **ancore** sono simboli speciali che non corrispondono a caratteri reali, ma a posizioni specifiche. L'accento circonflesso `^` indica l'inizio di una stringa o di una riga, mentre il simbolo del dollaro `$` indica la fine. Ad esempio, il pattern `^Ciao` troverà corrispondenza solo se la frase inizia esattamente con "Ciao". Un'altra ancora fondamentale è `\b`, che rappresenta il **confine di una parola**. Usare `\bcane\b` ci permette di trovare la parola "cane" isolata, evitando che il computer si confonda trovandola dentro parole più lunghe come "canestro" o "vulcano".

---

## 4. La Scienza della Ripetizione (Quantificatori)

### 4.1 Gestire le occorrenze con `*`, `+` e `?`
Il vero potere delle Regex emerge quando dobbiamo gestire quantità variabili di testo. I **quantificatori** ci permettono di dire al computer quante volte un carattere o un gruppo deve ripetersi. L'asterisco `*` (chiamato anche Kleene Star) indica "zero o più occorrenze", il che significa che il carattere precedente può esserci tantissime volte o non esserci affatto. Il segno più `+` è simile ma richiede **almeno una** occorrenza. Infine, il punto interrogativo `?` rende l'elemento precedente **opzionale**, ovvero può apparire zero o una volta sola. Pensate alla parola "colore": se volessimo accettare anche la versione inglese "colour", potremmo usare il pattern `colou?re`.

### 4.2 Precisione con le parentesi graffe
Quando i simboli generici non bastano e abbiamo bisogno di un numero esatto di ripetizioni, utilizziamo le **parentesi graffe** `{}`. Questa sintassi ci permette di specificare un intervallo preciso: `{n}` indica esattamente *n* volte, mentre `{n,m}` indica da un minimo di *n* a un massimo di *m* volte. Questo è estremamente utile per convalidare dati strutturati. Se sappiamo che un anno deve avere sempre quattro cifre, scriveremo `\d{4}`. Se invece stiamo cercando nomi propri che hanno tra le 2 e le 10 lettere, potremmo usare un intervallo come `[A-Z][a-z]{1,9}`, assicurandoci che la prima lettera sia maiuscola seguita dal giusto numero di minuscole.

---

## 5. Raggruppamento e Sostituzione

### 5.1 L'uso delle parentesi tonde e l'estrazione di gruppi
Le parentesi tonde `()` servono a creare dei **gruppi logici** all'interno di un pattern. Questo ha due scopi principali: primo, permette di applicare quantificatori a intere sequenze (es. `(abc)+` cercherà "abc", "abcabc", ecc.); secondo, ci permette di **estrarre parti specifiche** del testo trovato. Immaginate di trovare un indirizzo e-mail come "studente@scuola.it": usando i gruppi `([\w.-]+)@([\w.-]+)`, Python potrà isolare il nome utente ("studente") e il dominio ("scuola.it") separatamente tramite il metodo `match.group(1)` e `match.group(2)`. È come avere delle piccole etichette che ci aiutano a smontare le informazioni complesse in pezzi più semplici.

### 5.2 Sostituire il testo con `re.sub`
Oltre a cercare e convalidare, le Regex sono fenomenali per la **pulizia e la trasformazione** del testo. La funzione `re.sub(pattern, sostituto, stringa)` cerca tutte le occorrenze di uno schema e le rimpiazza con un nuovo testo. Una funzione molto interessante è la possibilità di riutilizzare i gruppi catturati nella stringa di sostituzione usando la sintassi `\1`, `\2`, ecc.. Per esempio, se volessimo cambiare tutte le date dal formato "giorno/mese/anno" al formato "giorno-mese-anno", potremmo catturare i numeri con le parentesi e poi ricostruire la stringa usando i trattini, automatizzando un lavoro che a mano richiederebbe ore di noioso "copia e incolla".

---

## 6. Esempio Pratico: Convalida di una E-mail

Mettiamo ora in pratica tutto ciò che abbiamo imparato per creare un algoritmo che verifichi se una stringa è un indirizzo e-mail valido. Un'e-mail tipica è composta da una parte locale, il simbolo `@` e un dominio. Per farlo, utilizzeremo la funzione `re.fullmatch()`, che assicura che **l'intera stringa** corrisponda allo schema, evitando che frammenti di testo non validi vengano accettati. Lo schema che utilizzeremo controllerà una sequenza di caratteri alfanumerici (inclusi punti e trattini), seguita dalla chiocciola, un nome di dominio e infine un'estensione (come .com o .it) lunga tra i 2 e i 7 caratteri.

```python
import re

def controlla_email(email):
    # Definiamo il pattern per una e-mail standard
    regex_email = r'[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z]{2,7}'
    
    # re.fullmatch controlla che l'intera stringa segua il pattern
    if re.fullmatch(regex_email, email):
        return "E-mail valida!"
    else:
        return "E-mail non valida."

# Testiamo il nostro programma
print(controlla_email("studente.scuola@esempio.it")) # Valida
print(controlla_email("email-sbagliata@com"))        # Non valida
```
*Curiosità:* Le Regex possono diventare incredibilmente complicate per gestire ogni possibile caso di e-mail esistente al mondo. Spesso i programmatori scherzano dicendo che scrivere la Regex "perfetta" per le e-mail è una sfida impossibile, ma per la maggior parte degli usi quotidiani, uno schema come quello sopra è più che sufficiente.

---

## Esercizi di Comprensione

1. **Esercizio di Ricerca:** Scrivi una Regex che trovi tutte le parole che iniziano con la lettera 'p' e finiscono con la lettera 'o' in una frase (es. "primo", "palo"). [Suggerimento: usa `\b`, `p`, `\w*` e `o\b`]
2. **Esercizio sulle Date:** Crea uno script Python che estragga tutti gli anni (sequenze di esattamente 4 cifre) da questo testo: "La guerra iniziò nel 1914 e terminò nel 1918. Il trattato fu firmato nel 1919."
3. **Esercizio di Sostituzione:** Usando `re.sub`, scrivi un codice che censuri tutti i numeri di telefono in un testo, sostituendoli con la parola "[RISERVATO]". Supponi che i telefoni siano composti da 10 cifre consecutive.

---

## Domande di Verifica

*   Chi è considerato il padre delle espressioni regolari e in che anno le ha formalizzate?
*   Qual è la differenza principale tra le funzioni `re.search()` e `re.findall()`?
*   Cosa succede se inseriamo il simbolo `^` all'inizio di un pattern Regex? E se lo inseriamo all'interno di parentesi quadre come `[^abc]`?
*   Cosa si intende per comportamento "Greedy" (ingordo) dei quantificatori come `*` e `+`?
*   A cosa serve il prefisso `r` davanti alle stringhe dei pattern in Python?

Con questo si conclude la nostra lezione sulle espressioni regolari. Ricordate: la pratica è fondamentale! Utilizzate siti come **regex101.com** per testare i vostri pattern e non scoraggiatevi se all'inizio sembrano difficili; presto diventeranno uno degli strumenti più preziosi nel vostro zaino da programmatori.

Ti piacerebbe che creassi un quiz interattivo su questi argomenti per testare ulteriormente le tue conoscenze?