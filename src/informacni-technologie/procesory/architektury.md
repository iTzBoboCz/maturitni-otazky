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
- Pro 16, 32 i 64 bitové systémy
- Příklady rozšíření: x86-64, x87, IA-32, MMX
- V dnešní době převládá ve stolních počítačích, laptopech i herních konzolích

### ARM
- RISC
- Advanced RISC Machines
- Vyvíjí společnost Arm Ltd. a licencuje ostatním výrobcům
- Pro 32 a 64 bitové systémy
- Příklady rozšíření: SVE, SVE2, Neon
- Díky nízké ceně a spotřebě (tudíž i nižší produkce tepla) jsou procesory s instrukční architekturou ARM používány hlavně chytrých telefonech, laptopech a jiných „embedded“ systémech

## Procesory
**Typy**
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

**Příklady**
### Architektura NetBurst
- Procesory Intel - Pentium 4, Pentium D, Xeon (serverové procesory)
- Spolehá na vysoké taktovací frekvence