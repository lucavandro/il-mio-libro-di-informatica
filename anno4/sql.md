# SQL e SQLite

## 1. Introduzione a SQL e SQLite

### 1.1 Cos’è un database e a cosa serve

### 1.2 Caratteristiche di SQL

### 1.3 Differenze tra SQL e SQLite

### 1.4 Vantaggi e limiti di SQLite

## 2. Le categorie di comandi SQL

### 2.1 DDL (Data Definition Language)

### 2.2 DML (Data Manipulation Language)

### 2.3 QL (Query Language) / DQL (Data Query Language)

### 2.4 DCL (Data Control Language)

### 2.5 TCL (Transaction Control Language)  <!-- suggerito: importante per capire COMMIT/ROLLBACK -->

## 3. Creazione e gestione delle tabelle

### 3.1 CREATE TABLE: sintassi e opzioni

Per creare una tabella in un database serve il comando `CREATE TABLE`. È come progettare una nuova scheda per la tua collezione di figurine: decidi quali informazioni vuoi raccogliere!

**Esempio:**

Supponiamo di voler creare la tabella dei Comuni:

```sql
CREATE TABLE Comuni (
    ID INTEGER PRIMARY KEY,
    Nome TEXT NOT NULL,
    Provincia TEXT,
    SiglaProvincia TEXT,
    AreaGeografica TEXT,
    Residenti INTEGER,
    Stranieri INTEGER,
    DensitaDemografica REAL,
    Superficie REAL,
    Altezza INTEGER,
    ZonaAltimetrica TEXT,
    TipoComune TEXT,
    GradoUrbanizzazione TEXT,
    ZonaSismica TEXT,
    Regione TEXT
);
```

E per i Sindaci:

```sql
CREATE TABLE Sindaci (
    ID INTEGER PRIMARY KEY,
    Nome TEXT NOT NULL,
    Cognome TEXT NOT NULL,
    Anni INTEGER,
    Partito TEXT,
    Sesso TEXT,
    ComuneID INTEGER,
    FOREIGN KEY (ComuneID) REFERENCES Comuni(ID)
);
```

### 3.2 Tipi di dati in SQLite

Ogni colonna di una tabella ha un tipo di dato, come le etichette su una scatola 📦: ti dicono cosa puoi metterci dentro.

- `INTEGER`: numeri interi (es. 42)
- `REAL`: numeri decimali (es. 3.14)
- `TEXT`: testo (es. "Roma")
- `BLOB`: dati binari (immagini, file)

SQLite è molto flessibile: se provi a inserire un testo in una colonna numerica, spesso non dà errore, ma è buona pratica rispettare i tipi!

### 3.3 Vincoli (PRIMARY KEY, UNIQUE, NOT NULL, DEFAULT, CHECK, FOREIGN KEY)

I vincoli sono le regole del gioco 🎲: servono a garantire che i dati siano corretti e coerenti.

- `PRIMARY KEY`: identifica in modo univoco ogni riga (come il codice fiscale per le persone)
- `UNIQUE`: il valore deve essere unico (es. nessun comune con lo stesso nome e provincia)
- `NOT NULL`: il valore non può essere vuoto
- `DEFAULT`: valore predefinito se non specificato
- `CHECK`: controlla che il valore rispetti una condizione (es. Residenti >= 0)
- `FOREIGN KEY`: collega una tabella a un’altra (es. Sindaci.ComuneID → Comuni.ID)

**Curiosità:**
I vincoli aiutano a evitare errori come avere due sindaci per lo stesso comune, o un comune senza nome!

### 3.4 Modifica e cancellazione tabelle (ALTER TABLE, DROP TABLE)

Se vuoi cambiare la struttura di una tabella (aggiungere una colonna, rinominare, ecc.) usi `ALTER TABLE`. Se vuoi eliminarla del tutto (attenzione! ⚠️), usi `DROP TABLE`.

**Esempio:**

```sql
ALTER TABLE Comuni ADD COLUMN CodiceISTAT TEXT;
DROP TABLE Sindaci;
```

---

## 4. Inserimento, modifica e cancellazione dei dati

### 4.1 INSERT INTO

Per aggiungere dati in una tabella si usa `INSERT INTO`, come aggiungere una nuova scheda alla tua collezione.

**Esempio:**

