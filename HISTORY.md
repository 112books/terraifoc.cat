# Històric de treball — Terra i Foc

Registre cronològic de canvis, decisions i tasques realitzades.

---

## 2026-07-22

### Navegació mòbil amb icones de línia
- **Arxius:** `layouts/partials/header.html`, `assets/css/main.css`
- **Canvi:** Cada secció de la nav té un icona SVG de línia (persona, gent, edifici, llibre, estrella, imatge, sobre).
- A mòbil (< 768px): barra fixa a baix, scrollable horitzontal, sense labels. Icona d'idioma (CA/EN) al final de la barra amb bordet.
- A escriptori: icones + text en fila, botó idioma amb fons i bordet.

### Secció activa amb color foc
- **Arxius:** `layouts/_default/baseof.html`, `assets/css/main.css`
- **JS:** IntersectionObserver detecta quina secció és visible i afegeix `nav-icon-active` a l'enllaç corresponent.
- **CSS:** Icona activa canvia a `var(--foc)` ( vermell ).

### Icona Taller canviada
- **Arxiu:** `layouts/partials/header.html`
- **Canvi:** Icona de quadrícula → edifici (`<path d="M3 21h18..."/>`).

### Correcció analytics GoatCounter
- **Arxiu:** `.github/workflows/fetch-analytics.yml`
- **Problema:** `END=$(date +%Y-%m-%d)` passava la data sense hora. GoatCounter interpretava `00:00:00` i la query SQL no retornava hits (issue [#836](https://github.com/arp242/goatcounter/issues/836)).
- **Solució:** `END=$(date +%Y-%m-%dT23:59:59Z)` — inclou tot el dia.
- **Nota:** El workflow encara no ha executat amb la correcció (és horari, cada hora a :00).

### Botó idioma visible a les dues versions
- **Arxius:** `layouts/partials/header.html`, `assets/css/main.css`
- **Problema:** `.header-lang` estava dins `nav-links` i no es veia a cap versió.
- **Solució:** `.header-lang` mogut fora de `nav-links`, al header directament.
- Desktop: al final de la fila de nav, amb `margin-left: auto`.
- Mòbil: fixa a dalt a la dreta (`position: fixed`, `z-index: 101`).

### Foto Joan+Lola full-width a mòbil
- **Arxius:** `assets/css/main.css`
- `.col-gallery` a mòbil canviat a `grid-template-columns: 1fr` (abans forçava 2 columnes).
- Figura i imatge a `width: 100%`, `height: auto`.

### Hamburguesa mòbil + overlay de navegació
- **Arxius:** `layouts/partials/header.html`, `assets/css/main.css`, `layouts/_default/baseof.html`
- **Botó hamburger:** Visible només a mòbil (`display: none` a escriptori).
- **Overlay:** Pantalla completa amb llistat de seccions en text gran + botó idioma.
- **JS:** Toggle `is-open` amb tancament per clic a enllaç, Escape, i `aria-expanded`.
- **Icones bottom bar:** Sense text (`nav-icon-label: display: none`), `flex: 1 1 0` per ajustar-se.

### Neteja CSS
- Eliminat `.header-lang .lang-link` duplicat (línia 269-283).

### Ajustos d'espaiat i mida
- **Desktop:** `.nav-links` amb `margin-left: 24px` per separar del logo.
- **Mòbil:** icones reduïdes a 20px (18px a ≤480px). Padding barra inferior ajustat.
- **Hamburguesa:** `width: 36px`, `height: 36px`, `flex-direction: column` explícit al mòbil.

### Contingut correcció punts 1–6 (CA+EN)
- **Arxius:** `i18n/ca.yaml`, `i18n/en.yaml`, `layouts/index.html`
- Punt 1: 3× `<figcaption>Retrat de Joan</figcaption>` eliminat de la mini-galeria.
- Punt 2: Figcaption família canviat a "Família Martínez i Serres actualment".
- Punt 3: `familia_pare_visio_text` prefixat amb "El seu pare..." (CA) / "His father..." (EN).
- Punt 4: "La feina dels seus pares" — títol ja correcte, sense canvi.
- Punt 5: `familia_pecoes_title` → "Peces que es feien a l'obrador familiar" (CA) / "Pieces made at the family workshop" (EN).
- Totes les traduccions EN aplicades.

### Commit
```
20c4f5a Navegació mòbil amb icones de línia, botó idioma diferenciat, correcció analytics
```

---

## 2026-07-21

### Glossari i Crèdits com a pàgines interiors
- **Arxius:** `layouts/glossari/single.html`, `layouts/_default/single.html`, `content/glossari/index.md`, `content/en/glossari/index.md`, `content/credits/index.md`, `content/en/credits/index.md`
- Glossari mogut a `/glossari/` amb layout dedicat que renderitza `data/glossary.yaml`.
- Crèdits mogut a `/credits/` amb contingut als arxius markdown.
- Nav actualitzada: enllaços apunten a pàgines interiors.
- Clau `nav_credits` afegida a i18n (CA: "Crèdits", EN: "Credits").
- Layout `single.html` creat per a pàgines interiors.

### Contingut real del PDF del Joan
- **Arxiu:** `i18n/ca.yaml` i `i18n/en.yaml`
- Secció Joan: títol "En Joan i el seu currículum", foto (sense figcaption), timeline completa (1945–2010).
- Secció Família: 3 blocs dedicats amb fotos (visió del pare, feina dels pares, malaltia/venda).
- Secció Taller: 11 blocs verticals (cadascun: h3 + div.content-text + gallery-grid).
- Col·laboradors: `<ul>` amb enllaços interns a `#collab-benet`, `#collab-manosa`, `#collab-maties`.
- Representants: `<ul>` amb noms + dates.
- `safeHTML` habilitat per a textos de col·laboracions amb `<a>` i `<ul>`.

### Password gate eliminat
- **Arxiu:** `layouts/_default/baseof.html`
- Script inline de contrasenya `LinuxBCN2026` (sessionStorage) eliminat.

### Seguretat i SEO
- `robots.txt` bloqueja tots els bots (crawlers + IA: GPTBot, ClaudeBot, CCBot, etc.).
- `<meta name="robots" content="noindex, nofollow, noarchive, nosnippet, noimageindex">` afegit.
- CSP actualitzada amb `gc.zgo.at` i `terraifoc-cat.goatcounter.com`.

### CSS
- `section-reveal` sempre visible (`opacity: 1`), IntersectionObserver eliminat.
- `text-transform: uppercase` eliminat de tots els títols.
- `white-space: pre-line` a `.content-text` per a salts de paràgraf via `\n\n`.

---

## 2026-07-20

### Organització d'imatges
- Fotos classificades: `guerrers/`, `pecoes/`, `pecoes-obrador/`, `taller/`, `historiques/`, `curriculum/`, `colaboradors/`.
- Logo vectoritzat.

### Glossari
- **Arxiu:** `data/glossary.yaml`
- 60+ termes CA+EN (gerrers, ceràmica, ofici, etc.).

### dades_taller
- **Arxius:** `content/_index.md`, `content/en/_index.md`
- 10 entrades YAML amb strings doblement citats i `\n`.

---

## Decisions de disseny

| Element | Decisió | Raó |
|---|---|---|
| Colors | `#361712` (terra) + `#c81111` (foc) | Identitat visual del taller |
| Font | Jost (Google Fonts) | Moderna, neta, amb personalitat |
| Password gate | Eliminat | No era seguretat real, molestava |
| robots.txt | Bloqueja tot | Contingut privat, no SEO |
| Galeria | 3 columnes, gap 2px, hover zoom | Estil net, fotos quadrades |
| Footer | "Fundat el 1969 per Joan Martínez Peidro" | Context històric |
