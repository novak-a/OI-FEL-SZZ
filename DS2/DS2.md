# DS2 (B4M36DS2)

## Questions

- Big Data (V characteristics, current trends), NoSQL databases (motivation, features). Scaling (vertical, horizontal, network fallacies, cluster). Distribution models (sharding, replication, master-slave and peer-to-peer architectures). CAP theorem (properties, ACID, BASE). Consis- tency (strong, eventual, read, write, quora). Performance tuning (Amdahl’s law, Little’s law, message cost model). Polyglot persistence.

- MapReduce (architecture, functions, data ﬂow, execution, use cases). Hadoop (MapReduce, HDFS).

- XPath (path expressions, axes, node tests, predicates). XQuery (constructors, FLWOR, conditional, quantiﬁed and comparison expressions). SPARQL (subgraph matching, graph patterns, datasets, ﬁlters, solution modiﬁers, query forms).

- RiakKV (CRUD operations, links, link walking, convergent replicated data types, Search 2.0, vector clocks, Riak Ring, replica placement strategy). Redis (data types, operations, TTL). Cassandra (keyspaces, column families, CRUD operations). MongoDB (CRUD operations,update and query operators, projection, modiﬁers).
  
- Graph data structures (adjacency matrix, adjacency list, incidence matrix). Data locality (BFS layout, bandwidth minimization problem, Cuthill-McKee algorithm). Graph partitioning (1D partitioning, 2D partitioning). Neo4j (traversal framework, traversal description, traverser). Cypher (graph matching, read, write and general clauses).

## Big Data (V characteristics, current trends), NoSQL databases (motivation, features). Scaling (vertical, horizontal, network fallacies, cluster). Distribution models (sharding, replication, master-slave and peer-to-peer architectures). CAP theorem (properties, ACID, BASE). Consistency (strong, eventual, read, write, quora). Performance tuning (Amdahl’s law, Little’s law, message cost model). Polyglot persistence.


### Big Data:
- 5 V charakteristiky:
  1. Objem (Volume): obrovské množství dat
  2. Rychlost (Velocity): rychlé generování a zpracování dat
  3. Rozmanitost (Variety): různé formáty dat (strukturovaná, nestrukturovaná)
  4. Pravdivost (Veracity): důvěryhodnost a kvalita dat
  5. Hodnota (Value): užitečnost získaných informací z dat
- Současné trendy:
  - Aplikace strojového učení a umělé inteligence
  - Cloud computing pro ukládání a zpracování dat
  - Analýza sociálních sítí a sentimentu
  - Internet věcí (IoT) a chytrá města
  - Zpracování a analýza reálných časových dat

![c](c.png)

### NoSQL databáze:
- Motivace:
  - Potřeba zpracovávat velké objemy nestrukturovaných dat
  - Rychlost a škálovatelnost
  - Vyšší tolerance k chybám a výpadkům
  - Flexibilita a jednoduchost v návrhu datových modelů
- Vlastnosti:
  - BezSQL (Not-only-SQL): nepoužívají pouze SQL dotazy
  - Škálovatelnost: horizontální škálování, distribuované prostředí
  - Typy NoSQL databází: dokumentové, klíč-hodnota, sloupcové, grafové
  - Eventuální konzistence: ochota obětovat striktní konzistenci za rychlost a škálovatelnost
  - Snadná a rychlá integrace s Big Data aplikacemi

### Škálování:
- Vertikální škálování:
  - Přidávání zdrojů (CPU, paměť, úložiště) do jednoho serveru
  - Omezení: fyzické limity serveru, vyšší cena, možný výpadek v provozu
- Horizontální škálování:
  - Rozdělení zátěže mezi více serverů
  - Výhody: lepší výkonnost, tolerance k výpadkům, snadné přidání dalších serverů
  - Nevýhody: složitější správa, potřeba distribuovaných systémů

### Síťové klamání (Network Fallacies):
1. Spolehlivost sítě
2. Nulová latence
3. Nekonečná šířka pásma
4. Bezpečná síť
5. Homogenita sítě

### Cluster (shluk):
- Skupina propojených serverů pracujících společně jako jeden systém
- Výhody:
  - Zvýšení výkonnosti a zátěžové kapacity
  - Tolerance k výpadkům a zajištění dostupnosti
  - Snadné škálování
- Nevýhody:
  - Složitější správa a konfigurace
  - Vyšší náklady na hardware a software

### Distribuční modely:
- Sharding:
  - Rozdělení dat do menších částí (shard) a uložení na různých serverech
  - Výhody: zvýšení výkonnosti, snížení zátěže, snadné škálování
  - Nevýhody: složitější správa, náročnější na vývoj aplikací
