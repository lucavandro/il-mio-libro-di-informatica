# Calcolo numerico con Octave

> *"Il calcolo numerico è l'arte di risolvere problemi matematici usando algoritmi che i computer possono eseguire"* 🧮

## Introduzione

Octave è un potente linguaggio di programmazione open-source specializzato nel calcolo numerico e scientifico. È perfetto per risolvere sistemi di equazioni lineari, manipolare matrici, creare grafici e molto altro! 

In questo capitolo imparerai a:
- 🔢 Lavorare con le matrici e capire cosa rappresentano
- ⚖️ Convertire sistemi lineari dalla forma algebrica a quella matriciale
- � Creare grafici e visualizzazioni professionali
- �🛠️ Manipolare e operare con le matrici
- 🎯 Risolvere sistemi lineari usando diversi metodi
- 📐 Applicare il teorema di Rouchè-Capelli
- 📈 Implementare l'interpolazione lineare

---

## 1. Introduzione alle matrici

### 1.1 Cosa sono le matrici

Una **matrice** è come una "tabella di numeri" organizzata in righe e colonne 📊. Immagina una griglia dove ogni casella contiene un numero - ecco cos'è una matrice!

**Analogia pratica**: Una matrice è come:
- 🏢 Un palazzo di appartamenti: ogni piano (riga) e ogni appartamento (colonna) ha un inquilino (numero)
- 📋 Un foglio di calcolo Excel con celle numerate
- 🎯 Una mappa del tesoro dove ogni coordinata (riga, colonna) indica una posizione

**Notazione matematica:**
Una matrice **A** di dimensioni **m × n** (m righe, n colonne) si scrive:

```
A = [a₁₁  a₁₂  a₁₃  ...  a₁ₙ]
    [a₂₁  a₂₂  a₂₃  ...  a₂ₙ]
    [a₃₁  a₃₂  a₃₃  ...  a₃ₙ]
    [...  ...  ...  ...  ...]
    [aₘ₁  aₘ₂  aₘ₃  ...  aₘₙ]
```

Dove **aᵢⱼ** è l'elemento alla riga **i** e colonna **j**.

**Primi esempi in Octave:**

```octave
% Creare una matrice 2x3 (2 righe, 3 colonne)
A = [1, 2, 3; 4, 5, 6]

% Oppure, per maggiore leggibilità:
A = [1  2  3
     4  5  6]

% Visualizzare la matrice
disp('Matrice A:')
disp(A)

% Accedere all'elemento in posizione (2,3)
elemento = A(2,3)  % Risultato: 6

% Dimensioni della matrice
[righe, colonne] = size(A)
disp(['Dimensioni: ', num2str(righe), 'x', num2str(colonne)])
```

### 1.2 Rappresentazione e notazione

**Convenzioni di notazione:**

1. **Maiuscole** per le matrici: A, B, C, X, Y
2. **Minuscole** per gli elementi: aᵢⱼ, bᵢⱼ, xᵢ
3. **Indici**: primo indice = riga, secondo indice = colonna

**Esempi pratici:**

```octave
% Matrice 3x3 con numeri consecutivi
M = [1  2  3
     4  5  6
     7  8  9]

% Accesso agli elementi
primo_elemento = M(1,1)      % 1
ultimo_elemento = M(3,3)     % 9
elemento_centrale = M(2,2)   % 5

% Accesso a righe e colonne intere
prima_riga = M(1,:)          % [1 2 3]
seconda_colonna = M(:,2)     % [2; 5; 8]

% Sotto-matrice
sotto_matrice = M(1:2, 2:3)  % [2 3; 5 6]
```

**Importante** 🚨: In Octave gli indici iniziano da 1, non da 0 (diversamente da Python)!

### 1.3 Tipi di matrici speciali

#### **Matrice Quadrata** (n × n)
Stesso numero di righe e colonne:

```octave
% Matrice quadrata 3x3
Quadrata = [1  2  3
            4  5  6
            7  8  9]
```

#### **Matrice Identità** (I)
Tutti 1 sulla diagonale principale, 0 altrove:

```octave
% Matrice identità 3x3
I = eye(3)
% Risultato:
% [1  0  0]
% [0  1  0]
% [0  0  1]

% Matrice identità di dimensione n
n = 5;
I_5 = eye(n)
```

#### **Matrice Zero**
Tutti elementi uguali a 0:

```octave
% Matrice di zeri 2x4
Z = zeros(2, 4)

% Matrice di zeri quadrata 3x3
Z_quad = zeros(3)
```

#### **Matrice Diagonale**
Solo elementi sulla diagonale principale:

```octave
% Creare matrice diagonale da un vettore
diagonale = [2, 5, -1, 3];
D = diag(diagonale)
% Risultato:
% [2   0   0   0]
% [0   5   0   0]
% [0   0  -1   0]
% [0   0   0   3]

% Estrarre la diagonale da una matrice
M = [1  2  3; 4  5  6; 7  8  9];
diag_estratta = diag(M)  % [1; 5; 9]
```

#### **Matrice Triangolare**

```octave
% Matrice triangolare superiore
A = [1  2  3  4
     0  5  6  7
     0  0  8  9
     0  0  0  10]

% Estrarre parte triangolare superiore da una matrice
M = rand(4);  % Matrice casuale 4x4
Sup = triu(M)  % Triangolare superiore
Inf = tril(M)  % Triangolare inferiore
```

### 1.4 Prime operazioni in Octave

#### **Creazione di matrici**

```octave
% Metodi diversi per creare matrici
A = [1, 2; 3, 4]                    % Definizione diretta
B = zeros(2, 3)                     % Matrice di zeri
C = ones(3, 2)                      % Matrice di uni
D = eye(4)                          % Matrice identità
E = rand(3, 3)                      % Matrice casuale [0,1]
F = randn(2, 4)                     % Matrice casuale normale
G = magic(3)                        % Quadrato magico

% Sequenze e range
H = 1:5                             % Vettore riga [1 2 3 4 5]
I = (1:2:10)'                       % Vettore colonna [1; 3; 5; 7; 9]
J = linspace(0, 10, 5)              % 5 punti da 0 a 10
```

#### **Informazioni sulla matrice**

```octave
A = [1  2  3  4
     5  6  7  8
     9 10 11 12]

% Dimensioni
[m, n] = size(A)        % m=3, n=4
num_elementi = numel(A)  % 12 elementi totali
num_righe = size(A, 1)   % 3 righe
num_colonne = size(A, 2) % 4 colonne

% Controlli logici
is_square = (size(A,1) == size(A,2))    % false
is_empty = isempty(A)                    % false
is_vector = isvector(A)                  % false
```

#### **Manipolazione base**

```octave
% Trasposta
A = [1  2  3
     4  5  6]
A_trasposta = A'        % o transpose(A)
% Risultato:
% [1  4]
% [2  5]
% [3  6]

% Concatenazione
B = [7  8  9
     10 11 12]

% Concatenazione verticale
C = [A; B]              % 4x3

% Concatenazione orizzontale  
D = [A, B]              % 2x6

% Reshape (cambiare forma mantenendo gli elementi)
E = reshape(A, 3, 2)    % Da 2x3 a 3x2
F = A(:)                % Vettore colonna con tutti gli elementi
```

**Esercizio pratico** 💪:

```octave
% Crea una matrice 4x4 che contenga:
% - Sulla diagonale principale: i numeri da 1 a 4
% - Sopra la diagonale: tutti 2
% - Sotto la diagonale: tutti -1

% Soluzione:
M = diag(1:4) + 2*triu(ones(4), 1) - 1*tril(ones(4), -1)
disp(M)
```

**Curiosità** 🧠: Le matrici sono fondamentali in computer grafica! Ogni rotazione, traslazione o ridimensionamento di un'immagine 3D viene fatto moltiplicando per matrici speciali!

## 2. Dai sistemi lineari alle matrici

### 2.1 Sistemi di equazioni lineari: richiamo teorico

Un **sistema di equazioni lineari** è un insieme di equazioni dove ogni equazione è di primo grado. 📐

**Esempio della vita reale** 🛒: Problema del fruttivendolo

Immagina di andare dal fruttivendolo per tre giorni consecutivi:

- 2 mele + 3 pere + 1 arancia costano 10€
- 1 mela + 2 pere + 3 arance costano 11€  
- 3 mele + 1 pera + 2 arance costano 12€

Come trovare il prezzo di ogni frutto? 🤔

**Forma generale di un sistema lineare:**

```
a₁₁x₁ + a₁₂x₂ + ... + a₁ₙxₙ = b₁
a₂₁x₁ + a₂₂x₂ + ... + a₂ₙxₙ = b₂
...
aₘ₁x₁ + aₘ₂x₂ + ... + aₘₙxₙ = bₘ
```

**Possibili soluzioni:**

- 🎯 **Unica soluzione**: Il sistema ha esattamente una soluzione
- ♾️ **Infinite soluzioni**: Il sistema ha infinite soluzioni (ridondante)
- ❌ **Nessuna soluzione**: Il sistema è impossibile (contraddittorio)

**Condizioni geometriche (per 2 equazioni in 2 incognite):**

```
Unica soluzione:    Due rette che si intersecano in un punto
Infinite soluzioni: Due rette coincidenti  
Nessuna soluzione:  Due rette parallele
```

```octave
% Esempio pratico: Sistema del fruttivendolo
% Variabili: x1 = prezzo mele, x2 = prezzo pere, x3 = prezzo arance

% Sistema in forma estesa:
% 2x1 + 3x2 + 1x3 = 10
% 1x1 + 2x2 + 3x3 = 11
% 3x1 + 1x2 + 2x3 = 12

fprintf('=== SISTEMA DEL FRUTTIVENDOLO ===\n');
fprintf('Trova i prezzi di mele, pere e arance!\n\n');

% Risoluzione diretta in Octave (anticipiamo la forma matriciale)
A = [2  3  1
     1  2  3  
     3  1  2];
     
b = [10; 11; 12];

% Risoluzione (spiegheremo questo metodo più avanti)
prezzi = A \ b;

fprintf('Prezzi trovati:\n');
fprintf('Mele: %.2f €/kg\n', prezzi(1));
fprintf('Pere: %.2f €/kg\n', prezzi(2));
fprintf('Arance: %.2f €/kg\n', prezzi(3));

% Verifica: sostituiamo nella prima equazione
verifica1 = 2*prezzi(1) + 3*prezzi(2) + 1*prezzi(3);
fprintf('\nVerifica prima equazione: %.2f = 10.00 ✓\n', verifica1);
```

### 2.2 Dalla forma algebrica alla forma matriciale

La **magia** delle matrici è che ci permettono di scrivere un sistema di equazioni in modo compatto! ✨

**Trasformazione passo-passo:**

**Forma algebrica** (quella che conosciamo):
```
2x + 3y + z = 10
x + 2y + 3z = 11
3x + y + 2z = 12
```

**Forma matriciale** (più compatta):
```
Ax = b
```

Dove:
- **A** = matrice dei coefficienti
- **x** = vettore delle incognite  
- **b** = vettore dei termini noti

```octave
% Trasformazione completa: da algebrico a matriciale
function demo_trasformazione()
    fprintf('=== TRASFORMAZIONE ALGEBRICO → MATRICIALE ===\n');
    
    % Sistema originale
    fprintf('Sistema algebrico:\n');
    fprintf('2x + 3y + z = 10\n');
    fprintf('x + 2y + 3z = 11\n');
    fprintf('3x + y + 2z = 12\n\n');
    
    % Estrazione componenti
    fprintf('PASSO 1: Identifica i coefficienti\n');
    
    % Matrice A (coefficienti delle variabili)
    A = [2  3  1    % coefficienti della prima equazione
         1  2  3    % coefficienti della seconda equazione  
         3  1  2];  % coefficienti della terza equazione
         
    fprintf('Matrice A (coefficienti):\n');
    disp(A);
    
    % Vettore x (incognite)
    fprintf('Vettore x (incognite): [x; y; z]\n\n');
    
    % Vettore b (termini noti)
    b = [10; 11; 12];
    fprintf('Vettore b (termini noti):\n');
    disp(b);
    
    fprintf('PASSO 2: Verifica Ax = b\n');
    
    % Soluzione
    x = A \ b;
    fprintf('Soluzione: x = [%.3f; %.3f; %.3f]\n', x(1), x(2), x(3));
    
    % Verifica moltiplicando Ax
    prodotto = A * x;
    fprintf('Verifica Ax:\n');
    disp(prodotto);
    
    fprintf('Confronto Ax vs b:\n');
    for i = 1:3
        fprintf('Equazione %d: %.6f ≈ %.6f ✓\n', i, prodotto(i), b(i));
    end
end

demo_trasformazione();
```

**Vantaggi della forma matriciale:** 💪

1. **Compattezza**: Un sistema di 1000 equazioni si scrive sempre come Ax = b
2. **Algoritmi**: Computer molto efficienti con le matrici
3. **Teoria**: Possiamo usare l'algebra lineare per analizzare il sistema
4. **Generalità**: Stessi metodi per sistemi di qualsiasi dimensione

```octave
% Esempio: Sistema grande (10x10)
function sistema_grande()
    fprintf('=== SISTEMA GRANDE (10x10) ===\n');
    
    n = 10;
    
    % Genera sistema casuale ma ben condizionato
    rng(42);  % Per riproducibilità
    A = randn(n, n) + 5*eye(n);  % Matrice dominante sulla diagonale
    x_vero = ones(n, 1);         % Soluzione nota
    b = A * x_vero;              % Calcola i termini noti
    
    % Risolvi il sistema
    tic;
    x_calcolato = A \ b;
    tempo = toc;
    
    % Calcola l'errore
    errore = norm(x_calcolato - x_vero);
    
    fprintf('Dimensioni sistema: %dx%d\n', n, n);
    fprintf('Tempo di risoluzione: %.6f secondi\n', tempo);
    fprintf('Errore numerico: %.2e\n', errore);
    fprintf('Soluzione corretta? %s\n', mat2str(errore < 1e-10));
    
    % Confronto primi 5 elementi
    fprintf('\nConfronto (primi 5 elementi):\n');
    fprintf('Vero     Calcolato    Errore\n');
    for i = 1:5
        fprintf('%.6f  %.6f    %.2e\n', x_vero(i), x_calcolato(i), abs(x_vero(i) - x_calcolato(i)));
    end
end

sistema_grande();
```

## 3. Visualizzazione e plotting in Octave

### 3.1 Grafici base: plot e figure

Il **plotting** è essenziale nel calcolo numerico! 📊 Vedere i dati aiuta a capire meglio i risultati e a individuare errori.

#### **Comandi fondamentali per il plotting**

```octave
% === GRAFICI BASE IN OCTAVE ===
close all;  % Chiude tutte le figure aperte
clear;      % Pulisce il workspace

% 1. GRAFICO SEMPLICE
fprintf('=== GRAFICO SEMPLICE ===\n');

% Dati di esempio: funzione seno
x = linspace(0, 2*pi, 100);  % 100 punti da 0 a 2π
y = sin(x);

% Creare una figura
figure(1);
plot(x, y);
title('Funzione Seno');
xlabel('x (radianti)');
ylabel('sin(x)');
grid on;  % Aggiunge la griglia

fprintf('Creato grafico della funzione seno\n');

% 2. MULTIPLE FUNZIONI SULLO STESSO GRAFICO
fprintf('\n=== MULTIPLE FUNZIONI ===\n');

figure(2);
y1 = sin(x);
y2 = cos(x);
y3 = sin(x) .* cos(x);  % Prodotto (nota il punto prima di *)

plot(x, y1, 'b-', 'LineWidth', 2, 'DisplayName', 'sin(x)');
hold on;  % Mantiene il grafico precedente
plot(x, y2, 'r--', 'LineWidth', 2, 'DisplayName', 'cos(x)');
plot(x, y3, 'g:', 'LineWidth', 2, 'DisplayName', 'sin(x)·cos(x)');
hold off;

title('Confronto Funzioni Trigonometriche');
xlabel('x (radianti)');
ylabel('Valore');
legend('Location', 'best');  % Aggiunge la legenda
grid on;

fprintf('Creato grafico con multiple funzioni\n');

% 3. PERSONALIZZAZIONE AVANZATA
fprintf('\n=== PERSONALIZZAZIONE ===\n');

figure(3);
% Dati: polinomio con rumore
x_data = linspace(-2, 2, 20);
y_true = x_data.^3 - 2*x_data.^2 + x_data + 1;
noise = 0.5 * randn(size(x_data));  % Rumore gaussiano
y_noisy = y_true + noise;

% Grafico dei dati sperimentali
plot(x_data, y_noisy, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', ...
     'DisplayName', 'Dati sperimentali');
hold on;

% Fit polinomiale
p = polyfit(x_data, y_noisy, 3);  % Polinomio di grado 3
x_smooth = linspace(-2, 2, 200);
y_fit = polyval(p, x_smooth);

plot(x_smooth, y_fit, 'b-', 'LineWidth', 2, 'DisplayName', 'Fit polinomiale');

% Personalizzazioni
title('Fitting Polinomiale con Dati Rumorosi', 'FontSize', 14, 'FontWeight', 'bold');
xlabel('x', 'FontSize', 12);
ylabel('y', 'FontSize', 12);
legend('Location', 'best', 'FontSize', 11);
grid on;

% Aggiungere annotazioni
text(-1.5, 3, sprintf('R² = %.3f', corr(y_noisy, polyval(p, x_data))^2), ...
     'FontSize', 12, 'BackgroundColor', 'yellow');

fprintf('Creato grafico con personalizzazioni avanzate\n');
```

#### **Stili di linea e marcatori**

