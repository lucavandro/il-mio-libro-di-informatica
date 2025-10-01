# Errori computazionali

## 1. Introduzione agli errori computazionali

### 1.1 Cos'è un errore computazionale

Immagina di essere un fotografo che cerca di catturare un tramonto perfetto 📸. Anche con la migliore macchina fotografica, l'immagine non sarà mai identica al 100% alla realtà: i colori potrebbero essere leggermente diversi, alcuni dettagli potrebbero an## 4. Propagazione degli errori

### 4.1 Come si propagano gli errori nei calcoli

La propagazione degli errori è come il "telefono senza fili" 📞. Quando un piccolo errore si introduce all'inizio di una catena di calcoli, può amplificarsi o ridursi man mano che procediamo.

**Analogia pratica**: Immagina di costruire una torre di carte 🏗️. Se la prima carta è leggermente storta, ogni carta successiva amplificherà questo errore, fino a far crollare l'intera struttura!

**Esempio fondamentale:**

```python
import math

def dimostra_propagazione():
    """
    Dimostra come gli errori si propagano attraverso i calcoli
    """
    # Valore "esatto" (con errore minimo)
    x_esatto = 1.0
    
    # Valore con errore
    x_con_errore = 1.0000001  # Errore di 10^-7
    
    print("Propagazione attraverso operazioni:")
    print(f"Valore esatto: {x_esatto}")
    print(f"Valore con errore: {x_con_errore}")
    print(f"Errore iniziale: {abs(x_con_errore - x_esatto):.2e}")
    print("-" * 50)
    
    # Elevamento a potenza (amplifica l'errore)
    potenza = 10
    risultato_esatto = x_esatto ** potenza
    risultato_con_errore = x_con_errore ** potenza
    errore_finale = abs(risultato_con_errore - risultato_esatto)
    
    print(f"Dopo x^{potenza}:")
    print(f"Risultato esatto: {risultato_esatto}")
    print(f"Risultato con errore: {risultato_con_errore}")
    print(f"Errore finale: {errore_finale:.2e}")
    print(f"Amplificazione: {errore_finale / abs(x_con_errore - x_esatto):.1f}x")
    
    # Radice quadrata (riduce l'errore)
    valore_grande = 100.0
    valore_con_errore = 100.01
    
    sqrt_esatto = math.sqrt(valore_grande)
    sqrt_con_errore = math.sqrt(valore_con_errore)
    
    print(f"\nRadice quadrata (riduce l'errore):")
    print(f"√100 = {sqrt_esatto}")
    print(f"√100.01 = {sqrt_con_errore}")
    print(f"Errore originale: {abs(valore_con_errore - valore_grande)}")
    print(f"Errore dopo √: {abs(sqrt_con_errore - sqrt_esatto):.6f}")

dimostra_propagazione()
```

### 4.2 Errore assoluto e errore relativo

**Errore Assoluto** 📏: La differenza tra il valore vero e quello calcolato
```
Errore Assoluto = |valore_vero - valore_calcolato|
```

**Errore Relativo** 📊: L'errore assoluto rapportato al valore vero
```
Errore Relativo = |valore_vero - valore_calcolato| / |valore_vero|
```

**Analogia**: Se sbagli di 1 metro misurando:
- La lunghezza di una matita (20 cm): errore relativo = 500% 😱
- La lunghezza di un campo da calcio (100 m): errore relativo = 1% 😊

```python
def calcola_errori(valore_vero, valore_misurato):
    """
    Calcola errore assoluto e relativo
    """
    errore_assoluto = abs(valore_vero - valore_misurato)
    errore_relativo = errore_assoluto / abs(valore_vero) if valore_vero != 0 else float('inf')
    
    print(f"Valore vero: {valore_vero}")
    print(f"Valore misurato: {valore_misurato}")
    print(f"Errore assoluto: {errore_assoluto}")
    print(f"Errore relativo: {errore_relativo:.2%}")
    print("-" * 30)

# Esempi pratici
print("CONFRONTO ERRORI:")
calcola_errori(1000000, 1000001)  # Errore piccolo su numero grande
calcola_errori(0.000001, 0.000002)  # Errore piccolo su numero piccolo
calcola_errori(1.0, 1.1)  # Errore grande su numero normale

# Esempio scientifico
calcola_errori(9.81, 9.8)  # Accelerazione di gravità
calcola_errori(299792458, 300000000)  # Velocità della luce (approssimata)
```

### 4.3 Condizionamento di un problema

Il **numero di condizionamento** misura quanto un problema è "sensibile" ai piccoli cambiamenti nei dati di input. È come misurare quanto è "traballante" una sedia 🪑.

**Problema ben condizionato** ✅: Piccole variazioni nell'input causano piccole variazioni nell'output
**Problema mal condizionato** ❌: Piccole variazioni nell'input causano grandi variazioni nell'output

```python
import numpy as np

def test_condizionamento():
    """
    Dimostra problemi ben e mal condizionati
    """
    print("PROBLEMA BEN CONDIZIONATO:")
    print("Calcolo di f(x) = x + 1")
    x_values = [1.0, 1.001, 1.002]
    for x in x_values:
        result = x + 1
        print(f"f({x}) = {result}")
    
    print("\nPROBLEMA MAL CONDIZIONATO:")
    print("Sistema di equazioni lineari:")
    
    # Matrice mal condizionata (quasi singolare)
    A = np.array([[1.0, 1.0],
                  [1.0, 1.000001]])
    
    b1 = np.array([2.0, 2.000001])
    b2 = np.array([2.0, 2.000002])  # Piccola variazione
    
    # Risoluzione
    x1 = np.linalg.solve(A, b1)
    x2 = np.linalg.solve(A, b2)
    
    print(f"Soluzione con b1: {x1}")
    print(f"Soluzione con b2: {x2}")
    print(f"Variazione in b: {np.linalg.norm(b2 - b1):.2e}")
    print(f"Variazione in x: {np.linalg.norm(x2 - x1):.2e}")
    
    # Numero di condizionamento
    cond_number = np.linalg.cond(A)
    print(f"Numero di condizionamento: {cond_number:.2e}")
    
    if cond_number > 1e12:
        print("⚠️  PROBLEMA MAL CONDIZIONATO!")
    else:
        print("✅ Problema ben condizionato")

test_condizionamento()
```