- Replikace:
  - Více kopírování dat mezi servery pro zajištění dostupnosti a zálohy
  - Výhody: zvýšení odolnosti vůči výpadkům, snížení zátěže
  - Nevýhody: zvýšení nákladů na úložiště, režie při synchronizaci dat

### Architektury:
- Master-Slave:
  - Jeden hlavní server (master) a jeden nebo více záložních serverů (slave)
  - Master: spravuje zápis dat, synchronizuje s Slave servery
  - Slave: pouze čtení dat, záložní server pro případ výpadku Master serveru
  - Výhody: zvýšení výkonnosti, snížení zátěže, jednoduchá správa
  - Nevýhody: možný úzký hrdlo (master), složitější zápis dat
- Peer-to-Peer (P2P):
  - Síť, ve které každý uzel komunikuje přímo s ostatními uzly
  - Žádný ústřední server nebo autorita
  - Výhody: škálovatelnost, odolnost vůči výpadkům, decentralizace
  - Nevýhody: složitější správa, zvýšená režie při komunikaci mezi uzly

### CAP věta:
- Vlastnosti:
  1. Konzistence (Consistency): každý uzel v síti vidí stejná data
  2. Dostupnost (Availability): každý dotaz na systém dostane odpověď
  3. Tolerance k rozdělení (Partition Tolerance): systém funguje i při výpadcích části sítě
- CAP věta: v distribuovaném systému nelze zaručit všechny tři vlastnosti současně, pouze dvě z nich

![cap](cap.png)

### ACID:
- Vlastnosti transakcí v tradičních (SQL) databázích:
  1. Atomicita (Atomicity): transakce je buď celá provedena nebo vůbec
  2. Konzistence (Consistency): databáze zůstane konzistentní po každé transakci
  3. Izolace (Isolation): paralelní transakce se neovlivňují navzájem
  4. Trvanlivost (Durability): potvrzené transakce jsou trvale uloženy

![acid](acid.png)
### BASE:
- Vlastnosti transakcí v NoSQL databázích:
  1. Základní dostupnost (Basically Available): systém je dostupný i při výpadcích části sítě
  2. Měkká stavovost (Soft State): stav systému se může měnit časem, i bez vstupu (snaží se opravovat)
  3. Eventuální konzistence (Eventual Consistency): konzistence dat je zaručena po určitém čase
- BASE je obětování konzistence za dostupnost a toleranci k rozdělení (oproti ACID)

![base](base.png)


### Konzistence:
- Silná konzistence (Strong Consistency):
  - Každý čtenář vidí nejnovější zápis nebo chybu
  - Zaručuje, že všechny uzly v distribuovaném systému zobrazují stejná data
  - Může mít negativní dopad na výkonnost a škálovatelnost
- Eventuální konzistence (Eventual Consistency):
  - Zaručuje, že všechny změny budou nakonec propagovány do všech uzlů
  - Nezaručuje okamžitou konzistenci dat, ale po určitém čase
  - Výhody: rychlost, škálovatelnost, flexibilita
  - Používáno v NoSQL databázích a BASE systémech

![strong](strong.png)

### Konzistence čtení a zápisu:
- Čtenářská konzistence (Read Consistency):
  - Zajišťuje, že čtenář vidí data konzistentní s posledním zápisem
- Zápisová konzistence (Write Consistency):
  - Zajišťuje, že zápis dat je proveden konzistentně napříč všemi uzly

### Kvóra (Quorum):
- Mechanismus pro dosažení konzistence v distribuovaných systémech
- Založeno na hlasování uzlů pro potvrzení čtení a zápisu
- R > W: silná konzistence čtení, slabá konzistence zápisu
- W > R: slabá konzistence čtení, silná konzistence zápisu
- R + W > N: silná konzistence čtení i zápisu, kde N je počet uzlů

### Optimalizace výkonu:

- Amdahlův zákon:
  - Popisuje vliv paralelizace na zrychlení výpočtu
  - Zákon: S = 1 / (P + (1 - P) / N)
    - S: zrychlení výpočtu
    - P: podíl části úkolu, která nemůže být paralelizována
    - N: počet procesorů
  - Ukazuje, že zrychlení je omezeno sériovou částí úkolu

![amdahl](amdahl.png)

- Littleův zákon:
  - Popisuje vztah mezi počtem přítomných požadavků, rychlostí zpracování a dobou odezvy
  - Zákon: L = λW
    - L: průměrný počet požadavků v systému
    - λ: rychlost příchodu nových požadavků (požadavky za jednotku času)
    - W: průměrná doba odezvy na požadavek
  - Používá se pro optimalizaci front, zpracování požadavků a plánování zdrojů