```octave
% Guida completa agli stili di plotting
function guida_stili_plotting()
    fprintf('\n=== GUIDA STILI DI PLOTTING ===\n');
    
    figure('Position', [100, 100, 1000, 600]);
    
    % Dati di esempio
    x = linspace(0, 10, 50);
    
    % Subplot per organizzare multiple grafici
    subplot(2, 3, 1);  % 2 righe, 3 colonne, posizione 1
    
    % STILI DI LINEA
    plot(x, sin(x), '-', 'LineWidth', 2, 'DisplayName', 'Continua (-)');
    hold on;
    plot(x, sin(x-0.5), '--', 'LineWidth', 2, 'DisplayName', 'Tratteggiata (--)');
    plot(x, sin(x-1), ':', 'LineWidth', 2, 'DisplayName', 'Punteggiata (:)');
    plot(x, sin(x-1.5), '-.', 'LineWidth', 2, 'DisplayName', 'Tratto-punto (-.)');
    title('Stili di Linea');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 2);
    % COLORI
    plot(x, cos(x), 'b-', 'LineWidth', 2, 'DisplayName', 'Blu (b)');
    hold on;
    plot(x, cos(x-0.5), 'r-', 'LineWidth', 2, 'DisplayName', 'Rosso (r)');
    plot(x, cos(x-1), 'g-', 'LineWidth', 2, 'DisplayName', 'Verde (g)');
    plot(x, cos(x-1.5), 'm-', 'LineWidth', 2, 'DisplayName', 'Magenta (m)');
    plot(x, cos(x-2), 'k-', 'LineWidth', 2, 'DisplayName', 'Nero (k)');
    title('Colori Base');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 3);
    % MARCATORI
    x_sparse = linspace(0, 10, 20);  % Meno punti per vedere i marcatori
    plot(x_sparse, sin(x_sparse), 'o-', 'MarkerSize', 6, 'DisplayName', 'Cerchi (o)');
    hold on;
    plot(x_sparse, sin(x_sparse-0.5), 's-', 'MarkerSize', 6, 'DisplayName', 'Quadrati (s)');
    plot(x_sparse, sin(x_sparse-1), '^-', 'MarkerSize', 6, 'DisplayName', 'Triangoli (^)');
    plot(x_sparse, sin(x_sparse-1.5), 'd-', 'MarkerSize', 6, 'DisplayName', 'Diamanti (d)');
    title('Tipi di Marcatori');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 4);
    % COLORI PERSONALIZZATI (RGB)
    plot(x, exp(-x/5).*cos(x), 'Color', [0.8, 0.2, 0.6], 'LineWidth', 3, 'DisplayName', 'RGB [0.8,0.2,0.6]');
    hold on;
    plot(x, exp(-x/5).*sin(x), 'Color', [0.1, 0.7, 0.3], 'LineWidth', 3, 'DisplayName', 'RGB [0.1,0.7,0.3]');
    title('Colori RGB Personalizzati');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 5);
    % TRASPARENZA (Alpha)
    area(x, exp(-x/8), 'FaceColor', 'blue', 'FaceAlpha', 0.3, 'DisplayName', 'Area trasparente');
    hold on;
    plot(x, exp(-x/8), 'b-', 'LineWidth', 2, 'DisplayName', 'Linea bordo');
    title('Trasparenza e Aree');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 6);
    % STILI COMBINATI
    errorbar(x_sparse, sin(x_sparse), 0.1*ones(size(x_sparse)), 'ro-', ...
             'MarkerSize', 6, 'MarkerFaceColor', 'red', 'LineWidth', 1.5, ...
             'DisplayName', 'Dati con errore');
    title('Barre di Errore');
    legend('Location', 'best');
    grid on;
    
    % Titolo generale
    sgtitle('Guida Completa agli Stili di Plotting in Octave', 'FontSize', 16, 'FontWeight', 'bold');
    
    fprintf('Creata guida completa agli stili di plotting\n');
end

guida_stili_plotting();
```

**🎯 Riassunto skills di plotting acquisite:**

### ✅ **Competenze di visualizzazione completate:**

1. **Grafici base** 📊
   - `plot()`, `figure()`, personalizzazione stili
   - Linee, colori, marcatori, leggende

2. **Personalizzazione avanzata** 🎨
   - Titoli, etichette, annotazioni
   - Colori RGB, trasparenza, subplot

3. **Applicazioni immediate** 🚀
   - Visualizzazione funzioni matematiche
   - Fitting polinomiali con dati rumorosi
   - Confronto di multiple funzioni

Ora gli studenti possono creare visualizzazioni di base per i loro calcoli numerici! 📊✨

### 2.1 Sistemi di equazioni lineari: richiamo teorico

Un **sistema di equazioni lineari** è un insieme di equazioni dove ogni incognita compare solo al primo grado (niente x², √x, o altre operazioni complesse) 📐.

**Forma generale di un sistema lineare:**

```
a₁₁x₁ + a₁₂x₂ + a₁₃x₃ + ... + a₁ₙxₙ = b₁
a₂₁x₁ + a₂₂x₂ + a₂₃x₃ + ... + a₂ₙxₙ = b₂
a₃₁x₁ + a₃₂x₂ + a₃₃x₃ + ... + a₃ₙxₙ = b₃
...
aₘ₁x₁ + aₘ₂x₂ + aₘ₃x₃ + ... + aₘₙxₙ = bₘ
```

**Esempio concreto** 🎯:
Immagina di voler trovare il prezzo di mele, pere e arance sapendo che:
- 2 mele + 3 pere + 1 arancia costano 10€
- 1 mela + 1 pera + 2 arance costano 8€  
- 3 mele + 2 pere + 1 arancia costano 12€

Chiamando x₁ = prezzo mela, x₂ = prezzo pera, x₃ = prezzo arancia:

```
2x₁ + 3x₂ + 1x₃ = 10
1x₁ + 1x₂ + 2x₃ = 8
3x₁ + 2x₂ + 1x₃ = 12
```

**Tipi di soluzioni:**
- 🎯 **Unica soluzione**: Il sistema ha esattamente una soluzione
- ♾️ **Infinite soluzioni**: Il sistema ha infinite soluzioni (sistema sottodeterminato)
- ❌ **Nessuna soluzione**: Il sistema è impossibile (sistema incompatibile)

### 2.2 Dalla forma algebrica alla forma matriciale

Il "trucco" geniale è trasformare il sistema in una moltiplicazione tra matrici! 🧩

**Passo 1**: Separare i coefficienti dalle incognite e dai termini noti

Dal sistema:
```
2x₁ + 3x₂ + 1x₃ = 10
1x₁ + 1x₂ + 2x₃ = 8
3x₁ + 2x₂ + 1x₃ = 12
```

**Passo 2**: Organizzare in tre matrici

**Matrice dei coefficienti A:**
```
A = [2  3  1]
    [1  1  2]
    [3  2  1]
```

**Vettore delle incognite x:**
```
x = [x₁]
    [x₂]
    [x₃]
```

**Vettore dei termini noti b:**
```
b = [10]
    [8]
    [12]
```

**Passo 3**: Scrivere in forma matriciale
```
A · x = b
```

**Implementazione in Octave:**

```octave
% Definire il sistema dell'esempio (mele, pere, arance)
A = [2  3  1
     1  1  2
     3  2  1]

x = sym('x', [3, 1])  % Vettore simbolico delle incognite

b = [10
     8
     12]

% Visualizzare il sistema
disp('Matrice dei coefficienti A:')
disp(A)
disp('Vettore delle incognite x:')
disp(x)
disp('Vettore dei termini noti b:')
disp(b)

% Verifica: A*x dovrebbe dare le equazioni originali
disp('Moltiplicazione A*x (forma simbolica):')
risultato = A * x
```

**Esempio passo-passo di conversione:**

```octave
% Sistema più semplice: 2 equazioni, 2 incognite
% 3x + 2y = 7
% x - y = 1

% Forma matriciale:
A_semplice = [3   2
              1  -1]

b_semplice = [7
              1]

disp('Sistema semplice 2x2:')
disp('3x + 2y = 7')
disp(' x -  y = 1')
disp('')
disp('In forma matriciale A*x = b:')
disp('A ='), disp(A_semplice)
disp('b ='), disp(b_semplice)
```

### 2.3 Interpretazione geometrica

La forma matriciale non è solo un trucco algebrico - ha un **significato geometrico profondo**! 🌌

**Per sistemi 2×2:**
- Ogni equazione rappresenta una **retta** nel piano
- La soluzione è il **punto di intersezione** delle rette

**Per sistemi 3×3:**
- Ogni equazione rappresenta un **piano** nello spazio 3D
- La soluzione è il **punto** dove si intersecano tutti i piani

**Visualizzazione in Octave:**

```octave
% Visualizzare il sistema 2x2 geometricamente
% 3x + 2y = 7
% x - y = 1

% Definire il range di x
x_vals = linspace(-2, 4, 100);

% Prima equazione: 3x + 2y = 7 → y = (7-3x)/2
y1 = (7 - 3*x_vals) / 2;

% Seconda equazione: x - y = 1 → y = x - 1
y2 = x_vals - 1;

% Grafico
figure;
plot(x_vals, y1, 'b-', 'LineWidth', 2, 'DisplayName', '3x + 2y = 7');
hold on;
plot(x_vals, y2, 'r-', 'LineWidth', 2, 'DisplayName', 'x - y = 1');

% Trova e marca il punto di intersezione
A_plot = [3  2; 1 -1];
b_plot = [7; 1];
soluzione = A_plot \ b_plot;  % Risoluzione del sistema

plot(soluzione(1), soluzione(2), 'ko', 'MarkerSize', 10, 'MarkerFaceColor', 'green');
text(soluzione(1)+0.1, soluzione(2)+0.1, sprintf('(%.2f, %.2f)', soluzione(1), soluzione(2)));

grid on;
legend;
title('Interpretazione Geometrica del Sistema Lineare');
xlabel('x');
ylabel('y');
axis equal;
```

**Casi particolari geometrici:**

```octave
% Caso 1: Sistema con soluzione unica (rette che si intersecano)
A1 = [1  1; 2 -1];
b1 = [3; 1];

% Caso 2: Sistema impossibile (rette parallele)
A2 = [1  2; 2  4];  % Seconda riga = 2 * prima riga
b2 = [3; 5];        % Ma 5 ≠ 2*3, quindi impossibile

% Caso 3: Infinite soluzioni (rette coincidenti)
A3 = [1  2; 2  4];  % Seconda riga = 2 * prima riga  
b3 = [3; 6];        % E 6 = 2*3, quindi coincidenti

% Test dei casi
disp('Caso 1 - Soluzione unica:')
if rank(A1) == rank([A1, b1]) && rank(A1) == size(A1, 2)
    sol1 = A1 \ b1;
    disp(['Soluzione: x = ', num2str(sol1(1)), ', y = ', num2str(sol1(2))])
end

disp('Caso 2 - Sistema impossibile:')
if rank(A2) ~= rank([A2, b2])
    disp('Il sistema non ha soluzioni!')
end

disp('Caso 3 - Infinite soluzioni:')
if rank(A3) == rank([A3, b3]) && rank(A3) < size(A3, 2)
    disp('Il sistema ha infinite soluzioni!')
end
```

### 2.4 Esempi pratici di conversione

#### **Esempio 1: Problema di miscelazione** 🧪

*In un laboratorio dobbiamo preparare 3 soluzioni miscelando 4 sostanze chimiche. Convertire in forma matriciale:*

```
Soluzione 1: 2A + 3B + 1C + 0D = 100ml
Soluzione 2: 1A + 1B + 2C + 1D = 150ml  
Soluzione 3: 0A + 2B + 1C + 3D = 200ml
```

```octave
% Matrice dei coefficienti (3 equazioni, 4 incognite)
A_lab = [2  3  1  0
         1  1  2  1
         0  2  1  3]

% Vettore dei termini noti (volumi desiderati)
b_lab = [100
         150
         200]

% Vettore delle incognite: [A; B; C; D]
disp('Sistema di miscelazione in forma matriciale:')
disp('A ='), disp(A_lab)
disp('b ='), disp(b_lab)
disp('Incognite: A, B, C, D (quantità delle 4 sostanze)')
```

#### **Esempio 2: Analisi di un circuito elettrico** ⚡

*Trovare le correnti in un circuito usando le leggi di Kirchhoff:*

```
Maglia 1: 5I₁ + 3I₂ + 0I₃ = 12V
Maglia 2: 3I₁ + 8I₂ + 2I₃ = 8V
Nodo:    I₁ - I₂ - I₃ = 0A
```

```octave
% Sistema per l'analisi del circuito
A_circuito = [5   3   0
              3   8   2  
              1  -1  -1]

b_circuito = [12
              8
              0]

disp('Analisi circuito elettrico:')
disp('A ='), disp(A_circuito)
disp('b ='), disp(b_circuito)

% Risoluzione
I = A_circuito \ b_circuito;
disp('Correnti nel circuito:')
fprintf('I1 = %.3f A\n', I(1))
fprintf('I2 = %.3f A\n', I(2))  
fprintf('I3 = %.3f A\n', I(3))
```

#### **Esempio 3: Bilanciamento di equazioni chimiche** ⚗️

*Bilanciare la reazione: aH₂ + bO₂ → cH₂O*

Le equazioni di conservazione degli atomi diventano:
```
Idrogeno (H): 2a + 0b - 2c = 0
Ossigeno (O): 0a + 2b - 1c = 0
```

```octave
% Sistema per bilanciamento chimico
% Aggiungiamo a = 1 per fissare la scala
A_chimica = [2   0  -2
             0   2  -1
             1   0   0]  % a = 1

b_chimica = [0
             0  
             1]  % a = 1

disp('Bilanciamento equazione chimica H2 + O2 → H2O:')
coefficienti = A_chimica \ b_chimica;
fprintf('Coefficienti: %.0fH2 + %.0fO2 → %.0fH2O\n', coefficienti(1), coefficienti(2), coefficienti(3))
```

**Trucco per la conversione** 💡:
1. **Identifica le incognite** (cosa devi trovare?)
2. **Scrivi le equazioni** in forma standard (tutto a sinistra = termine noto)
3. **Estrai i coefficienti** riga per riga
4. **Organizza in matrici** A, x, b
5. **Verifica** che A·x = b rappresenti il sistema originale

## 4. Operazioni con le matrici

### 4.1 Operazioni elementari (somma, sottrazione, moltiplicazione)

Le operazioni con le matrici seguono regole precise che inizialmente possono sembrare strane, ma hanno un senso profondo! 🧮

#### **Somma e Sottrazione di Matrici**

**Regola**: Si possono sommare/sottrarre solo matrici della **stessa dimensione**, elemento per elemento.

```octave
% Somma di matrici 2x3
A = [1  2  3
     4  5  6]

B = [2  1  0
     -1 3  2]

% Somma elemento per elemento
C = A + B
% Risultato:
% [3  3  3]
% [3  8  8]

% Sottrazione
D = A - B  
% Risultato:
% [-1  1  3]
% [ 5  2  4]

% Verifica delle dimensioni
disp(['Dimensioni A: ', num2str(size(A))])
disp(['Dimensioni B: ', num2str(size(B))])
disp('Le matrici hanno stesse dimensioni: somma possibile!')
```

**Importante** ⚠️: Non puoi sommare una matrice 2×3 con una 3×2!

```octave
% Esempio di errore
A = [1 2 3; 4 5 6];    % 2x3
E = [1; 2; 3];          % 3x1

% Questa operazione darà errore:
% F = A + E;  % ERRORE: dimensioni incompatibili
```

#### **Moltiplicazione per uno scalare**

Moltiplica ogni elemento della matrice per il numero:

```octave
% Moltiplicazione per scalare
A = [1  2
     3  4]

% Moltiplicare per 3
B = 3 * A
% Risultato:
% [3   6]
% [9  12]

% Funziona anche con numeri decimali
C = 0.5 * A
% Risultato:
% [0.5  1.0]
% [1.5  2.0]

% Operazioni combinate
D = 2*A + 3*B - C
```

#### **Moltiplicazione tra Matrici**

La moltiplicazione tra matrici è **l'operazione più importante** ma anche la più "strana"! 🤯

**Regola**: Per moltiplicare A×B, il **numero di colonne di A** deve uguale al **numero di righe di B**.

```
A(m×n) × B(n×p) = C(m×p)
```

**Come si calcola:**
L'elemento C(i,j) è il prodotto scalare della riga i di A per la colonna j di B.

```octave
% Esempio passo-passo
A = [1  2  3
     4  5  6]    % 2x3

B = [7   8
     9  10
    11  12]      % 3x2

% A×B è possibile (3 colonne di A = 3 righe di B)
C = A * B
% Risultato sarà 2x2

% Calcolo manuale dell'elemento C(1,1):
% C(1,1) = 1*7 + 2*9 + 3*11 = 7 + 18 + 33 = 58

% Calcolo manuale dell'elemento C(1,2):  
% C(1,2) = 1*8 + 2*10 + 3*12 = 8 + 20 + 36 = 64

% Verifica in Octave
disp('Moltiplicazione A*B:')
disp(C)

% Nota: B*A NON è possibile! (2 colonne di B ≠ 2 righe di A)
% D = B * A;  % ERRORE!
```

**Visualizzazione della moltiplicazione:**

```octave
% Funzione per visualizzare la moltiplicazione step-by-step
function visualizza_moltiplicazione(A, B)
    [m, n] = size(A);
    [n2, p] = size(B);
    
    if n ~= n2
        error('Dimensioni incompatibili per la moltiplicazione');
    end
    
    C = A * B;
    
    fprintf('A (%dx%d) × B (%dx%d) = C (%dx%d)\n\n', m, n, n2, p, m, p);
    
    for i = 1:m
        for j = 1:p
            fprintf('C(%d,%d) = ', i, j);
            somma = 0;
            for k = 1:n
                if k > 1, fprintf(' + '); end
                fprintf('%.0f×%.0f', A(i,k), B(k,j));
                somma = somma + A(i,k) * B(k,j);
            end
            fprintf(' = %.0f\n', somma);
        end
        fprintf('\n');
    end
    
    disp('Risultato finale:');
    disp(C);
end

% Test della funzione
A_test = [1 2; 3 4];
B_test = [5 6; 7 8];
visualizza_moltiplicazione(A_test, B_test);
```

**Proprietà importanti della moltiplicazione:**

```octave
% 1. NON è commutativa: A*B ≠ B*A (in generale)
A = [1 2; 3 4];
B = [5 6; 7 8];

AB = A * B;
BA = B * A;

disp('A*B ='), disp(AB)
disp('B*A ='), disp(BA)
disp('A*B == B*A?'), disp(isequal(AB, BA))

% 2. È associativa: (A*B)*C = A*(B*C)
C = [1 0; 0 2];
ABC1 = (A * B) * C;
ABC2 = A * (B * C);
disp('(A*B)*C == A*(B*C)?'), disp(isequal(ABC1, ABC2))

% 3. Elemento neutro: A*I = I*A = A
I = eye(2);
AI = A * I;
IA = I * A;
disp('A*I = A?'), disp(isequal(A, AI))
disp('I*A = A?'), disp(isequal(A, IA))
```

### 4.2 Trasposta e determinante

#### **Trasposta di una matrice**

La **trasposta** A' si ottiene "ribaltando" la matrice lungo la diagonale principale: le righe diventano colonne! 🔄

```octave
% Trasposta di una matrice
A = [1  2  3
     4  5  6]    % 2x3

A_trasposta = A'  % oppure transpose(A)
% Risultato (3x2):
% [1  4]
% [2  5] 
% [3  6]

disp('Matrice originale A:'), disp(A)
disp('Trasposta A'':'), disp(A_trasposta)

% Proprietà della trasposta
B = [7 8; 9 10; 11 12];  % 3x2

% (A')' = A
A_doppia_trasposta = (A')';
disp('(A'')'' = A?'), disp(isequal(A, A_doppia_trasposta))

% (A*B)' = B'*A' (ordine invertito!)
AB = A * B;          % 2x2
AB_trasposta = AB';  % 2x2
B_A_trasposta = B' * A';  % 2x2
disp('(A*B)'' = B''*A''?'), disp(isequal(AB_trasposta, B_A_trasposta))
```