**Esempio classico - Calcolo di radici vicine:**
```python
import numpy as np

def radici_equazione_quadratica(a, b, c):
    """
    Calcola le radici di ax² + bx + c = 0
    Dimostra problemi di condizionamento
    """
    discriminante = b**2 - 4*a*c
    
    if discriminante < 0:
        return None, None
    
    sqrt_discriminante = np.sqrt(discriminante)
    
    # Formula standard (può essere instabile)
    x1_standard = (-b + sqrt_discriminante) / (2*a)
    x2_standard = (-b - sqrt_discriminante) / (2*a)
    
    # Formula alternativa per evitare cancellazione catastrofica
    if b >= 0:
        x1_stabile = (-b - sqrt_discriminante) / (2*a)
        x2_stabile = (2*c) / (-b - sqrt_discriminante)
    else:
        x1_stabile = (2*c) / (-b + sqrt_discriminante)
        x2_stabile = (-b + sqrt_discriminante) / (2*a)
    
    return (x1_standard, x2_standard), (x1_stabile, x2_stabile)

# Esempio con radici molto vicine (mal condizionato)
a, b, c = 1, 1000000, 1
print("Equazione: x² + 1000000x + 1 = 0")

standard, stabile = radici_equazione_quadratica(a, b, c)
print(f"Metodo standard: {standard}")
print(f"Metodo stabile: {stabile}")

# Verifica (sostituendo nella equazione originale)
x1, x2 = stabile
verifica1 = a*x1**2 + b*x1 + c
verifica2 = a*x2**2 + b*x2 + c
print(f"Verifica x1: {verifica1}")
print(f"Verifica x2: {verifica2}")
```

### 4.4 Stabilità numerica degli algoritmi

Un algoritmo è **numericamente stabile** se produce risultati accurati anche in presenza di piccoli errori di arrotondamento. È come un ponte che rimane in piedi anche con piccole vibrazioni 🌉.

**Caratteristiche di un algoritmo stabile:**
- Gli errori di arrotondamento non si amplificano
- Il risultato finale è vicino alla soluzione esatta
- Funziona bene anche con dati "rumorosi"

```python
def confronta_algoritmi_somma():
    """
    Confronta algoritmi stabili e instabili per la somma
    """
    # Creiamo una lista di numeri con ordini di grandezza molto diversi
    numeri = [1e16, 1.0, -1e16, 1.0, 1.0]
    
    print("Numeri da sommare:", numeri)
    print(f"Somma teorica: {sum(numeri)}")
    
    # Algoritmo instabile: somma nell'ordine dato
    somma_instabile = 0.0
    for num in numeri:
        somma_instabile += num
        print(f"Parziale: {somma_instabile}")
    
    print(f"Risultato instabile: {somma_instabile}")
    
    # Algoritmo più stabile: ordina i numeri per grandezza
    numeri_ordinati = sorted(numeri, key=abs)
    print(f"\nNumeri ordinati per grandezza: {numeri_ordinati}")
    
    somma_stabile = 0.0
    for num in numeri_ordinati:
        somma_stabile += num
        print(f"Parziale: {somma_stabile}")
    
    print(f"Risultato stabile: {somma_stabile}")
    
    # Algoritmo di Kahan (compensazione degli errori)
    def somma_kahan(numeri):
        somma = 0.0
        compensazione = 0.0
        
        for num in numeri:
            y = num - compensazione
            temp = somma + y
            compensazione = (temp - somma) - y
            somma = temp
        
        return somma
    
    risultato_kahan = somma_kahan(numeri)
    print(f"Risultato Kahan: {risultato_kahan}")

confronta_algoritmi_somma()
```

**Metafora finale** 🎭: Gli errori computazionali sono come l'eco in una montagna. A volte si amplifican​o creando rumore assordante, altre volte si attenuano dolcemente. Il nostro compito è costruire algoritmi che controllino questo "eco" matematico!ersi. Allo stesso modo, quando un computer esegue calcoli matematici, il risultato potrebbe non essere perfettamente uguale al valore matematico teorico.

Un **errore computazionale** è la differenza tra il valore esatto di un calcolo matematico e il valore che il computer riesce effettivamente a calcolare e rappresentare. Questo accade perché i computer, pur essendo incredibilmente potenti, hanno dei limiti fisici nella rappresentazione dei numeri.

**Esempio pratico:**
```python
# Prova questo semplice calcolo in Python
risultato = 0.1 + 0.2
print(risultato)
# Output: 0.30000000000000004 (invece di 0.3!)
```

Questo esempio mostra come anche un calcolo apparentemente semplice possa produrre un errore computazionale.

### 1.2 Perché si verificano gli errori nei calcoli

Gli errori computazionali si verificano per diverse ragioni, tutte legate ai limiti fisici e matematici dei computer:

1. **Memoria limitata**: I computer hanno una quantità finita di memoria per rappresentare i numeri
2. **Sistema binario**: I computer usano il sistema binario (0 e 1), mentre noi usiamo il decimale
3. **Approssimazioni**: Alcuni numeri (come π o √2) hanno infinite cifre decimali
4. **Operazioni successive**: Gli errori si accumulano quando si fanno molti calcoli in sequenza

È come cercare di scrivere il numero π completo su un foglio: prima o poi finirai lo spazio! 📝

### 1.3 Importanza dell'analisi degli errori

Perché dovremmo preoccuparci di questi errori? Immagina se:
- Il GPS della tua auto avesse un errore di qualche metro ad ogni calcolo 🗺️
- Il sistema di controllo di un aereo accumulasse errori durante il volo ✈️
- I calcoli per una missione spaziale fossero imprecisi 🚀

L'analisi degli errori è fondamentale per:
- **Garantire l'affidabilità** dei risultati scientifici
- **Progettare sistemi sicuri** (automobili, aerei, impianti nucleari)
- **Validare modelli matematici** usati nelle previsioni del tempo
- **Ottimizzare algoritmi** per ridurre al minimo gli errori

### 1.4 Esempi storici di errori computazionali

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

L'errore di troncamento si verifica quando "tagliamo" una serie infinita o un calcolo iterativo prima del risultato esatto. È come interrompere un video prima della fine! 🎬

