# Schůzky

Zde budeme zaznamenávat, na čem jsme se domluvili a co bychom rádi probrali.

## <a name="28.04.2020"></a>28.04.2020
Co chcem probrat:

* Jaké další symfony moduly se nám mohou hodit?
* Budem implementovat kontrolní mechanizmy na platby a objednávky. Například, že nejsou platby bez objednávek, že součet platby odpovídá bankovnímu převodu? Rád bych připravil seznam kontrol.
* Jaká data budem z bankovních systému číst? Připravit návrh. Číslo transakce, datum transakce, datum zaúčtování, konstantní a variabilní symbol?, název obchodníka ...
* Budem řešit scénáře jako jsou: Oprava zadané platby, zrušení platbu, omylem rozdělená platba?
* Rozmyslet, jestli budem u balíků sledovat a ověřovat rozměry. Fáze 1. s tím počítá.
* Pokud tisknu nový štítek na balík a už tam je starý, tak musím starý znehodnotit. Jak to udělám? Utrhne ho? Zamaluje fixou? Něco dalšího?
* Minule jsme se domlouvali, že zavedeme termín aktivní štítek, to bude ten, o kterém si myslíme, že je na balíku. Myslím, že to není potřeba evidovat. Je to vždy poslední vygenerovaný a vytisknutý štítek. Ví někdo o scénáři, kde by to mohlo být jinak?
* Pokud přijímám balík a zjistím, že je poškozený a že ho lze přebalit, pak balík přebalím. Po přebalení pošlu balík rovnou do fronty dopravce, nebo do nějaké čekací s tím, že účtuji za přebalení?
* Štítek dopravce, kdo zná jak to detailně funguje? Stálo by za to, začít to blíž popisovat. Od začátku budeme mít dopravce dva. Vím o české poště, kdo je ten další?
* Na čem lze pomalu začít a nělde už se začalo:
    * User management.
    * Napojení na banku nebo banky.
    * Platební UCs
    * Napojení na dopravce.
    * Sběr dat zákazníka.
    * Objednávka a její stavy.
    * Balík a jeho stavy.

Na čem jsme se domluvili:

* ...
* ...


## 24.04.2020
Na čem jsme se domluvili

* Řízení rolí a oprávnění podle [https://bitbucket.org/internethandel/postman/issues/19](https://bitbucket.org/internethandel/postman/issues/19) vypadá dobře. Oprávnění symfony lze snadno dodělat. Používají se hierarchické role s využitím dědičnosti. Systém voters je fajn, docela dobře s tím dosáhnem, toho co potřebujem.
* Půjdem touto cestou.
* Potřebujem ukládat doručovací a odesílací adresy v různých formátech. Zvážíme dědičnost v doctrine, jinak to nasypem do jedné tabule.

## 21.04.2020
Otevřené otázky:

* Štítek dopravce, kdo zná jak to detailně funguje? Stálo by za to, začít to blíž popisovat. Od začátku budeme mít dopravce dva. Vím o české poště, kdo je ten další?
* Pří přijetí balíku od dopravce, jak mám vědět, podle jakého štítku pojedu dál? Například vrácený balík vracíme odesílateli. Tedy bude mít štítek dvou dopravců. V systému musí být uložené oba štítky, tak asi nebude vadit, že identifikuji podle libovolného z nich.

Na čem jsme se domluvili:

* Štítek na balíku bude právě jeden. Pokud poytřebuji nalepit nový a již tam je jeden nebo více je, tak starý štítek nebo štítky zničím nebo přelepím.
* Nikdy netisknem jeden štítek dvakrát. Pokud je potřeba vytisknout jakýkoliv štítek podruhé, pak se vygeneruje nový. Je to obrana před náhodným nalepením jednoho štítku na dva balíky. Musím tedy evidovat, kdy jaký štítek prošel načtením kde v procesu.
* Vlastní transakce nebudem evidovat. Pouze platby. Jedna transakce vede na více plateb. Pokud se podívam na detail platby, tak zde bude tlačítko rozdělit platbu, pak vyberu zákázku zvolím částku a příslušná částka se převede jako nová platba na zadanou objednávku. 
* Zavedeme termín aktivní štítek, to bude ten, o kterém si myslíme, že je na balíku.
* Ukládání plateb z banky je buď pouze ruční nebo pouze automatické.
* V pátek udělam schůzku, kde proberem user management, authentication a authorization.
* Entita zaměstnance a zákazníka bude stejná.
* Prozkoumáme moduly v symfony, jestli se tam nevyloupne nějaký, co by nám neusnadnil život.

## 14.04.2020
Na čem jsme se domluvili:

* Vyvinem to jako jednu applikaci.
* Domluvili jsme se na práci s gitem tak, že použijem větve:
    * `master` - obraz produkce, odsud se odlamuje `feature` branch.
    * `feature` - bude jich víc, budou se mergovat do `dev` větve pomocí pull requestů.
    * `dev` - bude obsahovat další release. Odsud budem dělat merge to `master`  větve.
* Fáze projektu:
    1. Základní funkcionalitu v rozsahu tohoto dokumentu, případně něco neuděláme.
    1. Přidáme hromadné podání.
    1. Další funkcionalita jako jsou dobírky, výběr last mile dopravce, podpora vícero dep, ...
* Rozdělíme dokumentaci na technickou u samotného kódu a analytickou zde, navzájem je prolinkujem.
* Jako issue management použijeme, to co nabízí bitbucket.
* O UX rozhoduje Bivoj.

Co, kdo udělá:

* Kluci zkusí verzovat DB pomocí "migrace dat".
* Applikaci kluci připraví jako docker image.
* První ticket na otestování kostry applikace.
* Dev je kopie produ, každou noc přelijem data z produ na dev.
* Kluci mi pošlou pozvánku na slack a bitbucket.
* Honza - Další pozvanku pošlu na úterý.
* Honza - Ozvu se Jirkovi, aby se mnou prošel applikaci.
* Honza - Přepsat UC pro přijetí a zpracování balíků, tak aby se při happy day scénáři tiskl rovnou štítek dopravce. S tím, že ne pro každého dopravce to bude možné. Dopravce musí umožňovat generování štítků dřív, než mu předáme balík.
* Honza - Přidat UC na příchozí platbu na vícero objednávek.
* Honza - Až budu mít přístup k bitbucketu, založím tickety na zbylé úkoly a nalinkuju je sem.

## 10.04.2020

* Jak si budeme říkat, že je nějaká funkcionalita vyvinutá.
* Junit testy a testovaní UI, budeme to dělat?

## 08.04.2020

Na čem jsme se domluvili:

* Vojta sepíše vývojařské desatero a přidá ho do dokumentace.
* Honza:
    * Pozve lid do repa
    * Repo udělá privátním
    * Nástřel UC na hromadné podávání
* Projekt pojedem podle analýzy, co není popsané neprogramujem.
* Co jsme nakousli, ale nedokončili:
    * Vznikne nejaká vrstva technické dokumentace mezi analýzou a php kódem.
* Naplánuju schůzku na 10.4.
* Ostatní kluci vyzkoušíjí php frameworky a založí kostru projektu.


### Šablona zápisu schůzky

```
## Datum
Co chcem probrat a otevřené otázky:

* ...
* ...

Na čem jsme se domluvili:

* ...
* ...
```
