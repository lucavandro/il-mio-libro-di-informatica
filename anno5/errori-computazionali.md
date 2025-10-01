# Errori computazionali

## 1. Introduzione agli errori computazionali

### 1.1 Cos'è un errore computazionale

Immagina di essere un fotografo che cerca di catturare un tramonto perfetto 📸. Anche con la migliore macchina fotografica, l'immagine non sarà mai identica al 100% alla realtà: i colori potrebbero essere leggermente diversi, alcuni dettagli potrebbero andare persi. Allo stesso modo, quando un computer esegue calcoli matematici, il risultato potrebbe non essere perfettamente uguale al valore matematico teorico.

Un **errore computazionale** è la differenza tra il valore esatto di un calcolo matematico e il valore che il computer riesce effettivamente a calcolare e rappresentare. Questo accade perché i computer, pur essendo incredibilmente potenti, hanno dei limiti fisici nella rappresentazione dei numeri.

**Esempio pratico:**

```python
# Prova questo semplice calcolo in Python
risultato = 0.1 + 0.2
print(risultato)
# Output: 0.30000000000000004 (invece di 0.3!)

# Prova anche questo semplice calcolo....
risultato2 = 10/3
print(risultato2)
# Output: 0.33333333333333335 (invece di 0.3!)
```

Questo esempio mostra come anche un calcolo apparentemente semplice possa produrre un errore computazionale.

### 1.2 Perché si verificano gli errori nei calcoli

Gli errori computazionali si verificano per diverse ragioni, tutte legate ai limiti fisici e matematici dei computer:

1. **Memoria limitata**: I computer hanno una quantità finita di memoria per rappresentare i numeri
2. **Sistema binario**: I computer usano il sistema binario (0 e 1), mentre noi usiamo il decimale
3. **Approssimazioni**: Alcuni numeri (come π o √2) hanno infinite cifre decimali
4. **Operazioni successive**: Gli errori si accumulano quando si fanno molti calcoli in sequenza

È come cercare di scrivere il numero π completo su un foglio: prima o poi finirai lo spazio! 📝

### 1.3 Errore assoluto e errore relativo

**Errore Assoluto** = |Valore Vero - Valore Approssimato|
**Errore Relativo** = |Errore Assoluto / Valore Vero| × 100%

**Analogia** 📏: Se sbagli la misura di:

- La lunghezza di una matita (20 cm): errore assoluto = 10 cm, errore relativo = 500% 😱
- La distanza Roma-Milano (600 km): errore assoluto = 10 cm, errore relativo ≈ 0% 😊

L'errore relativo ci dice quanto è "grave" l'errore rispetto alla grandezza che stiamo misurando.

**Esempio pratico:**

```python
import math

def calcola_errori(valore_vero, valore_approssimato):
    """Calcola errore assoluto e relativo"""
    errore_assoluto = abs(valore_vero - valore_approssimato)
    errore_relativo = (errore_assoluto / abs(valore_vero)) * 100 if valore_vero != 0 else float('inf')
    
    return errore_assoluto, errore_relativo

# Esempi con diversi valori
esempi = [
    (math.pi, 3.14),           # Approssimazione di π
    (math.e, 2.72),            # Approssimazione di e
    (1000000, 999999),         # Numero grande
    (0.001, 0.0011),           # Numero piccolo
]

print("Valore vero | Approssimazione | Err. Assoluto | Err. Relativo")
print("-" * 65)

for vero, approx in esempi:
    err_abs, err_rel = calcola_errori(vero, approx)
    print(f"{vero:10.6f} | {approx:13.6f} | {err_abs:11.6f} | {err_rel:8.3f}%")
```

### 1.4 Importanza dell'analisi degli errori
Perché dovremmo preoccuparci di questi errori? Immagina se:

- Il GPS della tua auto avesse un errore di qualche metro ad ogni calcolo 🗺️
- Il sistema di controllo di un aereo accumulasse errori durante il volo ✈️
- I calcoli per una missione spaziale fossero imprecisi 🚀