**Esempio con le serie di Taylor:**
```python
import math

# Calcolo del seno usando la serie di Taylor: sin(x) = x - x³/3! + x⁵/5! - x⁷/7! + ...
def sin_taylor(x, n_terms):
    """
    Calcola il seno usando i primi n_terms della serie di Taylor
    x: angolo in radianti
    n_terms: numero di termini da utilizzare
    """
    result = 0
    for n in range(n_terms):
        term = ((-1)**n) * (x**(2*n + 1)) / math.factorial(2*n + 1)
        result += term
    return result

x = math.pi / 4  # 45 gradi
print(f"sin({x}) esatto: {math.sin(x)}")
print(f"Con 5 termini: {sin_taylor(x, 5)}")
print(f"Con 10 termini: {sin_taylor(x, 10)}")
# Più termini = maggiore precisione, ma mai esatto al 100%
```

### 2.3 Errori di arrotondamento

Quando un numero ha più cifre di quelle che il computer può memorizzare, deve "arrotondare" il risultato. È come dover riassumere un libro in una frase: qualcosa si perde sempre! 📚

**Esempio di accumulo di errori:**
```python
# Simulazione di un accumulo di errori di arrotondamento
def accumula_errori():
    """
    Dimostra come gli errori di arrotondamento si accumulano
    """
    somma_float = 0.0
    
    # Aggiungiamo 0.1 per 1000 volte
    for i in range(1000):
        somma_float += 0.1
    
    print(f"1000 × 0.1 dovrebbe essere: 100.0")
    print(f"Il computer calcola: {somma_float}")
    print(f"Errore: {abs(100.0 - somma_float)}")

accumula_errori()
```

**Strategia per ridurre l'errore:**
```python
# Alternativa più precisa usando numeri interi
def calcolo_preciso():
    """
    Calcola la stessa somma usando una strategia più precisa
    """
    # Invece di sommare 0.1, sommiamo 1 e dividiamo alla fine
    somma_int = 0
    for i in range(1000):
        somma_int += 1  # Aggiungiamo 1 invece di 0.1
    
    risultato = somma_int / 10  # Dividiamo per 10 alla fine
    print(f"Calcolo più preciso: {risultato}")

calcolo_preciso()
```

### 2.4 Errori di overflow e underflow

**Overflow** 📈: Quando un numero è troppo grande per essere rappresentato
**Underflow** 📉: Quando un numero è troppo piccolo e viene approssimato a zero

```python
import sys

# Informazioni sui limiti del sistema
print(f"Numero float più grande: {sys.float_info.max}")
print(f"Numero float più piccolo: {sys.float_info.min}")

# Esempio di overflow
try:
    numero_gigante = 10.0 ** 400  # Troppo grande!
    print(f"10^400 = {numero_gigante}")
except OverflowError:
    print("Overflow! Il numero è troppo grande!")

# Esempio di underflow
numero_piccolissimo = 10.0 ** -400
print(f"10^-400 = {numero_piccolissimo}")  # Probabilmente stamperà 0.0

# Dimostrazione pratica in un ciclo
print("\nDimostrazione di underflow progressivo:")
valore = 1.0
for i in range(10):
    valore = valore / 10
    print(f"Iterazione {i+1}: {valore}")
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

**Esempio visivo:**
```python
import struct

def analizza_float(numero):
    """
    Analizza la rappresentazione binaria di un numero float
    """
    # Converte il float in rappresentazione binaria
    packed = struct.pack('!f', numero)
    unpacked = struct.unpack('!I', packed)[0]
    
    # Estrae segno, esponente e mantissa
    segno = (unpacked >> 31) & 0x1
    esponente = (unpacked >> 23) & 0xFF
    mantissa = unpacked & 0x7FFFFF
    
    print(f"Numero: {numero}")
    print(f"Segno: {segno} ({'negativo' if segno else 'positivo'})")
    print(f"Esponente: {esponente} (bias 127, valore reale: {esponente - 127})")
    print(f"Mantissa: {mantissa}")
    print(f"Binario completo: {format(unpacked, '032b')}")
    print("-" * 40)

# Esempi
analizza_float(3.14)
analizza_float(-0.5)
analizza_float(1.0)
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

```python
import numpy as np

# Confronto tra precisioni
numero_originale = 1.23456789012345678901234567890

# Singola precisione
float32 = np.float32(numero_originale)
print(f"Numero originale: {numero_originale}")
print(f"Float32 (singola): {float32}")
print(f"Differenza: {abs(numero_originale - float32)}")

# Doppia precisione
float64 = np.float64(numero_originale)
print(f"Float64 (doppia): {float64}")
print(f"Differenza: {abs(numero_originale - float64)}")

# Dimostrazione dei limiti
print(f"\nLimiti float32:")
print(f"Minimo: {np.finfo(np.float32).min}")
print(f"Massimo: {np.finfo(np.float32).max}")
print(f"Epsilon: {np.finfo(np.float32).eps}")

print(f"\nLimiti float64:")
print(f"Minimo: {np.finfo(np.float64).min}")
print(f"Massimo: {np.finfo(np.float64).max}")
print(f"Epsilon: {np.finfo(np.float64).eps}")
```

### 3.4 Valori speciali (infinito, NaN, zero)

Lo standard IEEE 754 definisce alcuni valori speciali per gestire situazioni matematiche particolari:

**+∞ e -∞ (Infinito)** ♾️:
```python
import math

# Modi per ottenere infinito
infinito_positivo = float('inf')
infinito_negativo = float('-inf')
infinito_da_divisione = 1.0 / 0.0

print(f"Infinito positivo: {infinito_positivo}")
print(f"Infinito negativo: {infinito_negativo}")
print(f"1/0 = {infinito_da_divisione}")

# Operazioni con infinito
print(f"inf + 1000 = {infinito_positivo + 1000}")
print(f"inf / 2 = {infinito_positivo / 2}")
print(f"inf > 999999999 = {infinito_positivo > 999999999}")
```

**NaN (Not a Number)** 🤔:
```python
# Modi per ottenere NaN
nan_value = float('nan')
nan_da_calcolo = 0.0 / 0.0
nan_radice_negativa = math.sqrt(-1)

print(f"NaN: {nan_value}")
print(f"0/0 = {nan_da_calcolo}")

# Proprietà strane di NaN
print(f"NaN == NaN: {nan_value == nan_value}")  # False!
print(f"math.isnan(NaN): {math.isnan(nan_value)}")  # True

# NaN "contamina" tutti i calcoli
print(f"NaN + 5 = {nan_value + 5}")
print(f"NaN * 0 = {nan_value * 0}")
```

