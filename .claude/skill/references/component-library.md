# Component Library — SONODIGITALE

Tutti i componenti UI riutilizzabili del sito.
Usare sempre questi pattern — non inventare varianti non documentate.

---

## BOTTONI

```css
/* BASE — tutti i bottoni */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-family: var(--font-body);
  font-weight: 700;
  font-size: 15px;
  padding: 14px 28px;
  border-radius: var(--radius-md);
  border: none;
  cursor: pointer;
  transition: all var(--transition-base);
  text-decoration: none;
  min-height: 48px; /* accessibilità */
  white-space: nowrap;
}

/* PRIMARY — una sola per area visiva */
.btn-primary {
  background: var(--orange);
  color: var(--white);
}
.btn-primary:hover {
  background: var(--orange-dark);
  transform: translateY(-1px);
  box-shadow: var(--shadow-orange);
}

/* SECONDARY — azione complementare */
.btn-secondary {
  background: transparent;
  color: var(--gray-800);
  border: 1.5px solid var(--gray-300);
}
.btn-secondary:hover {
  border-color: var(--orange);
  color: var(--orange);
}

/* OUTLINE ORANGE — su sfondi chiari, azione terziaria */
.btn-outline-orange {
  background: transparent;
  color: var(--orange);
  border: 1.5px solid var(--orange);
}
.btn-outline-orange:hover {
  background: var(--orange);
  color: var(--white);
}

/* DARK SECTION variants */
.btn-primary-dark {
  background: var(--orange);
  color: var(--white);
  /* stesso comportamento hover di btn-primary */
}
.btn-secondary-dark {
  background: transparent;
  color: rgba(255,255,255,0.85);
  border: 1.5px solid rgba(255,255,255,0.35);
}
.btn-secondary-dark:hover {
  border-color: var(--orange);
  color: var(--orange);
}

/* SMALL — solo in contesti compatti */
.btn-sm {
  padding: 10px 20px;
  font-size: 14px;
  min-height: 40px;
}

/* LARGE — hero CTA principale */
.btn-lg {
  padding: 16px 36px;
  font-size: 16px;
  min-height: 56px;
}
```

**Regole d'uso:**
- Mai due `.btn-primary` visibili nella stessa area senza scroll
- Su landing page: solo una CTA primaria visibile above the fold
- Mobile: i bottoni possono diventare `width: 100%` se sono da soli o in colonna

---

## CARD

```css
/* CARD BASE */
.card {
  background: var(--white);
  border: 1.5px solid var(--gray-200);
  border-radius: var(--radius-lg);
  padding: 28px 24px;
  transition: all var(--transition-base);
}

/* CARD HOVER — per card cliccabili */
.card-interactive:hover {
  border-color: var(--orange);
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

/* CARD FEATURED — evidenziata */
.card-featured {
  border-color: var(--orange);
  background: var(--orange-light);
}

/* CARD DARK — su sezioni gray-900 */
.card-dark {
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: var(--radius-lg);
  padding: 24px 20px;
}

/* TESTI NELLE CARD — regole di leggibilità */
.card h3 {
  font-family: var(--font-heading);
  font-size: 20px;
  font-weight: 700;
  line-height: var(--lh-heading);
  color: var(--gray-900);
  margin-bottom: 8px;
}
.card p {
  font-size: 16px;        /* MAI sotto 16px */
  line-height: var(--lh-body);
  color: var(--gray-700); /* MAI --gray-500 */
  margin-bottom: 16px;
}
.card .card-meta {
  font-size: 14px;
  color: var(--gray-500);
  line-height: 1.4;
}
```

---

## NAVIGATION

