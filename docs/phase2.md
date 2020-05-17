# Fáze 2
Zatím zde budeme neuspořádaně ukládat co víme, že budeme chtít.

Hlavní cíl fáze 2. je umožnit hromadné podání. Z toho plyne, že bude potřeba podporovat:

* Evidenci zákazníků. 
* Řešení UC pro zákazníka jako přihlašování, zapomenuté heslo, zmena hesla, zapomenutý login, ... 
* Zákazník bude platit:
    * Nějakou část dopředu - předplacení služeb.
    * Budeme mu na doručování balíků nějakou částku půjčovat, po jejím vyčerpání budeme čekat na zaplacení.
* Výběr měny, lokalizace a cíle doručení v závislosti na příchozích informacích z kampaně a domény je popsáno v [ticketu 35][issue35].
* colli - balíky v balíku. Bude to šetřit prostředky.
* ...
* ...


## 	

## 

## Domény a jazyk a přepínaní mezi nimi

Zadání a příklady jsou popsane na [Issue 35][issue35].

Use case zákazníků:

* Zákazník Čech chce poslat balík z Čech do Polska.
* Švýcarsko má více jazyků, pro Švýcary by bylo dobré mít možnost změnit jazyk.
* Zákazník Němec nás často používá a chce poslat balíček z jiné země, kde teď je - použije .de doménu, ale chce si vybrat odkud třeba Polsko a kam třeba Německo.
* Zákazník Čech posílá balík do Anglie, která má jiný formát adresy.
* Zákazník Čech posílá balík z Česka do Německa a chce platit v €.

Dál do toho vstupuje lokalizovaná doména, například postman.cz nebo postman.de a měna v jaké lze platit za doručení a ďaňový domicil. Otazky:

- Budeme potřebovat mít různé jazykové mutace na jedné doméně?
- Předávaní parametrů z googlu, jaké to jsou. Nemají vliv na URL? 

## Zákazník

Zatím spíš otázky:

- Budeme chtít provozovat zadávací formulář UC-4 pro koncové zákazníky ve fázi 2?
- Co vše potřebujeme o zákazníkovi uchovávat:
    - fakturační adresu.
    - zpáteční adresu.
- Budou informace o zákaznících lokalizovány? Například počet polí se bude v různých zemí lišit?

## 

## 


[issue35]: https://bitbucket.org/internethandel/postman/issues/35