**Zero positivo e negativo** ±0:
```python
# Python distingue tra +0.0 e -0.0
zero_positivo = 0.0
zero_negativo = -0.0

print(f"Zero positivo: {zero_positivo}")
print(f"Zero negativo: {zero_negativo}")
print(f"Sono uguali? {zero_positivo == zero_negativo}")  # True

# Ma si comportano diversamente in alcune operazioni
print(f"1/+0 = {1.0/zero_positivo}")  # +inf
print(f"1/-0 = {1.0/zero_negativo}")  # -inf
```

### 3.5 Operazioni aritmetiche e loro precisione

Lo standard IEEE 754 definisce come devono essere eseguite le operazioni aritmetiche e garantisce che il risultato sia il più vicino possibile al risultato matematico esatto:

```python
# Dimostrazione della precisione nelle operazioni
def test_precisione_operazioni():
    """
    Testa la precisione delle operazioni aritmetiche base
    """
    a = 1.0
    b = 3.0
    
    # Divisione
    risultato_divisione = a / b
    print(f"1/3 = {risultato_divisione}")
    print(f"1/3 con 20 decimali: {risultato_divisione:.20f}")
    
    # Moltiplicazione che dovrebbe dare 1
    prodotto = risultato_divisione * b
    print(f"(1/3) * 3 = {prodotto}")
    print(f"È esattamente 1? {prodotto == 1.0}")
    
    # Addizione problematica
    piccolo = 1e-16
    grande = 1.0
    somma1 = grande + piccolo
    somma2 = piccolo + grande
    
    print(f"\n1.0 + 1e-16 = {somma1}")
    print(f"1e-16 + 1.0 = {somma2}")
    print(f"Sono uguali? {somma1 == somma2}")

test_precisione_operazioni()
```

**Curiosità 🧠**: L'ordine delle operazioni può influenzare il risultato finale a causa degli errori di arrotondamento!

## 4. Propagazione dell'errore

### 4.1 Come si propagano gli errori nei calcoli
### 4.2 Errore assoluto e errore relativo
### 4.3 Condizionamento di un problema
### 4.4 Stabilità numerica degli algoritmi

## 5. Tecniche per ridurre gli errori

### 5.1 Algoritmi numericamente stabili

Progettare algoritmi numericamente stabili è come costruire case antisismiche 🏠. Non possiamo evitare i "terremoti" (errori di arrotondamento), ma possiamo costruire strutture che li resistano meglio!

**Principi fondamentali:**

1. **Evitare la cancellazione catastrofica**
2. **Minimizzare il numero di operazioni**
3. **Usare formule matematicamente equivalenti ma numericamente diverse**
4. **Controllare l'ordine delle operazioni**

```python
import math
import numpy as np

def esempio_cancellazione_catastrofica():
    """
    Dimostra il problema della cancellazione catastrofica
    e come risolverlo
    """
    print("PROBLEMA: Calcolo di (1 + x) - 1 per x molto piccolo")
    
    x_values = [1e-14, 1e-15, 1e-16]
    
    for x in x_values:
        # Metodo instabile
        risultato_instabile = (1.0 + x) - 1.0
        
        # Metodo stabile (diretto)
        risultato_stabile = x
        
        errore_relativo = abs(risultato_instabile - x) / abs(x) if x != 0 else 0
        
        print(f"x = {x}")
        print(f"  Metodo instabile: {risultato_instabile}")
        print(f"  Metodo stabile: {risultato_stabile}")
        print(f"  Errore relativo: {errore_relativo:.2%}")
        print()

def formula_quadratica_stabile(a, b, c):
    """
    Implementazione stabile della formula quadratica
    """
    discriminante = b*b - 4*a*c
    
    if discriminante < 0:
        return None  # Radici complesse
    
    sqrt_d = math.sqrt(discriminante)
    
    # Evitare cancellazione: calcolare la radice con segno opposto a b
    if b >= 0:
        radice1 = (-b - sqrt_d) / (2*a)
        radice2 = c / (a * radice1)  # Usando la relazione x1*x2 = c/a
    else:
        radice1 = (-b + sqrt_d) / (2*a)
        radice2 = c / (a * radice1)
    
    return radice1, radice2

def somma_kahan(lista_numeri):
    """
    Algoritmo di Kahan per somma compensata
    """
    somma = 0.0
    compensazione = 0.0
    
    for numero in lista_numeri:
        y = numero - compensazione      # Compensazione dell'errore precedente
        temp = somma + y               # Somma temporanea
        compensazione = (temp - somma) - y  # Nuovo errore di arrotondamento
        somma = temp                   # Nuova somma
    
    return somma

# Test degli algoritmi
print("1. CANCELLAZIONE CATASTROFICA:")
esempio_cancellazione_catastrofica()

print("2. FORMULA QUADRATICA STABILE:")
# Equazione con radici molto vicine
a, b, c = 1, 1000001, 1
r1, r2 = formula_quadratica_stabile(a, b, c)
print(f"Radici: {r1}, {r2}")
print(f"Verifica r1: {a*r1**2 + b*r1 + c}")
print(f"Verifica r2: {a*r2**2 + b*r2 + c}")

print("\n3. SOMMA DI KAHAN:")
numeri = [1.0, 1e-8, 1e-8] * 10000  # Molti numeri piccoli
somma_normale = sum(numeri)
somma_compensata = somma_kahan(numeri)
print(f"Somma normale: {somma_normale}")
print(f"Somma compensata: {somma_compensata}")
print(f"Valore teorico: {1.0 * 10000 + 1e-8 * 20000}")
```

### 5.2 Controllo della precisione

Il controllo della precisione è come avere un "termometro" per i nostri calcoli 🌡️. Ci dice quanto possiamo fidarci dei risultati!

**Metodi di controllo:**

