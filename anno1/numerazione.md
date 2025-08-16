# I sistemi di numerazione

## Introduzione

Benvenuti nel mondo affascinante dei sistemi di numerazione! In informatica, i numeri non sono solo numeri: sono il linguaggio fondamentale con cui computer e dispositivi digitali comunicano tra loro. Mentre noi umani usiamo naturalmente il sistema decimale (base 10), i computer "pensano" in binario (base 2). Comprendere questi sistemi numerici è essenziale per capire come funzionano davvero le tecnologie che usiamo ogni giorno.

In questo corso di 4 ore esploreremo i principali sistemi di numerazione utilizzati in informatica, impareremo a convertire numeri tra diverse basi e scopriremo strumenti pratici per effettuare questi calcoli. Alla fine, vedrete i numeri con occhi completamente nuovi!

---

## 1. Il sistema decimale: il nostro punto di partenza

### 1.1 Come funziona il sistema decimale

Il sistema decimale è così naturale per noi che raramente ci fermiamo a pensare al suo funzionamento. Utilizziamo 10 cifre (0, 1, 2, 3, 4, 5, 6, 7, 8, 9) e ogni posizione in un numero rappresenta una potenza di 10.

Prendiamo il numero 3429:

- 3 × 10³ = 3 × 1000 = 3000
- 4 × 10² = 4 × 100 = 400  
- 2 × 10¹ = 2 × 10 = 20
- 9 × 10⁰ = 9 × 1 = 9
- **Totale: 3000 + 400 + 20 + 9 = 3429**

### 1.2 Il concetto di base numerica

Una **base numerica** determina quante cifre diverse possiamo usare e il valore di ogni posizione. Nel sistema decimale:

- **Base**: 10
- **Cifre disponibili**: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
- **Valore delle posizioni**: ...10³, 10², 10¹, 10⁰

Questo principio si applica a qualsiasi base numerica, cambiando solo il numero di cifre disponibili e il valore delle posizioni.

### 1.3 Perché altri sistemi di numerazione?

Potreste chiedervi: "Se il decimale funziona così bene, perché usare altri sistemi?" La risposta sta nella natura dell'elettronica digitale. I computer utilizzano componenti elettronici che possono essere in due stati: acceso (1) o spento (0). Questo rende il sistema binario perfetto per rappresentare informazioni digitali.

---

## 2. Il sistema binario: il linguaggio dei computer

### 2.1 Introduzione al sistema binario

Il sistema binario è il fondamento di tutta l'informatica moderna. Utilizza solo due cifre (0 e 1) e ogni posizione rappresenta una potenza di 2.

**Caratteristiche del sistema binario:**

- **Base**: 2
- **Cifre disponibili**: 0, 1
- **Valore delle posizioni**: ...2³, 2², 2¹, 2⁰

### 2.2 Come leggere i numeri binari

Prendiamo il numero binario 1101:

- 1 × 2³ = 1 × 8 = 8
- 1 × 2² = 1 × 4 = 4
- 0 × 2¹ = 0 × 2 = 0
- 1 × 2⁰ = 1 × 1 = 1
- **Totale: 8 + 4 + 0 + 1 = 13 (in decimale)**

### 2.3 Perché il binario è perfetto per i computer

I computer utilizzano circuiti elettronici che riconoscono due stati:

- **0**: Assenza di tensione elettrica (spento)
- **1**: Presenza di tensione elettrica (acceso)

Questa semplicità rende il sistema binario incredibilmente affidabile e veloce per i calcoli elettronici.

### 2.4 Applicazioni pratiche del binario

Il sistema binario non è solo teoria astratta:

- **Memoria del computer**: Ogni bit di memoria può contenere un 0 o un 1
- **Processori**: Eseguono operazioni su numeri binari
- **Reti di comunicazione**: I dati viaggiano come sequenze di 0 e 1
- **Storage digitale**: Hard disk, SSD, USB memorizzano informazioni in binario

---

## 3. Conversioni tra decimale e binario

### 3.1 Da decimale a binario: il metodo delle divisioni successive

Per convertire un numero decimale in binario, utilizziamo il metodo delle divisioni successive per 2:

**Esempio: Convertiamo 25 in binario**

1. 25 ÷ 2 = 12 resto **1**
2. 12 ÷ 2 = 6 resto **0**  
3. 6 ÷ 2 = 3 resto **0**
4. 3 ÷ 2 = 1 resto **1**
5. 1 ÷ 2 = 0 resto **1**

Leggendo i resti dal basso verso l'alto: **11001**

