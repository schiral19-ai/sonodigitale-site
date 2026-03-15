# Page Types — SONODIGITALE

Pattern strutturali, schema markup e note UX per ogni pagina del sito.
Leggere la sezione specifica della pagina che stai costruendo.

---

## MAPPA SITO — Stato per fase

```
FASE 1 — Lancio (5 pagine)
├── Homepage          → Hero + smistamento + social proof
├── Formazione fin.   → HowTo + Course + urgenza
├── Chi sono          → Storia + Person + E-E-A-T
├── Contatti          → Form + LatePoint + NAP
└── FAQ — hub GEO     → FAQPage — asset strategico n.1

FASE 2 — Mese 2 (3 pagine)
├── Servizi           → Schema: Service x3
├── Testimonianze     → Schema: Review + Rating
└── Blog              → Schema: Article + Author

FASE 3 — Mese 3+ (1 pagina)
└── Video Corsi       → Schema: Product + Offer
```

### 5 Golden Query GEO — ogni pagina deve contribuire a rispondere a queste:
1. "Formazione AI finanziata Lombardia"
2. "Consulente AI per PMI Varese / Lombardia"
3. "Corso AI gratuito inoccupati GOL"
4. "Come usare AI in una piccola impresa"
5. "Chi fa formazione intelligenza artificiale in Lombardia"

---

## HOMEPAGE

**Obiettivo**: Smistare le 3 personas verso il percorso giusto + costruire fiducia iniziale
**Schema markup**: Person + Organization + LocalBusiness + HowTo + FAQPage + AggregateRating

### Struttura sezioni (ordine fisso)
1. NAV — sticky
2. HERO — foto + headline + credenziali + 2 CTA
3. SMISTAMENTO — 3 card persona (azienda / professionista / lavoro)
4. DATI — statistiche + ribaltamento verso la soluzione
5. FORMAZIONE FINANZIATA — dark section, 3 step + fondi + urgency
6. TESTIMONIANZE — rating aggregato + 4 recensioni
7. FAQ — 3 domande preview + link pagina completa
8. CTA FINALE — box 2 opzioni (guida gratuita / call)
9. FOOTER — 4 colonne + newsletter

### Note critiche homepage
- La sezione SMISTAMENTO deve essere above-the-fold o subito dopo — è la chiave della navigazione
- Le 3 card persona devono avere CTA specifiche, non generiche
- La sezione DATI serve a creare urgenza con numeri reali — non eliminarla
- La sezione dark (FORMAZIONE) è il momento di massima persuasione — curarla molto

---

## FORMAZIONE FINANZIATA

**Obiettivo**: Convertire le 3 personas su percorsi specifici + spiegare i finanziamenti disponibili
**Schema markup**: HowTo (come accedere ai finanziamenti) + Course + FAQPage

### Struttura sezioni
1. HERO PAGE — headline specifica + intro + 2 CTA (call / scopri finanziamenti)
2. SMISTAMENTO PERSONA — 3 tab o sezioni (Aziende / Professionisti / Inoccupati GOL)
3. COME FUNZIONA — 3 step HowTo
4. FONDI DISPONIBILI — tabella o card con importi e condizioni
5. IL PROGRAMMA — moduli, durata, modalità
6. RISULTATI — dati concreti o case study
7. URGENCY — posti limitati, scadenze bandi
8. TESTIMONIANZE — filtrabili per tipo (azienda / professionista / GOL)
9. FAQ FORMAZIONE — domande specifiche sui finanziamenti
10. CTA — prenota call

### Note critiche
- Questa è la pagina dove Sara (GOL) arriva direttamente da Centro Impiego → chiarezza assoluta
- Marco/Giulia (PMI) arrivano da LinkedIn → ROI e finanziamenti subito visibili
- I 3 tab persona evitano che ogni utente legga tutto — personalizzazione immediata
- Lo schema HowTo è fondamentale per la GEO — risponde a "come accedere formazione AI finanziata"

---

## CHI SONO

**Obiettivo**: Costruire fiducia profonda — E-E-A-T al massimo
**Schema markup**: Person (dettagliato) + Organization + ItemList (competenze)

### Struttura sezioni
1. HERO PERSONA — foto grande + nome + titolo preciso + tagline personale
2. LA MIA STORIA — narrativa personale breve (non CV) — perché faccio questo
3. CREDENZIALI FORMALI — accreditamento Regione Lombardia, Atoma SRL, formazione
4. ESPERIENZA CONCRETA — numeri reali: 70+ persone, 10 edizioni, anni di attività
5. METODOLOGIA — come lavoro, cosa rende diverso il mio approccio
6. COLLABORAZIONI — Atoma SRL, Regione Lombardia (logo se possibile)
7. TESTIMONIANZE — 2-3 testimonianze selezionate
8. CTA — prenota una call / contattami

### Note E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)
- **Experience**: storie concrete di aule GOL, risultati reali studenti
- **Expertise**: credenziali specifiche, non generiche — "accreditato Regione Lombardia" non "esperto"
- **Authoritativeness**: citare Atoma SRL, Progetto GOL, enti istituzionali
- **Trustworthiness**: foto reale, indirizzo fisico (Varese), email, LinkedIn verificato

### Note critiche
- Anna/Roberto (professionisti) arrivano qui da LinkedIn → la storia personale è cruciale
- Il tono è umano, non curriculum vitae — "Ecco perché faccio questo" non "Ecco le mie qualifiche"
- Questa pagina supporta tutte le altre — link da homepage, formazione, FAQ

---

## FAQ — Hub GEO

**Obiettivo**: Asset strategico n.1 per GEO — rispondere alle domande reali del target
**Schema markup**: FAQPage (ogni domanda come Question + Answer)

