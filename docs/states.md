# Stavy

Objednávky a balíky během vyřizování procházejí několika stavama. V první verzi, kde budeme mít právě jeden balík na objednávky, bude možné následující stavy spojit v jeden.

## Stavy objednávek

Objednávka prochází následujícími stavy:

![Stavy objednávky](./diagrams/out/states-order.png "Stavy objednávky")

###Stav "Nezaplacená"
To, jestli zákazník zaplatil by mohlo byt hodnoceno automaticky. Třeba porovnáním součtu částek daňových dokladů a součtu plateb. Bohužel to takto zjednodušit nelze. Některé daňové doklady nemusí být uhrazeny nebo proplaceny a je to tak v pořádku, stejně tak součet částek na daňových dokladech nemusí být stejný jako součet plateb a také to může být v pořádku. 

Přechod mezí stavy "Nezaplacená" a "Doručovaná" se provede ve chvíli, kdy zákazník zaplatí. V některých případech k zaplacení nedojde, zákazník může zrušit objednávku.

###Stav "Doručovaná"
O objednávce v tomto stavu víme, že s balíkem se ještě nějak pracuje a je třeba sledovat jestli doručovací proces běží. 

###Stav "Ukončená"
V tomto stavu máme objednávku kompletně ukončenou, všechny doručované balíky jsou také ukončeny a finance vypořádány.

## Stavy balíku
U balíku je třeba znát historii stavů. To je potřeba pro reklamace a evidenci pohybu balíku. Historii stavů lze později využít pro optimalizaci procesů.

Balík během doručování prochází následujícími stavy:

![Stavy balíku](./diagrams/out/states-package.png "Stavy balíku")

###Stav "Na cestě"
Balík bude ve stavu "Na cestě" aspoň dvakrát jednou od zákazníka do depa a podruhé z depa k adresátovi. Ze stavu "Na cestě" může balík přet do fonty, kde čeká na zaplacení. V případě, že se balík vrátí od dopravce jako nedoručitelný, pak půjde do chybové fronty.

###Stav "Ve frontě"
Je stav, kdy se nastane další problém, na jehož pracování nemáme připravený proces. Například, dopravce vrátí balík jako nedoručitelný.

###Stav "Uzavřeno"

Přehled stavů balíku:

![Stavy balíků](./diagrams/out/states-package-2.png "Stavy balíků")

#### Stav "Poškozený balík"
Není to samostatný stav, ale případ chybového stavu. Je to druh chyby, kdy dispečer zjistí, že balík je poškozený a je třeba se zákazníkum domluvit další postup. V tomto stavu lze další krok přiřadit na dispečera nebo pracovníka podpory. Například když balík vyžaduje nějakou informaci od dispečera. Nebo dispečer dostane pokyn k rozdělení balíku na několik samostatných. 