**Verifica**: 1×2⁴ + 1×2³ + 0×2² + 0×2¹ + 1×2⁰ = 16 + 8 + 0 + 0 + 1 = 25 ✓

### 3.2 Da binario a decimale: il metodo delle potenze

Per convertire da binario a decimale, moltiplichiamo ogni cifra per la corrispondente potenza di 2:

**Esempio: Convertiamo 110110 in decimale**

Posizioni da destra a sinistra:

- 0 × 2⁰ = 0 × 1 = 0
- 1 × 2¹ = 1 × 2 = 2
- 1 × 2² = 1 × 4 = 4
- 0 × 2³ = 0 × 8 = 0
- 1 × 2⁴ = 1 × 16 = 16
- 1 × 2⁵ = 1 × 32 = 32

**Totale: 0 + 2 + 4 + 0 + 16 + 32 = 54**

### 3.3 Trucchi e strategie per conversioni rapide

**Potenze di 2 da memorizzare:**

- 2⁰ = 1
- 2¹ = 2  
- 2² = 4
- 2³ = 8
- 2⁴ = 16
- 2⁵ = 32
- 2⁶ = 64
- 2⁷ = 128
- 2⁸ = 256

**Trucco per numeri piccoli**: Per numeri decimali fino a 15, potete usare la tabella delle potenze di 2 per scomposizioni mentali rapide.

### 3.4 Esercizi pratici guidati

**Esercitiamoci insieme:**

1. **Decimale → Binario**:
   - 42 → ?
   - 128 → ?
   - 255 → ?

2. **Binario → Decimale**:
   - 1010 → ?
   - 11111 → ?
   - 10000000 → ?

---

## 4. Il sistema esadecimale: la strada più breve

### 4.1 Introduzione al sistema esadecimale

Il sistema esadecimale (base 16) è particolarmente importante in informatica perché offre un modo compatto per rappresentare numeri binari lunghi.

**Caratteristiche del sistema esadecimale:**

- **Base**: 16
- **Cifre disponibili**: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
- **Valori delle lettere**: A=10, B=11, C=12, D=13, E=14, F=15

### 4.2 Perché l'esadecimale è utile in informatica

L'esadecimale è prezioso perché:

- **4 bit = 1 cifra esadecimale**: Questo rende le conversioni molto semplici
- **Compattezza**: Un byte (8 bit) si rappresenta con sole 2 cifre esadecimali
- **Leggibilità**: Più facile da leggere rispetto a lunghe sequenze di 0 e 1

### 4.3 Conversioni con l'esadecimale

**Da decimale a esadecimale:**
Usiamo divisioni successive per 16.

**Esempio: 255 in esadecimale**

1. 255 ÷ 16 = 15 resto **15** (F)
2. 15 ÷ 16 = 0 resto **15** (F)

Risultato: **FF**

**Da esadecimale a decimale:**
**Esempio: 2A3 in decimale**

- 3 × 16⁰ = 3 × 1 = 3
- A × 16¹ = 10 × 16 = 160  
- 2 × 16² = 2 × 256 = 512

**Totale: 3 + 160 + 512 = 675**

### 4.4 La relazione speciale tra binario e esadecimale

Ogni cifra esadecimale corrisponde esattamente a 4 bit:

| Esadecimale | Binario | Decimale |
|-------------|---------|----------|
| 0           | 0000    | 0        |
| 1           | 0001    | 1        |
| 2           | 0010    | 2        |
| 3           | 0011    | 3        |
| 4           | 0100    | 4        |
| 5           | 0101    | 5        |
| 6           | 0110    | 6        |
| 7           | 0111    | 7        |
| 8           | 1000    | 8        |
| 9           | 1001    | 9        |
| A           | 1010    | 10       |
| B           | 1011    | 11       |
| C           | 1100    | 12       |
| D           | 1101    | 13       |
| E           | 1110    | 14       |
| F           | 1111    | 15       |

**Esempio pratico:**
Il binario 11010110 diventa:

- 1101 = D
- 0110 = 6
- Risultato: **D6** in esadecimale

### 4.5 Applicazioni dell'esadecimale

L'esadecimale è ampiamente utilizzato per:

- **Indirizzi di memoria**: I programmatori usano indirizzi esadecimali
- **Codici colore**: #FF0000 rappresenta il rosso puro
- **Codici errore**: I sistemi operativi mostrano errori in esadecimale
- **Debugging**: Analisi del contenuto della memoria

---

## 5. Il sistema ottale: un cenno storico e pratico

