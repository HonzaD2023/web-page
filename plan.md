# SKILLSHOT — Kompletní plán webu
*Verze 1.2 · 2026-05-05*

---

## 1. Identita a positioning
- Název: Skillshot
- Slogan: **Čti lidi. Ovládni místnost.**
- Cílová skupina: HR manažeři a L&D korporátních firem
- Tón: Odvážný, konkrétní, profesionální — výsledky, ne procesy
- Jazyk: Čeština, vykání jednotné (Naučíte se, Získáte, Odcházíte)

---

## 2. Kurzy
1. **Řeč těla: Čti lidi jako knihu** — neverbální komunikace, 2 dny, max. 12 osob
2. **Psychologie přesvědčování: Techniky vlivu** — psychologie vlivu, 2 dny, max. 12 osob

---

## 3. Vizuální identita
Barvy: #0a0a0a (primární), #e63946 (červená/kurz 1), #f4a261 (oranžová/kurz 2), #f5f5f5 (pozadí), #555 (subtext WCAG AA)
Typografie: system-ui, Segoe UI — žádné Google Fonts
Ikony: inline SVG přímo v HTML (ne soubory, ne CDN)
Fotografie ze Unsplash (s overlayem rgba(0,0,0,0.70)):
- index hero: photo-1552664730-d307ca884978 (skupinový workshop)
- rec-tela hero: photo-1573497019940-1c28c88b4f3e (gesta/tvář při jednání)
- psychologie hero: photo-1552664730-d307ca884978 (workshop)

---

## 4. Struktura a textace

### index.html — Hlavní strana

**NAVIGACE** (stejná na všech stránkách)
Logo: Skill[shot] — "shot" červeně, odkaz na index.html
Odkazy: Úvod (jen index) | Řeč těla | Psychologie přesvědčování
CTA: Kontaktujte nás → index.html#kontakt
Aktivní stránka: podtržení 2px solid #e63946
Mobil: CSS-only hamburger (checkbox hack, hidden input), .nav-cta skrytý na 768px

**HERO**
Foto: skupinový workshop s overlayem 70%
Tag: SOFT SKILLS AGENTURA
H1: Čti lidi. *Ovládni místnost.* (em = červeně)
Perex: Trénujeme týmy, které umí číst lidi, přesvědčovat s jistotou a vyjednávat z pozice síly.
CTA primární: Prohlédnout kurzy → #kurzy
CTA sekundární: Domluvit schůzku → #kontakt

**PROČ SKILLSHOT** (nad kurzy, 2 bloky, inline SVG)
Blok 1 (zap SVG): Žádná teorie pro teorii / Každý nástroj si účastníci vyzkouší ještě během školení. Odcházíte s dovednostmi, ne poznámkami.
Blok 2 (bar-chart SVG): Měřitelné výsledky / Definujeme KPI předem. Po školení vyhodnotíme skutečný posun. Platíte za výsledek, ne za čas.

