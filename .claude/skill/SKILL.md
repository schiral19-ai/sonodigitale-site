---
name: sonodigitale-frontend
description: >
  Framework completo di design e sviluppo frontend per SONODIGITALE di Roberto Schiraldi.
  Attiva SEMPRE questa skill quando lavori su qualsiasi pagina, componente, sezione o landing page di sonodigitale.it.
  Include brand system completo, type scale con regole di leggibilita per target 40+, design token aggiornati,
  principi di design moderni 2025/2026, pattern per tutte le pagine del sito (9 pagine + landing),
  logiche WordPress/Gutenberg/Astra, component library completa e due modalita operative BUILD e AUDIT.
  Non costruire ne modificare nulla senza leggere questa skill prima.
  Usare anche per nuove landing page, landing lead gen, pagine promo, componenti riutilizzabili,
  revisioni design, fix leggibilita mobile, aggiornamento brand kit.
---

# SONODIGITALE Frontend Design System

Framework operativo per costruire e migliorare sonodigitale.it con qualità produzione, coerenza di brand e leggibilità ottimale per il target reale di Roberto Schiraldi.

**Target utenti reali**: PMI 40-55 anni, inoccupati 30-50 anni, professionisti 35-60 anni.
Questo determina ogni scelta di design: dimensioni testo, contrasti, spazio, semplicità.

---

## PRIMA DI AGIRE — Scegli la modalità e i references da leggere

### BUILD — Costruisci da zero
Nuova pagina, nuova sezione, nuovo componente, landing page.

```
Leggi sempre:
  → SKILL.md (questo file)
  → references/design-vision.md
  → references/wordpress-gutenberg.md

Poi leggi il reference specifico per il task:
  → references/page-types.md        (pagine sito: home, chi sono, formazione, faq, contatti, servizi, blog...)
  → references/landing-system.md    (landing page: lead gen, promo, eventi, GOL, PMI, professionisti)
  → references/component-library.md (componenti singoli: form, card, bottoni, nav...)
  → references/personas-ux.md       (quando devi decidere gerarchia, CTA, percorso utente)
```

### AUDIT — Analizza e migliora l'esistente
Revisione codice esistente, fix leggibilità, miglioramento design, verifica accessibilità.

```
Leggi sempre:
  → SKILL.md (questo file)
  → references/component-library.md

Poi:
  1. Esegui la Audit Checklist in questo file punto per punto
  2. Riporta ogni problema: [CRITICO] / [IMPORTANTE] / [MIGLIORAMENTO]
  3. Proponi correzioni con codice specifico
  4. Dopo approvazione: applica tutto
  5. Ri-esegui checklist per verificare
```

---

## BRAND SYSTEM

### Identità
- **Brand**: SONODIGITALE
- **Persona**: Roberto Schiraldi — formatore AI accreditato Regione Lombardia
- **Mission**: Rendere l'AI accessibile a PMI, professionisti e inoccupati
- **Tono visivo**: Professionale ma caldo. Autorevole senza distanza. Arancione come energia e fiducia.

### Colori — CSS custom properties canoniche

```css
:root {
  /* PRIMARY */
  --orange:       #FC7E15;   /* Accento primario — CTA, highlight, numeri, link attivi */
  --orange-dark:  #D96A0B;   /* Hover su elementi arancione */
  --orange-light: #FFF3E6;   /* Background sezioni calde, card featured */

  /* NEUTRAL SCALE */
  --black:      #000000;
  --white:      #FFFFFF;
  --gray-900:   #212121;     /* Testo principale, titoli, sezioni dark */
  --gray-800:   #424242;     /* Testo secondario importante */
  --gray-700:   #616161;     /* Testo body standard — MINIMO per testo leggibile */
  --gray-600:   #757575;     /* Descrizioni — solo su sfondo bianco */
  --gray-500:   #9E9E9E;     /* ⚠️ SOLO metadati/note minime — MAI testo body */
  --gray-300:   #E0E0E0;     /* Bordi, divisori */
  --gray-200:   #EEEEEE;     /* Bordi leggeri, card */
  --gray-100:   #F5F5F5;     /* Background sezioni alternate */
  --gray-50:    #FAFAFA;     /* Background quasi-bianco */
}
```

### Regole contrasto — non derogare mai

