# lucavarotto.github.io

Il mio sito personale: una pagina sola, pubblicata da GitHub Pages all'indirizzo
**[lucavarotto.github.io](https://lucavarotto.github.io/)**.

## Com'è fatto

Tutto sta in `index.html`: 882 righe, di cui 493 di CSS e 120 di JavaScript, entrambi
in linea. Nessun framework, nessuna dipendenza da installare, nessun passo di build —
si modifica il file, si fa commit sul ramo `main` e GitHub Pages pubblica.

Dall'esterno arrivano solo due cose: i caratteri *Playfair Display* e *DM Sans* da
Google Fonts, e le icone di Font Awesome 6.5.0 da cdnjs.

## Struttura

```
lucavarotto.github.io/
├── index.html                     la pagina: markup, stile e script
├── assets/
│   ├── LucaVarotto_CV-it.pdf      CV in italiano, scaricabile dalla pagina
│   ├── LucaVarotto_CV-eng.pdf     CV in inglese
│   └── SL.jpg                     anteprima per le condivisioni (og:image)
└── README.md
```

## La pagina

Cinque sezioni in sequenza: **Chi sono**, **Esperienze e Formazione**, **Progetti**,
**Competenze**, **Contatti e Risorse**.

Due dettagli da conoscere prima di metterci mano:

- **La superficie animata in alto a destra** è un `<canvas>` disegnato a mano: una
  superficie di regressione con 26 osservazioni e i rispettivi residui, che ruota di
  0,12 radianti al secondo, cioè un giro ogni 52 secondi. I punti escono da un
  generatore pseudo-casuale con seme fisso, quindi il disegno è identico a ogni
  caricamento.
- **Le animazioni si fanno da parte**: con `prefers-reduced-motion` la superficie
  disegna un fotogramma e si ferma, un `IntersectionObserver` la mette in pausa quando
  esce dallo schermo, e il ciclo è limitato a 30 fotogrammi al secondo.

## Dove mettere le mani

| Cosa | Dove |
| --- | --- |
| Un progetto | un `<li class="project">` dentro `.projects-list`: titolo, link al repository, descrizione e tag |
| Una tappa del percorso | un `<li>` dentro `<ol class="timeline">`, dalla più recente alla più vecchia |
| I CV | si sostituiscono i PDF in `assets/` tenendo gli stessi nomi, così i link restano validi |
| I titoli di sezione | sono gli unici testi in Playfair Display, il carattere con la e commerciale calligrafica |
