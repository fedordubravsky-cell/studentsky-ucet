# Študentský účet - ČSOB Landing Page

## Projekt
- **Typ:** Statický HTML (stiahnutý z Liferay DXP)
- **Súbor:** `Účet na rozjezd v dospělosti _ ČSOB.html`
- **Framework:** Liferay DXP, PUI Design System, jQuery, YUI3
- **Aktualizácia:** 12.12.2024

---

## AKTUÁLNY STAV (po redesigne)

### Dizajn Systém
- **Hlavná šírka:** `max-width: 1200px` (konzistentne všade)
- **Farebná schéma:**
  - Globálny background: `#ebf6fd` (svetlo modrá)
  - Content boxy: `#ffffff` (biela)
  - Text: `#333` (dark), `#555` (medium), `#666` (light)
- **Dizajn filozofia:** Hranatý (border-radius: 0), čistý, moderný
- **Responzivita:** Mobile-first, flex-wrap na všetkých sekciách

---

## VYKONANÉ ZMENY (chronologicky)

### 1. Background farba - Jan (20) sekcia
- **Zmenené:** Background z `#f8f9fa` (šedá) → `#ebf6fd` (svetlo modrá)
- **Dôvod:** Unifikácia s ostatnými sekciami
- **Riadok:** 2513

### 2. RESPONZIVITA - Celý web (KRITICKÁ OPRAVA)
**Problém:** Na mobile bol obsah vľavo zarovnaný, vpravo modrý background (horizontal overflow)

**Opravy:**
- **Debetní karta sekcia:**
  - `min-width: 300px` → `min-width: 250px`
  - Pridaný `flex-wrap: wrap`
  - Upravený padding z `40px 40px 40px 0` → `40px`
  - **Riadky:** 2570-2580

- **Jan (20) sekcia:**
  - Pridaný `flex-wrap: wrap`
  - Pridaný `min-width: 280px` na text
  - Pridaný `max-width: 100%` na obrázok
  - **Riadky:** 2514, 2517, 2548

- **Recenzie:**
  - `min-width: 280px` → `min-width: 250px`
  - Pridaný `justify-content: center`
  - **Riadky:** 2893-2909

- **EEAT sekcia:**
  - `min-width: 280px` → `min-width: 250px`
  - **Riadok:** 3495

- **Globálne mobilné CSS:**
  - Pridané media queries pre tablet (768px) a mobile (480px)
  - Stacking sekcií, menší padding, responsive font-sizes
  - **Riadky:** 3736-3780

### 3. Debetní karta - Kompletný redesign
**Pôvodne:** Promobox s rounded corners, mix styling
**Teraz:** Konzistentný s Jan (20)

**Zmeny:**
- **Wrapper:** Pridaný svetlo modrý background `#ebf6fd` s `padding: 60px 20px`
- **Box:** Biely, hranatý, `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`
- **Layout:** Obrázok vľavo, text vpravo, `flex-wrap: wrap`
- **Obrázok:** `max-width: 450px`, responsive
- **Bullet points spacing:** `line-height: 1.8` → `1.4`, pridaný `margin-bottom: 8px`
- **Riadky:** 2567-2602

### 4. Nulové poplatky - Zjednodušenie
**Pôvodne:** Šedý box s tabuľkou
**Teraz:** Čistý layout na svetlo modrom pozadí

**Zmeny:**
- **Odstránené:** Šedý wrapper `#f8f9fa`
- **Odstránené:** Biely vnútorný box okolo všetkého
- **Wrapper:** Len svetlo modrý background `#ebf6fd`
- **H2:** Zarovnaný vľavo (odstránené `text-align: center`)
- **Tabuľka:** Plná šírka kontajnera (1200px), biely box len okolo tabuľky
- **Info box:** Žltý disclaimer štýl `#fff9e6`, šírka 800px (zhodný s tabuľkou)
- **Riadky:** 2607-2649

### 5. Jan (20) - Redesign na Promobox pattern
**Pôvodne:** Biely box s flex layoutom
**Teraz:** Promobox bez bieleho boxu