![little](little.png)

- Model nákladů na zprávy (Message Cost Model):
  - Model pro analýzu komunikačních nákladů v distribuovaných systémech
  - Faktory ovlivňující náklady:
    - Latence: čas potřebný pro doručení zprávy
    - Šířka pásma: přenosová rychlost mezi uzly
    - Režie: zpracování zpráv na odesílacím a přijímacím uzlu
  - Pomáhá optimalizovat komunikaci mezi uzly a snižovat dobu odezvy

![cost](cost.png)

### Polygot persistance

Polyglot persistence je koncept ve správě databází, který zahrnuje použití různých technologií ukládání dat k efektivnějšímu zpracování různých typů datových potřeb v rámci jediné aplikace. Namísto spoléhání se na jednu databázi pro ukládání všech druhů dat, polyglot persistence obhajuje výběr nejlepšího úložného řešení na základě konkrétních požadavků na typ dat, vzorce použití nebo potřebnou funkci. Tento přístup uznává, že žádná jednotlivá databáze nemůže být optimálně efektivní pro všechny druhy dat a dotazů.

- V praxi může platforma elektronického obchodu používat kombinaci databází, jako jsou:
    - Relační databáze pro zpracování transakcí a správu zásob.
    - Úložiště dokumentů pro uživatelské profily a přizpůsobená nastavení.
    - Databáze vyhledávačů pro katalogy produktů a vyhledávací funkce.
    - Databáze grafů pro doporučení založená na uživatelských vztazích a spojeních produktů.
    - Celkově lze říci, že polyglot persistence je o výběru správného nástroje pro správnou práci, maximalizaci efektivity aplikace prostřednictvím strategického využití databáze při zohlednění přidané složitosti a integračních problémů, které tento přístup přináší.

## MapReduce (architecture, functions, data ﬂow, execution, use cases). Hadoop (MapReduce, HDFS).

### MapReduce:
- Architektura:
  - Programovací model pro paralelní a distribuované zpracování velkého množství dat
  - Skládá se ze dvou hlavních funkcí: Map a Reduce
  - Obvykle se provádí na clusterech

![alt text](progmodel.png)
![alt text](defmapreduce.png)

- Funkce:
  1. Map: zpracování vstupních dat, transformace na páry klíč-hodnota
  2. Reduce: agregace páru klíč-hodnota podle klíče a výpočet výsledku

![alt text](mapreducefunctions.png)
![alt text](mapreducefunctions2.png)
![alt text](mapreducefunctions3.png)

- Datový tok:
  1. Vstupní data jsou rozdělena do částí (shard)
  2. Map funkce se spustí na každém shardu paralelně a generuje páry klíč-hodnota
  3. Páry klíč-hodnota jsou seskupeny podle klíčů
  4. Reduce funkce zpracovává seskupené páry klíč-hodnota a vypočítá výsledky

- Provedení:
  1. Job Tracker: koordinuje celý proces, rozděluje úkoly, sleduje pokrok
  2. Task Tracker: zpracovává map a reduce úkoly na jednotlivých uzlech

- Příklady použití:
  - Analýza textu a počítání slov
  - Zpracování log souborů a analýza webového provozu
  - Vyhledávání vzorů v datech
  - Strojové učení a statistické analýzy

### Provedení ze slidů

![alt text](step1.png)
![alt text](step2.png)
![alt text](step3.png)
![alt text](step4.png)
![alt text](step5.png)
![alt text](step6.png)
![alt text](step9.png)
![alt text](step10.png)
![alt text](step11.png)
![alt text](step12.png)
![alt text](step13.png)
![alt text](step14.png)
![alt text](step15.png)

lze použít combine function

![alt text](combine.png)

komutativita -> x . y = y . x

asociativita -> (x . y) . z = x . (y . z)

Idempotence je v matematice, zejména v abstraktní algebře, vlastnost algebraických operací či prvků nějaké algebry. Operace je idempotentní, pokud jejím opakovaným použitím na nějaký vstup vznikne stejný výstup, jako vznikne jediným použitím dané operace. Tato vlastnost se vyskytuje například v lineární algebře u projekcí, je to také jedna z definičních vlastností uzávěrového operátoru. Například min(x, x) = x

![alt text](step16.png)
![alt text](summary.png)

### Hadoop:
- Open-source framework pro distribuované zpracování velkého množství dat
- Hlavní komponenty:
  1. Hadoop MapReduce
  2. Hadoop Distributed File System (HDFS)

