# ZKS (BE4M36ZKS)

## Questions

- Describe and compare the V and W models of the software testing process. Explain static testing and its role in the W model. Describe individual methods of static testing.

- Explain the principle of Model Based Testing (MBT) and compare its advantages and disadvantages with manual testing approach. Give some examples of models that can be employed in MBT. How does MBT relate to test automation?

- Outline the main test automation principle and economics. What are possible levels at which tests can be automated? Give some examples of main approaches and technologies that can be used in software test automation.

- Explain the equivalence class and boundary values concepts and principle of the Combinatorial Interaction Testing. What is a combinatorial explosion effect, how to effectively reduce the input data combinations? Principle of pairwise (2-way) and N-way testing.

- Principle of path-based testing. Formal deﬁnition of system model and test coverage criteria (node/edge coverage, edge-pair coverage, prime-path coverage). How prioritization of process/workﬂow activities is modelled and handled in the generation of the test cases?

## Termínus technikus


- **Black box testing:** Nevíme, co testujeme, nevidíme dovnitř, testy stavíme na základě pravděpodobných případů používání
- **White box testing:** Máme k dispozici kód, děláme informované testy nebo analýzu kódu
- **Verifikace:** Testujeme, jestli to odpovídá specifikaci
- **Validace:** Testujeme, jestli to je to, co klient chce
- **Regrese:** Do systému zanášíme další chyby při tom, jak se ho snažíme opravit.
- **Test coverage:** Pokrytí testů, tedy jaká část SW je otestovaná (řádky kódu, kombinace vstupů). Vyjadřuje se v procentech.
- **Smoke test:** Základní test funkcionality / předběžné testování
- **Test condition:** Něco, co testujeme, třeba funkce nebo jiná část systému. 


## Describe and compare the V and W models of the software testing process. Explain static testing and its role in the W model. Describe individual methods of static testing.

### Proč chceme dobrý způsob návrhu

Boehmův zákon : cena opravy chyby roste!

![boehm](boehm.png)

### Waterfall model

![waterfall](waterfall.png)

### V model

![v](v.png)

- Lineární model
- Testování je prováděno na konci vývojového procesu
- Fáze:
  1. Analýza požadavků
  2. Návrh systému
  3. Návrh architektury
  4. Návrh komponent
  5. Implementace
  6. Integrace
  7. Testování
  8. Nasazení
- Nevýhody:
  - Méně flexibilní než W-model
  - Změny v požadavcích mohou způsobit zpoždění a náklady

### W model

![w](w.png)

- Iterativní model
- Testování je prováděno během celého vývojového procesu
- Fáze:
  1. Analýza požadavků
  2. Návrh systému
  3. Návrh architektury
  4. Návrh komponent
  5. Implementace
  6. Integrace
  7. Testování
  8. Nasazení
- Výhody:
  - Flexibilnější než V-model
  - Snadnější detekce a řešení problémů v průběhu vývoje
  - Změny v požadavcích méně pravděpodobně způsobí zpoždění a náklady

### Srovnání V-modelu a W-modelu:

- V-model je lineární a méně flexibilní
- W-model je iterativní a flexibilnější
- V-model provádí testování až na konci vývoje
- W-model provádí testování během celého vývoje


### Statické testování a jeho role ve W-modelu:

#### Statické testování:
- Testování softwaru bez spuštění kódu
- Zaměřuje se na kontrolu kódu, dokumentace a dalších artefaktů
- Techniky statického testování:
  - Průzkum kódu (Code review)
  - Statická analýza kódu (Static code analysis)
  - Kontrola dokumentace (Documentation review)
  - Průzkum návrhu (Design review)
  - Kontrola požadavků (Requirements review)

#### Role ve W-modelu:
- Statické testování je důležitou součástí W-modelu
- Provádí se během celého vývojového procesu, nejen v testovací fázi
- Pomáhá detekovat a řešit problémy v kódu a dokumentaci dříve
- Redukuje riziko chyb a náklady spojené s opravami
- Přispívá k vyšší kvalitě softwaru

### Individuální metody statického testování:

1. Průzkum kódu (Code review):
   - Manuální kontrola zdrojového kódu
   - Hledání chyb, nedostatků, či nesouladu se standardy
   - Mohou být prováděny kolegy, týmem nebo i autorem kódu (sebereview)

2. Statická analýza kódu (Static code analysis):
   - Automatická kontrola zdrojového kódu pomocí nástrojů a algoritmů
   - Identifikace potenciálních chyb, problémů a nesouladů se standardy
   - Příklady nástrojů: FindBugs, PMD, SonarQube, JSHint

3. Kontrola dokumentace (Documentation review):
   - Manuální kontrola dokumentace projektu
   - Ověření správnosti, úplnosti a srozumitelnosti informací
   - Zahrnuje kontrolu technické dokumentace, návody, specifikace apod.

4. Průzkum návrhu (Design review):
   - Manuální kontrola návrhu systému nebo komponenty
   - Ověření, zda návrh splňuje požadavky a je vhodný pro implementaci
   - Posouzení technických a architektonických rozhodnutí

5. Kontrola požadavků (Requirements review):
   - Manuální kontrola specifikace požadavků na systém
   - Ověření správnosti, úplnosti a srozumitelnosti požadavků
   - Hledání možných konfliktů, nejasností nebo nekonzistencí

## Explain the principle of Model Based Testing (MBT) and compare its advantages and disadvantages with manual testing approach. Give some examples of models that can be employed in MBT. How does MBT relate to test automation?

### Manuální testování:
- Testování prováděné testerem
- Tester kontroluje systém nebo aplikaci podle testovacích scénářů
- Zahrnuje funkční, UI a uživatelský zážitek testování

### Model Based Testing (MBT):
- Testování založené na modelech
- Vytvoření abstraktního modelu systému nebo aplikace
- Generování testovacích případů z modelu pomocí algoritmů a nástrojů
- Automatická tvorba a provádění testů

### Výhody MBT oproti manuálnímu testování:
- Rychlejší generování testovacích případů
- Vyšší pokrytí testů díky systematickému přístupu
- Minimalizace lidských chyb při tvorbě a provádění testů
- Lehčí aktualizace testů při změnách v systému nebo požadavcích
- Úspora času a nákladů na vývoj

### Nevýhody MBT oproti manuálnímu testování:
- Vyšší počáteční náklady na vytvoření a udržbu modelu
- Nutnost specializovaných znalostí a nástrojů pro MBT
- Možné omezení v modelování složitých nebo nestandardních situací
- Menší vhodnost pro testování UI nebo uživatelského zážitku

### Příklady modelů použitelných v Model Based Testing (MBT):

1. Konečný automat (Finite State Machine, FSM):
   - Model založený na stavech a přechodech mezi nimi
   - Popisuje chování systému nebo komponenty
   - Vhodný pro testování systémů s omezeným počtem stavů a přechodů

2. Petriho síť (Petri Net):
   - Matematický model pro popis distribuovaných systémů
   - Zahrnuje místa, přechody a tokeny pro popis chování
   - Použitelný pro testování paralelních nebo konkurenčních systémů

3. Markovův řetězec (Markov Chain):
   - Model náhodných procesů s konečným počtem stavů
   - Přechody mezi stavy závisejí pouze na aktuálním stavu
   - Užitečný pro testování systémů s pravděpodobnostními přechody

4. Scénářové modely (Scenario Models):
   - Modely popisující konkrétní případy užití nebo interakce s aplikací
   - Vhodné pro testování funkcionality systému z pohledu uživatele

5. Datové modely (Data Models):
   - Modely zaměřené na strukturu a vztahy mezi daty v systému
   - Použitelné pro testování datových operací, jako je ukládání, načítání a zpracování dat

### Vztah MBT k automatickému testování:

- MBT je způsob, jak generovat testovací scénáře a případy z modelů systému
- Automatické testování je proces spouštění těchto testovacích případů bez lidské interakce
- MBT a automatické testování se často používají společně:
  - MBT generuje testovací případy
  - Automatické testování provádí tyto testovací případy
  - Tím se zvyšuje efektivita, rychlost a přesnost testování