```css
/* NAV PRINCIPALE */
.nav {
  position: sticky;
  top: 0;
  background: rgba(255,255,255,0.97);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--gray-200);
  z-index: 100;
}
.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 64px;
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 24px;
}
.nav-brand {
  font-family: var(--font-display);
  font-size: 24px;
  letter-spacing: 1px;
  color: var(--black);
  text-transform: uppercase;
}
.nav-links a {
  font-size: 14px;
  font-weight: 500;
  color: var(--gray-700);
  transition: color var(--transition-fast);
}
.nav-links a:hover { color: var(--orange); }

/* HAMBURGER — touch target corretto */
.nav-hamburger {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 10px;          /* touch target 44x44px */
  min-width: 44px;
  min-height: 44px;
  align-items: center;
  justify-content: center;
}
.nav-hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--gray-800);
  margin: 5px 0;
  transition: var(--transition-base);
}

@media (max-width: 768px) {
  .nav-links { display: none; }
  .nav-hamburger { display: flex; }
  .nav-links.open {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 64px; left: 0; right: 0;
    background: var(--white);
    padding: 16px 24px;
    border-bottom: 1px solid var(--gray-200);
    box-shadow: var(--shadow-md);
    z-index: 99;
  }
  .nav-links.open a { padding: 12px 0; font-size: 16px; } /* touch target */
}

/* LANDING HEADER — logo solo, no menu */
.landing-header {
  padding: 16px 24px;
  display: flex;
  justify-content: center;
  border-bottom: 1px solid var(--gray-200);
}
```

---

## FORM

```css
/* FORM CONTAINER */
.form-group {
  margin-bottom: 20px;
}
.form-label {
  display: block;
  font-size: 14px;
  font-weight: 500;
  color: var(--gray-800);
  margin-bottom: 6px;
}
.form-label .required {
  color: var(--orange);
  margin-left: 4px;
}

/* INPUT BASE */
.form-input,
.form-textarea,
.form-select {
  width: 100%;
  padding: 12px 16px;
  font-size: 16px;        /* Mai sotto 16px — evita zoom iOS */
  font-family: var(--font-body);
  color: var(--gray-900);
  background: var(--white);
  border: 1.5px solid var(--gray-300);
  border-radius: var(--radius-md);
  transition: border-color var(--transition-fast);
  min-height: 48px;       /* touch target */
  -webkit-appearance: none; /* rimuove stile iOS */
}
.form-input:focus,
.form-textarea:focus,
.form-select:focus {
  outline: none;
  border-color: var(--orange);
  box-shadow: 0 0 0 3px rgba(252,126,21,0.15);
}
.form-input::placeholder { color: var(--gray-500); }

/* TEXTAREA */
.form-textarea {
  min-height: 120px;
  resize: vertical;
  line-height: var(--lh-body);
}

/* SELECT */
.form-select {
  cursor: pointer;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%23616161' stroke-width='2' fill='none'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 16px center;
  padding-right: 40px;
}

/* CHECKBOX / RADIO */
.form-checkbox-label {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  font-size: 14px;
  color: var(--gray-700);
  cursor: pointer;
  line-height: 1.5;
}
.form-checkbox {
  width: 18px;
  height: 18px;
  min-width: 18px;
  margin-top: 2px;
  accent-color: var(--orange);
  cursor: pointer;
}

/* ERROR STATE */
.form-input.error { border-color: #E53E3E; }
.form-error-msg {
  font-size: 13px;
  color: #E53E3E;
  margin-top: 4px;
}

/* SUCCESS STATE */
.form-input.success { border-color: #38A169; }

/* FORM NOTE */
.form-note {
  font-size: 12px;
  color: var(--gray-500);
  margin-top: 8px;
  line-height: 1.4;
}
```

**Regola iOS critica:** `font-size: 16px` sugli input previene lo zoom automatico di Safari su iPhone. Non scendere mai sotto.

---

## SECTION HEADER

```css
/* STANDARD — usare per ogni sezione */
.section-tag {
  font-family: var(--font-body);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--orange);
  margin-bottom: 12px;
  display: block;
}
.section-title {
  font-family: var(--font-heading);
  font-size: var(--text-h2);
  font-weight: 700;
  line-height: var(--lh-heading);
  color: var(--gray-900);
  margin-bottom: 16px;
  max-width: var(--measure-wide);
}
.section-subtitle {
  font-size: var(--text-lead);
  color: var(--gray-600);
  line-height: var(--lh-relaxed);
  max-width: var(--measure-body);
  margin-bottom: 40px;
}

/* SU SFONDO DARK */
.section-dark .section-title { color: var(--white); }
.section-dark .section-subtitle { color: rgba(255,255,255,0.75); }
.section-dark .section-tag { color: var(--orange); }

@media (max-width: 768px) {
  .section-title { font-size: var(--text-h2-mobile); }
  .section-subtitle { font-size: 16px; margin-bottom: 28px; }
}
```

