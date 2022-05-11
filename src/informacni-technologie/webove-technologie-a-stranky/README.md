# webové technologie a stránky

## Tři pilíře

### HyperText Transmission Protocol (HTTP)

Komunikační protokol
vstupně výstupního charakteru, který rozumí adresám URL. Umožňuje browseru vyžádat si na serveru konkrétní www stránku, kterou mu server následně zašle. Protokol je bezestavový - každý požadavek je samotný. Nemá návaznost na předchozí požadavky. Protokol pracuje v systému požadavek/odpověď a používá transportní služby protokolu TCP. Žádosti klienta mají formu jednoduchých příkazů – metod: GET (pro poskytnutí stránky), HEAD (požadavek na zaslání hlavičky stránky), POST (posílá data na server).

### Hypertext Markup Language (HTML)

### Adresovací systém URL (Uniform Resource Locator)

Používá se pro přesnou identifikaci dokumentů na internetu. Diakritika se může používat - pokud to podporuje hosting a služby tam. SEO friendly a user friedly URL.

URL kromě domény, https, ... může obsahovat i:

- jméno a heslo: autentizace
- číslo portu
- cesta ke stránce ejkej ej struktura adresářů
- koncovka stránky
- ID elementu (kotva): odkaz na přesné místo na stránce

## HTML - Hypertext Markup Language

Značkovací jazyk vkládá do textu dokumentu další informace o vlastním textu, kombinuje text a informaci o textu, existuje od roku 1990 a nejnovější verze HTML5. . Značkovací jazyky se využívají především pro přenos informací (dat) mezi počítači. Jsou dobře přenosné mezi různými operačními systémy (nejsou na žádném OS závislé). Založen na DOM (Document Object Model),

File API

- Velikost nahrávaného souboru není omezena serverem (soubor se automaticky rozdělí a opět složí)
- umožňuje jak nahrávat neomezené množství souborů najednou (dříve to bylo možné pouze pomocí pluginu Flash)
  Fullscreen API
- Např. při přehrávání videí na YouTube (zvětšení na celou obrazovku dříve řešil Flash)
  Geolocation API
  Media API (dříve řešil Flash)
  TextTrack API (umožňuje připojit k přehrávaným multimédiím titulky)
  Podpora SVG (např. loga ve vektorové grafice)

### Struktura stránky

Tvořeno párovými, nepárovými tagy. Každý tag má určené vlastnosti/atributy. Např. (`<a href=”odkaz” target=”_blank”>`)

- `<!DOCTYPE html>` : začátek stránky, bude následovat dokument typu HTML
- `<html></html>` : v tom je tag head a body
- `<head></head>` : určen pro metadata, klíčová slova, titulek, odkazy na styly, import, apod.
- `<body></body>` : všechen obsah na stránce

## CSS

Stylování stránky, aby stránka nějak vypadala. Od roku 1996, aktuální verze CSS3, dá se pomocí ním ovlivňovat tagy, id, classy, něco v něčem/subclassy, ...
CSS jde buď naincludovat v `<head>` tagu z externího souboru, popřípadě ho psát jako atribut/vlastnost style do určitého tagu nebo do tagu `<style>`.
Existují různé knihovny a frameworky: Bootstrap, Materialize, Tailwind, ...
Vytvořené CSS se následně kompiluje do minifikovaných souboru z důvodu efektivity webu (rychlost, data).

Díky @media v CSSku dnes můžeme jednodušše tvořit responzivní design.

- @media (min-width: 600px) { body { background: black } } = pokud screen size bude minimálně 600px, tak bude pozadí černé

### Preprocesory

Preprocesory mají zjednodušovat, zefektivňovat a zrychlovat práci s CSS. Přidávají do CSS logiku, proměnné, matematické operace, vnořování, dědičnost, ...
Napsaný kód v preprocesoru se následně compiluje do standardního CSS souboru.

K nejznámnějším patří například Sass, LESS, Stylus, PostCSS, ...

## JavaScript

Skriptovací jazyk, OOP, od roku 1995, s Javou nemá nic společného, autor Brendan Eich. Dá se využít na straně klienta (oživit např. statické weby), tak pomocí (např. Node.JS) pracovat i na straně serveru. S pomocí elektronu též může být překompilovaný do desktopové aplikace (např. Discord) nebo na mobil (Android i iOS).

Více na toto téma [zde](../web-javascript).

## PHP - Hypertext Preprocessor

Skriptovací programovací jazyk, lze provozovat jak na straně severu, tak i v kopilované formě na vývoj konzolových a desktopových aplikací. PHP pracuje na serveru a prohlížeč dostává až výsledek. Aktuálně verze 8. Nejrozšířenější scriptovací jazyk pro web (přes 79%). Nejznámějšími PHP projekty je Wordpress, Wikipedie, Facebook (Facebook používá PHP transformované do C++ pomocí aplikace HipHop for PHP a to především kvůli vyšší rychlosti). I díky Wordpressu, který je celosvětově nejpoužívanější CMS systém a je založený na PHP, se tento jazyk těší takové oblibě.

## Další ...

Python, C#, Ruby On Rails, Java, ...

## Redakční systémy - CMS systémy (Content Management System)

I méně pokročilý uživatel si může vytvořit vlastní webovou stránku pomocí redakčního systému a následně si ji i spravovat. Má na výběr několik šablon, které může v interaktivním prostředí upravit (např. texty, barvy, obrázky atd.). Výhodou je, že člověk nemusí se umět programovat a vše si nakliká. Nevýhoda je výkon, optimalizace, SEO a další vlastnosti stránek.
Nejznámější redakční systémy: Wordpress, Joomla, Drupal, Shoptet, Wix, Webnode, ...

Wix, squarespace

## Provoz WWW stránek

Pokud si chceme založit webové stránky, musíme si nejdřív koupit hosting a zaplatit doménu u poskytovatele (např. Wedos). Pro ČR je správce domén CZ.NIC.

Lze sehnat i doménu zdarma (například .tk)). Pomocí FTP (File Transfer Protocol) po té nahrajete své webové stránky na hosting.
