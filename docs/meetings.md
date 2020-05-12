s# Schůzky

Zde budeme zaznamenávat, na čem jsme se domluvili a co bychom rádi probrali.

## 12.05.2020
Co chcem probrat a otevřené otázky:

* Označovat tickety, které popisují zadání pro fázi 2 nebo nápady, které teď do fáze 1 není třeba  zpracovat. Dávat jím typ "idea". Budou na očích, neztratí se, ale nemusíme je teď řešit. Př. je [Issue 35][issue35].

Na čem jsme se domluvili:

* Na stránku na wiki budeme dávat odkazy na dokumentaci, kterou jsme během týdne udělali. Každé pondělí večer to Vojta shrne a pošle na všechny členy týmu. Po měsící si řekneme, jestli to pomáhá.
* Pro fazi 1. nepotřebujeme balík v balíku. Nutno začít připravovt.
* UC-4 problém se zobrozováním bodu 4. s platebními pokyny. Odsuneme bod 4. za tlačítko objednat. Bivoj připraví textaci.
* Z entity položka objednávky vyndám informace o měření balíku od zákazníka a dám to do entity měření.
* Issues typu `Proposal` budou pro další fáze. Typ `Enhancement` bude pro tuto fázi 1.
* Petr bude odpovědný za finální připomínkování formulářů.

## <a name="04.05.2020"></a>04.05.2020

Na čem jsme se domluvili:

* Automatické UI testy Martin pěkně popsal na [wiki](https://bitbucket.org/internethandel/postman/wiki/testovani). Nebudem teď plošně implementovat. Zkusíme pár kousků později.
* Napíšeme automatický UI test na příjem objednávky. Součástí bude automatické spouštění testů po zamergovaní do nebo commitu do vývojové větve a produkční větve.
* Jednotkové testy, ano. Udělám zchůzku na to, co chcem testovat a jak.
* Udělám schůzku, kde zkusíme připravit pár ukolů na nějakou oblast. Cíl je mít práci, dobře připravenou.

## <a name="04.05.2020"></a>04.05.2020
Co chcem probrat a otevřené otázky:

* Platby, napojení na banky a toho týkající se dotazy dole

Na čem jsme se domluvili:

* Pole, které nám banky nmohou poskytnou:
    * Číslo transakce
    * Datum transakce
    * Datum zaúčtování
    * Konstantní a variabilní symbol
    * Název obchodníka
    * Částka
    * Měna
    * Zpráva pro příjemce
* Budem ukládat všechna pole.
* Založíme bankovní účet v Polsku v polské měně.
* Ve fázi 1. se potřebujeme připojit na polskou banku a na českou, to bude Fio. Na fio se připojíme automaticky a na polskou se připojíme se ručně nebo automaticky.
* Do budoucna by bylo dobré umět v kontaktní historii označit zákazníka "potížistu", aby dál nedostával reklamu (i vyžádanou).
* Všechny banky nějakou formou publikují nějaký digitalní soubor s platbami. Např.: CSV, Excel.
    * Když chybí id transakce, pak se to řeší tak, že se udělá hash z údajů v transakci a ten se použije jako identifikátor.
* Upravit UC na vkládání plateb. Vždy to bude nějaký soubor s daty od banky. Pro každou banku tam bude chlívek na nahrání souboru. 
* Zrušíme UC na ruční zadávání plateb a možnost platby mazat.
* Návrh je, aby se v systému se platby neprováděli. Pouze se ze připraví žádosti o provedení plateb zákazníkům. 
    * Finálně to rozmyslíme tak, aby to bylo co nejsnažší.
    * TODO je třeba rozmyslet, jak řešit, že to někdo interně neschválí.
* Zkusíme s Davidem připravit analýzu a popis úkolů, jak to udělat.
* Kontroly pouze na konzistenci dat na zůstatky na účtech. V systému musí být možnost, po bankách a po kalendařních měsících zobrazit kolik jsme vydali a přijali. To budem porovnávat se pohybem na účtech. Z banky budem číst, co jsme poslali i přijali. Počíme stím, ze se tam mohou objevit nějaké nepravidelnosti.
* Nebudem řešit scénáře jako jsou: Oprava zadané platby, zrušení platbu, omylem rozdělená platba? Nebudeme teď řesit.
* Nemusím umět spojovat platby, stačí jí rozdělit zpět.

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
* Na čem lze pomalu začít a někde už se začalo:
    * User management.
    * Napojení na banku nebo banky.
    * Platební UCs
    * Napojení na dopravce.
    * Sběr dat zákazníka.
    * Objednávka a její stavy.
    * Balík a jeho stavy.
    * Šablony.
    * Napojení na tiskárnu šítků. Jak identifikaci té správné.

Na čem jsme se domluvili:

* Povídání o jazykových mutacích sepíše Jirka. Musím mu připravit místo, kam byt to mělo přijít. Je na to [task 38](https://bitbucket.org/internethandel/postman/issues/38/).
* Kluci mi dají vědět, jak se vyřešil zoom.
* Mame rozdělených 6 bundlů, kluci se založí samostatné tickety, kde proberou bližší pohled na bundle. Přistě bundly proberem. Na tomto základě se rozhodneme, jestli bundle použijeme nebo ne.
* UC na platby a její ověřování proberem samostatně s Davidem a Bivojem. To jsou body z přípravy.
* U balíků budeme sledovat a ověřovat rozměry a váhu. Budem počítat s tím, že to třeba na poslední chvíli vypnem.
* Likvidace neplatných štítků dispečer provede tak, že neplatný štítek přelepí novým. Pokud to není možné, pak se neplatný štítek nebo štítky odtrhnou.
* Aktivní štítek není nutné evidovat. Je to vždy ten poslední vytištěný štítek.
* Pojištění balíků. Zákazníkům budeme říkat, že balík je pojištěn jen do nějaké výše. Přesná výše bude odvozena od standardní ceny pojištění dopravce.
* Posílání dat o štítkách dopravce dopravcům. Při předání balíků chcem posílat vždy všechna data. I když jim aktuálně napředáváme všechny balíky, o kterých posíláme data. Bráníme se chybě, kdy dispečer nezkontroluje balík při předání dopravci. Nebude to platit pro všechny dopravce.
* Pokud projekt pokročí, pak by bylo dobré zpřesnit kontrolu balíků tím, že zavedem umělé jednotky - dávky. Dávka budou balíky ke zpracování v nějaké frontě. Dávku využijeme k tomu, že se nám žádné balíky v procesu neztratili. Zjednodušený popis je, že zvážíme dávku balíků před zpracováním a po něm. Mělo by to sedět.
* Pokud dispečer zjistí menší poškození obalu balíku a dispečer rozhodne o přebalení. Pak nebudeme ze zákaníka výmáhat platbu za přebalení. Budem posílat upozornění zákazníkovi s fotkou poškození a info o přebalení.
* Detaily dopravců zná Vojta a David. Dopravci budou: DPD Polsko, České pošta. Naplánuju schůzku, kde probereme detaily, jejich specifika, cokoliv, co by mohlo být důležité pro jejich integraci.
* S rozhodováním, kdo se zapojí do jakého tématu počkáme na příští týden.
* Všichní si rozmyslíme, kdo by měl zajem co dělat. Je to dnešním zápisu.
* Martin zjistí, jak je to testovaním UI na frontendu. Založil jsem [task 40](https://bitbucket.org/internethandel/postman/issues/40/).
* Honza rozmyslí, jak řešit situaci, že balík v nějakém procesu poškodíme sami.

## 24.04.2020
Na čem jsme se domluvili

* Řízení rolí a oprávnění podle [https://bitbucket.org/internethandel/postman/issues/19](https://bitbucket.org/internethandel/postman/issues/19) vypadá dobře. Oprávnění symfony lze snadno dodělat. Používají se hierarchické role s využitím dědičnosti. Systém voters je fajn, docela dobře s tím dosáhnem, toho co potřebujem.
* Půjdem touto cestou.
* Potřebujem ukládat doručovací a odesílací adresy v různých formátech. Zvážíme dědičnost v doctrine, jinak to nasypem do jedné tabule.

## <a name="21.04.2020"></a>21.04.2020
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

[issue35]: https://bitbucket.org/internethandel/postman/issues/35

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

