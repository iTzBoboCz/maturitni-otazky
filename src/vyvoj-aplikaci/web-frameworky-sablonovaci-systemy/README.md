# Web - Frameworky, šablonovací systémy

Framework je softwarová struktura obsahující často používané součásti, a tím urychlí a zjednoduší vývoj.

Šablonovací systém je část webové aplikace, která se stará o tzv. prezentační vrstvu aplikace. Ta uživateli vykresluje danou stránku webu s využitím předem připravených šablon. Do nich při vykreslování plní data, která předtím získala jiná část aplikace a šablonovacímu systému je předala.

Kontrolery (Controllers), řízení - Kontroler je část, se kterou komunikuje uživatel. Předá jí parametry a ona mu vrátí data (např. HTML stránku). Kontroler typicky parametry předá modelům, od kterých získá data. Tato data předá pohledům (šablonám), které data začlení do nějakého HTML kódu. Tento HTML kód pošle kontroler uživateli do prohlížeče. Funguje tedy jako takový prostředník.
Modely (Models), logika - Obsahují logiku aplikace, jako např. práci s databází nebo výpočty. Každá datová entita má většinou právě svůj model (uživatel, článek, komentář, ...).
Pohledy (Views), výstup - Obsahují Blade šablony (s HTML kódem). Blade je šablonovací systém, který na rozdíl od ostatních systémů nezakazuje používání PHP kódu v pohledu, tudíž neslouží pouze pro vkládání proměnných do HTML kódu. Blade používá speciální syntaxi, jež je poté převedena na normální PHP kód, a zároveň tento vygenerovaný pohled je následně uložen do mezipaměti pro příští použití kvůli rychlejšímu načítání (pokud není daný pohled modifikován).

zde obrázek: https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/1024px-MVC-Process.svg.png
a zde: https://www.itnetwork.cz/images/13932/laravel/cyklus-stranky-diagram.png

Výhodou frameworku je též bezpečnost. Většina moderních frameworků se pravidelně aktualizuje. Většina je navržena objektově.

## PHP

### Nette
Český framework (David Grudla). Princip ModelViewPresenter (Presenter ~ Controller). Vestavěný router, DI container, Latte (šablonovací systém)

-	Česká komunita, málo rozšířený mimo ČR
-	Stále udržovaný (podpora PHP 8)
-	Osvědčený (použito firmami jako DHL, ESET, Slevomat…)
-	Rozděleno na spoustu individuálních balíčků, spousta 3rd party knihoven (ORM databázová abstrakce, výpis tabulek se stránkováním a filtry, atd.)

###  Laravel

Open source php framework, MVC model, MIT licence. Populární hlavně kvůli -> opírá se o velikány typu Symfony, Composer(nástroj pro správu knihoven a jiných zdrojů v PHP), Eloquent ORM (nástroj v Laravelu pro práci s db) a Blade (šablonovací systém).

Lavarel má mnoho funkcí, zde některé z nich:
- autentizace – kontrola přístupu uživatelů
- routování – správa, směrování a zpracování dotazů na jednom místě
- databáze – veškeré nástroje pro komunikaci s databází
- mail – posílání emailu s přílohami a vloženými soubory
- sessions – zastává veškeré agendy okolo sessions
-	request validation, error handling (např. formuláře)
-	csrf token pro safu odesílání dat (formuláře)
- caching – kešování používaných dat

### Symfony

PHP framework, vycházející z MVC, opensource, MIT licence, některé jeho součásti využívají nástroje jako Doctrine, Composer, Drupal, Joomla nebo PrestaShop.

- Projekt je standardně rozdělen do jednotlivých aplikací, ty se dále dělí na moduly a ty na jednotlivé akce.
-	Je řešen modulárně (lze instalovat jen takové komponenty, které skutečně potřebujeme = snížení velikosti projektu)
- Vytváření projektů, aplikací, modulů, mnohá nastavení a údržba se provádí právě přes příkazový řádek (může být problém na sdílených hostinzích).

## Javascript

### jQuery

Framework, nebo spíše knihovna pro JavaScript
-	Zjednodušuje například manipulaci s HTML elementy, AJAX dotazy a animace
-	V dřívějších dobách byla také užitečná k tomu, aby web ve všech prohlížečích fungoval stejně - různé prohlížeče tehdy často různě spouštěly JavaScript
-	Existuje pro ni hodně pluginů pro jednoduché vytváření HTML elementů
-	V dnešní době se od této knihovny postupně ustupuje - jednodušší věci už jdou jednoduše dělat i v čistém JavaScriptu, a pro složitější věci se používají spíše rozsáhlejší frameworky, jako například React, Angular nebo Vue.

