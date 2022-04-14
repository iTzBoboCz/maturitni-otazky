<h1 align="center">Maturitní otázky</h1>
<h3 align="center">Střední průmyslová škola na Proseku, obor IT</h3>

---

<p align="center">
  <a href="https://github.com/iTzBoboCz/galera-web">
    <img alt="GPL 3.0 License" src="https://img.shields.io/github/license/iTzBoboCz/maturitni-otazky.svg"/>
  </a>
</p>

:rocket: Tento projekt slouží ke spolupráci mezi žáky 4ITA ve společné cestě za :hear_no_evil:maturitou:hear_no_evil:.

Vygenerovanou stránku si můžete prohlédnout [zde](https://itzbobocz.github.io/maturitni-otazky/).

Kniha se generuje ze souborů ve formátu Markdown. Tutoriál na práci s ním naleznete [zde](https://github.com/iTzBoboCz/maturitni-otazky/blob/main/markdown-tutorial.md).

## Jak začít?

Tento repozitář obsahuje nakonfigurované nástroje, které usnadňují práci s formátováním jak textu, tak i názvů commitů.

Pokud tyto nástroje chcete použít, je nutné mít nainstalovaný [Node 16](https://nodejs.org).
Poté už jen ve složce projektu spustíte:

```
# nainstaluje/aktualizuje moduly
$ npm install

# nastaví hooky
$ npm run prepare
```

---

### Commitlint

Kvůli orientaci v git historii vznikla [specifikace](https://www.conventionalcommits.org/en/v1.0.0/) pro názvy commitů. Podle ní by všechny commity měly mít v názvu předponu s typem úkonu, který vykonáváme.

#### Formát

:heavy_check_mark: typ: zprava
:crown: typ(nazev-kapitoly): zprava

#### Příklady

:x: toto je zmena kterou jsem udelal o volne hodine
:heavy_check_mark: feat: pridano rozrazeni typu monitoru # feat = něco nového (feature)
:heavy_check_mark: fix: zmena nazvu souboru # oprava/úprava
:heavy_check_mark: fix: upraveny uvod grafickych karet
:crown: fix(graficke-karty): upraveny uvod

_Pro více informací můžete navštívit i [tuto ukázku](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)_

### Prettier

Slouží k formátování kódu. Spouští se při každém uložení souboru.

### Husky

Hooky automaticky kontrolují soubory před tím, než je commitnete. Slouží k odchycení :bug:.

## Build

Tento krok **není nutný**, protože se stránka s maturitními otázkami aktualizuje sama při každém pushnutí.

Před instalací knihovny mdbook je nutné mít nainstalovaný Rust, více informací [zde](https://www.rust-lang.org/tools/install).

```
# install dependencies
$ cargo install mdbook

# build
$ mdbook build
```