| Combinazione | Contrasto | Regola |
|---|---|---|
| `--gray-700` (#616161) su bianco | 5.9:1 ✅ | Standard consigliato per testo body |
| `--gray-600` (#757575) su bianco | 4.6:1 ✅ | OK per testi secondari |
| `--gray-500` (#9E9E9E) su bianco | 2.8:1 ❌ | **VIETATO** per testo leggibile |
| Bianco puro su `--gray-900` | 16:1 ✅ | Ottimo per sezioni dark |
| Bianco 80% su `--gray-900` | 12:1 ✅ | Testo body su dark |
| Bianco 60% su `--gray-900` | 7:1 ✅ | Testo secondario su dark — minimo accettabile |
| Bianco 40% su `--gray-900` | 4:1 ⚠️ | Solo metadati non critici |
| `--orange` (#FC7E15) su bianco | 3.0:1 ⚠️ | Solo testi grandi (18px+) o decorativi |

### Tipografia — Font stack

```css
--font-display: 'League Gothic', sans-serif;  /* Hero headline, numeri grandi, impatto */
--font-heading: 'Lato', sans-serif;           /* Titoli sezione, card heading, nav */
--font-body:    'Roboto', sans-serif;         /* Tutto il body text, UI */
```

**Carattere del brand tipografico:**
- **League Gothic** = forza, impatto, modernità — usare con parsimonia per massimo effetto
- **Lato** = calore, leggibilità, fiducia — il font delle relazioni umane
- **Roboto** = chiarezza, neutralità — testi lunghi, interfaccia, form

---

## TYPE SCALE — Regole di leggibilità per target 40+

Il target principale ha presbiopismo iniziale su mobile. Standard più alti del normale sono non negoziabili.

```css
:root {
  /* BASE — mai andare sotto questi valori per testo leggibile */
  --text-base:    16px;   /* Body text — minimo assoluto ovunque */
  --text-sm:      15px;   /* Testo secondario — MINIMO accettabile su mobile */
  --text-xs:      14px;   /* Note, metadati — solo desktop, mai body su mobile */
  --text-xxs:     13px;   /* SOLO etichette UI (tag, badge) — MAI testo leggibile */

  /* BODY */
  --text-body:    16px;
  --text-body-lg: 17px;   /* Paragrafi hero, intro sezione enfatizzata */
  --text-lead:    18px;   /* Sottotitoli sezione, primo paragrafo */

  /* HEADINGS */
  --text-h4: 18px;
  --text-h3: 20px;
  --text-h2-mobile: 26px;
  --text-h2-tablet: 30px;
  --text-h2:        36px;
  --text-h1-mobile: 28px;
  --text-h1-tablet: 36px;
  --text-h1:        44px;

  /* DISPLAY — League Gothic */
  --text-display:    48px;   /* Numeri statistiche, hero accent */
  --text-display-lg: 64px;   /* Solo hero principale desktop */

  /* LINE HEIGHT */
  --lh-tight:   1.15;   /* Solo titoli hero molto grandi */
  --lh-heading: 1.30;   /* Tutti gli heading */
  --lh-body:    1.65;   /* Body text — mai sotto 1.6 */
  --lh-relaxed: 1.80;   /* FAQ, testi lunghi, descrizioni dettagliate */

  /* MISURA RIGA OTTIMALE — max-width sui paragrafi */
  --measure-card:  480px;
  --measure-body:  640px;
  --measure-wide:  760px;   /* Massimo assoluto per testo leggibile */
}
```

### Decisione rapida — prima di ogni font-size

1. Sarà letto su mobile? → minimo **15px**
2. È testo body (paragrafi, card description, step text)? → **16px**
3. È testo secondario (note, fonte, metadati)? → **14px solo desktop**
4. È etichetta UI (tag, badge, label form)? → **13px accettabile**
5. È su sfondo dark? → **+1px rispetto al corrispondente su sfondo chiaro**

### Override mobile obbligatori

```css
@media (max-width: 768px) {
  body { font-size: 16px; line-height: 1.65; }

  p, .card p, .card-description,
  .step-card p, .persona-card p { font-size: 16px; line-height: 1.65; }

  .text-secondary, .fund-card p  { font-size: 15px; }
  .text-meta, .review-detail     { font-size: 14px; }

  /* Touch targets minimi */
  .btn, .nav-cta, .faq-question,
  a.card-link                    { min-height: 44px; }
  .nav-hamburger                 { padding: 10px; min-width: 44px; min-height: 44px; }
}
```

---

## LAYOUT SYSTEM

```css
:root {
  --max-width: 1140px;

  /* SPACING SCALE */
  --space-xs:  8px;
  --space-sm:  16px;
  --space-md:  24px;
  --space-lg:  32px;
  --space-xl:  48px;
  --space-2xl: 64px;
  --space-3xl: 88px;

  /* SECTION PADDING */
  --section-mobile:  56px 0;
  --section-tablet:  72px 0;
  --section-desktop: 88px 0;

  /* BORDER RADIUS */
  --radius-sm:  6px;
  --radius-md:  8px;
  --radius-lg:  12px;
  --radius-xl:  16px;
  --radius-2xl: 24px;

  /* SHADOWS */
  --shadow-sm:     0 1px 4px rgba(0,0,0,0.06);
  --shadow-md:     0 4px 16px rgba(0,0,0,0.08);
  --shadow-lg:     0 8px 32px rgba(0,0,0,0.10);
  --shadow-orange: 0 4px 20px rgba(252,126,21,0.25);

  /* TRANSITIONS */
  --transition-fast: 0.15s ease;
  --transition-base: 0.25s ease;
  --transition-slow: 0.4s ease;
}
```

### Breakpoints

```
< 480px   → mobile small  — colonna singola, font minima, padding 20px
480-768px → mobile/tablet — grid max 2 col, font in transizione
768-1024px → tablet       — grid completo, font quasi-desktop
> 1024px  → desktop       — max-width attivo, font scale piena
```

---

## AUDIT CHECKLIST

In modalità AUDIT, verificare ogni punto. Formato risposta:
`[CRITICO/IMPORTANTE/MIGLIORAMENTO] Problema → Causa → Correzione`

### Leggibilità mobile
- [ ] font-size sotto 16px su testo body o card description
- [ ] line-height sotto 1.6 su paragrafi
- [ ] testo italic sotto 15px
- [ ] max-width su paragrafi assente o sopra 760px
- [ ] hero-text sotto 16px su mobile

### Contrasto
- [ ] `--gray-500` su bianco per testo body
- [ ] bianco sotto 60% opacità su dark per testo leggibile
- [ ] `--orange` su bianco per testo body sotto 18px

### Touch targets
- [ ] bottoni sotto min-height 44px
- [ ] hamburger con area toccabile sotto 44x44px
- [ ] link adiacenti con gap inferiore a 8px

### Struttura e gerarchia
- [ ] più di una btn-primary visibile nella stessa area
- [ ] sezioni con padding sotto 48px su mobile
- [ ] container senza padding laterale mobile

### Performance e accessibilità
- [ ] immagini senza alt attribute
- [ ] immagini senza width/height espliciti (causa CLS)
- [ ] form inputs senza aria-label
- [ ] animazioni senza prefers-reduced-motion
- [ ] Google Fonts senza preconnect
- [ ] CSS non organizzato con custom properties (rischio incoerenza)

---

## REFERENCES — Quando leggere cosa

| Task | References da leggere |
|---|---|
| Homepage (nuova o revisione) | design-vision + page-types (§ Homepage) + wordpress-gutenberg |
| Pagina Chi sono | design-vision + page-types (§ Chi sono) + personas-ux + wordpress-gutenberg |
| Pagina Formazione finanziata | design-vision + page-types (§ Formazione) + landing-system + wordpress-gutenberg |
| Pagina FAQ | page-types (§ FAQ) + wordpress-gutenberg |
| Pagina Contatti | page-types (§ Contatti) + component-library (§ Form) + wordpress-gutenberg |
| Pagina Servizi (Fase 2) | page-types (§ Servizi) + wordpress-gutenberg |
| Blog (Fase 2) | page-types (§ Blog) + wordpress-gutenberg |
| Video Corsi (Fase 3) | page-types (§ Video Corsi) + landing-system + wordpress-gutenberg |
| Landing lead gen | landing-system + design-vision + component-library |
| Landing GOL / PMI / professionisti | landing-system + personas-ux + design-vision |
| Componente UI singolo | component-library |
| Decisione gerarchia / CTA | personas-ux |

---

## BRAND KIT — Stato e aggiornamento

Questo file è la **fonte di verità** del design system SONODIGITALE.

Quando un miglioramento viene validato in produzione:
1. Aggiornare i valori in questo file
2. Aggiornare `docs/brand-kit.md` nel repo GitHub
3. Applicare progressivamente alle altre pagine

**Valori in revisione attiva (da validare su homepage v2):**
- font-size body mobile: 13-14px → 15-16px
- contrasto testi secondari: `--gray-500` → `--gray-700`
- touch target hamburger: padding 4px → padding 10px
- line-height card descriptions: 1.5 → 1.65

---

*Versione: 2.0 — Marzo 2026 | Roberto Schiraldi / SONODIGITALE*
*Aggiornare ogni volta che un pattern viene validato in produzione.*