**Zmeny:**
- **Odstránený:** Biely wrapper box
- **Použité triedy:** `html-b-section`, `html-c-promobox`, `html-has-mobile-image`
- **H2 tag:** `<h3>` → `<h2 class="html-b-promobox-title">`
- **Emoji:** Pridané 💳 a 💰 pre visual enhancement
- **Bullet points:** Zmenené na paragrafy s emoji
- **Obrázok:** Zmenený na `jan_ukazka.png` (lokálny súbor)
- **Riadky:** 2512-2552

### 6. Recenzie - Širší layout
- **Max-width:** `1000px` → `1200px`
- **Dôvod:** Zhodný s ostatnými sekciami
- **Riadok:** 2891

### 7. EEAT sekcia - Vertikálny layout
**Pôvodne:** 2 boxy vedľa seba (grid 1fr 1fr)
**Teraz:** Boxy pod sebou

**Zmeny:**
- **Grid:** `grid-template-columns: 1fr 1fr` → `1fr`
- **Max-width:** `1000px` → `1200px`
- **Verification box:** Background `#f8f9fa` → `#ffffff`
- **Styling:** Border `2px solid #d8d8d8`, box-shadow, border-left 4px
- **Odstránený:** Disclaimer box (ℹ️ Důležité upozornění)
- **Riadky:** 3455-3882

### 8. Regulačná sekcia - Konzistencia
**Zmeny:**
- **Max-width:** `900px` → `1200px`
- **Background:** Všetky 3 boxy `#f8f9fa` → `#ffffff`
- **Border:** Pridaný `2px solid #d8d8d8` + farebný left border
- **Box-shadow:** `0 2px 4px rgba(0, 0, 0, 0.05)`
- **Border-left thickness:** Zostalo 3px (vs 4px v EEAT - minor inconsistency)
- **Riadky:** 3895-3948

---

## AUDIT VÝSLEDKY

### Vykonaný: 12.12.2024
**Scope:** Kompletná stránka - styling, HTML štruktúra, konzistencia

### Nájdené nekonzistencie (18 celkom):

#### 🔴 KRITICKÉ (8):
1. **H2 font-size:** Len 1/13 má explicitný size
2. **H2 margin:** Variuje 20px - 60px
3. **Paragraph font-size:** 0.85rem, 0.95rem, 1rem
4. **Paragraph line-height:** 1.4, 1.5, 1.6
5. **Box padding:** 20px, 28px 32px, 32px, 40px
6. **Box-shadow:** 3 rôzne varianty
7. **Border-radius:** 0 vs 12px (recenzie)
8. **Border-left:** 3px vs 4px

#### 🟡 STREDNÉ (3):
9. Color schéma (3 odtiene šedej)
10. CSS triedy vs inline mix
11. Button systémy (4 rôzne)

#### 🟢 NÍZKE (2):
12. Emoji použitie
13. Gap spacing variácie

### Odporúčania (zatiaľ nerealizované):
- Štandardizovať H2 tagy
- Unifikovať box-shadow na `0 2px 8px rgba(0,0,0,0.08)`
- Border-radius všade na 0
- Vytvoriť CSS utility triedy

---

## FAQ SEKCIA
- **Umiestnenie:** Nad "Za tímto produktem stojí"
- **Obsah:** 14 otázok s odpoveďami (accordion)
- **Funkcia:** `html-c-accordion` s automatickou inicializáciou
- **ID:** `#faq` pre navigáciu
- **Riadky:** 3218-3399

---

## HERO SEKCIA
- **Background:** `lp-banner-ucet-na-rozjezd-m-760x170.jpg`
- **Styling:** `background-size: cover; background-position: center`
- **Riadok:** 2339

---

## TECHNICKÉ DETAILY

### Naming Conventions
- **BEM-like** s PUI/HTML prefixmi
- Príklad: `html-c-promobox`, `html-is-button`, `eeat-expert-box`

