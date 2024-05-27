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