### Hadoop MapReduce:
- Implementace MapReduce modelu pro zpracování dat v Hadoopu
- Řídí paralelní zpracování dat pomocí map a reduce funkcí
- Podporuje škálování, odolnost vůči výpadkům a distribuci dat
- Řeší Fault tolerance = nějaký node selže (master i slave)
- Řeší Straggler - worker pracuje příliš dlouho, vyměním ho

### HDFS - Hadoop Distributed File System:

- Hlavní komponenty HDFS:
  1. NameNode
  2. DataNode

- NameNode:
  - Ústřední server pro správu metadata souborového systému
  - Udržuje informace o adresářové struktuře, právech, a umístění bloků dat
  - Komunikuje s DataNode pro správu uložených dat
  - HDFS může mít jednu aktivní a jednu nebo více pasivních (záložních) NameNode
  - Pasivní NameNode synchronizuje data s aktivní NameNode pro zajištění odolnosti vůči výpadkům

![alt text](namenode.png)

- DataNode:
  - Servery, které skutečně ukládají data na disky
  - Data jsou uložena ve formě bloků s pevnou velikostí (např. 64 MB nebo 128 MB)
  - DataNode komunikuje s NameNode a zpracovává požadavky na čtení/zápis dat
  - Data jsou automaticky replikována na více DataNode pro zajištění dostupnosti a odolnosti vůči výpadkům

![alt text](datanode.png)
- Práce s HDFS:
  1. Uživatel pošle požadavek na čtení/zápis dat na NameNode
  2. NameNode zkontroluje metadata a v případě zápisu vybere vhodné DataNode pro uložení dat
  3. Uživatel komunikuje přímo s vybranými DataNode pro čtení nebo zápis dat
  4. Po dokončení zápisu informuje DataNode NameNode o úspěšném uložení dat

- HDFS je navržen pro:
  1. Ukládání velkých souborů
  2. Paralelní zpracování dat
  3. Vysokou propustnost a odolnost vůči výpadkům
  4. Integraci s Hadoop MapReduce pro efektivní zpracování dat

![alt text](hadoopusecase.png)

## XPath (path expressions, axes, node tests, predicates). XQuery (constructors, FLWOR, conditional, quantiﬁed and comparison expressions). SPARQL (subgraph matching, graph patterns, datasets, ﬁlters, solution modiﬁers, query forms).

### XPath

- XPath
  - Cesta vyjadřuje umístění uzlů v XML dokumentu
  - Používá se pro vyhledávání dat v XML dokumentech

![alt text](xpath1.png)
- Výrazy cesty
  - Absolutní: Začínají od kořenového uzlu (např. `/kniha/nazev`)
  - Relativní: Začínají od aktuálního uzlu (např. `./nazev`)
- Osy
  - child: Bezprostřední potomci aktuálního uzlu
  - descendant: Všichni potomci aktuálního uzlu
  - parent: Rodič aktuálního uzlu
  - ancestor: Všichni předkové aktuálního uzlu
  - sibling: Sourozenci aktuálního uzlu
    ![alt text](xpath2.png)
    ![alt text](xpath3.png)
- Testy uzlů
  - node(): Vybere všechny uzly
  - text(): Vybere všechny textové uzly
  - comment(): Vybere všechny komentářové uzly
  - processing-instruction(): Vybere všechny uzly zpracovávající pokyny
    ![alt text](xpath4.png)
- Predikáty
  - Umožňují filtrovat výsledky XPath výrazů
  - Uzavírají se do hranatých závorek (např. `/kniha[nazev='Mistr a Markétka']`)
  - Často se používají s operátory a funkcemi (např. `not()`, `and`, `or`)
    ![alt text](xpath5.png)

### XQuery

- XQuery
  - Jazyk pro dotazování a manipulaci s XML a JSON dokumenty
  - Má vyšší výrazovou sílu než XPath
- Konstruktory
  - Element: `<jmeno>{obsah}</jmeno>`
  - Atribut: `attribute jmeno {"hodnota"}`
  - Text: `text {"obsah"}`
  - Komentář: `comment {"komentář"}`
  - Zpracovávací pokyn: `processing-instruction jmeno {"hodnota"}`
  ![alt text](xquery1.png)
- FLWOR
  - Pro vyhledávání a transformaci dat
  - F: For - prochází kolekcemi
  - L: Let - přiřazuje hodnotu proměnné
  - W: Where - podmínka pro filtrování
  - O: Order by - řazení výsledků
  - R: Return - vrácení výsledku
    ![alt text](flowr1.png)
    ![alt text](flowr2.png)
- Podmínkové výrazy
  - if (podmínka) then (výraz1) else (výraz2)
    ![alt text](flowr3.png)
- Kvantifikované výrazy
  - every $x in (sekvence) satisfies (podmínka)
  - some $x in (sekvence) satisfies (podmínka)
    ![alt text](flowr4.png)