---

## BADGE E TAG

```css
/* TAG INLINE */
.tag {
  display: inline-block;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.5px;
  padding: 3px 10px;
  border-radius: 99px;
  text-transform: uppercase;
}
.tag-orange {
  background: var(--orange-light);
  color: var(--orange-dark);
}
.tag-dark {
  background: var(--gray-900);
  color: var(--white);
}
.tag-outline {
  background: transparent;
  border: 1px solid var(--gray-300);
  color: var(--gray-700);
}

/* BADGE URGENCY */
.badge-urgency {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: 13px;
  font-weight: 700;
  color: var(--orange-dark);
  background: var(--orange-light);
  border: 1px solid rgba(252,126,21,0.3);
  border-radius: var(--radius-md);
  padding: 6px 12px;
}
.badge-urgency::before {
  content: '⏰';
  font-size: 14px;
}

/* BADGE FREE */
.badge-free {
  display: inline-flex;
  align-items: center;
  font-size: 13px;
  font-weight: 700;
  color: #1D6A3D;
  background: #F0FFF4;
  border: 1px solid #9AE6B4;
  border-radius: var(--radius-md);
  padding: 6px 12px;
}
```

---

## ALERT / CALLOUT

```css
/* HIGHLIGHT BOX — per messaggi importanti */
.callout {
  border-left: 4px solid var(--orange);
  background: var(--orange-light);
  border-radius: 0 var(--radius-md) var(--radius-md) 0;
  padding: 20px 24px;
  margin: 24px 0;
}
.callout h3 {
  font-size: 18px;
  font-weight: 700;
  color: var(--gray-900);
  margin-bottom: 8px;
}
.callout p {
  font-size: 16px;
  color: var(--gray-700);
  line-height: var(--lh-body);
  margin: 0;
}

/* URGENCY BAR */
.urgency-bar {
  background: rgba(252,126,21,0.12);
  border: 1px solid rgba(252,126,21,0.3);
  border-radius: var(--radius-md);
  padding: 14px 20px;
  font-size: 14px;
  display: flex;
  align-items: center;
  gap: 8px;
  flex-wrap: wrap;
}
.urgency-bar strong { color: var(--orange-dark); }
.urgency-bar span { color: var(--gray-700); }

/* Su sfondo dark */
.urgency-bar-dark {
  background: rgba(252,126,21,0.15);
  border-color: rgba(252,126,21,0.3);
}
.urgency-bar-dark strong { color: var(--orange); }
.urgency-bar-dark span { color: rgba(255,255,255,0.75); }
```

---

## TESTIMONIAL / REVIEW

```css
/* REVIEW CARD */
.review-card {
  background: var(--white);
  border: 1px solid var(--gray-200);
  border-radius: var(--radius-lg);
  padding: 24px;
}
.review-stars {
  color: var(--orange);
  font-size: 15px;
  letter-spacing: 2px;
  margin-bottom: 12px;
}
.review-quote {
  font-size: 16px;         /* ERA 14px — correggere */
  font-style: italic;
  color: var(--gray-700);
  line-height: var(--lh-body);
  margin-bottom: 16px;
}
.review-author {
  display: flex;
  align-items: center;
  gap: 12px;
}
.review-avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--white);
  font-size: 15px;
  font-weight: 700;
  flex-shrink: 0;
}
.review-name {
  font-size: 14px;
  font-weight: 700;
  color: var(--gray-800);
}
.review-detail {
  font-size: 13px;         /* Accettabile per metadati */
  color: var(--gray-500);
  margin-top: 2px;
}

/* AGGREGATE RATING */
.aggregate-rating {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 32px;
}
.agg-score {
  font-family: var(--font-display);
  font-size: 56px;
  color: var(--orange);
  line-height: 1;
}
.agg-stars { color: var(--orange); font-size: 20px; letter-spacing: 3px; }
.agg-count { font-size: 14px; color: var(--gray-600); margin-top: 4px; }
.agg-source { font-size: 12px; color: var(--gray-500); margin-top: 2px; }
```

