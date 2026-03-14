# SONODIGITALE — Homepage Website

## Progetto
Sito web per **SONODIGITALE** di Roberto Schiraldi — Formazione e consulenza AI in Lombardia.

**Brand:** SONODIGITALE  
**Dominio:** sonodigitale.it  
**Piattaforma:** WordPress 6.9.1 + Astra + Gutenberg  
**Hosting:** IONOS  

---

## Struttura Repository

```
sonodigitale-site/
├── homepage-completa.html      # Homepage completa in un unico file (riferimento)
├── assets/
│   ├── css/
│   │   └── style.css           # CSS completo (va nell'header del tema WordPress)
│   ├── js/
│   │   └── main.js             # JavaScript (fade-in animations)
│   └── schema-markup.json      # Schema JSON-LD (va nell'<head> di ogni pagina)
├── sections/                   # Sezioni HTML separate per Gutenberg
│   ├── 00-nav.html             # Navigazione (gestita dal tema Astra)
│   ├── 01-hero.html            # Hero + identità + CTA
│   ├── 02-smistamento.html     # 3 card personas (aziende/professionisti/inoccupati)
│   ├── 03-dati.html            # Dati mercato AI Italia (Osservatorio PoliMI 2025)
│   ├── 04-formazione.html      # Formazione finanziata — 3 step + fondi + urgenza
│   ├── 05-testimonianze.html   # 4 recensioni reali Google Atoma (4.8/5)
│   ├── 06-faq.html             # FAQ preview (3 domande) + link pagina completa
│   ├── 07-cta-finale.html      # CTA finale — lead magnet + call conoscitiva
│   └── 08-footer.html          # Footer (gestito dal tema Astra)
├── docs/
│   └── SONODIGITALE_Homepage_Specifica_v4.docx  # Specifica completa
└── README.md
```

---

## Implementazione in WordPress/Gutenberg

### Passo 1: CSS
Inserire il contenuto di `assets/css/style.css` in:
- **Astra** → Aspetto → Personalizza → CSS aggiuntivo
- Oppure in un plugin come "Simple Custom CSS and JS"

### Passo 2: Schema Markup JSON-LD
Inserire il contenuto di `assets/schema-markup.json` nell'`<head>` del sito:
- **Astra** → Aspetto → Personalizza → Avanzato → Header Scripts
- Avvolgere in: `<script type="application/ld+json">` ... `</script>`

### Passo 3: Font Google
Aggiungere nell'header del tema:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=League+Gothic&family=Lato:wght@300;400;700&family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
```

### Passo 4: Sezioni HTML
Per ogni file in `sections/` (da 01 a 07):
1. In Gutenberg, aggiungi un blocco **"HTML personalizzato"**
2. Incolla il contenuto del file corrispondente
3. Ripeti per ogni sezione nell'ordine

**Nota:** La navigazione (00-nav.html) e il footer (08-footer.html) sono normalmente gestiti dal tema Astra, non vanno nel contenuto della pagina.

### Passo 5: JavaScript
Inserire `assets/js/main.js` nel footer del sito:
- **Astra** → Aspetto → Personalizza → Avanzato → Footer Scripts
- Avvolgere in: `<script>` ... `</script>`

---

## Specifiche Design

### Colori Brand
| Colore | Hex | Uso |
|--------|-----|-----|
| Arancione | `#FC7E15` | CTA, accenti, numeri, highlight |
| Arancione chiaro | `#FFF3E6` | Sfondi accent |
| Arancione scuro | `#D96A0B` | Hover states |
| Nero | `#000000` | Testo titoli |
| Bianco | `#FFFFFF` | Sfondi principali |
| Grigi | `#212121` → `#FAFAFA` | Scala di grigi per testi e sfondi |

### Font
| Font | Uso | Peso |
|------|-----|------|
| League Gothic | Brand name, numeri grandi | Regular |
| Lato | Titoli sezioni, heading | 300, 400, 700 |
| Roboto | Corpo testo, UI | 400, 500, 700 |

### Breakpoint Responsive
- **Desktop:** > 768px (layout completo)
- **Tablet:** ≤ 768px (colonne singole, menu hamburger)
- **Mobile:** ≤ 480px (font ridotti, bottoni full-width)

---

## SEO / GEO

### Title Tag
`SONODIGITALE | Formazione AI Finanziata e Consulenza — Lombardia` (57 car.)

### Meta Description
`Roberto Schiraldi, formatore AI accreditato Regione Lombardia. Percorsi di formazione finanziata fino al 100% per PMI, professionisti e inoccupati. Prenota una call gratuita.` (155 car.)

### Schema Markup (JSON-LD)
- **Person:** Roberto Schiraldi + credenziali + affiliazione Atoma SRL
- **Organization:** SONODIGITALE + area served Lombardia
- **LocalBusiness:** indirizzo Varese + contatti
- **HowTo:** "Come accedere alla formazione AI finanziata" (3 step)
- **FAQPage:** 3 domande + risposte strutturate
- **AggregateRating:** 4.8/5 su 49 recensioni (Atoma Google)

### 5 Golden Query GEO
1. "Formazione AI finanziata Lombardia"
2. "Consulente AI per PMI Lombardia"
3. "Corso AI gratuito inoccupati GOL"
4. "Come usare AI in una piccola impresa"
5. "Chi fa formazione intelligenza artificiale in Lombardia"

---

## NAP (Name, Address, Phone) — Coerenza obbligatoria
Deve essere IDENTICO su sito, Google Business Profile, LinkedIn e directory:

- **Nome:** Roberto Schiraldi
- **Località:** Varese, Lombardia
- **Email:** roberto@sonodigitale.it

---

## Numeri verificabili (aggiornare trimestralmente)
- **70+ persone formate sull'AI** (50 corsisti GOL in 10 edizioni + 20 professionisti/aziende)
- **10 edizioni corso erogate** (da giugno 2025)
- **4.8/5** rating Google Atoma Formazione (49 recensioni)
- Ultimo aggiornamento: marzo 2026

---

## TODO
- [ ] Sostituire placeholder foto con foto reale Roberto
- [ ] Collegare dominio sonodigitale.it su IONOS
- [ ] Inserire P.IVA nel footer
- [ ] Configurare form lead magnet (email marketing: Brevo/Mailchimp)
- [ ] Collegare CTA "Prenota call" a LatePoint
- [ ] Creare lead magnet PDF "10 Modi per Usare l'AI"
- [ ] Testare schema markup con Google Rich Results Test
- [ ] Creare e ottimizzare Google Business Profile
- [ ] Implementare cookie banner GDPR
- [ ] Creare pagine fase 1: Formazione, Chi Sono, FAQ, Contatti

---

## Mappa sito completa

### Fase 1 (lancio)
- Homepage ← **QUESTO FILE**
- /formazione (3 sezioni: aziende, professionisti, GOL)
- /chi-sono (storia + E-E-A-T + Atoma)
- /contatti (form + LatePoint + NAP)
- /faq (20-30 domande strutturate per GEO)

### Fase 2 (mese 2)
- /servizi (consulenza AI)
- /testimonianze (pagina dedicata)
- /blog (articoli SEO + cluster tematici)

### Fase 3 (mese 3+)
- /video-corsi (catalogo + acquisto)

---

*Progetto SONODIGITALE — Roberto Schiraldi — Marzo 2026*
