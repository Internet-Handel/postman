# Architektura

Technický návrh systému. Nebude možné zde popsat všechny aspekty řešení. Jsou zde popsané jen některé části.

## Bezpečnost

V návrhu budeme vycházet z toho, co nabízí symfony framewok. Detaily jsou popsané na [symfony.com/doc/current/security.html](https://symfony.com/doc/current/security.html). Systém využívá hierarchické role. V našem případě hierarchie bude vypadat takto:

![Hierarchie rolí][arch-04]

## Kód balíku

Kód balíku musí splňovat několik vlastností:

* I po lidské chybě, jako je záměna dvou znaků, nebo překlep jednoho znaku musíme být schopní balíček dohledat.
* Kód se musí pohodlně číst a opisovat.
* Nebude rozlišovat velká a malá písmena.
* Nesmí obsahovat znaky, v které se často zaměňují jako jsou:
    * nula a ```O```.
    * jedna a ```L```.

Jedno z možných řešení je, že se kód kód bude skládat ze tří pomlčkou oddělených částí po čtyřech znacích: ```XXXX-XXXX-XXXX```. Jednotlivé znaky budem náhodně generovat z těchto skupin:

* Souhlásky - ```b, c, d, f, g, h, j, k, m, n, p, r, s, t, v, x, z```
* Samohlásky a číslice - ```a, e, y, u, 2, 3, 4, 5, 6, 7, 8, 9```

Každá čtveřice bude vygenerovaná tak, že se budou střídat náhodné znaky z obou skupin. Střídat můžem i pořadí skupin. Například:

* ```K3GE-DAM8-ERUS```
* ```AT3K-8P3D-B4M6```

Variant kódu balíku bude:

![Variant kódu balíku][arch-03]

Pro každý balík, bude tento kód balíku vygenerovaný a uložený. Když operátor zadá kód balíku, pomocí nějakého algoritmu pro zjištění podobnosti dvou řetězců a najdeme ten, který v nějaké toleranci odpovídá. Jako inspirace lze použít Levenshteinovu vzdálenost. Pro hledání balíků podle kódu lze využít [SOLR](https://lucene.apache.org/solr/), kde již je Levenshteinova vzdálenost implementovaná.

Kódů balíků by měl být unikátní. Pokud se při jeho generování stane, že se vygeneruje již existující, pak se zahodí a systém zkusí vygenerovat další, dokud se netrefí do nepoužitého kódu balíku.

## Kód interního štítku balíku

**TODO TECH - Jak dlouhý bude? Podle specifikace čárového kódu?**

Jedná se o náhodné XXX místné číslo. Toto číslo se přiděluje balíku při přijetí. Je bezvýznamové a  není spjato s objednávkou nebo zákazníkem. Není spjato, protože při přijetí balíku se nemusí podařit dohledat ani objednávka ani zákazník. Kód na interním štítku balíku bude vytištěn jako čárový kód i jako čísla.

Kód interního štítku balíku bude náhodné číslo. Náhodné, abychom je mohli dobře odlišit. Je možné, že budem implementovat hledání podle poškozené části. V aktuálním něvrhu to není.

## Variabilní symbol a číslo objednávky
Variabilní symbol pro zaplacení objednávky a číslo objednávky budou jedna hodnota. Bude to unikátní desetimístné náhodně vygenerované číslo. To, že je to desetimístné číslo plyne z formátu variabilního symbolu.

## Číslo daňového dokladu
Daňové doklady jako jsou faktury a dobropisy musí být rozlišitelné podle jejich čísla. Pro všechny daňové doklady použijem 13 místné číslo složene z čísla objednávky doplněné pořadovým číslem daňového dokladu v objednávce. Například pro objednávku č.: ```9812563321``` bude mít faktura č.: ```9812563321001```.

## Entita zákazníka

V některých případech by bylo dobré mít samostatnou entitu zákazníka a k ní napojené objednávky. Například bychom mohli lépe určit zákazníka podle čísla účtu příchozí platby. Toto teď nebudem implementovat. Entitu zákazníka odvodíme od entity uživatele.

## Entitní model
Zde budou popsány vztajy mezi objekty a základní set attributů.

Vztahy mezi základními objekty budou vypadat takto:

![Přehled][arch-01]

#### Měření

Měření balíku děláme ve dvou prípadech. V prvním ho prvede zákazník při zadávání objednávky a v druhém ho provádí dispečer v interních procesech. V obou případech se jedná o stejná data.

### Objednávka

**TODO**

### Události balíku

Událost nese informaci o tom, co se v daném okamžiku s balíkem stalo. Událost je jednorázový objekt, který se pořídí a dál nemění. Chceme ho zachovat i v případě, že původní objekt zanikne, nebo se upraví. Obsahuje attributy:
 
* O jakou událost se jedná, příklady jsou na obrázku níž.
* Odkaz na balík, kterého se událost týká.
* Kdo událost vykonal. To můze být libovolný zaměstnanec, zákazník nebo to v budoucnu může být nějaký proces.
* Datum vzniku události.
* Odkaz na sledovaný objekt nebo atributy, které se k události pojí. Sledovaný objek je objekt, kterého se událost týká, například připárovaný balík.

V některých případech by událost měla být samostatný objekt a sledovaný objekt druhý samostatný objekt. Událost měla být samostatně uložená od sledovaného objektu Pokud událost splní nekré z následujících bodů: 

* Sledovaný objekt může být odstraněn nebo změněn, přitom stále potřebujeme znát původní hodnoty.
* Během existence sledovaného objektu můžeme potřebovat víc událostí.

Návrh vztahů mezi objekty:

![Události][arch-05]

### Balík a jeho stavy
U balíku se uchovává:

* Stav balíku - ze stavů je možné vyčíst, co se dějě a řídit, co se má stát.
* Událost - jednorázová událost, která nemění stav balku. Například měření a vážení.

![Události balíku](./diagrams/out/arch-02.png "Události balíku")

#### Stavy balíku
U balíku je třeba evidovat několik různých stavů. Jednotlivé stavy se od sebe mohou lišit počtem atributů a způsobem práce s nimi. Například stav "Poškozený balík" může být přiřazen na dispečera nebo pracovníka podpory. Ostatní stavy jsou vždy přiřazeny na jednu roli. Například pokud je balík ve frontě, kde čeka na zaplacení, tak pouze pracovník podpory může říct, že je balík zaplacen a přesunout ho do fronty konkrétního doporavce.

![Stavy balíků][arch-02]

## Návrh architektury applikace
Z počátku nepotřebujem nic speciálního. Pouze při realizací dávat pozor, že finální UC se mohou lišit od návrhů. Například implementace napojení na konkrétního dopravce může ovlivnost způsob zpracování fronty dopravce. Například požadavek na validaci adresy ze strany dopravce může vést k tomu, že při přijetí balíku a po jeho spárování s objednávkou se musí přidat validace adresy.

## Auditní log
Systém nebude bezpečný. Bude možné vystavit fakturu zákazníkovy, změnit doručovací adaresu a podobné bez obvyklých kontrol. Z těchto důvodů budou změny ukládány do speciálního auditního logu. Log nebude systémem dále využíván. Pro kontrolu by nad ním měl být vybudovaný nějaký jednoduchý BI systém. Auditní log by měl být textový soubor, kde jednotlivé řádky budou představovat jednotlivé události. Událost se bude skládat z několika vhodně oddělenými poli v následujícím poředí:

* Datum a čas vzniku události.
* Kdo událost vyvolal. Zde bude systém, nebo jméno konkrétního uživatele.
* V jakém UC byla událost vyvolaná.
* O jaký druh entity se jedná.
* Identifikace měněné entity.
* Popis změny. Například když pracovník změní doručovací adresu, pak by zde měla být nová adresa.
* Jakékoliv další informace, které později můžou pomoct.

Auditní log by se měl z bezpečnostních důvodů uládat jinam než provozní logy.

##Poznámky
Co by mělo platit:

* Při založení objednávky musí vzniknout instance balíku. Na ní je uložen kód balíku.
* Balík, který se při přijetí nepodaří spojit s objednávkou, nemusí mít kód balíku.


## Zajímavé odkazy
Další informace jsou na:

* Wikipedia, Kontrolní číslo - [https://en.wikipedia.org/wiki/Check_digit](https://en.wikipedia.org/wiki/Check_digit)
* Wikipedia, Levenshteinova vzdálenost - [https://en.wikipedia.org/wiki/Levenshtein_distance](https://en.wikipedia.org/wiki/Levenshtein_distance)
* Wikipedia, Variabilní symbol - [https://cs.wikipedia.org/wiki/Variabilní_symbol](https://cs.wikipedia.org/wiki/Variabiln%C3%AD_symbol)
* Wikipedia, Čárový kód - [https://cs.wikipedia.org/wiki/Čárový_kód](https://cs.wikipedia.org/wiki/Čárový_kód)

[arch-01]: ./diagrams/out/arch-01.png "Přehled"
[arch-02]: ./diagrams/out/states-package-2.png "Stavy balíků"
[arch-03]: ./diagrams/out/arch-03.png "Variant kódu balíku"
[arch-04]: ./diagrams/out/arch-04.png "Hierarchie rolí"
[arch-05]: ./diagrams/out/arch-05.png "Události"
