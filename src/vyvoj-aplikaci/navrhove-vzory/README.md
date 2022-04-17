# Návrhové vzory

## Co to je?

- je to způsob postupu, dle kterého upravíme náš postup při tvorbě programu
- není to specifická část kódu, ale obecný koncept pro řešení specifického problému
- jsou to
  - ověřené programovací "styly" nebo "postupy"
  - řešení na mnoho obvyklých problémů při tvorbě softwarovém designu
- jsou často zaměňovány s algoritmy
  - protože oba koncepty popisují řešení ke specifickému problému
  - rozdíl je v tom že
    - algoritmy jsou jako kuchařka (pevně dané postupy)
    - vzory jsou jako plán (vidíme výsledek a funkce, ale přesné pořadí záleží na nás)

## Proč?

- každou věc můžeme dělat 2 způsoby
  - funkčním
  - správným
- při použití návrhových vzorů je mnohem snažší pro jiného člověka se v kódu lépe zorientovat
- lepší komunikace s kolegy (např. "Oh, tak použij Singleton na to")
  - není zapotřebí dlouhé vysvětlování
- většina návrhových vzorů jsou jednoduché a standardní postupy
  - někdo jen je sepsal, dal jim název a určil pravidla

## Z čeho se skládají?

- vzory jsou popsány velice formálně
- skládají se z
  - Záměru (nastínění problému i řešení)
  - Motivace (podrobnější vysvětlení problému i řešení)
  - Struktury (vztahy mezi třídami)
  - Většínou i s ukázkou vzorového kódu

## Dělení

- Creational patterns (vytvářecí)
  - jak jsou objekty vytvářeny
- Structural patterns (strukturální)
  - jaké mají objekty mezi sebou vztahy
- Behavioral patterns (chování)
  - jak objekty spolu komunikují

### Creational patterns

- **Singleton**

  - objekt, který může být instancován pouze jednou
  - příkladem může být:
    - připojení k databázi
    - nastavení aplikace
  - ```php
    class Singleton
    {
        private static $instance = NULL;

        protected function __construct() { }

        public static function getInstance() : Singleton
        {
            if (self::$instance === NULL)
            {
                self::$instance = new static();
            }

            return self::$instance;
        }
    }
    ```

- **Builder**

  - objekt se vytváří postupně a ne najednou
  - ```php
    class Burger
    {
        private $_bun;
        private $_ketchup;
        private $_mustard;
        private $_cheese;
        private $_salad;
        private $_meat;

        public function __construct(
            boolean $bun = false,
            boolean $ketchup = false,
            boolean $mustard = false,
            boolean $cheese = false,
            boolean $salad = false,
            boolean $meat = false)
        {
            $this->_bun = $bun;
            $this->_ketchup = $ketchup;
            $this->_mustard = $mustard;
            $this->_cheese = $cheese;
            $this->_salad = $salad;
            $this->_meat = $meat;
        }

        public function addBun() { $this->_bun = true; return $this; }
        public function addKetchup() { $this->_ketchup = true; return $this; }
        public function addMustard() { $this->_mustard = true; return $this; }
        public function addCheese() { $this->_cheese = true; return $this; }
        public function addSalad() { $this->_salad = true; return $this; }
        public function addMeat() { $this->_meat = true; return $this; }
    }

    // najednou vs postupně
    $burgerA = new Burger(true, false, false, true, true, true);

    // $burgerA === $burgerB
    $burgerB = new Burger()->addBun()->addCheese()->addSalad()->addMeat();
    ```

- **Prototype**

  - je to alternativa k dědění tříd
    - dědí se z objektu a ne ze třídy
    - dědí se i hodnoty z objektu
  - ```js
    const zombie = {
      eatBrains() {
        return "Yum 🧠";
      },
    };
    zombie.eatBrains();

    // Prototype
    const zombieWithName = Object.create(zombie, { name: "Igor" });
    zombieWithName.eatBrains();
    zombieWithName.name;
    ```

### Structural patterns

