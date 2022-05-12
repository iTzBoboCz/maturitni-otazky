# Architektury procesorů
## Instrukční sady
**Typy**
### RISC
- Reduced Instruction Set Computing
- Architektura mikroprocesorů s redukovanou instrukční sadou
- **Zaměřeno na:**
    - Jednoduchost -> není zde instrukce pro násobení (realizováno softwarově pomocí instrukcí sčítání a bitových posunů)
    - Vysoce optimalizované sady strojových instrukcí
- Architektura load-store - celkový počet instrukcí RISC procesoru může být paradoxně vyšší, než u jiných architektur
- Instrukce mají pevně danou délku
- Vznik v 70. letech kvůli zjištění, že tehdejší počítačové programy nevyužívaly zdaleka všechny dostupné instrukce 
- Zástupci: ARM, MIPS, AMD Am29000, ARC, Atmel AVR, PA-RISC, Power (včetně PowerPC), SuperH, SPARC, DEC Alpha

### CISC
- Complex Instruction Set Computing
- Jedná se o opak RISC
- Kompletní soubor instrukcí - snaží se mít, co největší počet instrukcí s různými operacemi (i přestože je možné je nahradit jednoduššími operacemi) -> čím bohatější, tím výkonnější
- Později se ukázalo jako ne příliš efektivní
- Instrukce měly proměnlivou délku i dobu vykonání

**Příklady**
### x86
- CISC
- Vyvinuto společností Intel
- Pro 16, 32 i 64 bitové systémy (64 bitová adresace)
- Příklady rozšíření: x86-64, x87, IA-32, MMX
- V dnešní době převládá ve stolních počítačích, laptopech i herních konzolích

### ARM
- RISC
- Advanced RISC Machines
- Vyvíjí společnost Arm Ltd. a licencuje ostatním výrobcům
- Pro 32 a 64 bitové systémy
- Příklady rozšíření: SVE, SVE2, Neon
- Díky nízké ceně a spotřebě (tudíž i nižší produkce tepla) jsou procesory s instrukční architekturou ARM používány hlavně chytrých telefonech, laptopech a jiných „embedded“ systémech

### MIPS (starší)
- RISC
- Microprocessor without Interlocked Pipelined Stages
- Nejprve 32 bitové, později pro 64 bitové systémy
- Příklady rozšíření: MDMX, MIPS-3D
- Používáno ve starších konzolích (Nintendo 64, PlayStation, PlayStation 2) a routerech

## Procesory
### Skalární architektura
- Procesory Intel - 8086, 80286, 80386, 80486
- Více funkčních bloků, které fungují samostatně (procesor z více částí)
- Je zde tedy možné zprácování různých částí instrukcí najednou (jsou rozděleny)
- **Zpracování instrukce:**
    1. Výpočet adresy místa v operační paměti
    2. Načtení instrukce z dané adresy v operační paměti
    3. Dekódování instrukce (nalezení mikrokódu reprezentující instrukci v paměti ROM)
    4. Provedení výpočtů v ALU / FPU
    5. Zápis výsledku do registrů

### Superskalární architektura
- Procesory Intel - Pentium, Pentium MMX, Pentium II, Pentium III, odlehčené verze Celeron
- Možnost zpracování několika instrukcí v jednom instrukčním řetězci (pipeline) zároveň
- Je zde více prováděcích jednotek (převážně ALU) v jednom jádře procesoru
    - V jednom taktu může tedy být za určitých podmínek dokončeno více instrukcí -> superpipelining
    - Tyto instrukce na sobě nesmí být závislé
- O paralelním provádění operací rozhoduje radič procesoru

### Architektura NetBurst
- Procesory Intel - Pentium 4, Pentium D, Xeon (serverové procesory) - rok 2000
- Spolehá na vysoké taktovací frekvence -> velký příkon a tedy velké ztrátové teplo (TDP - Thermal Design Power)
- **HyperThreading technologie**
    - Myšlenka: jeden fyzický procesor bude pracovat jako dva logické procesory
    - Jde o zdvojení jednotek, které uchovávají aktuální stav výpočtů - tedy registrů -> ostatní součásti (ALU/FPU, prediktory a cache paměti) jsou sdílené