L'analisi degli errori è fondamentale per:

- **Garantire l'affidabilità** dei risultati scientifici
- **Progettare sistemi sicuri** (automobili, aerei, impianti nucleari)
- **Validare modelli matematici** usati nelle previsioni del tempo
- **Ottimizzare algoritmi** per ridurre al minimo gli errori

**Esempi concreti dell'importanza dell'analisi degli errori:**

🏥 **Medicina**: Nei macchinari per radioterapia, anche un errore di posizionamento di pochi millimetri può significare la differenza tra colpire un tumore o danneggiare tessuti sani. I sistemi di calcolo devono garantire precisione assoluta.

💰 **Finanza**: Le banche elaborano milioni di transazioni al giorno. Un piccolo errore di arrotondamento, moltiplicato per milioni di operazioni, potrebbe causare perdite o guadagni di migliaia di euro. Nel 1996, una banca giapponese perse 1,4 miliardi di dollari a causa di un errore in un algoritmo di trading.

🌡️ **Meteorologia**: Le previsioni del tempo dipendono da modelli complessi che elaborano enormi quantità di dati. Piccoli errori nei calcoli iniziali possono portare a previsioni completamente sbagliate dopo alcuni giorni (effetto farfalla).

🔬 **Ricerca scientifica**: Nel 2006, un errore computazionale in un modello climatico portò a conclusioni errate sui cambiamenti climatici, influenzando politiche ambientali per anni prima che l'errore fosse scoperto.

🎯 **Ingegneria strutturale**: Il calcolo della resistenza di ponti, grattacieli e altre strutture deve essere estremamente preciso. Un errore nei calcoli potrebbe compromettere la sicurezza pubblica.

**Quando gli errori diventano critici:**

- **Sistemi real-time**: Dove decisioni immediate dipendono da calcoli precisi
- **Sistemi di sicurezza**: Dove vite umane dipendono dall'accuratezza
- **Calcoli a lungo termine**: Dove piccoli errori si accumulano nel tempo
- **Sistemi ad alto volume**: Dove errori piccoli moltiplicati diventano significativi

La comprensione e il controllo degli errori computazionali non è quindi solo una questione teorica, ma una necessità pratica per vivere in un mondo sempre più dipendente dai computer! 🌐

### 1.5 Esempi storici di errori computazionali

**Il Bug del Pentium (1994) 🐛**
Il processore Intel Pentium aveva un errore nella divisione di alcuni numeri specifici. Intel inizialmente minimizzò il problema, ma poi dovette sostituire milioni di processori, costando loro 475 milioni di dollari!

**Esplosione dell'Ariane 5 (1996) 💥**
Il razzo europeo Ariane 5 esplose 37 secondi dopo il lancio a causa di un errore di overflow: un numero troppo grande per essere contenuto nella memoria del computer di bordo.

**Il Patriot Missile (1991) 🎯**
Durante la Guerra del Golfo, un errore di precisione nell'orologio interno del sistema Patriot causò un errore di 0.34 secondi, sufficiente per non intercettare un missile Scud che colpì una base americana.

**Il Problema Y2K (2000) 📅**
Molti sistemi informatici rappresentavano gli anni con solo 2 cifre (99 per 1999). Il passaggio al 2000 avrebbe potuto causare il caos, interpretando "00" come 1900 invece che 2000.

## 2. Tipi di errori computazionali

### 2.1 Errori di rappresentazione

Gli errori di rappresentazione si verificano quando un numero non può essere rappresentato esattamente nel sistema binario del computer. È come cercare di scrivere 1/3 in forma decimale: ottieni 0.333333... con infinite cifre!

**Esempio pratico:**

```python
# Alcuni numeri decimali non possono essere rappresentati esattamente in binario
print(0.1)  # Output: 0.1 (sembra corretto)
print(f"{0.1:.20f}")  # Output: 0.10000000000000000555... (la realtà!)

# Un caso famoso: 1/10 in binario
decimal_value = 0.1
binary_representation = format(decimal_value, '.60f')
print(f"0.1 è rappresentato come: {binary_representation}")
```

