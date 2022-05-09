# Techniky sdílení zdrojového kódu

## Verzovací systémy (VS)

- spravují změny kódu
- uchovávají všechny změny kódu
- jsou to nástroje k usnadnění, urychlení vývoje SW

- umožňují
  - vracet se k předchozím verzím kódu
    - historie kódu
  - přehled o přidaných, odebraných, upravených částech kódu
    - kdo, kdy a co změnil
  - časovou osu práce
- **výhody**
  - jednodušší práce v týmu
  - možnost vrátit změny
    - obnovit starší verzi
  - přehledná organizace kódu
- **typy**
  - lokální VS
    - nejjednodušší
    - všechny změny jsou na jednom zařízení
  - centralizovaný VS
    - klient-server
    - repo. je na serveru
    - např. Subversion
    - nevýhodou je závislost na serveru
  - distribuovaný VS
    - každý uživatel má repo. na lokální zařízení
    - server zde slouží jako prostředník pro sdílení repozitářů
    - spolehlivější než cetralizovaný
    - např. Git, Mercurial
-

## Pojmy

- **repozitář**
  - soubor všech složek a souborů
    - které jsou pod správou VS
- **clone**
  - klonování externího repozitáře na lokální zařízení
- **commit**
  - odesílání změn repozitáře do VS
- **push**
  - odesílání změn repozitáře do externího VS
  - posílá všechny commity
    - pokud nenastal konflikt
- **fetch**
  - synchronizování commitů lokálního repo. s externím repo.
  - změny, které byli staženy, tak nejsou použity
- **pull**
  - stáhne změny a použije je
  - v gitu
    - `git pull` == `git fetch && git merge FETCH_HEAD`
- **conflict**
  - předcházení nechtěnému přepisování kódu
  - může vzniknout
    - vývojář A a B upravují stejné části kódu
    - A push a poté B push
      - je nahlášen konflikt pro B
- **diffing**
  - zobrazení rozdílů mezi růzdnémi verzemi
- **fork**
  - je to klon originálního repo., který je poté vyvíjen nezávisle
- **merge**
  - spojení větve s jinou větví
  - může zde dojít ke konfliktu

### Git

- nejpoužívanější
- Linus Torvalds
- původně zamýšleno pro asistenci při vývoji Linuxu

### Github

- web aplikace hostující repozitáře
- nabízí funkce gitu v grafickém rozhraní
- alternativy
  - Gitlab
  - Bitbucket

## Real-time sdílení kódu

- umožňuje více vývojářům pracovat na jednom souboru
- změny se synchronizují v reálném čase
- obvykle v podobě integrace s IDE
- např. Teletype (rozšíření pro IDE Atom), Visual Studio Live Share (rozšíření pro Visual Studio a Visual Studio Code)
- existují také webové aplikace
  - Codeshare.io

## Správce balíčků

- nástroj pro programovací jazyk
- umožňuje
  - import balíčků
    - import externího kódu (např. knihovny)
  - distribuce
    - vytvářet balíčky
    - balíčky mohou mít závislosti
      - balíček A protřebuje balíček B
- příklady
  - Pip
    - Python
  - Gradle
    - Java
  - Npm
    - Javascript
  - Composer
    - PHP
  - NuGet
    - C#
  - Apt
    - Linux (např. Ubuntu)