```python
import numpy as np
from decimal import Decimal, getcontext

def controllo_convergenza():
    """
    Dimostra tecniche per controllare la convergenza e precisione
    """
    def calcola_pi_leibniz(n_termini):
        """Calcola π usando la serie di Leibniz"""
        pi_approssimato = 0.0
        for k in range(n_termini):
            termine = (-1)**k / (2*k + 1)
            pi_approssimato += termine
        return 4 * pi_approssimato
    
    print("CONTROLLO CONVERGENZA - Calcolo di π:")
    pi_vero = math.pi
    
    for n in [10, 100, 1000, 10000]:
        pi_calc = calcola_pi_leibniz(n)
        errore = abs(pi_calc - pi_vero)
        
        print(f"n={n:5d}: π ≈ {pi_calc:.8f}, errore = {errore:.2e}")
        
        # Criterio di arresto: errore < 10^-6
        if errore < 1e-6:
            print(f"✅ Precisione richiesta raggiunta con {n} termini")
            break

def aritmetica_estesa():
    """
    Dimostra l'uso di aritmetica ad alta precisione
    """
    print("\nARITMETICA AD ALTA PRECISIONE:")
    
    # Impostare precisione decimale
    getcontext().prec = 50
    
    # Calcolo problematico con float normale
    a_float = 1.0 / 3.0
    risultato_float = a_float * 3.0
    
    # Stesso calcolo con Decimal
    a_decimal = Decimal(1) / Decimal(3)
    risultato_decimal = a_decimal * 3
    
    print(f"Float: 1/3 * 3 = {risultato_float}")
    print(f"Decimal: 1/3 * 3 = {risultato_decimal}")
    print(f"Errore float: {abs(risultato_float - 1.0)}")
    print(f"Errore decimal: {abs(float(risultato_decimal) - 1.0)}")

def test_stabilita():
    """
    Test automatico di stabilità numerica
    """
    print("\nTEST DI STABILITÀ:")
    
    def funzione_instabile(x):
        return (math.exp(x) - 1) / x if x != 0 else 1
    
    def funzione_stabile(x):
        """Usando espansione di Taylor per x piccoli"""
        if abs(x) < 1e-8:
            # exp(x) ≈ 1 + x + x²/2 + x³/6 + ...
            # (exp(x) - 1)/x ≈ 1 + x/2 + x²/6 + ...
            return 1 + x/2 + x**2/6 + x**3/24
        else:
            return (math.exp(x) - 1) / x
    
    x_values = [1e-10, 1e-12, 1e-14, 1e-16]
    
    for x in x_values:
        instabile = funzione_instabile(x)
        stabile = funzione_stabile(x)
        teorico = 1.0  # Limite per x→0
        
        print(f"x = {x:.0e}:")
        print(f"  Instabile: {instabile}")
        print(f"  Stabile: {stabile}")
        print(f"  Errore instabile: {abs(instabile - teorico):.2e}")
        print(f"  Errore stabile: {abs(stabile - teorico):.2e}")

# Esecuzione dei test
controllo_convergenza()
aritmetica_estesa()
test_stabilita()
```

### 5.3 Uso di aritmetica estesa

L'aritmetica estesa è come usare una "lente d'ingrandimento" per i numeri 🔍. Ci permette di vedere e lavorare con dettagli che normalmente andrebbero persi!

**Quando usarla:**
- Calcoli che richiedono altissima precisione
- Problemi mal condizionati
- Verifiche di algoritmi numerici
- Calcoli finanziari o scientifici critici

```python
from decimal import Decimal, getcontext
from fractions import Fraction
import mpmath

def confronto_aritmetiche():
    """
    Confronta diverse aritmetiche per calcoli di alta precisione
    """
    print("CONFRONTO ARITMETICHE - Calcolo di 1/7:")
    
    # Float standard (64 bit)
    float_result = 1.0 / 7.0
    print(f"Float (64 bit): {float_result}")
    print(f"Con 20 decimali: {float_result:.20f}")
    
    # Decimal con alta precisione
    getcontext().prec = 50
    decimal_result = Decimal(1) / Decimal(7)
    print(f"Decimal (50 cifre): {decimal_result}")
    
    # Frazione esatta
    fraction_result = Fraction(1, 7)
    print(f"Frazione esatta: {fraction_result}")
    print(f"Frazione decimale: {float(fraction_result):.20f}")
    
    # mpmath (precisione arbitraria)
    mpmath.mp.dps = 50  # 50 cifre decimali
    mpmath_result = mpmath.mpf(1) / mpmath.mpf(7)
    print(f"mpmath (50 cifre): {mpmath_result}")

def calcolo_e_alta_precisione():
    """
    Calcola il numero e con diverse precisioni
    """
    print("\nCALCOLO DI e (numero di Eulero):")
    
    def calcola_e_serie(n_termini, precision=50):
        """Calcola e usando la serie 1 + 1/1! + 1/2! + 1/3! + ..."""
        getcontext().prec = precision
        
        e = Decimal(1)  # Primo termine
        fattoriale = Decimal(1)
        
        for n in range(1, n_termini):
            fattoriale *= n
            e += Decimal(1) / fattoriale
        
        return e
    
    # Confronto con diversi numeri di termini
    e_math = math.e
    
    for n_termini in [10, 20, 50, 100]:
        e_calcolato = calcola_e_serie(n_termini)
        errore = abs(float(e_calcolato) - e_math)
        
        print(f"Termini: {n_termini:3d}, e ≈ {e_calcolato}, errore: {errore:.2e}")

def applicazione_finanziaria():
    """
    Esempio di applicazione finanziaria che richiede alta precisione
    """
    print("\nAPPLICAZIONE FINANZIARIA:")
    print("Calcolo interesse composto per 30 anni")
    
    capitale_iniziale = Decimal('1000000.00')  # 1 milione di euro
    tasso_annuo = Decimal('0.05')  # 5% annuo
    anni = 30
    
    # Calcolo con float normale
    cap_float = 1000000.0
    tasso_float = 0.05
    risultato_float = cap_float * (1 + tasso_float) ** anni
    
    # Calcolo con Decimal
    getcontext().prec = 28  # Precisione per calcoli finanziari
    risultato_decimal = capitale_iniziale * (1 + tasso_annuo) ** anni
    
    print(f"Capitale iniziale: €{capitale_iniziale:,.2f}")
    print(f"Tasso annuo: {tasso_annuo * 100}%")
    print(f"Periodo: {anni} anni")
    print()
    print(f"Risultato float: €{risultato_float:,.2f}")
    print(f"Risultato Decimal: €{risultato_decimal:,.2f}")
    print(f"Differenza: €{abs(float(risultato_decimal) - risultato_float):,.2f}")

# Esecuzione degli esempi
confronto_aritmetiche()
calcolo_e_alta_precisione()
applicazione_finanziaria()
```

