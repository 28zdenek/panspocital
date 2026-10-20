# Pan Spočítal – design systém

> Verze 2.1 · 20. 10. 2026 · živá ukázka se všemi komponentami a kódem: https://panspocital.cz/design-system/
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
| `--color-focus` | `#4FB3E8` | obrys při ovládání klávesnicí |
| `--color-success` / `-bg` / `-text` | `#1E7B4C` / `#E5F4EA` / `#14462A` | jen stav: hotovo, schváleno |
| `--color-danger` / `-bg` / `-text` | `#B42318` / `#FBE6E4` / `#6B1D16` | jen stav: chyba, smazání |
| `--color-warn` / `-bg` / `-text` | `#E9B949` / `#FFF4D6` / `#5B4300` | jen stav: pozor |

Poměr na stránce: ~60 % pozadí a bílá, ~28 % noční, ~10 % modrá, zlatou nese jen labrador.

**Kontrast:** text na pozadí 11,7 : 1 · vedlejší text 7,1 : 1 · modrá na pozadí 4,8 : 1 · bílá na modré 5,1 : 1. Světle modré odstíny (`#CFE9FB`, `#8FD0F2`) **nikdy na text**.

## 5. Typografie

- Jediné písmo: **Bricolage Grotesque** (Google Fonts), řezy 400 / 600 / 800.
- H1: `clamp(38px, 7vw, 76px)`, 800, `letter-spacing: -0.045em`, řádkování 1.
- H2: `clamp(26px, 3.6vw, 38px)`, 800, `-0.03em`.
- H3: 22 px, 800 · H4: 20 px, 800 · H5: 18 px, 600 · H6: 16 px, 600, velká písmena.
- Display (velký úvod): `clamp(44px, 9vw, 104px)`. Velká čísla (splátka): `clamp(32px, 5vw, 48px)`, tabulková čísla.
- Malý text 15 px, popisek 13 px (nikdy menší).
- Text: 18 px / 1,6. Perex: `clamp(18px, 2.2vw, 22px)`, vedlejší barva.
- Štítek: 13–14 px, 600, velká písmena, `letter-spacing: 0.06em`.
- Délka řádku max. ~60 znaků.

## 6. Mezery, tvary, stíny, pohyb

- Mezery: násobky 4 px (`--space-1` … `--space-16`). Sekce 48 px+.
- Kontejner 1180 px (text 980 px), okraj 20 px, na mobilu 16 px. Mezera mezi sekcemi `--section` (48–96 px).
- Breakpointy: mobil < 560 px · tablet 560–900 px · desktop > 900 px · široký > 1180 px. Navrhujeme od 360 px.
- Výšky prvků: `--control-sm` 40 px, `--control-md` 48 px (výchozí), `--control-lg` 56 px. Ikony 16 / 20 / 24 px.
- Vrstvy (`--z-*`): sticky 100, dropdown 200, tooltip 300, okno 400, toast 500.
- Zaoblení: 8 (malé) · 18 (poznámky, postavy) · 24 (karty) · 28 px (fotky, video) · 999 (štítky, tlačítka).
- Stíny dlouhé a měkké, tónované do modra: `--shadow-sm | md | lg`. Nikdy tvrdé šedé.
- Pohyb: 0,15–0,2 s, `--ease`. Karta při najetí vyjede o 4 px. Respektujeme `prefers-reduced-motion`.

## 7. Komponenty (`css/components.css`)

Ukázka a kód každé komponenty: https://panspocital.cz/design-system/

