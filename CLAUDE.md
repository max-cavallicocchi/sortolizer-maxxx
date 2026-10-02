# Sortolizer (fork di Max)

Visualizzatore di algoritmi di ordinamento in JavaScript puro, pagina statica con `<canvas>`.
Fork di [TheSuperNile/Sortolizer](https://thesupernile.github.io/Sortolizer), nato come progetto per Alex.
**Stato: in pausa** (Alex al momento non è più interessato).

## Struttura

Tutto il codice sta in `Sortolizer-main/` (nessuna build, nessuna dipendenza, nessun test):

| File | Ruolo |
|---|---|
| `index.html` | Pagina principale: canvas 900x500, pulsanti shuffle/algoritmi, icona ingranaggio in alto a destra |
| `settings.html` | Configurazione (in italiano): numero di barre 4–1024, salvato in `localStorage` (`sortolizer.numBars`) |
| `main.js` | Barre, disegno, suono, shuffle e tutti gli algoritmi |
| `sortingAlgStylesheet.css` | Stili (incluso `.cornerIcon` per ingranaggio/chiudi) |
| `README.MD` | README originale dell'autore (in inglese) |

## Come funziona `main.js`

- `barArray` = array di `SortBar`; `lastShuffledBarArray` = copia per "Load bar position from last shuffle".
- Ogni algoritmo è `async` e usa `swapIndexes()` (scambia, colora, ridisegna, suona) e `sleep()` per animare.
- Ogni algoritmo ha un wrapper `…SortEntry()` chiamato dal pulsante: blocca la UI (`sortArray`/`shuffling`), lancia l'algoritmo, poi `greenPass()`.
- Il numero di barre arriva da `loadNumBarsSetting()` all'avvio; le costanti `DEFAULT/MIN/MAX_NUM_BARS` sono duplicate in `settings.html`: tienile allineate.
- Bogo sort è l'unico interrompibile (`runBogo`); per gli altri serve ricaricare la pagina.
- "Miracle Sort" ha il pulsante ma nessuna funzione collegata.

## Eseguire

Aprire `Sortolizer-main/index.html` nel browser (o servire la cartella con `python3 -m http.server`).
Deploy: IntelliJ (`.idea/deployment.xml`) carica `Sortolizer-main/` via SFTP su `/www.cavallicocchi.it/sortolizer`.

## Convenzioni

- Interfaccia delle impostazioni in italiano; pulsanti e README originali in inglese.
- Stile del codice dell'autore: 4 spazi, commenti sopra i blocchi, nomi lunghi e descrittivi. Mantienilo.
- Dopo ogni modifica agli algoritmi, provarli tutti nel browser (con numeri di barre non potenza di 2, es. 100 e 1000).

## Modifiche rispetto all'originale

Vedi `CHANGELOG.md`.