- Porovnávací výrazy
  - '=', '!=', '<', '>', '<=', '>='
  - 'eq', 'ne', 'lt', 'gt', 'le', 'ge'

### SPARQL

![alt text](sparql1.png)
![alt text](sparql2.png)
- SPARQL
  - Jazyk pro dotazování a manipulaci s RDF grafovými daty
  - Používá se pro práci s daty ve formátu RDF
- Subgrafické porovnávání
  - Hledání vzorů v RDF grafech
  - Provádí se pomocí trojic subjekt-predikát-objekt
- Grafové vzory
  - Základní: Jednoduché trojice (např. `?x rdf:type foaf:Person`)
  - Volitelné: Používají klíčové slovo OPTIONAL (např. `OPTIONAL {?x foaf:mbox ?email}`)
  - Alternativní: Používají klíčové slovo UNION (např. `{?x foaf:name ?name} UNION {?x rdfs:label ?name}`)
- Datasety
  - Default: Graf, který je vyhledáván implicitně
  - Named: Grafy, které jsou vyhledávány explicitně pomocí klíčového slova FROM NAMED
- Filtry
  - Omezují výsledky dotazu podle zadaných podmínek
  - Používají klíčové slovo FILTER (např. `FILTER (?age >= 18)`)
- Modifikátory řešení
  - Order by: Řazení výsledků (např. `ORDER BY ?name`)
  - Limit: Omezení počtu výsledků (např. `LIMIT 10`)
  - Offset: Posunutí výsledků (např. `OFFSET 5`)
  - Distinct: Odstranění duplikátů (např. `SELECT DISTINCT ?name`)
- Formy dotazů
  - SELECT: Výběr proměnných
  - CONSTRUCT: Vytváření nových RDF trojic
  - ASK: Dotaz na existenci vzoru
  - DESCRIBE: Popis zdrojů RDF
  
    ![alt text](sparql3.png)
    ![alt text](sparql4.png)
    ![alt text](sparql5.png)
    ![alt text](sparql6.png)


## RiakKV (CRUD operations, links, link walking, convergent replicated data types, Search 2.0, vector clocks, Riak Ring, replica placement strategy). Redis (data types, operations, TTL). Cassandra (keyspaces, column families, CRUD operations). MongoDB (CRUD operations,update and query operators, projection, modiﬁers).

### RiakKV 

- RiakKV
  - Distribuovaný **klíč-hodnota** úložiště
  - Navržený pro vysokou dostupnost a škálovatelnost
- CRUD operace
  - Create: Vytvoření hodnoty s klíčem
  - Read: Čtení hodnoty podle klíče
  - Update: Aktualizace hodnoty s klíčem
  - Delete: Smazání hodnoty s klíčem
- Odkazy (links)
  - Reprezentují vztahy mezi objekty v RiakKV
  - Umožňují navigaci mezi objekty
- Procházení odkazů (link walking)
  - Prohledávání objektů v RiakKV pomocí odkazů
  - Zahrnuje kroky ve formátu "kbelík,tag,řetězec"
- Konvergentní replikované datové typy (CRDT)
  - Umožňují konzistentní replikaci dat v distribuovaném systému
  - Zahrnuje: množiny, mapy, flagy, registry a čítače
- Search 2.0
  - Full-textové vyhledávání v RiakKV
  - Založeno na Apache Solr
- Vektorové hodiny (vector clocks)
  - Algoritmus pro řešení konfliktů v distribuovaném systému
  - Sleduje verze objektů a řeší konflikty
- Riak Ring
  - Struktura pro rozdělení dat v RiakKV
  - Zajišťuje škálovatelnost a toleranci selhání
- Strategie umístění replik (replica placement strategy)
  - Určuje, jak a kde jsou repliky uloženy v RiakKV
  - Zahrnuje: uniformní, zónování a vlastní strategie

![alt text](riak1.png)
![alt text](riak2.png)

![RiakKV Ring](riak-ring.png)

### Redis

- Redis
  - Výkonný klíč-hodnota úložiště v paměti
  - Podporuje rozmanité datové typy
- Datové typy
  - Řetězce (strings)
  - Seznamy (lists)
  - Množiny (sets)
  - Uspořádané množiny (sorted sets)
  - Mapy (hashes)
  - Bitmapy (bitmaps)
  - HyperLogLogs
- Operace
  - GET, SET: Čtení a zápis řetězců
  - LPUSH, RPUSH, LPOP, RPOP: Práce se seznamy
  - SADD, SREM, SISMEMBER: Práce s množinami
  - ZADD, ZRANK, ZRANGE: Práce s uspořádanými množinami
  - HSET, HGET, HDEL: Práce s mapami