```sql
INSERT INTO Comuni (Nome, Provincia, Residenti) VALUES ('Roma', 'Roma', 2873000);
```

Per i Sindaci:

```sql
INSERT INTO Sindaci (Nome, Cognome, Anni, Partito, Sesso, ComuneID) VALUES ('Giovanni', 'Rossi', 54, 'Indipendente', 'M', 1);
```

### 4.2 UPDATE

`UPDATE` serve a modificare dati già presenti, come correggere una scheda sbagliata.

**Esempio:**

```sql
UPDATE Comuni SET Residenti = 2874000 WHERE Nome = 'Roma';
```

### 4.3 DELETE

`DELETE` elimina una o più righe da una tabella. Usalo con attenzione, perché una volta cancellato... non si torna indietro! 🗑️

**Esempio:**

```sql
DELETE FROM Sindaci WHERE Nome = 'Giovanni' AND Cognome = 'Rossi';
```

**Curiosità:**
In SQLite puoi annullare una cancellazione solo se usi le transazioni (vedi più avanti)!

## 4. Inserimento, modifica e cancellazione dei dati

Gestire i dati in un database è come aggiornare la tua collezione di figurine: puoi aggiungere nuove figurine (INSERT), correggere quelle che hai (UPDATE) o eliminarle se non ti servono più (DELETE). Vediamo come funzionano questi comandi in SQL, usando le tabelle `Comuni` e `Sindaci` come esempio.

### 4.1 INSERT INTO

Il comando `INSERT INTO` serve per aggiungere nuove righe (record) a una tabella. Immagina di voler aggiungere un nuovo comune alla tua collezione: con `INSERT` crei una nuova "scheda" con tutte le informazioni.

**Sintassi base:**

```sql
INSERT INTO NomeTabella (Colonna1, Colonna2, ...) VALUES (Valore1, Valore2, ...);
```

**Esempio:**  
Aggiungiamo un nuovo comune:

```sql
INSERT INTO Comuni (Nome, Provincia, SiglaProvincia, AreaGeografica, Residenti, Stranieri, DensitaDemografica, Superficie, Altezza, ZonaAltimetrica, TipoComune, GradoUrbanizzazione, ZonaSismica, Regione)
VALUES ('Bergamo', 'Bergamo', 'BG', 'Nord', 120000, 8000, 3000.5, 40.2, 249, 'Collina', 'Città', 'Alta', '2', 'Lombardia');
```

Se vuoi inserire solo alcune colonne (le altre avranno valore `NULL` o il valore di default):

```sql
INSERT INTO Sindaci (Nome, Cognome, Anni, Partito, Sesso, ComuneID)
VALUES ('Luca', 'Verdi', 45, 'Indipendente', 'M', 1);
```

**Curiosità:**  
Se ometti la lista delle colonne, devi fornire un valore per ogni colonna nell’ordine in cui sono state definite nella tabella. È buona pratica specificare sempre le colonne!

### 4.2 UPDATE

Il comando `UPDATE` serve per modificare i dati già presenti in una tabella. È come correggere una figurina che aveva un errore o aggiornare le informazioni.

**Sintassi base:**

```sql
UPDATE NomeTabella SET Colonna1 = NuovoValore1, Colonna2 = NuovoValore2 WHERE condizione;
```

**Esempio:**  
Supponiamo che il numero di residenti di Bergamo sia aumentato:

```sql
UPDATE Comuni SET Residenti = 121000 WHERE Nome = 'Bergamo' AND Provincia = 'Bergamo';
```

Puoi aggiornare più colonne insieme:

```sql
UPDATE Sindaci SET Anni = 46, Partito = 'Nuovo Partito' WHERE ID = 1;
```

**Attenzione!**  
Se ometti la clausola `WHERE`, tutte le righe della tabella verranno aggiornate!  
Ad esempio, questo comando cambierebbe il partito di tutti i sindaci:

```sql
UPDATE Sindaci SET Partito = 'Indipendente';
```

### 4.3 DELETE

Il comando `DELETE` serve per eliminare una o più righe da una tabella. È come togliere una figurina dalla collezione.  
Usalo con attenzione: una volta cancellato un dato, non si può recuperare (a meno di usare le transazioni).

**Sintassi base:**

```sql
DELETE FROM NomeTabella WHERE condizione;
```

