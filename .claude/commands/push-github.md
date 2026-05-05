# Skill: push-github

Proveď git commit a push aktuálních změn na GitHub podle níže uvedených pravidel.

## Pravidla

### Větev
Vždy commituj a pushuj na větev **main**. Nikdy nevytvárej nové větve.

### Commit message — formát

```
<typ>: <stručný popis v češtině>
```

**Typy:**
| Typ | Kdy použít |
|-----|-----------|
| `feat` | nová funkcionalita nebo stránka |
| `fix` | oprava chyby nebo broken layoutu |
| `style` | změna CSS, vizuální úpravy bez změny obsahu |
| `content` | úprava textů, obrázků, obsahu stránek |
| `refactor` | přepsání kódu bez změny funkce |
| `chore` | konfigurace, soubory projektu, .gitignore apod. |

**Pravidla pro popis:**
- Psáno česky, malým písmenem (kromě vlastních jmen)
- Imperativ nebo podstatné jméno: „přidat footer odkaz", „opravit hamburger menu na mobilu"
- Max. 72 znaků
- Bez tečky na konci

**Příklady správných zpráv:**
```
feat: přidat stránku podmínky užívání
style: upravit barvy footeru a hover efekty
fix: opravit rozlití layoutu na mobilním zobrazení
content: aktualizovat kontaktní údaje v tiráži
chore: přidat favicon do assets
```

## Postup

1. Zkontroluj stav repozitáře:
   ```
   git status
   git diff
   ```

2. Přidej změněné soubory (konkrétně, ne `git add .`):
   ```
   git add <soubor1> <soubor2> ...
   ```

3. Vytvoř commit se zprávou podle konvence výše:
   ```
   git commit -m "typ: popis změny"
   ```

4. Pushni na main:
   ```
   git push origin main
   ```

5. Potvrď úspěšný push výpisem posledního commitu:
   ```
   git log --oneline -3
   ```

## Poznámky
- Nikdy nepoužívej `--no-verify` ani `--force`
- Každý commit by měl řešit jednu logickou změnu
- Pokud repozitář ještě nemá remote, zeptej se uživatele na URL před push krokem
