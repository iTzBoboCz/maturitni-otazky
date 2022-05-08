# Kybernetické útoky a hrozby

- [Účel útoků](#Účel-útoků)

- [Malware](#malware)

- [Typy útoků](#typy-útoků)

- [Útočné strategie](#Útočné-strategie)

## Pojmy

- **kyberprostor** - prostor v rámci počítačové sítě
- **kyberkriminalita** - trestné činy v kyberprotoru
- **hacker** - snaží se najít a využít slabých míst v informačních systémech
  - white hat (etický hacker)
    - slabá místa nahlašuje
    - pomáhá s opravením slabých míst
  - black hat
    - bez oprávnění majitele
    - mají zlé úmysly
  - gray hat
    - mix předcházejících
    - nemají zlé úmysly
    - nelegální
    - díry v systémech nahlašují vlastníkovi
      - někdy žádají o menší částku peněz za opravení této díry

## Účel útoků

Kybernetické útoky mají obvykle dva cíle. Buď získat něco (informace,
peníze), nebo cíl poškodit (zničit data, přerušit komunikaci...). Toho
lze dosáhnout mnoha způsoby.

## Malware

jakýkoliv škodlivý kód, který má za cíl učinit škodu

### Spyware

malware určený ke sledování uživatele. Obvykle sleduje aktivitu,
stisknuté klávesy a sběr dat. Díky tomu se k útočníkovi mohou dostat
vaše hesla nebo cokoliv, co zadáváte do pc. Obvykle také upravuje
nastavení bezpečnosti, aby nebyl odhalen. Do počítače se nejčastěji
dostává jako součást legitimního software nebo jako součást trojanu.

### Adware

malware určený k zobrazování reklam. Z toho má pak utočník peněžní zisk,
bězně se vyskytuje společně se spyware.

### Ransomware

od slova ransom (výkupné). Zašifruje disk počítače a za úplatu jej opět
odemkne. Obvykle využívá systémové zranitelnosti pro uzamčení systému,
šíří se stažením nebo náhodnou flashkou (viz ta nemocnice v česku).

Ransomware je velmi efektivní pro velké budovy, protože pokud se dostne
do vnitřní sítě, tak se dokáže snadno šířit (pokud síť nění dobře
zabepečená). Pokud máte napříkad nemocnici, která je najednou bez
počítačů, tak jste poměrně v háji a začnete zvažovat zaplacení...
zašifrovaný disk lze jen těžko odšifrovat, takže jediná záchrana je
obnovit zálohy, nebo najít chybu v samotném viru pomocí reverzního
inženýrství (to je ještě težší).

### Scareware

malware, který má za cíl donutit uživatele vykonat akci na bázi strachu

- viz reklamy na netu ("váš systém je nakažen, klikněte zde pro
  odstranění problému"). Po kliknutí se systém nakazí jiným malware...

Pro lidi, kteří nejsou poprvé u počítače to není moc velká hrozba, ale
pokud jste důchodyně, nebo tak podobně, tak je velká šace, že tento typ
útoku bude efektivní.

### Bot

malware určený k automatickému vykonávání určených akcí. Počítači je
jinak neškodný, ale při aktivaci může vykonávat jisté online akce.
Obvykle je součástí botnetu (síť několika botů). Pak slouží například
pro vykonání DDoS útoku.

### Virus

škodlivý kód, který je obvykle součástí jiné spustitelné aplikace
(cracknuté hry například). [Pro spuštění potřebuje akci uživatele]{.ul}.
Viry mohou být neškodné (mohou zobrazovat obrázky nebo cokoliv jiného
pro vystrašení - trolling) nebo mohou vážně poškodit OS, smazat data,
atp. Viry mohou mutovat, aby se vyhnuli odhalení. Většina se do pc
dostane stažením nelegální kopie sw, nebo pomocí přenosného média (CD,
Flash disk...)

### Červ

malware, který se sám replikuje nezávysle na uživateli, využívá
zranitelnosti sítě pro šíření. Po nakažení se rychle šíří po síti dál.
Všechny červi mají podobné vzorce chování - povolení zranitelnosti,
cestu pro zreplikování a všechny obsahují nějaký payload.

červi jsou zodpovědní za jedny z nejvíce rozšířených útoků. například
code red (2001) nakazil za 19h přes 300k serverů (viz obrázek)

![](media/image1.png){width="6.267716535433071in"
height="3.3472222222222223in"}

### Rootkit

malware navržený s cílem vytvořit backdoor v systému. (backdoor = skrytý
vstup do systému, například otevřené porty a sw pro vzdálený přístup).
Většina rootkitů využívá zranitelnosti

### Trojan

malware maskující se za jiný program. Svoje činnosti maskuje za činnosti
vyžádané (například instalace aplikace). Využívá jemu přidělených práv,
když uživatel spustí jeho kód. Od viru se liší tím, že se váže na
nespustitelné soubory.

## Typy útoků

### Social Engineering

Přistupový útok s cílem zmanipulovat uživatele, aby provedl určitou akci. Může jít o sdělení hesla, udělení přístupu, nebo dokonce poskytnutí platebních údajů.

#### Příklady

- **telefonát zaměstnanci** s přístupem do systému

  > „Jedná se o kritickou situaci, potřebuju heslo...“

- **email od supportu (pretexting)** na steamu
  (proto je v těch chatech nahoře ta notifikace, ať nikomu nedáváte heslo)

  > „Máme problém s vaším účtem, můžete nám dát přihlašovací údaje, abychom se na to podívali?“

- **fyzický vstup (tailgating)**, social engineering se vztahuje i na fyzická místa, můžete požádat někoho, ať jde třeba zkontrolovat serverovnu, a budete ho tam sledovat…

- **něco za něco (quid pro quo)** - přijde vám mail, že princ Habíbo u vás potřebuje schovat 50 kg diamantů, ale potřebuje peníze na dopravu…

Sociální inženýrství je v dnešní době nejsilnější/nejefektivnější způsob útoků. Většina systémů je dobře zabezpečena a vyžadují velkou dovednost, aby jste se do nich dostali, nicméně využít hlouposti lidí je děsně jednoduché.

#### Phishing

druh sociálního inženýrství. Princip je odesílání emailu a vydávání se za něhoko jiného. Cílem může být nainstalování software nebo sdílení osobních informací.

##### Spear phishing

lepší verze phishingu. Je cílená na konkrétní osobu, útok probíhá
prvotním zjišťováním informací o určené osobě. Poté útočník využije tyto
informace a vytvoří útok specificky pro tuto osobu. Příklad - cíl se
zajímá o auta, tak se útočník přidá do stejné FB skupiny a pošle cíli
nabídku na prodej auta s odkazem. Odkaz povede na stránku obsahující
zavirovaný obrázek... to povede k nakažení cíle.

##### Baiting

sociální inženýrství soustředící se na nálákání cíle a vzbuzení jeho
zvědavosti. Nejčastější typ útoku je zanechání přenosného média někde na
veřejném místě. Po zasunutí média do pc je cíl infikován malwarem.

### Password cracking (Bruteforce)

typ útoku, který zkouší každou kombinaci k prolomení hesla. Lze využít
třeba k prolomení hesla do šifrovaného souboru, účtu, WiFi. Samotný útok
není moc efektivní, trvá dlouho a spoléhá na raw výkon počítače, než na
zranitelnost systému. Útok lze usnadnit využítím seznamu hesel
(wordlist). Tyto seznamy lze stáhnout na internetu a obvykle jde o často
používaná hesla a odcizená hesla. Nyní nejčetnější seznam se nazývá
"RockYou.txt" a obsahuje 32 milionů hesel.

#### Něco málo k bezpečnosti hesel

k vytvoření účtu potřebujete heslo a to má obvykle nějaké parametry (8
znaků, velké a malé písmeno, čislo a speciální symbol...). Tímto ale
zároveň dávají nápovědu, co vše heslo musí obsahovat, abych ho prolomil.
Tudíž to není moc bezpečné... nejbezpečnější je, stanovit minimální
délku (například 16 znaků), protože to je na bruteforce hodně.

Dále se dělá, že hesla nesmí obsahovat slova a při zadávání hesla je
heslo ověřováno se slovníkem. To také ale není bezpečné, protože
uživatelé si to heslo pak nebudou pamatovat, takže si ho někam napíší...
nejlépe na papírek a přilepí na monitor. Proto je opět nejbezpečnější
mít dlouhé, ale ne moc složité heslo, než mít super silné heslo, ale mít
ho napsané na papíře u monitoru.

### Exploiting

využívání zranitelností je jedna z nejčastějších metod útoků. Spoléhá na
nalezení chyby v kódu OS nebo specifické aplikace, protokolu... ke
zranitelnosti se útočník dostane oskenováním cílového počítače a
zjištěním co nejvíce informací. Do relevantích informací patří - os a
jeho verze, běžící služby a jejich verze, otevřené porty... po zjistění
těchto informací útočník vyhledá, zda pro ně už neexistuje nějaký
exploit (viz
[[https://www.exploit-db.com/]{.ul}](https://www.exploit-db.com/) ),
pokud ano, tak ho útočník využije a dostane se třeba ke vzdálenému
přístupu.

#### Příklady

- **hack herních konzolí** - po nalezení chyby v os je možné instalovat vlastní SW

- **intel meltdown** - hardware zranitelnost intel procesorů. Jde o race condition (popsáno pozdeji) mezi zadáváním instrukcí a ověřením práv.. (moc dlouhé na popis)

- **shellshock** - exploit v unixu, jde o neautorizované spouštění příkazů v BASH. TLDR - pokud byl kód přidán na konec proměnné, tak byl vykonán a to už bez ověření práv. Je to jedna z nejznámějších bezpečnostích chyb. Objevena byla v roce 2014, ale v systému byla již od roku 1992.

### Denial of service (DoS)

druh síťového útoku. Jde o flood útok, kdy útočník z jednoho počítače
odesílá velký počet bezúčelných paketů. Cílem útoku je znemožnit přístup
k určité službě a tím zamezit jejímu použití (ztráta peněz cílové
společnosti). DoS útoky jsou snadné na provedení a proto představují
velký risk.

#### Typy

- **kvantita** - cíl zahlcen tolika požadavky, že nezvládne zpracovat
  další.

- **špatně formátovaný paket** - paket je formátován tak, že cíl nedokáže
  paket zpracovat (obsahuje chyby, errory...). Cílové zařízení je proto
  zmatené a může crashnout.

### Distributed DoS (DDoS)

zjednodušeně jde o koordinovaný DoS z více zdrojů. Obvykle je proveden
pomocí botnetu složeného ze "zombie počítačů". (nakažené pc bot
malwarem, takže vykonávají akce útočníka)

### Man-in-the-middle (MITM)

útok, během kterého útočník naruší komunikaci svým zařízením a
odposlouchává/upravuje komunikaci. Útoku lze snadno zamezit šifrováním
komunikace, ale pokud útoční zachytí výměnu klíčů, tak je komunikace
prozrazena.

**nejčastější druhy:**

- **ARP poisoning** - utočník se v sítí bude vydávat za router, tudíž přesměruje celou komunikaci přes něj

- **DNS spoofing** - otrávení DNS tabulky, takže pak bude přesměrovávat na chybnou adresu, obvykle útočníkovu

### SQL injection

Jedna z nejčastěji používaných technik útoku na web. Upravení SQL dotazu
na webu tak, aby vracel například všechny záznamy (leak celé DB). Toho
lze docílit přidáním vždy správné podmínky (\... OR 1 = 1). To vrátí vše
z tabulky.

### SEO poisoning

otrávení search enginu. Útočník může uměle zlepšit výkonnost podvodné
stránky obsahující malware, aby byla častěji zobrazována = více navštěv
= více lidí, kteří se mohou nakazit

## Útočné strategie

### Blended attack

kombinace několika útoků najednou, je potřebný pro více komplexní útoky,
používá se prakticky všude.

**příklady:**

- kombinace spam emailů a odkazu na malware
- bot malware vede k botnetu a to vede na DDoS, DDoS shodí web banky a pak útočník rozešle phishing maily omlouvající se za nepříjemnost a přesměruje je na fake login page

### Kill chain

struktura útoku. Obsahuje části obvykle potřebné pro správné provedení
útoku.

#### Útok

- Reconnaissance (výběr cíle, průzkum, hledání zranitelností)

- Weaponization (vytvoření útoku, malwaru...)

- Delivery (odeslání útoku k cíli)

- Exploitation (spuštění útoku)

- Instalation (instalalce vzdáleného přístupu na cílové zařízení)

- Command and Control (získání přímého přístupu do systému)

- Actions on objective (zisk dat nebo provedení škodlivé akce)

#### Obrana

- Detect (detekovat útok a útočníka)

- Deny (zamezit vzdálenému přístupu)

- Disrupt (zastavit odchozí traffic)

- Degrade (protiútok Command and Control)

- Decieve (zásah do útočníkova Command and Control)

- Contain (opravit chybu/zranitelnost)
