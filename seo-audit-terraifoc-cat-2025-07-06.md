# Terra i Foc — Auditoria SEO / GEO / AEO

**Data:** 6 de juliol de 2025  
**Pàgines revisades:** 6 (Homepage CA, Homepage EN, Glossari CA, Glossari EN, Crèdits CA, Crèdits EN)  
**Tipus:** Auditoria completa

---

## Puntuacions

| Dimensió | Puntuació | Estat |
|---|---|---|
| SEO | 3/10 | Needs Work |
| GEO | 2/10 | Needs Work |
| AEO | 4/10 | Needs Work |
| **Combinat** | **9/30** | |

---

## Resum executiu

Terra i Foc té contingut excepcionalment ric — milers de paraules d'història familiar de primera mà que abasten cinc generacions, processos tècnics ceràmics detallats i un glossari complet de més de 60 termes. Això és exactament el tipus de contingut autèntic i autoritari que els cercadors i els sistemes d'IA recompensen.

**Però el lloc és completament INVISIBLE** a tots els cercadors i motors d'IA a causa de dos problemes crítics:

1. **Meta robots `noindex, nofollow`** a totes les pàgines de la versió desplegada
2. **`robots.txt` amb `Disallow: /`** a la versió desplegada

**Corregir aquests dos problemes sols transformaria el lloc d'invisible a altament competitiu** en els resultats de cerca per a ceràmica artesanal a la regió del Penedès.

---

## Top 3 prioritats

1. **Eliminar `<meta name=robots content="noindex,nofollow...">` de totes les pàgines** — El lloc és completament invisible als cercadors. Això és el bloqueig número 1.

2. **Corregir `robots.txt`** — La versió desplegada té `Disallow: /` per a tots els user agents (inclòs Googlebot). Cal canviar-lo a `Allow: /`.

3. **Afegir FAQ schema al glossari** — El glossari té 60+ definicions que podrien ser featured snippets, però no tenen marcatge structured data.

---

## Força més gran

Contingut excepcionalment ric — milers de paraules d'història familiar de primera mà, tècniques ceràmiques i un glossari exhaustiu. Això és or pur per a SEO i GEO si es deixa indexar.

---

## Pàgines audities

| URL | Tipus | Notes |
|---|---|---|
| https://terraifoc.cat/ | Homepage (CA) | tag noindex, password gate, schema LocalBusiness |
| https://terraifoc.cat/en/ | Homepage (EN) | tag noindex, password gate, schema LocalBusiness |
| https://terraifoc.cat/glossari/ | Glossari (CA) | 60+ termes ceràmics, tag noindex |
| https://terraifoc.cat/en/glossari/ | Glossari (EN) | 60+ termes ceràmics, tag noindex |
| https://terraifoc.cat/credits/ | Crèdits (CA) | Atribucions, tag noindex |
| https://terraifoc.cat/en/credits/ | Crèdits (EN) | Atribucions, tag noindex |

---

## Anàlisi SEO — 3/10

### Tècnic On-Page

| Senyal | Troballa | Estat |
|---|---|---|
| Title tag | Present a totes les pàgines. Format: "Terra i Foc · Obrador de ceràmica artesanal". Longitud òptima. | ✅ Bo |
| Meta description | Present. Usa i18n hero_tagline. Genèrica a sub-pàgines ("Obrador de ceràmica artesanal"). | ⚠️ Atenció |
| Jerarquia de capçaleres | H1 a l'homepage via sr-only. H2/H3 utilitzats arreu amb estructures rellevants paraules clau. | ✅ Bo |
| Estructura URL | Neta i llegible: /glossari/, /credits/, /en/. Sense paràmetres. | ✅ Bo |
| Tag canonical | Present i auto-referenciat a totes les pàgines. | ✅ Bo |
| Robots meta | **CRÍTIC: noindex, nofollow, noarchive, nosnippet, noimageindex a TOTES les pàgines.** | ❌ Falta |
| Viewport meta | Present (width=device-width, initial-scale=1.0). | ✅ Bo |
| Alt text d'imatges | Totes les imatges tenen alt text descriptiu. Imatges de galeria amb llegenda descriptiva. | ✅ Bo |
| Enllaços interns | Navegació per ancoratge entre seccions. Canviador d'idioma. | ✅ Bo |
| Open Graph / Twitter | og:title, og:description, og:url, og:type, og:locale, og:site_name presents. og:image és SVG (no ideal). | ⚠️ Atenció |
| robots.txt | **CRÍTIC: La versió desplegada té Disallow: / per a tots els agents. Bloqueja tots els crawlers.** | ❌ Falta |
| Sitemap | Present i ben estructurat amb enllaços hreflang per a CA i EN. | ✅ Bo |
| Schema markup | LocalBusiness JSON-LD a totes les pàgines. Ric: name, description, address, email, foundingDate, knowsLanguage. | ✅ Bo |
| HTTPS | Lloc servit sobre HTTPS. | ✅ Bo |
| Fil d'Ariadna | No present. No hi ha schema BreadcrumbList. | ❌ Falta |

