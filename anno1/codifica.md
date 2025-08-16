# Codifica dell'informazione

## Introduzione

Benvenuti nel mondo affascinante della codifica dell'informazione! Ogni giorno interagiamo con miliardi di informazioni digitali: foto, video, musica, testi, messaggi. Ma come fa un computer a "capire" e memorizzare una foto del vostro gatto o la vostra canzone preferita? La risposta sta nella codifica dell'informazione, il processo che trasforma tutto ciò che vediamo, sentiamo e pensiamo in un linguaggio che i computer possono comprendere: sequenze di 0 e 1.

In questo corso di 4 ore esploreremo come i computer rappresentano e gestiscono l'informazione, dalle unità più piccole (i bit) fino alle applicazioni più complesse come immagini ad alta risoluzione e audio di qualità professionale. Scoprirete che dietro ogni pixel, ogni nota musicale e ogni carattere di testo c'è un mondo di matematica elegante e ingegneria brillante.

---

## 1. Introduzione alla codifica dell'informazione

### 1.1 Che cos'è la codifica dell'informazione?

La **codifica dell'informazione** è il processo di trasformazione di dati di qualsiasi tipo (testo, immagini, suoni, video) in una forma che i computer possono elaborare, memorizzare e trasmettere. È come tradurre da una lingua umana a una lingua che solo i computer comprendono.

**Analogia del dizionario**: Immaginate di dover spiegare il concetto di "rosso" a qualcuno che vede solo in bianco e nero. Dovreste trovare un modo per "codificare" il rosso usando solo informazioni che quella persona può capire. Allo stesso modo, i computer "vedono" solo 0 e 1, quindi dobbiamo tradurre tutto in questo linguaggio binario.

### 1.2 Perché è necessaria la codifica?

I computer sono dispositivi elettronici che funzionano con segnali elettrici molto semplici. Pensate a un interruttore della luce: può essere acceso o spento, non esistono vie di mezzo. Allo stesso modo, ogni circuito elettronico di un computer può trovarsi in due stati fondamentali: **acceso** quando c'è presenza di corrente elettrica (rappresentato dal numero 1), oppure **spento** quando la corrente è assente (rappresentato dal numero 0).

Questa apparente semplicità è in realtà il segreto del successo dei computer moderni e offre tre vantaggi straordinari. Prima di tutto, garantisce un'**affidabilità** incredibile: è molto facile per un circuito elettronico distinguere tra "c'è corrente" e "non c'è corrente", quindi gli errori sono rarissimi. Immaginate se doveste riconoscere 100 sfumature diverse di grigio: sarebbe molto più difficile e fareste più errori rispetto al distinguere semplicemente tra bianco e nero! In secondo luogo, questa semplicità permette una **velocità** straordinaria: i circuiti possono passare da acceso a spento miliardi di volte al secondo, molto più velocemente di qualsiasi meccanismo complesso. Infine, offre una **scalabilità** infinita: combinando milioni o miliardi di questi semplici interruttori, si possono creare sistemi incredibilmente complessi che gestiscono video, musica, giochi e persino intelligenze artificiali.

### 1.3 Storia della codifica

**Telegrafo e Codice Morse (1830s)**
Il primo esempio di codifica digitale fu il codice Morse, che rappresentava lettere e numeri con sequenze di punti e linee:

- A = · −
- B = − · · ·
- SOS = · · · − − − · · ·

**Era dei computer (1940s-oggi)**
Con l'avvento dei computer elettronici, nacque l'esigenza di codificare tutto in binario:

- **1940s**: Primi computer binari
- **1960s**: Standard ASCII per caratteri
- **1970s-80s**: Codifica di immagini e audio
- **1990s-oggi**: Codifica multimediale complessa

### 1.4 Tipi di informazione da codificare

Ogni volta che usate un dispositivo digitale, gestite quattro grandi categorie di informazioni che devono essere tutte tradotte nel linguaggio binario dei computer.

La prima categoria è l'**informazione testuale**, che include tutto ciò che riguarda le parole scritte. Non si tratta solo delle lettere dell'alfabeto, dei numeri e dei simboli di punteggiatura, ma anche delle informazioni sulla formattazione: quando scrivete una parola in **grassetto** o in *corsivo*, il computer deve ricordare non solo quali lettere compongono quella parola, ma anche il fatto che deve apparire diversa dal testo normale. Inoltre, deve mantenere la struttura del documento: quali parti sono titoli, quali sono paragrafi normali, dove vanno gli spazi e dove vanno a capo le righe.

La seconda categoria è l'**informazione visiva**, probabilmente quella più ovvia nell'era dei social media e delle foto digitali. Qui rientrano le immagini fotografiche che scattate con il vostro smartphone, ma anche la grafica vettoriale (come i loghi e le icone), i video che guardate su YouTube o TikTok e le animazioni dei videogiochi. Ogni pixel di ogni immagine deve essere codificato con precisione per riprodurre fedelmente colori, luci e ombre.

La terza categoria è l'**informazione audio**: dalla vostra playlist musicale preferita ai suoni naturali registrati nella natura, dalle voci nelle videochiamate agli effetti sonori dei film. Ogni vibrazione sonora che l'orecchio umano può percepire deve essere catturata e trasformata in numeri che il computer può elaborare e riprodurre attraverso cuffie o altoparlanti.

Infine, c'è l'**informazione di controllo**, invisibile ma fondamentale: i comandi che impartite al sistema operativo quando cliccate su un'icona, i protocolli di rete che permettono al vostro telefono di comunicare con internet, e tutti i metadati che descrivono gli altri tipi di file (per esempio, quando è stata scattata una foto o chi è l'artista di una canzone).

---

## 2. Il concetto di bit e byte

### 2.1 Il bit: l'unità fondamentale

Il **bit** (binary digit) è l'unità più piccola di informazione in un sistema digitale. Può assumere solo due valori:

- **0** (zero, falso, spento)
- **1** (uno, vero, acceso)

**Analogie per comprendere il bit:**

