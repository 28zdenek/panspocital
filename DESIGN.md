# Pan Spočítal – design systém

> Verze 1.0 · 19. 10. 2026 · živá ukázka: https://panspocital.cz/design-system/
>
> Tenhle soubor je pravidlo pro lidi i pro AI asistenty. Než uděláš cokoliv nového
> (stránku, banner, příspěvek, video), přečti si ho a použij `css/tokens.css`
> a `css/components.css`.

## 1. Značka v jedné větě

**Pan Spočítal** je kamarád, který ti hypotéku spočítá i vyřídí – od prvního propočtu až po klíče od nového domova. Po lidsku, přehledně a bez stresu.

Obory: hypotéky, úvěry, pojištění, spoření. Trh: Česko.

## 2. Principy

1. **Po lidsku** – tykáme, krátké věty, žádný bankovní žargon.
2. **Klid a důvěra** – světlé pozadí, modrá, hodně vzduchu. Nic nebliká.
3. **Postavy jsou hrdinové** – žádné ikonky ani fotobanky, příběh nesou 3D postavy.
4. **Jedno slovo v barvě** – v nadpisu zvýrazňujeme vždy jen jedno klíčové slovo.

## 3. Logo

- Kulatý výřez s Panem Spočítalem a labradorem (`img/logo.jpg`) + nápis ve dvou řádcích: **Pan** (modře, 600) / **Spočítal** (800, stažené písmo).
- Výřez má bílý okraj 3 px a jemný modrý stín (`.ps-brand`).
- Ikona: `favicon.png` (64 px), `apple-touch-icon.png` (180 px). Minimální velikost 32 px.
- **Nikdy:** deformovat, dávat do čtverce, přebarvovat mimo paletu, používat starou zelenou postavičku.
- Zdroj loga ve vysokém rozlišení: `~/Documents/Hypoteky/maskoti/logo/logo-b.png` (mimo repozitář).

## 4. Barvy

Používej **sémantické tokeny**, ne hex kódy.

| Token | Hex | Použití |
|---|---|---|
| `--color-text` | `#12355B` | veškerý text, tmavé plochy |
| `--color-text-muted` | `#3D5670` | popisky, perex |
| `--color-accent` | `#1A72B3` | odkazy, zvýraznění v nadpisu, hlavní tlačítko |
| `--color-accent-hover` | `#155E94` | hover akcentu |
| `--color-accent-soft` | `#CFE9FB` | štítky, světlé plochy |
| `--color-info-bg` | `#E3F1FB` | informační boxy |
| `--color-warn-bg` | `#FFF4D6` | varování |
| `--color-bg` | `#F4F8FB` | pozadí stránky |
| `--color-surface` | `#FFFFFF` | karty |
| `--color-line` | `#DCE7F0` | linky a okraje |
| `--ps-blue-300` | `#8FD0F2` | barva vesty – jen ilustrace a plochy |

**Kontrast:** text na pozadí 11,7 : 1 · vedlejší text 7,1 : 1 · modrá na pozadí 4,8 : 1 · bílá na modré 5,1 : 1. Světle modré odstíny (`#CFE9FB`, `#8FD0F2`) **nikdy na text**.

## 5. Typografie

- Jediné písmo: **Bricolage Grotesque** (Google Fonts), řezy 400 / 600 / 800.
- H1: `clamp(38px, 7vw, 76px)`, 800, `letter-spacing: -0.045em`, řádkování 1.
- H2: `clamp(26px, 3.6vw, 38px)`, 800, `-0.03em`.
- H3: 22 px, 800.
- Text: 18 px / 1,6. Perex: `clamp(18px, 2.2vw, 22px)`, vedlejší barva.
- Štítek: 13–14 px, 600, velká písmena, `letter-spacing: 0.06em`.
- Délka řádku max. ~60 znaků.

## 6. Mezery, tvary, stíny, pohyb

- Mezery: násobky 4 px (`--space-1` … `--space-16`). Sekce 48 px+.
- Kontejner 1180 px (text 980 px), okraj 20 px, na mobilu 16 px.
- Zaoblení: 8 (malé) · 18 (poznámky, postavy) · 24 (karty) · 28 px (fotky, video) · 999 (štítky, tlačítka).
- Stíny dlouhé a měkké, tónované do modra: `--shadow-sm | md | lg`. Nikdy tvrdé šedé.
- Pohyb: 0,15–0,2 s, `--ease`. Karta při najetí vyjede o 4 px. Respektujeme `prefers-reduced-motion`.