### 5.1 Introduzione al sistema ottale

Il sistema ottale (base 8) ha avuto importanza storica in informatica, specialmente nei primi computer.

**Caratteristiche del sistema ottale:**

- **Base**: 8
- **Cifre disponibili**: 0, 1, 2, 3, 4, 5, 6, 7
- **Valore delle posizioni**: ...8³, 8², 8¹, 8⁰

### 5.2 Perché il sistema ottale è stato importante

Nei primi computer, l'ottale era popolare perché:

- **3 bit = 1 cifra ottale**: Relazione semplice con il binario
- **Compattezza**: Più compatto del binario, più semplice dell'esadecimale
- **Tradizione Unix**: Molti sistemi Unix usano ancora permessi ottali

### 5.3 Conversioni con l'ottale

**Da decimale a ottale:**
Divisioni successive per 8.

**Esempio: 100 in ottale**

1. 100 ÷ 8 = 12 resto **4**
2. 12 ÷ 8 = 1 resto **4**  
3. 1 ÷ 8 = 0 resto **1**

Risultato: **144** (ottale)

**Relazione binario-ottale:**
Ogni cifra ottale = 3 bit binari

| Ottale | Binario |
|--------|---------|
| 0      | 000     |
| 1      | 001     |
| 2      | 010     |
| 3      | 011     |
| 4      | 100     |
| 5      | 101     |
| 6      | 110     |
| 7      | 111     |

### 5.4 Applicazioni moderne dell'ottale

Anche se meno comune oggi, l'ottale si trova ancora in:

- **Permessi file Unix/Linux**: chmod 755, 644, ecc.
- **Programmazione C**: Letterali ottali (es. \033)
- **Reti informatiche**: Alcune configurazioni legacy

---

## 6. Strumenti pratici: Calcolatrice di Windows

### 6.1 Modalità Programmatore della Calcolatrice

La Calcolatrice di Windows include una modalità "Programmatore" perfetta per i cambi di base.

**Per accedere alla modalità Programmatore:**

1. Aprire la Calcolatrice di Windows
2. Menu ≡ → Programmatore
3. Oppure utilizzare la scorciatoia Alt + 3

### 6.2 Interfaccia della modalità Programmatore

L'interfaccia mostra:

- **Pannello principale**: Display del numero
- **Selezione base**: HEX, DEC, OCT, BIN
- **Rappresentazioni multiple**: Vede il numero in tutte le basi simultaneamente
- **Tastiera adattiva**: Solo i tasti validi per la base selezionata sono attivi

### 6.3 Come effettuare conversioni

**Procedura passo-passo:**

1. **Selezionare la base di partenza** (DEC, BIN, OCT, HEX)
2. **Inserire il numero** utilizzando la tastiera
3. **Cliccare sulla base di destinazione** per vedere la conversione
4. **Il risultato appare immediatamente** nel display

**Esempio pratico:**

- Inserire "255" in modalità DEC
- Cliccare BIN per vedere: 11111111
- Cliccare HEX per vedere: FF
- Cliccare OCT per vedere: 377

### 6.4 Funzioni avanzate della calcolatrice

**Operazioni disponibili:**

- **Operazioni bit-wise**: AND, OR, XOR, NOT
- **Shift**: Spostamento di bit a sinistra/destra  
- **Modalità byte**: Visualizzazione su 8, 16, 32, 64 bit
- **Cronologia**: Mantiene traccia dei calcoli precedenti

### 6.5 Trucchi e consigli pratici

**Scorciatoie da tastiera:**

- F8: DEC
- F9: HEX  
- F10: OCT
- F11: BIN

**Suggerimenti per l'uso efficace:**

- Utilizzare Ctrl+C per copiare risultati
- La modalità QWORD mostra fino a 64 bit
- Utile per verificare i calcoli manuali

---

## 7. Fogli di calcolo: Excel e Google Sheets

### 7.1 Funzioni di conversione in Excel

Excel offre funzioni dedicate per conversioni tra basi numeriche:

**Funzioni principali:**

- `DEC2BIN(numero)`: Decimale → Binario
- `DEC2HEX(numero)`: Decimale → Esadecimale  
- `DEC2OCT(numero)`: Decimale → Ottale
- `BIN2DEC(numero)`: Binario → Decimale
- `HEX2DEC(numero)`: Esadecimale → Decimale
- `OCT2DEC(numero)`: Ottale → Decimale

### 7.2 Esempi pratici in Excel

**Conversioni da decimale:**

