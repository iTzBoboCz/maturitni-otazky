# Behavioral patterns

## Memento

- umožňuje se vrátit k předchozímu stavu (undo)
- **Problém**:
  - undo v editoru
  - ![](https://refactoring.guru/images/patterns/diagrams/memento/problem2-en.png?id=a1c8258832f35d27f1a566322b34bf78)
- **Řešení**:
  - vytvoření snapshot
  - ![](https://refactoring.guru/images/patterns/diagrams/memento/solution-en.png?id=b8adab0fc6d22cf8d630e560b9a8fafd)

## Observer

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

## Chain of Responsibility

- umožňuje předávat požadavky řetězci zpracovatelů (handlers)
  - každý zpracovatel musí buď požadavek zpracovat nebo poslat dalšímu zpracovateli
  - ![](https://refactoring.guru/images/patterns/content/chain-of-responsibility/chain-of-responsibility.png)
- **Problém**:
  - vyřešení požadavku na objednávací systém
  - ![](https://refactoring.guru/images/patterns/diagrams/chain-of-responsibility/problem2-en.png)
- **Řešení**:
  - vytvoření řetězce zpracovatelů
  - ![](https://refactoring.guru/images/patterns/diagrams/chain-of-responsibility/solution1-en.png)
