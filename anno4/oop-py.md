# OOP: Programmazione Orientata agli Oggetti in Python

## 🔍 **Modulo 1: Introduzione alla Programmazione Orientata agli Oggetti**

### 1.1 Cos'è la Programmazione Orientata agli Oggetti?

#### 1.1.1 Dal mondo reale al codice

Immaginate di essere nel vostro salotto e di guardarvi intorno: vedete una televisione, un divano, un tavolino, forse una pianta. Ogni oggetto che vedete ha delle caratteristiche specifiche e può fare delle cose particolari. La televisione ha una dimensione, un colore, una marca, e può essere accesa, spenta, cambiare canale. Il divano ha un numero di posti, un colore, un materiale, e può ospitare persone. Questa è esattamente l'idea alla base della programmazione orientata agli oggetti.

La programmazione orientata agli oggetti, o OOP (Object-Oriented Programming), è un modo di pensare e scrivere codice che si ispira proprio a come funziona il mondo reale. Invece di scrivere programmi come una lunga lista di istruzioni che il computer deve eseguire una dopo l'altra, nell'OOP creiamo degli "oggetti software" che rappresentano cose del mondo reale o concetti astratti.

Un aspetto affascinante dell'OOP è che rispecchia naturalmente il modo in cui il nostro cervello organizza le informazioni. Quando pensiamo a un'automobile, automaticamente sappiamo che ha caratteristiche come il colore, la marca, il modello, e che può fare cose come accelerare, frenare, accendersi. In programmazione, questo diventa una "classe Auto" con attributi (colore, marca, modello) e metodi (accelera, frena, accendi).

Questa analogia non è casuale: la programmazione orientata agli oggetti è stata sviluppata proprio per rendere più naturale e intuitiva la scrittura di software complessi. Alan Kay, uno dei pionieri dell'OOP, si ispirò alla biologia cellulare, immaginando programmi come organismi composti da cellule (oggetti) che comunicano tra loro attraverso messaggi.

#### 1.1.2 I vantaggi dell'OOP

La programmazione orientata agli oggetti non è solo un modo elegante di scrivere codice, ma offre vantaggi concreti e misurabili che diventano sempre più evidenti man mano che i progetti crescono in complessità. Il primo grande vantaggio è l'organizzazione del codice. Pensate alla differenza tra una stanza dove tutto è sparso in giro e una dove ogni cosa ha il suo posto: trovare quello che cercate diventa immediatamente più facile.

Nell'OOP, invece di avere centinaia di funzioni sparse che fanno cose diverse, raggruppiamo le funzioni correlate insieme agli dati su cui operano. Se stiamo lavorando con studenti, tutte le funzioni che riguardano gli studenti (calcolare la media, aggiungere voti, stampare informazioni) stanno insieme ai dati dello studente (nome, età, voti). Questa organizzazione rende il codice molto più facile da leggere, capire e modificare.

Il secondo vantaggio fondamentale è il riutilizzo del codice. Una volta che abbiamo creato una classe "Studente" che funziona bene, possiamo utilizzarla in qualsiasi parte del nostro programma, o addirittura in programmi completamente diversi. È come avere un mattoncino Lego perfetto che possiamo usare per costruire case, castelli, o navicelle spaziali. Questo non solo ci fa risparmiare tempo, ma riduce anche la possibilità di errori, perché stiamo riutilizzando codice già testato e funzionante.

Un altro vantaggio cruciale è la manutenibilità. Nel mondo reale del software, i programmi non vengono scritti una volta e poi dimenticati: devono essere aggiornati, corretti, migliorati costantemente. Con l'OOP, se dobbiamo modificare come funziona qualcosa, dobbiamo cambiare il codice solo in un posto. Se, ad esempio, decidiamo di cambiare il modo in cui calcoliamo la media dei voti di uno studente, dobbiamo modificare solo il metodo nella classe Studente, e tutti gli studenti del nostro programma automaticamente useranno il nuovo calcolo.

Infine, l'OOP facilita enormemente il lavoro di squadra. In progetti grandi, dove decine di programmatori lavorano insieme, ognuno può concentrarsi su un insieme specifico di classi senza interferire con il lavoro degli altri. È come un'orchestra dove ogni musicista suona il suo strumento: il violinista non deve preoccuparsi di come il pianista produca i suoi suoni, deve solo assicurarsi di suonare al momento giusto e in armonia con gli altri.


### 1.2 OOP vs Programmazione Procedurale

### 1.2 OOP vs Programmazione Procedurale

La programmazione procedurale organizza il codice come sequenza di funzioni che operano su dati separati. L'OOP raggruppa dati e funzioni in oggetti che interagiscono, facilitando comprensione e manutenzione del codice.

#### Esempio: Triangolo Rettangolo

**Approccio Procedurale:**
```python
import math

def calcola_ipotenusa(cateto1, cateto2):
    return math.sqrt(cateto1**2 + cateto2**2)

def calcola_perimetro(cateto1, cateto2, ipotenusa):
    return cateto1 + cateto2 + ipotenusa

def calcola_area(cateto1, cateto2):
    return (cateto1 * cateto2) / 2

# Utilizzo
cateto_a = 3
cateto_b = 4
ipotenusa = calcola_ipotenusa(cateto_a, cateto_b)
perimetro = calcola_perimetro(cateto_a, cateto_b, ipotenusa)
area = calcola_area(cateto_a, cateto_b)

print(f"Ipotenusa: {ipotenusa}, Perimetro: {perimetro}, Area: {area}")
```

**Approccio Orientato agli Oggetti:**
```python
import math

class TriangoloRettangolo:
    def __init__(self, cateto1, cateto2):
        self.cateto1 = cateto1
        self.cateto2 = cateto2
    
    def calcola_ipotenusa(self):
        return math.sqrt(self.cateto1**2 + self.cateto2**2)
    
    def calcola_perimetro(self):
        ipotenusa = self.calcola_ipotenusa()
        return self.cateto1 + self.cateto2 + ipotenusa
    
    def calcola_area(self):
        return (self.cateto1 * self.cateto2) / 2
    
    def __str__(self):
        return f"Triangolo({self.cateto1}, {self.cateto2}) - Ipotenusa: {self.calcola_ipotenusa():.2f}"

# Utilizzo
triangolo = TriangoloRettangolo(3, 4)
print(f"Ipotenusa: {triangolo.calcola_ipotenusa()}")
print(f"Perimetro: {triangolo.calcola_perimetro()}")
print(f"Area: {triangolo.calcola_area()}")
print(triangolo)
```

**Differenze principali:**
- **Procedurale**: Dati e funzioni separati, passaggio manuale di parametri
- **OOP**: Dati e comportamenti unificati nell'oggetto, maggiore chiarezza e riusabilità


### 1.3 Classi, oggetti e istanze

#### 1.3.1 La differenza tra classe e oggetto

Per capire la differenza tra classe e oggetto, immaginate di essere in una fabbrica di automobili. Prima di produrre un'auto, i progettisti creano un **progetto dettagliato** che specifica tutto: dove vanno le ruote, la forma della carrozzeria, la posizione del motore, i colori disponibili. Questo progetto è come una **classe** in programmazione.

Una **classe** è essenzialmente un "progetto" o un "modello" che descrive come dovranno essere fatti gli oggetti. È come il disegno tecnico dell'automobile: definisce le caratteristiche che avrà (colore, numero di porte, cilindrata) e le azioni che potrà compiere (accelerare, frenare, accendere le luci), ma non è ancora un'automobile vera e propria.

Un **oggetto**, invece, è come l'automobile fisica che esce dalla catena di montaggio: è una realizzazione concreta del progetto. Dall'stesso progetto di automobile, la fabbrica può produrre migliaia di auto diverse: una rossa con interni in pelle, una blu con interni in tessuto, una bianca con tetto apribile. Ogni automobile è un oggetto diverso, ma tutte seguono lo stesso progetto (la classe).

Una cosa importante da capire è che la classe esiste solo nel codice, come un'idea o un progetto. Gli oggetti, invece, esistono quando il programma viene eseguito e occupano spazio nella memoria del computer.

#### 1.3.2 Il concetto di istanza

Quando creiamo un oggetto da una classe, diciamo che stiamo **istanziando** la classe, e l'oggetto risultante si chiama **istanza** della classe. È un po' come quando ordinate una pizza: il menu (la classe) descrive tutti i tipi di pizza disponibili, ma quando ne ordinate una, ricevete un'istanza specifica di quella pizza.

Ogni istanza è completamente indipendente dalle altre. Se Mario accelera la sua auto, questo non influenza la velocità dell'auto di Sara. È come avere due radio sintonizzate sullo stesso programma: se alzate il volume di una, l'altra rimane al volume precedente.

Pensate a una classe "Studente": può descrivere che tutti gli studenti hanno un nome, un'età, una classe di appartenenza e possono studiare o riposare. Ma quando create specifiche istanze come Alice, Bob e Clara, ognuno di loro avrà i propri valori per nome ed età, e se Alice studia e si stanca, questo non influenza l'energia di Bob o Clara.

#### 1.3.3 Attributi e metodi di istanza

Ogni istanza ha le sue **variabili di istanza** (chiamate anche attributi) che memorizzano informazioni specifiche per quell'oggetto. Nel nostro esempio degli studenti, ogni studente ha il suo nome, la sua età, i suoi voti. Queste informazioni sono personali per ogni istanza.

I **metodi** sono le azioni che ogni istanza può compiere. Tutti gli studenti possono studiare e riposare, ma quando Alice studia, influenza solo la sua energia, non quella di Bob o Clara.

Pensate agli attributi come ai "dati personali" di ogni oggetto, e ai metodi come alle "abilità" che ogni oggetto possiede. È come se ogni studente avesse un diario personale (gli attributi) e sapesse fare certe cose (i metodi), ma il contenuto del diario e le azioni sono specifiche per ognuno.

Immaginate uno zaino: ogni zaino ha il suo colore, la sua capacità massima e il suo peso attuale (attributi), e tutti gli zaini possono fare le stesse azioni come aggiungere oggetti, rimuovere oggetti o mostrare il contenuto (metodi). Ma ogni zaino mantiene i suoi oggetti separatamente: aggiungere un libro allo zaino della scuola non influenza il contenuto dello zaino dello sport.

#### 1.3.4 Analogia finale: La ricetta e i dolci

Per riassumere tutti questi concetti, immaginate di avere una **ricetta per i biscotti**. La ricetta è come la **classe**: descrive gli ingredienti necessari (attributi) e i passaggi da seguire (metodi), ma non è un biscotto vero.

Ogni volta che seguite la ricetta e fate una infornata, create dei **biscotti concreti** (oggetti o istanze). Ogni biscotto ha le sue caratteristiche specifiche: uno potrebbe essere leggermente più scuro, un altro più rotondo, ma tutti seguono la stessa ricetta base.

Se fate tre infornade diverse in momenti diversi, avrete tre gruppi di biscotti completamente indipendenti. Mangiare un biscotto della prima infornata non influenza quelli della seconda infornata.

Questa è esattamente la relazione tra classi e oggetti in programmazione: una classe è il modello, gli oggetti sono le realizzazioni concrete di quel modello, e ogni oggetto vive la sua vita indipendente dagli altri. La classe definisce cosa può fare un biscotto (cuocere, essere mangiato) e quali caratteristiche ha (forma, gusto, livello di cottura), ma ogni biscotto specifico mantiene il suo stato personale indipendentemente dagli altri.

**🤔 Domande di Verifica - Modulo 1**

1. Immaginatevi di dover modellare un sistema per gestire una scuola. Identificate almeno tre classi che potreste creare e spiegate come potrebbero essere collegate attraverso l'ereditarietà.

2. Confrontate i vantaggi e gli svantaggi della programmazione procedurale rispetto a quella orientata agli oggetti. In quali situazioni preferireste l'una o l'altra?

3. Pensate a un'applicazione che usate spesso (come WhatsApp, Instagram, o un videogioco). Come pensate che sia organizzata internamente? Quali potrebbero essere alcune delle classi principali?

## 🏗️ **Modulo 2: Classi e Oggetti in Python**

### 2.1 Creazione di Classi

#### 2.1.1 Sintassi e esempio pratico