Per capire davvero cos'è un bit, pensate a tre situazioni della vita quotidiana che sicuramente conoscete. La prima è l'interruttore della luce nella vostra camera: può essere acceso o spento, non esistono posizioni intermedie. Quando è acceso, passa corrente e la lampadina si illumina (come il valore 1 di un bit); quando è spento, non passa corrente e la stanza resta buia (come il valore 0). La seconda analogia è ancora più semplice: quando qualcuno vi fa una domanda che richiede una risposta sì o no, state comunicando l'equivalente di un bit di informazione. "Hai fatto i compiti?" può avere solo due risposte possibili, proprio come un bit può avere solo due valori. Infine, pensate a quando lanciate una moneta in aria: può uscire testa o croce, mai entrambe contemporaneamente. Ogni bit in un computer è come una moneta che si è fermata definitivamente su uno dei due lati.

**Capacità informativa di un bit:**

Anche se può sembrare incredibile, un singolo bit può trasmettere informazioni molto utili nella vita reale. Pensate a quando entrate in un bagno pubblico: la piccola luce rossa o verde sulla porta vi comunica un bit di informazione che vi dice se è libero o occupato. In ambito medico, un test rapido può essere positivo o negativo, comunicando un bit cruciale per la diagnosi. Sui social media, quando mettete "mi piace" a un post, state aggiungendo un bit di informazione che esprime il vostro gradimento. Perfino il genere di una persona può essere rappresentato con un bit (anche se nella realtà moderna sappiamo che è più complesso): maschio o femmina, 0 o 1. Ogni volta che dovete prendere una decisione tra due opzioni - accettare o rifiutare un invito, andare a destra o a sinistra, accendere o spegnere un dispositivo - state elaborando mentalmente un bit di informazione.

### 2.2 Combinazioni di bit

Ora arriva la parte davvero interessante: cosa succede quando mettiamo insieme più bit? È come passare da avere solo due colori (bianco e nero) a poter creare una tavolozza sempre più ricca e variegata.

Iniziamo con **2 bit insieme**: se ciascuno può essere 0 o 1, le combinazioni possibili diventano quattro: 00, 01, 10, 11. Pensate a un semaforo che invece di tre colori ne avesse quattro: potremmo usare 2 bit per indicare quattro direzioni diverse (Nord, Sud, Est, Ovest), oppure quattro livelli di velocità consentita, o ancora quattro stati d'animo di base.

Con **3 bit** le possibilità si moltiplicano ulteriormente, arrivando a otto combinazioni diverse: 000, 001, 010, 011, 100, 101, 110, 111. Otto è un numero molto utile: pensate agli otto colori di base che usavate da bambini con i pastelli (rosso, blu, giallo, verde, arancione, viola, marrone, nero), oppure alle otto note musicali di un'ottava (do, re, mi, fa, sol, la, si, do), o ancora alle otto direzioni principali di una bussola (Nord, Nordest, Est, Sudest, Sud, Sudovest, Ovest, Nordovest).

