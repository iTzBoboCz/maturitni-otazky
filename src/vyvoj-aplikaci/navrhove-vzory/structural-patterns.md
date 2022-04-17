# Structural patterns

## Proxy

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

## Adapter

- používá se k znovu použití existující třídy, která není kompatibilní s další třídou
  - nemusí se modifikovat kód existující třídy
- ![](https://refactoring.guru/images/patterns/diagrams/adapter/solution-en.png?id=5f4f1b4575236a3853f274b690bd6656)

## Flyweight

- umožňuje vložit více dat na RAM, díky sdílení částí mezi objekty místo nechání všech dat v každém objektu
- **Problém**:
  - ![](https://refactoring.guru/images/patterns/diagrams/flyweight/problem-en.png?id=1ab15b46781c548e3e7c55dddbee72de)
- **Řešení**:
  - Sdílí se instance třídy Particle
  - ![](https://refactoring.guru/images/patterns/diagrams/flyweight/solution3-en.png?id=e861e35c1214c46ac7333a127462de68)
