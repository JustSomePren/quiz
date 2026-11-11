# Chytrý učící kvíz — Leadership & management

Jednoduchá webová aplikace (1 soubor `index.html`), běží přímo v prohlížeči, funguje offline i na mobilu. Pokrok se ukládá lokálně v prohlížeči (localStorage).

**Spustit:** otevři `index.html`, nebo běžící GitHub Pages odkaz (Settings → Pages → větev `main`, kořen `/`).

## Jak to funguje (chytré učení)
- Otázky se řadí do dávek po max 5 aktivních: nové karty přibývají jen když jsou poslední odpovědi úspěšné — při 3+ špatných z posledních 5 se nové otázky nedávají; už zvládnuté se občas (cca 18 %) vracejí k procvičení
- Ukazatel Zvládnuto se zobrazuje zeleně až po prvním reálně zvládnutém; plný X / 115 až od 90/115
- Každá otázka má v pozadí skóre: nezodpovězené mají vysokou prioritu, čerstvě položené nižší (rotace v rámci dávky)
- **2× špatně po sobě → priorita rapidně nahoru** (×6, pak ×2 za každou další chybu)
- **3× správně za sebou → rapidně dolů**; pokud byla otázka předtím chybována, nejde hned o "zvládnuto" — dá se **pauza (~5 min, při opakování déle)** a pak se otázka ukáže znovu k ověření; teprve správně po pauze = definitivně zvládnuto
- Cíl: **všechny otázky zvládnuté** (3× správně za sebou + ověření po pauze u chybovaných) — pak se zobrazí výherní banner
- Odpovědi se **míchají při každém zobrazení** a otázka se navíc střídá mezi **variantami znění**
- Režim „Celý test" = klasická zkouška přes všechny otázky najednou
- Přehled stavu každé otázky (klik = procvičit), reset pokroku, klávesy 1–6 / Enter

## Data
`otazky.json` — 115 otázek ABCD se správnými odpověďmi a variantami znění (JSON je zároveň zabudované v `index.html`; po úpravě dat je potřeba promítnout změnu i do `index.html`).