### Qualitat del contingut

| Senyal | Troballa | Estat |
|---|---|---|
| Nombre de paraules | Milers de paraules arreu de les seccions de l'homepage. Contingut històric i tècnic extremadament ric. | ✅ Bo |
| Senyals de paraules clau | Ceràmica artesanal, obrador, Penedès, Joan Martínez Peidro — ben coberts. | ✅ Bo |
| Senyals de frescor | No hi ha dates de publicació o actualització visibles al contingut. | ⚠️ Atenció |
| Llegibilitat | Ben estructurat amb subtítols, paràgrafs, seccions curtes. Tècnic però accessible. | ✅ Bo |

### Dades estructurades

| Senyal | Troballa | Estat |
|---|---|---|
| Schema LocalBusiness | Present a totes les pàgines. Inclou name, description, address, email, foundingDate, knowsLanguage. | ✅ Bo |
| Schema Organization | No present separadament. Podria fusionar-se amb LocalBusiness. | ⚠️ Atenció |
| Schema FAQ | No present. El glossari té 60+ definicions que podrien usar FAQ o definedTermSet. | ❌ Falta |
| Schema Article | No present. Les seccions de contingut ric es beneficiarien de marcatge Article. | ❌ Falta |
| BreadcrumbList | No present. | ❌ Falta |

---

## Anàlisi GEO — 2/10

### Avaluació E-E-A-T

| Senyal | Troballa | Estat |
|---|---|---|
| Informació de l'autor | Isabel Serres acreditada pels textos. Joan Mz Serres per l'adaptació web. Pàgina de crèdits present. | ✅ Bo |
| Pàgina About | Biografia extensa de Joan Martínez Peidro amb currículum complet (1945-2010). | ✅ Bo |
| Informació de contacte | Email (hola@terraifoc.cat), adreça (C. Verge de Montserrat 17, El Pago). Sense telèfon. | ⚠️ Atenció |
| Senyals de confiança | Història familiar de 5+ generacions. Medalles, exposicions, col·laboracions documentades. | ✅ Bo |
| Schema Organization | Schema LocalBusiness present però sense telèfon ni xarxes socials. | ⚠️ Atenció |

### Contingut per a síntesi d'IA

| Senyal | Troballa | Estat |
|---|---|---|
| Densitat factual | Excepcional: dates específiques, noms, llocs, processos tècnics, temperatures, materials. | ✅ Bo |
| Reivindicacions clares | Proposta de valor central clarament establerta a la secció hero i descripció. | ✅ Bo |
| Cites de fonts | Referències als Butlletins de Ceràmica, llibres específics, esdeveniments històrics. | ✅ Bo |
| Exhaustivitat | Extremadament exhaustiva. Cobreix història, tècniques, materials, eines, vida diària, treballadors. | ✅ Bo |
| Claredat d'entitat | Terra i Foc, Joan Martínez Peidro, El Pago, Subirats — clarament nomenats arreu. | ✅ Bo |
| Senyals d'originalitat | Història familiar de primera mà, fotografies originals, currículum únic. | ✅ Bo |

### GEO tècnic

| Senyal | Troballa | Estat |
|---|---|---|
| Profunditat de dades estructurades | Només LocalBusiness. Sense Author, Dataset, ni SpeakableSpecification. | ⚠️ Atenció |
| HTTPS | Lloc segur. Senyal de confiança per a motors d'IA. | ✅ Bo |
| Rastreabilitat | **CRÍTIC: noindex + robots.txt Disallow bloca TOTS els crawlers inclòs IA.** | ❌ Falta |
| Perfils socials | Enllaç Instagram present a config però no a schema sameAs. | ⚠️ Atenció |

---

## Anàlisi AEO — 4/10

### Elegibilitat per a featured snippets

| Senyal | Troballa | Estat |
|---|---|---|
| Paràgrafs de resposta directa | Algunes seccions tenen paràgrafs definicionals clars (ex: "El càntir és un exemple..."). | ⚠️ Atenció |
| Patrons de definició | El glossari defineix termes clarament ("X és / Y que..."). Perfecte per a snippets. | ✅ Bo |
| Contingut de llistes | El currículum és una línia temporal numerada. Podria optimitzar-se per a snippets de llista. | ⚠️ Atenció |
| Contingut de taules | Taula de dades amb columnes Any / Fita / Forn / Producció. | ✅ Bo |