**Matrici simmetriche:**
Una matrice è **simmetrica** se A = A' (uguale alla sua trasposta):

```octave
% Creare una matrice simmetrica
A = [1  2  3
     2  5  4
     3  4  6]

disp('A ='), disp(A)
disp('A'' ='), disp(A')
disp('A è simmetrica?'), disp(isequal(A, A'))

% Forzare una matrice ad essere simmetrica
B = rand(3);  % Matrice casuale
B_simmetrica = (B + B') / 2;  % Media con la sua trasposta
disp('B simmetrica verificata:'), disp(isequal(B_simmetrica, B_simmetrica'))
```

#### **Determinante**

Il **determinante** è un numero che "riassume" molte proprietà di una matrice quadrata 🎲.

**Per matrice 2×2:**
```
det([a b; c d]) = ad - bc
```

**Per matrice 3×3** (regola di Sarrus):
```
det([a b c; d e f; g h i]) = aei + bfg + cdh - ceg - afh - bdi
```

```octave
% Calcolo del determinante
A2 = [3  1
      2  4]

det_A2 = det(A2)  % 3*4 - 1*2 = 12 - 2 = 10
disp(['Determinante 2x2: ', num2str(det_A2)])

% Verifica manuale
det_manuale = A2(1,1)*A2(2,2) - A2(1,2)*A2(2,1);
disp(['Calcolo manuale: ', num2str(det_manuale)])

% Matrice 3x3
A3 = [1  2  3
      4  5  6  
      7  8  9]

det_A3 = det(A3)
disp(['Determinante 3x3: ', num2str(det_A3)])

% Verifica con regola di Sarrus
a=1; b=2; c=3; d=4; e=5; f=6; g=7; h=8; i=9;
det_sarrus = a*e*i + b*f*g + c*d*h - c*e*g - a*f*h - b*d*i;
disp(['Regola di Sarrus: ', num2str(det_sarrus)])
```

**Significato del determinante:**

```octave
% Interpretazioni del determinante

% 1. Invertibilità: det ≠ 0 ⟺ matrice invertibile
A_invertibile = [2  1; 3  4];
A_singolare = [2  4; 1  2];    % Righe proporzionali

disp('Matrice invertibile:')
disp(['det = ', num2str(det(A_invertibile))])
disp(['È invertibile? ', num2str(det(A_invertibile) ~= 0)])

disp('Matrice singolare:')
disp(['det = ', num2str(det(A_singolare))])
disp(['È invertibile? ', num2str(det(A_singolare) ~= 0)])

% 2. Fattore di scala per aree/volumi
% Il determinante di una matrice 2x2 è l'area del parallelogramma
% formato dai suoi vettori colonna
v1 = [3; 1];  % Primo vettore
v2 = [1; 4];  % Secondo vettore
M = [v1, v2];
area_parallelogramma = abs(det(M));
disp(['Area del parallelogramma: ', num2str(area_parallelogramma)])

% Visualizzazione
figure;
parallelogramma_x = [0, v1(1), v1(1)+v2(1), v2(1), 0];
parallelogramma_y = [0, v1(2), v1(2)+v2(2), v2(2), 0];
plot(parallelogramma_x, parallelogramma_y, 'b-', 'LineWidth', 2);
hold on;
quiver(0, 0, v1(1), v1(2), 0, 'r', 'LineWidth', 2);
quiver(0, 0, v2(1), v2(2), 0, 'g', 'LineWidth', 2);
grid on;
axis equal;
title(['Parallelogramma - Area = ', num2str(area_parallelogramma)]);
```

### 4.3 Matrice inversa

La **matrice inversa** A⁻¹ è come il "reciproco" per le matrici: A × A⁻¹ = I 🔄

**Quando esiste:**
- Solo per matrici **quadrate**
- Solo se det(A) ≠ 0 (matrice non singolare)

```octave
% Calcolo della matrice inversa
A = [2  1
     3  4]

% Verificare che sia invertibile
if det(A) ~= 0
    A_inv = inv(A)    % oppure A^(-1)
    
    % Verifica: A * A^(-1) = I
    verifica = A * A_inv;
    disp('A ='), disp(A)
    disp('A^(-1) ='), disp(A_inv)
    disp('A * A^(-1) ='), disp(verifica)
    disp('È uguale all''identità?'), disp(allclose(verifica, eye(2), 1e-10))
else
    disp('La matrice non è invertibile!')
end

% Formula per matrice 2x2
% A^(-1) = (1/det(A)) * [d -b; -c a]  dove A = [a b; c d]
function A_inv = inversa_2x2(A)
    if size(A,1) ~= 2 || size(A,2) ~= 2
        error('La matrice deve essere 2x2');
    end
    
    a = A(1,1); b = A(1,2);
    c = A(2,1); d = A(2,2);
    
    det_A = a*d - b*c;
    
    if abs(det_A) < 1e-10
        error('La matrice è singolare (non invertibile)');
    end
    
    A_inv = (1/det_A) * [d -b; -c a];
end

% Test della funzione
A_test = [3 1; 2 4];
A_inv_manuale = inversa_2x2(A_test);
A_inv_octave = inv(A_test);

disp('Confronto metodi per calcolare l''inversa:')
disp('Metodo manuale:'), disp(A_inv_manuale)
disp('Funzione inv():'), disp(A_inv_octave)
disp('Differenza:'), disp(abs(A_inv_manuale - A_inv_octave))
```

**Proprietà dell'inversa:**

```octave
% Proprietà dell'inversa
A = [2 1; 3 4];
B = [1 2; 0 3];

% 1. (A^(-1))^(-1) = A
A_inv = inv(A);
A_inv_inv = inv(A_inv);
disp('(A^(-1))^(-1) = A?'), disp(allclose(A, A_inv_inv, 1e-10))

% 2. (A*B)^(-1) = B^(-1) * A^(-1) (ordine invertito!)
AB = A * B;
AB_inv = inv(AB);
B_inv_A_inv = inv(B) * inv(A);
disp('(A*B)^(-1) = B^(-1) * A^(-1)?'), disp(allclose(AB_inv, B_inv_A_inv, 1e-10))

% 3. (A')^(-1) = (A^(-1))'
A_t_inv = inv(A');
A_inv_t = (inv(A))';
disp('(A'')^(-1) = (A^(-1))''?'), disp(allclose(A_t_inv, A_inv_t, 1e-10))
```

### 4.4 Manipolazione di matrici in Octave

#### **Operazioni avanzate**

```octave
% Creazione di matrici particolari
n = 4;

% Matrici di base
Z = zeros(n);           % Matrice di zeri
O = ones(n);            % Matrice di uni  
I = eye(n);             % Matrice identità
R = rand(n);            % Matrice casuale [0,1]
N = randn(n);           % Matrice normale (media=0, std=1)

% Matrici strutturate
D = diag(1:n);          % Matrice diagonale
T_sup = triu(R);        % Triangolare superiore
T_inf = tril(R);        % Triangolare inferiore

% Combinazioni
S = (R + R')/2;         % Matrice simmetrica
A = R + n*I;            % Matrice con diagonale dominante
```

#### **Manipolazione e selezione**

```octave
% Matrice di esempio
M = magic(5);  % Quadrato magico 5x5
disp('Matrice magic(5):'), disp(M)

% Selezione di sottomatrici
sub1 = M(2:4, 3:5);     % Righe 2-4, colonne 3-5
sub2 = M([1,3,5], :);   % Righe 1,3,5, tutte le colonne
sub3 = M(:, [2,4]);     % Tutte le righe, colonne 2,4

% Modifica di elementi
M(1,1) = 99;            % Cambia un elemento
M(end, :) = 0;          % Ultima riga a zero
M(:, 1) = 1:5;          % Prima colonna = [1;2;3;4;5]

% Operazioni su righe/colonne
riga_max = max(M, [], 2);    % Massimo per ogni riga
col_sum = sum(M, 1);         % Somma per ogni colonna
M_norm = M ./ max(M(:));     % Normalizzazione [0,1]

% Trovare elementi
[max_val, max_idx] = max(M(:));     % Valore e posizione massimi
[riga_max, col_max] = ind2sub(size(M), max_idx);  % Converti indice lineare

% Condizioni logiche
grandi = M > 10;        % Matrice logica degli elementi > 10
M(M < 5) = 0;          % Sostituisce elementi < 5 con 0
posizioni = find(M > 15);  % Indici lineari degli elementi > 15
```

**Funzioni utili per l'analisi:**

```octave
% Matrice di test
A = [1  4  7
     2  5  8
     3  6  9]

% Informazioni statistiche
media_globale = mean(A(:));           % Media di tutti gli elementi
media_righe = mean(A, 2);             % Media per riga
media_colonne = mean(A, 1);           % Media per colonna

std_globale = std(A(:));              % Deviazione standard globale
min_max = [min(A(:)), max(A(:))];     % Minimo e massimo globali

% Proprietà matriciali
rank_A = rank(A);                     % Rango della matrice
trace_A = trace(A);                   % Traccia (somma diagonale)
norm_A = norm(A);                     % Norma euclidiana
cond_A = cond(A);                     % Numero di condizionamento

% Report completo
fprintf('\n=== ANALISI MATRICE ===\n');
fprintf('Dimensioni: %dx%d\n', size(A,1), size(A,2));
fprintf('Rango: %d\n', rank_A);
fprintf('Determinante: %.3f\n', det(A));
fprintf('Traccia: %.3f\n', trace_A);
fprintf('Norma: %.3f\n', norm_A);
fprintf('Condizionamento: %.2e\n', cond_A);
fprintf('Min/Max: [%.3f, %.3f]\n', min_max(1), min_max(2));
fprintf('Media: %.3f\n', media_globale);
```

**Trucco professionale** 💡: Usa sempre `allclose(A, B, tolerance)` invece di `A == B` per confrontare matrici con numeri decimali, perché gli errori di arrotondamento possono causare falsi negativi!

## 5. Risoluzione di sistemi lineari

### 5.1 Metodi diretti

I **metodi diretti** trovano la soluzione esatta di un sistema lineare (se esiste) in un numero finito di operazioni 🎯. Sono come seguire una ricetta precisa per cucinare!

**Vantaggi:**
- Soluzione esatta (senza approssimazioni)
- Tempo di calcolo prevedibile
- Sempre convergono (se il sistema ha soluzione)

**Svantaggi:**
- Possono essere costosi per sistemi molto grandi
- Sensibili agli errori di arrotondamento

#### **Risoluzione diretta in Octave**

```octave
% Metodo più semplice: operatore backslash (\)
% Risolve Ax = b

A = [2  1  -1
     1  3   2
     3  1   1]

b = [8
     13
     10]

% Soluzione diretta
x = A \ b

% Verifica della soluzione
verifica = A * x
differenza = abs(b - verifica)

disp('Sistema Ax = b:')
disp('A ='), disp(A)
disp('b ='), disp(b)
disp('Soluzione x ='), disp(x)
disp('Verifica Ax ='), disp(verifica)
disp('Errore |b - Ax| ='), disp(differenza)
```

L'operatore `\` in Octave è **intelligente**: sceglie automaticamente il metodo migliore basandosi sulla struttura della matrice!

### 5.2 Eliminazione di Gauss

L'**eliminazione di Gauss** è il metodo "manuale" per risolvere sistemi lineari. È come risolvere un puzzle step-by-step! 🧩

#### **Algoritmo passo-passo**

1. **Forma la matrice aumentata** [A|b]
2. **Eliminazione in avanti**: trasforma in forma triangolare superiore
3. **Sostituzione all'indietro**: risolvi dalle ultime equazioni alle prime

```octave
% Implementazione dell'eliminazione di Gauss
function x = gauss_elimination(A, b)
    n = size(A, 1);
    
    % Crea la matrice aumentata [A|b]
    Ab = [A, b];
    
    % FASE 1: Eliminazione in avanti
    for k = 1:n-1
        % Trova il pivot (elemento più grande in valore assoluto)
        [~, max_row] = max(abs(Ab(k:n, k)));
        max_row = max_row + k - 1;
        
        % Scambia le righe se necessario (pivoting parziale)
        if max_row ~= k
            Ab([k, max_row], :) = Ab([max_row, k], :);
            fprintf('Scambio righe %d e %d\n', k, max_row);
        end
        
        % Verifica che il pivot non sia zero
        if abs(Ab(k, k)) < 1e-10
            error('La matrice è singolare o mal condizionata');
        end
        
        % Eliminazione
        for i = k+1:n
            factor = Ab(i, k) / Ab(k, k);
            Ab(i, :) = Ab(i, :) - factor * Ab(k, :);
            fprintf('R%d = R%d - %.3f * R%d\n', i, i, factor, k);
        end
        
        disp(['Dopo eliminazione colonna ', num2str(k), ':'])
        disp(Ab)
    end
    
    % FASE 2: Sostituzione all'indietro
    x = zeros(n, 1);
    for i = n:-1:1
        sum_ax = 0;
        for j = i+1:n
            sum_ax = sum_ax + Ab(i, j) * x(j);
        end
        x(i) = (Ab(i, n+1) - sum_ax) / Ab(i, i);
        fprintf('x(%d) = %.6f\n', i, x(i));
    end
end

% Test dell'algoritmo
A_test = [2  1  -1
          1  3   2  
          3  1   1]

b_test = [8
          13
          10]

disp('=== ELIMINAZIONE DI GAUSS ===')
x_gauss = gauss_elimination(A_test, b_test);

% Confronto con soluzione di Octave
x_octave = A_test \ b_test;
disp('Confronto soluzioni:')
disp(['Gauss:   ', num2str(x_gauss')])
disp(['Octave:  ', num2str(x_octave')])
disp(['Errore:  ', num2str(abs(x_gauss - x_octave)')])
```

#### **Problemi numerici e soluzioni**

```octave
% Esempio di sistema mal condizionato
A_bad = [1    1
         1    1.000001]

b_bad = [2
         2.000001]

disp('Sistema mal condizionato:')
disp('1*x + 1*y = 2')
disp('1*x + 1.000001*y = 2.000001')

x_bad = A_bad \ b_bad;
disp(['Soluzione: x = ', num2str(x_bad(1)), ', y = ', num2str(x_bad(2))])

% Piccola perturbazione nel termine noto
b_pert = [2; 2.000002];  % Cambiamo solo l'ultimo decimale
x_pert = A_bad \ b_pert;
disp(['Soluzione perturbata: x = ', num2str(x_pert(1)), ', y = ', num2str(x_pert(2))])

% Calcolo del numero di condizionamento
cond_number = cond(A_bad);
disp(['Numero di condizionamento: ', num2str(cond_number, '%.2e')])

if cond_number > 1e12
    disp('⚠️  ATTENZIONE: Sistema mal condizionato!')
end
```

### 5.3 Decomposizione LU

La **decomposizione LU** scompone una matrice A in due matrici più semplici:
- **L**: Lower triangular (triangolare inferiore)
- **U**: Upper triangular (triangolare superiore)

Tale che: **A = L × U**

**Perché è utile?**
- Risolvere molti sistemi con la stessa matrice A ma diversi termini noti b
- Calcolare il determinante: det(A) = det(L) × det(U)
- Base per altri algoritmi numerici

```octave
% Decomposizione LU in Octave
A = [4  3   2
     3  4  -1
     2 -1   5]

% Decomposizione LU con pivoting
[L, U, P] = lu(A);

disp('Matrice originale A:'), disp(A)
disp('Matrice L (triangolare inferiore):'), disp(L)
disp('Matrice U (triangolare superiore):'), disp(U) 
disp('Matrice di permutazione P:'), disp(P)

% Verifica: P*A = L*U
verifica_LU = L * U;
A_permutata = P * A;
disp('P*A ='), disp(A_permutata)
disp('L*U ='), disp(verifica_LU)
disp('P*A = L*U?'), disp(allclose(A_permutata, verifica_LU, 1e-10))

% Calcolo del determinante usando LU
det_A_direct = det(A);
det_L = prod(diag(L));  % Prodotto diagonale di L
det_U = prod(diag(U));  % Prodotto diagonale di U
det_P = det(P);         % Determinante della permutazione
det_A_LU = det_P * det_L * det_U;

disp(['Determinante diretto: ', num2str(det_A_direct)])
disp(['Determinante da LU: ', num2str(det_A_LU)])
```

#### **Risoluzione di sistemi con LU**

```octave
% Risoluzione efficiente di Ax = b usando decomposizione LU
% Strategia: A*x = b → L*U*x = b → L*y = b, poi U*x = y

function x = solve_with_LU(L, U, P, b)
    % Passo 1: Permuta il termine noto
    b_perm = P * b;
    
    % Passo 2: Risolvi L*y = b_perm (sostituzione in avanti)
    n = size(L, 1);
    y = zeros(n, 1);
    for i = 1:n
        sum_ly = 0;
        for j = 1:i-1
            sum_ly = sum_ly + L(i, j) * y(j);
        end
        y(i) = (b_perm(i) - sum_ly) / L(i, i);
    end
    
    % Passo 3: Risolvi U*x = y (sostituzione all'indietro)
    x = zeros(n, 1);
    for i = n:-1:1
        sum_ux = 0;
        for j = i+1:n
            sum_ux = sum_ux + U(i, j) * x(j);
        end
        x(i) = (y(i) - sum_ux) / U(i, i);
    end
end

% Test con sistema multiplo (stessa A, diversi b)
A = [4  3   2
     3  4  -1
     2 -1   5]

[L, U, P] = lu(A);

% Primo sistema
b1 = [1; 0; 0];
x1_LU = solve_with_LU(L, U, P, b1);
x1_direct = A \ b1;

% Secondo sistema  
b2 = [0; 1; 0];
x2_LU = solve_with_LU(L, U, P, b2);
x2_direct = A \ b2;

% Terzo sistema
b3 = [0; 0; 1];
x3_LU = solve_with_LU(L, U, P, b3);
x3_direct = A \ b3;

disp('=== CONFRONTO METODI ===')
fprintf('Sistema 1 - LU: [%.3f %.3f %.3f], Diretto: [%.3f %.3f %.3f]\n', ...
        x1_LU, x1_direct)
fprintf('Sistema 2 - LU: [%.3f %.3f %.3f], Diretto: [%.3f %.3f %.3f]\n', ...
        x2_LU, x2_direct)
fprintf('Sistema 3 - LU: [%.3f %.3f %.3f], Diretto: [%.3f %.3f %.3f]\n', ...
        x3_LU, x3_direct)

% Le soluzioni x1, x2, x3 formano le colonne della matrice inversa!
A_inv_LU = [x1_LU, x2_LU, x3_LU];
A_inv_direct = inv(A);
disp('Matrice inversa da LU:'), disp(A_inv_LU)
disp('Matrice inversa diretta:'), disp(A_inv_direct)
```

### 5.4 Implementazione in Octave

#### **Confronto dei metodi disponibili**

