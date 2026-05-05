# Skillshot — Web projektu

## Projekt
Prezentační web české soft skills agentury Skillshot. 3 stránky + sdílené CSS.
Hosting: GitHub Pages. Žádný backend, žádný framework, čistý HTML/CSS.

## Struktura souborů
- index.html — hlavní strana
- rec-tela.html — kurz Řeč těla
- psychologie-presvecovani.html — kurz Psychologie přesvědčování
- css/style.css — sdílené styly (NEMĚNIT inline styly v HTML)
- assets/icons/ — Lucide SVG ikony lokálně
- 404.html — chybová stránka
- README.md — dokumentace
- plan.md — kompletní plán webu s textacemi

## Klíčová pravidla
- Jazyk: čeština, vykání (Naučíte se, Získáte, Odcházíte)
- Žádné emoji v obsahu — pouze SVG ikony z assets/icons/
- Žádné CDN závislosti — vše lokálně
- Formuláře: Formspree action="https://formspree.io/f/[FORMSPREE_ID]"
- Interní href bez ./ prefixu (GitHub Pages kompatibilita)
- Každý HTML soubor: lang="cs", charset="UTF-8", viewport meta, description meta

## Barvy
- #0a0a0a — primární pozadí
- #e63946 — červená (kurz 1, hero, CTA)
- #f4a261 — oranžová (kurz 2, kontakt)
- #f5f5f5 — světlé pozadí sekcí
- #555555 — subtext (WCAG AA)

## Cílová skupina
HR manažeři a L&D korporátních firem. Tón: odvážný, konkrétní, výsledky ne procesy.
