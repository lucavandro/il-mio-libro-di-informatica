# Lezione 1: Introduzione ai Sistemi Informativi e alle Basi di Dati

## Obiettivi della lezione
Al termine di questa lezione sarai in grado di:
- Comprendere cosa sono i sistemi informativi e informatici
- Distinguere le differenze tra sistema informativo e sistema informatico
- Capire l'importanza dell'organizzazione delle informazioni in un'azienda

## 1.1 Cos'è un Sistema Informativo?
Immagina di essere il proprietario di un negozio di scarpe. Ogni giorno hai bisogno di sapere quante scarpe hai venduto, quali modelli stanno per finire, quanto hai guadagnato e quali sono i modelli più richiesti dai clienti. Tutte queste informazioni, insieme alle persone che le gestiscono e agli strumenti utilizzati per elaborarle, formano quello che chiamiamo **sistema informativo**.

Un sistema informativo è quindi l'insieme di:
- Informazioni utilizzate per svolgere le attività
- Persone che gestiscono queste informazioni
- Strumenti e procedure per elaborare le informazioni
- Modalità di organizzazione delle informazioni

## 1.2 Dal Sistema Informativo al Sistema Informatico
Torniamo al nostro negozio di scarpe. All'inizio, forse gestivi tutto su carta: avevi un quaderno per segnare le vendite, uno per il magazzino, e così via. Questo è un sistema informativo "tradizionale". 

Quando decidi di utilizzare un computer per gestire queste informazioni, stai passando a un **sistema informatico**. Il sistema informatico è quindi la parte del sistema informativo che viene gestita attraverso strumenti informatici (computer, tablet, smartphone, ecc.).

## 1.3 Differenze Principali

Per capire meglio la differenza, facciamo un esempio pratico:

**Sistema Informativo di una Biblioteca:**
- Catalogo dei libri (su carta o computer)
- Bibliotecari
- Procedure di prestito
- Schede dei lettori
- Regole per i prestiti

**Sistema Informatico della stessa Biblioteca:**
- Software per gestire i prestiti
- Database dei libri
- Computer per la ricerca
- Lettori di codici a barre
- Tessere elettroniche

Come vedi, il sistema informatico è una parte del sistema informativo, quella che utilizza strumenti tecnologici.

## 1.4 Vantaggi dell'Automazione
Trasformare un sistema informativo tradizionale in un sistema informatico porta numerosi vantaggi:

1. **Velocità**: trovare un libro in un database è molto più veloce che cercarlo in un catalogo cartaceo

2. **Precisione**: il computer non si stanca e non fa errori di distrazione

3. **Accesso multiplo**: più persone possono consultare le stesse informazioni contemporaneamente

4. **Sicurezza**: è più facile fare copie di backup dei dati e proteggerli

5. **Analisi dei dati**: il computer può facilmente elaborare i dati per fornire statistiche e report

## 1.5 Un Esempio Reale
Pensiamo a una scuola:

**Sistema Informativo della Scuola** include:
- Tutti i dati degli studenti
- I voti e le pagelle
- I registri degli insegnanti
- Le circolari
- Il personale che gestisce questi dati
- Le procedure per gestire assenze, voti, ecc.

**Sistema Informatico della Scuola** è composto da:
- Registro elettronico
- Software per la segreteria
- Database degli studenti
- Sito web della scuola
- Computer e rete internet

## Verifica le tue Conoscenze
1. Qual è la principale differenza tra sistema informativo e sistema informatico?
2. Perché un'azienda dovrebbe passare da un sistema informativo tradizionale a uno informatico?
3. Nel sistema informativo di un ospedale, fai alcuni esempi di elementi che non fanno parte del sistema informatico.

## Riepilogo
In questa lezione abbiamo imparato che:
- Il sistema informativo comprende tutte le informazioni e le modalità con cui vengono gestite in un'organizzazione
- Il sistema informatico è la parte del sistema informativo che utilizza strumenti tecnologici
- L'automazione porta numerosi vantaggi in termini di efficienza e precisione

Nella prossima lezione vedremo come vengono organizzati i dati all'interno di questi sistemi e perché è importante strutturarli in modo efficiente.

# Lezione 2: Organizzazione dei Dati

## 2.1 Gli Archivi: Cosa Sono e Come Funzionano
Immagina di dover gestire una videoteca. Hai bisogno di tenere traccia di:
- I film disponibili
- I clienti registrati
- I prestiti in corso

In un sistema tradizionale, potresti creare tre archivi separati:
1. **Archivio Film**: con titolo, regista, anno, genere
2. **Archivio Clienti**: con nome, indirizzo, telefono
3. **Archivio Prestiti**: con data prestito, film prestato, cliente

