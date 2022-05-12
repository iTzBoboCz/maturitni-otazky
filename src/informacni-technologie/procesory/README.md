# Procesory
- CPU (Central Processing Unit)
- Procesor je řídící jednotkou každého počítače
- Velmi složitý číslicový integrovaný obvod, který je řízen pomocí instrukcí uložených v operační paměti

## Parametry

### Jednotky pro rychlost
- MIPS - Milion instrukcí za sekundu
- MOPS - Milion operací za sekundu
- FLOPS - Počet operací v pohyblivé řádové čárce za sekundu

### Základy
- **Rychlost jádra** - uváděna v počtu operací provedených za sekundu (MIPS)
- **Výrobní proces** - uvádí se velikost tranzistorů v nm (nanometr)
- **Počet jader** - běžně 1-16 jader
- **Počet vláken** - rozdělení prostředků v jádru pro více programů
- **Efektivita strojového kódu** - uvádí se počet instrukcí potřebných pro provádění běžných operací např. počet Dhrystone na MIPS
- **Výkon FPU (Floating-Point Unit)**
    - Matematický koprocesor, využívá se k vykonávání operací s čísly s pohyblivou řádovou čárkou 
    - Přítomnost FPU/počet základních operací v jednoduché nebo dvojnásobné přesnosti, které zvládne provést jednotka FPU
    - Výkon uváděn v MFLOPS (megaflops) až jednotky TFLOPS (teraflops), podle architektury a počtu FPU 
- **Cache** - kapacita integrované paměti v CPU, uvádí se v MiB (většinou 4-12 MiB)
- **Velikost adresovatelné paměti**
    - Velikost externí paměti, kterou je procesor schopen přímo používat
    - U 32 bitových CPU řádově 4 GiB
- **Šířka externí datové sběrnice**
    - Maximální počet bitů, které je možné během jedné operace přenést z/do čipu
    - Bit 8 – 128

- ## Dělení procesorů
- **CPU (_Central Processing Unit_)**
    - Otevřenost procesoru (všechny periferie musí být připojeny externě)
    - Vysoká cena, výkon, spotřeba a ztrátový výkon, rozměry
- **MCU (_Micro Controller Unit_)**
    - Zmatek ve značení kvůli výrobcům
    - Výkon není nejdůležitější
    - Nízká cena, spotřeba (jednotky mikroampérů - 500 µA), rozměry
    - Malá možnost rozšíření
    - Průkopník: 8 bitový procesor Intel i8051
    - 16 bitový technologický procesor Siemens SAB 80C166 (integroval A/D převodníky, komunikační linky a masivní systém čítačů/časovačů/přerušení)
- **DSP (_Digital Signal Processor_)**
    - Určeny zejména pro zpracování signálů
    - Vysoká rychlost zpracování číslicových dat
    - Velmi rychlé matematické operace 
    - Schopnost zpracovávat velké objemy dat
    - Součástí každého procesoru DSP by měl být rychlý analogově/digitální a digitálně/analogový převodník
    - Velmi náročné na přístupovou rychlost pamětí, které používají (práce s velkým objemem dat)
    - Využití ve zvukových a grafických kartách (zajišťuje zvukové efekty a kompresi zvuku a obrazu)
    - Využití u HDD u čtecích hlav jako D/A převodník -> rychlejší čtení, vyšší integrace