**Curiosità 🤔**: Il numero 0.1 in binario è 0.0001100110011... (periodico), quindi non può mai essere rappresentato esattamente!

### 2.2 Errori di troncamento

L'errore di troncamento si verifica quando "tagliamo" un calcolo prima di arrivare al risultato esatto. È come interrompere un video prima della fine! 🎬

**Ma cosa significa "tagliare" un calcolo?**

Molte operazioni matematiche richiedono un numero infinito di passaggi per essere perfette. Il computer, però, deve fermarsi da qualche parte. Facciamo alcuni esempi semplici:

**1️⃣ Calcolo della radice quadrata**
Per calcolare √2, il computer usa un metodo che migliora progressivamente l'approssimazione:

- Tentativo 1: 1.5 (errore grande)
- Tentativo 2: 1.42 (meglio!)
- Tentativo 3: 1.414 (ancora meglio!)
- Tentativo 4: 1.4142 (quasi perfetto!)
- ...

Se il computer si ferma al tentativo 3 invece che al 10, ottiene un risultato meno preciso: questo è l'errore di troncamento!

**2️⃣ Calcolo di frazioni con divisioni**
Prova a calcolare 1÷3 con la calcolatrice:

- Primo decimale: 0.3
- Secondo decimale: 0.33
- Terzo decimale: 0.333
- Quarto decimale: 0.3333
- ...

Il valore esatto sarebbe 0.333333... (infiniti 3), ma la calcolatrice si ferma a un certo punto!

**Esempi pratici nella vita quotidiana:**

🧮 **Calcolo delle tasse**: Quando l'Agenzia delle Entrate calcola gli interessi su un debito, utilizza formule complesse che richiedono molti passaggi. Fermandosi prima del calcolo "perfetto", si introduce un errore di troncamento.

*Esempio numerico*: Calcolo dell'interesse composto su un debito di €10.000 al 5% annuo per 20 anni:

- Con calcolo semplificato (pochi passaggi): €27.166,67
- Con calcolo preciso (molti passaggi): €27.182,82
- Errore di troncamento: €16,15

📱 **App del meteo**: Le previsioni del tempo usano calcoli complessi che vengono "tagliati" per avere le previsioni in tempi ragionevoli. Se facessero calcoli infiniti, avremmo previsioni perfette ma dopo mesi di attesa!

*Esempio numerico*: Previsione della temperatura:

- Con calcolo veloce (pochi passaggi): 19.1°C
- Con calcolo lento (molti passaggi): 18.3°C  
- Errore di troncamento: 0.8°C

🎮 **Videogiochi**: Quando il tuo personaggio salta, il computer calcola la traiettoria del salto con la fisica. Se facesse calcoli infiniti, il gioco andrebbe a 0.001 frame al secondo!

*Esempio*:

- Posizione dopo 1 secondo (calcolo veloce): coordinata (5.2, 8.1)
- Posizione dopo 1 secondo (calcolo preciso): coordinata (5.18, 8.13)

Il calcolo, pur non essendo preciso al 100%, è abbastanza vicino a quello esatto.

🚗 **Navigatore GPS**: Quando calcola il percorso più breve, il GPS esplora milioni di strade possibili. Ma se provasse TUTTE le combinazioni, impiegherebbe ore! Quindi si ferma quando trova un percorso "abbastanza buono".

**La differenza cruciale:**

- **Errore di arrotondamento**: "Non riesco a scrivere tutte le cifre" (problema di spazio in memoria)
- **Errore di troncamento**: "Non ho tempo di fare tutti i calcoli" (problema di velocità)

È come la differenza tra:

- Scrivere 3.141 invece di π perché hai solo 5 caselle (arrotondamento)
- Fermarti a calcolare solo i primi 4 decimali di π perché hai fretta (troncamento)

**Come si controlla l'errore di troncamento:**

I programmatori decidono quando "fermarsi" basandosi su:

- ⏰ **Tempo disponibile**: "Ho solo 0.1 secondi per questo calcolo"
- 🎯 **Precisione desiderata**: "Mi basta un errore sotto l'1%"
- 🔋 **Energia della batteria**: "Devo risparmiare per non scaricare il telefono"

La sfida è trovare il giusto equilibrio tra velocità e precisione! ⚖️

Un po' come quando studi: potresti passare ore a perfezionare un tema, ma ad un certo punto devi "tagliare" e consegnare, anche se non è perfetto al 100%! 📚

### 2.3 Errori di arrotondamento

Gli errori di arrotondamento si verificano quando un numero deve essere "ridotto" per adattarsi alla memoria del computer. È come dovere scrivere "ciao" in uno spazio che può contenere solo 3 lettere: diventa "cia"! ✂️

**Esempio: Calcolo della circonferenza terrestre**

Consideriamo il calcolo della circonferenza terrestre, dato che il raggio è approssimativamente 6.371 km.

**Formula**: C = 2πr

**Con π approssimato (3.14):**

- C = 2 × 3.14 × 6.371 km
- C = 6.28 × 6.371 km
- C = **40.009,788 km**

**Con π più preciso (3.141592653):**

- C = 2 × 3.141592653 × 6.371 km  
- C = 6.283185306 × 6.371 km
- C = **40.019,186 km**

Questo significa che usando la semplice approssimazione π ≈ 3.14 invece di un valore più preciso, commettiamo un errore di quasi **9,4 chilometri** nel calcolo della circonferenza terrestre! 🌍

**Conclusione**: Gli errori di arrotondamento, anche se sembrano piccoli, possono avere conseguenze importanti in calcoli che coinvolgono grandezze fisiche reali. In questo caso, l'uso di sole 2 cifre decimali per π introduce un errore di quasi 10 km nel calcolo di una distanza planetaria.

### 2.4 Errori di overflow e underflow

**Overflow** 📈: Quando un numero diventa troppo grande per essere rappresentato
**Underflow** 📉: Quando un numero diventa troppo piccolo (vicino a zero) per essere rappresentato accuratamente

**Esempio di overflow:**

```python
import sys

# Trova il massimo numero rappresentabile
print(f"Massimo float: {sys.float_info.max}")

try:
    # Tenta di creare un numero troppo grande
    numero_grande = 10.0 ** 400
    print(f"10^400 = {numero_grande}")
except OverflowError:
    print("Overflow! Numero troppo grande!")

# Esempio pratico: calcolo di fattoriali
def fattoriale_problematico(n):
    risultato = 1.0
    for i in range(1, n + 1):
        risultato *= i
        if risultato == float('inf'):
            print(f"Overflow al fattoriale di {i}!")
            break
    return risultato

print("Calcoliamo fattoriali crescenti:")
for n in [100, 200, 300]:
    f = fattoriale_problematico(n)
    print(f"{n}! = {f}")
```

## 3. Standard IEEE 754

### 3.1 Introduzione allo standard IEEE 754

Lo standard IEEE 754 è come il "codice della strada" per i numeri nei computer 🚗. Stabilisce le regole su come rappresentare e manipolare i numeri decimali (chiamati "numeri in virgola mobile" o "floating point") in modo uniforme in tutti i computer del mondo.

Prima di questo standard (introdotto nel 1985), ogni produttore di computer aveva le sue regole, creando caos e incompatibilità. È come se ogni paese avesse regole stradali diverse!

**Perché è importante:**

- **Standardizzazione**: Tutti i computer seguono le stesse regole
- **Portabilità**: Un programma scritto su un computer funziona ugualmente su un altro
- **Predicibilità**: Gli errori di calcolo sono prevedibili e documentati

### 3.2 Rappresentazione dei numeri in virgola mobile

Un numero in virgola mobile è composto da tre parti, come un indirizzo completo (via, numero civico, città):