| Třída | Co to je |
|---|---|
| `.ps-body`, `.ps-container` (+`--text`) | základ stránky, kontejner |
| `.ps-display`, `.ps-h1` … `.ps-h6`, `em` uvnitř | nadpisy, `em` = zvýrazněné slovo |
| `.ps-lead`, `.ps-label`, `.ps-muted`, `.ps-small`, `.ps-caption`, `.ps-num` | perex, štítek nad nadpisem, vedlejší / malý text, popisek, číslo bez zalomení |
| `.ps-link` (+`--arrow`) | odkaz v textu / samostatný se šipkou |
| `.ps-list--check`, `.ps-list--num` | seznam s fajfkami / s čísly |
| `.ps-brand` (+`--sm`) | logo |
| `.ps-btn--primary/secondary/dark/ghost/danger/white`, `--sm/--lg/--block/--icon`, `aria-busy`, `disabled`, `.ps-btn-group` | tlačítka |
| `.ps-tag` (+`--dark`) | štítek tématu |
| `.ps-badge` (+`--success/warn/danger/neutral/solid/plain`) | odznak stavu |
| `.ps-alert` (+`--success/warn/danger`), `__title`, `__close` | upozornění s ikonou |
| `.ps-note` (+`--warn`) | jednoduchá poznámka v textu |
| `.ps-field`, `.ps-input`, `.ps-select`, `.ps-textarea`, `.ps-hint`, `.ps-error`, `.ps-success`, `--error/--success` | formulářová pole a stavy |
| `.ps-input-group`, `__addon` | pole s jednotkou (Kč, %, let) |
| `.ps-check` (checkbox/radio, text v `<span>`), `.ps-choice` (volby jako karty), `.ps-switch`, `.ps-fieldset` | volby |
| `.ps-range`, `.ps-range-row`, `.ps-range-scale` | posuvník kalkulačky (vyplnění přes `--val`) |
| `.ps-result`, `__row` | tmavý panel s výsledkem kalkulačky |
| `.ps-slider-field`, `.ps-input-group__btn` | posuvník spárovaný s polem a −/+ (povinné, WCAG 2.5.7) |
| `.ps-choice--rate` | výběr fixace jako dlaždice se sazbou |
| `.ps-meter` (+`is-warn/is-danger`) | LTV s hranicemi ČNB 80 / 90 % |
| `.ps-summary`, `.ps-trust`, `.ps-legal` | souhrn přenesený do formuláře, řádek důvěry, reprezentativní příklad |
| `.ps-tip`, `__btn`, `__bubble` (+`--bottom`) | tooltip |
| `.ps-table-wrap`, `.ps-table` (+`--striped/--compact`), `.is-num`, `.is-best` | tabulky |
| `.ps-card` (+`__media/__body/__title/__text`, `--hover`) | karta |
| `.ps-character` | karta postavy s popiskem |
| `.ps-tabs`, `__list`, `__tab`, `__panel` | záložky |
| `.ps-accordion` (`<details>`), `__body` | FAQ |
| `.ps-nav`, `__links`, `__toggle` · `.ps-breadcrumb` · `.ps-pagination` | navigace |
| `.ps-stepper` (`.is-done/.is-current`), `.ps-progress`, `.ps-step` | postup a průběh |
| `.ps-spinner`, `.ps-skeleton` | načítání |
| `.ps-modal` (`<dialog>`), `__head/__body/__foot`, `.ps-close` · `.ps-toast-area`, `.ps-toast` | okno, krátká zpráva |
| `.ps-avatar` (+`--sm/--lg`), `.ps-avatar-group`, `.ps-quote`, `.ps-stars` | lidé a reference (avatary v `img/avatar/`) |
| `.ps-stat`, `__value`, `__label` | velké číslo |
| `.ps-empty` | prázdný stav, 404 |
| `.ps-cta` | tmavý pás s výzvou |
| `.ps-footer`, `__cols`, `__legal` | patička (povinné údaje zprostředkovatele dodá eDO) |
| `.ps-photo`, `.ps-divider` (+`--text`), `.ps-surface` | fotka, oddělovač, bílý panel |
| `.ps-grid--2/3/4`, `.ps-split`, `.ps-stack` (+`--sm/--lg`), `.ps-cluster`, `.ps-section`, `.ps-sr-only` | rozvržení |

Pravidla:
- Na obrazovce **jen jedno hlavní tlačítko**; text tlačítka je sloveso („Spočítat hypotéku“, „Chci nabídku“).
- Popisek vždy nad polem, chyba pod polem lidsky a s radou. Poptávkový formulář max. 3–4 pole.
- Ikony: [Lucide](https://lucide.dev), obrysové, čára 2 px, `currentColor`.
- Stav nikdy jen barvou (vždy i text nebo ikona).

### Kalkulačka (v2, podle výzkumu 20. 10. 2026)
- Sazbu nenechávat psát: výběr fixace + sazba z průměru trhu s datem a zdrojem, vlastní sazba volitelně.
- Vstupy: cena nemovitosti + vlastní zdroje → úvěr a LTV (limit ČNB 80 %, do 36 let 90 %). Druhá záložka „Na kolik dosáhnu“.
- Výsledek je zdarma; kontakt až za hodnotu navíc („Pošli mi srovnání bank“), hodnoty se předvyplní.
- Každé číslo o nákladech = reprezentativní příklad s RPSN (§ 91 zák. 257/2016 Sb.) – text dodá eDO.
- Telefon s vysvětlením, proč ho chceme. Marketingový souhlas zvlášť a nezaškrtnutý.

### Čísla a formáty
- Částka `4 500 000 Kč`, zkráceně `4,5 mil. Kč`, splátka `18 450 Kč/měs.`, úrok `4,49 %`, datum `20. 10. 2026`, telefon `+420 777 123 456`, čas `9.00–17.00`.
- Mezi číslem a jednotkou pevná mezera (`&nbsp;`). V JS `n.toLocaleString('cs-CZ')`.
- U každého výpočtu věta, že jde o orientační výpočet.

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