**Esempio:**  
Eliminiamo il sindaco con nome "Luca Verdi":

```sql
DELETE FROM Sindaci WHERE Nome = 'Luca' AND Cognome = 'Verdi';
```

Se vuoi eliminare tutti i sindaci di un certo comune:

```sql
DELETE FROM Sindaci WHERE ComuneID = 1;
```

**Attenzione!**  
Come per `UPDATE`, se non metti la clausola `WHERE`, eliminerai tutte le righe della tabella:

```sql
DELETE FROM Comuni; -- Elimina tutti i comuni!
```

**Curiosità:**  
In SQLite, puoi annullare una cancellazione solo se usi le transazioni (`BEGIN`, `ROLLBACK`). È come avere una "rete di sicurezza" quando fai modifiche importanti!

---

## 5. La SELECT: interrogare i dati

La SELECT è il comando più usato in SQL: serve a "fare domande" al database e ottenere risposte. Immagina di essere un investigatore 🕵️‍♂️ che cerca informazioni tra milioni di dati!

### 5.1 Sintassi base di SELECT

La forma più semplice è:

```sql
SELECT * FROM Comuni;
```

Questo comando mostra tutte le colonne e tutte le righe della tabella Comuni.

### 5.2 Selezione di colonne specifiche

Se vuoi vedere solo alcune colonne, basta elencarle:

```sql
SELECT Nome, Provincia FROM Comuni;
```

### 5.3 DISTINCT

`DISTINCT` serve a eliminare i duplicati, come se volessi vedere solo una volta ogni provincia presente nei comuni.

```sql
SELECT DISTINCT Provincia FROM Comuni;
```

### 5.4 Filtri con WHERE

`WHERE` è il filtro: ti permette di selezionare solo le righe che ti interessano, come cercare tutti i comuni di una certa regione.

```sql
SELECT Nome FROM Comuni WHERE Regione = 'Lazio';
```

### 5.5 Ordinamento con ORDER BY

`ORDER BY` ordina i risultati, ad esempio per vedere i comuni più popolosi in cima:

```sql
SELECT Nome, Residenti FROM Comuni ORDER BY Residenti DESC;
```

### 5.6 Limiti e offset (LIMIT, OFFSET)

`LIMIT` limita il numero di risultati, `OFFSET` salta le prime righe. Utile per "paginare" i dati, come nei risultati di Google!

```sql
SELECT Nome FROM Comuni LIMIT 10 OFFSET 20;
```

### 5.7 Operatori logici e di confronto

Puoi combinare più condizioni con AND, OR, NOT, e usare operatori come =, <, >, <=, >=, !=

```sql
SELECT Nome FROM Comuni WHERE Residenti > 100000 AND Regione = 'Lombardia';
```

### 5.8 LIKE e pattern matching

`LIKE` permette di cercare "simile a", usando i caratteri jolly `%` (qualsiasi sequenza) e `_` (un solo carattere).

```sql
SELECT Nome FROM Comuni WHERE Nome LIKE 'San %';
```

Trova tutti i comuni che iniziano con "San ".

### 5.9 Funzioni di aggregazione (COUNT, SUM, AVG, MIN, MAX)

Le funzioni di aggregazione permettono di fare calcoli sui dati, come contare i comuni, sommare i residenti, trovare il massimo, ecc.

```sql
SELECT COUNT(*) FROM Comuni;
SELECT SUM(Residenti) FROM Comuni WHERE Regione = 'Sicilia';
SELECT AVG(Residenti) FROM Comuni;
SELECT MIN(Altezza), MAX(Altezza) FROM Comuni;
```

### 5.10 Raggruppamento con GROUP BY e HAVING

`GROUP BY` raggruppa i dati per una colonna, `HAVING` filtra i gruppi.

```sql
SELECT Provincia, COUNT(*) FROM Comuni GROUP BY Provincia;
SELECT Provincia, COUNT(*) FROM Comuni GROUP BY Provincia HAVING COUNT(*) > 50;
```

### 5.11 JOIN tra tabelle (INNER JOIN, LEFT JOIN, ecc.)

Le JOIN permettono di collegare più tabelle, come unire i dati dei Sindaci con quelli dei Comuni.