- TTL (Time-To-Live)
  - Expirace klíčů po určité době
  - SETEX, PSETEX: Nastavení TTL při zápisu
  - EXPIRE, PEXPIRE: Nastavení TTL pro existující klíč
  - TTL, PTTL: Získání zbývajícího času do expirace

![alt text](redis1.png)
![alt text](redis2.png)
![alt text](redis3.png)
![alt text](redis4.png)

### Cassandra

- Cassandra
  - Distribuovaná databáze s vysokou škálovatelností a dostupností
  - Navržená pro práci s velkým množstvím dat
- Keyspaces
  - Kontejnery pro ukládání sloupcových rodin (column families)
  - Definují replikační faktor a strategii
- Column families
  - Ukládají data v Cassandra
  - Skládají se ze sloupců a řádků
- CRUD operace
  - CREATE: Vytvoření keyspace, tabulky nebo indexu
  - INSERT: Vložení nebo aktualizace záznamu
  - SELECT: Čtení záznamů
  - UPDATE: Aktualizace záznamu
  - DELETE: Smazání záznamu nebo části záznamu

Keyspaces v Apache Cassandra jsou obdobou databází v relačních databázových systémech (RDBMS). Jsou to nejvyšší kontejnery pro data v Cassandře a hrají klíčovou roli v organizaci dat, správě replikace a definování možností ukládání dat. Zde je podrobný přehled o keyspaces v Cassandře:

Definice Keyspace
Keyspace v Cassandře je jmenný prostor, který definuje replikaci dat na uzlech. Obsahuje sadu tabulek a je vytvořen pomocí specifické konfigurace, která definuje, jak jsou data replikována napříč clusterem.

Vytvoření Keyspace
Pro vytvoření keyspace se používá příkaz CREATE KEYSPACE. Tento příkaz zahrnuje specifikaci replikační strategie a dalších možností.

Příklad:

sql
Copy code
CREATE KEYSPACE my_keyspace
WITH replication = {
  'class': 'SimpleStrategy',
  'replication_factor': 3
};

Column families (sloupce rodiny) v Apache Cassandra jsou základními stavebními kameny pro ukládání dat. Každá tabulka v Cassandře je ve skutečnosti sloupcová rodina, což znamená, že Cassandra je sloupcově orientovaná databáze. Zde je podrobný přehled o sloupcových rodinách v Cassandře:

Struktura Column Family
Row Key: Každá sloupcová rodina obsahuje řádky, které jsou identifikovány jedinečným klíčem řádku. Klíč řádku slouží jako primární klíč.

Columns: Každá řádka obsahuje sadu sloupců. Každý sloupec má jméno, hodnotu a časovou značku (timestamp). Sloupce mohou být přidány nebo odstraněny dynamicky bez předchozího definování struktury.

Super Columns: Jedná se o strukturu sloupce, který sám obsahuje další sloupce. Super sloupce nejsou běžně používané v moderních verzích Cassandry, ale je dobré o nich vědět pro historický kontext.

Vytvoření Column Family
Column family (tabulka) se vytváří pomocí příkazu CREATE TABLE. Při vytváření tabulky musíte definovat její název a sloupce.

Příklad:

sql
Copy code
CREATE TABLE users (
    user_id UUID PRIMARY KEY,
    username TEXT,
    email TEXT,
    age INT
);
Primární Klíče
Partition Key: Hlavní část primárního klíče, která určuje, jak jsou data rozložena napříč uzly v clusteru.
Clustering Columns: Umožňují řadit a organizovat data uvnitř partice.
Příklad s kombinovaným primárním klíčem:

sql
Copy code
CREATE TABLE orders (
    user_id UUID,
    order_id UUID,
    product_id UUID,
    order_date TIMESTAMP,
    PRIMARY KEY (user_id, order_id)
);

CQL neumí joiny, takže je to extrémně rychlý


![alt text](cassandra0.png)
![alt text](cassandra1.png)
![alt text](cassandra2.png)
![alt text](cassandra3.png)
![alt text](cassandra4.png)
![alt text](cassandra5.png)
![alt text](cassandra6.png)
![alt text](cassandra7.png)
![alt text](cassandra8.png)
![alt text](cassandra9.png)

### MongoDB

- MongoDB
  - Dokumentová databáze s vysokou škálovatelností a flexibilitou
  - Ukládá data ve formátu BSON (binární JSON)
- CRUD operace
  - Create: Vytvoření dokumentu (db.kolekce.insert())
  - Read: Čtení dokumentů (db.kolekce.find())
  - Update: Aktualizace dokumentů (db.kolekce.update())
  - Delete: Smazání dokumentů (db.kolekce.remove())