- **XD (_eXecute Disable_) bit technologie**
    - Obrana proti útokům červů a virů, které se snaží o přetečení paměťového zásobníku
- **SpeedStep technologie**
    - Upravení taktovací frekvence jádra procesoru dle potřeb aplikace -> snížení spotřeby elektřiny a snižení jeho produkovaného tepla
- **Rapid Execution Engine**
    - Procesor má celkem 3 ALU, z toho 2 pro jednoduché operace -> pracují na dvojnásobné frekvenci než jádro procesoru -> možné provést až 4 instrukce za jeden strojový cyklus
- Přidána tepelná ochrana (pomocí TCC - Thermal Control Circuit)

### Architektura Core
- Procesory Intel - Core Duo, Core 2 Duo, Core 2 Quad, Core 2 Extreme - rok 2006
- Vícejádrové procesory
- Možnost zpracování instrukcí paralelně -> procesor může řešit více úloh zároveň
- Plná podpora 64 bitových OS (obsahuje plně 64 bitové ALU)
- **Wide Dynamic Excution**
    - Zpracování více instrukcí během jednoho taktu
    - 4 dekodéry instrukcí (3 na jednoduché operace, 1 na složitější operace)
    - Macro-Fusion - tato technika se snaží o dekódování dvou instrukcí na jednu mikroinstrukci
    - MicroOps-Fusion - umožňuje sloučit dvě mikroinstrukce, které jsou těsně spjaty do jedné (např. určení adresy paměťového místa + uložení dat na toto místo)
- **Inteligent Power Capability**
    - Odpojuje nevyužité části procesoru od napájení + řídí otáčku ventilátorů
- **Smart Memory Access**
    - Slouží k optimalizaci pořadí instrukcí
    - Zdokonalená technika pro předvídání (predikci) dat
- **Advanced Smart Cache**
    - Dynamické přidělování kapacity pro každé jádro
- HyperThreading z důvodu složitosti odstraňen

### Architektura Nehalem
- Procesory Intel - Core i7, Core i5, Core i3 - rok 2008
- Vícejádrové procesory s částečnou nebo plnou intergrací severního můstku do procesoru
- **Integrovaný řadič paměti**
    - Přímo v pouzdře procesoru
    - Rychlá výměna dat mezi operační pamětí a výpočetními jednotkami procesoru
    - Víceprocesorové stanice (např. servery) -> každý procesor má vlastní paměťový prostor
- **QPI (_QuickPath Interconnect_)**
    - Vysokorychlostní procesorová sběrnice
    - Umožňuje navíc komunikace mezi procesory u víceprocesorových systémů
    - Náhrada stávající sběrnice FSB
    - U AMD procesorů sběrnice HyperTransport
- HyperThreading opět implementován -> ze 4 fyzických jader až 8 virtuálních (nové označení Simultaneous MultiThreading (SMT))
- **Režim Turbo Boost**
    - Hlídání TDP procesoru a vytížení jader
    - Pro úsporu může jádra vypínat

### Architektura Sandy Bridge
- Druhá generace procesorů Core - Core i7, Core i5, Core i3 - 2011
- 32 nm technologie
- Severní můstek plně integrován do procesoru
    - System Agent (SA)
    - GPU - grafický procesor -> CPU + GPU = APU (Accelerated Processing Unit)
        - Intel HD Graphics 2000 (resp. 3000)
        - Přímý přístup do L3 cache
        - Možnost přizpůsobení frekvence a výkonu dle potřeby
        - Vlastní napájení
    - Operační paměti DDR3 (řadič)
    - Řadič sběrnice PCI-Express x16 v2.0
    - PCU (Power Control Unit) - řízení napájení, frekvence a tepelný monitoring procesoru
- Vnitřní kruhová sběrnice (ring bus) -> propojení jader, GPU a obvodů SA
- Turbo Boost 2.0

### Architektura Ivy Bridge
- Třetí generace procesorů Core - Core i7, Core i5, Core i3 - 2012
- 22 nm technologie