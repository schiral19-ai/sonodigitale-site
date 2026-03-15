# Design Vision — SONODIGITALE

Principi di design moderni 2025/2026 per costruire pagine visivamente eccellenti.
Leggere per ogni BUILD. L'obiettivo è: bello, distintivo, professionale, non generico.

---

## IL PARAMETRO DI QUALITÀ

Prima di consegnare qualsiasi pagina, poni questa domanda:
**"Questo sito comunica autorevolezza e fiducia a un imprenditore di 48 anni che lo vede per la prima volta su iPhone?"**

Se la risposta è no o forse, non è finito.

---

## PRINCIPI FONDAMENTALI

### 1. Spazio come lusso percepito
Sezioni generose (88px desktop, 56px mobile) comunicano autorevolezza.
Non comprimere per "mettere più contenuto" — si perde qualità percepita.
Ogni sezione deve respirare. Il bianco non è spazio vuoto, è silenzio intenzionale.

### 2. Gerarchia visiva senza ambiguità
Ogni sezione ha un solo elemento dominante. Il visitatore capisce in 2 secondi dove guardare.
Regola: un H1 per pagina, un btn-primary per area visiva, un messaggio principale per sezione.
Evitare "flat hierarchy" dove tutto ha lo stesso peso visivo.

### 3. Arancione come firma — non come rumore
`--orange` (#FC7E15) è il colore dell'azione e della fiducia.
Usarlo per: CTA primarie, numeri statistici, accenti su parole chiave, bordi featured.
NON usarlo per: background di sezioni intere, testo body, decorazioni diffuse.
Meno arancione = più impatto quando appare.

### 4. Ritmo cromatico tra sezioni
La sequenza di background crea ritmo emotivo nella pagina:
`bianco → grigio chiaro (#FAFAFA) → nero (#212121) → bianco`
Massimo 1-2 sezioni dark per pagina. La sezione dark deve avere purpose narrativo (es. la formazione finanziata, l'urgenza, il cambio di prospettiva).

### 5. Tipografia fluida e intenzionale
League Gothic solo per 1-2 momenti di massimo impatto (headline hero, numeri stat).
Lato per tutti i titoli di sezione — crea calore e leggibilità.
Roboto per tutto il resto — neutro e affidabile.
Non mescolare font senza ragione. Ogni variazione deve essere intenzionale.

### 6. Micro-interazioni sobrie e significative
Card hover: `translateY(-4px)` + shadow leggera — segnala interattività senza distrazione.
Button hover: colore più scuro + `translateY(-1px)` + shadow orange — risposta tattile.
Link: colore → orange su hover, transizione 0.2s. Nessuna sottolineatura di default.
Nessuna animazione che ritarda o disturba la lettura.

### 7. Mobile-first come mentalità, non come regola
Progettare prima per 375px (iPhone SE). Se funziona lì, scala bene ovunque.
L'utente mobile è quello con meno pazienza e meno contesto — deve capire tutto subito.

---

## PATTERN VISIVI MODERNI 2025/2026

### Cosa usare
- **Layout asimmetrici controllati**: testo e immagine non sempre 50/50 — 60/40 o 70/30 crea più tensione visiva
- **Grandi numeri tipografici**: le statistiche in League Gothic 48-64px sono più persuasive di grafici complessi
- **Bordi come struttura**: card con border 1.5px invece di shadow creano un look più contemporaneo e nitido
- **Sfondi texture leggera**: un pattern noise 3-5% opacity su sezioni dark aggiunge profondità senza distrazione
- **Spacing generoso tra elementi**: gap tra sezioni 24-32px, non 8-12px
- **Tag/label uppercase**: section-tag in uppercase con letter-spacing 2px prima dei titoli — crea ordine e professionalità
- **CTA con freccia**: `Scopri →` o `Prenota la call →` — la freccia indica direzione e azione

### Cosa evitare
- **Purple gradients su bianco**: il cliché del 2022-2023, fuori dal brand
- **Emoji nei titoli principali**: infantilizza il brand su target PMI
- **Ombre ovunque**: box-shadow su ogni elemento appiattisce la gerarchia
- **Troppi colori accent**: solo orange. Nient'altro.
- **Testo centrato su paragrafi lunghi**: al massimo 2-3 righe. I paragrafi vanno sempre allineati a sinistra
- **Immagini stock generiche**: AI che stringe la mano a robot — logorato, non credibile
- **Font Inter o Space Grotesk**: troppo usati, perdono identità

---

## COMPOSIZIONE SEZIONI — Architettura visiva

### Sezione standard (su sfondo chiaro)
```
[section-tag — uppercase orange]
[H2 — Lato bold]
[Sottotitolo — testo descrittivo gray-600]
[Corpo — grid o layout contenuto]
[CTA — se presente, una sola primaria]
```

### Sezione dark (sfondo gray-900)
```
[section-tag — orange su dark]
[H2 — bianco]
[Testo lead — bianco 80%]
[Corpo — card con border rgba bianco 12%]
[CTA — btn-primary orange + btn-secondary bordo bianco]
```

### Sezione featured/highlight (sfondo orange-light)
```
Solo per contenuti di massima importanza (urgency, offerta speciale, social proof)
[Bordo sinistro 4px orange]
[Testo diretto e breve]
[CTA immediata]
```

---

## PERFORMANCE — Design e codice che non rallenta

Ogni scelta visiva deve essere sostenibile lato performance.
Core Web Vitals influenzano SEO, GEO e esperienza utente.

### Regole obbligatorie nel codice prodotto

```html
<!-- Font loading corretto — preconnect PRIMA del link stylesheet -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=League+Gothic&family=Lato:wght@400;700&family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">

<!-- Immagini con dimensioni esplicite (previene CLS) -->
<img src="foto.jpg" alt="Roberto Schiraldi formatore AI" width="120" height="120" loading="lazy">

<!-- Immagine hero senza lazy (above the fold) -->
<img src="hero.jpg" alt="..." width="..." height="..." loading="eager" fetchpriority="high">
```

```css
/* Animazioni solo se l'utente non ha preferenza riduzione movimento */
@media (prefers-reduced-motion: no-preference) {
  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-in.visible { opacity: 1; transform: translateY(0); }
}
```

### CSS critico
Per le pagine del sito (non landing): il CSS above-the-fold (nav + hero) va inline nel `<head>`.
Il resto del CSS può essere in file separato con `rel="preload"`.

### Immagini
- Formato: WebP con fallback JPG
- Hero image: max 200KB ottimizzata
- Card images: max 80KB
- Sempre `width` e `height` espliciti per prevenire Cumulative Layout Shift

---

## SEZIONI AD ALTO IMPATTO — Come elevarle

### Hero Section
Il momento più importante della pagina. Deve fare 3 cose in 3 secondi:
1. Dire chi sei (con credenziale specifica, non generica)
2. Dire cosa fai (beneficio concreto, non descrizione del servizio)
3. Dire cosa fare ora (una sola CTA primaria chiarissima)

**Elevazione qualitativa:**
- Foto di Roberto: circolare con border orange 3px — umano e riconoscibile
- H1: almeno una parola in orange — crea fuoco visivo
- Le credenziali: bullet list orizzontale con dot orange — non testo inline
- Due CTA: primary piena + secondary outline — mai due primary
- Sfondo: bianco puro o con texture noise 2% — non grigio

### Social Proof Section
Le testimonianze non sono optional — sono prove di realtà.
**Elevazione qualitativa:**
- Rating aggregato con numero grande (4,8) in League Gothic orange
- Avatar con iniziale colorata (non icona generica)
- Quote in italic ma a 16px — mai sotto
- Nome + dettaglio specifico (corso, anno, outcome) — non solo nome

### Stats Section
I numeri sono l'arma più potente per il target PMI.
**Elevazione qualitativa:**
- Numeri in League Gothic 48-64px orange
- Label in Roboto 14px gray-600 — contrasto forte con il numero
- Fonte in italic 12px gray-500 — dà credibilità al dato
- Grid 3 colonne desktop, 1 colonna mobile

---

*Leggere questo file per ogni BUILD. La qualità visiva non è un optional — è parte del posizionamento di Roberto.*