- Operátory aktualizace
  - $set: Nastavení hodnoty pole nebo vytvoření nového pole
  - $unset: Odstranění pole
  - $inc: Inkrementace hodnoty pole
  - $mul: Násobení hodnoty pole
  - $rename: Přejmenování pole
- Operátory dotazování
  - $eq: Rovnost
  - $gt, $gte: Větší než, větší než nebo rovno
  - $lt, $lte: Menší než, menší než nebo rovno
  - $ne: Nerovnost
  - $in: Hodnota je v seznamu
  - $nin: Hodnota není v seznamu
  - $and, $or, $not: Logické operátory
- Projekce
  - Určuje, která pole vrátit v dotazu
  - 1 pro zobrazení pole, 0 pro skrytí pole (např. `{pole: 1}`)
- Modifikátory
  - $limit: Omezení počtu vrácených dokumentů
  - $skip: Přeskočení určitého počtu dokumentů
  - $sort: Řazení dokumentů podle zadaných kritérií

![alt text](mongo1.png)
![alt text](mongo2.png)
![alt text](mongo3.png)
![alt text](mongo4.png)
![alt text](mongo5.png)
![alt text](mongo6.png)
![alt text](mongo7.png)
![alt text](mongo8.png)
![alt text](mongo9.png)

## Graph data structures (adjacency matrix, adjacency list, incidence matrix). Data locality (BFS layout, bandwidth minimization problem, Cuthill-McKee algorithm). Graph partitioning (1D partitioning, 2D partitioning). Neo4j (traversal framework, traversal description, traverser). Cypher (graph matching, read, write and general clauses).

## Grafové datové struktury

- Grafové datové struktury
  - Používány pro reprezentaci grafů (sítí, diagramů) v paměti počítače
  - Základní struktury: maticová a seznamová reprezentace
- Matice sousednosti (adjacency matrix)
  - Čtvercová matice, která popisuje vztahy mezi vrcholy grafu
  - V[i][j] = 1, pokud vrcholy i a j sousedí, jinak 0
  - Pro vážené grafy: V[i][j] = váha hrany, pokud vrcholy i a j sousedí, jinak 0
  - Výhody:
    - Rychlé zjištění, zda mezi vrcholy existuje hrana
    - Jednoduchá implementace
  - Nevýhody:
    - Nevhodné pro řídké grafy (mnoho nulových hodnot)
    - Vyšší paměťová náročnost
- Seznam sousednosti (adjacency list)
  - Pole seznamů, kde každý seznam obsahuje sousedy daného vrcholu
  - V[i] = seznam sousedních vrcholů vrcholu i
  - Pro vážené grafy: V[i] = seznam dvojic (soused, váha hrany)
  - Výhody:
    - Nižší paměťová náročnost pro řídké grafy
    - Rychlé procházení sousedů daného vrcholu
  - Nevýhody:
    - Pomalejší zjištění, zda mezi vrcholy existuje hrana
    - Složitější implementace
- Matice incidence (incidence matrix)
  - Matice, která popisuje vztahy mezi vrcholy a hranami grafu
  - V[i][j] = 1, pokud vrchol i je spojen s hranou j, jinak 0
  - Pro orientované grafy: V[i][j] = -1, pokud hrana j vychází z vrcholu i; V[i][j] = 1, pokud hrana j vstupuje do vrcholu i
  - Výhody:
    - Jednoznačně reprezentuje orientované i neorientované grafy
    - Umožňuje rychle zjistit, které vrcholy jsou spojeny s danou hranou
  - Nevýhody:
    - Vyšší paměťová náročnost než seznam sousednosti
    - Pomalejší procházení sousedů daného vrcholu

![alt text](matrix1.png)
![alt text](matrix2.png)
![alt text](matrix3.png)


### Data locality

- Data locality
  - Optimalizace přístupu k datům v počítačové paměti
  - Zlepšuje výkon a efektivitu paměti
- BFS layout (Breadth-First Search)
  - Uspořádání dat v paměti podle BFS procházení grafu
  - Výhody:
    - Zlepšuje data locality pro algoritmy založené na BFS
    - Snížení latence při přístupu k sousedním vrcholům
- Bandwidth minimization problem
  - Problém minimalizace šířky pásma matice
  - Cílem je přeuspořádat řádky a sloupce matice tak, aby neprázdné prvky byly co nejblíže hlavní diagonále
  - Redukce šířky pásma zlepšuje data locality