### Styling Approach
- **Mix:** 60% inline CSS, 20% CSS triedy, 20% mix
- **Dôvod:** Rýchla implementácia + compatibility s Liferay
- **CSS sekcie:** EEAT má vlastný `<style>` blok (riadky 3447-3781)

### Responzivita
- **Breakpoints:** 768px (tablet), 480px (mobile)
- **Prístup:** Mobile-first, flex-wrap
- **Testing:** Kontrolované na 320px, 375px, 768px, 1200px+

### Box Shadow Varianty (nekonzistentné)
```css
/* Variant 1 - najpoužívanejší */
box-shadow: 0 2px 8px rgba(0,0,0,0.08);

/* Variant 2 - recenzie */
box-shadow: 0 4px 12px rgba(0,0,0,0.08);

/* Variant 3 - EEAT, regulácia */
box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
```

### Border System
- **Hranatý dizajn:** `border-radius: 0` (všade okrem recenzií)
- **Výnimka:** Recenzie majú `border-radius: 12px` ⚠️
- **Farebné okraje:**
  - Modrý `#0a77a9` (ČNB, EEAT expert)
  - Zelený `#28a745` (GSFT, EEAT verification)
  - Fialový `#6f42c1` (PSD2)
  - Žltý `#ffc107` (disclaimery)

---

## OBRÁZKY

### Hlavné obrázky:
- **Jan (20):** `jan_ukazka.png` (lokálny)
- **Debetní karta:** `promobox-detska-karta-555x380.png`
- **Hero banner:** `lp-banner-ucet-na-rozjezd-m-760x170.jpg`

### Ikony:
- `mladi.svg` (Jan sekcia)
- `ico-smartbanking-22x22.svg`
- `0kc-icon-60x60.svg`
- ČNB, GSFT, PSD2 logos (external URLs)

---

## ZNÁME PROBLÉMY (z auditu)

### ⚠️ Treba opraviť:
1. **H2 styling nekonzistencia** - väčšina nemá explicitné štýly
2. **Recenzie border-radius** - jediná sekcia so zaoblenými rohmi
3. **Border-left thickness** - 3px vs 4px v rôznych sekciách
4. **Box padding** - 4 rôzne hodnoty naprieč stránkou

### ✅ Vyriešené:
1. ~~Responzivita - horizontal overflow~~ ✅
2. ~~Background color nekonzistencia~~ ✅
3. ~~EEAT boxy šedé pozadie~~ ✅
4. ~~Regulačné boxy šedé pozadie~~ ✅
5. ~~Max-width nekonzistencia~~ ✅ (teraz všade 1200px)

---

## NEXT STEPS (odporúčané)

1. **H2 standardizácia:**
   ```css
   font-size: 1.75rem;
   font-weight: 600;
   color: #333;
   margin: 0 0 24px 0;
   ```

2. **Recenzie border-radius:** `12px` → `0`

3. **Box-shadow unifikácia:** Všade `0 2px 8px rgba(0,0,0,0.08)`

4. **Border-left:** Všade `4px`

5. **CSS utility classes:** Vytvoriť pre opakujúce sa patterny

---

## CHANGELOG

### 2024-12-12 - Major Redesign
- ✅ Opravená responzivita (mobile overflow)
- ✅ Unifikovaný background na `#ebf6fd`
- ✅ Všetky content boxy biele
- ✅ Max-width 1200px všade
- ✅ EEAT vertikálny layout
- ✅ Regulačné boxy styling
- ✅ Jan (20) redesign na promobox pattern
- ✅ Debetní karta redesign
- ✅ Nulové poplatky simplifikácia
- ✅ Audit kompletnej stránky

### Pôvodné zmeny (pred 2024-12-12)
- FAQ sekcia
- Hero background image
- Trust badges (odstránené)

---

## ŠTATISTIKY

- **Celkový počet riadkov:** 5843
- **Hlavné sekcie:** 13
- **H2 nadpisy:** 13
- **Obrazy:** ~45 súborov
- **CSS media queries:** 3 (desktop, tablet, mobile)
- **Veľkosť súboru:** ~850 KB