- **Proxy**

  - je to zástupný objekt za originální objekt
  - zástupný objekt vykonává akce předtím, než se požadavek dostane k původnímu objektu, nebo poté co se k němu dostane
  - ```php
    interface Subject
    {
        public function request(): void;
    }

    // Objekt
    class RealSubject implements Subject
    {
        public function request(): void
        {
            echo "RealSubject: Handling request.\n";
        }
    }

    // Proxy
    class Proxy implements Subject
    {
        private $realSubject;

        public function __construct(RealSubject $realSubject)
        {
            $this->realSubject = $realSubject;
        }

        public function request(): void
        {
            if ($this->checkAccess()) {
                $this->realSubject->request();
                $this->logAccess();
            }
        }

        // Akce před
        private function checkAccess(): bool
        {
            echo "Proxy: Checking access prior to firing a real request.\n";
            return true;
        }

        // Akce po
        private function logAccess(): void
        {
            echo "Proxy: Logging the time of request.\n";
        }
    }

    function clientCode(Subject $subject)
    {
        // ...

        $subject->request();

        // ...
    }

    $realSubject = new RealSubject();
    clientCode($realSubject);

    // vs
    $proxy = new Proxy(new RealSubject());
    clientCode($proxy);
    ```

- **Adapter**

  - používá se k znovu použití existující třídy, která není kompatibilní s další třídou
    - nemusí se modifikovat kód existující třídy
  - ![](https://refactoring.guru/images/patterns/diagrams/adapter/solution-en.png?id=5f4f1b4575236a3853f274b690bd6656)

- **Flyweight**
  - umožňuje vložit více dat na RAM, díky sdílení částí mezi objekty místo nechání všech dat v každém objektu
  - **Problém**:
    - ![](https://refactoring.guru/images/patterns/diagrams/flyweight/problem-en.png?id=1ab15b46781c548e3e7c55dddbee72de)
  - **Řešení**:
    - Sdílí se instance třídy Particle
    - ![](https://refactoring.guru/images/patterns/diagrams/flyweight/solution3-en.png?id=e861e35c1214c46ac7333a127462de68)

### Behavioral patterns

- **Memento**

  - umožňuje se vrátit k předchozímu stavu (undo)
  - **Problém**:
    - undo v editoru
    - ![](https://refactoring.guru/images/patterns/diagrams/memento/problem2-en.png?id=a1c8258832f35d27f1a566322b34bf78)
  - **Řešení**:
    - vytvoření snapshot
    - ![](https://refactoring.guru/images/patterns/diagrams/memento/solution-en.png?id=b8adab0fc6d22cf8d630e560b9a8fafd)

- **Observer**

  - _znám jako Event-Subscriber nebo Listener_
  - odebírací mechanismus (subscribe)
  - umožňuje informovat objekty, které objekt odebírají, že se stala akce
  - **Problém**:
    - čekání na nový produkt
    - buď posíláme informaci nikomu nebo všem zákazníkům
    - ![](https://refactoring.guru/images/patterns/content/observer/observer-comic-1-en.png?id=1ec8571b22ea8fd2ed537f06cc763152)
  - **Řešení**:
    - vytvoření objektu, který bude obsahovat všechny odběratele
    - ![](https://refactoring.guru/images/patterns/diagrams/observer/solution1-en.png?id=60fb9a2822649dec1c68b78733479c57)

- **Chain of Responsibility**
  - umožňuje předávat požadavky řetězci zpracovatelů (handlers)
    - každý zpracovatel musí buď požadavek zpracovat nebo poslat dalšímu zpracovateli
    - ![](https://refactoring.guru/images/patterns/content/chain-of-responsibility/chain-of-responsibility.png)
- **Problém**:
  - vyřešení požadavku na objednávací systém
  - ![](https://refactoring.guru/images/patterns/diagrams/chain-of-responsibility/problem2-en.png)
- **Řešení**:
  - vytvoření řetězce zpracovatelů
  - ![](https://refactoring.guru/images/patterns/diagrams/chain-of-responsibility/solution1-en.png)

## Zdroj

- [Guru Refactoring](https://refactoring.guru/design-patterns)
