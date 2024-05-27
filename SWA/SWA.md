# SWA (BE4M36SWA)

## Questions

- Describe Krutchen's 4+1 View Model of a software architecture. Explain how it captures the complete behavior of a developed software from multiple perspectives of the system. How is this model aligned with the UML models?

- What is a software architecture? Describe the importance of software architecture when developing a system. What are the software architecture design guidelines? What are the architectural styles? Give an example of an architectural style and describe it in detail.

- What is a design pattern? What problem are design patterns solving? What types of design patterns exist? Why is it important to know the design patterns? Are there design antipatterns?

- What is a microservice architecture? What are its advantages and disadvantages compared to a monolithic architecture. How is microservices development different from developing a monolithic application? Are there any methodologies or guidelines or best practices to follow when developing microservices? Obviously, there are patterns that can be applied in this area, are there any antipatterns that should be avoided?

- Software architects can choose one architecture over another. The choice may affect the quality of the final product. Can you tell if one architecture is better than another or if one architecture is bad while the other is not? How can you measure the quality of an architecture? Can you measure the quality from different perspectives?

## Describe Krutchen's 4+1 View Model of a software architecture. Explain how it captures the complete behavior of a developed software from multiple perspectives of the system. How is this model aligned with the UML models?

### Popis Krutchenova 4+1 View Modelu softwarové architektury:

![Kruchten model](kruchten.png)

- **Pohled logický (Logical View)**:
   - Zobrazuje třídy, objekty, rozhraní a jejich vztahy
   - Zaměřuje se na funkcionalitu systému
- **Pohled procesní (Process View)**:
   - Popisuje procesy a konkurenci v systému
   - Zaměřuje se na výkonnost, škálovatelnost a stabilitu
- **Pohled vývojový (Development View)**:
   - Zobrazuje organizaci zdrojového kódu, knihoven a komponent
   - Zaměřuje se na správu kódu a modulární strukturu
- **Pohled fyzický (Physical View)**:
   - Popisuje mapování softwarových komponent na hardware
   - Zaměřuje se na nasazení a distribuci systému
- **Scénáře (Scenarios):**
   - Uplatňuje se pro ověření a validaci návrhu architektury
   - Pomáhá provést průřez všemi čtyřmi pohledy

### Jak 4+1 View Model zachycuje chování softwaru z různých perspektiv:

- **Logický pohled (Logical View)**:
  - Poskytuje abstraktní pohled na systém z hlediska funkčnosti
  - Umožňuje analyzovat a navrhovat statickou strukturu systému
  - Pomáhá identifikovat třídy, rozhraní a jejich vztahy
  - Slouží k pochopení domény a funkcí, které systém poskytuje

- **Procesní pohled (Process View)**:
  - Zkoumá chování systému z hlediska běhových procesů a vláken
  - Umožňuje identifikovat synchronizační a komunikační aspekty mezi jednotlivými procesy
  - Pomáhá zajišťovat škálovatelnost, výkonnost a stabilitu systému
  - Slouží k analýze a řešení problémů týkajících se konkurence a distribuce

- **Fyzický pohled (Physical View)**:
  - Popisuje, jak jsou softwarové komponenty nasazeny na hardwarové prostředky
  - Umožňuje řešit otázky týkající se komunikace a propojení mezi hardwarovými jednotkami
  - Pomáhá identifikovat potenciální omezení a problémy v hardwarové konfiguraci
  - Slouží k optimalizaci nasazení a distribuce systému

- **Vývojový pohled (Development View)**:
  - Zkoumá strukturu zdrojového kódu, knihoven a modulů
  - Umožňuje identifikovat závislosti a propojení mezi jednotlivými částmi kódu
  - Pomáhá zlepšovat čitelnost, udržitelnost a modularitu kódu
  - Slouží k usnadnění práce vývojářů a podpoře týmové spolupráce

- **Scénáře (Scenarios)**:
  - Představují konkrétní příklady použití systému (use cases)
  - Umožňují ověřit a validovat návrh architektury
  - Pomáhají identifikovat problémy a nedostatky v návrhu
  - Slouží k provádění průřezů mezi všemi čtyřmi pohledy a k integraci různých aspektů systému


### Co jsou scénáře:

Scénáře se často vztahují k atributům kvality ( = Atribut kvality je měřitelná nebo testovatelná vlastnost. systému, která se používá k určení toho, jak dobře je systém uspokojuje potřeby zúčastněných stran)

![atributy](attributes.png)

Obecné i konkrétní scénáře mají:

- **Zdroj podnětu**, což je cokoliv, co vytváří podnět. Může být interní nebo externí vůči systému.
- **Podnět** je podmínka, která způsobí, že systém zareaguje. Zdroj podmínky může vzniknout interně nebo externě, bude třeba rozlišovat typy podmínek.
- **Prostředí** je režim systému, když přijímá podnět. Jedná se o důležitý aspekt, zejména pokud systém zahrnuje distribuované výpočty nebo pokud může existovat i v jiných provozních režimech než jen v režimu spuštění a zastavení, jako je například zotavování se z poruchy.
- **Artefakt** je část systému, která je podnětem ovlivněna. V rozsáhlých systémech by měl podnět přímo ovlivnit celý systém.
- **Reakce** je to, jak se artefakt zachová v důsledku přijetí podnětu. Tato odezva může zahrnovat zpracování chyby, zotavení z poruchy, aktualizace systémových protokolů, odeslání bezpečnostních výstrah nebo změna systému. aktuálního prostředí.
- **Míra odezvy** je metrika používaná ke kvantifikaci odezvy, aby bylo možné měřit atribut kvality. Tato metrika by měla být kvantitativní a objektivní, například pravděpodobnost selhání, doba odezvy, doba opravy, a průměrné zatížení systému.

![scenarios](scenarios.png)

### Co je UML:

UML, Unified Modeling Language je v softwarovém inženýrství grafický jazyk pro vizualizaci, specifikaci, navrhování a dokumentaci programových systémů.

Máme 14 různých UML diagramů rozdělených do dvou skupin.

![UML](uml.png)

### Integrace UML s 4+1 View Model:

- UML diagramy poskytují vizuální reprezentaci pro každý pohled v 4+1 View Modelu
- Umožňují efektivní komunikaci mezi architekty, vývojáři, testery a dalšími členy týmu
- Podporují analýzu, návrh, implementaci a údržbu systému
- Usnadňují kontrolu a řízení kvality architektury

### UML diagramy pro 4+1 View Model:

- **Logický pohled (Logical View):**
    - Třídní diagram (Class Diagram)
    - Objektový diagram (Object Diagram)
    - Kompoziční struktura (Composite Structure Diagram)
    - Balíčkový diagram (Package Diagram)

- **Procesní pohled (Process View):**
    - Diagram činností (Activity Diagram)
    - Sekvenční diagram (Sequence Diagram)
    - Diagram spolupráce (Collaboration Diagram)
    - Stavový diagram (State Diagram)

- **Fyzický pohled (Physical View):**
    - Diagram nasazení (Deployment Diagram)
    - Diagram komponent (Component Diagram)
    - Komunikační diagram (Communication Diagram)

- **Vývojový pohled (Development View):**
    - Balíčkový diagram (Package Diagram)
    - Diagram komponent (Component Diagram)
