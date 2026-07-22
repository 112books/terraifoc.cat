---
title: "Accessibilitat"
description: "Declaració d'accessibilitat del lloc web Terra i Foc"
---

## Compromís amb l'accessibilitat

Terra i Foc es compromet a fer el seu lloc web accessible a totes les persones, independentment de les seves capacitats o limitacions, d'acord amb la **Llei 9/2017** d'accessibilitat de Catalunya i el **Reial Decret 1112/2018** sobre accessibilitat dels llocs web i aplicacions per a dispositius mòbils del sector públic.

## Nivell de conformitat

Aquest lloc web ha estat dissenyat seguint els estàndards **WCAG 2.1** (Web Content Accessibility Guidelines) del W3C, amb l'objectiu d'assolir el **nivell AA** de conformitat.

## Mesures implementades

### Navegació

- **Enllaç de skip:** "Salta al contingut" per saltar la navegació i anar directament al contingut principal.
- **Navegació per teclat:** totes les funcions són accessibles mitjançant el teclat (Tab, Enter, Escape).
- **Focus visible:** el focus es mostra clarament amb un contorn vermell al voltant dels elements actius.

### Contingut

- **Estructura semàntica:** ús correcte d'etiquetes HTML (`header`, `nav`, `main`, `footer`, `section`).
- **Capçaleres lògiques:** jerarquia coherent (H1, H2, H3) per facilitar la navegació amb lectors de pantalla.
- **Text alternatiu:** totes les imatges tenen `alt` descriptiu.
- **Llengua declarada:** l'atribut `lang` identifica l'idioma de la pàgina.

### Dissenny i contrast

- **Tipus de lletra:** Jost, amb cos base de 17px per facilitar la lectura.
- **Contrast de color:** paleta de colors dissenyada per complir els ratis de contrast WCAG AA (mínim 4.5:1 per text normal).
- **Responsive:** el lloc s'adapta a tots els dispositius (mòbil, tauleta, escriptori).

### Formulari

- **Etiquetes associades:** cada camp té la seva etiqueta (`label`) enllaçada mitjançant `for`.
- **Validació accessible:** els errors i estats es comunican mitjançant `aria-live` per als lectors de pantalla.
- **Navegació per teclat:** ordre lògic de tabulació.

### Multimèdia

- **Vídeos incrustats:** els vídeos de YouTube del taller inclouen subtítols quan estan disponibles.
- **Controls accessibles:** els botons de la galeria/lightbox són operables amb teclat i tenen `aria-label` descriptius.

## Animacions

El lloc respecta la preferència `prefers-reduced-motion` del sistema operatiu de l'usuari. Si l'usuari té activada la reducció de moviment, les animacions de scroll-reveal es desactiven.

## Àrees de millora

Terra i Foc treballa continuament per millorar l'accessibilitat del seu lloc. Algunes àrees en procés de revisió:

- Auditoria completa de contrast en components secundaris.
- Ampliació de subtítols i transcripcions als vídeos.
- Revisió de l'ordre de lectura amb lectors de pantalla (NVDA, VoiceOver).

## Comunicar problemes d'accessibilitat

Si trobeu alguna barrera d'accessibilitat o teniu suggeriments, podeu contactar-nos a:

**Correu electrònic:** [hola@terraifoc.cat](mailto:hola@terraifoc.cat)

Descriuiu el problema amb la major detall possible (pàgina, element, tecnologia que feu servir) i us respondrem el més aviat possible.

## Legislació aplicable

- **Llei 9/2017** d'accessibilitat de Catalunya.
- **Reial Decret 1112/2018** sobre accessibilitat dels llocs web.
- **WCAG 2.1** del W3C (nivell AA).