1. **Segno (S)**: 1 bit - indica se il numero è positivo o negativo
2. **Esponente (E)**: determina "quanto è grande" il numero
3. **Mantissa (M)**: contiene le cifre significative del numero

**Formula matematica:**

```
Numero = (-1)^S × (1 + M) × 2^(E-bias)
```

### 3.3 Singola precisione (32 bit) e doppia precisione (64 bit)

**Singola Precisione (float - 32 bit)** 🎯:

- 1 bit per il segno
- 8 bit per l'esponente
- 23 bit per la mantissa
- Circa 7 cifre decimali significative

**Doppia Precisione (double - 64 bit)** 🎯🎯:

- 1 bit per il segno  
- 11 bit per l'esponente
- 52 bit per la mantissa
- Circa 15-16 cifre decimali significative

### 3.4 Valori speciali (infinito, NaN, zero)

Lo standard IEEE 754 definisce alcuni valori speciali per gestire situazioni matematiche particolari:

**+∞ e -∞ (Infinito)** ♾️ - **NaN (Not a Number)** 🤔 - **Zero positivo e negativo** ±0


### 3.4 Conversione di un numero da base 10 a IEEE754 a 32bit

La rappresentazione IEEE 754 a 32 bit (singola precisione) utilizza 1 bit per il segno, 8 bit per l'esponente e 23 bit per la mantissa. Seguiamo i passi per convertire i numeri 10.5, -11.25 e 11.6.

#### Passaggi generali:
1. **Determina il segno (S)**: 0 per numeri positivi, 1 per numeri negativi.
2. **Converti il numero in binario**: Dividi la parte intera e la parte decimale, convertendole separatamente.
3. **Normalizza il numero**: Porta il numero in forma scientifica binaria, del tipo \(1.m \times 2^E\), dove \(1.m\) è la mantissa.
4. **Calcola l'esponente (E)**: Aggiungi il bias (127 per IEEE 754 a 32 bit) all'esponente della forma scientifica.
5. **Costruisci la mantissa (M)**: Prendi i bit significativi dopo il punto binario della parte normalizzata, riempiendo fino a 23 bit.
6. **Combina i campi**: Unisci segno, esponente e mantissa per ottenere il numero finale.

---

#### Esempio 1: 10.5

1. **Segno (S)**: 10.5 è positivo, quindi \(S = 0\).
2. **Binario**:  
    - Parte intera: \(10_{10} = 1010_2\).  
    - Parte decimale: \(0.5_{10} = 0.1_2\).  
    - Risultato: \(10.5_{10} = 1010.1_2\).
3. **Normalizzazione**: \(1010.1_2 = 1.0101_2 \times 2^3\).
4. **Esponente (E)**: \(3 + 127 = 130\). In binario: \(130_{10} = 10000010_2\).
5. **Mantissa (M)**: Prendi i bit dopo il punto: \(01010000000000000000000\) (23 bit).
6. **Risultato finale**:  
    - Segno: \(0\).  
    - Esponente: \(10000010\).  
    - Mantissa: \(01010000000000000000000\).  
    - IEEE 754: \(0 10000010 01010000000000000000000\).

---

#### Esempio 2: -11.25

1. **Segno (S)**: -11.25 è negativo, quindi \(S = 1\).
2. **Binario**:  
    - Parte intera: \(11_{10} = 1011_2\).  
    - Parte decimale: \(0.25_{10} = 0.01_2\).  
    - Risultato: \(-11.25_{10} = -1011.01_2\).
3. **Normalizzazione**: \(-1011.01_2 = -1.01101_2 \times 2^3\).
4. **Esponente (E)**: \(3 + 127 = 130\). In binario: \(130_{10} = 10000010_2\).
5. **Mantissa (M)**: Prendi i bit dopo il punto: \(01101000000000000000000\) (23 bit).
6. **Risultato finale**:  
    - Segno: \(1\).  
    - Esponente: \(10000010\).  
    - Mantissa: \(01101000000000000000000\).  
    - IEEE 754: \(1 10000010 01101000000000000000000\).

---

#### Esempio 3: 11.6