```octave
% Matrice di test di dimensione moderata
n = 100;
A = rand(n) + n*eye(n);  % Matrice con diagonale dominante
b = rand(n, 1);

% Metodo 1: Operatore backslash (automatico)
tic;
x1 = A \ b;
time1 = toc;

% Metodo 2: Decomposizione LU esplicita
tic;
[L, U, P] = lu(A);
y = L \ (P * b);  % Sostituzione in avanti
x2 = U \ y;       % Sostituzione all'indietro  
time2 = toc;

% Metodo 3: Matrice inversa (sconsigliato per grandi sistemi!)
tic;
A_inv = inv(A);
x3 = A_inv * b;
time3 = toc;

% Metodo 4: Decomposizione QR
tic;
[Q, R] = qr(A);
x4 = R \ (Q' * b);
time4 = toc;

% Confronto accuratezza
error1 = norm(A*x1 - b);
error2 = norm(A*x2 - b);
error3 = norm(A*x3 - b);
error4 = norm(A*x4 - b);

% Report
fprintf('\n=== CONFRONTO METODI (n=%d) ===\n', n);
fprintf('%-20s %10s %15s\n', 'Metodo', 'Tempo (s)', 'Errore');
fprintf('%-20s %10.4f %15.2e\n', 'Backslash (\\)', time1, error1);
fprintf('%-20s %10.4f %15.2e\n', 'LU esplicita', time2, error2);
fprintf('%-20s %10.4f %15.2e\n', 'Inversa', time3, error3);
fprintf('%-20s %10.4f %15.2e\n', 'QR', time4, error4);

% Raccomandazioni
fprintf('\n=== RACCOMANDAZIONI ===\n');
if time1 == min([time1, time2, time3, time4])
    fprintf('✅ Più veloce: Backslash (\\)\n');
end
if error1 == min([error1, error2, error3, error4])
    fprintf('✅ Più accurato: Backslash (\\)\n');
end
fprintf('⚠️  Evitare inv() per risolvere sistemi lineari!\n');
```

#### **Diagnosi e debugging di sistemi lineari**

```octave
function diagnosi_sistema(A, b)
    fprintf('\n=== DIAGNOSI SISTEMA LINEARE ===\n');
    
    [m, n] = size(A);
    fprintf('Dimensioni: A è %dx%d, b è %dx1\n', m, n, length(b));
    
    % Controllo dimensioni
    if length(b) ~= m
        fprintf('❌ ERRORE: Dimensioni incompatibili!\n');
        return;
    end
    
    % Calcolo del rango
    rank_A = rank(A);
    rank_Ab = rank([A, b]);
    
    fprintf('Rango di A: %d\n', rank_A);
    fprintf('Rango di [A|b]: %d\n', rank_Ab);
    
    % Applicazione teorema di Rouchè-Capelli
    if rank_A ~= rank_Ab
        fprintf('❌ Sistema IMPOSSIBILE (rank(A) ≠ rank([A|b]))\n');
    elseif rank_A == n
        fprintf('✅ Sistema con SOLUZIONE UNICA\n');
        x = A \ b;
        fprintf('Soluzione: ');
        for i = 1:length(x)
            fprintf('x%d = %.6f  ', i, x(i));
        end
        fprintf('\n');
        
        % Verifica soluzione
        residuo = norm(A*x - b);
        fprintf('Residuo ||Ax - b||: %.2e\n', residuo);
        
    else  % rank_A < n
        fprintf('⚠️  Sistema con INFINITE SOLUZIONI\n');
        fprintf('Gradi di libertà: %d\n', n - rank_A);
        
        % Soluzione particolare
        x_part = pinv(A) * b;  % Pseudo-inversa
        fprintf('Soluzione particolare (norma minima): ');
        for i = 1:length(x_part)
            fprintf('x%d = %.6f  ', i, x_part(i));
        end
        fprintf('\n');
    end
    
    % Controllo condizionamento
    if n == m  % Solo per matrici quadrate
        cond_num = cond(A);
        fprintf('Numero di condizionamento: %.2e\n', cond_num);
        
        if cond_num > 1e12
            fprintf('⚠️  ATTENZIONE: Sistema mal condizionato!\n');
        elseif cond_num > 1e6
            fprintf('⚠️  Sistema mediamente condizionato\n');
        else
            fprintf('✅ Sistema ben condizionato\n');
        end
    end
end

% Test della funzione di diagnosi
disp('Test 1: Sistema ben condizionato')
A1 = [2 1; 1 3];
b1 = [5; 7];
diagnosi_sistema(A1, b1);

disp('Test 2: Sistema mal condizionato')
A2 = [1 1; 1 1.000001];
b2 = [2; 2.000001];
diagnosi_sistema(A2, b2);

disp('Test 3: Sistema impossibile')
A3 = [1 2; 2 4];
b3 = [3; 5];
diagnosi_sistema(A3, b3);

disp('Test 4: Sistema con infinite soluzioni')
A4 = [1 2; 2 4];
b4 = [3; 6];
diagnosi_sistema(A4, b4);
```

**Consigli pratici** 💡:

1. **Usa sempre `A \ b`** invece di `inv(A) * b` - è più veloce e accurato!
2. **Controlla il condizionamento** con `cond(A)` prima di risolvere
3. **Usa la diagnosi** per capire il tipo di sistema prima di procedere
4. **Per sistemi grandi**, considera metodi iterativi invece di quelli diretti

## 6. Teorema di Rouchè-Capelli

### 6.1 Rango di una matrice

Il **rango** di una matrice è uno dei concetti più importanti dell'algebra lineare! 📏 È come misurare quante "dimensioni indipendenti" ha la matrice.

**Definizione**: Il rango di una matrice A è il **numero massimo di righe (o colonne) linearmente indipendenti**.

**Intuizione geometrica**: 
- Una matrice 2×2 con rango 2 "copre" tutto il piano
- Una matrice 2×2 con rango 1 "copre" solo una retta  
- Una matrice 3×3 con rango 3 "copre" tutto lo spazio 3D
- Una matrice 3×3 con rango 2 "copre" solo un piano nello spazio

```octave
% Esempi di calcolo del rango
disp('=== ESEMPI DI RANGO ===')

% Matrice con rango massimo (righe indipendenti)
A1 = [1  2  3
      4  5  6
      7  8  10]  % Terza riga NON è combinazione delle altre

rank_A1 = rank(A1);
disp('Matrice A1:'), disp(A1)
disp(['Rango: ', num2str(rank_A1), ' (rango massimo = min(3,3) = 3)'])

% Matrice con rango deficitario (righe dipendenti)
A2 = [1  2  3
      4  5  6
      7  8  9]  % Terza riga = 2*seconda - prima

rank_A2 = rank(A2);
disp('Matrice A2:'), disp(A2)
disp(['Rango: ', num2str(rank_A2), ' (rango deficitario)'])

% Verifica dipendenza lineare in A2
% R3 = 2*R2 - R1 ?
R3_calcolata = 2*A2(2,:) - A2(1,:);
R3_vera = A2(3,:);
disp('Verifica R3 = 2*R2 - R1:')
disp(['Calcolata: [', num2str(R3_calcolata), ']'])
disp(['Vera:      [', num2str(R3_vera), ']'])
disp(['Uguali? ', num2str(isequal(R3_calcolata, R3_vera))])

% Matrice rettangolare
A3 = [1  2  3  4
      5  6  7  8
      9 10 11 12]  % 3x4

rank_A3 = rank(A3);
[m, n] = size(A3);
disp('Matrice A3 (3x4):'), disp(A3)
disp(['Rango: ', num2str(rank_A3), ' (max possibile = min(3,4) = 3)'])
```

**Calcolo del rango con eliminazione di Gauss:**

```octave
function [rango, forma_scala] = calcola_rango_gauss(A)
    % Calcola il rango usando eliminazione di Gauss
    
    [m, n] = size(A);
    A_work = A;  % Copia di lavoro
    
    disp('Matrice originale:'), disp(A)
    
    pivot_row = 1;
    for col = 1:n
        % Trova il pivot nella colonna corrente
        [~, max_idx] = max(abs(A_work(pivot_row:m, col)));
        max_idx = max_idx + pivot_row - 1;
        
        % Se tutti gli elementi sono (quasi) zero, salta la colonna
        if abs(A_work(max_idx, col)) < 1e-10
            continue;
        end
        
        % Scambia le righe se necessario
        if max_idx ~= pivot_row
            A_work([pivot_row, max_idx], :) = A_work([max_idx, pivot_row], :);
            fprintf('Scambio righe %d e %d\n', pivot_row, max_idx);
        end
        
        % Normalizza il pivot
        A_work(pivot_row, :) = A_work(pivot_row, :) / A_work(pivot_row, col);
        fprintf('Normalizzo riga %d (pivot in colonna %d)\n', pivot_row, col);
        
        % Elimina gli elementi sotto il pivot
        for i = pivot_row+1:m
            if abs(A_work(i, col)) > 1e-10
                factor = A_work(i, col);
                A_work(i, :) = A_work(i, :) - factor * A_work(pivot_row, :);
                fprintf('R%d = R%d - %.3f * R%d\n', i, i, factor, pivot_row);
            end
        end
        
        disp(['Dopo eliminazione colonna ', num2str(col), ':'])
        disp(A_work)
        
        pivot_row = pivot_row + 1;
        if pivot_row > m
            break;
        end
    end
    
    % Conta le righe non nulle
    rango = 0;
    for i = 1:m
        if norm(A_work(i, :)) > 1e-10
            rango = rango + 1;
        end
    end
    
    forma_scala = A_work;
end

% Test della funzione
A_test = [1  2  1  3
          2  4  3  7
          1  2  2  4]

[rango_calc, forma_scalini] = calcola_rango_gauss(A_test);
rango_octave = rank(A_test);

disp(['Rango calcolato: ', num2str(rango_calc)])
disp(['Rango Octave: ', num2str(rango_octave)])
disp('Forma a scalini finale:'), disp(forma_scalini)
```

### 6.2 Enunciato del teorema

Il **Teorema di Rouchè-Capelli** è il "giudice supremo" che decide se un sistema lineare ha soluzioni! ⚖️

**Enunciato**: Dato un sistema lineare Ax = b:

1. **Il sistema ha soluzione** ⟺ rank(A) = rank([A|b])

2. **Se il sistema ha soluzione:**
   - Se rank(A) = n (numero incognite) → **soluzione unica** 🎯
   - Se rank(A) < n → **infinite soluzioni** ♾️

**In formule:**
```
Sistema Ax = b con A matrice m×n:

• Nessuna soluzione    ⟺ rank(A) ≠ rank([A|b])
• Soluzione unica      ⟺ rank(A) = rank([A|b]) = n  
• Infinite soluzioni   ⟺ rank(A) = rank([A|b]) < n
```

**Implementazione completa del teorema:**

```octave
function risultato = rouche_capelli(A, b)
    % Implementazione completa del teorema di Rouchè-Capelli
    
    [m, n] = size(A);
    
    % Calcola i ranghi
    rank_A = rank(A);
    rank_Ab = rank([A, b]);
    
    % Risultato della diagnosi
    risultato = struct();
    risultato.rank_A = rank_A;
    risultato.rank_Ab = rank_Ab;
    risultato.num_incognite = n;
    risultato.num_equazioni = m;
    
    % Header del report
    fprintf('\n=== TEOREMA DI ROUCHÈ-CAPELLI ===\n');
    fprintf('Sistema: %d equazioni, %d incognite\n', m, n);
    fprintf('rank(A) = %d\n', rank_A);
    fprintf('rank([A|b]) = %d\n', rank_Ab);
    fprintf('Numero incognite = %d\n', n);
    fprintf('\n');
    
    % Applicazione del teorema
    if rank_A ~= rank_Ab
        % Caso 1: Sistema impossibile
        risultato.tipo = 'impossibile';
        risultato.num_soluzioni = 0;
        
        fprintf('🚫 SISTEMA IMPOSSIBILE\n');
        fprintf('   Motivo: rank(A) ≠ rank([A|b])\n');
        fprintf('   Le equazioni sono incompatibili\n');
        
    elseif rank_A == n
        % Caso 2: Soluzione unica
        risultato.tipo = 'unica';
        risultato.num_soluzioni = 1;
        
        fprintf('✅ SISTEMA CON SOLUZIONE UNICA\n');
        fprintf('   Motivo: rank(A) = rank([A|b]) = n\n');
        
        % Calcola la soluzione
        x = A \ b;
        risultato.soluzione = x;
        
        fprintf('   Soluzione: ');
        for i = 1:length(x)
            fprintf('x%d = %.6f  ', i, x(i));
        end
        fprintf('\n');
        
        % Verifica
        residuo = norm(A*x - b);
        risultato.residuo = residuo;
        fprintf('   Verifica ||Ax - b|| = %.2e\n', residuo);
        
    else
        % Caso 3: Infinite soluzioni
        risultato.tipo = 'infinite';
        risultato.num_soluzioni = inf;
        risultato.gradi_liberta = n - rank_A;
        
        fprintf('♾️  SISTEMA CON INFINITE SOLUZIONI\n');
        fprintf('   Motivo: rank(A) = rank([A|b]) < n\n');
        fprintf('   Gradi di libertà: %d\n', n - rank_A);
        
        % Soluzione particolare (norma minima)
        x_particolare = pinv(A) * b;
        risultato.soluzione_particolare = x_particolare;
        
        fprintf('   Soluzione particolare (norma minima): ');
        for i = 1:length(x_particolare)
            fprintf('x%d = %.6f  ', i, x_particolare(i));
        end
        fprintf('\n');
        
        % Base del nucleo (soluzioni omogenee)
        nucleo = null(A);
        risultato.nucleo = nucleo;
        
        if ~isempty(nucleo)
            fprintf('   Soluzione generale: x_particolare + combinazione del nucleo\n');
            fprintf('   Dimensione nucleo: %d\n', size(nucleo, 2));
        end
    end
    
    fprintf('\n');
end

% Test sistematici
disp('=== TEST DEL TEOREMA ===')

% Test 1: Sistema con soluzione unica
disp('Test 1: Sistema 2x2 con soluzione unica')
A1 = [2  1; 3  4];
b1 = [5; 7];
result1 = rouche_capelli(A1, b1);

% Test 2: Sistema impossibile  
disp('Test 2: Sistema impossibile')
A2 = [1  2; 2  4];  % Righe proporzionali
b2 = [3; 5];        % Termini noti NON proporzionali
result2 = rouche_capelli(A2, b2);

% Test 3: Sistema con infinite soluzioni
disp('Test 3: Sistema con infinite soluzioni')
A3 = [1  2; 2  4];  % Righe proporzionali
b3 = [3; 6];        % Termini noti proporzionali
result3 = rouche_capelli(A3, b3);

% Test 4: Sistema sottodeterminato (più incognite che equazioni)
disp('Test 4: Sistema sottodeterminato (2 eq, 3 incognite)')
A4 = [1  2  1; 2  1  3];
b4 = [4; 7];
result4 = rouche_capelli(A4, b4);

% Test 5: Sistema sovradeterminato (più equazioni che incognite)
disp('Test 5: Sistema sovradeterminato (3 eq, 2 incognite)')
A5 = [1  1; 2  1; 1  2];
b5 = [3; 4; 5];
result5 = rouche_capelli(A5, b5);
```

### 6.3 Classificazione dei sistemi lineari

Basandoci sul teorema di Rouchè-Capelli, possiamo classificare completamente tutti i possibili sistemi lineari:

#### **Schema di classificazione completo**

```octave
% Tabella di classificazione completa
function tabella_classificazione()
    fprintf('\n=== CLASSIFICAZIONE SISTEMI LINEARI ===\n');
    fprintf('%-20s %-15s %-15s %-20s %-15s\n', ...
            'Condizione', 'rank(A)', 'rank([A|b])', 'Tipo Sistema', 'Soluzioni');
    fprintf('%s\n', repmat('-', 1, 85));
    
    fprintf('%-20s %-15s %-15s %-20s %-15s\n', ...
            'rank(A) ≠ rank([A|b])', 'r', 'r+1', 'IMPOSSIBILE', '0');
    fprintf('%-20s %-15s %-15s %-20s %-15s\n', ...
            'rank(A) = rank([A|b]) = n', 'n', 'n', 'COMPATIBILE DET', '1');
    fprintf('%-20s %-15s %-15s %-20s %-15s\n', ...
            'rank(A) = rank([A|b]) < n', 'r<n', 'r<n', 'COMPATIBILE IDET', '∞');
    
    fprintf('\nLegenda:\n');
    fprintf('- DET = Determinato (soluzione unica)\n');
    fprintf('- IDET = Indeterminato (infinite soluzioni)\n');
    fprintf('- n = numero di incognite\n');
    fprintf('- r = rango comune\n');
end

tabella_classificazione();
```

#### **Esempi guidati per ogni caso**

```octave
% Generatore di esempi per ogni tipo di sistema
function genera_esempi_classificazione()
    
    fprintf('\n=== ESEMPI PER OGNI TIPO ===\n');
    
    % Tipo 1: Sistema impossibile
    fprintf('\n1️⃣  ESEMPIO: Sistema impossibile\n');
    fprintf('Come costruirlo: righe A proporzionali, b NON proporzionali\n');
    
    A_imp = [1  2
             3  6]  % R2 = 3*R1
    
    b_imp = [1
             4]    % b2 ≠ 3*b1, quindi impossibile
    
    rouche_capelli(A_imp, b_imp);
    
    % Tipo 2: Sistema con soluzione unica
    fprintf('\n2️⃣  ESEMPIO: Sistema determinato\n');
    fprintf('Come costruirlo: matrice A con rango massimo\n');
    
    A_det = [1  2
             3  5]  % Righe indipendenti
    
    b_det = [1
             4]
    
    rouche_capelli(A_det, b_det);
    
    % Tipo 3: Sistema con infinite soluzioni
    fprintf('\n3️⃣  ESEMPIO: Sistema indeterminato\n');
    fprintf('Come costruirlo: righe A proporzionali, b proporzionali\n');
    
    A_ind = [1  2
             2  4]  % R2 = 2*R1
    
    b_ind = [3
             6]    % b2 = 2*b1, quindi compatibile
    
    rouche_capelli(A_ind, b_ind);
    
    % Tipo 4: Sistema sottodeterminato
    fprintf('\n4️⃣  ESEMPIO: Sistema sottodeterminato (più incognite)\n');
    fprintf('2 equazioni, 3 incognite → sempre infinite soluzioni se compatibile\n');
    
    A_sotto = [1  1  1
               1  2  3]
    
    b_sotto = [6
               14]
    
    rouche_capelli(A_sotto, b_sotto);
    
    % Tipo 5: Sistema sovradeterminato
    fprintf('\n5️⃣  ESEMPIO: Sistema sovradeterminato (più equazioni)\n');
    fprintf('3 equazioni, 2 incognite → può essere impossibile o determinato\n');
    
    A_sopra = [1  1
               1  2  
               2  3]
    
    b_sopra = [3
               5
               8]
    
    rouche_capelli(A_sopra, b_sopra);
end

genera_esempi_classificazione();
```