---

## STAT CARD

```css
.stat-card {
  text-align: center;
  padding: 28px 20px;
  border: 1px solid var(--gray-200);
  border-radius: var(--radius-lg);
}
.stat-num {
  font-family: var(--font-display);
  font-size: 52px;
  color: var(--orange);
  line-height: 1;
  margin-bottom: 10px;
}
.stat-label {
  font-size: 15px;
  color: var(--gray-600);
  line-height: 1.5;
  max-width: 200px;
  margin: 0 auto;
}
.stat-source {
  font-size: 12px;
  color: var(--gray-500);
  font-style: italic;
  margin-top: 20px;
}
```

---

## FOOTER

```css
.footer {
  background: var(--gray-900);
  color: rgba(255,255,255,0.8);
  padding: 64px 0 32px;
}
.footer-brand {
  font-family: var(--font-display);
  font-size: 22px;
  color: var(--white);
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 4px;
}
.footer-tagline {
  font-size: 13px;
  color: rgba(255,255,255,0.5);
  font-style: italic;
  margin-bottom: 20px;
}
.footer-col-title {
  font-size: 12px;
  font-weight: 700;
  color: var(--white);
  text-transform: uppercase;
  letter-spacing: 1.5px;
  margin-bottom: 16px;
}
.footer a {
  font-size: 14px;
  color: rgba(255,255,255,0.65);
  display: block;
  line-height: 2.2;
  transition: color var(--transition-fast);
}
.footer a:hover { color: var(--orange); }

/* NEWSLETTER FORM nel footer */
.footer-newsletter {
  display: flex;
  gap: 8px;
  margin-top: 12px;
}
.footer-newsletter input {
  flex: 1;
  padding: 10px 14px;
  font-size: 14px;
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: var(--radius-md);
  background: rgba(255,255,255,0.07);
  color: var(--white);
  font-family: var(--font-body);
  min-height: 44px;
}
.footer-newsletter input::placeholder { color: rgba(255,255,255,0.4); }
.footer-newsletter input:focus {
  outline: none;
  border-color: var(--orange);
}
.footer-newsletter button {
  padding: 10px 18px;
  background: var(--orange);
  color: var(--white);
  border: none;
  border-radius: var(--radius-md);
  font-size: 13px;
  font-weight: 700;
  cursor: pointer;
  font-family: var(--font-body);
  min-height: 44px;
  transition: background var(--transition-fast);
}
.footer-newsletter button:hover { background: var(--orange-dark); }

/* FOOTER MINIMAL — landing page */
.footer-minimal {
  padding: 24px;
  text-align: center;
  font-size: 13px;
  color: var(--gray-500);
  border-top: 1px solid var(--gray-200);
}
```

---

## FAQ ACCORDION

```css
.faq-list { max-width: var(--measure-wide); }
.faq-item { border-bottom: 1px solid var(--gray-200); }
.faq-question {
  font-family: var(--font-heading);
  font-size: 17px;
  font-weight: 700;
  color: var(--gray-900);
  padding: 20px 0 12px;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-height: 44px; /* touch target */
  user-select: none;
}
.faq-question::after {
  content: '+';
  font-size: 24px;
  color: var(--orange);
  font-weight: 300;
  flex-shrink: 0;
  margin-left: 16px;
  transition: transform var(--transition-fast);
}
.faq-item.open .faq-question::after { content: '−'; }
.faq-answer {
  font-size: 16px;
  color: var(--gray-700);
  line-height: var(--lh-relaxed);
  padding: 0 0 20px;
  max-width: var(--measure-body);
}
```

---

*Questo file è la libreria ufficiale dei componenti SONODIGITALE.*
*Non creare varianti non documentate. Se serve un nuovo componente, documentarlo qui.*