Creare una classe in Python è come disegnare il progetto di una casa: definiamo la struttura che useremo per costruire oggetti simili. La sintassi inizia con `class` seguito dal nome (in PascalCase), e il metodo `__init__` funge da costruttore. Il parametro `self` rappresenta l'istanza dell'oggetto su cui operiamo. Possiamo avere attributi di classe (condivisi) e attributi di istanza (specifici per ogni oggetto), mentre i metodi definiscono le azioni che l'oggetto può compiere.

```python
class Studente:
    # Attributo di classe condiviso da tutti gli studenti
    scuola = "Liceo Scientifico Galilei"
    
    def __init__(self, nome, eta, classe):
        # Attributi di istanza specifici per ogni studente
        self.nome = nome
        self.eta = eta
        self.classe = classe
        self.voti = []
    
    def aggiungi_voto(self, voto):
        if 0 <= voto <= 10:
            self.voti.append(voto)
            print(f"Voto {voto} aggiunto per {self.nome}")
        else:
            print("Errore: il voto deve essere tra 0 e 10")
    
    def calcola_media(self):
        if len(self.voti) > 0:
            return sum(self.voti) / len(self.voti)
        else:
            return 0
    
    def presenta(self):
        media = self.calcola_media()
        return f"Ciao, sono {self.nome}, ho {self.eta} anni, frequento la {self.classe} e la mia media è {media:.2f}"
```

L'esempio mostra come l'incapsulamento protegga i dati (validazione del voto), come i metodi operino sui dati dell'oggetto (calcolo della media), e come gestiamo casi limite per rendere il codice robusto.

### 2.2 Creazione e Utilizzo di Oggetti

#### 2.2.1 Istanziazione di oggetti

Creare un oggetto da una classe è come utilizzare il progetto della casa per costruire finalmente una casa vera. In terminologia tecnica, questo processo si chiama "istanziazione": stiamo creando un'istanza (un esempio specifico) della nostra classe. È un momento magico in cui il modello astratto diventa qualcosa di concreto e utilizzabile.

La sintassi per creare un oggetto è sorprendentemente semplice: scriviamo il nome della classe seguito dalle parentesi, dentro le quali mettiamo i parametri richiesti dal costruttore. Quello che succede dietro le quinte è che Python crea automaticamente un nuovo oggetto, chiama il metodo `__init__` per inizializzarlo con i parametri che abbiamo fornito, e poi ci restituisce un riferimento a questo nuovo oggetto.

```python
# Creazione di diversi studenti
marco = Studente("Marco Rossi", 17, "4A")
sara = Studente("Sara Bianchi", 16, "3B")
luca = Studente("Luca Verdi", 18, "5C")

# Ogni oggetto è indipendente e ha i suoi dati
print(marco.nome)  # Output: Marco Rossi
print(sara.eta)    # Output: 16
print(luca.classe) # Output: 5C
```

Una cosa affascinante da capire è che ogni oggetto che creiamo è completamente indipendente dagli altri. Anche se `marco`, `sara` e `luca` sono tutti studenti creati dalla stessa classe, ognuno ha la sua memoria separata e i suoi dati specifici. È come avere tre case costruite dallo stesso progetto: possono sembrare simili dall'esterno, ma ognuna ha i suoi mobili, i suoi abitanti, la sua storia.

Possiamo interagire con ogni oggetto chiamando i suoi metodi. Quando scriviamo `marco.aggiungi_voto(8)`, stiamo dicendo all'oggetto `marco` di eseguire il metodo `aggiungi_voto` con il parametro 8. Python automaticamente passa `marco` come parametro `self` al metodo, così il metodo sa su quale oggetto specifico deve operare.

La bellezza di questo sistema è che possiamo avere lo stesso metodo che si comporta diversamente su oggetti diversi, a seconda dei dati che ogni oggetto contiene. Se chiamiamo `calcola_media()` su `marco` che ha voti [8, 7, 9] e su `sara` che ha voti [6, 8, 7], otterremo risultati diversi anche se il metodo è identico.

#### 2.2.2 Accesso agli attributi

Accedere agli attributi di un oggetto in Python è come aprire i cassetti di un mobile per vedere cosa c'è dentro. Usiamo la notazione punto (`oggetto.attributo`) per "raggiungere" i dati che ci interessano. Questa sintassi è così naturale che spesso non ci rendiamo conto di quanto sia potente: stiamo navigando nella struttura dati dell'oggetto come se stessimo esplorando le stanze di una casa.

Python ci dà una libertà notevole nell'accesso agli attributi. Possiamo non solo leggere i valori, ma anche modificarli direttamente. Questo è allo stesso tempo una grande potenza e una grande responsabilità. È come avere le chiavi di tutte le stanze della casa: possiamo andare ovunque vogliamo, ma dobbiamo stare attenti a non rompere nulla.

```python
# Lettura degli attributi
print(f"Nome dello studente: {marco.nome}")
print(f"Età: {marco.eta}")
print(f"Classe: {marco.classe}")
print(f"Scuola: {marco.scuola}")  # Attributo di classe

# Modifica degli attributi
marco.eta = 18  # Marco ha compiuto gli anni!
marco.nome = "Marco Rossi"  # Aggiustiamo il nome completo

# Possiamo anche aggiungere nuovi attributi al volo (sconsigliato!)
marco.hobby = "calcio"
```

Una caratteristica interessante di Python è che possiamo aggiungere attributi a un oggetto anche dopo averlo creato. Questo è molto flessibile, ma può anche portare a codice confuso e difficile da mantenere. È come decidere di aggiungere una stanza a una casa dopo averla costruita: tecnicamente possibile, ma non sempre una buona idea.

Gli attributi di classe meritano un'attenzione speciale. Quando accediamo a `marco.scuola`, Python prima controlla se `marco` ha un attributo di istanza chiamato `scuola`. Se non lo trova, risale alla classe e cerca un attributo di classe con quel nome. Questo meccanismo ci permette di avere valori condivisi tra tutti gli oggetti di una classe, ma anche di permettere a singoli oggetti di avere valori diversi se necessario.


### 2.4 Esercitazione Pratica: Classe ContoBancario

#### 2.4.1 Implementazione

Per consolidare tutto quello che abbiamo imparato, sviluppiamo insieme un esempio più complesso: una classe per gestire un conto bancario. Questo esempio ci permetterà di vedere come tutti i concetti che abbiamo studiato si combinano per creare qualcosa di utile e realistico.

Un conto bancario ha caratteristiche ben definite: un intestatario, un saldo, e una storia delle transazioni. Le operazioni che possiamo fare sono altrettanto chiare: depositare denaro, prelevare denaro, consultare il saldo, e vedere la storia delle transazioni. L'aspetto interessante è che dobbiamo anche gestire regole di business: non possiamo prelevare più di quanto abbiamo, non possiamo depositare importi negativi, e dobbiamo tenere traccia di tutto quello che succede.

```python
from datetime import datetime

class ContoBancario:
    def __init__(self, intestatario, saldo_iniziale=0):
        self.intestatario = intestatario
        self.saldo = saldo_iniziale
        self.transazioni = []
        self._aggiungi_transazione(f"Apertura conto con saldo iniziale di {saldo_iniziale}€")
    
    def _aggiungi_transazione(self, descrizione):
        # Metodo privato per aggiungere una transazione
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        self.transazioni.append(f"[{timestamp}] {descrizione}")
    
    def deposita(self, importo):
        if importo <= 0:
            print("Errore: l'importo deve essere positivo")
            return False
        
        self.saldo += importo
        self._aggiungi_transazione(f"Deposito di {importo}€ - Nuovo saldo: {self.saldo}€")
        print(f"Depositati {importo}€. Saldo attuale: {self.saldo}€")
        return True
    
    def preleva(self, importo):
        if importo <= 0:
            print("Errore: l'importo deve essere positivo")
            return False
        
        if importo > self.saldo:
            print(f"Errore: saldo insufficiente. Saldo attuale: {self.saldo}€")
            return False
        
        self.saldo -= importo
        self._aggiungi_transazione(f"Prelievo di {importo}€ - Nuovo saldo: {self.saldo}€")
        print(f"Prelevati {importo}€. Saldo attuale: {self.saldo}€")
        return True
    
    def consulta_saldo(self):
        return self.saldo
    
    def stampa_estratto_conto(self):
        print(f"\n=== ESTRATTO CONTO - {self.intestatario} ===")
        print(f"Saldo attuale: {self.saldo}€")
        print("\nStorico transazioni:")
        for transazione in self.transazioni:
            print(transazione)
        print("=" * 50)
    
    def __str__(self):
        return f"Conto di {self.intestatario} - Saldo: {self.saldo}€"
    
    def __len__(self):
        return len(self.transazioni)
```

Questo esempio illustra molti principi importanti dell'OOP. Prima di tutto, notate l'uso del metodo `_aggiungi_transazione`: il nome inizia con un underscore, che in Python è una convenzione per indicare che si tratta di un metodo "privato", cioè pensato per uso interno alla classe. Non è veramente privato (Python non ha la privacy forzata), ma il nome suggerisce che non dovrebbe essere chiamato dall'esterno.

La gestione degli errori è un altro aspetto cruciale. Invece di permettere operazioni non valide che potrebbero corrompere i dati, la classe controlla ogni operazione e rifiuta quelle che non rispettano le regole. Questo è l'incapsulamento in azione: proteggiamo l'integrità dei nostri dati fornendo interfacce controllate per interagire con essi.

L'uso del modulo `datetime` mostra come le classi Python possono facilmente integrarsi con la ricca libreria standard del linguaggio. Ogni transazione viene etichettata con un timestamp preciso, rendendo possibile ricostruire esattamente cosa è successo e quando.

**🤔 Domande di Verifica - Modulo 2**

1. Spiegate la differenza tra attributi di classe e attributi di istanza. Quando usereste l'uno o l'altro?

2. Perché il parametro `self` è necessario in tutti i metodi di una classe? Cosa rappresenta esattamente?

3. Implementate una classe `Libro` che abbia attributi titolo, autore e anno di pubblicazione.

4. Nel nostro esempio del `ContoBancario`, perché abbiamo scelto di fare controlli sui parametri nei metodi `deposita` e `preleva` invece di permettere qualsiasi operazione?

5. Immaginate di dover aggiungere un limite di scoperto al conto bancario. Come modifichereste la classe per permettere prelievi fino a -500€?

6. Progettate una classe `Biblioteca` che possa contenere una lista di libri. Quali metodi speciali implementereste e perché?

## 🔗 **Modulo 3: Ereditarietà e Polimorfismo**

### 3.1 Ereditarietà (Inheritance)

#### 3.1.1 Concetti base dell'ereditarietà

L'ereditarietà è uno dei pilastri più potenti della programmazione orientata agli oggetti, un meccanismo che ci permette di creare nuove classi basandoci su classi esistenti. Pensate all'ereditarietà come al processo biologico: un figlio eredita caratteristiche dai genitori ma può anche sviluppare caratteristiche proprie uniche. Allo stesso modo, una classe "figlia" eredita attributi e metodi dalla classe "madre" ma può aggiungere funzionalità specifiche o modificare comportamenti esistenti.

Immaginate di progettare un sistema per una scuola. Potreste iniziare con una classe generale `Persona` che ha attributi comuni come nome, età, e codice fiscale. Da questa classe base, potreste derivare classi più specifiche come `Studente`, `Professore`, e `Personale`. Ogni classe specializzata mantiene le caratteristiche base di una persona ma aggiunge elementi specifici: uno studente ha voti e classe di appartenenza, un professore ha materie insegnate e anni di esperienza.

L'ereditarietà risolve uno dei problemi più fastidiosi della programmazione: la duplicazione del codice. Senza ereditarietà, dovreste riscrivere gli stessi metodi per gestire nome ed età in ogni classe. Con l'ereditarietà, scrivete questi metodi una volta nella classe base e tutte le classi derivate li ereditano automaticamente. È come avere una ricetta di base per la pasta che potete modificare per creare carbonara, amatriciana, o cacio e pepe senza riscrivere ogni volta i passaggi fondamentali.

Python implementa l'ereditarietà con una sintassi elegante e potente. Quando definite una classe, potete specificare da quale classe "eredita" mettendo il nome della classe padre tra parentesi. La classe figlia avrà automaticamente accesso a tutti i metodi e attributi pubblici della classe padre, come se li aveste scritti direttamente nella classe figlia.

