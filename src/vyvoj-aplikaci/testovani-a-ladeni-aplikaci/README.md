# Testování a ladění aplikací

- cílem programování je vytvořit funkční program

  - splňující všechny požadavky zadání

- podmínky pro odstranění nejzávažnějších chyb
  1. pro splnění cílů je dobrý návrh aplikace
  2. znalost programovacího jazyka
  3. znalost prostředí v němž program poběží
- typy chyb (vnější)
  - hardwarové
  - softwarové
    - nedostatek volné paměti pro náš program
    - chyba v programu, se kterým náš spolupracuje
    - chyba v operačním systému
- typy chyb
  - syntaktické
    - chytré editory tyto chyby odhalí
    - špatná gramatika
      - např. `x var = 5` místo `var x = 5`
  - sémantické
    - nebo také logické chyby
    - prohřešky proti požadovanému chování programu
    - např.
      - `int i = "5"` místo `int i = 5` (nelze převést string na int)
      - chceme vrátit `true` ale vracíme `false` (prohozený operátor `==` za `!=`)
        ```js
        function isEqual(a, b) {
          return a != b;
        }
        ```
      - tento druh chyby se odchytává pomocí testů
- **ladění**
  - systematické hledání chyb pomocí krokování v debuggeru
  - debugger je program, který umožní zastavit běh programu po každé vykonání jednoho řádku programu nebo se na předem definované zarážce (breakpoint)
  - pokud je program pozastaven, lze si prohlížet či měnit obsah paměti či konktrétních proměnných, stav zásobníku, registrů atd.
  - tímto způsobem kontrolujeme zda program dělá to co jsme zamýšleli
- **testování**
  - činnost jejímž primárním cílem je odhalit chyby
  - nesledujeme běh programu, ale snažíme se program spouštět za nejrůznějších podmínek
  - testovat lze ručně, pomocí skriptů nebo pomocí sofistikovaných nástrojů
  - jakkoli náročným testováním nelze dokázat, že testovaná aplikace je zcela bez chyb (počítačové hry)
- **profilování**
  - profiler
    - program, který umí statisticky analyzovat, ve kterých funkcích tráví nejvíce času

## Dělení testů

- **jak neuspět? :confused:**
  - zapomenout, že se testuje
  - předstírat, že testeři jsou odpovědní za kvalitu, nikoli management
  - diktovat datum spuštění bez ohledu na reálná omezení projektu
  - hodnotit testera podle počtu nalezených chyb
  - oddělit vývoj a testování
- provádění testů
  - pozdě
    - problém se splněním termínů
    - málo časo na testování
  - brzo
    - nestabilní SW
    - zbytečně vynaložený čas a práce testerů

### Podle znalosti kódu

- **Black Box**
  - testujeme oproti rozhraní
  - nezajímá nás implementace
  - robustnější
    - není nutné často upravovat
- **White box**
  - strukturální testy
  - přihlížíme k implementaci
  - křehčí
    - změna implementace rozbije testy

### Podle způsobu realizace

- manuální testování
- automatizované testování

### Podle fáze testování

- **tři různé dimenze**
  - co testujeme
    - unit testy
      - ověřují se jednotky
      - testy jsou automatizované
    - integrační testy
      - testování zda jednotky spolu správně fungují
    - systémové testy
      - testování celého systému (aplikace)
  - jaký aspekt testujeme
    - funkční testy
      - testování funkčnosti, ne funkcí
        - smoke, sanity, regresní testy
    - výkonnostní / zátěžové testy
    - bezpečnostní / penetrační testy
    - testy spolehlivosti
    - testy dostupnosti
  - s jakým cílem testujeme
    - regresní testy
      - testování jestli po opravě chyby nebo přidání funkčnosti se něco nepokazilo
    - kvalifikační testy
    - akceptační testy
      - zda aplikace splňuje požadavky klienta
- důležité je dělat pozitivní i negativní testy
  - funguje co má fungovat
  - nefunguje co nemá fungovat
