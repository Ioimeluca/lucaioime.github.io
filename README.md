# Luca Ioime · Sito di Campagna

Sito statico per la candidatura a consigliere comunale di Luca Ioime — Partito Democratico, coalizione "San Nicola Città Viva", elezioni amministrative San Nicola la Strada del 24 e 25 maggio 2026.

## Struttura

```
luca-ioime-site/
├── index.html          ← unico file HTML, CSS embedded, no build step
├── images/
│   ├── luca-headshot-crop.jpg   (hero, ritaglio dal poster)
│   ├── luca-guitar.jpg          (B&N, sezione "Percorso")
│   ├── luca-tedx-stage.jpg      (sezione TEDx)
│   ├── luca-portrait.jpg        (riserva, conferenza con microfono)
│   ├── luca-headshot.jpg        (riserva, poster intero)
│   └── luca-square.jpg          (immagine OG/condivisione social)
└── README.md
```

Tutto compreso pesa circa **1 MB**. Nessuna dipendenza, nessun build, nessun server: si apre con doppio clic in qualsiasi browser per testarlo.

## Deploy su GitHub Pages — 3 minuti

### Opzione A — drag & drop dal browser (la più semplice, zero terminale)

1. Vai su https://github.com/new e crea un repository:
   - Per ottenere un URL del tipo `https://lucaioime.github.io/`, chiama il repo **`lucaioime.github.io`** (deve essere pubblico, e il nome deve combaciare con lo username).
   - In alternativa chiamalo come vuoi (es. `campagna-2026`); il sito sarà su `https://<utente>.github.io/campagna-2026/`.
2. Sulla home del repo appena creato, clicca **"uploading an existing file"**.
3. Trascina dentro `index.html` e l'**intera cartella `images/`** (basta selezionarli tutti insieme).
4. Scrivi un commit message ("Primo deploy") e clicca **Commit changes**.
5. Vai in **Settings → Pages** (menù a sinistra). Sotto "Source" seleziona branch **`main`** e cartella **`/ (root)`**, poi **Save**.
6. Aspetta 30-60 secondi: il sito sarà online all'URL indicato in cima alla stessa pagina.

### Opzione B — da terminale (per chi ha git)

```bash
cd luca-ioime-site
git init
git add .
git commit -m "Primo deploy"
git branch -M main
git remote add origin https://github.com/<tuo-utente>/lucaioime.github.io.git
git push -u origin main
```
Poi attiva GitHub Pages come al punto 5 dell'Opzione A.

## Dominio personalizzato (opzionale)

Per avere un URL tipo `lucaioime.it`:
1. Acquista il dominio (Aruba, Register.it, Namecheap…).
2. Nel pannello DNS del registrar, crea 4 record `A` puntando agli IP di GitHub Pages: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`. Più un record `CNAME` `www` → `<utente>.github.io`.
3. Su GitHub: Settings → Pages → "Custom domain" → inserisci `lucaioime.it` e attiva "Enforce HTTPS".

## Cose da rivedere prima di pubblicare ⚠️

Due punti che richiedono **un controllo umano** prima del go-live:

1. **Approvazione testi** — i copy del Manifesto, Percorso, Esperienza e Formazione sono drafting editoriale costruito sul CV di Luca, sull'iconografia del poster, e sulle informazioni pubbliche. Il Manifesto in particolare è la **traduzione in italiano** del bio di Luca dal suo profilo LinkedIn (originale: "I'm the result of every adventure…"). Tutto il resto è scrittura programmatica in terza/prima persona, basata su fatti verificabili. **Falli leggere a Luca** prima della pubblicazione: deve sentire suoi ogni punto e virgola.

2. **Disclaimer legale in footer** — c'è già il template di "Committente responsabile" obbligatorio per la propaganda elettorale ai sensi della Legge 28/2000 (par condicio). Verificate che il testo sia conforme a quanto richiesto dal regolamento elettorale e dal vostro responsabile di campagna; in caso di dubbi, chiedete al delegato/mandatario elettorale della lista.

## Note tecniche

- **Performance**: tutto inline (CSS + JS in `index.html`), immagini ottimizzate JPEG progressive, font caricati da Google Fonts con `preconnect`. Lighthouse target: 95+ su mobile.
- **Accessibilità**: skip-link, contrasti AAA su testo principale, alt-text su tutte le immagini, `prefers-reduced-motion` rispettato.
- **SEO**: meta description, Open Graph (immagine `luca-square.jpg`), `lang="it"`, gerarchia heading semantica.
- **Privacy**: zero tracker, zero cookie, zero analytics. Il sito è stateless. Niente banner cookie da mostrare, niente GDPR da gestire.
- **Responsive**: testato a 380px (mobile) e 1280px (desktop). Layout fluido tra i due.

## Modifiche rapide

Tutto il sito è in `index.html`. Per cambiare:
- **Email/social**: cerca "ioime.luca@gmail.com" o "ioime_way" nel file, sostituisci.
- **Date elezione**: cerca "24 e 25 maggio 2026", sostituisci ovunque.
- **Aggiungere una sezione "Programma"**: si può inserire una nuova `<section>` tra la sezione TEDx e la sezione Vota; il pattern editoriale è coerente, basta replicare uno dei blocchi esistenti (consiglio: lo stile della sezione "Authority" con metriche).

Quando arriverà il programma elettorale dettagliato, posso aggiornare il sito con una sezione "Le mie 5 priorità" o simile — chiamatami quando l'avete pronto.
