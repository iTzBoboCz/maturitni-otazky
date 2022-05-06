# Web API

Web API – Application Programming Interface for the web

API je způsob vzájemné komunikace 2 počítačů. Jeden pošle žádost o provedení nějaké funkce nebo procedury a druhý počítač mu na to něco odpoví.

Umožňuje využívat jíž naprogramovaná řešení a integrovat je do vlastních webových stránek

Slouží k rozšíření funkcionality a automatizaci určitých procedur.

- Stateless
  - Obě strany o sobě nemusí uchovávat žádné informace.
  - Všechny žádosti a odpovědi jsou nezávislé na ostatních

**REST API**

- Representational State Transfer
- Většina API v dnešní době jsou RESTful což znamená, že se řídí souborem pravidel nebo omezení které se právě jmenují RESTful.
- Je standardem pro většinu API vývojářů od začátku 21. století
- Roy Fielding
  - V roce 2000 definoval REST ve své disertační práci
- Žádost
  - Používá http pro provedení žádosti
  - Start Line
    - Metoda
    - Cesta ke zdroji (URL)
  - Hlavička (Header)
    - Accept (V jakém formátu chcete ty data získat)
    - Authorization (Token pro získání dat)
    - Connection(keep-alive)
  - Tělo
    - Zde jsou umístěny samotný data
  - Základní metody
    - GET(Přečíst)
    - POST(Vytvořit)
    - PATCH(Upravit)
    - DELETE(sMAZAT)
- Odpověď
  - V horní části zprávy je stavový kód
    - 2XX – Vše je v pořádku
    - 4XX – Chyba u klienta
    - 5XX – Chyba u serveru
  - Hlavička
    - Obsahuje data o serveru
      - Server(ngino)
      - Age (1935)
      - Connection(keep-alive)
  - Tělo
    - Obsahuje data
      - Většinou data jsou typu JSON
- **OpenAPI**
  - Je formát popisu API pro REST API.
  - Soubor OpenAPI umožňuje popsát celou vaši API, včetně
    - Dostupné koncové body (/users) a operace na každém koncovém bodě (GET /users, POST /users)
    - Operační parametry Vstup a výstup pro každou operaci
    - Metody autentizace
    - Kontaktní údaje, licence, podmínky použití a další informace.

**SOAP Protokol**

- Simple Object Access Protocol
- Umožnuje posílání XML zpráv jen pouze mezi dvěma aplikacemi (peer to peer)
- Nejčastěji se SOAP používá jako náhrada vzdáleného volání procedur (RPC), tedy v modelu požadavek/odpověď.
- Složení XML zprávy

| **Element** | **Popis** | **Požadované** |
| --- | --- | --- |
| EnvelopeObálka | Identifikuje XML dokument jako SOAP zprávu | Ano |
| HeaderHlavička | Většinou obsahuje informace, které identifikují uživatele, nějaký data pro přihlášení | Ne |
| BodyTělo | Hlavní část, v ní se nacházejí nejdůležitější data, jako například jaká služba se vyvolává, předávané parametry | Ano |
| FaultChyba | Poskytuje informace o chybách, ke kterým došlo při zpracování zprávy | Ne |

- Příklad zprávy klienta, který vyžaduje informace o produktu s ID 827635

![](RackMultipart20220506-1-p6m60g_html_7b6981a928485810.png)

- Odpověď webové služby pro klienta

![](RackMultipart20220506-1-p6m60g_html_9c3ecf7f987dbe36.png)

**REST vs SOAP**

|   | **REST** | **SOAP** |
| --- | --- | --- |
| **Název** | Represantational State Transfer | Simple Object Access Protocol |
| **Design** | Volné a flexibilní pokyny, které jsou založeny na architektuře | Přísná, jasně definovaná pravidla |
| **Přístup** | Řízen daty | Řízen funkcemi |
| **Statefulness** (Stavovost) | Je vždy stateless | Může, ale nemusí být stateless |
| **Caching** (Ukládaní do mezi paměti) | Volání API se ukládají do mezi paměti | Volání API nejsou ukládaný do mezi paměti |
| **Výkon** | Vyžaduje méně zdrojů | Vyžaduje více energie, zdrojů |
| **Formát zprávy** | XML, JSON, YAML, HTML a další | Pouze XML |
| **Přenosové protokoly** | Pouze HTTP | SMTP, HTTP, UDP a další |
| **Využití** | Veřejné API pro webové služby, sociální sítě a mobilní služby | Platební brány, finanční služby, aplikace vyššího úrovně, telekomunikační služby |
| **Výhody** | Zabezpečení, standardizace a rozšiřitelnost | Vysoký výkon, škálovatelnost, flexibilita a přívětivost prohlížeče |

**GraphQL**

- Vývojářem je Facebook
- Největší konkurencí je REST
- Je potřeba specifikovat konkrétní data, která ze serverové části mají přijít na klientskou
  - Uživatel nedostane data, které nepotřebuje -\&gt; eliminace nepotřebných data
- Objektové typy (Entrypointy)
  - Query
    - Specifikuje data, se kterými je třeba v rámci procesu pracovat, a současně stanovují podobu vrácené odpovědi
  - Mutation
    - 3 Podoby
      - Create, Update, Delete
    - Tyto podoby se vyskytují v závislosti na požadované modifikaci, přičemž současně mohou vrátit take hodnoty vytvořené na server, například přidělené ID
  - Subscriptions
    - Nejvíc využívaný v real-time aplikacích, mohou navázat na některou z událostí prováděnou v backendu a v souvislosti s ní provést předem určenou akci
    - Např. zobrazit určitý výpis komentářů
- Výhody
  - Rychlost a stabilita aplikace
    - Je zapříčiněno tím, že nemusí vracet zbytečná data
  - Data jsou validována ještě před vykonáním dotazu
- Nevýhody
  - Cachování
  - Dlouhé a komplexní dotazy
- Porovnání s REST
  - V GraphQL neni možné vytáhnout všechny data z tabulky jako v REST, pokud je potřeba získat všechny atributy získat, musíte je vyjmenovat v dotaze
    - REST(SQL)
      - SELECT \* FROM TABLE
    - GraphQL
      - {
        - human(id:&quot;1000&quot;){
            - name
            - height
        - }
      - }

Zdroje :

[https://stackoverflow.com/questions/48123867/open-api-vs-rest-api-difference](https://stackoverflow.com/questions/48123867/open-api-vs-rest-api-difference)

[https://restfulapi.net/http-methods/](https://restfulapi.net/http-methods/)

[https://restfulapi.net/](https://restfulapi.net/)

[https://www.codecademy.com/article/what-is-rest](https://www.codecademy.com/article/what-is-rest)

[https://graphql.org/learn/queries/](https://graphql.org/learn/queries/)

https://graphql.org/learn/