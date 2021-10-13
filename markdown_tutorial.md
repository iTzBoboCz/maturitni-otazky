# Markdown Tutorial

## Nadpisy

- stejně jako v HTML, jsou i v markdown urovně 1 až 6
- nadpis vytvoříte tím, že na řádek napíšete tolik `#`, jakou úroveň chcete
  - :eyes: za `#` musí následovat mezera
  - :eyes: pod nadpisem musí být prázdná řádka

### Příklady

:heavy_check_mark:

```markdown
# H1

## H2

lorem ipsum
```

:x:

```
   # H1
     ## H2
 ####### H7
lorem ipsum
```

:warning:

```
# H1
## H2
lorem ipsum
```

## Stylizování

- **Tučně**
  - `**slovo**`
- _Kurzíva_
  - `*slovo*`
- ==Zvýrazdnění==
  - `==slovo==`
- ~~Přeškrtnutí~~
  - `~~slovo~~`
- > Citace
  - `> citace`
- Dolní~index~
  - `slovo~index~`
- Horní^index^
  - `slovo^index^`

:eyes:
**_kurzíva tučně_**

```
***kurzíva tučně***
```

## Listy

- nečíslované
  ```markdown
  - a
  - b
  - c
  ```
- číslované
  ```markdown
  1. a
  2. b
  3. c
  ```

## Odkazy

- stránka
  - `[Google](http://google.com)` => [Google](http://google.com)
- soubor
  - `![Logo SPŠ na proseku](url)` => ![Logo SPŠ na proseku](https://www.sps-prosek.cz/wp-content/themes/novy-prosek/img/logo.png =x50)
  - nastavení velikosti
    - formát: `![Logo SPŠ na proseku](url =WxH)`
    - příklady
      1.  `![Logo SPŠ na proseku](url =30x)` => šířka 30 px
      2.  `![Logo SPŠ na proseku](url =x30)` => výška 30 px
      3.  `![Logo SPŠ na proseku](url =50x30)` => šířka 50 px, výška 30 px

## Tabulky

| Věc      | Hodnota  |
| -------- | -------- |
| počítač  | 20000 Kč |
| mobil    | 10000 Kč |
| maturita | :fire:   |

```
Věc | Hodnota
-------- | -----
počítač | 20000 Kč
mobil | 10000 Kč
maturita | :fire:
```

### Zarovnání

| Sloupec 1                       |                        Sloupec 2                         |                       Sloupec 3 |
| ------------------------------- | :------------------------------------------------------: | ------------------------------: |
| doleva                          |                         na střed                         |                         doprava |
| Nunc tincidunt ante vitae massa | Lorem ipsum dolor sit amet, consectetuer adipiscing elit | Nunc tincidunt ante vitae massa |

```
| Sloupec 1 | Sloupec 2 | Sloupec 3 |
|--------|:--------:| -------------:|
| doleva | na střed | doprava |
| Nunc tincidunt ante vitae massa | Lorem ipsum dolor sit amet, consectetuer adipiscing elit |  Nunc tincidunt ante vitae massa |
```

## Poznámky pod čarou[^1]

1. `[^ID]`
2. `[^ID]: poznámka`

[^1]: Nadpis

## Zkratky

- definují se `*[ZKRATKA]: Význam`

## Ostatní

### Obsah

1. [Nadpisy](#nadpisy)
   1. [Příklady](#priklady)
2. [Stylizování](#stylizování)
3. [Poznámky pod čarou](#poznámky-pod-čarou)

```
1. [Nadpisy](#nadpisy)
	1. [Příklady](#priklady)
2. [Stylizování](#stylizování)
3. [Poznámky pod čarou](#poznámky-pod-čarou)
```