```
=DEC2BIN(25)     → Risultato: 11001
=DEC2HEX(255)    → Risultato: FF  
=DEC2OCT(100)    → Risultato: 144
```

**Conversioni verso decimale:**

```
=BIN2DEC("1101")  → Risultato: 13
=HEX2DEC("FF")    → Risultato: 255
=OCT2DEC("144")   → Risultato: 100
```

### 7.3 Conversioni incrociate

Per conversioni dirette tra basi non decimali, si combinano le funzioni:

**Binario → Esadecimale:**

```
=DEC2HEX(BIN2DEC("11111111"))  → Risultato: FF
```

**Esadecimale → Binario:**

```
=DEC2BIN(HEX2DEC("A0"))  → Risultato: 10100000
```

### 7.4 Creare tabelle di conversione

**Esempio di tabella automatica:**

| Decimale | Binario        | Esadecimale | Ottale |
|----------|----------------|-------------|--------|
| 0        | =DEC2BIN(A2)   | =DEC2HEX(A2)| =DEC2OCT(A2) |
| 1        | =DEC2BIN(A3)   | =DEC2HEX(A3)| =DEC2OCT(A3) |
| ...      | ...            | ...         | ... |

### 7.5 Google Sheets: stesse funzioni, cloud-based

Google Sheets utilizza le stesse funzioni di Excel:

- Accessibile da qualsiasi dispositivo
- Collaborazione in tempo reale
- Salvataggio automatico
- Perfetto per lavori di gruppo

### 7.6 Applicazioni pratiche nei fogli di calcolo

**Usi educativi:**

- Creare tabelle di verifica per gli esercizi
- Automatizzare controlli di conversioni manuali
- Generare esercizi casuali per la pratica

**Usi professionali:**

- Analisi di dati binari
- Conversioni per programmazione
- Documentazione di calcoli

---

## 9. Esercizi pratici e laboratorio

### 9.1 Esercizi di conversione guidati

**Livello Base:**

1. Convertire i seguenti numeri decimali in binario:
   - 8 → ?
   - 15 → ?
   - 32 → ?

2. Convertire i seguenti numeri binari in decimale:
   - 1010 → ?
   - 1111 → ?
   - 100000 → ?

**Livello Intermedio:**
3. Convertire in esadecimale:

- 255 (decimale) → ?
- 11111111 (binario) → ?

4. Convertire in ottale:
   - 64 (decimale) → ?
   - 1000000 (binario) → ?

### 9.2 Laboratorio con calcolatrice Windows

**Attività guidata:**

1. Aprire la Calcolatrice in modalità Programmatore
2. Inserire il numero 42 in decimale
3. Convertire in binario, esadecimale e ottale
4. Verificare i risultati manualmente
5. Ripetere con numeri diversi

### 9.3 Laboratorio con Excel/Google Sheets

**Creare un convertitore automatico:**

1. Creare una tabella con colonne: Decimale, Binario, Esadecimale, Ottale
2. Inserire numeri da 0 a 20 nella colonna Decimale
3. Utilizzare le funzioni per completare automaticamente le altre colonne
4. Verificare alcuni risultati manualmente

### 9.4 Sfide avanzate

**Per studenti più veloci:**

1. Trovare il pattern nei primi 16 numeri in tutte le basi
2. Calcolare quanti bit servono per rappresentare 1000 in binario
3. Scoprire perché i programmatori confondono Halloween e Natale (31 Oct = 25 Dec)

---


## 📚 Risorse per l'approfondimento

**Siti web interattivi:**

- [RapidTables Number Converter](https://www.rapidtables.com/convert/number/)
- [Khan Academy: Computer Science](https://www.khanacademy.org/computing/computer-science)


**Libri consigliati:**

- "Code: The Hidden Language of Computer Hardware and Software" di Charles Petzold
- "But How Do It Know?" di J. Clark Scott

---

## 🤔 Domande frequenti

**Q: Perché devo imparare questi sistemi se ci sono calcolatrici?**
A: Comprendere i sistemi numerici vi aiuta a capire come pensano i computer e vi prepara per corsi avanzati di informatica.

**Q: Qual è il sistema più importante da imparare?**
A: Il binario è fondamentale, ma l'esadecimale è molto pratico. Entrambi sono essenziali.

**Q: Questi sistemi si usano davvero nel lavoro?**
A: Assolutamente sì! Programmatori, amministratori di rete, e tecnici li usano quotidianamente.

**Q: È normale trovare difficili le conversioni all'inizio?**
A: Sì, è completamente normale. Con la pratica diventeranno automatiche.

---