### 6.4 Applicazioni pratiche

Il teorema di Rouchè-Capelli non è solo teoria - ha applicazioni concrete importantissime! 🔧

#### **Applicazione 1: Verifica di compatibilità in problemi ingegneristici**

```octave
% Problema: Analisi di un traliccio (struttura ingegneristica)
% Verificare se le forze sono in equilibrio

function analisi_traliccio()
    fprintf('\n=== ANALISI TRALICCIO ===\n');
    fprintf('Problema: Verificare equilibrio di forze in un nodo\n');
    
    % Matrice delle direzioni delle forze (componenti x,y)
    % Ogni colonna rappresenta una forza
    A = [cos(0),     cos(pi/3),   cos(2*pi/3)     % Componenti x
         sin(0),     sin(pi/3),   sin(2*pi/3)]    % Componenti y
    
    % Forze esterne applicate al nodo (equilibrio → somma = 0)
    b = [0    % Somma forze x = 0
         0]   % Somma forze y = 0
    
    fprintf('Matrice direzioni forze:\n');
    disp(A);
    fprintf('Condizioni equilibrio (forze esterne):\n');
    disp(b);
    
    % Analisi con Rouchè-Capelli
    result = rouche_capelli(A, b);
    
    if strcmp(result.tipo, 'infinite')
        fprintf('✅ Struttura STATICAMENTE INDETERMINATA\n');
        fprintf('   Richiede analisi elastica per soluzione unica\n');
    elseif strcmp(result.tipo, 'unica')
        fprintf('✅ Struttura STATICAMENTE DETERMINATA\n');
        fprintf('   Forze calcolabili dall''equilibrio statico\n');
    else
        fprintf('❌ Configurazione NON EQUILIBRABILE\n');
    end
end

analisi_traliccio();
```

#### **Applicazione 2: Bilanciamento di reazioni chimiche**

```octave
% Bilanciamento automatico di equazioni chimiche
function bilancia_reazione()
    fprintf('\n=== BILANCIAMENTO REAZIONE CHIMICA ===\n');
    fprintf('Reazione: aH2 + bO2 → cH2O\n');
    
    % Matrice di conservazione degli atomi
    % Righe: elementi (H, O)
    % Colonne: specie chimiche (H2, O2, H2O)
    A = [2   0  -2    % Conservazione idrogeno: 2a + 0b - 2c = 0
         0   2  -1]   % Conservazione ossigeno: 0a + 2b - 1c = 0
    
    b = [0     % Conservazione H
         0]    % Conservazione O
    
    fprintf('Matrice conservazione atomi:\n');
    disp(A);
    
    result = rouche_capelli(A, b);
    
    if strcmp(result.tipo, 'infinite')
        fprintf('Sistema ha infinite soluzioni → normalizziamo\n');
        
        % Fissiamo a = 1 per avere soluzione unica
        A_norm = [A; 1 0 0];  % Aggiungiamo a = 1
        b_norm = [b; 1];      % a = 1
        
        result_norm = rouche_capelli(A_norm, b_norm);
        
        if strcmp(result_norm.tipo, 'unica')
            coeff = result_norm.soluzione;
            fprintf('\nCoefficienti bilanciati:\n');
            fprintf('%.0fH2 + %.0fO2 → %.0fH2O\n', coeff(1), coeff(2), coeff(3));
        end
    end
end

bilancia_reazione();
```

#### **Applicazione 3: Controllo di qualità in produzione**

```octave
% Problema: Verifica di fattibilità in un processo produttivo
function controllo_produzione()
    fprintf('\n=== CONTROLLO QUALITÀ PRODUZIONE ===\n');
    fprintf('Problema: 3 macchine, 2 prodotti, vincoli di capacità\n');
    
    % Matrice tempi di produzione (ore/unità)
    % Righe: macchine, Colonne: prodotti
    A = [2  3     % Macchina 1: 2h per prodotto A, 3h per prodotto B
         1  2     % Macchina 2: 1h per prodotto A, 2h per prodotto B  
         4  1]    % Macchina 3: 4h per prodotto A, 1h per prodotto B
    
    % Ore disponibili per macchina
    b = [40      % Macchina 1: 40 ore disponibili
         25      % Macchina 2: 25 ore disponibili
         50]     % Macchina 3: 50 ore disponibili
    
    fprintf('Tempi produzione (ore/unità):\n');
    disp(A);
    fprintf('Ore disponibili:\n');
    disp(b);
    
    result = rouche_capelli(A, b);
    
    if strcmp(result.tipo, 'unica')
        fprintf('✅ PRODUZIONE DETERMINATA\n');
        x = result.soluzione;
        fprintf('Quantità ottimali: %.2f unità prodotto A, %.2f unità prodotto B\n', ...
                x(1), x(2));
        
        % Verifica non negatività (vincolo fisico)
        if all(x >= 0)
            fprintf('✅ Soluzione fisicamente accettabile\n');
        else
            fprintf('❌ Soluzione con quantità negative → infeasible\n');
        end
        
    elseif strcmp(result.tipo, 'infinite')
        fprintf('♾️  PRODUZIONE FLESSIBILE\n');
        fprintf('   Molte combinazioni possibili → serve ottimizzazione\n');
        
    else
        fprintf('❌ VINCOLI INCOMPATIBILI\n');
        fprintf('   Capacità insufficiente per soddisfare tutti i vincoli\n');
    end
end

controllo_produzione();
```

**Riassunto delle applicazioni** 📋:

1. **Ingegneria strutturale**: Verifica stabilità ed equilibrio
2. **Chimica**: Bilanciamento automatico di reazioni
3. **Produzione**: Controllo fattibilità e ottimizzazione
4. **Economia**: Analisi input-output di Leontief
5. **Fisica**: Conservazione di quantità fisiche
6. **Computer graphics**: Trasformazioni geometriche

Il teorema di Rouchè-Capelli è il "detective" 🕵️ che ci dice sempre se un problema lineare ha senso e quante soluzioni aspettarci!

## 7. Interpolazione lineare

### 7.1 Concetti fondamentali dell'interpolazione

L'**interpolazione** è come "collegare i puntini" in modo matematicamente intelligente! 📈 Dato un insieme di punti noti, vogliamo trovare una funzione che passi esattamente per quei punti.

**Problema base**: Dati n+1 punti (x₀,y₀), (x₁,y₁), ..., (xₙ,yₙ), trovare una funzione f(x) tale che:
f(xᵢ) = yᵢ per i = 0, 1, ..., n

**Tipi di interpolazione:**
- **Lineare**: Usa rette tra coppie di punti consecutive
- **Polinomiale**: Usa un unico polinomio di grado n
- **Spline**: Usa polinomi di basso grado collegati dolcemente
- **Trigonometrica**: Usa funzioni seno e coseno

**Applicazioni comuni:**
- 🎬 Computer graphics (animazioni fluide)
- 📊 Analisi dati (riempire valori mancanti)  
- 🔬 Elaborazione segnali (ricostruzione da campioni)
- 📐 CAD (design di curve e superfici)

```octave
% Esempio introduttivo: Interpolazione vs Approssimazione
close all;

% Punti di dati conosciuti
x_data = [0, 1, 2, 3, 4];
y_data = [1, 3, 2, 5, 4];

% Interpolazione: funzione che passa ESATTAMENTE per i punti
x_fine = linspace(0, 4, 100);
y_interp = interp1(x_data, y_data, x_fine, 'linear');

% Approssimazione: funzione che si "avvicina" ai punti
p = polyfit(x_data, y_data, 2);  % Polinomio di grado 2
y_approx = polyval(p, x_fine);

% Grafico comparativo
figure;
plot(x_data, y_data, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Dati originali');
hold on;
plot(x_fine, y_interp, 'b-', 'LineWidth', 2, 'DisplayName', 'Interpolazione lineare');
plot(x_fine, y_approx, 'g--', 'LineWidth', 2, 'DisplayName', 'Approssimazione polinomiale');
grid on;
legend('Location', 'best');
title('Interpolazione vs Approssimazione');
xlabel('x');
ylabel('y');

% Verifica: l'interpolazione passa esattamente per i punti
fprintf('=== VERIFICA INTERPOLAZIONE ===\n');
for i = 1:length(x_data)
    y_calc = interp1(x_data, y_data, x_data(i), 'linear');
    fprintf('Punto (%g, %g): interpolazione = %g, errore = %.2e\n', ...
            x_data(i), y_data(i), y_calc, abs(y_data(i) - y_calc));
end
```

### 7.2 Interpolazione lineare tra due punti

L'interpolazione lineare è la più semplice: collegare due punti con una retta! 📏

**Formula matematica**: Dati due punti (x₀,y₀) e (x₁,y₁), la retta interpolante è:

```
y = y₀ + (y₁ - y₀) * (x - x₀) / (x₁ - x₀)
```

**Forma parametrica**:
```
y = (1 - t) * y₀ + t * y₁
dove t = (x - x₀) / (x₁ - x₀)
```

```octave
% Implementazione dell'interpolazione lineare tra due punti
function y = interp_lineare_due_punti(x0, y0, x1, y1, x)
    % Interpolazione lineare tra (x0,y0) e (x1,y1)
    
    % Controllo input
    if x0 == x1
        error('I punti devono avere ascisse diverse');
    end
    
    % Formula di interpolazione lineare
    t = (x - x0) / (x1 - x0);  % Parametro normalizzato [0,1]
    y = (1 - t) * y0 + t * y1;  % Combinazione convessa
    
    % Informazioni di debug
    if length(x) == 1
        fprintf('Interpolazione tra (%.3f, %.3f) e (%.3f, %.3f)\n', x0, y0, x1, y1);
        fprintf('x = %.3f → t = %.3f → y = %.3f\n', x, t, y);
        
        if t < 0
            fprintf('⚠️  ESTRAPOLAZIONE a sinistra (t < 0)\n');
        elseif t > 1
            fprintf('⚠️  ESTRAPOLAZIONE a destra (t > 1)\n');
        else
            fprintf('✅ INTERPOLAZIONE corretta (0 ≤ t ≤ 1)\n');
        end
    end
end

% Test della funzione
fprintf('=== TEST INTERPOLAZIONE LINEARE ===\n');

% Punti di esempio
x0 = 1; y0 = 3;
x1 = 4; y1 = 7;

% Test interpolazione (interno)
x_test = 2.5;
y_test = interp_lineare_due_punti(x0, y0, x1, y1, x_test);

% Test estrapolazione (esterno)
x_extra = 5;
y_extra = interp_lineare_due_punti(x0, y0, x1, y1, x_extra);

% Grafico esplicativo
x_plot = linspace(0, 6, 100);
y_plot = interp_lineare_due_punti(x0, y0, x1, y1, x_plot);

figure;
plot([x0, x1], [y0, y1], 'ro', 'MarkerSize', 10, 'MarkerFaceColor', 'red', 'DisplayName', 'Punti dati');
hold on;
plot(x_plot, y_plot, 'b-', 'LineWidth', 2, 'DisplayName', 'Retta interpolante');
plot(x_test, y_test, 'gs', 'MarkerSize', 8, 'MarkerFaceColor', 'green', 'DisplayName', 'Interpolazione');
plot(x_extra, y_extra, 'ms', 'MarkerSize', 8, 'MarkerFaceColor', 'magenta', 'DisplayName', 'Estrapolazione');

% Zona di interpolazione
x_zona = [x0, x1, x1, x0, x0];
y_zona = [min(y_plot)-1, min(y_plot)-1, max(y_plot)+1, max(y_plot)+1, min(y_plot)-1];
fill(x_zona, y_zona, 'yellow', 'FaceAlpha', 0.2, 'EdgeColor', 'none', 'DisplayName', 'Zona interpolazione');

grid on;
legend('Location', 'best');
title('Interpolazione Lineare tra Due Punti');
xlabel('x');
ylabel('y');
axis([0, 6, 0, 10]);
```

**Proprietà dell'interpolazione lineare:**

```octave
% Analisi delle proprietà
function analizza_proprieta_lineare()
    fprintf('\n=== PROPRIETÀ INTERPOLAZIONE LINEARE ===\n');
    
    % Punti di test
    x0 = 2; y0 = 5;
    x1 = 6; y1 = 13;
    
    fprintf('Punti: P0(%.1f, %.1f), P1(%.1f, %.1f)\n', x0, y0, x1, y1);
    
    % Proprietà 1: Passa esattamente per i punti estremi
    y_check0 = interp_lineare_due_punti(x0, y0, x1, y1, x0);
    y_check1 = interp_lineare_due_punti(x0, y0, x1, y1, x1);
    fprintf('\n1. Verifica estremi:\n');
    fprintf('   f(%.1f) = %.6f (atteso: %.1f)\n', x0, y_check0, y0);
    fprintf('   f(%.1f) = %.6f (atteso: %.1f)\n', x1, y_check1, y1);
    
    % Proprietà 2: Linearità (punto medio)
    x_medio = (x0 + x1) / 2;
    y_medio_calc = interp_lineare_due_punti(x0, y0, x1, y1, x_medio);
    y_medio_atteso = (y0 + y1) / 2;
    fprintf('\n2. Punto medio:\n');
    fprintf('   x_medio = %.1f\n', x_medio);
    fprintf('   y_calcolato = %.3f\n', y_medio_calc);
    fprintf('   y_atteso = %.3f\n', y_medio_atteso);
    fprintf('   Differenza: %.2e\n', abs(y_medio_calc - y_medio_atteso));
    
    % Proprietà 3: Monotonia (conserva la tendenza)
    if y1 > y0
        fprintf('\n3. Monotonia: Funzione crescente\n');
        x_test = [x0 + 0.25*(x1-x0), x0 + 0.75*(x1-x0)];
        y_test = interp_lineare_due_punti(x0, y0, x1, y1, x_test);
        fprintf('   x = %.3f → y = %.3f\n', x_test(1), y_test(1));
        fprintf('   x = %.3f → y = %.3f\n', x_test(2), y_test(2));
        fprintf('   Crescente? %s\n', mat2str(y_test(2) > y_test(1)));
    end
    
    % Proprietà 4: Derivata costante
    derivata = (y1 - y0) / (x1 - x0);
    fprintf('\n4. Derivata costante: %.3f\n', derivata);
end

analizza_proprieta_lineare();
```

### 7.3 Interpolazione lineare a tratti

Quando abbiamo più di due punti, l'interpolazione lineare a tratti collega ogni coppia consecutiva con una retta! 🔗

**Idea**: Dati n+1 punti, creare n segmenti lineari:
- Segmento 1: da (x₀,y₀) a (x₁,y₁)  
- Segmento 2: da (x₁,y₁) a (x₂,y₂)
- ...
- Segmento n: da (xₙ₋₁,yₙ₋₁) a (xₙ,yₙ)

```octave
% Implementazione completa dell'interpolazione lineare a tratti
function y = interp_lineare_tratti(x_data, y_data, x_query)
    % Interpolazione lineare a tratti
    % x_data, y_data: punti noti (devono essere ordinati per x crescenti)
    % x_query: punti dove valutare l'interpolazione
    
    n = length(x_data);
    
    % Controlli di validità
    if length(y_data) ~= n
        error('x_data e y_data devono avere la stessa lunghezza');
    end
    
    if n < 2
        error('Servono almeno 2 punti per l''interpolazione');
    end
    
    % Verifica ordinamento
    if any(diff(x_data) <= 0)
        error('x_data deve essere strettamente crescente');
    end
    
    % Inizializza output
    y = zeros(size(x_query));
    
    % Interpola ogni punto richiesto
    for i = 1:length(x_query)
        x = x_query(i);
        
        % Trova l'intervallo contenente x
        if x < x_data(1)
            % Estrapolazione a sinistra (usa il primo segmento)
            idx = 1;
            fprintf('⚠️  Estrapolazione a sinistra: x = %.3f < x_min = %.3f\n', x, x_data(1));
        elseif x > x_data(end)
            % Estrapolazione a destra (usa l'ultimo segmento)
            idx = n - 1;
            fprintf('⚠️  Estrapolazione a destra: x = %.3f > x_max = %.3f\n', x, x_data(end));
        else
            % Interpolazione: trova l'intervallo giusto
            idx = find(x_data <= x, 1, 'last');
            if idx == n  % x coincide con l'ultimo punto
                y(i) = y_data(end);
                continue;
            end
        end
        
        % Interpolazione lineare nel segmento [x_data(idx), x_data(idx+1)]
        x0 = x_data(idx);     y0 = y_data(idx);
        x1 = x_data(idx+1);   y1 = y_data(idx+1);
        
        t = (x - x0) / (x1 - x0);
        y(i) = (1 - t) * y0 + t * y1;
    end
end

% Test con dataset realistico
fprintf('\n=== TEST INTERPOLAZIONE A TRATTI ===\n');

% Dati di temperatura durante la giornata
ore = [0, 6, 12, 18, 24];           % Ore del giorno
temp = [15, 12, 25, 22, 16];        % Temperature (°C)

fprintf('Dati originali:\n');
for i = 1:length(ore)
    fprintf('  Ore %2.0f:00 → %2.0f°C\n', ore(i), temp(i));
end

% Interpola ogni ora
ore_query = 0:24;
temp_interp = interp_lineare_tratti(ore, temp, ore_query);

% Confronto con funzione built-in di Octave
temp_octave = interp1(ore, temp, ore_query, 'linear');

fprintf('\nConfronto interpolazioni:\n');
fprintf('%-4s %-12s %-12s %-10s\n', 'Ora', 'Mia Funz.', 'Octave', 'Diff');
for i = 1:length(ore_query)
    diff_val = abs(temp_interp(i) - temp_octave(i));
    fprintf('%2.0f   %8.3f     %8.3f   %.2e\n', ore_query(i), temp_interp(i), temp_octave(i), diff_val);
end

% Grafico della temperatura interpolata
figure;
plot(ore, temp, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Misurazioni');
hold on;
plot(ore_query, temp_interp, 'b-', 'LineWidth', 2, 'DisplayName', 'Interpolazione lineare');
plot(ore_query, temp_octave, 'g--', 'LineWidth', 1, 'DisplayName', 'Octave interp1');
grid on;
legend('Location', 'best');
title('Temperatura durante la giornata');
xlabel('Ora del giorno');
ylabel('Temperatura (°C)');
xlim([0, 24]);

% Evidenzia i segmenti lineari
for i = 1:length(ore)-1
    x_seg = [ore(i), ore(i+1)];
    y_seg = [temp(i), temp(i+1)];
    plot(x_seg, y_seg, 'k-', 'LineWidth', 3, 'Color', [0.8, 0.8, 0.8]);
end
```

**Analisi delle caratteristiche:**

