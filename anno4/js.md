# JavaScript per pagine interattive

JavaScript modifica il comportamento della pagina nel browser. Molti costrutti
sono già noti da Python; la novità principale è la programmazione guidata dagli
eventi e l'interazione con il DOM.

## 1. Obiettivi

Al termine del capitolo saprai collegare uno script, leggere e modificare il DOM,
gestire eventi e form, rappresentare lo stato e aggiornare l'interfaccia in modo
accessibile.

## 2. Collegare lo script

```html
<script src="app.js" defer></script>
```

`defer` fa eseguire lo script dopo che il documento è stato analizzato.

## 3. Variabili e tipi

```javascript
const nome = "Ada";
let tentativi = 0;
const temperatura = 21.5;
const valido = true;
```

Si usa `const` quando il nome non deve essere riassegnato; `let` quando il valore cambia.

`const` non rende immutabile un array o un oggetto: impedisce soltanto di assegnare
un altro valore allo stesso nome.

## 4. Funzioni

```javascript
function celsiusFahrenheit(celsius) {
  return celsius * 9 / 5 + 32;
}

console.log(celsiusFahrenheit(20));
```

Le funzioni freccia sono frequenti nei gestori di eventi:

```javascript
const doppio = numero => numero * 2;
```

All'inizio conviene usare la forma che rende più evidente parametri e risultato,
senza cercare di abbreviare ogni funzione.

## 5. Selezioni e cicli

```javascript
function valuta(voto) {
  if (voto < 0 || voto > 10) {
    return "non valido";
  }
  if (voto >= 6) {
    return "sufficiente";
  }
  return "non sufficiente";
}
```

```javascript
const misure = [18.2, 19.5, 20.1];

for (const misura of misure) {
  console.log(misura);
}
```

Questi costrutti riprendono concetti già studiati in Python. L'attenzione principale è l'interazione con la pagina.

## 6. DOM

Il DOM rappresenta il documento come un albero di oggetti.

```mermaid
flowchart TD
    D["document"] --> H["html"]
    H --> B["body"]
    B --> T["h1"]
    B --> F["form"]
    F --> I["input"]
    F --> P["button"]
```

```javascript
const titolo = document.querySelector("h1");
titolo.textContent = "Nuovo titolo";
```

`querySelector()` restituisce `null` se non trova l'elemento. Uno script deve essere
caricato al momento giusto e usare selettori coerenti con l'HTML.

## 7. Eventi

HTML:

```html
<button id="calcola" type="button">Calcola</button>
<p id="risultato" aria-live="polite"></p>
```

JavaScript:

```javascript
const pulsante = document.querySelector("#calcola");
const risultato = document.querySelector("#risultato");

pulsante.addEventListener("click", () => {
  risultato.textContent = "Calcolo completato";
});
```

`aria-live` permette alle tecnologie assistive di annunciare un aggiornamento.

L'evento contiene informazioni sull'interazione. Non conviene inserire tutta la
logica nel gestore: il gestore legge l'input, chiama funzioni dedicate e aggiorna
l'interfaccia.

## 8. Form

```html
<form id="conversione">
  <label for="celsius">Temperatura in °C</label>
  <input id="celsius" type="number" step="0.1" required>
  <button>Converti</button>
</form>
<p id="output" aria-live="polite"></p>
```

```javascript
const form = document.querySelector("#conversione");
const campo = document.querySelector("#celsius");
const output = document.querySelector("#output");

form.addEventListener("submit", (evento) => {
  evento.preventDefault();
  const valore = Number(campo.value);

  if (!Number.isFinite(valore)) {
    output.textContent = "Inserisci un numero valido";
    return;
  }

  output.textContent = `${celsiusFahrenheit(valore).toFixed(1)} °F`;
});
```

## 9. Creare elementi

```javascript
const lista = document.querySelector("#misure");
const elemento = document.createElement("li");
elemento.textContent = "21,4 °C";
lista.append(elemento);
```

Si preferisce `textContent` quando si inserisce testo fornito dall'utente. Usare `innerHTML` senza controllo può introdurre vulnerabilità.

## 10. Stato semplice

```javascript
const misure = [];

function aggiungiMisura(valore) {
  misure.push(valore);
  aggiornaInterfaccia();
}
```

Lo stato contiene i dati correnti; l'interfaccia li rappresenta.

```mermaid
flowchart LR
    E["Evento"] --> L["Aggiorna la logica"]
    L --> S["Modifica lo stato"]
    S --> I["Ridisegna l'interfaccia"]
```

Mantenere questo flusso riduce le incoerenze tra dati e pagina.

## 11. Errori frequenti

- usare `var` senza necessità invece di `const` e `let`;
- confrontare numeri senza convertire il valore letto da un campo;
- modificare il DOM da molte parti senza una funzione comune;
- dimenticare `preventDefault()` quando si gestisce un form;
- usare `innerHTML` con testo proveniente dall'utente;
- rendere l'interazione disponibile soltanto con il mouse.

## 12. Laboratorio guidato

Costruisci in quattro passaggi un registro di misure:

1. acquisisci e valida un numero;
2. aggiungilo allo stato;
3. ricrea la lista visibile;
4. mostra conteggio, minimo, massimo e media.

Dopo ogni passaggio prova campo vuoto, testo non numerico, numero negativo e uso
della sola tastiera.

## 13. Progetto

Realizza una pagina che acquisisca misure, le mostri in una lista, calcoli la media e segnali input non validi. Deve funzionare con mouse e tastiera.

## 14. Verifica

1. Perché si preferisce `const` quando possibile?
2. Che cosa rappresenta il DOM?
3. Qual è il ruolo di un gestore di eventi?
4. Perché stato e interfaccia vanno tenuti distinti?
