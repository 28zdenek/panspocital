# panspocital.cz

Web značky **Pan Spočítal** – hypotéky, úvěry, pojištění a spoření po lidsku.
Pracovní verze (`noindex`), hostovaná zdarma na GitHub Pages.

| Stránka | Adresa |
|---|---|
| Hlavní web | https://panspocital.cz |
| Design systém | https://panspocital.cz/design-system/ |
| Návod, jak projekt vznikl | https://panspocital.cz/navod/ |

## Design systém

- [`DESIGN.md`](DESIGN.md) – pravidla značky (logo, barvy, písmo, komponenty, maskot, hlas). **Čti jako první.**
- [`css/tokens.css`](css/tokens.css) – design tokeny (jediný zdroj barev, písma, mezer, stínů).
- [`css/components.css`](css/components.css) – hotové komponenty s prefixem `ps-`.

Nová stránka:

```html
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@400;600;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="/css/tokens.css">
<link rel="stylesheet" href="/css/components.css">
<body class="ps-body">…</body>
```

S AI asistentem (Claude Code): *„Přečti si DESIGN.md a použij css/tokens.css a css/components.css.“*

## Struktura

```
index.html            hlavní stránka
navod/                návod, jak projekt vznikl
design-system/        živá dokumentace design systému
css/                  tokens.css, components.css
img/logo.jpg          logo (kulatý výřez)
img/rodina/           rodina Spočítalových (reference postav)
img/3d/               návrhy maskota 1–40
video/                úvodní video + náhled
og.jpg                obrázek pro sdílení 1200×630
favicon.png, apple-touch-icon.png
CNAME                 vlastní doména
```

## Nasazení

Push do větve `main` → GitHub Pages zveřejní zhruba do minuty.
Doména `panspocital.cz` je ve Wedosu, DNS A/AAAA míří na GitHub Pages, `www` je CNAME na `28zdenek.github.io`.
