# WordPress + Gutenberg + Astra — Regole implementazione

Leggere SEMPRE prima di generare codice finale destinato a WordPress.
Il codice deve funzionare nell'ecosistema WP senza conflitti.

---

## STACK TECNICO SONODIGITALE

```
WordPress: 6.9.x
Tema: Astra (free o Pro)
Editor: Gutenberg (editor a blocchi nativo)
Hosting: IONOS
Builder: Gutenberg nativo — NON Elementor come default
Plugin attivi: LatePoint (prenotazioni), plugin SEO (da definire)
Repository: GitHub (schiral19-ai/sonodigitale-site)
```

---

## APPROCCI DI IMPLEMENTAZIONE — Scegli il giusto per ogni caso

### APPROCCIO A — HTML Custom Block (consigliato per sezioni complesse)
Per sezioni con CSS personalizzato che non si riproducono facilmente con blocchi Gutenberg nativi.

```html
<!-- In Gutenberg: blocco HTML personalizzato -->
<!-- Inserire via: + > HTML personalizzato -->

<section class="sd-hero">
  <div class="sd-container">
    <!-- contenuto -->
  </div>
</section>
```

Il CSS va nel **Customizer WordPress → CSS aggiuntivo** oppure in un file del child theme.

### APPROCCIO B — Blocchi nativi Gutenberg stilizzati
Per contenuti semplici (paragrafi, titoli, liste) che si gestiscono bene con i blocchi nativi.

```
Titolo → Blocco Titolo (H2, H3...)
Paragrafo → Blocco Paragrafo
Lista → Blocco Elenco
Immagine → Blocco Immagine (con alt obbligatorio)
Bottone → Blocco Pulsante
Colonne → Blocco Colonne
```

### APPROCCIO C — Full HTML page (per la homepage e landing page)
Il codice HTML completo viene caricato come template di pagina.
Usato già per la homepage-completa.html nel repo.

**Per questo approccio:**
1. Il file HTML va nel repo GitHub
2. Il CSS può essere inline nel `<style>` o in file separato `/assets/css/`
3. In WordPress: Pagina → Template → "Pagina intera" o "Blank Canvas" (Astra)
4. Il contenuto HTML viene incollato nel blocco HTML personalizzato

---

## CLASSI CSS — Prefixing per evitare conflitti

Tutti i CSS custom di SONODIGITALE devono avere il prefisso `sd-` per evitare conflitti con Astra e WordPress.

```css
/* CORRETTO — con prefisso */
.sd-hero { ... }
.sd-section { ... }
.sd-card { ... }
.sd-btn-primary { ... }

/* EVITARE — classi generiche che potrebbero collidere con WP/Astra */
.hero { ... }          /* potrebbe collidere */
.card { ... }          /* potrebbe collidere */
.btn { ... }           /* Astra usa questa classe */
```

**Eccezione:** Quando si usa l'approccio C (HTML completo), il CSS è isolato nella pagina e i conflitti sono minimi. In quel caso le classi senza prefisso sono accettabili.

---

## CSS CUSTOM PROPERTIES — Dove metterle

Le CSS custom properties (`:root { --orange: ... }`) vanno inserite in:

**Opzione 1 (consigliata):** WordPress Customizer → CSS aggiuntivo
```css
:root {
  --orange: #FC7E15;
  --orange-dark: #D96A0B;
  /* etc. */
}
```

**Opzione 2:** Child theme → `style.css`
Preferire se si ha un child theme attivo.

**Opzione 3:** Inline nel `<style>` dell'HTML page
Solo per approccio C (pagine HTML complete standalone).

---

## ASTRA — Configurazioni importanti

### Cosa configurare in Astra per allinearsi al brand:

```
Aspetto → Personalizza → Globale → Font del corpo:
  → Famiglia: Roboto
  → Dimensione: 16px
  → Altezza riga: 1.65

Aspetto → Personalizza → Globale → Colori:
  → Colore primario: #FC7E15
  → Colore link: #FC7E15
  → Colore hover link: #D96A0B

Aspetto → Personalizza → Intestazione → Altezza: 64px

Aspetto → Personalizza → Larghezza contenuto: 1140px
```

### Cosa NON toccare in Astra
- Non modificare i font degli heading globali da Astra — li gestiamo con CSS custom
- Non usare i "color schemes" di Astra — usiamo le nostre CSS custom properties
- Non attivare Elementor come editor default — rimaniamo su Gutenberg