**KURZY** (id="kurzy", pozadí #f5f5f5)
Nadpis: Dva kurzy. Jeden výsledek.
Perex: Praktické programy navržené přímo pro firemní prostředí — bez zbytečné teorie, s okamžitou využitelností.

Karta 1 — TMAVÁ (#0a0a0a pozadí, bílý text):
- Tag: NEVERBÁLNÍ KOMUNIKACE (červený)
- H3: Řeč těla: Čti lidi jako knihu
- Popis: Naučte se rozpoznat emoce, záměry a lži dřív, než je druhá strana vysloví.
- Meta: 2 dny · skupinový trénink
- Link: Detail kurzu → rec-tela.html

Karta 2 — SVĚTLÁ (#ffffff pozadí, tmavý text):
- Tag: PSYCHOLOGIE VLIVU (oranžový)
- H3: Psychologie přesvědčování: Techniky vlivu
- Popis: Pochopte mechanismy rozhodování a naučte se eticky ovlivňovat názory, chování a výsledky.
- Meta: 2 dny · skupinový trénink
- Link: Detail kurzu → psychologie-presvecovani.html

**KONTAKT** (id="kontakt", pozadí #0a0a0a)
Nadpis: Pojďme si promluvit
Perex: Rádi připravíme nezávaznou nabídku na míru pro váš tým. Odpovídáme do 24 hodin.
Kontakty: info@skillshot.cz | +420 775 123 456 | Nám. Bratří Synků 4, Praha 4 | IČO: 09876543
Formulář (Formspree): labely + jméno, firma, e-mail, zpráva, tlačítko "Odeslat poptávku"

**KONTAKTNÍ OSOBA — Jana Dvořáková**
Umístění: vedle kontaktních dat nebo nad formulářem, v rámci kontaktní sekce.
Soubor fotky: assets/jana-dvorakova.jpg (⚠️ uložit ručně — pravý klik na foto v chatu → Uložit jako)

HTML pattern:
```html
<div class="contact-person">
  <img src="assets/jana-dvorakova.jpg" alt="Jana Dvořáková, Skillshot" class="contact-photo">
  <div class="contact-person-info">
    <p class="contact-person-name">Jana Dvořáková</p>
    <p class="contact-person-role">Zakladatelka & hlavní lektorka</p>
    <a href="mailto:info@skillshot.cz" class="contact-person-email">info@skillshot.cz</a>
  </div>
</div>
```

CSS pattern:
```css
.contact-person {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
}
.contact-photo {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  object-fit: cover;
  object-position: center top;
  border: 2px solid #f4a261;
  flex-shrink: 0;
}
.contact-person-name {
  font-size: 1.1rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 0.25rem;
}
.contact-person-role {
  font-size: 0.85rem;
  color: #888;
  margin-bottom: 0.4rem;
}
.contact-person-email {
  font-size: 0.9rem;
  color: #f4a261;
  text-decoration: none;
}
```

Poznámky k implementaci:
- Foto kruhové (border-radius: 50%), object-position: center top aby byla vidět tvář
- Oranžový border (#f4a261) odpovídá barevnému akcentu kontaktní sekce
- Na mobilu (480px): flex-direction: column, foto centrované
- alt text: "Jana Dvořáková, Skillshot" (přístupnost)

---

### rec-tela.html — Řeč těla

**HERO**
Foto: gesta/tvář při jednání, overlay 70%, červený akcent
Tag: NEVERBÁLNÍ KOMUNIKACE
H1: Řeč těla: Čti lidi *jako knihu.*
Perex: Dvoudenní intenzivní trénink pro obchodníky, manažery a HR profesionály, kteří chtějí vidět víc, než ostatní říkají.
CTA: Mám zájem o kurz → #poptat

**CO SE NAUČÍTE** (6 bodů, inline SVG)
- oko: Rozpoznat skryté emoce a záměry dřív, než je druhá strana vysloví
- trojúhelník: Odhalit nesoulad mezi slovy a tělem — klíč k důvěryhodnosti
- ruka: Číst gesta a postoj v reálném čase bez přerušení konverzace
- lidé: Poznat, kdo skutečně rozhoduje — i když celou schůzku mlčí
- lupa: Detekovat nejistotu, lež nebo skrytý odpor včas
- štít: Působit sebevědomě a čitelně i pod tlakem

**PRO KOHO** (3 profily, červený border-left)
- Obchodní zástupci: Čtěte zákazníka ještě před prvním slovem. Poznejte kdy souhlasí a kdy jen přikyvuje.
- Manažeři a lídři: Poznejte skutečný stav týmu, ne jen to co vám říkají na poradě.
- HR a náboráři: Odhalte nesoulad mezi CV a realitou ještě při pohovoru.

**JAK KURZ PROBÍHÁ**
Den 1 — Základy čtení těla
- Věda za gestikou: proč tělo "mluví" jinak než slova
- Mimika a mikrovýrazy: 7 základních emocí, které nelze skrýt
- Proxemika: co vzdálenost říká o vztazích a moci
- Oční kontakt, postoj, orientace těla — výklad v kontextu
- Praktické cvičení: analýza videozáznamů reálných situací

Den 2 — Aplikace v praxi
- Simulace obchodních jednání a pohovorů v malých skupinách
- Videoanalýza nahrávek účastníků s individuálním komentářem
- Vlastní neverbální projev: jak působit sebevědomě a čitelně
- Etika čtení těla: kdy a jak poznatky používat
- Individuální zpětná vazba lektora, akční plán pro každého účastníka

Info: max. 12 osob | cena na vyžádání | osvědčení o absolvování

**FORMULÁŘ** (id="poptat", tmavé pozadí)
Nadpis: Připraveni vidět pravdu?
Perex: Vyplňte formulář a ozveme se do 24 hodin s nabídkou na míru.
Pole: jméno, firma, e-mail, hidden kurz="Řeč těla: Čti lidi jako knihu", dotaz/poznámka
Tlačítko: Nezávazně poptat kurz

---

### psychologie-presvecovani.html — Psychologie přesvědčování

**HERO**
Foto: skupinový workshop, overlay 70%, oranžový akcent
Tag: PSYCHOLOGIE VLIVU
H1: Psychologie přesvědčování: *Techniky vlivu.*
Perex: Naučte se, jak lidé skutečně rozhodují — a jak toho využít eticky, efektivně a s trvalým výsledkem.
CTA: Mám zájem o kurz → #poptat

**CO SE NAUČÍTE** (6 bodů, inline SVG)
- magnet: Cialdiniho principy vlivu — jak je aplikovat okamžitě, ne jen pochopit
- bublina: Framing a kotvení: proč stejná věc řečená jinak vede k jinému rozhodnutí
- procesor: Kognitivní zkratky mozku (biasy) — jak je předvídat a využít eticky
- fajfka: Přesvědčování bez manipulace: kde je hranice a jak ji nepřekročit
- lidé: Jak proměnit skeptika v zastánce — i bez formální autority
- mikrofon: Strukturovaný příběh jako nejsilnější nástroj změny názoru

**PRO KOHO** (3 profily, oranžový border-left)
- Obchodní týmy: Zvyšte úspěšnost jednání a zkraťte prodejní cyklus. Přesvědčujte s jistotou, ne náhodou.
- Manažeři a lídři: Získejte souhlas bez nátlaku, veďte změnu bez odporu. Ovlivňujte bez formální autority.
- Marketing a komunikace: Pište texty a kampaně, které skutečně mění chování. Ne jen informují.

**JAK KURZ PROBÍHÁ**
Den 1 — Psychologie rozhodování
- Jak mozek skutečně rozhoduje: vědomé vs. automatické procesy
- Cialdiniho 7 principů vlivu: reciprocita, závazek, sociální důkaz, autorita, oblíbenost, nedostatek, jednota
- Kognitivní zkreslení v praxi: anchoring, framing, confirmation bias
- Kotvení a framing: jak nastavit referenční bod ještě před jednáním
- Případové studie z firemního prostředí

Den 2 — Techniky vlivu v praxi
- Strukturovaný příběh jako nástroj přesvědčování: stavba, tempo, emoce
- Roleplay reálných scénářů: obchodní jednání, interní prezentace, change management
- Etické hranice vlivu: rozdíl mezi přesvědčováním a manipulací
- Individuální zpětná vazba lektora na styl komunikace
- Akční plán: 3 techniky k okamžitému nasazení

Info: max. 12 osob | cena na vyžádání | osvědčení o absolvování

**FORMULÁŘ** (id="poptat", tmavé pozadí)
Nadpis: Připraveni ovládnout umění přesvědčování?
Perex: Vyplňte formulář a ozveme se do 24 hodin s nabídkou na míru.
Pole: jméno, firma, e-mail, hidden kurz="Psychologie přesvědčování: Techniky vlivu", dotaz/poznámka
Tlačítko: Nezávazně poptat kurz

---

## 5. Technické požadavky
- Každý HTML: lang="cs", charset="UTF-8", viewport, description meta, link na css/style.css
- Logo v nav: vždy `<a href="index.html">`, nikdy `<div>`
- Formuláře: action="https://formspree.io/f/[FORMSPREE_ID]" — nahradit před spuštěním
- Hamburger: CSS-only checkbox hack, input type="checkbox" hidden
- Ikony: inline SVG s aria-hidden="true", stroke="currentColor"
- Responsivita: clamp() pro typografii, CSS grid auto-fit
- Breakpointy: 768px (tablet), 480px (mobil)
- GitHub repo: https://github.com/HonzaD2023/web-page (branch: main)
- GitHub Pages: https://honzad2023.github.io/web-page/

---

## 6. Opravy responsivity (identifikované auditem)

### Oprava 1 — .nav-cta skrýt na mobilu
```css
@media (max-width: 768px) {
  .nav-cta { display: none; }
}
```
Důvod: při flex-direction:column v nav zůstává CTA jako třetí element mimo hamburger menu.

### Oprava 2 — textarea fallback pro starší Android (`:has()` nepodporováno)
Přidat třídu `.form-field--full` na wrapper textarěy:
```html
<div class="form-field form-field--full">
```
```css
.form-field--full { grid-column: 1 / -1; }
```
Důvod: `:has(textarea)` selektor není podporován na Android < Chrome 105.

### Oprava 3 — learn-grid breakpoint na tabletu
```css
@media (max-width: 768px) {
  .learn-grid { grid-template-columns: 1fr; }
}
```
Důvod: na 768px se vejdou 2 sloupce s minmax(280px), ale text je příliš stísněný.

### Oprava 4 — odstranit duplicitní nav bloky v media query
V style.css jsou dva bloky `nav { ... }` v @media (max-width: 768px) — sloučit do jednoho.

---

## 7. Kontrola prokliků a odkazů

### Interní navigace — otestovat na každé stránce
| Odkaz | Z | Cíl | Očekávaný výsledek |
|-------|---|-----|-------------------|
| Logo Skillshot | všechny stránky | index.html | Přechod na hlavní stranu |
| Řeč těla (nav) | index, psychologie | rec-tela.html | Přechod na podstránku kurzu 1 |
| Psychologie (nav) | index, rec-tela | psychologie-presvecovani.html | Přechod na podstránku kurzu 2 |
| Kontaktujte nás (nav) | rec-tela, psychologie | index.html#kontakt | Scroll na kontaktní sekci hlavní strany |
| Kontaktujte nás (nav) | index | #kontakt | Scroll dolů na kontakt |
| Prohlédnout kurzy (hero CTA) | index | #kurzy | Scroll na sekci kurzů |
| Domluvit schůzku (hero CTA) | index | #kontakt | Scroll na kontakt |
| Detail kurzu → (karta 1) | index | rec-tela.html | Přechod na kurz 1 |
| Detail kurzu → (karta 2) | index | psychologie-presvecovani.html | Přechod na kurz 2 |
| Mám zájem o kurz (hero CTA) | rec-tela, psychologie | #poptat | Scroll na formulář poptávky |
| ← Zpět na hlavní stranu | rec-tela, psychologie | index.html | Přechod zpět |

### Kontaktní odkazy — otestovat kliknutí
| Odkaz | Očekávaný výsledek |
|-------|-------------------|
| info@skillshot.cz | Otevře e-mailového klienta |
| +420 775 123 456 | Na mobilu otevře volání, na desktopu nic/tel: |

### Formuláře — otestovat odeslání
| Formulář | Test | Očekávaný výsledek |
|----------|------|-------------------|
| index.html #kontakt | Vyplnit a odeslat | Formspree potvrzení / redirect |
| rec-tela.html #poptat | Vyplnit + hidden pole kurz | E-mail s názvem kurzu |
| psychologie #poptat | Vyplnit + hidden pole kurz | E-mail s názvem kurzu |
| Všechny formuláře | Odeslat bez required pole | Browser validace, neodeslat |

### 404 stránka
| Test | Očekávaný výsledek |
|------|-------------------|
| Zadat neexistující URL | Zobrazí 404.html |
| Klik "Zpět na hlavní stranu" | Přechod na index.html |

---

## 8. Rozšíření sekce "Jak kurz probíhá" — návod pro implementaci

Aktuální stav: sekce obsahuje 2 bloky (Den 1, Den 2) s krátkým popisem a info řádek (počet osob, cena, osvědčení).

### Co přidat do HTML (oba soubory)

**Rozšířit `.day-block`** o odrážky pod odstavcem:
```html
<div class="day-block">
  <div class="day-number">1</div>
  <h4>Základy čtení těla</h4>
  <p>Věda za gestikou, mimika a mikrovýrazy, proxemika, první dojmy.</p>
  <ul class="day-topics">
    <li>Mimika a 7 základních emocí, které nelze skrýt</li>
    <li>Proxemika: co vzdálenost říká o vztazích a moci</li>
    <li>Analýza videozáznamů reálných situací</li>
  </ul>
</div>
```

**CSS pro `.day-topics`:**
```css
.day-topics {
  list-style: none;
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.day-topics li {
  font-size: 0.9rem;
  color: var(--muted);
  padding-left: 1rem;
  position: relative;
}
.day-topics li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--accent);
}
```

### Textace pro rec-tela.html
Den 1 — body: Věda za gestikou, mimika a mikrovýrazy, proxemika.
Odrážky: Mimika a 7 základních emocí, které nelze skrýt | Proxemika: co vzdálenost říká o moci | Oční kontakt a orientace těla | Analýza videozáznamů reálných situací

Den 2 — body: Simulace jednání, videoanalýza, individuální zpětná vazba.
Odrážky: Simulace obchodních jednání v malých skupinách | Videoanalýza vlastního projevu | Etika čtení těla: kdy a jak poznatky používat | Akční plán pro každého účastníka

### Textace pro psychologie-presvecovani.html
Den 1 — body: Jak mozek rozhoduje, Cialdiniho principy, kognitivní zkreslení.
Odrážky: Cialdiniho 7 principů vlivu v praxi | Kotvení a framing před jednáním | Kognitivní biasy: anchoring, confirmation bias | Případové studie z firemního prostředí

Den 2 — body: Roleplay scénářů, etické hranice, individuální zpětná vazba.
Odrážky: Strukturovaný příběh jako nástroj přesvědčování | Roleplay: obchodní jednání a change management | Rozdíl přesvědčování vs. manipulace | 3 techniky k okamžitému nasazení

---

## 9. Verifikační checklist

**Textace:**
- [ ] Vykání jednotné všude (Naučíte se, Získáte, Odcházíte)
- [ ] Žádné emoji — pouze inline SVG
- [ ] Body = výsledky, ne témata
- [ ] Slogan "Čti lidi. Ovládni místnost." na index hero

**Design:**
- [ ] Karta kurzu 1 tmavá (#0a0a0a), karta 2 světlá (#fff)
- [ ] Fotografie s overlayem 70%
- [ ] Inline SVG ikony s aria-hidden="true"
- [ ] Aktivní stav v navigaci (červené podtržení)
- [ ] Logo = `<a>` tag, ne `<div>`

**Responsivita (Chrome DevTools):**
- [ ] iPhone SE 375px — žádný horizontální scroll
- [ ] iPhone SE 375px — hamburger menu funkční
- [ ] iPhone SE 375px — .nav-cta skrytý
- [ ] iPad 768px — formulář 2 sloupce, textarea přes celou šířku
- [ ] Galaxy S20 360px — karty kurzů 1 sloupec
- [ ] Všechny podstránky na 390px — learn-grid, for-whom 1 sloupec

**Prokliky a odkazy:**
- [ ] Všechny nav odkazy funkční na všech 3 stránkách
- [ ] Logo vede na index.html
- [ ] CTA "Kontaktujte nás" scrolluje/přechází na kontakt
- [ ] "Zpět na hlavní stranu" na podstránkách
- [ ] "Detail kurzu →" karty na index.html
- [ ] "Mám zájem o kurz" scrolluje na #poptat
- [ ] mailto:info@skillshot.cz otevírá e-mailového klienta
- [ ] tel:+420775123456 funkční na mobilu
- [ ] 404.html se zobrazí na neexistující URL
- [ ] "Zpět" odkaz na 404.html

**Formuláře:**
- [ ] Formspree ID nahrazeno ve všech 3 souborech
- [ ] Testovací odeslání proběhlo
- [ ] Required pole blokují odeslání bez vyplnění
- [ ] Hidden pole "kurz" odesláno správně

**Technická kontrola:**
- [ ] W3C validátor bez chyb (validator.w3.org)
- [ ] lang="cs" a charset="UTF-8" na každé stránce
- [ ] favicon.svg se zobrazuje v záložce prohlížeče
- [ ] 404.html přítomen
