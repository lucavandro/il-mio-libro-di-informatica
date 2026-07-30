# SQL e SQLite

## 1. Creare tabelle

```sql
PRAGMA foreign_keys = ON;

CREATE TABLE studenti (
    id_studente INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    classe TEXT NOT NULL
);

CREATE TABLE libri (
    id_libro INTEGER PRIMARY KEY,
    titolo TEXT NOT NULL,
    autore TEXT NOT NULL
);

CREATE TABLE prestiti (
    id_prestito INTEGER PRIMARY KEY,
    id_studente INTEGER NOT NULL,
    id_libro INTEGER NOT NULL,
    data_inizio TEXT NOT NULL,
    data_restituzione TEXT,
    FOREIGN KEY (id_studente) REFERENCES studenti(id_studente),
    FOREIGN KEY (id_libro) REFERENCES libri(id_libro)
);
```

SQLite usa un sistema di tipi flessibile. Le date vengono spesso conservate in formato ISO `AAAA-MM-GG`.

## 2. Inserire dati

```sql
INSERT INTO studenti (nome, classe)
VALUES ('Ada', '4A');
```

In un programma i valori forniti dall'utente devono essere passati mediante parametri, non concatenati nella query.

## 3. Interrogare

```sql
SELECT nome, classe
FROM studenti
ORDER BY nome;
```

Filtrare:

```sql
SELECT titolo, autore
FROM libri
WHERE autore = 'Primo Levi';
```

## 4. Aggiornare ed eliminare

```sql
UPDATE studenti
SET classe = '5A'
WHERE id_studente = 1;
```

```sql
DELETE FROM prestiti
WHERE id_prestito = 10;
```

Senza `WHERE`, `UPDATE` o `DELETE` può coinvolgere tutte le righe. Prima si prova la stessa condizione con `SELECT`.

## 5. Funzioni di aggregazione

```sql
SELECT classe, COUNT(*) AS numero_studenti
FROM studenti
GROUP BY classe
ORDER BY classe;
```

Funzioni utili: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`.

## 6. Join

```sql
SELECT
    studenti.nome,
    libri.titolo,
    prestiti.data_inizio
FROM prestiti
JOIN studenti
    ON studenti.id_studente = prestiti.id_studente
JOIN libri
    ON libri.id_libro = prestiti.id_libro
WHERE prestiti.data_restituzione IS NULL;
```

Una join ricostruisce informazioni distribuite in più tabelle.

## 7. Algebra relazionale intuitiva

- **selezione**: sceglie righe;
- **proiezione**: sceglie colonne;
- **congiunzione**: collega relazioni.

Questi concetti corrispondono rispettivamente a `WHERE`, elenco delle colonne e `JOIN`.

## 8. Transazioni

```sql
BEGIN;

UPDATE prodotti
SET quantita = quantita - 1
WHERE id_prodotto = 5;

INSERT INTO movimenti (id_prodotto, quantita)
VALUES (5, -1);

COMMIT;
```

Una transazione raggruppa operazioni che devono riuscire insieme. In caso di problema si usa `ROLLBACK`.

## 9. Laboratorio

1. Crea il database progettato.
2. Inserisci almeno venti righe.
3. Scrivi query con filtri e ordinamento.
4. Usa almeno una funzione di aggregazione.
5. Costruisci due join.
6. Verifica i vincoli con dati volutamente errati.
