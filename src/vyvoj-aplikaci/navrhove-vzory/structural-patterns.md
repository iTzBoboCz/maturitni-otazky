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
- ![](./images/structural-patterns-adapter.png)

## Flyweight

- umožňuje vložit více dat na RAM, díky sdílení částí mezi objekty místo nechání všech dat v každém objektu
- **Problém**:
  - ![](./images/structural-patterns-flyweight-problem.png)
- **Řešení**:
  - Sdílí se instance třídy Particle
  - ![](./images/structural-patterns-flyweight-solution.png)