La matematica ci dice che con **n bit** possiamo rappresentare esattamente **2ⁿ possibilità** diverse. Questo significa che con 4 bit otteniamo 16 possibilità (pensate alle 16 caselle di una scacchiera 4×4), con 8 bit arriviamo a 256 possibilità (abbastanza per tutti i caratteri dell'alfabeto più numeri e simboli), e con 16 bit raggiungiamo ben 65.536 possibilità diverse! È come avere una tavolozza di colori sempre più ricca: più bit aggiungiamo, più sfumature diverse possiamo rappresentare.

### 2.3 Il byte: il blocco costruttivo

Adesso che sapete come funzionano i bit singoli e le loro combinazioni, è arrivato il momento di conoscere il **byte**, che è semplicemente un gruppo di 8 bit considerati insieme come un'unità. Il byte è l'unità standard che tutti i computer del mondo usano per misurare la memoria e lo spazio di archiviazione, un po' come il metro è l'unità standard per misurare le distanze.

Ma perché proprio 8 bit e non 7 o 10? La scelta non è casuale, ma deriva da ragioni molto pratiche che hanno plasmato l'informatica moderna. Prima di tutto, c'è una questione di **praticità**: 8 bit possono rappresentare 256 valori diversi (da 0 a 255), che sono sufficienti per includere tutte le lettere maiuscole e minuscole dell'alfabeto inglese, tutti i numeri da 0 a 9, tutti i simboli di punteggiatura più comuni, e persino alcuni caratteri speciali. È come avere un alfabeto abbastanza grande da scrivere qualsiasi cosa in inglese, ma non così grande da diventare complicato da gestire.

C'è poi una ragione legata all'**efficienza hardware**: i processori dei computer sono progettati per lavorare naturalmente con multipli di 8. Questo significa che possono elaborare, spostare e memorizzare i dati molto più velocemente quando sono organizzati in gruppi di 8 bit. È come se i byte fossero dei mattoncini perfettamente progettati per incastrarsi nei meccanismi interni del computer.

Infine, la scelta di 8 bit ha favorito la **standardizzazione** mondiale: quando tutti i produttori hanno adottato lo stesso standard, è diventato molto più facile far funzionare insieme computer di marche diverse, programmi sviluppati in paesi diversi e dispositivi creati in epoche diverse.

La capacità di un byte è davvero impressionante: può rappresentare numeri interi da 0 a 255, tutti i 256 caratteri del set ASCII esteso (che include lettere, numeri, simboli e anche caratteri speciali), oppure un pixel di un'immagine in scala di grigi con 256 diversi livelli di luminosità, dal nero più profondo al bianco più brillante.

### 2.4 Rappresentazione di caratteri

**ASCII (American Standard Code for Information Interchange)**

- Utilizza 7 bit (128 caratteri)
- Caratteri inglesi di base: A-Z, a-z, 0-9, simboli

**Esempi ASCII:**

- A = 65 = 01000001
- a = 97 = 01100001
- 0 = 48 = 00110000
- spazio = 32 = 00100000

**Unicode**

- Standard moderno che può usare fino a 32 bit per carattere
- Supporta tutte le lingue del mondo: 中文, العربية, हिन्दी, Русский
- Oltre 1 milione di caratteri possibili

### 2.5 Visualizzazione dei byte

**Rappresentazione esadecimale**
Spesso i byte vengono mostrati in esadecimale per compattezza:

- 1 byte = 2 cifre esadecimali
- Esempio: 255 = FF, 128 = 80, 0 = 00

**Editor esadecimali**
Strumenti che mostrano il contenuto "grezzo" dei file:

```
48 65 6C 6C 6F 20 57 6F 72 6C 64 21
H  e  l  l  o     W  o  r  l  d  !
```

---

## 3. Multipli del bit e del byte

### 3.1 Multipli del byte: sistema binario vs decimale

**Sistema binario (base 2) - Standard IEC**
I computer lavorano in base 2, quindi i multipli "reali" sono potenze di 2:

| Nome     | Simbolo | Valore              | In byte            |
|----------|---------|---------------------|--------------------|
| Kibibyte | KiB     | 2¹⁰ = 1.024 byte    | 1.024              |
| Mebibyte | MiB     | 2²⁰ = 1.048.576     | 1.024 KiB          |
| Gibibyte | GiB     | 2³⁰ = 1.073.741.824 | 1.024 MiB          |
| Tebibyte | TiB     | 2⁴⁰                 | 1.024 GiB          |

**Sistema decimale (base 10) - Standard SI**
I produttori spesso usano multipli decimali per semplicità:

| Nome     | Simbolo | Valore              | In byte            |
|----------|---------|---------------------|--------------------|
| Kilobyte | KB      | 10³ = 1.000 byte    | 1.000              |
| Megabyte | MB      | 10⁶ = 1.000.000     | 1.000 KB           |
| Gigabyte | GB      | 10⁹ = 1.000.000.000 | 1.000 MB           |
| Terabyte | TB      | 10¹² = 1.000.000.000.000 | 1.000 GB     |

### 3.2 La confusione dei multipli

**Perché esistono due sistemi?**

- **Sistema binario**: Riflette il funzionamento reale dei computer
- **Sistema decimale**: È più familiare agli umani (usiamo base 10)

**Differenze pratiche:**

- 1 GB (decimale) = 0,93 GiB (binario)
- Un HD da "500 GB" in realtà contiene circa 465 GiB
- Questa differenza aumenta con taglie maggiori

**Dove si trova ciascun sistema:**

- **Binario**: Memoria RAM, dimensioni file nel sistema operativo
- **Decimale**: Hard disk, SSD, velocità di rete

### 3.3 Multipli del bit

Per velocità di trasmissione e larghezza di banda si usano i multipli del bit:

**Multipli comuni:**

- Kilobit (Kbit, Kb) = 1.000 bit
- Megabit (Mbit, Mb) = 1.000.000 bit  
- Gigabit (Gbit, Gb) = 1.000.000.000 bit

**Nota importante**:

- 8 bit = 1 byte
- 1 Megabit = 125 Kilobyte
- La vostra connessione a 100 Mbps può scaricare al massimo 12,5 MB/s

### 3.4 Esempi pratici di dimensioni

**Documenti di testo:**

- Lettera: 1-5 KB
- Libro: 1-5 MB
- Enciclopedia: 100 MB - 1 GB

**Immagini:**

- Icona 16x16: 1 KB
- Foto smartphone: 3-8 MB
- Immagine professionale: 20-100 MB

**Audio:**

- Canzone MP3: 3-6 MB
- Album CD: 500-700 MB
- Audio non compresso: 50 MB/minuto

**Video:**

- Video YouTube 480p: 10 MB/minuto
- Film 1080p: 3-8 GB
- Film 4K: 15-30 GB

---

## 4. Quando si usa il bit e quando si usa il byte

### 4.1 Ambiti di utilizzo del bit

Esistono situazioni specifiche in cui gli esperti di informatica preferiscono parlare di bit anziché di byte, e non è solo una questione di abitudine: c'è sempre una ragione tecnica precisa dietro questa scelta.

L'ambito più importante dove si usano i bit è nelle **velocità di trasmissione**. Quando il vostro provider internet vi dice che avete una connessione da 100 Mbps (megabit per secondo), sta parlando di quanti bit possono viaggiare attraverso il cavo ogni secondo. Le velocità di rete si misurano sempre in bit per secondo: la vostra ADSL potrebbe essere 20 Mbps, la fibra ottica casalinga arriva spesso a 1 Gbps (gigabit per secondo), il Wi-Fi può raggiungere 300 Mbps, mentre il Bluetooth si ferma intorno ai 2 Mbps. Perché si usano i bit per le velocità? Ci sono tre ragioni principali: prima di tutto è una tradizione storica delle telecomunicazioni, che esistevano già prima dei computer; in secondo luogo, i segnali digitali viaggiano davvero bit per bit attraverso i cavi e le onde radio; infine, c'è una ragione di marketing non troppo nascosta: i numeri espressi in bit sono otto volte più grandi di quelli espressi in byte, quindi sembrano più impressionanti!

Un altro campo dove i bit sono fondamentali è la **profondità colore** nella grafica digitale. Quando sentite parlare di immagini a 8 bit, 24 bit o 32 bit, si riferisce a quanti bit vengono usati per rappresentare ogni singolo pixel. Un'immagine a 1 bit può essere solo bianca o nera (come i vecchi fax), una a 8 bit può avere 256 colori o 256 sfumature di grigio, una a 24 bit può rappresentare oltre 16 milioni di colori diversi (quella che chiamiamo "True Color"), mentre una a 32 bit include anche informazioni sulla trasparenza.

Infine, quando si parla di **processori e architetture** di computer, i bit descrivono la capacità di elaborazione. Un processore a 32 bit può elaborare 32 bit di dati contemporaneamente, mentre uno a 64 bit ne elabora 64 alla volta, rendendolo teoricamente più veloce ed efficiente. I registri interni del processore, che sono come la memoria temporanea di lavoro, vengono sempre misurati in bit perché riflettono direttamente l'architettura hardware.

### 4.2 Ambiti di utilizzo del byte

Mentre i bit sono perfetti per velocità e profondità, i byte dominano un territorio completamente diverso: tutto ciò che riguarda lo spazio e la memorizzazione dei dati.

Quando parliamo di **dimensioni file e storage**, entriamo nel regno dei byte. Il documento Word che state scrivendo per la scuola potrebbe occupare 1,5 MB (megabyte), l'hard disk del vostro computer potrebbe avere una capacità di 1 TB (terabyte), la memoria RAM del vostro smartphone è probabilmente 4 o 8 GB (gigabyte), e quella chiavetta USB che usate per i compiti da 32 GB. Perché per lo storage si usano i byte invece dei bit? La ragione è profondamente tecnica: un byte è l'unità minima che il computer può "indirizzare" in memoria, cioè è il più piccolo pezzo di dati che può trovare e modificare. È come dire che mentre potete contare i mattoni singoli di un muro (i bit), quando dovete costruire o ristrutturare pensate in termini di intere tegole (i byte). Inoltre, per gli utenti normali è molto più intuitivo ragionare in byte: dire che una foto occupa 5 MB è più comprensibile che dire 40 milioni di bit!

I byte sono fondamentali anche quando parliamo di **memoria e buffer** dei sistemi. Il buffer di rete del vostro router potrebbe essere di 64 KB (kilobyte), la cache del processore del computer potrebbe essere 8 MB, mentre lo stack di memoria che i programmi usano per le operazioni temporanee si misura tipicamente in KB. Questi numeri in byte ci danno un'idea immediata della capacità e delle prestazioni del sistema.

Un caso particolare è quando misuriamo il **throughput effettivo**, cioè la velocità reale di trasferimento dei dati. Mentre le connessioni internet si pubblicizzano in Mbps (megabit per secondo), quando effettivamente scaricate un file vedrete la velocità in MB/s (megabyte per secondo). Per esempio, se avete una connessione da 100 Mbps, la velocità massima teorica di download sarà 12,5 MB/s. Quando copiate file da una cartella all'altra sul computer, vedrete velocità come 100 MB/s, e quando scrivete dati su un SSD moderno potreste raggiungere 500 MB/s. Questi numeri in byte sono più significativi per l'utente finale perché riflettono direttamente quanto tempo ci vorrà per completare un'operazione concreta.

### 4.3 Conversioni pratiche

**Formula fondamentale:**
1 byte = 8 bit

**Conversioni di velocità:**

- 100 Mbps ÷ 8 = 12,5 MB/s (velocità massima di download)
- 1 GB file ÷ 12,5 MB/s = 80 secondi per scaricare

**Esempi reali:**

- Connessione 20 Mbps = 2,5 MB/s reali
- File da 100 MB = 40 secondi per scaricare
- Streaming 4K richiede ~25 Mbps = 3,125 MB/s

### 4.4 Contesti di confusione comune

**Pubblicità vs realtà:**

- "Internet 100 Mega" = 100 Mbps = 12,5 MB/s massimi
- "USB 3.0 a 5 Gbps" = 625 MB/s teorici, ~400 MB/s reali

**Sistemi operativi:**

- Windows mostra dimensioni in byte decimali per HD
- Ma usa byte binari per memoria RAM
- macOS ha cambiato da binario a decimale nel 2009

---

## 5. Misurazione delle velocità di trasferimento

### 5.1 Concetti fondamentali

Per capire veramente le velocità di trasferimento dati, dobbiamo prima distinguere tra due concetti che spesso vengono confusi ma che sono molto diversi tra loro.

Il primo concetto è la differenza tra **bandwidth (larghezza di banda)** e **throughput**. Immaginate l'internet come un'autostrada: la bandwidth è come il numero di corsie disponibili, cioè la capacità teorica massima di traffico che può passare. Se avete una connessione da 100 Mbps, quella è la vostra bandwidth - il massimo assoluto che la vostra "autostrada digitale" può sopportare. Il throughput, invece, è il traffico che effettivamente passa in un momento specifico: anche se l'autostrada ha 6 corsie, magari ne state usando solo 3 perché non c'è così tanto traffico, oppure ci sono dei rallentamenti dovuti a lavori in corso o incidenti. Il throughput è sempre minore o uguale al bandwidth, mai superiore - è fisicamente impossibile far passare più traffico di quanto le corsie permettano.

Il secondo concetto fondamentale è la differenza tra **latenza** e **velocità**. Continuando con l'analogia dell'autostrada, la latenza è il tempo che impiegate ad arrivare a destinazione (misurato in millisecondi per le reti), mentre la velocità è quante auto possono passare ogni secondo (misurata in bit per secondo). Potreste avere un'autostrada velocissima ma che richiede un'ora per arrivare in città perché è molto lontana (alta velocità, alta latenza), oppure una strada di campagna lenta ma che vi porta subito al bar sotto casa (bassa velocità, bassa latenza). Per navigare su internet, la latenza è cruciale: quando cliccate un link, il tempo che passa prima che la pagina inizi a caricarsi dipende dalla latenza, non dalla velocità. Per scaricare un file grande, invece, è più importante la velocità che la latenza.

### 5.2 Unità di misura delle velocità

**Velocità in bit per secondo:**

- bps (bit per secondo)
- Kbps = 1.000 bps
- Mbps = 1.000.000 bps
- Gbps = 1.000.000.000 bps

**Velocità in byte per secondo:**

- B/s (byte per secondo)
- KB/s = 1.000 B/s  
- MB/s = 1.000.000 B/s
- GB/s = 1.000.000.000 B/s

**Conversione rapida:**
Dividere i Mbps per 8 per ottenere MB/s approssimativi

### 5.3 Fattori che influenzano la velocità

**Fattori tecnici:**

- **Protocolli di rete**: TCP ha overhead maggiore di UDP
- **Congestione**: Troppe persone sulla stessa rete
- **Distanza fisica**: Più è lontano, maggiore la latenza
- **Qualità del mezzo**: Fibra > Rame > Wireless

**Fattori di sistema:**

- **CPU**: Deve elaborare i dati ricevuti
- **Memoria**: Buffer insufficiente rallenta il trasferimento
- **Storage**: Un HD lento non può tenere il passo
- **Software**: Antivirus e firewall aggiungono overhead

### 5.4 Tipi di connessioni e velocità tipiche

**Internet residenziale:**

- ADSL: 1-20 Mbps download, 0,5-1 Mbps upload
- Fibra FTTH: 100 Mbps - 1 Gbps simmetrico
- 4G/LTE: 10-100 Mbps (variabile)
- 5G: 100 Mbps - 1 Gbps (teorico)

**Reti locali:**

- Ethernet 100 Mbps: Standard vecchio
- Ethernet 1 Gbps: Standard attuale
- Wi-Fi 802.11n: ~150 Mbps reali
- Wi-Fi 802.11ac: ~300-500 Mbps reali

**Storage interno:**

- Hard disk tradizionale: 100-200 MB/s
- SSD SATA: 400-600 MB/s
- SSD NVMe: 1-7 GB/s
- RAM: 10-50 GB/s

### 5.5 Come misurare le velocità

**Test di velocità Internet:**

- Speedtest.net: Il più popolare
- Fast.com (Netflix): Test realistico per streaming
- Google Speed Test: Integrato nella ricerca

**Strumenti di sistema:**

- **Windows**: Task Manager → Prestazioni → Ethernet
- **macOS**: Activity Monitor → Network
- **Linux**: `iftop`, `nethogs`, `iotop`

**Interpretazione dei risultati:**

- Velocità di picco vs velocità sostenuta
- Upload vs download
- Latenza (ping) per gaming e videoconferenze

---

## 6. Codifica delle immagini

### 6.1 Da analogico a digitale

**Come l'occhio vede le immagini:**
L'occhio umano percepisce la luce come onde elettromagnetiche continue. Per digitalizzare un'immagine, dobbiamo:

1. **Campionare**: Dividere l'immagine in punti discreti (pixel)
2. **Quantizzare**: Assegnare valori numerici ai colori
3. **Codificare**: Tradurre in bit e byte

### 6.2 Pixel e risoluzione

**Il pixel: unità base**
Un **pixel** (picture element) è il più piccolo elemento di un'immagine digitale. È come un mattoncino colorato in un mosaico.

**Risoluzione spaziale:**

- **Definizione**: Numero di pixel per unità di misura
- **Immagini**: 1920×1080 = 2.073.600 pixel
- **Stampa**: 300 DPI (Dots Per Inch) = 300 pixel per pollice
- **Schermi**: 72-300 PPI (Pixels Per Inch)

**Esempi di risoluzioni:**

- HD: 1280×720 (921.600 pixel)
- Full HD: 1920×1080 (2.073.600 pixel)
- 4K: 3840×2160 (8.294.400 pixel)
- 8K: 7680×4320 (33.177.600 pixel)

### 6.3 Codifica dei colori

**Modello RGB (Red, Green, Blue)**
Ogni pixel contiene tre valori per i colori primari della luce:

**RGB a 24 bit (True Color):**

- 8 bit per il rosso (0-255)
- 8 bit per il verde (0-255)  
- 8 bit per il blu (0-255)
- Totale: 256³ = 16.777.216 colori

**Esempi di colori:**

- Rosso puro: RGB(255, 0, 0)
- Verde puro: RGB(0, 255, 0)
- Blu puro: RGB(0, 0, 255)
- Bianco: RGB(255, 255, 255)
- Nero: RGB(0, 0, 0)
- Giallo: RGB(255, 255, 0)

**Altri sistemi di colore:**

- **CMYK**: Per stampa (Cyan, Magenta, Yellow, Black)
- **HSV**: Hue, Saturation, Value (più intuitivo)
- **LAB**: Standard per la percezione umana

### 6.4 Formati di immagini non compressi

**Bitmap (BMP)**

- Formato più semplice
- 1 pixel = 3 byte (RGB)
- Dimensione = Larghezza × Altezza × 3 byte

**Calcolo dimensioni:**

- Foto 4000×3000 pixel
- 4000 × 3000 × 3 = 36.000.000 byte = 36 MB

**Raw/TIFF**

- Usati in fotografia professionale
- Possono includere più informazioni per pixel
- 48 bit (16 per canale) per qualità superiore

### 6.5 Compressione delle immagini

Ora arriviamo a uno dei problemi più grandi dell'era digitale: le immagini non compresse sono enormi! Per capire quanto, facciamo un calcolo concreto: una foto scattata con uno smartphone moderno da 12 megapixel, se fosse memorizzata senza alcuna compressione, occuperebbe circa 36 MB di spazio. Questo significa che in una memoria da 32 GB potreste salvare solo circa 900 foto - e stiamo parlando di una memoria abbastanza capiente! Ma il problema diventa gigantesco quando parliamo di video: un filmato in 4K non compresso occuperebbe circa 6 GB per ogni minuto di registrazione. Un film di due ore richiederebbe 720 GB di spazio, più di quanto può contenere un disco fisso di molti computer!

Per risolvere questo problema, gli informatici hanno sviluppato tecniche di compressione, che si dividono in due grandi categorie con filosofie completamente diverse.

La **compressione lossless** (senza perdite) è come avere un sistema di archiviazione perfetto: riuscite a comprimere i dati, ma quando li riaprite sono identici all'originale, senza aver perso nemmeno un pixel. Il formato **PNG** è perfetto per questo: se avete uno screenshot del vostro computer o un'immagine con grafiche nette e colori uniformi, il PNG può ridurre significativamente le dimensioni mantenendo una qualità perfetta. Il **GIF**, nonostante sia molto vecchio, è ancora usato per le animazioni semplici, anche se può rappresentare solo 256 colori diversi. Il **TIFF compresso** è lo standard nell'industria grafica professionale quando non ci si può permettere di perdere nemmeno il più piccolo dettaglio.

La **compressione lossy** (con perdite) è molto più aggressiva: butta via deliberatamente alcune informazioni dell'immagine originale per ottenere file molto più piccoli. Il principio è che l'occhio umano non riesce a percepire certe differenze, quindi perché sprecare spazio per memorizzarle? Il **JPEG** è il re assoluto di questa categoria: una foto che in formato non compresso occuperebbe 36 MB, in JPEG di buona qualità può essere ridotta a soli 2-3 MB, una riduzione di oltre il 90%! I formati più moderni come **WebP** (sviluppato da Google) e **HEIF** (usato da Apple sui nuovi iPhone) sono ancora più efficienti, riuscendo a ottenere la stessa qualità visiva con file ancora più piccoli.

### 6.6 Il formato JPEG nel dettaglio

**Come funziona JPEG:**

1. **Conversione RGB→YCbCr**: Separa luminanza e crominanza
2. **Sottocampionamento crominanza**: L'occhio è meno sensibile ai colori
3. **DCT (Discrete Cosine Transform)**: Analisi delle frequenze
4. **Quantizzazione**: Elimina dettagli impercettibili
5. **Codifica entropica**: Compressione finale

**Livelli di qualità JPEG:**

- 100%: Quasi senza perdite (~500 KB per foto tipica)
- 90%: Qualità eccellente (~200 KB)
- 70%: Qualità buona (~100 KB)
- 50%: Qualità accettabile (~50 KB)
- 10%: Qualità molto bassa (~20 KB)

**Artefatti JPEG:**

- **Blocking**: Quadretti visibili
- **Ringing**: Aloni attorno ai bordi
- **Color bleeding**: Sfocatura dei colori

### 6.7 Formati moderni e futuri

**WebP (Google)**

- 25-30% più efficiente di JPEG
- Supporta trasparenza e animazioni
- Adozione crescente sui browser

**AVIF (AV1 Image File Format)**

- Basato sul codec video AV1
- 50% più efficiente di JPEG
- Supporto browser ancora limitato

**HEIF/HEIC (Apple)**

- Standard su iPhone dal 2017
- Efficienza superiore a JPEG
- Supporto limitato su altre piattaforme

---

## 7. Codifica dei suoni

### 7.1 Da analogico a digitale

**Come funziona l'udito:**
L'orecchio umano percepisce le onde sonore come variazioni di pressione dell'aria. Il suono è analogico e continuo.

**Digitalizzazione del suono:**
Per convertire il suono in digitale dobbiamo:

1. **Campionare**: Misurare l'ampiezza del suono a intervalli regolari
2. **Quantizzare**: Convertire ogni misura in un numero
3. **Codificare**: Memorizzare i numeri in formato digitale

### 7.2 Campionamento audio

Il campionamento audio è l'operazione più importante e delicata nella digitalizzazione del suono. Immaginate di dover disegnare una curva continua, ma potendo usare solo punti isolati: più punti usate, più fedele sarà la vostra riproduzione della curva originale.

La **frequenza di campionamento** (Sample Rate) indica quante volte al secondo misuriamo l'intensità del suono. È come scattare foto rapidissime di un'onda sonora: più foto scattate al secondo, migliore sarà la qualità della riproduzione.

Le frequenze standard che incontrerete nella vita quotidiana hanno tutte una storia e una ragione precisa. La **telefonia** usa solo 8 kHz perché l'obiettivo è capire le parole, non godere della musica: è la qualità minima per distinguere le voci umane. La **radio AM** arriva a 22 kHz, offrendo una qualità accettabile per la musica ma non eccellente. Il **CD audio** usa 44,1 kHz, uno standard che ha rivoluzionato l'industria musicale negli anni '80: questa frequenza garantisce una riproduzione fedele di tutta la gamma sonora che l'orecchio umano può percepire. La **TV e i video** usano spesso 48 kHz per sincronizzarsi meglio con le immagini. L'**audio professionale** può spingersi a 96 kHz o addirittura 192 kHz per gli studi di registrazione più avanzati, anche se molti esperti dibattono se queste frequenze altissime siano realmente percettibili dall'orecchio umano.

Il principio scientifico dietro tutto questo è il **Teorema di Nyquist**, una legge fondamentale dell'elettronica che dice: per riprodurre fedelmente un suono, la frequenza di campionamento deve essere almeno il doppio della frequenza più alta del suono stesso. L'orecchio umano sente suoni da 20 Hz (bassi molto profondi) fino a 20.000 Hz (acuti molto alti), quindi teoricamente basterebbero 40.000 campioni al secondo. I CD usano 44.100 campioni al secondo (44,1 kHz) per avere un margine di sicurezza e garantire che anche i suoni più acuti siano riprodotti perfettamente.

### 7.3 Profondità in bit (Bit Depth)

**Risoluzione dell'ampiezza:**
Ogni campione viene rappresentato con un certo numero di bit:

**Profondità comuni:**

- **8 bit**: 256 livelli (qualità molto bassa)
- **16 bit**: 65.536 livelli (qualità CD)
- **24 bit**: 16.777.216 livelli (qualità professionale)
- **32 bit**: Per elaborazione in studio

**Rapporto segnale/rumore:**

- 16 bit: ~96 dB SNR
- 24 bit: ~144 dB SNR
- Soglia del dolore: ~120 dB

### 7.4 Calcolo delle dimensioni audio

**Formula base:**
Dimensione = Frequenza × Bit depth × Canali × Durata

**Esempio: CD Audio**

- Frequenza: 44.100 Hz
- Bit depth: 16 bit
- Canali: 2 (stereo)
- Durata: 60 secondi

Calcolo: 44.100 × 16 × 2 × 60 = 84.672.000 bit = 10.584.000 byte ≈ 10,1 MB

**Esempi pratici:**

- Canzone CD (4 min): ~42 MB
- Album CD (60 min): ~630 MB
- Audio professionale 24/96: ~345 MB per canzone

### 7.5 Formati audio non compressi

**WAV (Microsoft)**

- Standard Windows
- Supporta varie profondità e frequenze
- Nessuna compressione = qualità massima

**AIFF (Apple)**

- Equivalente Apple del WAV
- Standard su macOS
- Qualità identica al WAV

**FLAC (Free Lossless Audio Codec)**

- Compressione senza perdite
- Riduce le dimensioni del 30-50%
- Open source e royalty-free

### 7.6 Compressione audio lossy

L'MP3 è probabilmente il formato digitale più famoso al mondo, quello che ha rivoluzionato il modo in cui ascoltiamo musica. Ma come fa a comprimere una canzone da 50 MB a soli 5 MB mantenendo una qualità accettabile?

Il formato **MP3 (MPEG-1 Audio Layer 3)** si basa su un principio geniale chiamato analisi psicoacustica, che studia come il nostro orecchio e il nostro cervello percepiscono realmente i suoni. Gli ingegneri hanno scoperto che non tutti i suoni registrati sono effettivamente "sentiti" dal nostro orecchio: alcuni sono mascherati da altri più forti, alcuni sono troppo deboli per essere percepiti, altri sono fuori dalla gamma di frequenze che riusciamo a distinguere.

Il processo di compressione MP3 funziona in quattro fasi principali. Prima viene fatta un'**analisi psicoacustica** del file audio: un algoritmo "ascolta" la musica e identifica quali parti sono importanti per l'orecchio umano e quali possono essere eliminate senza che nessuno se ne accorga. Poi inizia il **mascheramento**: quando c'è un suono molto forte (come un colpo di tamburo), l'algoritmo elimina tutti i suoni più deboli che avvengono nello stesso momento, perché tanto il tamburo li coprirebbe completamente. Il terzo passo è la **quantizzazione**, dove l'algoritmo riduce la precisione matematica dei suoni meno importanti: è come usare meno colori per dipingere le parti meno visibili di un quadro. Infine, la **codifica Huffman** comprime ulteriormente i dati usando tecniche matematiche simili a quelle dei file ZIP.

I **livelli di qualità MP3** offrono diversi compromessi tra dimensione del file e fedeltà audio. A **320 kbps** (kilobit per secondo) ottenete la qualità massima dell'MP3, con file di circa 7,5 MB per una canzone tipica - molti audiofili considerano questa qualità indistinguibile dal CD originale. A **192 kbps** avete ancora un'ottima qualità con file da 4,5 MB, perfetta per l'ascolto quotidiano. Il livello **128 kbps**, che genera file da 3 MB, è stato lo standard per molti anni ed è ancora accettabile per la maggior parte delle situazioni. Scendendo a **96 kbps** (2,25 MB) la qualità diventa più limitata ma può andare bene per podcast o musica di sottofondo, mentre a **64 kbps** o meno si sentono chiaramente gli artefatti della compressione.

### 7.7 Formati audio moderni

**AAC (Advanced Audio Coding)**

- Successore dell'MP3
- 20-30% più efficiente
- Standard per iTunes, YouTube, streaming

**Ogg Vorbis**

- Open source
- Qualità superiore a MP3
- Supporto limitato sui dispositivi

**Opus**

- Formato più moderno
- Ottimo per VoIP e streaming
- Bassa latenza

### 7.8 Audio per applicazioni specifiche

**Streaming musicale:**

- Spotify: 320 kbps AAC/Ogg
- Apple Music: 256 kbps AAC
- Tidal: FLAC (qualità master)

**Telefonia VoIP:**

- Skype: Opus, 16-32 kbps
- WhatsApp: AMR-NB, 12,2 kbps
- Zoom: Opus, variabile

**Gaming:**

- Effetti sonori: WAV non compressi
- Musica: Ogg Vorbis
- Voce: Opus a basso bitrate

---

## 8. Laboratorio pratico e strumenti

### 8.1 Analisi di file multimediali

Il modo migliore per capire davvero la codifica dell'informazione è sporcarsi le mani e analizzare file reali. Fortunatamente esistono strumenti gratuiti che ci permettono di "guardare dentro" i file multimediali e scoprire tutti i loro segreti tecnici.

**MediaInfo** è il vostro migliore amico per questa attività: questo programma gratuito vi mostra tutto quello che c'è da sapere su qualsiasi file audio o video. Potete scaricarlo facilmente da internet e funziona su Windows, Mac e Linux. Quando aprite un file con MediaInfo, vi mostrerà informazioni dettagliate come la risoluzione di un video, il bitrate dell'audio, il formato di compressione usato, e molto altro. **ExifTool** è specializzato nei metadati delle immagini: vi può dire quando è stata scattata una foto, con quale modello di fotocamera, quali impostazioni sono state usate, e persino la posizione GPS se disponibile. Per i più curiosi, esistono anche gli **Hex Editor**, programmi che mostrano il contenuto "grezzo" di qualsiasi file come sequenze di numeri esadecimali - è come vedere il codice Matrix dietro ai vostri file!

Proviamo insieme un **esercizio pratico con una foto**. Prima di tutto, scattate una foto con il vostro smartphone (se non ne avete una a portata di mano, potete usare qualsiasi immagine digitale). Trasferite la foto sul computer e apritela con MediaInfo. Ora diventate dei detective digitali: osservate la risoluzione in pixel (per esempio 4000×3000), la profondità colore (probabilmente 24 bit), la dimensione del file (forse 3-5 MB) e il formato di compressione (probabilmente JPEG). A questo punto diventa interessante: calcolate quale sarebbe la dimensione teorica senza compressione moltiplicando larghezza × altezza × 3 byte (per i tre colori RGB). Se la foto è 4000×3000 pixel, il calcolo è 4000 × 3000 × 3 = 36.000.000 byte = 36 MB! Confrontate questo numero con la dimensione reale del file JPEG: probabilmente scoprirete che la compressione ha ridotto il file del 90% o più.

Facciamo lo stesso esperimento con un **file audio**. Scegliete una delle vostre canzoni preferite in formato MP3 e analizzatela con MediaInfo. Cercate informazioni come la frequenza di campionamento (probabilmente 44,1 kHz), il bitrate (forse 128, 192 o 320 kbps), la durata precisa in secondi e la dimensione totale del file. Ora potete fare alcuni calcoli interessanti: moltiplicando la durata in secondi per il bitrate in bit al secondo, otterrete il numero totale di bit del file. Poi potete stimare quanto occuperebbe la stessa canzone in formato WAV non compresso usando la formula che abbiamo imparato: 44.100 × 16 × 2 × durata_in_secondi ÷ 8 = dimensione in byte. Scoprirete che anche qui la compressione MP3 ha ridotto drasticamente le dimensioni!

### 8.2 Esperimenti di compressione

Ora che sapete analizzare i file, è arrivato il momento di sperimentare direttamente con la compressione. Questi esperimenti vi faranno capire in modo pratico i compromessi tra qualità e dimensioni dei file.

Per l'**esperimento con i formati immagine**, iniziate con una foto di buona qualità che vi piace particolarmente. Usando un programma di grafica come GIMP (gratuito) o anche semplicemente "Salva con nome" in molti programmi di visualizzazione immagini, salvate la stessa identica foto in formati diversi: BMP (completamente non compresso), PNG (compressione senza perdite), JPEG al 100% di qualità, JPEG al 50% di qualità, e JPEG al 10% di qualità. Ora osservate cosa succede: il file BMP sarà gigantesco, quello PNG significativamente più piccolo ma identico visivamente, mentre i JPEG diventeranno progressivamente più piccoli ma anche più "degradati". Aprite i file uno accanto all'altro e osservate attentamente: a che punto iniziate a notare la perdita di qualità? Molti rimangono sorpresi nello scoprire che JPEG al 70-80% è spesso indistinguibile dall'originale per l'occhio umano, pur essendo molto più piccolo.

L'**esperimento con i formati audio** è altrettanto illuminante ma richiede orecchie attente. Partite da un file audio di alta qualità, preferibilmente una canzone con molti dettagli sonori come musica classica o jazz. Convertite lo stesso brano in formati diversi: WAV (non compresso), FLAC (compressione senza perdite), MP3 a 320 kbps, MP3 a 128 kbps, e MP3 a 64 kbps. Ora fate un test di ascolto "alla cieca": chiedete a qualcuno di farvi sentire i file in ordine casuale senza dirvi qual è quale, e provate a indovinare la qualità. Potreste rimanere sorpresi nel scoprire che distinguere tra WAV e MP3 320 kbps è molto più difficile di quanto pensavate, soprattutto se non avete cuffie o altoparlanti di alta qualità. Questo esperimento vi farà capire perché molti servizi di streaming musicale usano bitrate relativamente bassi: per la maggior parte delle persone e delle situazioni d'ascolto, la differenza non è percettibile, ma il risparmio in termini di banda internet e spazio di archiviazione è enorme.

### 8.3 Calcoli pratici

La parte più divertente e utile del corso è quando applicate le conoscenze teoriche a situazioni reali che potreste incontrare nella vita quotidiana. Questi calcoli vi aiuteranno a fare scelte consapevoli quando acquistate dispositivi o servizi digitali.

Iniziamo con il **dimensionamento storage**, uno dei problemi più comuni nell'era degli smartphone e delle fotocamere digitali ad alta risoluzione. Supponiamo che vogliate comprare una scheda SD da 32 GB per il vostro smartphone e vi stiate chiedendo quante foto da 12 megapixel ci entrano. Facciamo i calcoli insieme: una foto da 12 MP in formato JPEG di buona qualità occupa tipicamente 3-4 MB. Con 32 GB di spazio (che in realtà sono circa 30 GB utilizzabili per via delle differenze tra GB decimali e binari), potete calcolare 30.000 MB ÷ 4 MB = 7.500 foto circa. Ma cosa succede se registrate video in 4K? Un minuto di video 4K può occupare 300-400 MB, quindi 30.000 MB ÷ 350 MB = circa 85 minuti di video, poco più di un'ora. Questi calcoli vi aiutano a capire se 32 GB sono sufficienti per le vostre esigenze o se vale la pena spendere di più per una memoria più capiente.

Passiamo alla **pianificazione bandwidth**, fondamentale nell'era dello streaming e del lavoro da casa. Se volete guardare Netflix in qualità 1080p, il servizio richiede circa 5-6 Mbps di banda costante. Se in casa siete in quattro persone che vogliono guardare contemporaneamente quattro film diversi, avrete bisogno di almeno 4 × 6 = 24 Mbps di connessione internet. Ma questo è solo per Netflix: aggiungete le videochiamate di lavoro (2-3 Mbps), il gaming online (1-2 Mbps), i backup automatici su cloud, e gli aggiornamenti di sistema, e capirete perché le connessioni da 100 Mbps stanno diventando sempre più comuni.

Un altro calcolo molto pratico riguarda i **tempi di upload**: se dovete caricare 100 foto da 5 MB ciascuna su Google Photos, e la vostra connessione ha 10 Mbps in upload, quanto tempo ci vorrà? Il calcolo è: 100 foto × 5 MB = 500 MB totali. Convertendo in bit: 500 MB × 8 = 4.000 Mbit. Con 10 Mbps di velocità, il tempo sarà 4.000 ÷ 10 = 400 secondi, circa 6-7 minuti. Ma attenzione: questa è la velocità teorica massima; in realtà potrebbe volerci di più a causa dell'overhead del protocollo e delle variazioni di velocità della connessione.

Infine, un calcolo molto attuale è il **traffico dati mensile** per lo streaming musicale. Se ascoltate Spotify 2 ore al giorno in qualità "High" (320 kbps), quanto consumate al mese? Il calcolo è: 320 kbps ÷ 8 = 40 KB/s, quindi 40 KB × 3600 secondi/ora × 2 ore × 30 giorni = 8.640.000 KB = circa 8,6 GB al mese. Se avete un piano dati da 20 GB, la musica in streaming vi consumerà quasi la metà del traffico disponibile!

---

**Siti web educativi:**

- [How Stuff Works - Computer](https://computer.howstuffworks.com/)
- [Khan Academy - Computing](https://www.khanacademy.org/computing)
- [Compress or Die](https://compress-or-die.com/): Test compressione immagini

## 🤔 Domande frequenti

**Q: Perché il mio HD da 1TB mostra solo 930GB?**
A: I produttori usano GB decimali (1000³), mentre il sistema operativo mostra GiB binari (1024³). Inoltre, parte dello spazio è riservata al file system.

**Q: È vero che la qualità 320kbps MP3 è indistinguibile dal CD?**
A: Per la maggior parte delle persone e situazioni sì, ma audiofili con ottimi sistemi possono notare differenze, specialmente su musica complessa.

**Q: Perché le foto del mio telefono sono così grandi?**
A: I sensori moderni catturano molti megapixel e i telefoni spesso salvano anche versioni elaborate. Potete ridurre la risoluzione nelle impostazioni.

**Q: Il 5G è davvero così veloce come pubblicizzato?**
A: Le velocità teoriche sono molto alte, ma quelle reali dipendono da copertura, traffico di rete e distanza dalle antenne.

