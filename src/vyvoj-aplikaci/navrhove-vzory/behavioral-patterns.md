# Behavioral patterns

## Memento

- umožňuje se vrátit k předchozímu stavu (undo)
- **Problém**:
  - undo v editoru
  - ![](./images/behavioral-patterns-momento-problem.png)
- **Řešení**:
  - vytvoření snapshot
  - ![](./images/behavioral-patterns-momento-solution.png)

## Observer

- _znám jako Event-Subscriber nebo Listener_
- odebírací mechanismus (subscribe)
- umožňuje informovat objekty, které objekt odebírají, že se stala akce
- **Problém**:
  - čekání na nový produkt
  - buď posíláme informaci nikomu nebo všem zákazníkům
  - ![](./images/behavioral-patterns-observer-problem.png)
- **Řešení**:

  - vytvoření objektu, který bude obsahovat všechny odběratele
  - ![](./images/behavioral-patterns-observer-solution.png)

## Chain of Responsibility

- umožňuje předávat požadavky řetězci zpracovatelů (handlers)
  - každý zpracovatel musí buď požadavek zpracovat nebo poslat dalšímu zpracovateli
  - ![](./images/behavioral-patterns-chain-of-responsibility.png)
- **Problém**:
  - vyřešení požadavku na objednávací systém
  - ![](./images/behavioral-patterns-chain-of-responsibility-problem.png)
- **Řešení**:
  - vytvoření řetězce zpracovatelů
  - ![](./images/behavioral-patterns-chain-of-responsibility-solution.png)