### Struttura
1. INTRO — brief (2-3 righe max) su cosa trovano nella pagina
2. CATEGORIE FAQ — tab o sezioni filtrabili:
   - Per chi cerchi lavoro (GOL, inoccupati)
   - Per aziende e PMI
   - Per professionisti
   - Sul programma e i contenuti
   - Sui finanziamenti
3. TUTTE LE FAQ — lista completa con accordion
4. CTA — "Non trovi la risposta? Scrivimi"

### Regole per ogni risposta FAQ (GEO-ottimizzata)
- Inizia con la risposta diretta (non con "Ottima domanda" o rimandi)
- Lunghezza ideale: 80-200 parole
- Includere sempre almeno un dato specifico (%, €, ore, ecc.)
- Usare sotto-liste se la risposta ha più punti
- Citare enti reali (Regione Lombardia, Atoma SRL) per autorevolezza
- Chiudersi con un invito all'azione naturale

### Note critiche
- Sara (GOL) arriva qui direttamente → le FAQ per inoccupati devono essere chiarissime
- Questa pagina è la più importante per la GEO — le AI citano spesso FAQ ben strutturate
- Aggiornare con nuove domande reali emerse dai corsisti (fonte preziosa)

---

## CONTATTI

**Obiettivo**: Convertire all'azione (call o email) con minima frizione
**Schema markup**: LocalBusiness + ContactPage

### Struttura
1. HEADLINE — diretta: "Parliamo" o "Inizia da qui"
2. OPZIONI CONTATTO — 3 modalità chiare:
   - Prenota call (LatePoint o Calendly) — CTA primaria
   - Email diretta — CTA secondaria
   - WhatsApp — per chi preferisce (opzionale)
3. FORM SEMPLICE — max 4 campi: nome, email, tipo richiesta (dropdown), messaggio
4. NAP — Name, Address, Phone ben visibili (per GEO locale)
5. RASSICURAZIONE — "Rispondo entro 24h", "Nessun impegno", "Call gratuita"

### Note critiche
- Forma MINIMAL — ogni campo in più riduce le conversioni
- LatePoint (già installato su WP) per la prenotazione call — non link esterno
- Il NAP (Name Address Phone) strutturato è fondamentale per GEO locale
- Nessuna distrazione: no sidebar, no menu espanso — focus totale sulla conversione

---

## SERVIZI (Fase 2)

**Obiettivo**: Dettaglio dei 3 pilastri del business per chi vuole capire prima di contattare
**Schema markup**: Service x3 (formazione, consulenza, video corsi)

### Struttura
1. INTRO — brief value proposition
2. SERVIZIO 1: Formazione finanziata — target, benefici, come funziona, CTA
3. SERVIZIO 2: Consulenza AI per PMI — target, benefici, processo, CTA
4. SERVIZIO 3: Video corsi — target, contenuti, piattaforma, CTA
5. CONFRONTO — tabella o card comparativa dei 3 percorsi
6. CTA UNIFICATA — "Non sai quale fa per te? Parliamone"

---

## TESTIMONIANZE (Fase 2)

**Obiettivo**: Social proof dedicata — costruire fiducia con prove concrete
**Schema markup**: Review + AggregateRating

### Struttura
1. RATING AGGREGATO — score, numero recensioni, fonte
2. FILTRI — per tipo (GOL / PMI / Professionista)
3. GRID RECENSIONI — tutte le recensioni, paginabili
4. VIDEO TESTIMONIAL — se disponibili (alta priorità per credibilità)
5. LOGHI AZIENDE — se disponibili
6. CTA — "Unisciti a chi ha già scelto SONODIGITALE"

---

## BLOG (Fase 2)

**Obiettivo**: SEO organico + GEO + lead generation da traffico organico
**Schema markup**: Article + Author (per ogni articolo) + Blog (per listing)

### Struttura listing
1. HERO BLOG — headline + ultimo articolo featured
2. CATEGORIE — filtri per topic (Prompt Engineering / Formazione finanziata / AI per PMI / Tools)
3. GRID ARTICOLI — 6-9 per pagina, paginazione
4. NEWSLETTER CTA — iscrizione sidebar o banner intermedio

### Struttura singolo articolo
1. HEADER — titolo H1 + categoria + data + author (Roberto con foto)
2. READING TIME + SOMMARIO — per articoli lunghi
3. CORPO ARTICOLO — H2/H3 strutturati, immagini ottimizzate
4. CTA INLINE — dopo introduzione e a fine articolo
5. RELATED ARTICLES — 3 articoli correlati
6. AUTHOR BOX — Roberto + bio breve + link chi sono

### Keyword target prioritarie per il blog
- "formazione AI finanziata Lombardia" (pillar)
- "prompt engineering guida pratica"
- "come usare ChatGPT per lavoro"
- "AI per piccole imprese Italia"
- "corso AI gratuito inoccupati Lombardia"

---

## VIDEO CORSI (Fase 3)

**Obiettivo**: Vendita diretta corsi online — conversione da traffico caldo
**Schema markup**: Product + Offer + AggregateRating

### Struttura
1. HERO CORSO — titolo + outcome + CTA acquisto / accesso
2. A CHI SERVE — 3-4 bullet specifici
3. COSA IMPARERAI — moduli con descrizione
4. ANTEPRIMA — video trailer o screenshot lezioni
5. ISTRUTTORE — Roberto + credenziali (link Chi sono)
6. RECENSIONI — rating + recensioni dei corsisti
7. FAQ CORSO — domande specifiche sul corso
8. PRICING — prezzo chiaro + CTA acquisto
9. GARANZIE — soddisfatti o rimborsati, supporto, aggiornamenti

---

*Aggiornare questo file man mano che le pagine vengono costruite e validate.*