```sql
SELECT Sindaci.Nome, Sindaci.Cognome, Comuni.Nome AS Comune
FROM Sindaci
INNER JOIN Comuni ON Sindaci.ComuneID = Comuni.ID;
```

**Curiosità:**
Le JOIN sono come i superpoteri di SQL: ti permettono di vedere dati collegati che da soli non avresti mai potuto incrociare!

### 5.12 SELECT nidificate (subquery)

Una subquery è una SELECT dentro un’altra SELECT, come una "domanda nella domanda".

```sql
SELECT Nome FROM Comuni WHERE Residenti = (SELECT MAX(Residenti) FROM Comuni);
```

Questa query trova il comune più popoloso.

## 6. Gestione degli utenti e dei permessi (DCL)

In molti database, puoi decidere chi può vedere o modificare i dati, proprio come in una chat puoi scegliere chi può leggere i tuoi messaggi. In SQL si usano i comandi `GRANT` (concedi) e `REVOKE` (revoca).

**Esempio:**

```sql
GRANT SELECT ON Comuni TO utente1;
REVOKE UPDATE ON Sindaci FROM utente2;
```

**Nota:**
SQLite non gestisce utenti e permessi avanzati: tutti possono fare tutto! Ma è importante conoscere questi comandi per altri database come MySQL o PostgreSQL.

---

## 7. Transazioni e integrità dei dati (TCL)

Le transazioni sono come una partita a Monopoli 🎲: o tutte le mosse vanno a buon fine, o si torna indietro! Servono a garantire che i dati restino sempre corretti, anche in caso di errori o interruzioni.

### 7.1 BEGIN, COMMIT, ROLLBACK

- `BEGIN` inizia una transazione
- `COMMIT` conferma tutte le modifiche
- `ROLLBACK` annulla tutto e riporta la situazione a prima

**Esempio:**

```sql
BEGIN;
UPDATE Comuni SET Residenti = Residenti - 1000 WHERE Nome = 'Roma';
UPDATE Comuni SET Residenti = Residenti + 1000 WHERE Nome = 'Milano';
COMMIT;
```

Se qualcosa va storto, puoi usare `ROLLBACK;` per annullare tutto.

### 7.2 Integrità referenziale

L’integrità referenziale garantisce che i collegamenti tra tabelle siano sempre validi. Ad esempio, non puoi avere un sindaco che fa riferimento a un comune che non esiste!

SQLite supporta le chiavi esterne, ma vanno attivate con:

```sql
PRAGMA foreign_keys = ON;
```

---

## 8. Strumenti e curiosità su SQLite

### 8.1 Interfacce grafiche e strumenti di gestione

Per lavorare con SQLite puoi usare programmi con interfaccia grafica (GUI) come **DB Browser for SQLite** o **DBeaver**. Sono come il telecomando della TV: rendono tutto più semplice e intuitivo!

### 8.2 Utilizzo di SQLite in applicazioni reali (browser, app, ecc.)

SQLite è usato in tantissime app famose: browser come Chrome e Firefox, WhatsApp, Telegram, videogiochi e persino in alcune automobili 🚗!

### 8.3 Backup e esportazione dati

Fare il backup di un database è come salvare la partita di un videogioco: se succede qualcosa, puoi ripartire da dove eri rimasto!

Con SQLite basta copiare il file del database, oppure esportare i dati in formato CSV:

```sql
.mode csv
.output comuni.csv
SELECT * FROM Comuni;
.output stdout
```

---

## 9. Esercizi e casi pratici

- E9.1 Crea la tabella Comuni e inserisci almeno 3 comuni italiani con dati realistici.
- E9.2 Inserisci almeno 2 sindaci collegati ai comuni creati.
- E9.3 Scrivi una query per trovare tutti i comuni con più di 100.000 residenti.
- E9.4 Trova il nome e la provincia di tutti i comuni che iniziano per "San".
- E9.5 Conta quanti comuni ci sono in ogni regione.
- E9.6 Trova il sindaco più giovane e il più anziano.
- E9.7 Elenca tutti i sindaci e il nome del loro comune usando una JOIN.
- E9.8 Simula una modifica di massa: aumenta del 10% i residenti di tutti i comuni della regione "Lombardia".
- E9.9 Elimina un sindaco e verifica che non restino riferimenti "orfani".
- E9.10 Esporta la tabella Comuni in formato CSV.
