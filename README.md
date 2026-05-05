# Skillshot — Web agentury

Prezentační web české soft skills agentury **Skillshot**. Statický web bez závislostí, připravený pro hosting na GitHub Pages.

## Struktura

```
skillshot/
├── index.html                      # Hlavní strana
├── rec-tela.html                   # Kurz: Řeč těla
├── psychologie-presvecovani.html   # Kurz: Psychologie přesvědčování
├── podminky-uzivani.html           # Podmínky užívání
├── css/
│   └── style.css                   # Sdílené styly
├── assets/
│   └── icons/                      # SVG ikony (Lucide, lokálně)
├── .claude/
│   └── commands/
│       └── push-github.md          # Skill pro commit a push na GitHub
├── 404.html                        # Chybová stránka
└── README.md
```

## Stránky

- **Hlavní strana** — hero, benefity, přehled kurzů, kontaktní formulář
- **Řeč těla: Čti lidi jako knihu** — detail kurzu 1, poptávkový formulář
- **Psychologie přesvědčování: Techniky vlivu** — detail kurzu 2, poptávkový formulář
- **Podmínky užívání** — smluvní podmínky, storno politika, GDPR, duševní vlastnictví

## Technologie

- Čistý HTML5 + CSS3, žádný framework ani build tool
- Responsivní design (mobile-first, CSS grid + clamp())
- Hamburger menu: CSS-only (bez JavaScriptu)
- Kontaktní formulář: [Formspree.io](https://formspree.io) — nutno nastavit vlastní ID
- Ikony: [Lucide Icons](https://lucide.dev) (SVG, lokálně)
- Fotografie: [Unsplash](https://unsplash.com) (licence zdarma)

## Nastavení formuláře

1. Vytvořit účet na [formspree.io](https://formspree.io)
2. Vytvořit nový formulář, zkopírovat ID (formát: `xxxxxxxx`)
3. V `index.html`, `rec-tela.html` a `psychologie-presvecovani.html` nahradit:
   ```html
   action="https://formspree.io/f/[ID]"
   ```
   vlastním ID

## Publikování na GitHub Pages

1. Nahrát repo na GitHub
2. Settings → Pages → Source: `main` branch, `/ (root)`
3. Web bude dostupný na `https://[username].github.io/[repo-name]/`

## Claude Code

Projekt obsahuje lokální skill pro Git workflow:

```
/push-github    — provede commit a push na main podle konvence projektu
```

Konvence commit zpráv: `typ: popis česky` (např. `feat: přidat stránku podmínky užívání`)  
Typy: `feat` · `fix` · `style` · `content` · `refactor` · `chore`

## Checklist před publikací

- [ ] Formulář otestován (testovací odeslání přes Formspree)
- [ ] Validace HTML: [validator.w3.org](https://validator.w3.org)
- [ ] Všechny interní odkazy funkční (včetně `podminky-uzivani.html`)
- [ ] Obrázky mají `alt` atribut
- [ ] Favicon přítomen
- [ ] Mobilní zobrazení ověřeno (Chrome DevTools)

## Vizuální identita

| Prvek | Hodnota |
|-------|---------|
| Primární barva | `#0a0a0a` |
| Akcent červená (kurz 1) | `#e63946` |
| Akcent oranžová (kurz 2) | `#f4a261` |
| Pozadí | `#f5f5f5` |
| Subtext | `#555` (WCAG AA) |

---

© 2026 Skillshot s.r.o.