```octave
% Analisi completa delle caratteristiche dell'interpolazione a tratti
function analizza_interpolazione_tratti()
    fprintf('\n=== ANALISI CARATTERISTICHE ===\n');
    
    % Dataset con comportamenti diversi
    x = [0, 1, 2, 3, 4, 5];
    y = [0, 2, 1, 4, 3, 6];
    
    x_fine = linspace(-0.5, 5.5, 200);
    y_interp = interp_lineare_tratti(x, y, x_fine);
    
    % 1. Continuità
    fprintf('1. CONTINUITÀ:\n');
    fprintf('   Funzione continua in tutti i punti interni? ');
    continua = true;
    for i = 2:length(x)-1
        % Limite da sinistra e da destra
        eps = 1e-10;
        y_left = interp_lineare_tratti(x, y, x(i) - eps);
        y_right = interp_lineare_tratti(x, y, x(i) + eps);
        y_center = y(i);
        
        if abs(y_left - y_center) > 1e-8 || abs(y_right - y_center) > 1e-8
            continua = false;
            break;
        end
    end
    fprintf('%s\n', mat2str(continua));
    
    % 2. Derivabilità
    fprintf('\n2. DERIVABILITÀ:\n');
    fprintf('   Derivate nei punti interni:\n');
    for i = 2:length(x)-1
        % Derivata a sinistra e a destra
        slope_left = (y(i) - y(i-1)) / (x(i) - x(i-1));
        slope_right = (y(i+1) - y(i)) / (x(i+1) - x(i));
        
        fprintf('   x = %.1f: slope_sx = %.3f, slope_dx = %.3f', x(i), slope_left, slope_right);
        if abs(slope_left - slope_right) < 1e-8
            fprintf(' ✅ Derivabile\n');
        else
            fprintf(' ❌ Non derivabile (spigolo)\n');
        end
    end
    
    % 3. Monotonicità locale
    fprintf('\n3. MONOTONICITÀ:\n');
    for i = 1:length(x)-1
        if y(i+1) > y(i)
            trend = 'crescente';
        elseif y(i+1) < y(i)
            trend = 'decrescente';
        else
            trend = 'costante';
        end
        fprintf('   Segmento [%.1f, %.1f]: %s\n', x(i), x(i+1), trend);
    end
    
    % 4. Oscillazioni spurie
    fprintf('\n4. OSCILLAZIONI:\n');
    oscillazioni = 0;
    for i = 2:length(y)-1
        % Controllo se y(i) è un punto di flesso locale
        if (y(i) > y(i-1) && y(i) > y(i+1)) || (y(i) < y(i-1) && y(i) < y(i+1))
            oscillazioni = oscillazioni + 1;
        end
    end
    fprintf('   Numero di oscillazioni locali: %d\n', oscillazioni);
    if oscillazioni > 0
        fprintf('   ⚠️  Potrebbero essere artefatti dell''interpolazione lineare\n');
    end
    
    % Grafico con analisi
    figure;
    subplot(2,1,1);
    plot(x, y, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red');
    hold on;
    plot(x_fine, y_interp, 'b-', 'LineWidth', 2);
    
    % Evidenzia punti di non-derivabilità
    for i = 2:length(x)-1
        slope_left = (y(i) - y(i-1)) / (x(i) - x(i-1));
        slope_right = (y(i+1) - y(i)) / (x(i+1) - x(i));
        if abs(slope_left - slope_right) > 1e-8
            plot(x(i), y(i), 'ks', 'MarkerSize', 10, 'LineWidth', 2);
        end
    end
    
    grid on;
    title('Interpolazione Lineare a Tratti');
    xlabel('x');
    ylabel('y');
    legend('Dati', 'Interpolazione', 'Spigoli', 'Location', 'best');
    
    % Subplot delle derivate
    subplot(2,1,2);
    x_deriv = [];
    y_deriv = [];
    for i = 1:length(x)-1
        slope = (y(i+1) - y(i)) / (x(i+1) - x(i));
        x_seg = linspace(x(i), x(i+1), 20);
        y_seg = ones(size(x_seg)) * slope;
        x_deriv = [x_deriv, x_seg];
        y_deriv = [y_deriv, y_seg];
    end
    
    plot(x_deriv, y_deriv, 'g-', 'LineWidth', 2);
    grid on;
    title('Derivata dell''Interpolazione');
    xlabel('x');
    ylabel('dy/dx');
    ylim([min(y_deriv)-1, max(y_deriv)+1]);
end

analizza_interpolazione_tratti();
```

### 7.4 Implementazione e visualizzazione in Octave

#### **Confronto con altri metodi di interpolazione**

```octave
% Confronto sistematico tra diversi metodi di interpolazione
function confronto_metodi_interpolazione()
    fprintf('\n=== CONFRONTO METODI INTERPOLAZIONE ===\n');
    
    % Funzione di test (nota)
    f_true = @(x) sin(2*pi*x) + 0.5*cos(4*pi*x);
    
    % Punti di campionamento (pochi)
    x_data = [0, 0.2, 0.5, 0.7, 1.0];
    y_data = f_true(x_data);
    
    % Punti per valutazione (molti)
    x_eval = linspace(0, 1, 200);
    y_true = f_true(x_eval);
    
    % Metodi di interpolazione
    y_linear = interp1(x_data, y_data, x_eval, 'linear');
    y_cubic = interp1(x_data, y_data, x_eval, 'cubic');
    y_spline = interp1(x_data, y_data, x_eval, 'spline');
    y_pchip = interp1(x_data, y_data, x_eval, 'pchip');
    
    % Calcolo errori
    error_linear = norm(y_true - y_linear);
    error_cubic = norm(y_true - y_cubic);
    error_spline = norm(y_true - y_spline);
    error_pchip = norm(y_true - y_pchip);
    
    % Report errori
    fprintf('Errori di interpolazione (norma L2):\n');
    fprintf('  Lineare:    %.4f\n', error_linear);
    fprintf('  Cubica:     %.4f\n', error_cubic);
    fprintf('  Spline:     %.4f\n', error_spline);
    fprintf('  PCHIP:      %.4f\n', error_pchip);
    
    % Grafico comparativo
    figure('Position', [100, 100, 1200, 800]);
    
    subplot(2,2,1);
    plot(x_eval, y_true, 'k-', 'LineWidth', 2, 'DisplayName', 'Funzione vera');
    hold on;
    plot(x_data, y_data, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Dati');
    plot(x_eval, y_linear, 'b--', 'LineWidth', 2, 'DisplayName', 'Lineare');
    grid on;
    legend('Location', 'best');
    title('Interpolazione Lineare');
    
    subplot(2,2,2);
    plot(x_eval, y_true, 'k-', 'LineWidth', 2, 'DisplayName', 'Funzione vera');
    hold on;
    plot(x_data, y_data, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Dati');
    plot(x_eval, y_cubic, 'g--', 'LineWidth', 2, 'DisplayName', 'Cubica');
    grid on;
    legend('Location', 'best');
    title('Interpolazione Cubica');
    
    subplot(2,2,3);
    plot(x_eval, y_true, 'k-', 'LineWidth', 2, 'DisplayName', 'Funzione vera');
    hold on;
    plot(x_data, y_data, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Dati');
    plot(x_eval, y_spline, 'm--', 'LineWidth', 2, 'DisplayName', 'Spline');
    grid on;
    legend('Location', 'best');
    title('Interpolazione Spline');
    
    subplot(2,2,4);
    plot(x_eval, abs(y_true - y_linear), 'b-', 'LineWidth', 2, 'DisplayName', 'Errore lineare');
    hold on;
    plot(x_eval, abs(y_true - y_cubic), 'g-', 'LineWidth', 2, 'DisplayName', 'Errore cubica');
    plot(x_eval, abs(y_true - y_spline), 'm-', 'LineWidth', 2, 'DisplayName', 'Errore spline');
    grid on;
    legend('Location', 'best');
    title('Errori Assoluti');
    xlabel('x');
    ylabel('|errore|');
    set(gca, 'YScale', 'log');
end

confronto_metodi_interpolazione();
```

#### **Applicazione pratica: Interpolazione di dati sperimentali**

```octave
% Applicazione realistica: Interpolazione di dati di laboratorio
function laboratorio_interpolazione()
    fprintf('\n=== LABORATORIO: INTERPOLAZIONE DATI SPERIMENTALI ===\n');
    
    % Simulazione: Misure di conducibilità termica vs temperatura
    T_misure = [20, 50, 100, 150, 200, 250, 300];  % Temperatura (°C)
    k_misure = [401, 395, 385, 375, 365, 355, 345]; % Conducibilità (W/m·K)
    
    % Aggiunta di rumore realistico (errore sperimentale)
    rng(42);  % Per riproducibilità
    rumore = 5 * randn(size(k_misure));
    k_rumoroso = k_misure + rumore;
    
    fprintf('Dati sperimentali:\n');
    fprintf('%-10s %-15s %-15s\n', 'T (°C)', 'k teorico', 'k misurato');
    for i = 1:length(T_misure)
        fprintf('%-10.0f %-15.1f %-15.1f\n', T_misure(i), k_misure(i), k_rumoroso(i));
    end
    
    % Range di interpolazione più fine
    T_fine = linspace(20, 300, 100);
    
    % Diversi metodi di interpolazione
    k_linear = interp1(T_misure, k_rumoroso, T_fine, 'linear');
    k_cubic = interp1(T_misure, k_rumoroso, T_fine, 'cubic');
    k_spline = interp1(T_misure, k_rumoroso, T_fine, 'spline');
    
    % Confronto con modello teorico (lineare)
    p_teorico = polyfit(T_misure, k_misure, 1);  % Regressione lineare
    k_teorico = polyval(p_teorico, T_fine);
    
    % Grafico dei risultati
    figure;
    plot(T_misure, k_rumoroso, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', 'DisplayName', 'Dati sperimentali');
    hold on;
    plot(T_fine, k_teorico, 'k--', 'LineWidth', 2, 'DisplayName', 'Modello teorico');
    plot(T_fine, k_linear, 'b-', 'LineWidth', 2, 'DisplayName', 'Interpolazione lineare');
    plot(T_fine, k_cubic, 'g-', 'LineWidth', 2, 'DisplayName', 'Interpolazione cubica');
    plot(T_fine, k_spline, 'm-', 'LineWidth', 2, 'DisplayName', 'Spline');
    
    % Barre di errore sui dati
    errorbar(T_misure, k_rumoroso, 5*ones(size(T_misure)), 'r', 'LineStyle', 'none');
    
    grid on;
    legend('Location', 'best');
    title('Conducibilità Termica del Rame vs Temperatura');
    xlabel('Temperatura (°C)');
    ylabel('Conducibilità Termica (W/m·K)');
    
    % Analisi delle oscillazioni spurie
    fprintf('\nAnalisi oscillazioni:\n');
    
    % Calcola le derivate seconde (curvatura)
    d2_linear = diff(k_linear, 2);
    d2_cubic = diff(k_cubic, 2);
    d2_spline = diff(k_spline, 2);
    
    fprintf('Variazione curvatura (indicatore oscillazioni):\n');
    fprintf('  Lineare: %.3f\n', std(d2_linear));
    fprintf('  Cubica:  %.3f\n', std(d2_cubic));
    fprintf('  Spline:  %.3f\n', std(d2_spline));
    
    if std(d2_spline) > 2*std(d2_linear)
        fprintf('⚠️  La spline mostra oscillazioni eccessive!\n');
        fprintf('   Per dati rumorosi, preferire interpolazione lineare\n');
    end
    
    % Raccomandazioni
    fprintf('\nRaccomandazioni:\n');
    fprintf('📊 Per dati con rumore → Interpolazione lineare o regressione\n');
    fprintf('📈 Per dati lisci di alta qualità → Spline o cubica\n');
    fprintf('🔬 Per estrapolazione → Solo modelli fisici, mai interpolazione!\n');
end

laboratorio_interpolazione();
```

**Riassunto pratico** 📋:

**Quando usare l'interpolazione lineare:**
- ✅ Dati con rumore o incertezza
- ✅ Comportamento localmente lineare  
- ✅ Calcoli veloci richiesti
- ✅ Stabilità numerica importante

**Limitazioni:**
- ❌ Non derivabile nei nodi
- ❌ Non cattura curvature smooth
- ❌ Può essere troppo "angolosa"

**Alternative migliori:**

- 🔄 **Spline cubiche**: Per dati lisci e di alta qualità
- 🔄 **PCHIP**: Preserva la monotonicità 
- 🔄 **Regressione**: Per dati con rumore significativo

## 7. Visualizzazione e plotting in Octave

### 7.1 Grafici base: plot e figure

Il **plotting** è essenziale nel calcolo numerico! 📊 Vedere i dati aiuta a capire meglio i risultati e a individuare errori.

#### **Comandi fondamentali per il plotting**

```octave
% === GRAFICI BASE IN OCTAVE ===
close all;  % Chiude tutte le figure aperte
clear;      % Pulisce il workspace

% 1. GRAFICO SEMPLICE
fprintf('=== GRAFICO SEMPLICE ===\n');

% Dati di esempio: funzione seno
x = linspace(0, 2*pi, 100);  % 100 punti da 0 a 2π
y = sin(x);

% Creare una figura
figure(1);
plot(x, y);
title('Funzione Seno');
xlabel('x (radianti)');
ylabel('sin(x)');
grid on;  % Aggiunge la griglia

fprintf('Creato grafico della funzione seno\n');

% 2. MULTIPLE FUNZIONI SULLO STESSO GRAFICO
fprintf('\n=== MULTIPLE FUNZIONI ===\n');

figure(2);
y1 = sin(x);
y2 = cos(x);
y3 = sin(x) .* cos(x);  % Prodotto (nota il punto prima di *)

plot(x, y1, 'b-', 'LineWidth', 2, 'DisplayName', 'sin(x)');
hold on;  % Mantiene il grafico precedente
plot(x, y2, 'r--', 'LineWidth', 2, 'DisplayName', 'cos(x)');
plot(x, y3, 'g:', 'LineWidth', 2, 'DisplayName', 'sin(x)·cos(x)');
hold off;

title('Confronto Funzioni Trigonometriche');
xlabel('x (radianti)');
ylabel('Valore');
legend('Location', 'best');  % Aggiunge la legenda
grid on;

fprintf('Creato grafico con multiple funzioni\n');

% 3. PERSONALIZZAZIONE AVANZATA
fprintf('\n=== PERSONALIZZAZIONE ===\n');

figure(3);
% Dati: polinomio con rumore
x_data = linspace(-2, 2, 20);
y_true = x_data.^3 - 2*x_data.^2 + x_data + 1;
noise = 0.5 * randn(size(x_data));  % Rumore gaussiano
y_noisy = y_true + noise;

% Grafico dei dati sperimentali
plot(x_data, y_noisy, 'ro', 'MarkerSize', 8, 'MarkerFaceColor', 'red', ...
     'DisplayName', 'Dati sperimentali');
hold on;

% Fit polinomiale
p = polyfit(x_data, y_noisy, 3);  % Polinomio di grado 3
x_smooth = linspace(-2, 2, 200);
y_fit = polyval(p, x_smooth);

plot(x_smooth, y_fit, 'b-', 'LineWidth', 2, 'DisplayName', 'Fit polinomiale');

% Personalizzazioni
title('Fitting Polinomiale con Dati Rumorosi', 'FontSize', 14, 'FontWeight', 'bold');
xlabel('x', 'FontSize', 12);
ylabel('y', 'FontSize', 12);
legend('Location', 'best', 'FontSize', 11);
grid on;

% Aggiungere annotazioni
text(-1.5, 3, sprintf('R² = %.3f', corr(y_noisy, polyval(p, x_data))^2), ...
     'FontSize', 12, 'BackgroundColor', 'yellow');

fprintf('Creato grafico con personalizzazioni avanzate\n');
```

#### **Stili di linea e marcatori**

```octave
% Guida completa agli stili di plotting
function guida_stili_plotting()
    fprintf('\n=== GUIDA STILI DI PLOTTING ===\n');
    
    figure('Position', [100, 100, 1000, 600]);
    
    % Dati di esempio
    x = linspace(0, 10, 50);
    
    % Subplot per organizzare multiple grafici
    subplot(2, 3, 1);  % 2 righe, 3 colonne, posizione 1
    
    % STILI DI LINEA
    plot(x, sin(x), '-', 'LineWidth', 2, 'DisplayName', 'Continua (-)');
    hold on;
    plot(x, sin(x-0.5), '--', 'LineWidth', 2, 'DisplayName', 'Tratteggiata (--)');
    plot(x, sin(x-1), ':', 'LineWidth', 2, 'DisplayName', 'Punteggiata (:)');
    plot(x, sin(x-1.5), '-.', 'LineWidth', 2, 'DisplayName', 'Tratto-punto (-.)');
    title('Stili di Linea');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 2);
    % COLORI
    plot(x, cos(x), 'b-', 'LineWidth', 2, 'DisplayName', 'Blu (b)');
    hold on;
    plot(x, cos(x-0.5), 'r-', 'LineWidth', 2, 'DisplayName', 'Rosso (r)');
    plot(x, cos(x-1), 'g-', 'LineWidth', 2, 'DisplayName', 'Verde (g)');
    plot(x, cos(x-1.5), 'm-', 'LineWidth', 2, 'DisplayName', 'Magenta (m)');
    plot(x, cos(x-2), 'k-', 'LineWidth', 2, 'DisplayName', 'Nero (k)');
    title('Colori Base');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 3);
    % MARCATORI
    x_sparse = linspace(0, 10, 20);  % Meno punti per vedere i marcatori
    plot(x_sparse, sin(x_sparse), 'o-', 'MarkerSize', 6, 'DisplayName', 'Cerchi (o)');
    hold on;
    plot(x_sparse, sin(x_sparse-0.5), 's-', 'MarkerSize', 6, 'DisplayName', 'Quadrati (s)');
    plot(x_sparse, sin(x_sparse-1), '^-', 'MarkerSize', 6, 'DisplayName', 'Triangoli (^)');
    plot(x_sparse, sin(x_sparse-1.5), 'd-', 'MarkerSize', 6, 'DisplayName', 'Diamanti (d)');
    title('Tipi di Marcatori');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 4);
    % COLORI PERSONALIZZATI (RGB)
    plot(x, exp(-x/5).*cos(x), 'Color', [0.8, 0.2, 0.6], 'LineWidth', 3, 'DisplayName', 'RGB [0.8,0.2,0.6]');
    hold on;
    plot(x, exp(-x/5).*sin(x), 'Color', [0.1, 0.7, 0.3], 'LineWidth', 3, 'DisplayName', 'RGB [0.1,0.7,0.3]');
    title('Colori RGB Personalizzati');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 5);
    % TRASPARENZA (Alpha)
    area(x, exp(-x/8), 'FaceColor', 'blue', 'FaceAlpha', 0.3, 'DisplayName', 'Area trasparente');
    hold on;
    plot(x, exp(-x/8), 'b-', 'LineWidth', 2, 'DisplayName', 'Linea bordo');
    title('Trasparenza e Aree');
    legend('Location', 'best');
    grid on;
    
    subplot(2, 3, 6);
    % STILI COMBINATI
    errorbar(x_sparse, sin(x_sparse), 0.1*ones(size(x_sparse)), 'ro-', ...
             'MarkerSize', 6, 'MarkerFaceColor', 'red', 'LineWidth', 1.5, ...
             'DisplayName', 'Dati con errore');
    title('Barre di Errore');
    legend('Location', 'best');
    grid on;
    
    % Titolo generale
    sgtitle('Guida Completa agli Stili di Plotting in Octave', 'FontSize', 16, 'FontWeight', 'bold');
    
    fprintf('Creata guida completa agli stili di plotting\n');
end

guida_stili_plotting();
```