1. **Segno (S)**: 11.6 è positivo, quindi \(S = 0\).
2. **Binario**:  
    - Parte intera: \(11_{10} = 1011_2\).  
    - Parte decimale: \(0.6_{10} \approx 0.100110011001..._2\) (periodico).  
    - Risultato: \(11.6_{10} \approx 1011.100110011001..._2\).
3. **Normalizzazione**: \(1011.100110011001..._2 = 1.011100110011001..._2 \times 2^3\).
4. **Esponente (E)**: \(3 + 127 = 130\). In binario: \(130_{10} = 10000010_2\).
5. **Mantissa (M)**: Prendi i bit dopo il punto: \(01110011001100110011001\) (23 bit, troncando il periodico).
6. **Risultato finale**:  
    - Segno: \(0\).  
    - Esponente: \(10000010\).  
    - Mantissa: \(01110011001100110011001\).  
    - IEEE 754: \(0 10000010 01110011001100110011001\).

---

Questi sono i risultati finali in formato IEEE 754 a 32 bit per i tre numeri:
- **10.5**: \(0 10000010 01010000000000000000000\)
- **-11.25**: \(1 10000010 01101000000000000000000\)
- **11.6**: \(0 10000010 01110011001100110011001\)

## 4. Propagazione degli errori

### 4.1 Come si propagano gli errori nei calcoli

La propagazione degli errori è come il "telefono senza fili" 📞. Quando un piccolo errore si introduce all'inizio di una catena di calcoli, può amplificarsi o ridursi man mano che procediamo.

**Analogia pratica**: Immagina di costruire una torre di carte 🏗️. Se la prima carta è leggermente storta, ogni carta successiva amplificherà questo errore, fino a far crollare l'intera struttura!

**Esempio fondamentale:**

```python
import math

def dimostra_propagazione():
    """
    Dimostra come gli errori si propagano attraverso una catena di calcoli
    """
    # Valore iniziale con un piccolo errore
    x_esatto = 1.0
    x_con_errore = 1.0000001  # Errore di 0.0000001
    
    print("Operazione | Valore esatto | Con errore | Errore relativo")
    print("-" * 60)
    
    # Serie di operazioni che amplificano l'errore
    for i in range(5):
        # Operazione: elevare al quadrato e sottrarre 1
        x_esatto = x_esatto ** 2 - 1
        x_con_errore = x_con_errore ** 2 - 1
        
        if x_esatto != 0:
            errore_rel = abs((x_con_errore - x_esatto) / x_esatto) * 100
        else:
            errore_rel = 0
            
        print(f"Passo {i+1:2}   | {x_esatto:11.6f} | {x_con_errore:10.6f} | {errore_rel:8.2f}%")

dimostra_propagazione()
```

### 4.2 Condizionamento di un problema

Il **numero di condizione** indica quanto è "sensibile" un problema agli errori nei dati di input. È come la stabilità di una bicicletta:

- Bici normale: piccole oscillazioni → piccole correzioni (ben condizionato) 🚲
- Monociclo: piccole oscillazioni → grandi correzioni (mal condizionato) 🤹

**Definizione matematica:**

```
Numero di condizione ≈ (Variazione relativa dell'output) / (Variazione relativa dell'input)
```

**Esempio classico: risoluzione di sistemi lineari**

```python
import numpy as np
from scipy.linalg import hilbert, inv

def analizza_condizionamento():
    """Analizza il condizionamento della matrice di Hilbert"""
    
    print("Dimensione | Numero di condizione | Classificazione")
    print("-" * 55)
    
    for n in [3, 5, 7, 9, 12]:
        # Crea matrice di Hilbert (notoriamente mal condizionata)
        H = hilbert(n)
        
        # Calcola il numero di condizione
        cond_num = np.linalg.cond(H)
        
        # Classifica il condizionamento
        if cond_num < 100:
            classe = "Ben condizionato"
        elif cond_num < 10000:
            classe = "Moderatamente condizionato"
        else:
            classe = "Mal condizionato"
        
        print(f"{n:8}   | {cond_num:17.2e} | {classe}")

analizza_condizionamento()
```