Una caratteristica fondamentale dell'ereditarietà è la relazione "è-un" che crea tra le classi. Un `Studente` È UNA `Persona`, un `ProfessoreDiMatematica` È UN `Professore` che È UNA `Persona`. Questa relazione non è solo concettuale: significa che ovunque nel vostro codice potete usare un oggetto della classe figlia al posto di un oggetto della classe padre, perché la classe figlia ha tutte le capacità della classe padre (e anche qualcosa in più).

#### 3.1.2 Utilizzo dell'ereditarietà

Per capire veramente come funziona l'ereditarietà, costruiamo un esempio pratico partendo da una classe base `Persona` e sviluppando classi specializzate. Questo esempio vi mostrerà non solo la sintassi, ma anche le strategie per progettare gerarchie di classi efficaci.

```python
# Classe base
class Persona:
    def __init__(self, nome, cognome, eta):
        self.nome = nome
        self.cognome = cognome
        self.eta = eta
        self.email = f"{nome.lower()}.{cognome.lower()}@scuola.it"
    
    def presenta(self):
        return f"Ciao, sono {self.nome} {self.cognome}, ho {self.eta} anni"
    
    def compie_anni(self):
        self.eta += 1
        print(f"{self.nome} ha compiuto {self.eta} anni! 🎂")
    
    def aggiorna_email(self, nuova_email):
        self.email = nuova_email
        print(f"Email aggiornata per {self.nome}: {self.email}")

# Classe derivata per gli studenti
class Studente(Persona):
    def __init__(self, nome, cognome, eta, classe, anno_iscrizione):
        # Chiamiamo il costruttore della classe padre
        super().__init__(nome, cognome, eta)
        self.classe = classe
        self.anno_iscrizione = anno_iscrizione
        self.voti = {}  # Dizionario: materia -> lista di voti
        self.assenze = 0
    
    def aggiungi_voto(self, materia, voto):
        if materia not in self.voti:
            self.voti[materia] = []
        self.voti[materia].append(voto)
        print(f"Voto {voto} aggiunto in {materia} per {self.nome}")
    
    def media_materia(self, materia):
        if materia in self.voti and len(self.voti[materia]) > 0:
            return sum(self.voti[materia]) / len(self.voti[materia])
        return 0
    
    def media_generale(self):
        if not self.voti:
            return 0
        
        somma_medie = 0
        contatore_materie = 0
        for materia in self.voti:
            media_materia = self.media_materia(materia)
            if media_materia > 0:
                somma_medie += media_materia
                contatore_materie += 1
        
        return somma_medie / contatore_materie if contatore_materie > 0 else 0
    
    def presenta(self):  # Override del metodo del padre
        presentazione_base = super().presenta()
        return f"{presentazione_base}. Studio in classe {self.classe}"
    
    def studia(self, materia, ore):
        print(f"{self.nome} ha studiato {materia} per {ore} ore")
        if ore >= 2:
            print("Ottimo impegno! 📚")

# Classe derivata per i professori
class Professore(Persona):
    def __init__(self, nome, cognome, eta, materie_insegnate, anni_esperienza):
        super().__init__(nome, cognome, eta)
        self.materie_insegnate = materie_insegnate
        self.anni_esperienza = anni_esperienza
        self.classi_assegnate = []
    
    def assegna_classe(self, classe):
        if classe not in self.classi_assegnate:
            self.classi_assegnate.append(classe)
            print(f"Prof. {self.cognome} ora insegna anche alla classe {classe}")
    
    def valuta_studente(self, studente, materia, voto):
        if materia in self.materie_insegnate:
            studente.aggiungi_voto(materia, voto)
            print(f"Prof. {self.cognome} ha valutato {studente.nome}")
        else:
            print(f"Prof. {self.cognome} non può valutare in {materia}")
    
    def presenta(self):
        presentazione_base = super().presenta()
        materie = ", ".join(self.materie_insegnate)
        return f"{presentazione_base}. Insegno {materie} da {self.anni_esperienza} anni"

# Esempio di utilizzo
if __name__ == "__main__":
    # Creazione di oggetti
    mario = Studente("Mario", "Rossi", 16, "3A", 2021)
    prof_bianchi = Professore("Laura", "Bianchi", 45, ["Matematica", "Fisica"], 15)
    
    # Utilizzo dei metodi ereditati
    print(mario.presenta())
    print(prof_bianchi.presenta())
    
    # Utilizzo dei metodi specifici
    mario.studia("Matematica", 3)
    prof_bianchi.valuta_studente(mario, "Matematica", 8)
    
    print(f"Media di Mario in Matematica: {mario.media_materia('Matematica'):.2f}")
```

Questo esempio illustra diversi aspetti cruciali dell'ereditarietà. La funzione `super()` è il meccanismo che ci permette di chiamare metodi della classe padre. È particolarmente importante nel costruttore: `super().__init__()` assicura che l'oggetto sia inizializzato correttamente secondo le regole della classe padre prima di aggiungere le inizializzazioni specifiche della classe figlia.

L'override dei metodi è un'altra caratteristica fondamentale. Quando ridefinite un metodo nella classe figlia con lo stesso nome di un metodo nella classe padre, state dicendo "voglio che questo metodo si comporti diversamente per questa classe specifica". Nel nostro esempio, sia `Studente` che `Professore` hanno una loro versione del metodo `presenta()`, più specifica di quella generica della classe `Persona`.

### 3.2 Polimorfismo

#### 3.2.1 Polimorfismo tramite ereditarietà

Il polimorfismo è un concetto che inizialmente può sembrare astratto, ma che in realtà utilizziamo costantemente nella vita quotidiana. La parola "polimorfismo" deriva dal greco e significa "molte forme": è la capacità di oggetti diversi di rispondere allo stesso "comando" in modi appropriati alla loro natura specifica. Pensate a quando suonate il campanello di case diverse: il suono sarà diverso per ogni casa, ma il gesto è lo stesso.

Nella programmazione orientata agli oggetti, il polimorfismo ci permette di scrivere codice che può lavorare con oggetti di classi diverse, purché questi oggetti condividano una interfaccia comune (cioè abbiano metodi con gli stessi nomi). È incredibilmente potente perché ci permette di scrivere codice generico che non deve conoscere i dettagli specifici degli oggetti con cui lavora.

Il polimorfismo tramite ereditarietà funziona perché tutte le classi figlie ereditano i metodi della classe padre, ma possono ridefinirli (fare override) per comportarsi in modo specifico. Il risultato è che possiamo chiamare lo stesso metodo su oggetti di classi diverse e ottenere comportamenti appropriati per ogni classe.

```python
# Esempi di polimorfismo con la nostra gerarchia Persona
def organizza_riunione(partecipanti):
    """
    Funzione che dimostra il polimorfismo:
    può lavorare con qualsiasi tipo di Persona
    """
    print("🏫 RIUNIONE SCOLASTICA")
    print("=" * 40)
    
    for persona in partecipanti:
        # Stesso metodo, comportamenti diversi!
        print(f"• {persona.presenta()}")
    
    print("\nTutti i partecipanti si sono presentati! 👥")

def invia_email_gruppo(persone, messaggio):
    """
    Altra dimostrazione di polimorfismo:
    tutti hanno l'attributo email ereditato da Persona
    """
    print(f"\n📧 Invio email: '{messaggio}'")
    for persona in persone:
        print(f"   → {persona.email}")

# Creazione di un gruppo misto
gruppo_scuola = [
    Studente("Anna", "Verdi", 17, "4B", 2020),
    Professore("Marco", "Neri", 38, ["Storia", "Geografia"], 8),
    Studente("Luca", "Blu", 16, "3A", 2021),
    Professore("Sara", "Gialli", 42, ["Italiano", "Latino"], 12)
]

# Il polimorfismo in azione!
organizza_riunione(gruppo_scuola)
invia_email_gruppo(gruppo_scuola, "Riunione genitori il 15 maggio")
```

Quello che rende magico questo esempio è che la funzione `organizza_riunione()` non sa e non ha bisogno di sapere se sta lavorando con studenti o professori. Tutto quello che le serve è che ogni oggetto abbia un metodo `presenta()`. Quando chiama `persona.presenta()`, Python automaticamente esegue la versione corretta del metodo: quella di `Studente` per gli studenti, quella di `Professore` per i professori.

Questo è il cuore del polimorfismo: stesso codice, comportamenti diversi a seconda del tipo di oggetto. È come avere un telecomando universale che funziona con dispositivi diversi: premete il pulsante "accendi" e ogni dispositivo si accende nel modo appropriato.

#### 3.2.2 Duck Typing in Python

Python ha una filosofia unica riguardo al polimorfismo che si riassume nel principio del "Duck Typing": "Se cammina come un'anatra, nuota come un'anatra e fa qua qua come un'anatra, allora probabilmente è un'anatra". Questo significa che in Python non è necessario che due classi condividano la stessa gerarchia di ereditarietà per essere usate polimorficamente: basta che abbiano i metodi giusti con i nomi giusti.

Questa filosofia rende Python incredibilmente flessibile e naturale da usare. Non dovete per forza progettare gerarchie di classi complesse: se avete classi che fanno cose simili, potete spesso usarle insieme anche se non sono imparentate.

```python
# Classi completamente indipendenti (nessuna ereditarietà)
class Robot:
    def __init__(self, nome, modello):
        self.nome = nome
        self.modello = modello
    
    def presenta(self):
        return f"Sono {self.nome}, un robot modello {self.modello} 🤖"
    
    def lavora(self):
        print(f"{self.nome} sta eseguendo le sue funzioni robotiche")

class Animale:
    def __init__(self, nome, specie):
        self.nome = nome
        self.specie = specie
    
    def presenta(self):
        return f"Sono {self.nome}, un {self.specie} 🐾"
    
    def lavora(self):
        print(f"{self.nome} sta aiutando come animale da assistenza")

# Classe che usa il Duck Typing
class Scuola:
    def __init__(self):
        self.membri = []
    
    def aggiungi_membro(self, membro):
        # Non controlliamo il tipo, solo che abbia i metodi necessari
        if hasattr(membro, 'presenta') and hasattr(membro, 'lavora'):
            self.membri.append(membro)
            print(f"✅ {membro.nome} aggiunto alla scuola")
        else:
            print("❌ Questo membro non ha le capacità richieste")
    
    def presentazione_generale(self):
        print("\n🎭 PRESENTAZIONE GENERALE DELLA SCUOLA")
        print("=" * 50)
        for membro in self.membri:
            print(f"• {membro.presenta()}")
    
    def giornata_lavorativa(self):
        print("\n💼 INIZIA LA GIORNATA LAVORATIVA")
        print("-" * 30)
        for membro in self.membri:
            membro.lavora()

# Dimostrazione del Duck Typing
scuola = Scuola()

# Aggiungiamo membri di tipi completamente diversi
scuola.aggiungi_membro(Studente("Elena", "Rossi", 15, "2C", 2022))
scuola.aggiungi_membro(Professore("Giorgio", "Bianchi", 50, ["Scienze"], 20))
scuola.aggiungi_membro(Robot("R2D2", "Assistente Didattico"))
scuola.aggiungi_membro(Animale("Rex", "Cane guida"))

# Tutto funziona perfettamente insieme!
scuola.presentazione_generale()
scuola.giornata_lavorativa()

# Esempio di cosa succede se proviamo ad aggiungere qualcosa senza i metodi giusti
class OggettoSbagliato:
    def __init__(self, nome):
        self.nome = nome

oggetto = OggettoSbagliato("Qualcosa")
scuola.aggiungi_membro(oggetto)  # Questo fallirà
```

Il Duck Typing è una delle caratteristiche che rendono Python così potente e flessibile. Vi permette di combinare classi che non erano state progettate per lavorare insieme, purché abbiano le interfacce giuste. È come scoprire che il vostro telecomando della TV funziona anche con il decoder via cavo: non erano stati progettati insieme, ma usano gli stessi "comandi".

### 3.3 Ereditarietà Multipla e MRO

#### 3.3.1 Ereditarietà multipla

L'ereditarietà multipla è una caratteristica avanzata di Python che permette a una classe di ereditare da più classi padre contemporaneamente. È come avere genitori con competenze diverse: potreste ereditare la creatività da un genitore e la logica dall'altro. Tuttavia, questa potenza viene con responsabilità: l'ereditarietà multipla può creare situazioni complesse che richiedono attenzione.

Python gestisce l'ereditarietà multipla attraverso un algoritmo chiamato MRO (Method Resolution Order), che determina in quale ordine cercare i metodi quando una classe eredita da più genitori. Questo meccanismo assicura che ogni classe venga visitata una sola volta e che l'ordine sia coerente e prevedibile.

