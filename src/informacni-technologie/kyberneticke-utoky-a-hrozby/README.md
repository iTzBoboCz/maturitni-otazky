# Kybernetické útoky a hrozby

Kybernetické útoky mají obvykle dva cíle - získat něco (informace, peníze) a nebo cíl poškodit (zničit data, přerušit komunikaci...). Toho lze dosáhnout mnoha způsoby.

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

## Útočné strategie

### Blended attack

Kombinace několika útoků najednou, je potřebný pro více komplexní útoky. Používá se prakticky všude.

**příklady:**

- kombinace spam emailů a odkazu na malware
- bot malware vede k botnetu a to vede na DDoS, DDoS shodí web banky a pak útočník rozešle phishing maily omlouvající se za nepříjemnost a přesměruje je na fake login page

### Kill chain

Struktura útoku. Obsahuje části obvykle potřebné pro správné provedení útoku.

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
