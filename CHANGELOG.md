# Changelog

Modifiche rispetto al progetto originale [TheSuperNile/Sortolizer](https://thesupernile.github.io/Sortolizer).

## [Non rilasciato] - 2026-10-02

### Aggiunto
- Pagina di configurazione `settings.html` (icona ingranaggio in alto a destra) per scegliere il numero di barre, da 4 a 1024 (default 256), salvato in `localStorage`.
- Favicon (`favicon.svg`).
- Stili `.cornerIcon` per le icone in alto a destra.

### Corretto
- **Bitonic Sort**: ora funziona con qualsiasi numero di barre, non solo potenze di 2 (riscritto in modo ricorsivo con `bitonicMerge`).
- **Comb Sort**: condizione del ciclo invertita e gap che poteva scendere sotto 1.
- **Radix Sort**: il numero di cifre era fisso a 3; ora dipende dal valore massimo.
- **Shell Sort**: errore off-by-one che lasciava elementi non ordinati (`>` al posto di `>=`).

### Modificato
- Il deploy IntelliJ carica solo la cartella `Sortolizer-main`.

### Note
- Progetto in pausa.