### Formats de resposta estructurats

| Senyal | Troballa | Estat |
|---|---|---|
| Schema FAQ | No present. 60+ termes del glossari podrien ser FAQ schema. | ❌ Falta |
| Schema HowTo | No present. Les descripcions del procés del taller podrien usar HowTo. | ❌ Falta |
| Capçaleres amb preguntes | No hi ha capçaleres formulades com a preguntes. Totes les capçaleres són declaratives. | ❌ Falta |
| Schema Speakable | No present. | ❌ Falta |

### Preparació per a cerca per veu

| Senyal | Troballa | Estat |
|---|---|---|
| Llenguatge conversacional | El contingut és narratiu i descriptiu, no conversacional. | ⚠️ Atenció |
| Cobertura de cua llarga | No hi ha cobertura específica de preguntes qui/què/quan/on/per què/com. | ❌ Falta |
| Senyals locals | Adreça present. Dades NAP disponibles però no en format estructurat per a veu. | ⚠️ Atenció |

---

## Matriu de recomanacions prioritàries

| Prioritat | Problema | Dimensió | Esforç | Impacte |
|---|---|---|---|---|
| 🔴 Crític | Eliminar `<meta name=robots content="noindex,nofollow...">` de totes les pàgines | SEO / GEO / AEO | Baix | Crític — el lloc és invisible sense això |
| 🔴 Crític | Corregir robots.txt: canviar Disallow: / a Allow: / | SEO / GEO / AEO | Baix | Crític — bloca tots els crawlers |
| 🔴 Crític | Eliminar password gate per a crawlers (o fer-lo opcional) | SEO / GEO | Mig | Alt — els crawlers poden no superar el gate |
| 🟠 Alt | Afegir FAQ schema a la pàgina del glossari (60+ termes) | AEO / GEO | Mig | Alt — elegibilitat per a featured snippets |
| 🟠 Alt | Afegir telèfon al schema LocalBusiness | GEO | Baix | Mig — dades d'entitat completes |
| 🟠 Alt | Afegir sameAs perfils socials al schema (Instagram) | GEO | Baix | Mig — enforteix el graf d'entitats |
| 🟡 Mig | Usar una foto real per a og:image en lloc del logo SVG | SEO | Baix | Mig — millor compartició social |
| 🟡 Mig | Afegir schema Article a les seccions de contingut ric | SEO / GEO | Mig | Mig — dades estructurades més profundes |
| 🟡 Mig | Afegir schema BreadcrumbList | SEO | Baix | Baig — nice to have |
| 🟡 Mig | Afegir dates de publicació al contingut | SEO / GEO | Baix | Baig — senyals de frescor |
| 🟢 Quick Win | Crear humans.txt amb crèdits | SEO | Baix | Fet — fitxer creat |
| 🟢 Quick Win | Afegir capçaleres formulades com a preguntes | AEO | Baix | Mig — preparat per a cerca per veu |

---

## Què funciona bé

| # | Força |
|---|---|
| 1 | Contingut original i extremadament ric — milers de paraules d'història familiar de primera mà i coneixements tècnics ceràmics que abasten 5+ generacions |
| 2 | Implementació bilingüe (CA/EN) completa amb tags hreflang adequats i directoris de contingut separats |
| 3 | Schema LocalBusiness JSON-LD present a totes les pàgines amb dades de negoci precises |
| 4 | HTML ben estructurat amb jerarquia de capçaleres adequada, elements semàntics i funcions d'accessibilitat (skip links, aria labels) |
| 5 | Alt text d'imatges descriptiu arreu — cada foto té llegenda adequada |
| 6 | Glossari exhaustiu amb 60+ termes tècnics ceràmics — potencial per a featured snippets si es marca adequadament |
| 7 | Estructura d'URL neta i llegible (/glossari/, /credits/, /en/) |
| 8 | Sitemap funcional amb referències hreflang creuades entre versions CA i EN |
| 9 | Referències històriques reals — Butlletins de Ceràmica, Escola Massana, exposicions i dates específiques |
| 10 | Formulari de contacte amb Formspree, anti-spam honeypot i suport i18n |

---

## Nota important sobre la versió desplegada

El codi font local **ja té la configuració correcta**:
- `layouts/robots.txt`: `Allow: /` ✅
- `baseof.html`: Sense tag `noindex` ✅

**El problema és que la versió desplegada a GitHub Pages és diferent del codi local.** Cal fer push del codi local per redeployar i corregir els bloqueigs.

---

*Informe generat per Claude Skill SEO/GEO/AEO by Alex Labat*