**Linee guida per la scelta dell'aritmetica:**

🟢 **Float standard**: Calcoli generali, prestazioni importanti
🟡 **Decimal**: Calcoli finanziari, precisione controllata
🟠 **Fraction**: Calcoli esatti con frazioni
🔴 **mpmath**: Ricerca scientifica, precisione estrema

**Ricorda**: Più precisione = più tempo di calcolo. Scegli saggiamente! ⚖️
### 5.4 Validazione e verifica dei risultati

## 6. Esempi pratici e applicazioni

### 6.1 Esempi di calcoli con errori significativi

I seguenti esempi mostrano come gli errori computazionali possano avere conseguenze reali e concrete nel mondo che ci circonda! 🌍

#### **Caso 1: Il disastro del Patriot (1991)** 💥

Durante la Guerra del Golfo, il sistema di difesa missilistica Patriot non riuscì a intercettare un missile Scud iracheno a causa di un errore di arrotondamento nell'orologio di sistema.

```python
def simulazione_errore_patriot():
    """
    Simula l'errore del sistema Patriot
    """
    print("SIMULAZIONE ERRORE SISTEMA PATRIOT")
    print("="*50)
    
    # Il sistema contava il tempo in decimi di secondo
    # 0.1 non può essere rappresentato esattamente in binario
    
    tempo_teorico = 0.1  # Un decimo di secondo
    
    # Rappresentazione binaria approssimata (24 bit di mantissa)
    # 0.1 in binario è 0.0001100110011... (infinito)
    tempo_approssimato = 0.09999990463256836  # Valore reale memorizzato
    
    ore_operative = 100  # Il sistema era operativo da 100 ore
    decimi_di_secondo = ore_operative * 3600 * 10  # Contatore
    
    errore_per_tick = tempo_teorico - tempo_approssimato
    errore_totale = errore_per_tick * decimi_di_secondo
    
    print(f"Tempo teorico per tick: {tempo_teorico} s")
    print(f"Tempo memorizzato: {tempo_approssimato} s")
    print(f"Errore per tick: {errore_per_tick:.2e} s")
    print(f"Ore operative: {ore_operative} h")
    print(f"Numero di tick: {decimi_di_secondo:,}")
    print(f"ERRORE TOTALE: {errore_totale:.6f} s")
    print(f"Errore in metri (missile a Mach 5): {errore_totale * 1700:.1f} m")
    print()
    print("💀 Risultato: Il missile venne perso dai radar!")
    print("   28 soldati americani persero la vita")

simulazione_errore_patriot()
```

#### **Caso 2: Esplosione del razzo Ariane 5 (1996)** 🚀

Il primo volo del razzo Ariane 5 finì in esplosione dopo 37 secondi a causa di un overflow aritmetico.

```python
def simulazione_ariane5():
    """
    Simula l'errore del razzo Ariane 5
    """
    print("\nSIMULAZIONE ERRORE ARIANE 5")
    print("="*50)
    
    # Il sistema aveva un valore velocità orizzontale che superava
    # il limite di un intero a 16 bit
    
    velocita_vera = 36.7 * 3600  # 36.7 m/s convertiti in unità interne
    print(f"Velocità orizzontale reale: {velocita_vera:.1f} unità interne")
    
    # Limite intero 16 bit con segno: -32768 a +32767
    limite_int16 = 32767
    print(f"Limite intero 16 bit: ±{limite_int16}")
    
    if velocita_vera > limite_int16:
        print("⚠️  OVERFLOW RILEVATO!")
        print(f"Velocità {velocita_vera:.1f} > limite {limite_int16}")
        print()
        print("💥 Risultato: Sistema di navigazione in errore")
        print("   Il razzo si autodistrusse per sicurezza")
        print("   Perdita: 500 milioni di dollari + 4 satelliti")
    
    # Possibile correzione
    print(f"\n✅ Soluzione: Usare intero 32 bit (limite: ±{2**31-1:,})")

simulazione_ariane5()
```

### 6.2 Uso di software per l'analisi degli errori

**Strumenti professionali per l'analisi degli errori:**

```python
import numpy as np
import matplotlib.pyplot as plt

def analisi_propagazione_errori():
    """
    Analizza come si propagano gli errori in una catena di calcoli
    """
    print("\nANALISI PROPAGAZIONE ERRORI")
    print("="*50)
    
    # Simuliamo una catena di calcoli: f(x) = ((x + 1)² - 1) / 2x
    # Matematicamente equivale a f(x) = x + 1/2, ma numericamente diverso!
    
    def funzione_instabile(x):
        return ((x + 1)**2 - 1) / (2 * x) if x != 0 else float('inf')
    
    def funzione_stabile(x):
        return x + 0.5
    
    # Test con valori sempre più piccoli
    x_values = np.logspace(-1, -15, 15)  # Da 0.1 a 10^-15
    errori_relativi = []
    
    for x in x_values:
        risultato_instabile = funzione_instabile(x)
        risultato_stabile = funzione_stabile(x)
        
        if risultato_stabile != 0:
            errore_relativo = abs(risultato_instabile - risultato_stabile) / abs(risultato_stabile)
            errori_relativi.append(errore_relativo)
        else:
            errori_relativi.append(0)
    
    # Visualizzazione degli errori
    print("x\t\tInstabile\tStabile\t\tErrore Rel.")
    print("-" * 60)
    for i, x in enumerate(x_values[:10]):  # Primi 10 valori
        inst = funzione_instabile(x)
        stab = funzione_stabile(x)
        err = errori_relativi[i]
        print(f"{x:.1e}\t{inst:.6f}\t{stab:.6f}\t{err:.2e}")

analisi_propagazione_errori()
```

### 6.3 Casi studio in ambito scientifico e ingegneristico

#### **Caso Studio: Modellazione Climatica** 🌡️