### 3.2 Esportazione e formattazione professionale

#### **Salvare grafici in alta qualità**

```octave
% Guida per salvare grafici professionali
function salvataggio_grafici_professionali()
    fprintf('\n=== SALVATAGGIO GRAFICI PROFESSIONALI ===\n');
    
    % Creiamo un grafico di esempio di alta qualità
    figure('Position', [100, 100, 800, 600]);
    
    % Dati per un grafico di confronto metodi numerici
    x = linspace(0, 1, 11);
    y_exact = exp(x);
    
    % Simuliamo diversi metodi di approssimazione
    y_linear = 1 + x;  % Approssimazione lineare
    y_quad = 1 + x + x.^2/2;  % Approssimazione quadratica
    y_cubic = 1 + x + x.^2/2 + x.^3/6;  % Approssimazione cubica
    
    % Plot principale
    plot(x, y_exact, 'k-', 'LineWidth', 3, 'DisplayName', 'e^x (esatta)');
    hold on;
    plot(x, y_linear, 'b--', 'LineWidth', 2, 'DisplayName', 'Lineare: 1+x');
    plot(x, y_quad, 'r:', 'LineWidth', 2, 'DisplayName', 'Quadratica: 1+x+x²/2');
    plot(x, y_cubic, 'g-.', 'LineWidth', 2, 'DisplayName', 'Cubica: 1+x+x²/2+x³/6');
    
    % Punti di campionamento
    plot(x, y_exact, 'ko', 'MarkerSize', 6, 'MarkerFaceColor', 'black');
    
    % Formattazione professionale
    title('Approssimazioni di Taylor per e^x', 'FontSize', 16, 'FontWeight', 'bold');
    xlabel('x', 'FontSize', 14);
    ylabel('f(x)', 'FontSize', 14);
    
    legend('Location', 'northwest', 'FontSize', 12, 'Box', 'on');
    grid on;
    set(gca, 'GridLineStyle', ':', 'GridAlpha', 0.7);
    
    % Migliorare l'aspetto degli assi
    set(gca, 'FontSize', 12);
    set(gca, 'LineWidth', 1.2);
    
    % Aggiungere annotazioni
    text(0.7, 1.5, 'Zona di\nmaggiore errore', 'FontSize', 11, ...
         'BackgroundColor', 'yellow', 'EdgeColor', 'black', ...
         'HorizontalAlignment', 'center');
    
    % Freccia per indicare la zona
    annotation('arrow', [0.65, 0.75], [0.4, 0.52], 'LineWidth', 2, 'Color', 'red');
    
    fprintf('Grafico professionale creato\n');
    
    % SALVATAGGIO in diversi formati
    fprintf('\nSalvataggio in diversi formati:\n');
    
    % 1. PNG ad alta risoluzione (per web/presentazioni)
    print('-dpng', '-r300', 'approssimazioni_taylor.png');
    fprintf('  ✅ Salvato come PNG 300 DPI\n');
    
    % 2. EPS vettoriale (per pubblicazioni LaTeX)
    print('-depsc', '-tiff', 'approssimazioni_taylor.eps');
    fprintf('  ✅ Salvato come EPS vettoriale\n');
    
    % 3. PDF vettoriale (universale)
    print('-dpdf', 'approssimazioni_taylor.pdf');
    fprintf('  ✅ Salvato come PDF\n');
    
    % 4. SVG per il web
    print('-dsvg', 'approssimazioni_taylor.svg');
    fprintf('  ✅ Salvato come SVG\n');
    
    % Informazioni sui formati
    fprintf('\n📁 GUIDA AI FORMATI:\n');
    fprintf('   🖼️  PNG: Immagini web, presentazioni PowerPoint\n');
    fprintf('   📄 PDF: Documenti universali, stampa\n');
    fprintf('   📐 EPS: Pubblicazioni scientifiche LaTeX\n');
    fprintf('   🌐 SVG: Grafici web scalabili\n');
    
    % Esempio di configurazione per paper scientifico
    fprintf('\n📊 CONFIGURAZIONE PER PAPER SCIENTIFICO:\n');
    
    figure('Position', [200, 200, 600, 400]);  % Formato più compatto
    
    plot(x, abs(y_exact - y_linear), 'b-', 'LineWidth', 2, 'DisplayName', 'Errore lineare');
    hold on;
    plot(x, abs(y_exact - y_quad), 'r-', 'LineWidth', 2, 'DisplayName', 'Errore quadratico');
    plot(x, abs(y_exact - y_cubic), 'g-', 'LineWidth', 2, 'DisplayName', 'Errore cubico');
    
    set(gca, 'YScale', 'log');  % Scala logaritmica per gli errori
    
    title('Errori delle Approssimazioni', 'FontSize', 14);
    xlabel('x', 'FontSize', 12);
    ylabel('Errore Assoluto', 'FontSize', 12);
    legend('Location', 'best', 'FontSize', 10);
    grid on;
    
    % Font professionale
    set(findall(gcf, '-property', 'FontName'), 'FontName', 'Times');
    
    % Salva con impostazioni per pubblicazione
    set(gcf, 'PaperPositionMode', 'auto');
    print('-depsc', '-r300', '-painters', 'errori_approssimazioni.eps');
    
    fprintf('   📑 Salvato grafico errori per pubblicazione\n');
    
    % Tips finali
    fprintf('\n💡 TIPS PER GRAFICI PROFESSIONALI:\n');
    fprintf('   1. Usa colori distinguibili (anche in B&N)\n');
    fprintf('   2. Font leggibili (Times, Arial, Helvetica)\n');  
    fprintf('   3. Linee spesse (LineWidth ≥ 2)\n');
    fprintf('   4. Risoluzione alta (≥300 DPI) per stampa\n');
    fprintf('   5. Titoli e etichette descrittivi\n');
    fprintf('   6. Legenda posizionata strategicamente\n');
    fprintf('   7. Griglia sottile per leggibilità\n');
end

salvataggio_grafici_professionali();
```

**🎯 Riassunto skills di plotting acquisite:**

### ✅ **Competenze di visualizzazione completate:**

1. **Grafici base** 📊
   - `plot()`, `figure()`, personalizzazione stili
   - Linee, colori, marcatori, leggende

2. **Grafici specializzati** 🔬
   - Heatmap matrici, superfici 3D, contour plots
   - Visualizzazione convergenza algoritmi

3. **Analisi dati** 📈
   - Istogrammi, scatter plots, serie temporali
   - Box plots, Q-Q plots, rilevamento outliers

4. **Esportazione professionale** 💼
   - Formati multipli (PNG, PDF, EPS, SVG)
   - Configurazioni per pubblicazioni scientifiche

### 🚀 **Applicazioni pratiche immediate:**

- 📊 **Presentazione risultati** di calcoli numerici
- 📝 **Documentazione** di progetti scientifici

Ora gli studenti possono creare visualizzazioni professionali dei loro calcoli numerici! 🎨✨

## 8. Progetti pratici e applicazioni

### 8.1 Risoluzione di problemi di ingegneria

#### **Progetto 1: Analisi strutturale di un traliccio**

Un traliccio è una struttura composta da aste collegate tramite cerniere. 🏗️ L'analisi delle forze richiede la risoluzione di un sistema lineare molto grande!

```octave
% Progetto: Analisi di un traliccio piano
function progetto_traliccio()
    fprintf('=== PROGETTO: ANALISI TRALICCIO ===\n');
    
    % Definizione della geometria del traliccio
    % Nodi: [x, y] in metri
    nodi = [0, 0;      % Nodo 1 (appoggio sinistro)
            4, 0;      % Nodo 2 
            8, 0;      % Nodo 3 (appoggio destro)
            2, 3;      % Nodo 4 (vertice sinistro)
            6, 3];     % Nodo 5 (vertice destro)
    
    % Aste: [nodo_inizio, nodo_fine]
    aste = [1, 2;      % Asta 1 (base sinistra)
            2, 3;      % Asta 2 (base destra)  
            1, 4;      % Asta 3 (montante sinistro)
            4, 5;      % Asta 4 (traversa superiore)
            5, 3;      % Asta 5 (montante destro)
            2, 4;      % Asta 6 (diagonale sinistra)
            2, 5];     % Asta 7 (diagonale destra)
    
    n_nodi = size(nodi, 1);
    n_aste = size(aste, 1);
    
    fprintf('Geometria traliccio:\n');
    fprintf('  Nodi: %d\n', n_nodi);
    fprintf('  Aste: %d\n', n_aste);
    
    % Visualizzazione della geometria
    figure;
    % Disegna le aste
    for i = 1:n_aste
        n1 = aste(i, 1);
        n2 = aste(i, 2);
        plot([nodi(n1,1), nodi(n2,1)], [nodi(n1,2), nodi(n2,2)], 'b-', 'LineWidth', 3);
        hold on;
        
        % Etichetta asta al centro
        x_centro = (nodi(n1,1) + nodi(n2,1)) / 2;
        y_centro = (nodi(n1,2) + nodi(n2,2)) / 2;
        text(x_centro, y_centro, sprintf('A%d', i), 'FontSize', 10, 'Color', 'blue', ...
             'HorizontalAlignment', 'center', 'BackgroundColor', 'white');
    end
    
    % Disegna i nodi
    for i = 1:n_nodi
        plot(nodi(i,1), nodi(i,2), 'ro', 'MarkerSize', 12, 'MarkerFaceColor', 'red');
        text(nodi(i,1)+0.2, nodi(i,2)+0.2, sprintf('N%d', i), 'FontSize', 12, 'FontWeight', 'bold');
    end
    
    % Vincoli e carichi
    plot(nodi(1,1), nodi(1,2), 's', 'MarkerSize', 15, 'MarkerFaceColor', 'green'); % Cerniera
    plot(nodi(3,1), nodi(3,2), '^', 'MarkerSize', 15, 'MarkerFaceColor', 'green'); % Carrello
    
    % Forza applicata al nodo 4 (10 kN verso il basso)
    quiver(nodi(4,1), nodi(4,2), 0, -1, 'r', 'LineWidth', 3, 'MaxHeadSize', 0.3);
    text(nodi(4,1)+0.3, nodi(4,2)-0.5, '10 kN', 'FontSize', 12, 'Color', 'red', 'FontWeight', 'bold');
    
    grid on;
    axis equal;
    title('Geometria del Traliccio');
    xlabel('x (m)');
    ylabel('y (m)');
    legend('Aste', 'Nodi', 'Cerniera', 'Carrello', 'Carico', 'Location', 'best');
    
    % Costruzione del sistema lineare
    % Equazioni di equilibrio: 2 equazioni per ogni nodo libero
    % Incognite: forze interne nelle aste + reazioni vincolari
    
    fprintf('\nCostruzione sistema lineare...\n');
    
    % Calcola lunghezze e direzioni delle aste
    lunghezze = zeros(n_aste, 1);
    cos_theta = zeros(n_aste, 1);
    sin_theta = zeros(n_aste, 1);
    
    for i = 1:n_aste
        n1 = aste(i, 1);
        n2 = aste(i, 2);
        dx = nodi(n2, 1) - nodi(n1, 1);
        dy = nodi(n2, 2) - nodi(n1, 2);
        L = sqrt(dx^2 + dy^2);
        
        lunghezze(i) = L;
        cos_theta(i) = dx / L;
        sin_theta(i) = dy / L;
    end
    
    % Matrice di equilibrio (semplificata per questo esempio)
    % In un'analisi completa avremo una matrice molto più grande
    
    % Sistema semplificato: forze nei nodi 2, 4, 5 (nodi liberi)
    % Incognite: [F1, F2, F3, F4, F5, F6, F7, Rx1, Ry1, Ry3]
    %           forze aste (positive = trazione)  reazioni vincoli
    
    A = zeros(6, 10);  % 6 equazioni di equilibrio, 10 incognite
    b = zeros(6, 1);   % Termini noti (carichi esterni)
    
    % Equilibrio nodo 2 (X e Y)
    A(1, 1) = -cos_theta(1);  % Asta 1
    A(1, 2) = cos_theta(2);   % Asta 2  
    A(1, 6) = cos_theta(6);   % Asta 6
    A(1, 7) = cos_theta(7);   % Asta 7
    
    A(2, 1) = -sin_theta(1);  % Asta 1
    A(2, 2) = sin_theta(2);   % Asta 2
    A(2, 6) = sin_theta(6);   % Asta 6  
    A(2, 7) = sin_theta(7);   % Asta 7
    
    % Equilibrio nodo 4 (X e Y)
    A(3, 3) = -cos_theta(3);  % Asta 3
    A(3, 4) = cos_theta(4);   % Asta 4
    A(3, 6) = -cos_theta(6);  % Asta 6
    
    A(4, 3) = -sin_theta(3);  % Asta 3
    A(4, 4) = sin_theta(4);   % Asta 4
    A(4, 6) = -sin_theta(6);  % Asta 6
    b(4) = -10000;  % Forza di 10 kN verso il basso (in N)
    
    % Equilibrio nodo 5 (X e Y)  
    A(5, 4) = -cos_theta(4);  % Asta 4
    A(5, 5) = cos_theta(5);   % Asta 5
    A(5, 7) = -cos_theta(7);  % Asta 7
    
    A(6, 4) = -sin_theta(4);  % Asta 4
    A(6, 5) = sin_theta(5);   % Asta 5
    A(6, 7) = -sin_theta(7);  % Asta 7
    
    % Equilibrio globale (per determinare le reazioni)
    % Aggiungere equazioni per le reazioni vincolari
    % (Esempio semplificato)
    
    fprintf('Matrice del sistema:\n');
    fprintf('Dimensioni: %dx%d\n', size(A, 1), size(A, 2));
    fprintf('Rango matrice: %d\n', rank(A));
    
    % Per questo esempio, risolviamo un sistema ridotto
    % In un caso reale, dovreste aggiungere le equazioni per i vincoli
    
    fprintf('\n⚠️  Sistema incompleto per dimostrazione!\n');
    fprintf('📚 In un''analisi reale serve:\n');
    fprintf('   - Equilibrio globale della struttura\n');
    fprintf('   - Condizioni di vincolo\n');
    fprintf('   - Compatibilità cinematica\n');
end

progetto_traliccio();
```

#### **Progetto 2: Calcolo di un circuito a maglia**

```octave
% Progetto: Analisi di circuito elettrico
function progetto_circuito_elettrico()
    fprintf('\n=== PROGETTO: CIRCUITO ELETTRICO ===\n');
    
    % Circuito con 3 maglie e 6 resistori
    % Applicazione delle leggi di Kirchhoff
    
    % Parametri del circuito
    V1 = 12;  % Tensione generatore 1 (V)
    V2 = 8;   % Tensione generatore 2 (V)
    
    R1 = 2;   % Resistenze (Ohm)
    R2 = 4;
    R3 = 3; 
    R4 = 5;
    R5 = 1;
    R6 = 6;
    
    fprintf('Parametri circuito:\n');
    fprintf('  Generatori: V1 = %.1f V, V2 = %.1f V\n', V1, V2);
    fprintf('  Resistori: R1=%.1f, R2=%.1f, R3=%.1f, R4=%.1f, R5=%.1f, R6=%.1f Ω\n', ...
            R1, R2, R3, R4, R5, R6);
    
    % Applicazione della legge di Kirchhoff alle maglie
    % Incognite: correnti di maglia I1, I2, I3
    
    % Maglia 1: V1 - I1*R1 - (I1-I2)*R2 - (I1-I3)*R5 = 0
    % Maglia 2: (I1-I2)*R2 - I2*R3 - (I2-I3)*R4 = 0  
    % Maglia 3: (I1-I3)*R5 + (I2-I3)*R4 - I3*R6 - V2 = 0
    
    % Sistema in forma matriciale A*I = b
    A = [(R1 + R2 + R5),  -R2,          -R5;
         -R2,            (R2 + R3 + R4), -R4;
         -R5,            -R4,            (R4 + R5 + R6)];
    
    b = [V1; 0; V2];
    
    fprintf('\nSistema lineare per le correnti di maglia:\n');
    fprintf('Matrice coefficienti A:\n');
    disp(A);
    fprintf('Vettore termini noti b:\n');
    disp(b');
    
    % Risoluzione del sistema
    fprintf('Analisi del sistema:\n');
    det_A = det(A);
    cond_A = cond(A);
    fprintf('  Determinante: %.4f\n', det_A);
    fprintf('  Numero di condizione: %.2f\n', cond_A);
    
    if det_A == 0
        fprintf('❌ Sistema singolare - circuito mal definito!\n');
        return;
    elseif cond_A > 100
        fprintf('⚠️  Sistema mal condizionato (cond = %.1f)\n', cond_A);
    else
        fprintf('✅ Sistema ben condizionato\n');
    end
    
    % Risoluzione
    I_maglie = A \ b;
    
    fprintf('\nSoluzione - Correnti di maglia:\n');
    fprintf('  I1 = %.4f A\n', I_maglie(1));
    fprintf('  I2 = %.4f A\n', I_maglie(2));
    fprintf('  I3 = %.4f A\n', I_maglie(3));
    
    % Calcolo correnti nei rami
    I_R1 = I_maglie(1);
    I_R2 = I_maglie(1) - I_maglie(2);
    I_R3 = I_maglie(2);
    I_R4 = I_maglie(2) - I_maglie(3);
    I_R5 = I_maglie(1) - I_maglie(3);
    I_R6 = I_maglie(3);
    
    fprintf('\nCorrente nei singoli resistori:\n');
    fprintf('  I_R1 = %.4f A\n', I_R1);
    fprintf('  I_R2 = %.4f A\n', I_R2);
    fprintf('  I_R3 = %.4f A\n', I_R3);
    fprintf('  I_R4 = %.4f A\n', I_R4);
    fprintf('  I_R5 = %.4f A\n', I_R5);
    fprintf('  I_R6 = %.4f A\n', I_R6);
    
    % Calcolo potenze
    P_R1 = I_R1^2 * R1;
    P_R2 = I_R2^2 * R2;
    P_R3 = I_R3^2 * R3;
    P_R4 = I_R4^2 * R4;
    P_R5 = I_R5^2 * R5;
    P_R6 = I_R6^2 * R6;
    
    P_totale = P_R1 + P_R2 + P_R3 + P_R4 + P_R5 + P_R6;
    P_generatori = V1 * I_R1 + V2 * I_R6;
    
    fprintf('\nBilancio energetico:\n');
    fprintf('  Potenza dissipata: %.4f W\n', P_totale);
    fprintf('  Potenza generatori: %.4f W\n', P_generatori);
    fprintf('  Errore bilancio: %.2e W\n', abs(P_totale - P_generatori));
    
    % Verifica leggi di Kirchhoff
    fprintf('\nVerifica leggi di Kirchhoff:\n');
    
    % Legge delle correnti (nodi)
    % Ogni nodo deve avere somma correnti = 0
    fprintf('  Verifica conservazione correnti: ');
    if abs(I_R1 - I_R2 - I_R5) < 1e-10 && abs(I_R2 + I_R3 - I_R4) < 1e-10
        fprintf('✅ OK\n');
    else
        fprintf('❌ ERRORE\n');
    end
    
    % Legge delle tensioni (maglie)
    fprintf('  Verifica leggi tensioni: ');
    V_check1 = V1 - I_R1*R1 - I_R2*R2 - I_R5*R5;
    V_check2 = I_R2*R2 - I_R3*R3 - I_R4*R4;
    V_check3 = I_R5*R5 + I_R4*R4 - I_R6*R6 - V2;
    
    if max(abs([V_check1, V_check2, V_check3])) < 1e-10
        fprintf('✅ OK\n');
    else
        fprintf('❌ ERRORE\n');
    end
end

progetto_circuito_elettrico();
```