**Conseguenze pratiche:**

- **Problemi ben condizionati**: Gli errori di input causano errori proporzionali nell'output
- **Problemi mal condizionati**: Piccoli errori di input possono causare enormi errori nell'output

### 4.3 Stabilità numerica degli algoritmi

Un algoritmo è **numericamente stabile** se piccoli errori nei dati di input o nel calcolo non causano grandi errori nel risultato finale. È come la differenza tra:

- Un chirurgo esperto (stabile): mano ferma anche con piccole distrazioni ✋
- Un principiante nervoso (instabile): piccole distrazioni causano grandi errori 😰

**Esempio: Due algoritmi per calcolare la varianza**

```python
import random
import math

def varianza_instabile(dati):
    """Formula matematicamente corretta ma numericamente instabile"""
    n = len(dati)
    media = sum(dati) / n
    
    # Formula: Var = E[X²] - (E[X])²
    somma_quadrati = sum(x**2 for x in dati) / n
    quadrato_media = media**2
    
    return somma_quadrati - quadrato_media

def varianza_stabile(dati):
    """Formula numericamente stabile"""
    n = len(dati)
    media = sum(dati) / n
    
    # Formula: Var = Σ(x - μ)² / n
    somma_scarti_quadrati = sum((x - media)**2 for x in dati)
    
    return somma_scarti_quadrati / n

def confronta_algoritmi_varianza():
    """Confronta la stabilità di due algoritmi per il calcolo della varianza"""
    
    # Genera dati con media molto grande e varianza piccola
    # (caso che evidenzia problemi di stabilità)
    media_grande = 1e10
    dati = [media_grande + random.gauss(0, 1) for _ in range(1000)]
    
    var_instabile = varianza_instabile(dati)
    var_stabile = varianza_stabile(dati)
    var_numpy = np.var(dati)  # Implementazione di riferimento
    
    print("Algoritmo instabile:", var_instabile)
    print("Algoritmo stabile:  ", var_stabile)
    print("NumPy (riferimento):", var_numpy)
    print()
    print("Errore algoritmo instabile:", abs(var_instabile - var_numpy))
    print("Errore algoritmo stabile:  ", abs(var_stabile - var_numpy))

confronta_algoritmi_varianza()
```

**Caratteristiche degli algoritmi stabili:**

- Gli errori di arrotondamento non si amplificano
- Il risultato è accurato anche con dati "difficili"
- Sono preferibili anche se computazionalmente più costosi

**Esempio: Algoritmo di Kahan per la somma**

```python
def confronta_algoritmi_somma():
    """Confronta algoritmi di somma per stabilità numerica"""
    
    # Crea una lista con molti numeri piccoli
    # Questo è un caso difficile per la somma naive
    numeri = [1e-16] * 1000000 + [1.0]
    valore_atteso = 1.0 + 1e-16 * 1000000
    
    # Somma naive (instabile)
    def somma_naive(numeri):
        totale = 0.0
        for numero in numeri:
            totale += numero
        return totale
    
    # Algoritmo di Kahan (stabile)
    def somma_kahan(numeri):
        somma = 0.0
        c = 0.0  # Compensazione per errori persi
        
        for numero in numeri:
            y = numero - c
            t = somma + y
            c = (t - somma) - y
            somma = t
        
        return somma
    
    risultato_naive = somma_naive(numeri)
    risultato_kahan = somma_kahan(numeri)
    
    print(f"Valore atteso:     {valore_atteso}")
    print(f"Risultato naive:   {risultato_naive}")
    print(f"Risultato Kahan:   {risultato_kahan}")

confronta_algoritmi_somma()
```

**Metafora finale** 🎭: Gli errori computazionali sono come l'eco in una montagna. A volte si amplificano creando rumore assordante, altre volte si attenuano dolcemente. Il nostro compito è costruire algoritmi che controllino questo "eco" matematico!
