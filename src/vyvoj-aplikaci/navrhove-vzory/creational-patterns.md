# Creational patterns

## Singleton

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

## Builder

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

## Prototype

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