```python
# Classi base con funzionalità diverse
class Comunicatore:
    def __init__(self):
        self.lingue = ["Italiano"]
    
    def parla(self, messaggio):
        print(f"💬 Dice: {messaggio}")
    
    def impara_lingua(self, lingua):
        if lingua not in self.lingue:
            self.lingue.append(lingua)
            print(f"📚 Ha imparato {lingua}")

class Atleta:
    def __init__(self):
        self.sport = []
        self.forma_fisica = 100
    
    def allena(self, sport):
        if sport not in self.sport:
            self.sport.append(sport)
        self.forma_fisica = min(100, self.forma_fisica + 5)
        print(f"🏃 Si è allenato in {sport}. Forma fisica: {self.forma_fisica}")
    
    def gareggia(self, sport):
        if sport in self.sport:
            print(f"🏆 Gareggia in {sport} con ottimi risultati!")
        else:
            print(f"❌ Non può gareggiare in {sport}, non è allenato")

class Musicista:
    def __init__(self):
        self.strumenti = []
        self.brani_conosciuti = []
    
    def impara_strumento(self, strumento):
        if strumento not in self.strumenti:
            self.strumenti.append(strumento)
            print(f"🎵 Ha imparato a suonare {strumento}")
    
    def compone(self, titolo_brano):
        self.brani_conosciuti.append(titolo_brano)
        print(f"🎼 Ha composto '{titolo_brano}'")
    
    def esibisce(self):
        if self.strumenti and self.brani_conosciuti:
            strumento = self.strumenti[0]
            brano = self.brani_conosciuti[-1]
            print(f"🎭 Si esibisce con {strumento} suonando '{brano}'")

# Classe con ereditarietà multipla
class StudenteCompleto(Persona, Comunicatore, Atleta, Musicista):
    def __init__(self, nome, cognome, eta, classe):
        # Inizializziamo tutte le classi padre
        Persona.__init__(self, nome, cognome, eta)
        Comunicatore.__init__(self)
        Atleta.__init__(self)
        Musicista.__init__(self)
        
        self.classe = classe
        self.talenti = []
    
    def scopri_talento(self, area):
        """Metodo che unifica le diverse capacità ereditate"""
        if area == "lingue":
            print(f"🌟 {self.nome} mostra talento nelle lingue!")
            self.impara_lingua("Inglese")
            self.talenti.append("Poliglotta")
        
        elif area == "sport":
            print(f"🌟 {self.nome} mostra talento sportivo!")
            self.allena("Calcio")
            self.talenti.append("Atleta")
        
        elif area == "musica":
            print(f"🌟 {self.nome} mostra talento musicale!")
            self.impara_strumento("Pianoforte")
            self.compone("La mia prima melodia")
            self.talenti.append("Musicista")
    
    def giornata_tipo(self):
        """Dimostra come un oggetto possa usare capacità da più classi padre"""
        print(f"\n📅 GIORNATA TIPO DI {self.nome.upper()}")
        print("-" * 40)
        
        self.parla("Buongiorno a tutti!")
        
        if "Atleta" in self.talenti:
            self.allena("Calcio")
        
        if "Musicista" in self.talenti:
            self.esibisce()
        
        if "Poliglotta" in self.talenti:
            print(f"🗣️ Parla {len(self.lingue)} lingue: {', '.join(self.lingue)}")
    
    def presenta(self):
        presentazione_base = super().presenta()
        talenti_str = ", ".join(self.talenti) if self.talenti else "Ancora da scoprire"
        return f"{presentazione_base}. Talenti: {talenti_str}"

# Dimostrazione dell'ereditarietà multipla
if __name__ == "__main__":
    # Creazione di uno studente con capacità multiple
    alex = StudenteCompleto("Alessandro", "Verdi", 17, "4A")
    
    print("🎯 SCOPERTA DEI TALENTI")
    print("=" * 30)
    alex.scopri_talento("lingue")
    alex.scopri_talento("sport")
    alex.scopri_talento("musica")
    
    print(f"\n{alex.presenta()}")
    
    alex.giornata_tipo()
    
    # Vediamo il Method Resolution Order
    print(f"\n🔍 MRO di StudenteCompleto:")
    for i, classe in enumerate(StudenteCompleto.__mro__):
        print(f"   {i+1}. {classe.__name__}")
```

Questo esempio mostra come l'ereditarietà multipla permetta di combinare funzionalità da diverse fonti in modo elegante. La classe `StudenteCompleto` ha accesso a tutti i metodi di tutte le classi padre, creando un oggetto incredibilmente versatile.

Il Method Resolution Order (MRO) che vedete stampato alla fine mostra l'ordine in cui Python cerca i metodi. Questo ordine è determinato dall'algoritmo C3 linearization, che assicura che:
1. Una classe viene sempre cercata prima delle sue classi padre
2. L'ordine relativo delle classi padre viene mantenuto
3. Ogni classe viene visitata una sola volta

### 3.4 Esercitazione: Sistema di Veicoli

#### 3.4.1 Implementazione completa

Per consolidare tutti i concetti di ereditarietà e polimorfismo che abbiamo studiato, sviluppiamo un sistema completo per la gestione di diversi tipi di veicoli. Questo progetto ci permetterà di vedere come progettare una gerarchia di classi efficace e come il polimorfismo renda il codice elegante e flessibile.

```python
from datetime import datetime
import math

# Classe base per tutti i veicoli
class Veicolo:
    """Classe base che definisce le caratteristiche comuni di tutti i veicoli"""
    
    def __init__(self, marca, modello, anno, prezzo):
        self.marca = marca
        self.modello = modello
        self.anno = anno
        self.prezzo = prezzo
        self._chilometraggio = 0
        self._acceso = False
        self._carburante_litri = 0
        self._consumo_per_km = 0.1  # Valore base, verrà modificato nelle sottoclassi
    
    def accendi(self):
        if not self._acceso:
            self._acceso = True
            print(f"🔥 {self.marca} {self.modello} acceso!")
            return True
        else:
            print(f"⚠️ {self.marca} {self.modello} è già acceso")
            return False
    
    def spegni(self):
        if self._acceso:
            self._acceso = False
            print(f"🔴 {self.marca} {self.modello} spento!")
            return True
        else:
            print(f"⚠️ {self.marca} {self.modello} è già spento")
            return False
    
    def rifornisci(self, litri):
        """Metodo base per il rifornimento - sarà personalizzato nelle sottoclassi"""
        self._carburante_litri += litri
        print(f"⛽ Rifornimento: +{litri}L. Totale: {self._carburante_litri}L")
    
    def guida(self, chilometri):
        """Metodo polimorfic - comportamento base che può essere personalizzato"""
        if not self._acceso:
            print("❌ Non puoi guidare un veicolo spento!")
            return False
        
        carburante_necessario = chilometri * self._consumo_per_km
        if carburante_necessario > self._carburante_litri:
            print(f"❌ Carburante insufficiente! Servono {carburante_necessario:.1f}L")
            return False
        
        self._chilometraggio += chilometri
        self._carburante_litri -= carburante_necessario
        print(f"🛣️ Percorsi {chilometri}km. Consumo: {carburante_necessario:.1f}L")
        return True
    
    def eta_veicolo(self):
        anno_corrente = datetime.now().year
        return anno_corrente - self.anno
    
    def valore_attuale(self):
        """Calcola il valore attuale considerando l'età e il chilometraggio"""
        eta = self.eta_veicolo()
        deprezzamento_eta = 0.1 * eta  # 10% all'anno
        deprezzamento_km = 0.001 * self._chilometraggio  # 0.1% ogni 100km
        fattore_deprezzamento = 1 - min(0.8, deprezzamento_eta + deprezzamento_km)
        return self.prezzo * fattore_deprezzamento
    
    def __str__(self):
        stato = "🟢 acceso" if self._acceso else "🔴 spento"
        return f"{self.marca} {self.modello} ({self.anno}) - {self._chilometraggio}km - {stato}"

# Sottoclasse per automobili
class Automobile(Veicolo):
    def __init__(self, marca, modello, anno, prezzo, numero_porte, tipo_cambio):
        super().__init__(marca, modello, anno, prezzo)
        self.numero_porte = numero_porte
        self.tipo_cambio = tipo_cambio
        self._consumo_per_km = 0.08  # Le auto consumano meno
        self._capacita_serbatoio = 60
        self._aria_condizionata = False
    
    def rifornisci(self, litri):
        litri_effettivi = min(litri, self._capacita_serbatoio - self._carburante_litri)
        super().rifornisci(litri_effettivi)
        if litri_effettivi < litri:
            print(f"⚠️ Serbatoio pieno! Non sono entrati {litri - litri_effettivi}L")
    
    def attiva_aria_condizionata(self):
        if self._acceso:
            self._aria_condizionata = True
            self._consumo_per_km = 0.1  # Aumenta il consumo
            print("❄️ Aria condizionata attivata - viaggio confortevole!")
        else:
            print("❌ Accendi l'auto prima di usare l'aria condizionata")
    
    def parcheggia(self):
        if self._acceso:
            print(f"🅿️ {self.marca} {self.modello} parcheggiata")
            return self.spegni()
        else:
            print("⚠️ L'auto è già parcheggiata")
            return True

class Motocicletta(Veicolo):
    def __init__(self, marca, modello, anno, prezzo, cilindrata, tipo_moto):
        super().__init__(marca, modello, anno, prezzo)
        self.cilindrata = cilindrata
        self.tipo_moto = tipo_moto  # "sportiva", "cruiser", "touring"
        self._consumo_per_km = 0.04  # Le moto consumano poco
        self._capacita_serbatoio = 20
    
    def impennata(self):
        if not self._acceso:
            print("❌ Non puoi fare impennate con la moto spenta!")
            return False
        
        if self.tipo_moto == "sportiva" and self._chilometraggio > 1000:
            print(f"🏍️ Impennata spettacolare con la {self.marca} {self.modello}! 🔥")
            return True
        elif self.tipo_moto != "sportiva":
            print(f"⚠️ La {self.tipo_moto} non è adatta per le impennate")
            return False
        else:
            print("⚠️ Troppo pochi km per rischiare un'impennata!")
            return False
    
    def guida(self, chilometri):
        # Override per aggiungere bonus di agilità
        if super().guida(chilometri):
            if self.tipo_moto == "sportiva":
                bonus_km = chilometri * 0.1  # 10% di distanza bonus per agilità
                print(f"🏁 Bonus agilità moto sportiva: +{bonus_km:.1f}km equivalenti!")
            return True
        return False

class Camion(Veicolo):
    def __init__(self, marca, modello, anno, prezzo, capacita_carico_tonnellate):
        super().__init__(marca, modello, anno, prezzo)
        self.capacita_carico = capacita_carico_tonnellate
        self._carico_attuale = 0
        self._consumo_per_km = 0.25  # I camion consumano molto
        self._capacita_serbatoio = 300
    
    def carica(self, peso_tonnellate):
        if self._carico_attuale + peso_tonnellate <= self.capacita_carico:
            self._carico_attuale += peso_tonnellate
            # Il carico aumenta il consumo
            self._consumo_per_km = 0.25 + (0.05 * (self._carico_attuale / self.capacita_carico))
            print(f"📦 Caricati {peso_tonnellate}t. Totale: {self._carico_attuale}t/{self.capacita_carico}t")
            return True
        else:
            print(f"❌ Impossibile caricare {peso_tonnellate}t. Capacità insufficiente!")
            return False
    
    def scarica(self, peso_tonnellate=None):
        if peso_tonnellate is None:
            peso_tonnellate = self._carico_attuale
        
        if peso_tonnellate <= self._carico_attuale:
            self._carico_attuale -= peso_tonnellate
            # Ricalcola il consumo
            self._consumo_per_km = 0.25 + (0.05 * (self._carico_attuale / self.capacita_carico))
            print(f"📤 Scaricati {peso_tonnellate}t. Rimanenti: {self._carico_attuale}t")
            return True
        else:
            print("❌ Non puoi scaricare più di quanto caricato!")
            return False

# Classe per gestire una flotta di veicoli
class FlottaVeicoli:
    def __init__(self, nome_azienda):
        self.nome_azienda = nome_azienda
        self.veicoli = []
        self.km_totali = 0
    
    def aggiungi_veicolo(self, veicolo):
        self.veicoli.append(veicolo)
        print(f"✅ {veicolo.marca} {veicolo.modello} aggiunto alla flotta {self.nome_azienda}")
    
    def accendi_tutti(self):
        print(f"\n🚀 ACCENSIONE FLOTTA {self.nome_azienda.upper()}")
        print("-" * 50)
        for veicolo in self.veicoli:
            veicolo.accendi()
    
    def rifornimento_completo(self):
        print(f"\n⛽ RIFORNIMENTO COMPLETO FLOTTA")
        print("-" * 40)
        for veicolo in self.veicoli:
            # Polimorfismo: ogni veicolo gestisce il rifornimento a modo suo
            if isinstance(veicolo, Automobile):
                veicolo.rifornisci(60)
            elif isinstance(veicolo, Motocicletta):
                veicolo.rifornisci(20)
            elif isinstance(veicolo, Camion):
                veicolo.rifornisci(300)
    
    def viaggio_flotta(self, destinazione, chilometri):
        print(f"\n🛣️ VIAGGIO VERSO {destinazione.upper()} ({chilometri}km)")
        print("-" * 50)
        veicoli_arrivati = 0
        
        for veicolo in self.veicoli:
            if veicolo.guida(chilometri):
                veicoli_arrivati += 1
                self.km_totali += chilometri
        
        print(f"\n✅ {veicoli_arrivati}/{len(self.veicoli)} veicoli sono arrivati a destinazione")
        return veicoli_arrivati
    
    def report_flotta(self):
        print(f"\n📊 REPORT FLOTTA {self.nome_azienda.upper()}")
        print("=" * 60)
        
        valore_totale = 0
        for i, veicolo in enumerate(self.veicoli, 1):
            valore = veicolo.valore_attuale()
            valore_totale += valore
            print(f"{i}. {veicolo}")
            print(f"   💰 Valore attuale: €{valore:,.2f}")
            print(f"   📅 Età: {veicolo.eta_veicolo()} anni")
        
        print(f"\n💰 VALORE TOTALE FLOTTA: €{valore_totale:,.2f}")
        print(f"🛣️ CHILOMETRAGGIO TOTALE AZIENDALE: {self.km_totali}km")

# Dimostrazione completa del sistema
if __name__ == "__main__":
    # Creazione della flotta
    flotta = FlottaVeicoli("TrasportiExpress")
    
    # Aggiunta di veicoli diversi
    auto1 = Automobile("Toyota", "Corolla", 2020, 25000, 4, "automatico")
    auto2 = Automobile("BMW", "X3", 2019, 45000, 5, "automatico")
    moto1 = Motocicletta("Ducati", "Panigale", 2021, 18000, 1199, "sportiva")
    moto2 = Motocicletta("Harley", "Iron 883", 2018, 12000, 883, "cruiser")
    camion1 = Camion("Volvo", "FH16", 2017, 80000, 25)
    
    # Aggiungiamo tutti alla flotta
    for veicolo in [auto1, auto2, moto1, moto2, camion1]:
        flotta.aggiungi_veicolo(veicolo)
    
    # Test delle funzionalità
    flotta.accendi_tutti()
    flotta.rifornimento_completo()
    
    # Prepariamo il camion
    camion1.carica(15)
    
    # Test delle funzionalità specifiche
    auto1.attiva_aria_condizionata()
    moto1.impennata()  # Troppo pochi km!
    
    # Viaggi della flotta (polimorfismo in azione!)
    flotta.viaggio_flotta("Milano", 150)
    
    # Ora la moto può fare l'impennata
    moto1.impennata()
    
    # Altro viaggio
    flotta.viaggio_flotta("Roma", 300)
    
    # Report finale
    flotta.report_flotta()
```