```python
def modello_climatico_semplificato():
    """
    Mostra come gli errori si accumulano nella modellazione climatica
    """
    print("\nMODELLO CLIMATICO SEMPLIFICATO")
    print("="*50)
    
    # Modello semplice: T(t+1) = T(t) + α*CO2(t) - β*T(t)²
    # Dove α e β sono parametri climatici
    
    # Parametri (con incertezza)
    alpha_nominale = 0.01
    beta_nominale = 0.0001
    
    # Incertezza sui parametri (±1%)
    incertezza = 0.01
    
    alpha_min = alpha_nominale * (1 - incertezza)
    alpha_max = alpha_nominale * (1 + incertezza)
    beta_min = beta_nominale * (1 - incertezza)
    beta_max = beta_nominale * (1 + incertezza)
    
    # Condizioni iniziali
    T0 = 15.0  # Temperatura iniziale (°C)
    CO2_0 = 400  # Concentrazione CO2 iniziale (ppm)
    anni = 100
    
    def simula_clima(alpha, beta, anni_sim):
        T = T0
        CO2 = CO2_0
        temperature = [T]
        
        for anno in range(anni_sim):
            # Incremento CO2 (2 ppm/anno)
            CO2 += 2
            # Nuova temperatura
            T = T + alpha * (CO2 - 400) - beta * T**2
            temperature.append(T)
        
        return temperature
    
    # Simulazioni con diversi parametri
    temp_nominale = simula_clima(alpha_nominale, beta_nominale, anni)
    temp_ottimista = simula_clima(alpha_min, beta_max, anni)
    temp_pessimista = simula_clima(alpha_max, beta_min, anni)
    
    print(f"Temperatura iniziale: {T0}°C")
    print(f"CO2 iniziale: {CO2_0} ppm")
    print(f"Simulazione per {anni} anni:")
    print()
    print(f"Scenario nominale: {temp_nominale[-1]:.2f}°C")
    print(f"Scenario ottimista: {temp_ottimista[-1]:.2f}°C") 
    print(f"Scenario pessimista: {temp_pessimista[-1]:.2f}°C")
    print(f"Incertezza finale: ±{abs(temp_pessimista[-1] - temp_ottimista[-1])/2:.2f}°C")
    print()
    print("🔬 Nota: Una piccola incertezza nei parametri (1%)")
    print("   si amplifica significativamente nel tempo!")

modello_climatico_semplificato()
```

**Lezioni apprese dai casi studio:** 🎓

1. **Piccoli errori → Grandi conseguenze**: Gli errori di arrotondamento possono accumularsi pericolosamente
2. **Validazione cruciale**: Testare sempre i sistemi con casi limite
3. **Analisi di sensibilità**: Identificare quali parametri influenzano maggiormente il risultato
4. **Ridondanza**: Usare metodi diversi per verificare i risultati critici

## 7. Esercizi e problemi applicativi

### 🎯 **Livello Base**

#### **Esercizio 1: Identificazione degli errori**
Analizza i seguenti calcoli e identifica il tipo di errore presente:

```python
# A) Calcolo di 1/3
risultato_a = 1.0 / 3.0
print(f"1/3 = {risultato_a}")
print(f"Con 20 decimali: {risultato_a:.20f}")
# Domanda: Che tipo di errore è presente?

# B) Somma di numeri molto diversi
grande = 1.0e16
piccolo = 1.0
somma = grande + piccolo
print(f"{grande} + {piccolo} = {somma}")
print(f"Il risultato è corretto? {somma == grande}")
# Domanda: Perché succede questo?

# C) Sottrazione problematica
x = 1.000000000000001
y = 1.000000000000000
differenza = x - y
print(f"Differenza: {differenza}")
print(f"Differenza attesa: 1e-15")
# Domanda: L'errore relativo è accettabile?
```

**Soluzione guidata:**
- A) _Errore di rappresentazione_ - 1/3 non può essere rappresentato esattamente in binario
- B) _Perdita di precisione_ - Il numero piccolo viene "assorbito" da quello grande
- C) _Cancellazione catastrofica_ - La sottrazione amplifica l'errore relativo

#### **Esercizio 2: Confronto di algoritmi**
Implementa e confronta due versioni della formula quadratica:

```python
import math

def formula_standard(a, b, c):
    """Formula quadratica standard (può essere instabile)"""
    # Implementa: x = (-b ± √(b²-4ac)) / 2a
    pass

def formula_stabile(a, b, c):
    """Formula quadratica numericamente stabile"""
    # Implementa la versione che evita la cancellazione
    pass

# Test con coefficienti che causano problemi
a, b, c = 1, 1000000, 1
print("Testa entrambe le formule e confronta i risultati")
```

### 🎯 **Livello Intermedio**

#### **Esercizio 3: Analisi di convergenza**
Implementa il calcolo di π usando la serie di Leibniz e analizza la convergenza:

```python
def calcola_pi_leibniz(max_termini, tolleranza=1e-6):
    """
    Calcola π usando: π/4 = 1 - 1/3 + 1/5 - 1/7 + ...
    """
    pi_approssimato = 0.0
    segno = 1
    
    for n in range(max_termini):
        termine = segno / (2*n + 1)
        pi_approssimato += termine
        
        # Controlla convergenza ogni 1000 termini
        if n % 1000 == 0:
            pi_corrente = 4 * pi_approssimato
            errore = abs(pi_corrente - math.pi)
            print(f"Termini: {n:6d}, π ≈ {pi_corrente:.8f}, errore: {errore:.2e}")
            
            if errore < tolleranza:
                return pi_corrente, n
        
        segno *= -1
    
    return 4 * pi_approssimato, max_termini

# Domande:
# 1) Quanti termini servono per errore < 10^-6?
# 2) Come varia la velocità di convergenza?
# 3) Esistono serie più efficienti?
```

#### **Esercizio 4: Implementazione dell'algoritmo di Kahan**
Completa l'implementazione e testala:

```python
def somma_kahan_completa(numeri):
    """
    Implementa l'algoritmo di Kahan per somma compensata
    """
    # Da completare seguendo lo pseudocodice:
    # 1. Inizializza somma e compensazione
    # 2. Per ogni numero:
    #    - Calcola il valore compensato
    #    - Aggiorna la somma
    #    - Calcola la nuova compensazione
    pass

# Test con numeri che causano problemi
test_numeri = [1.0] + [1e-16] * 10000
risultato_standard = sum(test_numeri)
risultato_kahan = somma_kahan_completa(test_numeri)

print(f"Somma standard: {risultato_standard}")
print(f"Somma Kahan: {risultato_kahan}")
print(f"Valore teorico: {1.0 + 10000 * 1e-16}")
```

### 🎯 **Livello Avanzato**

#### **Esercizio 5: Analisi di un sistema mal condizionato**
Analizza il sistema di equazioni lineari mal condizionato:

