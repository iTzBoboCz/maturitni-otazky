# OOP

- objektově orientované programování
- je to programovací paradigma
  - existuje mnoho další paradigmat (POP, FOP, DOP, ...)
  - paradigma
    - způsob, jak třídit programovací jazyky na základě jejich vlastností
- jedná se o filozofii a způsob myšlení, designu a implementace, kde klademe důraz na znovupoužitel­nost
- snažíme se nasimulovat realitu tak, jak ji jsme zvyklí vnímat
- oproti procedurálnímu programování nespočívá jen v psaní kódu jiným způsobem, ale v uvažuvání jiným způsobem
- cílem je vytvářet **malé, relativně samostatné** a v různých aplikacích opakovaně použitelné jednotky

- **výhody**
  - snažší a rychlejší výboj
  - snadnější údržba
  - menší chybovost
- **nevýhody**
  - správa objektů zabare určité systémové prostředky

## Pojmy

- **objekt**
  - soběstačná entita
  - obsahuje vlastnosti
    - atributy a metody (schopnosti)
- **třída**
  - vzor, podle kterého se objekty vytvářejí
  - definuje vlastnosti
  - udáva jen jaké vlastnosti bude mít každý objekt dané třídy
- **instance**
  - konkrétní objekt určité třídy
- **vlastnosti třídy**
  - statické vlastnosti
- **dědění**
  - základní vlastnost OOP
  - slouží k tvoření nových datových struktur na základě starých
- **polymorgismus**
  - umožňuje přepsat/implementovat metodu u každé podtřídy
  - díky tomuto lze volat metodu různých podtříd a nemusí nás zajímat o jakou se jedná
- **zapouzdření**
  - umožňuje znepřístupnit/skrýt některé vlastnosti třídy tak, aby zůstaly použitelné jen pro třídu zevnitř
  - public, private, protected
- **abstraktní metoda**
  - je definovaná ve třídě
  - podtřídy musí tuto třídu implementovat

## Další paradigma

- **POP**
  - procedurálně orientované programování
  - program je rozdělen do menších celků (funkcí)
  - program musí obsahovat main funkci
  - např. C, Pascal, Fortran, Rust, ...
- **FOP**
  - funkcionální programování
  - snaží se zabránit měnění stavu a mutaci dat
    - neexistuje
      - deklarace proměnných
      - cykly
  - funkce můžou být parametry i vraceny
  - funkce musí vždy vracet na stejné vstupy stejný výsledek
  - založeno na výrazech
  - např. Haskell, Dart, Scala, F#, ...
- **DOP**
  - v OOP se zaměřujeme na jediný objekt
  - zde se zaměřujeme jak data uchovat a zpracovat
  - např. SQL