## 7. Komponenty (`css/components.css`)

| Třída | Co to je |
|---|---|
| `.ps-body`, `.ps-container` | základ stránky, kontejner |
| `.ps-h1/.ps-h2/.ps-h3`, `em` uvnitř | nadpisy, `em` = zvýrazněné slovo |
| `.ps-lead`, `.ps-label`, `.ps-muted` | perex, malý štítek nad nadpisem, vedlejší text |
| `.ps-brand` (+ `--sm`) | logo |
| `.ps-tag` (+ `--dark`) | štítek |
| `.ps-btn--primary / --secondary / --dark` | tlačítka, výška 48 px |
| `.ps-card`, `__media`, `__body`, `__title`, `__text`, `--hover` | karta |
| `.ps-character` | karta postavy s popiskem |
| `.ps-note` (+ `--warn`) | poznámka / varování |
| `.ps-step` | číslo kroku |
| `.ps-photo` | velká fotka se stínem |
| `.ps-field`, `.ps-input`, `.ps-hint` | formulář |
| `.ps-grid--2/3/4` | responzivní mřížky |

Pravidla: na stránce **jen jedno hlavní tlačítko**; text tlačítka je sloveso („Spočítat hypotéku“, „Chci nabídku“).

## 8. Maskot a rodina

Styl: **3D animovaný (jako z animovaného filmu), přirozené proporce, normální oblečení, světle modrá jen jako akcent**.
Zamítnuto: ruční kresba, plastelína, nálepky, plochý vektor, kulaté figurky.

| Postava | Vzhled | Témata |
|---|---|---|
| **Pan Spočítal** | mladý muž, krátké hnědé vlasy, světle modrá péřová vesta, šedá mikina, džíny, bílé tenisky | hypotéky, první bydlení |
| **Labrador** | zlatý, modrý obojek, klíček ve tvaru domku | děkovné stránky, 404, nálada |
| **Paní Spočítalová** | hnědý mikádo, světle modrý svetr, bílé triko, džíny | rozpočet, úvěry |
| **Malá Spočítalová** (5) | copánky se žlutými gumičkami, žluté šaty | spoření, děti |
| **Malý Spočítal** (9) | světle modré triko s „=“, džíny | kalkulačky, spoření |
| **Babička** | šedé kudrny, brýle, perly, béžový pletený svetr | pojištění, rezerva |
| **Děda** | bílý knír, šedá bekovka, hnědá vesta | důchod, úroky, zkušenost |

Reference: `img/rodina/*.jpg` (web), originály v `~/Documents/Hypoteky/maskoti/rodina/`.

**Základ promptu** (vždy s referenčním obrázkem):

```
Keep this exact character (young man with short brown hair, light sky blue puffer vest
over grey hoodie, jeans) and his happy golden labrador with a blue collar, same 3D Pixar
animation style. [SCÉNA]. Natural realistic colors, light sky blue as accent,
soft daylight, no text.
```

Zakázáno: poradce objímá klienty, hromady peněz/zlata, „zbohatni rychle“, smutné nebo vystrašené postavy (kromě scény „odcházíš“).

## 9. Hlas a tón

- **Tykáme.** „Hypotéku ti spočítáme.“
- **My děláme práci, ty máš klid.** Spočítáme, vyřídíme, ohlídáme, ozveme se.
- **Krátké věty, konkrétně.** „Ozveme se do 24 hodin.“
- **Lehký humor patří postavám**, ne penězům.
- ✅ „Od prvního propočtu až po klíče od nového domova.“
- ❌ „Komplexní řešení financování nemovitostí na míru Vašim potřebám.“

## 10. Přístupnost

- Kontrast textu ≥ 4,5 : 1. Klikací prvky ≥ 44 px. Viditelný `:focus-visible`.
- `alt` u postav, prázdný `alt` u dekorací.
- Video ztlumené s tlačítkem pro zvuk.

## 11. Sdílení (Open Graph)

- `og.jpg` 1200 × 630, pod 300 kB: postava vpravo, nadpis vlevo, logo nahoře, štítek s doménou dole.
- Po změně obrázku sdílej s `?v=N`, jinak WhatsApp ukáže starý náhled.