---

## GOOGLE FONTS — Caricamento corretto in WP

In WordPress, non caricare Google Fonts direttamente nell'HTML delle pagine.
Usare il metodo corretto per WP:

**Metodo 1 — Customizer (semplice):**
```
Aspetto → Personalizza → Globale → Font del corpo → seleziona Google Font
```
Astra gestisce il caricamento ottimizzato.

**Metodo 2 — functions.php del child theme:**
```php
function sonodigitale_enqueue_fonts() {
  wp_enqueue_style(
    'sonodigitale-fonts',
    'https://fonts.googleapis.com/css2?family=League+Gothic&family=Lato:wght@400;700&family=Roboto:wght@400;500;700&display=swap',
    array(),
    null
  );
}
add_action('wp_enqueue_scripts', 'sonodigitale_enqueue_fonts');
```

**Metodo 3 — Solo per pagine HTML complete (Approccio C):**
Includere il preconnect + link direttamente nell'`<head>` del file HTML.

---

## SCHEMA MARKUP JSON-LD — Dove inserirlo in WP

Per le pagine del sito (non HTML complete), lo schema markup va inserito tramite plugin SEO.

**Con Rank Math o Yoast:**
- Ogni pagina può avere schema markup aggiuntivo
- Inserire il JSON-LD nel campo "Schema" del plugin
- Oppure usare un blocco HTML in fondo alla pagina con il tag `<script type="application/ld+json">`

**Con pagine HTML complete (Approccio C):**
Il JSON-LD è già nell'`<head>` del file HTML — come nella homepage attuale.

---

## IMMAGINI — Gestione ottimale in WP

```
Formato preferito: WebP (con fallback JPG)
Upload: tramite Media Library di WordPress
Dimensioni:
  - Hero image: max 1440x800px, ottimizzata < 200KB
  - Card/thumbnail: max 800x600px, < 80KB
  - Avatar/foto profilo: max 400x400px, < 50KB

Attributi obbligatori:
  - alt text sempre compilato (SEO + accessibilità)
  - In Gutenberg: campo Alt testo nella barra laterale del blocco immagine

Lazy loading:
  - WordPress aggiunge loading="lazy" automaticamente
  - Per le immagini above the fold: aggiungere loading="eager" nel blocco HTML
```

---

## FORM E PRENOTAZIONI — LatePoint

LatePoint è già installato. Per le CTA di prenotazione call:

```html
<!-- Bottone che apre LatePoint booking -->
<a href="#" class="sd-btn-primary latepoint-book-button" 
   data-service-id="1" 
   data-agent-id="1">
  Prenota una call gratuita
</a>
```

Oppure usare il blocco Gutenberg di LatePoint (se disponibile) per il form inline.

**Per le landing page:** Il form di LatePoint può essere embedded direttamente nella landing come form principale di conversione.

---

## PERFORMANCE — Checklist pre-pubblicazione WP

Prima di pubblicare qualsiasi pagina:

- [ ] Immagini ottimizzate (WebP, dimensioni corrette)
- [ ] CSS aggiuntivo nel Customizer (non inline nelle pagine, tranne Approccio C)
- [ ] Google Fonts caricati con preconnect
- [ ] Schema markup JSON-LD presente (pagine principali)
- [ ] Alt text su tutte le immagini
- [ ] Meta title e meta description compilati (plugin SEO)
- [ ] Pagina testata su mobile (Chrome DevTools → 375px)
- [ ] Contrasto verificato (Chrome DevTools → Accessibility)
- [ ] Link interni funzionanti
- [ ] Form testato con submission di prova

---

## WORKFLOW GITHUB → WORDPRESS

Il repo GitHub è il punto di verità del codice.
Il flusso corretto:

```
1. Sviluppo/modifica in locale o Claude Code
2. Commit su GitHub (branch main o branch specifico)
3. Test su GitHub Pages (per HTML completi)
4. Copia codice → WordPress
5. Test su WP staging (se disponibile) o direttamente in produzione
6. Aggiornare README.md del repo con le modifiche
```

Per il futuro: valutare GitHub Actions per deploy automatico su IONOS.

---

*Aggiornare quando cambiano plugin, tema o configurazioni WordPress.*