```python
import numpy as np

def sistema_mal_condizionato():
    """
    Analizza la matrice di Hilbert (notoriamente mal condizionata)
    """
    n = 5  # Dimensione del sistema
    
    # Costruisce la matrice di Hilbert: H[i,j] = 1/(i+j+1)
    H = np.zeros((n, n))
    for i in range(n):
        for j in range(n):
            H[i, j] = 1.0 / (i + j + 1)
    
    print("Matrice di Hilbert 5x5:")
    print(H)
    
    # Calcola il numero di condizionamento
    cond_number = np.linalg.cond(H)
    print(f"\nNumero di condizionamento: {cond_number:.2e}")
    
    # Crea un vettore soluzione "vero"
    x_true = np.ones(n)  # Soluzione [1, 1, 1, 1, 1]
    b = H @ x_true       # Termine noto corrispondente
    
    # Risolve il sistema
    x_computed = np.linalg.solve(H, b)
    
    print(f"\nSoluzione vera: {x_true}")
    print(f"Soluzione calcolata: {x_computed}")
    print(f"Errore: {np.linalg.norm(x_computed - x_true):.2e}")
    
    # Test di sensibilità: perturba leggermente b
    perturbazione = 1e-10
    b_perturbato = b + perturbazione * np.random.randn(n)
    x_perturbato = np.linalg.solve(H, b_perturbato)
    
    print(f"\nPerturbazione in b: {np.linalg.norm(b_perturbato - b):.2e}")
    print(f"Variazione in x: {np.linalg.norm(x_perturbato - x_computed):.2e}")
    print(f"Amplificazione: {np.linalg.norm(x_perturbato - x_computed) / np.linalg.norm(b_perturbato - b):.2e}")

# Domande di analisi:
# 1) Cosa succede aumentando n a 10 o 15?
# 2) Come si comporta il condizionamento?
# 3) Esistono tecniche di regolarizzazione?
```

#### **Esercizio 6: Simulazione Monte Carlo degli errori**
Implementa una simulazione per analizzare la propagazione degli errori:

```python
import random
import numpy as np

def simulazione_monte_carlo_errori():
    """
    Simula la propagazione degli errori in un calcolo complesso
    """
    
    def funzione_complessa(x, y, z):
        """
        Funzione di test: f(x,y,z) = (x² + y²)^0.5 / (z + 1)
        """
        return math.sqrt(x**2 + y**2) / (z + 1)
    
    # Valori nominali
    x0, y0, z0 = 3.0, 4.0, 1.0
    
    # Incertezze (deviazioni standard)
    sigma_x, sigma_y, sigma_z = 0.1, 0.1, 0.05
    
    n_simulazioni = 100000
    risultati = []
    
    for _ in range(n_simulazioni):
        # Genera valori casuali con distribuzione normale
        x = random.gauss(x0, sigma_x)
        y = random.gauss(y0, sigma_y)
        z = random.gauss(z0, sigma_z)
        
        # Calcola il risultato
        f_xyz = funzione_complessa(x, y, z)
        risultati.append(f_xyz)
    
    # Analizza i risultati
    risultati = np.array(risultati)
    f_nominale = funzione_complessa(x0, y0, z0)
    
    print(f"Valore nominale: {f_nominale:.6f}")
    print(f"Media simulazione: {np.mean(risultati):.6f}")
    print(f"Deviazione standard: {np.std(risultati):.6f}")
    print(f"Minimo: {np.min(risultati):.6f}")
    print(f"Massimo: {np.max(risultati):.6f}")
    
    # Calcola percentili
    p5 = np.percentile(risultati, 5)
    p95 = np.percentile(risultati, 95)
    print(f"Intervallo 90% confidenza: [{p5:.6f}, {p95:.6f}]")
    
    # Domande:
    # 1) Quale parametro contribuisce di più all'incertezza?
    # 2) La distribuzione è normale?
    # 3) Come varia l'incertezza cambiando le sigma?
```

### 🏆 **Progetti Applicativi**

#### **Progetto 1: Analizzatore di Stabilità Numerica**
Crea un tool che analizza automaticamente la stabilità di una funzione:

```python
def analizzatore_stabilita(funzione, x_test, perturbazioni=[1e-8, 1e-12, 1e-16]):
    """
    Analizza la stabilità numerica di una funzione
    
    Args:
        funzione: La funzione da testare
        x_test: Lista di valori di test
        perturbazioni: Lista delle perturbazioni da testare
    """
    # Implementa:
    # 1) Test con perturbazioni crescenti
    # 2) Calcolo del numero di condizionamento empirico
    # 3) Analisi della propagazione degli errori
    # 4) Report automatico della stabilità
    pass

# Esempio d'uso:
def test_function(x):
    return (x + 1)**2 - 1  # Dovrebbe essere = 2x + x²

risultati = analizzatore_stabilita(test_function, [1e-8, 1e-10, 1e-12])
```

#### **Progetto 2: Simulatore di Errori in Sistemi Reali**
Sviluppa un simulatore che mostra come gli errori computazionali possano influenzare sistemi reali (GPS, controllo volo, calcoli finanziari).

### 🎓 **Domande di Riflessione**

1. **Filosofica**: Se tutti i calcoli hanno errori, come possiamo fidarci dei risultati scientifici?

2. **Pratica**: Quando è accettabile un errore del 1%? E del 0.001%?

3. **Etica**: Chi è responsabile quando un errore computazionale causa danni?

4. **Futuro**: Come cambieranno questi problemi con i computer quantistici?

5. **Metodologica**: È meglio un algoritmo veloce ma meno preciso o uno lento ma accurato?

---

### 📚 **Soluzioni e Suggerimenti**

**Per l'Esercizio 1**: Cerca di eseguire ogni snippet e osserva i risultati. Usa `format(numero, '.20f')` per vedere più decimali.

**Per l'Esercizio 2**: La chiave è evitare la sottrazione di numeri molto vicini. Suggerimento: usa la relazione `x₁ × x₂ = c/a`.

**Per l'Esercizio 3**: La serie di Leibniz converge molto lentamente. Confronta con la serie di Machin o altri metodi più efficaci.

**Per l'Esercizio 5**: Prova con matrici di dimensioni diverse e osserva come cresce il numero di condizionamento.

**Ricorda**: L'obiettivo non è evitare tutti gli errori (impossibile!), ma comprenderli e controllarli! 🎯