### React

Vyvíjený Facebookem (Mety) + komunitou, optimální pro práci s rychle se měnícími daty, opensource, pro tvorbu uživatelského rozhraní.
Na rozdíl od různých kompletních frameworků (např. Angular) se tedy soustředí na jednu specifickou oblast. Z hlediska klasické MVC architektury tvoří pouze view.

-	základem jsou tzv. komponenty (components): znovupoužitelné HTML elementy se zapouzdřenou funkcionalitou, jejichž skládáním vzniká UI aplikace
  -	vlastnosti (props)
  - vnitřní stav (state)
-	tento deklarativní způsob práce s daty aplikace vede k více předvídatelnému chování i lehčímu ladění
-	využívá se např. pro tvorbu tzv. single-page aplikací
-	vykreslování webových stránek na straně klienta (client-side rendering)
-	s využitím Next.JS frameworku umožňuje i server-side rendering

### Vue

Určený nejenom pro UI, zaměřuje se hlavně na deklarativní renderování a skládání komponent. Komplexní funkcionalita pro web. aplikaci je řešeno formou balíčků respektive jejich přidání. Hlavní je jednoduchost, rychlost (minifikovaná verze má pouze kolem 20KB) a proto má Vue vlastní systém balíčků a routingu (dovoluje psát dynamický web a dosazovat si proměnné do HTML, například z databáze či API, routovat URL adresy a mnohem více). Narozdíl od Reactu, můžete napsat normální HTML a pak mu "dát život" pomocí Vue. Může se psát v JavaScriptu, ale má také nativní podporu pro TypeScript (nadstavba pro JS).

## CSS

### Bootstrap
-	Knihovna hotových a nastylovaných HTML komponent pro frontend (používat rovnou, nebo ještě upravit pomocí CSS)
-	Buttony, navigační lišty, prvky formulářů, karty, modální okna, ...
-	Také obsahuje systém grid, který dovoluje jednoduše dělat web responzivni

### Tailwind

Zatímco Bootstrap je "component-first", Tailwind je naopak "utility-first". Kompletní komponenty si člověk vytvoří sám nebo si je naimportuje externě. Je zejména pro lidi, kteří rozumí CSS a dělají si vlastní designy.

## Python

### Django - (po jazzovém kytaristovi Django Reinhardtovi)

Opensource Python framework, MVC model, BSD licence, snadné vytvoření komplexních, databází řízení web. aplikací. Zaměřuje se na znovupoužitelnost a propojitelnost komponent, rychlý vývoj, vždy v duchu „DRY“ (Don’t Repeat Yourself).

### Flask

-	micro framework
-	modulární

## Java

Pom.xml (Project Object Model)
-	Obdoba composer.json v PHP
-	V Javě se projekty nazývají artefakty
-	Pom.xml obsahuje model našeho artefaktu včetně závislostí na jiné artefakty
-	Obsahuje informace o buildu, pluginech, ...
Spring
-	Framework pro jednoduchý vývoj webových aplikací v Javě
-	Pracuje na principu MVC

## C#

### ASP.NET

Sada knihoven (řešící obvyklé problémy - bezpečnost, autentizace uživatele, ...), klient-server, program běžící na serveru - výsledek zaslaná web. stránku. Je nástupcem technologie ASP (Active Server Pages) a přímým konkurentem JSP (Java Server Pages).
Stránku můžeme vytvářet buď pomocí/jsou to odnože od ASP.NET:
- ASP.NET WebForms (obdoba WinForms)
- ASP.NET MVC
- **ASP.NET Core** - nejpopulárnější, nejnovější, nahrazuje předchozí zastaralé verze, zabudovaný MVC model, ...

#Sablonovaci systemy

Je to něco jako to, co jsme dělali ve druháku s Vácou na webech. Šablona, do které se nahází data.

## Latte

Šablonovací systém pro PHP, který je zaměřený primárně na bezpečnost. Používá k tomu mimo jiné automatické kontextově sensitivní escapování (Context-Aware Escaping), které rozezná, ve které části dokumentu se výpis dat nachází, a podle toho zvolí správnou escapovací funkci. Escapování je automatické, aby se předešlo chybám vzniklým proto, že na ně programátor zapomene.

## Twig
Šablonový systém pro programovací jazyk PHP. Svou syntaxi odvozuje od systémů Jinja a Django, opensource, BSD licence. Je distribuován také jako součást softwaru Symfony. Od své verze 8 vydané v roce 2015 jej používá redakční systém Drupal.