Questo sistema completo dimostra tutti i principi dell'OOP in azione. L'ereditarietà ci permette di evitare duplicazioni mantenendo il codice DRY (Don't Repeat Yourself). Il polimorfismo rende la classe `FlottaVeicoli` semplice e flessibile: può gestire qualsiasi tipo di veicolo senza dover sapere i dettagli specifici di ognuno.

**🤔 Domande di Verifica - Modulo 3**

1. Spiegate la differenza tra override e overload di un metodo. Python supporta entrambi?

2. Nel nostro esempio della flotta, perché il metodo `guida()` è implementato nella classe base `Veicolo` ma viene personalizzato in `Motocicletta`?

3. Come funziona il Duck Typing? Fornite un esempio pratico diverso da quelli visti.

4. Quali sono i vantaggi e gli svantaggi dell'ereditarietà multipla? Quando la usereste?

5. Progettate una gerarchia di classi per un sistema di gestione di una biblioteca multimediale (libri, DVD, audiolibri). Quali metodi dovrebbero essere polimorfici?

6. Nel sistema dei veicoli, come implementereste una classe `VeicoloElettrico` che eredita da `Automobile` ma ha un sistema di "rifornimento" diverso?

## 🚀 **Modulo 4: Progetto Pratico e Best Practices**

### 4.1 Progetto: Sistema di Gestione Biblioteca

#### 4.1.1 Analisi del problema

Prima di iniziare a scrivere codice, ogni buon programmatore orientato agli oggetti deve fermarsi e analizzare il problema che deve risolvere. Il processo di analisi è come quello di un architetto che studia il terreno prima di progettare una casa: dobbiamo capire cosa ci serve, come le parti si relazionano tra loro, e quali sono i casi limite che dobbiamo gestire.

Il nostro progetto consiste nel creare un sistema per gestire una biblioteca moderna. Una biblioteca oggi non gestisce solo libri: ci sono DVD, audiolibri, riviste, e risorse digitali. Gli utenti possono essere studenti, docenti, o cittadini comuni, ognuno con privilegi diversi. Dobbiamo gestire prestiti, restituzioni, prenotazioni, e multe per i ritardi.

Iniziamo identificando le "entità" principali del nostro sistema: cosa sono le "cose" di cui dobbiamo tenere traccia? Abbiamo chiaramente i **materiali** (libri, DVD, etc.), gli **utenti** (persone che usano la biblioteca), e i **prestiti** (il legame tra un utente e un materiale per un periodo di tempo). Ogni entità avrà caratteristiche (attributi) e azioni che può compiere (metodi).

Poi pensiamo alle relazioni: un utente può avere più prestiti attivi, un materiale può essere prestato a un solo utente alla volta, un prestito collega un utente specifico a un materiale specifico per un periodo determinato. Queste relazioni ci aiuteranno a progettare come le nostre classi interagiranno.

Infine, identifichiamo le regole di business: quanto tempo può tenere un libro uno studente vs un docente? Cosa succede se qualcuno non restituisce in tempo? Si possono prenotare materiali già prestati? Queste regole diventeranno la logica all'interno dei nostri metodi, l'intelligenza che rende il sistema utile e non solo una collezione di dati.

Una considerazione importante è l'estensibilità: il nostro sistema dovrebbe essere facile da modificare ed estendere. Se domani la biblioteca decide di aggiungere strumenti musicali o attrezzature informatiche, non dovremmo dover riscrivere tutto da capo. Questo è dove l'OOP dimostra la sua vera potenza: classi ben progettate rendono facile aggiungere nuove funzionalità.

#### 4.1.2 Classe Libro

Iniziamo con la classe più fondamentale del nostro sistema: `Libro`. Un libro ha caratteristiche fisiche (titolo, autore, ISBN) e caratteristiche di stato (è disponibile? è prenotato? è danneggiato?). Ha anche azioni che può "subire": essere prestato, restituito, prenotato, segnalato come danneggiato.

```python
from datetime import datetime, timedelta
from enum import Enum

class StatoMateriale(Enum):
    DISPONIBILE = "disponibile"
    PRESTATO = "prestato"
    PRENOTATO = "prenotato"
    MANUTENZIONE = "manutenzione"
    PERSO = "perso"

class MaterialeBiblioteca:
    """Classe base per tutti i materiali della biblioteca"""
    
    def __init__(self, codice, titolo, autore, anno_pubblicazione, genere):
        self.codice = codice  # Codice univoco identificativo
        self.titolo = titolo
        self.autore = autore
        self.anno_pubblicazione = anno_pubblicazione
        self.genere = genere
        self.stato = StatoMateriale.DISPONIBILE
        self.data_ultimo_prestito = None
        self.numero_prestiti = 0
        self.note = []
    
    def è_disponibile(self):
        return self.stato == StatoMateriale.DISPONIBILE
    
    def è_prestato(self):
        return self.stato == StatoMateriale.PRESTATO
    
    def aggiungi_nota(self, nota):
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M")
        self.note.append(f"[{timestamp}] {nota}")
        print(f"📝 Nota aggiunta a '{self.titolo}': {nota}")
    
    def cambia_stato(self, nuovo_stato, motivo=""):
        stato_precedente = self.stato
        self.stato = nuovo_stato
        
        if motivo:
            self.aggiungi_nota(f"Stato cambiato da {stato_precedente.value} a {nuovo_stato.value}: {motivo}")
        
        print(f"🔄 '{self.titolo}' ora è: {nuovo_stato.value}")
    
    def __str__(self):
        return f"📖 {self.titolo} - {self.autore} [{self.stato.value}]"

class Libro(MaterialeBiblioteca):
    def __init__(self, codice, titolo, autore, anno_pubblicazione, genere, isbn, numero_pagine, editore):
        super().__init__(codice, titolo, autore, anno_pubblicazione, genere)
        self.isbn = isbn
        self.numero_pagine = numero_pagine
        self.editore = editore
        self.durata_prestito_base = 14  # giorni
    
    def è_volume_grosso(self):
        return self.numero_pagine > 500
    
    def durata_prestito_suggerita(self, tipo_utente):
        """Calcola la durata del prestito basata sul tipo di utente e caratteristiche del libro"""
        durata_base = self.durata_prestito_base
        
        if tipo_utente == "docente":
            durata_base *= 2  # I docenti possono tenere i libri il doppio
        
        if self.è_volume_grosso():
            durata_base += 7  # Una settimana extra per libri grossi
        
        if self.genere.lower() in ["manuale", "testo universitario", "tecnico"]:
            durata_base += 14  # Due settimane extra per testi di studio
        
        return durata_base
    
    def __str__(self):
        emoji = "📚" if self.è_volume_grosso() else "📖"
        return f"{emoji} {self.titolo} - {self.autore} ({self.numero_pagine}p) [{self.stato.value}]"

class DVD(MaterialeBiblioteca):
    def __init__(self, codice, titolo, regista, anno_pubblicazione, genere, durata_minuti, sottotitoli_italiano=True):
        super().__init__(codice, titolo, regista, anno_pubblicazione, genere)
        self.regista = regista  # Per i DVD, "autore" è il regista
        self.durata_minuti = durata_minuti
        self.sottotitoli_italiano = sottotitoli_italiano
        self.durata_prestito_base = 7  # I DVD si prestano per meno tempo
    
    def durata_prestito_suggerita(self, tipo_utente):
        durata_base = self.durata_prestito_base
        
        if tipo_utente == "docente":
            durata_base *= 2
        
        return durata_base
    
    def __str__(self):
        durata_ore = self.durata_minuti // 60
        durata_min = self.durata_minuti % 60
        return f"🎬 {self.titolo} - {self.regista} ({durata_ore}h{durata_min}m) [{self.stato.value}]"

class AudioLibro(MaterialeBiblioteca):
    def __init__(self, codice, titolo, autore, anno_pubblicazione, genere, narratore, durata_ore, formato):
        super().__init__(codice, titolo, autore, anno_pubblicazione, genere)
        self.narratore = narratore
        self.durata_ore = durata_ore
        self.formato = formato  # "CD", "digitale"
        self.durata_prestito_base = 21  # Gli audiolibri richiedono più tempo
    
    def durata_prestito_suggerita(self, tipo_utente):
        durata_base = self.durata_prestito_base
        
        if tipo_utente == "docente":
            durata_base *= 1.5  # Bonus più contenuto per audiolibri
        
        if self.durata_ore > 10:
            durata_base += 7  # Tempo extra per audiolibri lunghi
        
        return int(durata_base)
    
    def __str__(self):
        return f"🎧 {self.titolo} - {self.autore} (narrato da {self.narratore}, {self.durata_ore}h) [{self.stato.value}]"
```

Questa struttura gerarchica mostra come l'ereditarietà ci permette di condividere funzionalità comuni (tutti i materiali hanno un stato, possono essere prestati, hanno note) mentre permettendo specializzazioni (ogni tipo ha caratteristiche uniche e regole diverse per i prestiti).

#### 4.1.3 Classe Utente

Gli utenti della biblioteca sono l'altro protagonista del nostro sistema. Anche qui usiamo l'ereditarietà per gestire tipi diversi di utenti con privilegi e limitazioni diverse.

```python
from datetime import datetime, timedelta

class TipoUtente(Enum):
    STUDENTE = "studente"
    DOCENTE = "docente"
    CITTADINO = "cittadino"
    STAFF = "staff"

class Utente:
    """Classe base per tutti gli utenti della biblioteca"""
    
    def __init__(self, codice_utente, nome, cognome, email, telefono, tipo_utente):
        self.codice_utente = codice_utente
        self.nome = nome
        self.cognome = cognome
        self.email = email
        self.telefono = telefono
        self.tipo_utente = tipo_utente
        self.data_iscrizione = datetime.now()
        self.prestiti_attivi = []
        self.storico_prestiti = []
        self.multe_attive = []
        self.note_comportamento = []
        self._limite_prestiti = self._calcola_limite_prestiti()
        self._giorni_massimi_prestito = self._calcola_giorni_massimi()
    
    def _calcola_limite_prestiti(self):
        """Calcola il numero massimo di prestiti contemporanei"""
        limiti = {
            TipoUtente.STUDENTE: 3,
            TipoUtente.DOCENTE: 10,
            TipoUtente.CITTADINO: 2,
            TipoUtente.STAFF: 5
        }
        return limiti.get(self.tipo_utente, 2)
    
    def _calcola_giorni_massimi(self):
        """Calcola il numero massimo di giorni per un prestito"""
        giorni = {
            TipoUtente.STUDENTE: 30,
            TipoUtente.DOCENTE: 60,
            TipoUtente.CITTADINO: 21,
            TipoUtente.STAFF: 45
        }
        return giorni.get(self.tipo_utente, 21)
    
    def può_prestare(self, materiale):
        """Controlla se l'utente può prendere in prestito il materiale"""
        # Troppi prestiti attivi?
        if len(self.prestiti_attivi) >= self._limite_prestiti:
            return False, f"Limite prestiti raggiunto ({self._limite_prestiti})"
        
        # Ha multe non pagate?
        if self.multe_attive:
            multe_scadute = [m for m in self.multe_attive if m.è_scaduta()]
            if multe_scadute:
                return False, "Hai multe scadute non pagate"
        
        # Il materiale è disponibile?
        if not materiale.è_disponibile():
            return False, f"Materiale non disponibile: {materiale.stato.value}"
        
        return True, "OK"
    
    def aggiungi_nota_comportamento(self, nota):
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M")
        self.note_comportamento.append(f"[{timestamp}] {nota}")
        print(f"📋 Nota comportamento per {self.nome}: {nota}")
    
    def calcola_reputazione(self):
        """Calcola un punteggio di reputazione basato sul comportamento"""
        punteggio_base = 100
        
        # Penalità per multe
        punteggio_base -= len(self.multe_attive) * 10
        
        # Penalità per ritardi negli ultimi 6 mesi
        sei_mesi_fa = datetime.now() - timedelta(days=180)
        ritardi_recenti = sum(1 for prestito in self.storico_prestiti 
                            if prestito.data_fine and prestito.data_fine > sei_mesi_fa 
                            and prestito.giorni_ritardo() > 0)
        punteggio_base -= ritardi_recenti * 5
        
        # Bonus per prestiti senza problemi
        prestiti_perfetti = sum(1 for prestito in self.storico_prestiti 
                              if prestito.data_fine and prestito.giorni_ritardo() == 0)
        punteggio_base += min(prestiti_perfetti * 2, 50)  # Max 50 punti bonus
        
        return max(0, min(100, punteggio_base))
    
    def __str__(self):
        reputazione = self.calcola_reputazione()
        emoji_reputazione = "⭐" if reputazione >= 90 else "🟢" if reputazione >= 70 else "🟡" if reputazione >= 50 else "🔴"
        return f"{emoji_reputazione} {self.nome} {self.cognome} ({self.tipo_utente.value}) - {len(self.prestiti_attivi)} prestiti attivi"

class Studente(Utente):
    def __init__(self, codice_utente, nome, cognome, email, telefono, corso_di_studio, anno_corso):
        super().__init__(codice_utente, nome, cognome, email, telefono, TipoUtente.STUDENTE)
        self.corso_di_studio = corso_di_studio
        self.anno_corso = anno_corso
        self.può_accedere_risorse_avanzate = anno_corso >= 3  # Solo dal 3° anno
    
    def ha_diritto_proroga(self):
        """Gli studenti possono chiedere una proroga se hanno buona reputazione"""
        return self.calcola_reputazione() >= 80 and len(self.multe_attive) == 0

class Docente(Utente):
    def __init__(self, codice_utente, nome, cognome, email, telefono, dipartimento, materie_insegnate):
        super().__init__(codice_utente, nome, cognome, email, telefono, TipoUtente.DOCENTE)
        self.dipartimento = dipartimento
        self.materie_insegnate = materie_insegnate
        self.può_prenotare_aula_studio = True
        self.può_accedere_archivio_storico = True
    
    def richiedi_materiale_per_corso(self, materiale, nome_corso):
        """I docenti possono richiedere materiali specifici per i loro corsi"""
        nota = f"Richiesto per il corso: {nome_corso}"
        materiale.aggiungi_nota(nota)
        print(f"📚 Prof. {self.cognome} ha richiesto '{materiale.titolo}' per {nome_corso}")

class Cittadino(Utente):
    def __init__(self, codice_utente, nome, cognome, email, telefono, professione=""):
        super().__init__(codice_utente, nome, cognome, email, telefono, TipoUtente.CITTADINO)
        self.professione = professione
        self.può_accedere_solo_base = True  # Limitazioni per alcuni materiali
```

La struttura gerarchica degli utenti dimostra come l'OOP ci permetta di specializzare comportamenti mantenendo codice condiviso. Ogni tipo di utente ha le stesse funzionalità di base ma con parametri e privilegi diversi.

#### 4.1.4 Classe Biblioteca

La classe `Biblioteca` è il "direttore d'orchestra" del nostro sistema. Coordina tutte le operazioni, gestisce le regole di business, e mantiene la coerenza dei dati.

```python
from datetime import datetime, timedelta
import random

class Multa:
    def __init__(self, utente, importo, motivo, data_scadenza=None):
        self.utente = utente
        self.importo = importo
        self.motivo = motivo
        self.data_creazione = datetime.now()
        self.data_scadenza = data_scadenza or (datetime.now() + timedelta(days=30))
        self.pagata = False
    
    def è_scaduta(self):
        return not self.pagata and datetime.now() > self.data_scadenza
    
    def paga(self):
        self.pagata = True
        self.utente.multe_attive = [m for m in self.utente.multe_attive if m != self]
        print(f"💰 Multa di €{self.importo} pagata da {self.utente.nome}")

class Prestito:
    def __init__(self, utente, materiale, bibliotecario, durata_giorni=None):
        self.utente = utente
        self.materiale = materiale
        self.bibliotecario = bibliotecario
        self.data_inizio = datetime.now()
        
        # Calcola la durata basata sul tipo di materiale e utente
        if durata_giorni is None:
            durata_giorni = materiale.durata_prestito_suggerita(utente.tipo_utente.value)
        
        self.durata_prevista = durata_giorni
        self.data_scadenza = self.data_inizio + timedelta(days=durata_giorni)
        self.data_fine = None  # Sarà impostata alla restituzione
        self.proroghe = 0
        self.note_prestito = []
    
    def è_in_ritardo(self):
        return datetime.now() > self.data_scadenza and self.data_fine is None
    
    def giorni_ritardo(self):
        if self.data_fine:
            # Prestito già restituito
            return max(0, (self.data_fine - self.data_scadenza).days)
        else:
            # Prestito ancora attivo
            return max(0, (datetime.now() - self.data_scadenza).days)
    
    def può_essere_prorogato(self):
        return (self.proroghe < 2 and 
                not self.è_in_ritardo() and 
                self.materiale.stato == StatoMateriale.PRESTATO)
    
    def proroga(self, giorni_extra=7):
        if self.può_essere_prorogato():
            self.data_scadenza += timedelta(days=giorni_extra)
            self.proroghe += 1
            nota = f"Proroga #{self.proroghe} di {giorni_extra} giorni"
            self.note_prestito.append(f"[{datetime.now().strftime('%Y-%m-%d')}] {nota}")
            print(f"📅 {nota} per '{self.materiale.titolo}'")
            return True
        return False
    
    def __str__(self):
        stato = "🔴 IN RITARDO" if self.è_in_ritardo() else "🟢 Attivo" if not self.data_fine else "✅ Restituito"
        return f"{stato} | {self.materiale.titolo} → {self.utente.nome} (scade: {self.data_scadenza.strftime('%d/%m/%Y')})"

class SistemaBiblioteca:
    def __init__(self, nome_biblioteca, indirizzo=""):
        self.nome_biblioteca = nome_biblioteca
        self.indirizzo = indirizzo
        self.catalogo = {}  # codice_materiale -> MaterialeBiblioteca
        self.utenti = {}    # codice_utente -> Utente
        self.prestiti_attivi = []
        self.storico_prestiti = []
        self.prenotazioni = []
        self.statistiche = {
            'prestiti_totali': 0,
            'materiali_più_richiesti': {},
            'utenti_più_attivi': {},
        }
    
    def aggiungi_materiale(self, materiale):
        """Aggiunge un materiale al catalogo"""
        if materiale.codice in self.catalogo:
            print(f"❌ Materiale con codice {materiale.codice} già presente!")
            return False
        
        self.catalogo[materiale.codice] = materiale
        print(f"✅ Aggiunto al catalogo: {materiale}")
        return True
    
    def registra_utente(self, utente):
        """Registra un nuovo utente"""
        if utente.codice_utente in self.utenti:
            print(f"❌ Utente con codice {utente.codice_utente} già registrato!")
            return False
        
        self.utenti[utente.codice_utente] = utente
        print(f"✅ Utente registrato: {utente}")
        return True
    
    def cerca_materiali(self, termine_ricerca, filtro_tipo=None, solo_disponibili=False):
        """Cerca materiali nel catalogo"""
        risultati = []
        termine_lower = termine_ricerca.lower()
        
        for materiale in self.catalogo.values():
            # Controllo se il termine è nel titolo o autore
            match_titolo = termine_lower in materiale.titolo.lower()
            match_autore = termine_lower in materiale.autore.lower()
            
            if match_titolo or match_autore:
                # Filtro per tipo se specificato
                if filtro_tipo and not isinstance(materiale, filtro_tipo):
                    continue
                
                # Filtro per disponibilità se richiesto
                if solo_disponibili and not materiale.è_disponibile():
                    continue
                
                risultati.append(materiale)
        
        return risultati
    
    def presta_materiale(self, codice_materiale, codice_utente, bibliotecario="Sistema"):
        """Gestisce il prestito di un materiale"""
        # Verifica esistenza materiale e utente
        if codice_materiale not in self.catalogo:
            return False, "Materiale non trovato"
        
        if codice_utente not in self.utenti:
            return False, "Utente non trovato"
        
        materiale = self.catalogo[codice_materiale]
        utente = self.utenti[codice_utente]
        
        # Verifica possibilità di prestito
        può_prestare, motivo = utente.può_prestare(materiale)
        if not può_prestare:
            return False, motivo
        
        # Crea il prestito
        prestito = Prestito(utente, materiale, bibliotecario)
        
        # Aggiorna stati
        materiale.cambia_stato(StatoMateriale.PRESTATO, f"Prestato a {utente.nome}")
        materiale.data_ultimo_prestito = datetime.now()
        materiale.numero_prestiti += 1
        
        utente.prestiti_attivi.append(prestito)
        self.prestiti_attivi.append(prestito)
        
        # Aggiorna statistiche
        self.statistiche['prestiti_totali'] += 1
        if materiale.codice not in self.statistiche['materiali_più_richiesti']:
            self.statistiche['materiali_più_richiesti'][materiale.codice] = 0
        self.statistiche['materiali_più_richiesti'][materiale.codice] += 1
        
        print(f"📚 PRESTITO CREATO")
        print(f"   📖 Materiale: {materiale.titolo}")
        print(f"   👤 Utente: {utente.nome} {utente.cognome}")
        print(f"   📅 Scadenza: {prestito.data_scadenza.strftime('%d/%m/%Y')}")
        
        return True, "Prestito creato con successo"
    
    def restituisci_materiale(self, codice_materiale, codice_utente, note_restituzione=""):
        """Gestisce la restituzione di un materiale"""
        # Trova il prestito attivo
        prestito = None
        for p in self.prestiti_attivi:
            if (p.materiale.codice == codice_materiale and 
                p.utente.codice_utente == codice_utente):
                prestito = p
                break
        
        if not prestito:
            return False, "Prestito non trovato"
        
        # Calcola eventuale ritardo e multa
        giorni_ritardo = prestito.giorni_ritardo()
        multa_applicata = None
        
        if giorni_ritardo > 0:
            # Calcola multa: €0.50 per giorno di ritardo
            importo_multa = giorni_ritardo * 0.50
            motivo_multa = f"Ritardo di {giorni_ritardo} giorni per '{prestito.materiale.titolo}'"
            
            multa_applicata = Multa(prestito.utente, importo_multa, motivo_multa)
            prestito.utente.multe_attive.append(multa_applicata)
            
            print(f"⚠️ RITARDO: {giorni_ritardo} giorni - Multa: €{importo_multa:.2f}")
        
        # Completa la restituzione
        prestito.data_fine = datetime.now()
        if note_restituzione:
            prestito.note_prestito.append(f"[{datetime.now().strftime('%Y-%m-%d')}] Restituzione: {note_restituzione}")
        
        # Aggiorna stati
        prestito.materiale.cambia_stato(StatoMateriale.DISPONIBILE, "Restituito")
        
        # Sposta il prestito negli storici
        self.prestiti_attivi.remove(prestito)
        prestito.utente.prestiti_attivi.remove(prestito)
        self.storico_prestiti.append(prestito)
        prestito.utente.storico_prestiti.append(prestito)
        
        print(f"✅ RESTITUZIONE COMPLETATA")
        print(f"   📖 Materiale: {prestito.materiale.titolo}")
        print(f"   👤 Utente: {prestito.utente.nome}")
        
        return True, "Restituzione completata"
    
    def controllo_scadenze(self):
        """Controlla i prestiti in scadenza e applica multe automatiche"""
        oggi = datetime.now()
        prestiti_scaduti = []
        
        for prestito in self.prestiti_attivi:
            if prestito.è_in_ritardo():
                prestiti_scaduti.append(prestito)
        
        print(f"🔍 CONTROLLO SCADENZE - {len(prestiti_scaduti)} prestiti in ritardo")
        
        for prestito in prestiti_scaduti:
            giorni_ritardo = prestito.giorni_ritardo()
            print(f"   ⚠️ {prestito.utente.nome}: '{prestito.materiale.titolo}' - {giorni_ritardo} giorni")
        
        return prestiti_scaduti
    
    def genera_report_statistiche(self):
        """Genera un report completo delle statistiche"""
        print(f"\n📊 REPORT STATISTICHE - {self.nome_biblioteca.upper()}")
        print("=" * 60)
        
        # Statistiche generali
        print(f"📚 Materiali nel catalogo: {len(self.catalogo)}")
        print(f"👥 Utenti registrati: {len(self.utenti)}")
        print(f"📖 Prestiti attivi: {len(self.prestiti_attivi)}")
        print(f"📈 Prestiti totali: {self.statistiche['prestiti_totali']}")
        
        # Materiali più richiesti
        if self.statistiche['materiali_più_richiesti']:
            print(f"\n🏆 TOP 5 MATERIALI PIÙ RICHIESTI:")
            materiali_top = sorted(self.statistiche['materiali_più_richiesti'].items(), 
                                 key=lambda x: x[1], reverse=True)[:5]
            
            for i, (codice, prestiti) in enumerate(materiali_top, 1):
                materiale = self.catalogo[codice]
                print(f"   {i}. {materiale.titolo} - {prestiti} prestiti")
        
        # Analisi utenti
        utenti_attivi = [u for u in self.utenti.values() if len(u.prestiti_attivi) > 0]
        print(f"\n👤 Utenti con prestiti attivi: {len(utenti_attivi)}")
        
        # Prestiti in scadenza
        prestiti_scadenza_vicina = []
        for prestito in self.prestiti_attivi:
            giorni_alla_scadenza = (prestito.data_scadenza - datetime.now()).days
            if 0 <= giorni_alla_scadenza <= 3:
                prestiti_scadenza_vicina.append(prestito)
        
        if prestiti_scadenza_vicina:
            print(f"\n⏰ PRESTITI IN SCADENZA (prossimi 3 giorni): {len(prestiti_scadenza_vicina)}")
            for prestito in prestiti_scadenza_vicina:
                giorni = (prestito.data_scadenza - datetime.now()).days
                print(f"   📅 {prestito.utente.nome}: '{prestito.materiale.titolo}' (tra {giorni} giorni)")
```

### 4.2 Test del Sistema Completo

#### 4.2.1 Esempio di utilizzo

Ora mettiamo alla prova il nostro sistema con un esempio completo che dimostra tutte le funzionalità integrate.

```python
def demo_sistema_biblioteca():
    """Dimostrazione completa del sistema biblioteca"""
    
    # Creazione del sistema
    biblioteca = SistemaBiblioteca("Biblioteca Comunale 'Alessandro Manzoni'", "Via Roma 123")
    
    print(f"🏛️ {biblioteca.nome_biblioteca}")
    print(f"📍 {biblioteca.indirizzo}")
    print("=" * 60)
    
    # Popolamento del catalogo
    print("\n📚 POPOLAMENTO CATALOGO")
    print("-" * 30)
    
    materiali = [
        Libro("LIB001", "Il Nome della Rosa", "Umberto Eco", 1980, "Romanzo", "978-88-452-3547-8", 503, "Bompiani"),
        Libro("LIB002", "Programmazione Python", "Marco Rossi", 2022, "Manuale", "978-88-123-4567-9", 786, "TechBooks"),
        Libro("LIB003", "Storia d'Italia", "Giuseppe Verdi", 2019, "Storia", "978-88-987-6543-2", 342, "Storia Editore"),
        DVD("DVD001", "Inception", "Christopher Nolan", 2010, "Fantascienza", 148, True),
        DVD("DVD002", "La Vita è Bella", "Roberto Benigni", 1997, "Drammatico", 116, True),
        AudioLibro("AUD001", "1984", "George Orwell", 1949, "Distopia", "Mario Bianchi", 12, "digitale"),
        AudioLibro("AUD002", "Il Piccolo Principe", "Antoine de Saint-Exupéry", 1943, "Favola", "Laura Verdi", 4, "CD")
    ]
    
    for materiale in materiali:
        biblioteca.aggiungi_materiale(materiale)
    
    # Registrazione utenti
    print("\n👥 REGISTRAZIONE UTENTI")
    print("-" * 25)
    
    utenti = [
        Studente("STU001", "Mario", "Rossi", "mario.rossi@student.it", "123-456-7890", "Informatica", 3),
        Studente("STU002", "Anna", "Bianchi", "anna.bianchi@student.it", "123-456-7891", "Lettere", 1),
        Docente("DOC001", "Laura", "Verdi", "laura.verdi@university.it", "123-456-7892", "Informatica", ["Python", "Algoritmi"]),
        Cittadino("CIT001", "Giuseppe", "Neri", "giuseppe.neri@email.it", "123-456-7893", "Ingegnere")
    ]
    
    for utente in utenti:
        biblioteca.registra_utente(utente)
    
    # Test delle funzionalità di ricerca
    print("\n🔍 TEST RICERCA")
    print("-" * 15)
    
    risultati = biblioteca.cerca_materiali("Python")
    print(f"Ricerca 'Python': {len(risultati)} risultati trovati")
    for materiale in risultati:
        print(f"   • {materiale}")
    
    # Test prestiti
    print("\n📖 TEST PRESTITI")
    print("-" * 15)
    
    # Mario prende in prestito il libro di Python
    successo, messaggio = biblioteca.presta_materiale("LIB002", "STU001")
    print(f"Risultato: {messaggio}")
    
    # Anna prende in prestito il DVD
    successo, messaggio = biblioteca.presta_materiale("DVD001", "STU002")
    print(f"Risultato: {messaggio}")
    
    # Il docente prende l'audiolibro
    successo, messaggio = biblioteca.presta_materiale("AUD001", "DOC001")
    print(f"Risultato: {messaggio}")
    
    # Verifica stato prestiti
    print(f"\n📊 STATO ATTUALE:")
    print(f"Prestiti attivi: {len(biblioteca.prestiti_attivi)}")
    for prestito in biblioteca.prestiti_attivi:
        print(f"   • {prestito}")
    
    # Test proroga
    print("\n📅 TEST PROROGA")
    print("-" * 15)
    
    prestito_mario = biblioteca.prestiti_attivi[0]  # Il libro di Python
    if prestito_mario.proroga():
        print("✅ Proroga concessa")
    else:
        print("❌ Proroga non possibile")
    
    # Test restituzione
    print("\n📥 TEST RESTITUZIONE")
    print("-" * 20)
    
    # Anna restituisce il DVD
    successo, messaggio = biblioteca.restituisci_materiale("DVD001", "STU002", "DVD in perfette condizioni")
    print(f"Risultato: {messaggio}")
    
    # Simulazione ritardo (per test)
    print("\n⏰ SIMULAZIONE RITARDO")
    print("-" * 22)
    
    # Forziamo una data di scadenza passata per testare le multe
    prestito_mario.data_scadenza = datetime.now() - timedelta(days=5)
    
    # Restituzione in ritardo
    successo, messaggio = biblioteca.restituisci_materiale("LIB002", "STU001", "Scusa per il ritardo!")
    print(f"Risultato: {messaggio}")
    
    # Verifica multe
    mario = biblioteca.utenti["STU001"]
    if mario.multe_attive:
        print(f"💰 Mario ha {len(mario.multe_attive)} multe attive:")
        for multa in mario.multe_attive:
            print(f"   • €{multa.importo:.2f} - {multa.motivo}")
    
    # Test controllo scadenze
    print("\n🔍 CONTROLLO SCADENZE AUTOMATICO")
    print("-" * 35)
    biblioteca.controllo_scadenze()
    
    # Report finale
    biblioteca.genera_report_statistiche()
    
    print(f"\n✨ DEMO COMPLETATA!")

if __name__ == "__main__":
    demo_sistema_biblioteca()
```

### 4.3 Best Practices in OOP

#### 4.3.1 Principi SOLID

I principi SOLID sono cinque linee guida fondamentali per scrivere codice orientato agli oggetti di alta qualità. Questi principi non sono regole rigide ma suggerimenti che, se seguiti, rendono il codice più mantenibile, estensibile e robusto.

**S - Single Responsibility Principle (Principio di Responsabilità Singola)**: Ogni classe dovrebbe avere una sola ragione per cambiare, cioè dovrebbe essere responsabile di una sola funzionalità. Nel nostro sistema biblioteca, la classe `Prestito` si occupa solo di gestire i prestiti, non di gestire anche gli utenti o il catalogo. Questo rende il codice più facile da capire e modificare.

**O - Open/Closed Principle (Principio Aperto/Chiuso)**: Le classi dovrebbero essere aperte per l'estensione ma chiuse per la modifica. Possiamo aggiungere nuovi tipi di materiali (come riviste o mappe) estendendo `MaterialeBiblioteca` senza modificare il codice esistente. Questo principio è quello che rende l'ereditarietà così potente.

**L - Liskov Substitution Principle (Principio di Sostituzione di Liskov)**: Gli oggetti delle classi derivate dovrebbero poter sostituire oggetti della classe base senza alterare la correttezza del programma. Ogni sottoclasse di `MaterialeBiblioteca` può essere usata ovunque ci aspettiamo un `MaterialeBiblioteca`, mantenendo il comportamento corretto.

**I - Interface Segregation Principle (Principio di Segregazione delle Interfacce)**: È meglio avere molte interfacce specifiche piuttosto che una sola interfaccia generale. Invece di avere una mega-classe `UtenteSuperCompleto` con tutti i metodi possibili, abbiamo classi specifiche per studenti, docenti, e cittadini.

**D - Dependency Inversion Principle (Principio di Inversione delle Dipendenze)**: Le classi di alto livello non dovrebbero dipendere da classi di basso livello, ma entrambe dovrebbero dipendere da astrazioni. Il nostro `SistemaBiblioteca` lavora con l'astrazione `MaterialeBiblioteca`, non con implementazioni specifiche come `Libro` o `DVD`.

#### 4.3.2 Convenzioni di naming

Python ha convenzioni specifiche per i nomi che rendono il codice più leggibile e professionale. Le convenzioni non sono solo questioni estetiche: aiutano altri programmatori (e voi stessi in futuro) a capire rapidamente cosa fa ogni elemento del codice.

Per le **classi**, usiamo il PascalCase: ogni parola inizia con la maiuscola (`MaterialeBiblioteca`, `SistemaBiblioteca`). Per **variabili e funzioni**, usiamo lo snake_case: parole separate da underscore (`data_scadenza`, `calcola_reputazione`). Le **costanti** sono in MAIUSCOLO (`DURATA_PRESTITO_BASE`).

Gli **attributi e metodi privati** iniziano con un underscore (`_limite_prestiti`), mentre quelli "molto privati" con due underscore (`__metodo_interno`). Gli attributi pubblici non hanno underscore iniziali.

I **nomi dovrebbero essere descrittivi** ma non eccessivamente lunghi. È meglio `calcola_durata_prestito()` piuttosto che `calcola()` o `calcola_la_durata_del_prestito_basata_sul_tipo_di_utente_e_materiale()`.

#### 4.3.3 Documentazione con docstring

Le docstring sono un modo standardizzato per documentare classi, metodi e funzioni in Python. Non sono solo commenti: sono parte integrante del codice e possono essere usate da strumenti automatici per generare documentazione.

```python
class MaterialeBiblioteca:
    """
    Classe base per tutti i materiali che possono essere prestati dalla biblioteca.
    
    Questa classe definisce le caratteristiche e comportamenti comuni a tutti i materiali:
    libri, DVD, audiolibri, riviste, etc. Ogni materiale ha uno stato, può essere
    prestato e restituito, e mantiene uno storico delle operazioni.
    
    Attributes:
        codice (str): Identificativo univoco del materiale
        titolo (str): Titolo del materiale
        autore (str): Autore, regista, o creatore del materiale
        stato (StatoMateriale): Stato attuale del materiale
        numero_prestiti (int): Contatore dei prestiti effettuati
    
    Example:
        >>> libro = Libro("LIB001", "1984", "George Orwell", 1949, "Distopia", 
        ...               "978-0-452-28423-4", 328, "Secker & Warburg")
        >>> print(libro.è_disponibile())
        True
        >>> libro.cambia_stato(StatoMateriale.PRESTATO, "Prestato a Mario Rossi")
        🔄 '1984' ora è: prestato
    """
    
    def durata_prestito_suggerita(self, tipo_utente):
        """
        Calcola la durata suggerita per il prestito basata sul tipo di utente.
        
        Questo metodo deve essere implementato dalle sottoclassi per fornire
        durate specifiche basate sulle caratteristiche del materiale.
        
        Args:
            tipo_utente (str): Tipo di utente che richiede il prestito
                             ('studente', 'docente', 'cittadino', 'staff')
        
        Returns:
            int: Numero di giorni suggeriti per il prestito
        
        Raises:
            NotImplementedError: Se chiamato sulla classe base
        
        Note:
            Le sottoclassi dovrebbero considerare fattori come:
            - Complessità del materiale
            - Tempo di fruizione normale
            - Politiche specifiche per tipo di utente
        """
        raise NotImplementedError("Le sottoclassi devono implementare questo metodo")
```

Una buona docstring dovrebbe spiegare **cosa** fa il metodo, **perché** esiste, **come** usarlo, e **cosa** aspettarsi come risultato. Include anche esempi pratici quando utile.

### 4.4 Esercizi di Consolidamento

#### 4.4.1 Esercizio 1: Sistema Scuola

**Obiettivo**: Progettare un sistema per gestire una scuola con studenti, professori, corsi, e voti.

**Requisiti**:
- Classi per `Persona`, `Studente`, `Professore`
- Classe `Corso` con lista di studenti iscritti
- Classe `Voto` per registrare valutazioni
- Sistema di calcolo delle medie per studente e per corso
- Gestione dell'orario delle lezioni

**Funzionalità da implementare**:
- Iscrizione studenti ai corsi
- Assegnazione professori ai corsi
- Registrazione voti
- Calcolo statistiche (media studente, media corso, percentuale promossi)
- Report di fine quadrimestre

Questo esercizio vi permetterà di praticare l'ereditarietà, la composizione (un corso "ha" studenti), e la gestione di relazioni many-to-many (studenti possono seguire più corsi, corsi possono avere più studenti).

#### 4.4.2 Esercizio 2: E-commerce

**Obiettivo**: Creare un sistema di e-commerce con prodotti, carrello, ordini, e gestione magazzino.

**Requisiti**:
- Gerarchia di prodotti (`Prodotto`, `ProdottoFisico`, `ProdottoDigitale`)
- Classe `Cliente` con storico acquisti
- Classe `Carrello` per gestire acquisti temporanei
- Classe `Ordine` per acquisti confermati
- Sistema di sconti e promozioni

**Funzionalità da implementare**:
- Aggiunta/rimozione prodotti dal carrello
- Calcolo totale con sconti
- Gestione scorte magazzino
- Sistema di recensioni
- Tracciamento spedizioni per prodotti fisici

Questo esercizio vi farà lavorare con il polimorfismo (prodotti diversi si comportano diversamente), la composizione complessa, e la gestione di stati.

#### 4.4.3 Esercizio 3: Sistema Bancario

**Obiettivo**: Sviluppare un sistema bancario con diversi tipi di conti, transazioni, e servizi.

**Requisiti**:
- Gerarchia di conti (`Conto`, `ContoCorrente`, `ContoRisparmio`, `ContoInvestimenti`)
- Classe `Cliente` con più conti possibili
- Classe `Transazione` per movimenti
- Classe `Banca` per coordinare operazioni
- Sistema di interessi e commissioni

**Funzionalità da implementare**:
- Apertura/chiusura conti
- Trasferimenti tra conti
- Calcolo interessi automatico
- Estratti conto periodici
- Limiti e controlli di sicurezza
- Sistema di prestiti

Questo esercizio è il più complesso e vi farà utilizzare tutti i concetti dell'OOP: ereditarietà multipla (un conto può essere sia corrente che con fido), polimorfismo (diversi tipi di transazione), incapsulamento (protezione dei dati sensibili), e astrazione (interfacce comuni per operazioni bancarie).

**Suggerimenti per tutti gli esercizi**:
1. Iniziate sempre con l'analisi: identificate entità, attributi, e relazioni
2. Progettate la struttura delle classi prima di scrivere codice
3. Implementate funzionalità base prima di aggiungere caratteristiche avanzate
4. Testate ogni funzionalità man mano che la implementate
5. Usate docstring per documentare classi e metodi importanti
6. Pensate sempre all'estensibilità: il vostro codice sarà facile da modificare?

**🤔 Domande di Verifica - Modulo 4**

1. Spiegate come i principi SOLID si applicano al nostro sistema biblioteca. Fornite esempi specifici.

2. Perché abbiamo usato l'Enum per `StatoMateriale` invece di semplici stringhe? Quali vantaggi offre?

3. Nel sistema biblioteca, come gestireste l'aggiunta di un nuovo tipo di materiale (es. mappe geografiche) senza modificare il codice esistente?

4. Progettate un sistema di notifiche per avvisare gli utenti di scadenze imminenti. Quale pattern di design usereste?

5. Come implementereste un sistema di backup/ripristino per il database della biblioteca utilizzando i principi OOP?

6. Discutete i pro e i contro dell'uso dell'ereditarietà vs composizione nel nostro sistema. Ci sono parti dove avreste fatto scelte diverse?

## 🎓 **Riepilogo e Prossimi Passi**

### 📋 Cosa Abbiamo Imparato

In questo viaggio attraverso la programmazione orientata agli oggetti abbiamo coperto molto terreno. Abbiamo iniziato con i concetti fondamentali, scoprendo che l'OOP non è solo un modo diverso di scrivere codice, ma un modo diverso di *pensare* i problemi e le soluzioni.

**Nel Modulo 1** abbiamo posto le fondamenta, esplorando i quattro pilastri dell'OOP: incapsulamento, ereditarietà, polimorfismo e astrazione. Abbiamo visto come questi concetti ci aiutino a organizzare il codice in modo più naturale e mantenibile, rispecchiando come pensiamo il mondo reale.

**Nel Modulo 2** abbiamo messo le mani sul codice, imparando a creare classi e oggetti in Python. Abbiamo scoperto la potenza dei metodi speciali (magic methods) e costruito esempi pratici come il sistema ContoBancario, vedendo come l'incapsulamento protegga l'integrità dei nostri dati.

**Nel Modulo 3** abbiamo esplorato l'ereditarietà e il polimorfismo, concetti che rendono l'OOP veramente potente. Abbiamo visto come il Duck Typing di Python renda il polimorfismo naturale e flessibile, e costruito un sistema completo di gestione veicoli che dimostra questi principi in azione.

**Nel Modulo 4** abbiamo messo tutto insieme in un progetto reale: il sistema di gestione biblioteca. Questo progetto ha mostrato come applicare best practices, seguire i principi SOLID, e creare sistemi complessi ma mantenibili.

### 🛤️ Il Vostro Percorso Continua

Quello che avete imparato qui è solo l'inizio. La programmazione orientata agli oggetti è un paradigma ricco e profondo che continuerete a esplorare per tutta la vostra carriera di programmatori. Ogni progetto vi insegnerà qualcosa di nuovo, ogni problema vi farà vedere nuove applicazioni di questi principi.

**Per continuare a migliorare**, vi consiglio di:

1. **Praticare regolarmente**: Fate gli esercizi proposti, ma soprattutto inventatene di nuovi. Ogni volta che vedete un sistema nel mondo reale (una biblioteca, un negozio, una scuola), chiedetevi: "Come lo modellerei con l'OOP?"

2. **Leggere codice di altri**: Esplorate progetti open source su GitHub. Vedere come programmatori esperti strutturano le loro classi vi insegnerà pattern e tecniche nuove.

3. **Sperimentare con framework**: Provate framework come Django per il web o tkinter per le GUI. Questi strumenti sono costruiti con principi OOP e vi faranno vedere applicazioni avanzate.

4. **Studiare design patterns**: I pattern di design sono soluzioni provate a problemi ricorrenti nell'OOP. Il Singleton, l'Observer, il Factory Method sono solo alcuni esempi.

5. **Non smettere mai di fare domande**: Perché questa classe è strutturata così? Come potrei renderla più flessibile? C'è un modo migliore per organizzare queste responsabilità?

### 🔮 Verso Nuovi Orizzonti

L'OOP vi aprirà le porte a molte tecnologie e concetti avanzati:

- **Programmazione GUI**: Creare interfacce grafiche diventa naturale quando pensate in termini di oggetti che interagiscono
- **Sviluppo web**: Framework come Django e Flask sono profondamente orientati agli oggetti
- **Game development**: I videogiochi sono un perfetto esempio di sistemi OOP complessi
- **Machine Learning**: Anche l'AI moderna utilizza principi OOP per organizzare modelli e dati
- **Programmazione mobile**: Sia Android che iOS utilizzano paradigmi orientati agli oggetti

### 💡 Un Ultimo Pensiero

Ricordatevi che l'obiettivo non è mai scrivere codice che sia semplicemente "orientato agli oggetti", ma scrivere codice che sia **chiaro, mantenibile, e che risolva problemi reali**. L'OOP è uno strumento potente, ma come ogni strumento, va usato con saggezza e nel contesto giusto.

A volte una semplice funzione è meglio di una classe complessa. A volte un approccio procedurale è più diretto. L'arte della programmazione sta nel saper scegliere l'approccio giusto per ogni situazione.

### 🚀 Buon Viaggio!

Ora avete gli strumenti per affrontare progetti più complessi e sfidanti. Usate quello che avete imparato come trampolino per esplorare nuove tecnologie e costruire software che faccia la differenza nel mondo.

La programmazione orientata agli oggetti non è solo un modo di scrivere codice: è un modo di pensare sistemi, relazioni, e soluzioni. Portate questa mentalità con voi in ogni progetto futuro.

**Buona programmazione, e che i vostri oggetti siano sempre ben incapsulati! 🐍✨**