- Cuthill-McKee algoritmus
  - Heuristický algoritmus pro řešení problému minimalizace šířky pásma
  - Postup:
    1. Vyberte vrchol s nejnižším stupněm jako kořen
    2. Proveďte BFS procházení grafu od kořene
    3. Přeuspořádejte vrcholy podle BFS pořadí
  - Výhody:
    - Snadno implementovatelný
    - Zpravidla dává dobré výsledky
  - Nevýhody:
    - Ne vždy najde optimální řešení

![alt text](locality1.png)
![alt text](locality2.png)


### Graph partitioning

- Grafové rozdělení (Graph partitioning)
  - Proces rozdělení grafu na menší části (partice) s cílem optimalizovat výkon
  - Používá se při paralelizaci, distribuovaném zpracování a zefektivnění úložiště

- 1D rozdělení (1D partitioning)
  - Graf je rozdělen na partice podél jednoho rozměru (řádky nebo sloupce)
  - Používá se např. při rozdělení matice na bloky pro paralelní zpracování
  - Výhody:
    - Jednoduchá implementace
    - Snadné rozdělení zátěže mezi procesory nebo uzly
  - Nevýhody:
    - Může vést k nerovnoměrnému rozložení zátěže, pokud graf není rovnoměrně rozdělitelný
    - Méně efektivní pro grafy s nerovnoměrným rozložením hran

- 2D rozdělení (2D partitioning)
  - Graf je rozdělen na partice podél dvou rozměrů (řádky a sloupce)
  - Výhody:
    - Lepší vyvážení zátěže než u 1D rozdělení
    - Efektivnější pro grafy s nerovnoměrným rozložením hran
  - Nevýhody:
    - Složitější implementace
    - Vyšší režie při komunikaci mezi procesory nebo uzly

### Neo4j

- Neo4j
  - Grafická databáze s vysokou škálovatelností a flexibilitou
  - Umožňuje efektivní prohledávání a manipulaci s grafy
- Traversal framework
  - Rámec pro průchod grafem v Neo4j
  - Umožňuje efektivně a flexibilně procházet grafem za účelem hledání vzorů, cest a dalších struktur
- Traversal description (Popis průchodu)
  - Definuje, jak má být graf procházen
  - Specifikuje:
    - Výchozí vrcholy (start nodes)
    - Procházení směrem (vstupní/výstupní hrany)
    - Typy hran a vrcholů, které mají být zahrnuty
    - Hloubka průchodu (maximální počet kroků)
    - Evaluatory a pravidla pro zahrnutí vrcholů a hran do výsledku
- Traverser
  - Objekt, který provádí průchod grafem podle zadaného traversal description
  - Vrací výsledné vrcholy a hrany, které splňují zadaná pravidla
  - Umožňuje iterativní přístup k výsledkům průchodu

![alt text](neo1.png)
![alt text](neo2.png)
![alt text](neo3.png)
![alt text](neo4.png)

### Cypher

- Cypher
  - Deklarativní jazyk pro práci s grafy v Neo4j
  - Umožňuje jednoduché a efektivní dotazování a manipulaci s grafy
- Graph matching
  - Prohledávání grafu za účelem nalezení vzorů a struktur
  - Používá ASCII-art notaci pro definici vzorů
  - Např. `(a)-[:ZNÁ]->(b)` najde všechny vrcholy `a` a `b`, které jsou spojeny hranou typu "ZNÁ"
- Read clauses (Přečíst klauzule)
  - Klauzule pro čtení dat z grafu
  - MATCH: Hledání vzorů v grafu
  - WHERE: Filtrování výsledků podle zadaných podmínek
  - RETURN: Vracení výsledků dotazu
  - WITH: Průběžné zpracování výsledků (řazení, filtrování, aliasy)
  - UNWIND: Rozbalení seznamů na jednotlivé prvky
  - SKIP, LIMIT: Omezení počtu vrácených výsledků
  - ORDER BY: Řazení výsledků podle zadaných kritérií
- Write clauses (Zapsat klauzule)
  - Klauzule pro zápis a manipulaci dat v grafu
  - CREATE: Vytvoření nových vrcholů a hran
  - MERGE: Vytvoření vrcholu nebo hrany, pokud neexistuje, jinak aktualizace
  - SET: Nastavení vlastností vrcholů a hran
  - DELETE: Smazání vrcholů a hran
  - REMOVE: Odstranění vlastností nebo štítků z vrcholů
- General clauses (Obecné klauzule)
  - Klauzule pro řízení dotazů a nastavení
  - USING INDEX: Vynucení použití indexu pro dotaz
  - CALL: Volání uložených procedur a funkcí
  - LOAD CSV: Načítání dat ze CSV souboru
  - FOREACH: Provedení akce pro každý prvek seznamu

![alt text](cypher1.png)
![alt text](cypher2.png)
![alt text](cypher3.png)