### 8.2 Analisi di circuiti elettrici

#### **Progetto 3: Ottimizzazione di una miscela**

```octave
% Progetto: Problema di ottimizzazione lineare
function progetto_ottimizzazione_miscela()
    fprintf('\n=== PROGETTO: OTTIMIZZAZIONE MISCELA ===\n');
    
    % Problema: Una fabbrica produce una lega metallica mescolando 3 materiali
    % Obiettivo: Minimizzare il costo rispettando i vincoli di composizione
    
    % Dati del problema
    materiali = {'Rame', 'Stagno', 'Zinco'};
    costi = [5.2, 8.7, 3.1];  % Euro/kg
    
    % Composizione percentuale di ogni materiale
    %              Cu   Sn   Zn
    composizione = [95,  3,   2;    % Materiale 1 (Rame puro)
                    60, 35,   5;    % Materiale 2 (Bronzo)  
                    20, 10,  70];   % Materiale 3 (Ottone)
    
    % Specifiche della lega finale (percentuali minime/massime)
    Cu_min = 70; Cu_max = 80;  % Rame: 70-80%
    Sn_min = 15; Sn_max = 25;  % Stagno: 15-25%
    Zn_min = 5;  Zn_max = 15;  % Zinco: 5-15%
    
    fprintf('Materiali disponibili:\n');
    for i = 1:3
        fprintf('  %s: %.1f €/kg (Cu %.0f%%, Sn %.0f%%, Zn %.0f%%)\n', ...
                materiali{i}, costi(i), composizione(i,1), composizione(i,2), composizione(i,3));
    end
    
    fprintf('\nSpecifiche lega finale:\n');
    fprintf('  Rame: %.0f-%.0f%%\n', Cu_min, Cu_max);
    fprintf('  Stagno: %.0f-%.0f%%\n', Sn_min, Sn_max);
    fprintf('  Zinco: %.0f-%.0f%%\n', Zn_min, Zn_max);
    
    % Formulazione matematica
    % Variabili: x1, x2, x3 = frazioni dei materiali (x1 + x2 + x3 = 1)
    % Obiettivo: min(5.2*x1 + 8.7*x2 + 3.1*x3)
    
    % Vincoli di composizione:
    % 95*x1 + 60*x2 + 20*x3 >= 70  (Rame minimo)
    % 95*x1 + 60*x2 + 20*x3 <= 80  (Rame massimo)
    % 3*x1 + 35*x2 + 10*x3 >= 15   (Stagno minimo)
    % 3*x1 + 35*x2 + 10*x3 <= 25   (Stagno massimo)
    % 2*x1 + 5*x2 + 70*x3 >= 5     (Zinco minimo)
    % 2*x1 + 5*x2 + 70*x3 <= 15    (Zinco massimo)
    % x1 + x2 + x3 = 1              (Conservazione massa)
    % x1, x2, x3 >= 0               (Non negatività)
    
    % Sistema in forma standard: A*x <= b, Aeq*x = beq
    A = [-95, -60, -20;   % -Cu >= -70  →  Cu <= 80 (no, sbagliato)
          95,  60,  20;   %  Cu <= 80
          -3, -35, -10;   % -Sn >= -15  →  Sn >= 15  
           3,  35,  10;   %  Sn <= 25
          -2,  -5, -70;   % -Zn >= -5   →  Zn >= 5
           2,   5,  70];  %  Zn <= 15
    
    b = [-Cu_min; Cu_max; -Sn_min; Sn_max; -Zn_min; Zn_max];
    
    Aeq = [1, 1, 1];     % x1 + x2 + x3 = 1
    beq = 1;
    
    lb = [0, 0, 0];      % x >= 0
    ub = [1, 1, 1];      % x <= 1
    
    fprintf('\nSistema di vincoli:\n');
    fprintf('Matrice disuguaglianze A:\n');
    disp(A);
    fprintf('Vettore b:\n');
    disp(b');
    fprintf('Equazione: x1 + x2 + x3 = 1\n');
    
    % Risoluzione con metodo del simplesso (simulato)
    % In Octave reale usereste 'linprog' o toolbox di ottimizzazione
    
    fprintf('\n=== RISOLUZIONE GRAFICA/GEOMETRICA ===\n');
    
    % Per questo problema 2D (eliminiamo x3 = 1 - x1 - x2)
    % Sostituiamo nei vincoli e risolviamo graficamente
    
    % Range di ricerca
    x1_range = linspace(0, 1, 100);
    x2_range = linspace(0, 1, 100);
    [X1, X2] = meshgrid(x1_range, x2_range);
    X3 = 1 - X1 - X2;
    
    % Calcola composizioni risultanti
    Cu_result = 95*X1 + 60*X2 + 20*X3;
    Sn_result = 3*X1 + 35*X2 + 10*X3;
    Zn_result = 2*X1 + 5*X2 + 70*X3;
    
    % Maschera di fattibilità
    feasible = (X3 >= 0) & ...                          % x3 >= 0
               (Cu_result >= Cu_min & Cu_result <= Cu_max) & ...  % Vincoli Cu
               (Sn_result >= Sn_min & Sn_result <= Sn_max) & ...  % Vincoli Sn
               (Zn_result >= Zn_min & Zn_result <= Zn_max);       % Vincoli Zn
    
    % Funzione obiettivo  
    Cost = costi(1)*X1 + costi(2)*X2 + costi(3)*X3;
    Cost(~feasible) = NaN;  % Elimina punti non fattibili
    
    % Trova il minimo
    [min_cost, idx] = min(Cost(:));
    [row, col] = ind2sub(size(Cost), idx);
    
    x1_opt = X1(row, col);
    x2_opt = X2(row, col);
    x3_opt = X3(row, col);
    
    fprintf('Soluzione ottima:\n');
    fprintf('  x1 (Rame puro): %.3f (%.1f%%)\n', x1_opt, x1_opt*100);
    fprintf('  x2 (Bronzo):    %.3f (%.1f%%)\n', x2_opt, x2_opt*100);
    fprintf('  x3 (Ottone):    %.3f (%.1f%%)\n', x3_opt, x3_opt*100);
    fprintf('  Costo minimo:   %.2f €/kg\n', min_cost);
    
    % Verifica composizione finale
    Cu_finale = 95*x1_opt + 60*x2_opt + 20*x3_opt;
    Sn_finale = 3*x1_opt + 35*x2_opt + 10*x3_opt;
    Zn_finale = 2*x1_opt + 5*x2_opt + 70*x3_opt;
    
    fprintf('\nComposizione lega finale:\n');
    fprintf('  Rame:   %.1f%% (spec: %.0f-%.0f%%)\n', Cu_finale, Cu_min, Cu_max);
    fprintf('  Stagno: %.1f%% (spec: %.0f-%.0f%%)\n', Sn_finale, Sn_min, Sn_max);
    fprintf('  Zinco:  %.1f%% (spec: %.0f-%.0f%%)\n', Zn_finale, Zn_min, Zn_max);
    
    % Grafico della regione fattibile
    figure;
    contourf(X1, X2, Cost, 20);
    colorbar;
    hold on;
    contour(X1, X2, double(feasible), [0.5, 0.5], 'k-', 'LineWidth', 2);
    plot(x1_opt, x2_opt, 'r*', 'MarkerSize', 15, 'LineWidth', 3);
    
    title('Ottimizzazione Miscela - Regione Fattibile');
    xlabel('x_1 (frazione Rame puro)');
    ylabel('x_2 (frazione Bronzo)');
    legend('Costo (€/kg)', 'Regione fattibile', 'Ottimo', 'Location', 'best');
    grid on;
end

progetto_ottimizzazione_miscela();
```

### 8.3 Problemi di ottimizzazione lineare

### 8.4 Progetti interdisciplinari

#### **Progetto 4: Modellazione di una epidemia (SIR)**

```octave
% Progetto interdisciplinare: Modello epidemiologico SIR
function progetto_epidemia_SIR()
    fprintf('\n=== PROGETTO: MODELLO EPIDEMIOLOGICO SIR ===\n');
    
    % Modello SIR: Susceptible-Infected-Recovered
    % Sistema di equazioni differenziali linearizzato
    
    % Parametri del modello
    beta = 0.3;    % Tasso di trasmissione (1/giorno)
    gamma = 0.1;   % Tasso di guarigione (1/giorno)
    N = 100000;    % Popolazione totale
    
    % Condizioni iniziali
    I0 = 100;      % Infetti iniziali
    S0 = N - I0;   % Suscettibili iniziali  
    R0 = 0;        % Guariti iniziali
    
    fprintf('Parametri modello:\n');
    fprintf('  Popolazione: %d individui\n', N);
    fprintf('  Tasso trasmissione: %.2f/giorno\n', beta);
    fprintf('  Tasso guarigione: %.2f/giorno\n', gamma);
    fprintf('  R0 (numero riproduzione): %.2f\n', beta/gamma);
    
    % Linearizzazione attorno al punto iniziale
    % dS/dt ≈ -beta*S0*I/N
    % dI/dt ≈ beta*S0*I/N - gamma*I  
    % dR/dt ≈ gamma*I
    
    % Sistema linearizzato in forma matriciale: dx/dt = A*x
    % x = [S-S0; I-I0; R-R0]  (variazioni rispetto all'equilibrio)
    
    A = [0,            -beta*S0/N,  0;
         0,  beta*S0/N - gamma,    0;
         0,             gamma,     0];
    
    fprintf('\nMatrice del sistema linearizzato:\n');
    disp(A);
    
    % Analisi degli autovalori
    [V, D] = eig(A);
    autovalori = diag(D);
    
    fprintf('Autovalori del sistema:\n');
    for i = 1:length(autovalori)
        if imag(autovalori(i)) == 0
            fprintf('  λ%d = %.4f (reale)\n', i, real(autovalori(i)));
        else
            fprintf('  λ%d = %.4f + %.4fi\n', i, real(autovalori(i)), imag(autovalori(i)));
        end
    end
    
    % Stabilità del sistema
    fprintf('\nAnalisi stabilità:\n');
    if all(real(autovalori) <= 0)
        if any(real(autovalori) == 0)
            fprintf('  Sistema marginalmente stabile\n');
        else
            fprintf('  Sistema stabile (epidemia si estingue)\n');
        end
    else
        fprintf('  Sistema instabile (epidemia cresce)\n');
    end
    
    % Simulazione numerica del sistema non lineare
    t_span = 0:1:200;  % 200 giorni
    
    % Equazioni differenziali complete (non lineari)
    function dydt = sir_odes(t, y)
        S = y(1);
        I = y(2);
        R = y(3);
        
        dSdt = -beta * S * I / N;
        dIdt = beta * S * I / N - gamma * I;
        dRdt = gamma * I;
        
        dydt = [dSdt; dIdt; dRdt];
    end
    
    % Risoluzione numerica (metodo di Eulero semplificato)
    y0 = [S0; I0; R0];
    dt = 1;  % Passo temporale di 1 giorno
    
    S = zeros(length(t_span), 1);
    I = zeros(length(t_span), 1);
    R = zeros(length(t_span), 1);
    
    S(1) = S0;
    I(1) = I0;
    R(1) = R0;
    
    for i = 2:length(t_span)
        y_current = [S(i-1); I(i-1); R(i-1)];
        dydt = sir_odes(t_span(i-1), y_current);
        
        S(i) = S(i-1) + dt * dydt(1);
        I(i) = I(i-1) + dt * dydt(2);
        R(i) = R(i-1) + dt * dydt(3);
        
        % Verifica conservazione
        total = S(i) + I(i) + R(i);
        if abs(total - N) > 1
            fprintf('⚠️  Errore conservazione al giorno %d: %.1f\n', t_span(i), total);
        end
    end
    
    % Trova il picco dell'epidemia
    [max_infected, peak_day] = max(I);
    fprintf('\nRisultati simulazione:\n');
    fprintf('  Picco epidemia: %.0f infetti al giorno %d\n', max_infected, t_span(peak_day));
    fprintf('  Durata epidemia: ~%.0f giorni\n', find(I < 1, 1, 'first'));
    fprintf('  Totale colpiti: %.0f (%.1f%% popolazione)\n', R(end), R(end)/N*100);
    
    % Grafico dell'evoluzione
    figure;
    plot(t_span, S, 'b-', 'LineWidth', 2, 'DisplayName', 'Suscettibili');
    hold on;
    plot(t_span, I, 'r-', 'LineWidth', 2, 'DisplayName', 'Infetti');
    plot(t_span, R, 'g-', 'LineWidth', 2, 'DisplayName', 'Guariti');
    plot(t_span, S+I+R, 'k--', 'LineWidth', 1, 'DisplayName', 'Totale (verifica)');
    
    % Evidenzia il picco
    plot(t_span(peak_day), max_infected, 'ro', 'MarkerSize', 10, 'MarkerFaceColor', 'red');
    text(t_span(peak_day)+10, max_infected, sprintf('Picco: %.0f', max_infected), ...
         'FontSize', 12, 'Color', 'red');
    
    grid on;
    legend('Location', 'best');
    title('Modello SIR - Evoluzione Epidemia');
    xlabel('Tempo (giorni)');
    ylabel('Numero individui');
    
    % Analisi di sensibilità
    fprintf('\nAnalisi di sensibilità:\n');
    
    R0_values = [0.5, 1.0, 1.5, 2.0, 3.0];
    
    figure;
    for k = 1:length(R0_values)
        beta_test = R0_values(k) * gamma;
        
        % Risolvi con nuovo beta
        I_test = zeros(length(t_span), 1);
        S_test = zeros(length(t_span), 1);
        R_test = zeros(length(t_span), 1);
        
        S_test(1) = S0;
        I_test(1) = I0;
        R_test(1) = R0;
        
        for i = 2:length(t_span)
            dSdt = -beta_test * S_test(i-1) * I_test(i-1) / N;
            dIdt = beta_test * S_test(i-1) * I_test(i-1) / N - gamma * I_test(i-1);
            dRdt = gamma * I_test(i-1);
            
            S_test(i) = S_test(i-1) + dt * dSdt;
            I_test(i) = I_test(i-1) + dt * dIdt;
            R_test(i) = R_test(i-1) + dt * dRdt;
        end
        
        plot(t_span, I_test, 'LineWidth', 2, 'DisplayName', sprintf('R_0 = %.1f', R0_values(k)));
        hold on;
        
        fprintf('  R0 = %.1f → Picco: %.0f infetti\n', R0_values(k), max(I_test));
    end
    
    grid on;
    legend('Location', 'best');
    title('Sensibilità del Modello SIR al Parametro R_0');
    xlabel('Tempo (giorni)');
    ylabel('Infetti');
    
    fprintf('\n💡 Applicazioni pratiche:\n');
    fprintf('   📊 Previsione diffusione malattie\n');
    fprintf('   🏥 Pianificazione capacità ospedaliera\n');  
    fprintf('   💉 Strategie di vaccinazione\n');
    fprintf('   📱 Diffusione informazioni/virus informatici\n');
end

progetto_epidemia_SIR();
```

## 🎯 Conclusioni e approfondimenti

Complimenti! 🎉 Hai completato un viaggio attraverso il calcolo numerico con Octave, esplorando:

### ✅ **Competenze acquisite:**

1. **Fondamenti matriciali** 🔢
   - Creazione e manipolazione di matrici
   - Operazioni algebriche fondamentali
   - Proprietà matematiche essenziali

2. **Sistemi lineari** ⚖️
   - Conversione da forma algebrica a matriciale
   - Metodi di risoluzione diretti e iterativi
   - Analisi di esistenza e unicità delle soluzioni

3. **Teorema di Rouchè-Capelli** 📐
   - Classificazione completa dei sistemi lineari
   - Calcolo del rango di matrici
   - Applicazioni ingegneristiche pratiche

4. **Interpolazione lineare** 📈
   - Interpolazione tra due punti
   - Interpolazione a tratti
   - Confronto con altri metodi

5. **Applicazioni pratiche** 🔧
   - Analisi strutturale
   - Circuiti elettrici
   - Ottimizzazione
   - Modellazione interdisciplinare

### 🚀 **Prossimi passi:**

**Per chi vuole approfondire:**
- 📚 **Analisi numerica avanzata**: Metodi iterativi, convergenza, stabilità
- 🔬 **Equazioni differenziali**: Problemi ai valori iniziali e al contorno  
- 📊 **Statistica computazionale**: Regressione, analisi dei dati
- 🎮 **Computer graphics**: Trasformazioni geometriche, rendering

**Strumenti professionali:**
- 🐍 **Python** (NumPy, SciPy, Matplotlib)
- 📊 **MATLAB** (versione commerciale di Octave)
- ⚡ **Julia** (linguaggio ad alte prestazioni)
- 🔧 **R** (analisi statistica avanzata)

### 💡 **Consigli per il futuro:**

1. **Pratica costante** 💪 - Il calcolo numerico si impara facendo!
2. **Progetti reali** 🎯 - Applica le tecniche a problemi del tuo interesse
3. **Errori numerici** ⚠️ - Sempre verificare stabilità e precisione
4. **Visualizzazione** 📊 - I grafici aiutano a capire i risultati
5. **Documentazione** 📝 - Commenta sempre il tuo codice!

Il calcolo numerico è ovunque: dalle previsioni meteo 🌦️ alle simulazioni spaziali 🚀, dall'intelligenza artificiale 🤖 alla computer graphics 🎬. Le competenze che hai acquisito sono la base per esplorare questi affascinanti campi!

**Buon coding! 💻✨**