Un archivio è quindi una raccolta organizzata di dati dello stesso tipo. È come un cassetto dove metti tutte le cose simili insieme.

## 2.2 I Problemi degli Archivi Tradizionali

### 2.2.1 La Ridondanza dei Dati
Immagina che un cliente prenda in prestito un film. Nell'archivio prestiti dovrai scrivere:
- Nome e cognome del cliente (che hai già nell'archivio clienti)
- Titolo del film (che hai già nell'archivio film)

Questa duplicazione delle informazioni si chiama **ridondanza** e crea diversi problemi:
- Occupa più spazio del necessario
- Richiede più tempo per l'inserimento
- Può portare a inconsistenze

### 2.2.2 L'Inconsistenza dei Dati
Facciamo un esempio: 
Mario Rossi cambia numero di telefono. Se il suo numero è salvato in più posti, potrebbe succedere che:
- Lo aggiorniamo nell'archivio clienti
- Ci dimentichiamo di aggiornarlo nell'archivio prestiti
- Ora abbiamo due numeri diversi per la stessa persona!

Questa situazione si chiama **inconsistenza dei dati** ed è un grosso problema.

## 2.3 Altri Limiti degli Archivi

### 2.3.1 Difficoltà di Ricerca
Se vuoi sapere "quali film horror degli anni '90 sono attualmente in prestito?", dovresti:
1. Cercare nell'archivio film tutti i film horror degli anni '90
2. Per ognuno, cercare nell'archivio prestiti se è in prestito
3. Fare tutto manualmente!

### 2.3.2 Difficoltà di Condivisione
Se due persone devono lavorare contemporaneamente sugli stessi dati:
- Persona A sta aggiornando l'archivio clienti
- Persona B sta registrando un nuovo prestito
- Come fanno a coordinarsi?

## 2.4 Dalle Basi di Dati
Per risolvere questi problemi sono nate le basi di dati. Una base di dati è un sistema che:
- Mantiene i dati collegati tra loro
- Elimina le ridondanze inutili
- Garantisce la coerenza delle informazioni
- Permette ricerche veloci e complesse
- Gestisce gli accessi multipli

### 2.4.1 Esempio Pratico
Nella nostra videoteca con una base di dati:
- Il cliente viene registrato una sola volta
- Ogni film viene registrato una sola volta
- I prestiti collegano clienti e film senza duplicare le informazioni
- Le ricerche sono immediate
- Più persone possono usare il sistema contemporaneamente

## 2.5 Vantaggi delle Basi di Dati
1. **Dati non ridondanti**: ogni informazione viene memorizzata una sola volta

2. **Dati consistenti**: l'aggiornamento di un dato si riflette automaticamente ovunque

3. **Ricerche efficienti**: possiamo fare ricerche complesse in modo veloce

4. **Accesso condiviso**: più utenti possono usare i dati contemporaneamente

5. **Sicurezza**: possiamo decidere chi può vedere o modificare quali dati

## Verifica le tue Conoscenze
1. Cosa si intende per ridondanza dei dati? Fai un esempio.
2. Perché l'inconsistenza dei dati è un problema serio?
3. Quali sono i principali vantaggi di una base di dati rispetto agli archivi tradizionali?

## Esercizio Pratico
Pensa al registro elettronico della tua scuola. Identifica:
- Quali potrebbero essere gli archivi necessari
- Quali dati rischierebbero di essere ridondanti
- Come una base di dati risolve questi problemi

## Riepilogo
In questa lezione abbiamo visto:
- Come funzionano gli archivi tradizionali
- I problemi di ridondanza e inconsistenza
- Perché le basi di dati sono una soluzione migliore

Nella prossima lezione inizieremo a vedere come si progetta una base di dati utilizzando il modello Entità-Relazione.

# Lezione 3: Il Modello Entità-Relazione (Parte 1)

## Obiettivi della lezione
Al termine di questa lezione sarai in grado di:
- Comprendere cosa sono le entità e gli attributi
- Distinguere i diversi tipi di attributi
- Capire il concetto di chiave
- Iniziare a progettare un semplice schema E-R

## 3.1 Il Modello E-R: Un Modo per Progettare
Prima di costruire una casa, l'architetto fa un progetto. Lo stesso vale per le basi di dati: prima di crearle, dobbiamo progettarle. Il Modello Entità-Relazione (E-R) è come il progetto della nostra base di dati.

### 3.1.1 Perché usare il Modello E-R?
- È facile da capire
- Usa simboli grafici chiari
- Aiuta a organizzare le idee
- Permette di vedere subito gli errori

## 3.2 Le Entità: I "Protagonisti" della Base di Dati

### 3.2.1 Cosa sono le Entità?
Un'entità è qualcosa di cui vogliamo memorizzare informazioni. Per esempio, in una scuola le entità potrebbero essere:
- STUDENTE
- PROFESSORE
- CLASSE
- MATERIA

Le entità si rappresentano con un rettangolo:

```
┌──────────┐
│ STUDENTE │
└──────────┘
```

### 3.2.2 Come Riconoscere un'Entità?
Un'entità di solito:
- È un nome singolare
- Rappresenta molti oggetti dello stesso tipo
- Ha caratteristiche che vogliamo ricordare

## 3.3 Gli Attributi: Le Caratteristiche delle Entità

### 3.3.1 Cos'è un Attributo?
Gli attributi sono le informazioni che vogliamo memorizzare su un'entità. Per esempio, per l'entità STUDENTE potremmo avere:
- Nome
- Cognome
- Data di nascita
- Indirizzo
- Telefono

Gli attributi si rappresentano con ovali collegati all'entità:

```
┌──────────┐
│ STUDENTE │
└────┬─────┘
     │
 ┌───┴───┐
 │ Nome  │
 └───────┘
```

### 3.3.2 Tipi di Attributi

1. **Attributi Semplici**
   - Contengono un solo valore
   - Esempio: età, nome

2. **Attributi Composti**
   - Sono formati da più parti
   - Esempio: indirizzo (via, numero, città, CAP)
   ```
   ┌─────────┐
   │Indirizzo│
   └────┬────┘
    ┌───┴───┐
    │  Via  │ Numero │ Città │
    └───────┘
   ```

3. **Attributi Multipli**
   - Possono avere più valori
   - Esempio: telefono (uno studente può avere più numeri)
   - Si rappresentano con un ovale doppio

## 3.4 Le Chiavi: Come Identificare le Entità

### 3.4.1 Perché servono le Chiavi?
Immagina di avere due studenti che si chiamano Mario Rossi. Come facciamo a distinguerli? Abbiamo bisogno di un attributo (o un gruppo di attributi) che identifichi in modo univoco ogni studente.

### 3.4.2 Caratteristiche di una Chiave
Una chiave deve essere:
- Univoca: non ci possono essere due entità con lo stesso valore
- Non nulla: deve sempre avere un valore
- Stabile: non deve cambiare nel tempo

### 3.4.3 Esempi di Chiavi
- Per STUDENTE: numero di matricola
- Per PROFESSORE: codice fiscale
- Per CLASSE: sezione e anno
- Per MATERIA: codice materia

Le chiavi si sottolineano nello schema:

```
┌──────────┐
│ STUDENTE │
└────┬─────┘
     │
┌────┴─────┐
│Matricola │ (sottolineato)
└──────────┘
```

## 3.5 Esempio Pratico: La Biblioteca
Progettiamo una parte del database di una biblioteca:

Entità LIBRO con attributi:
- ISBN (chiave)
- Titolo
- Anno di pubblicazione
- Editore

Entità AUTORE con attributi:
- Codice Autore (chiave)
- Nome
- Cognome
- Nazionalità

## Verifica le tue Conoscenze
1. Quali sono le caratteristiche che deve avere un'entità?
2. Fai un esempio di attributo composto diverso da indirizzo.
3. Perché è importante scegliere bene la chiave di un'entità?

## Esercizio Pratico
Progetta lo schema E-R per una squadra di calcio, identificando:
1. Le entità principali
2. Gli attributi di ogni entità
3. Le chiavi appropriate

## Riepilogo
In questa lezione abbiamo imparato:
- Cosa sono le entità e come si rappresentano
- I diversi tipi di attributi
- L'importanza delle chiavi
- Come iniziare a progettare uno schema E-R

Nella prossima lezione vedremo come collegare tra loro le entità usando le relazioni.

# Lezione 4: Il Modello Entità-Relazione (Parte 2)

## Obiettivi della lezione
Al termine di questa lezione sarai in grado di:
- Comprendere cosa sono le associazioni tra entità
- Capire il concetto di cardinalità
- Riconoscere e usare le associazioni ricorsive
- Distinguere entità forti e deboli
- Comprendere generalizzazioni e specializzazioni

## 4.1 Le Associazioni: Come Collegare le Entità

### 4.1.1 Cosa sono le Associazioni?
Immagina di avere le entità STUDENTE e CLASSE. Gli studenti frequentano le classi: questo "frequenta" è un'associazione! Le associazioni (o relazioni) rappresentano i legami tra le entità.

Le associazioni si rappresentano con un rombo:

```
┌──────────┐      ┌──────────┐      ┌────────┐
│ STUDENTE │──────│frequenta │──────│ CLASSE │
└──────────┘      └──────────┘      └────────┘
```

### 4.1.2 Esempi di Associazioni
- STUDENTE frequenta CLASSE
- PROFESSORE insegna MATERIA
- LIBRO scritto_da AUTORE
- CLIENTE prenota LIBRO

## 4.2 Le Cardinalità: Quanti Collegamenti?

### 4.2.1 Cosa sono le Cardinalità?
Le cardinalità ci dicono quante volte un'entità può partecipare a un'associazione. Si indicano con numeri o simboli vicino alle linee:
- 1: esattamente uno
- N (o *): molti
- 0,1: zero o uno
- 1,N: almeno uno

### 4.2.2 Esempi Pratici

1. **Uno a Uno (1:1)**
```
┌──────────┐    (1,1)    ┌──────┐    (1,1)    ┌─────────┐
│ STUDENTE │────────────│guida │────────────│ PROGETTO │
└──────────┘            └──────┘            └─────────┘
```
Ogni studente guida un solo progetto e ogni progetto è guidato da un solo studente.

2. **Uno a Molti (1:N)**
```
┌──────────┐    (1,1)    ┌──────────┐    (1,N)    ┌────────┐
│ CLASSE   │────────────│appartiene │────────────│STUDENTE │
└──────────┘            └──────────┘            └────────┘
```
Ogni classe ha molti studenti, ogni studente appartiene a una sola classe.

3. **Molti a Molti (N:N)**
```
┌──────────┐    (0,N)    ┌─────────┐    (0,N)    ┌────────┐
│PROFESSORE│────────────│ insegna │────────────│ MATERIA │
└──────────┘            └─────────┘            └────────┘
```
Un professore può insegnare più materie e una materia può essere insegnata da più professori.

## 4.3 Associazioni Ricorsive
A volte un'entità può essere in relazione con se stessa. Per esempio:
- Un DIPENDENTE supervisiona altri DIPENDENTI
- Un CORSO è propedeutico a un altro CORSO

```
┌──────────┐
│DIPENDENTE│
└────┬─────┘
     │(0,1)
┌────┴─────┐
│supervisiona
└────┬─────┘
     │(0,N)
┌────┴─────┐
│DIPENDENTE│
└──────────┘
```

## 4.4 Entità Deboli
Un'entità debole è un'entità che non può esistere da sola, ma dipende da un'altra entità (detta forte).

Esempio: ESAME dipende da STUDENTE
- Non può esistere un esame senza uno studente
- La chiave dell'esame include la chiave dello studente

```
┌──────────┐    (1,1)    ┌──────┐    (0,N)    ╔════════╗
│ STUDENTE │────────────│sostiene│────────────║ ESAME  ║
└──────────┘            └──────┘            ╚════════╝
```
(L'entità debole si rappresenta con un doppio rettangolo)

## 4.5 Generalizzazioni e Specializzazioni
A volte abbiamo entità che sono casi particolari di altre entità.

Esempio: PERSONA può essere specializzata in STUDENTE e PROFESSORE
```
        ┌──────────┐
        │ PERSONA  │
        └─────┬────┘
              │
      ┌───────┴───────┐
      │               │
┌──────────┐   ┌──────────┐
│ STUDENTE │   │PROFESSORE│
└──────────┘   └──────────┘
```

## Verifica le tue Conoscenze
1. Qual è la differenza tra una relazione 1:N e una N:N?
2. Fai un esempio di associazione ricorsiva diversa da quelle viste.
3. Perché alcune entità sono considerate "deboli"?

## Esercizio Pratico
Progetta lo schema E-R di un cinema considerando:
- Film in programmazione
- Sale cinematografiche
- Spettacoli
- Prenotazioni
- Clienti

Identifica:
- Le cardinalità appropriate
- Eventuali entità deboli
- Possibili generalizzazioni

## Riepilogo
In questa lezione abbiamo imparato:
- Come collegare le entità usando le associazioni
- I diversi tipi di cardinalità
- Cosa sono le associazioni ricorsive
- La differenza tra entità forti e deboli
- Come usare generalizzazioni e specializzazioni


# Lezione 5: Vincoli di Integrità

## Introduzione
Immagina di essere il gestore di una biblioteca e di dover registrare i dati dei tuoi utenti. Maria, una nuova iscritta, ti comunica di avere -5 anni. Ovviamente c'è qualcosa che non va! Oppure Paolo vuole prendere in prestito un libro con codice 12345, ma questo libro non esiste nel tuo catalogo. Come facciamo a evitare questi errori? È qui che entrano in gioco i vincoli di integrità.

## Cosa sono i Vincoli di Integrità?
I vincoli di integrità sono come le regole di un gioco: ci dicono cosa possiamo e cosa non possiamo fare con i nostri dati. Sono dei "guardiani" che proteggono la nostra base di dati da informazioni sbagliate o incoerenti. È come quando riempiamo un modulo online: se proviamo a inserire un indirizzo email senza la @, il sistema ci avvisa che c'è un errore.

## I Vincoli di Dominio: Le Regole Base
Pensiamo a una scuola. Quando registriamo i voti degli studenti, sappiamo che:
- Un voto non può essere negativo
- Non può essere superiore a 10
- Non può essere decimale (non esiste 7.5!)

Questi sono esempi di vincoli di dominio: regole che ci dicono quali valori sono accettabili per una certa informazione. È come avere un controllore che verifica ogni dato prima di lasciarlo entrare nel nostro database.

Altri esempi di vita quotidiana:
- L'età di una persona deve essere un numero tra 0 e 120
- Un numero di telefono deve avere un certo numero di cifre
- Una data di nascita non può essere nel futuro

## Le Chiavi Primarie: L'Unicità è Importante
Immagina di avere due studenti che si chiamano Mario Rossi nella stessa classe. Come facciamo a distinguerli? Ecco che entra in gioco la chiave primaria. È come il codice fiscale per le persone: un codice unico che identifica in modo inequivocabile ogni record nel nostro database.

Una buona chiave primaria è come una buona carta d'identità:
- Non può essere duplicata (non possono esistere due persone con lo stesso codice)
- Non può essere vuota (tutti devono avere un codice)
- Non dovrebbe cambiare nel tempo (sarebbe un bel problema se il nostro codice fiscale cambiasse ogni anno!)

## Le Chiavi Esterne: Creare Collegamenti
Torniamo alla nostra biblioteca. Quando registriamo un prestito, dobbiamo collegarlo sia al libro che all'utente. La chiave esterna è proprio questo collegamento. È come quando in un documento mettiamo un riferimento a un altro documento.

Per esempio, quando registriamo un prestito, abbiamo:
- Il codice del prestito (chiave primaria)
- Il codice del libro (chiave esterna che si collega alla tabella dei libri)
- Il codice dell'utente (chiave esterna che si collega alla tabella degli utenti)

## L'Integrità Referenziale: Manteniamo l'Ordine
L'integrità referenziale è come un sistema di sicurezza che garantisce che tutti i collegamenti siano validi. Prendiamo alcuni esempi pratici:

1. Non possiamo registrare un prestito per un libro che non esiste
   È come cercare di spedire una lettera a un indirizzo inesistente

2. Non possiamo cancellare un libro se qualcuno lo ha in prestito
   È come cercare di demolire un palazzo mentre ci sono ancora persone dentro

3. Se cambiamo il codice di un libro, dobbiamo aggiornare tutti i prestiti collegati
   È come quando cambiamo indirizzo e dobbiamo comunicarlo a tutti i nostri contatti

## Un Esempio Completo: La Gestione di una Scuola
Pensiamo a come gestire i voti degli studenti:

- Ogni STUDENTE ha:
  * Un numero di matricola (chiave primaria, non può essere duplicato)
  * Nome e cognome (non possono essere vuoti)
  * Data di nascita (deve essere una data valida nel passato)

- Ogni VOTO ha:
  * La matricola dello studente (deve esistere nella tabella studenti)
  * La materia (deve essere una materia valida)
  * Il valore (deve essere tra 1 e 10)
  * La data (non può essere nel futuro)

Questi vincoli ci garantiscono che:
- Non possiamo inserire voti per studenti inesistenti
- Non possiamo inserire voti impossibili
- Tutte le informazioni sono logicamente coerenti

## Conclusione
I vincoli di integrità sono fondamentali per mantenere i nostri dati puliti e affidabili. Sono come le regole della grammatica: senza di esse, il nostro "discorso" (i dati) diventerebbe incomprensibile e inaffidabile. Nella prossima lezione vedremo come mettere in pratica tutti questi concetti creando una vera base di dati.

Ricorda: un database senza vincoli è come una città senza regole - prima o poi, qualcosa andrà storto!
