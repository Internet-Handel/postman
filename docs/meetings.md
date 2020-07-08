# Schůzky
Zde budeme zaznamenávat, na čem jsme se domluvili a co bychom rádi probrali.

## 09.07.2020 - Grooming
Co chcem probrat a otevřené otázky:

* Projít a odhadnout UC-21
* ...

Na čem jsme se domluvili:

* ...
* ...

## 07.07.2020 - Planning
Co chcem probrat a otevřené otázky:

* S Bivojem jsme se domluvili, že velkou část UC bude pořeba zrychlit. drtivou většinu UC pro dispečera a pracovníka podpory zajistíme tak, že si zavolají. Postupně budeme zjištovat, co potřebují k práci.
* ...

Na čem jsme se domluvili:

* Prosli jsme, co jsme stihli.
* Naplánovali další sprint.
* Do produkce potřebujeme jít v týdnu do čtvrtého září. Pak už pomalu začne příprava na vánoce, která bude mít prioritu.
* Máme na to 8 sprintů, v to čítajíc aktuálně běžící.
* Musíme na kost ořezat velkou část UC. V původně plánovaném rozsahu je to nestihnutelné.
* Pro účetnictví a fakturaci použijeme [flexiBee][flexiBee].
* Další groomin bude u Bivoje v Modřanech.

[flexiBee]: https://www.flexibee.eu

## 02.07.2020 - Grooming
Co chcem probrat a otevřené otázky:

* Grooming
* ...

Na čem jsme se domluvili:

* Po tisku je třeba požádat dispečera o naskenování vytištěného štítku. Naskenovaný kód štítku musí odpovídat kódu balíku se kterým aktuálně pracuje a zároveň to musím být poslední vytištěný kód balíku. Pokud jedno z toho není splněno, pak mu napíšeme "Chybný štítek a jaké číslo jsme na balíku čekali" a umožníme mu znovu tisknout. Pokud bylo splněno, pak nechame systém přejít na další obrazovku. Na další obrazovce by měla být hláška, že štítek odpovídal.
* ...

## 30.06.2020 - Planning
Co chcem probrat a otevřené otázky:

* Planning.
* Potřebujeme se ptát, co je obsahem balíku?
* Jak má probíhat scanování vytisklého štítku?
* Projít návrh UC-21 - zpracování přijatých balíků

Na čem jsme se domluvili:

* Platí, že čas vykazujeme v jiře na jednotlivé tikety.
* Na přístě připravím přehled vykázaných časů.
* Na každém dalším statusu připravím přehled výkazů, aby se někdo mohl chytit za hlavu a dodatečně vykázat ;-).
* 9.7. grooming bude v mega knihách a pak půjdeme společně na pivo. 

## 25.06.2020 - Grooming
Co chcem probrat a otevřené otázky:

* Projít UC-21 na zpracování přijatých balíků. 
* Jak evidovat stav nebo krok ve kterém se uživatel při průchodu wizarden nachází.
* Připravit tasky na další planning.

Na čem jsme se domluvili:

* Vážení - Váha pošle hodnotu po sériovém portu na počítač. Tam je něco (co to vlatně je ???), co data pošle na server. Na stránce javascript zkouší načíst naměřenou váhu ze serveru. Dokud to není načtené, je tam čekací animace. Až data přijdou na server, pak se uživateli ukáze hodnota z váhy. Při měření je třeba počkat, až se čtené hodnoty ustálí na nějakém čísle. Teprve pak hodnotu poslat.
* Měření - Máme jednoho dopravce. Stačí, když budeme rozměry řešit tak, že balík porovnáme se značkami na stole. Nebudeme tedy přesně měřit, ale pouze porovnávat. Výsledná informace od dispečera bude jestli rozměy odpovídají / neodpovídají.
* Focení balíku. Minimálně kvůli zpáteční adrese, by bylo dobré umět balík automaticky fotit. Už máme přístroj (Vojta), který zobrazí live náhled z kamery a umožní udělat fotky po stisku tlačítka ve webu.
* Potřebujeme se ptát, co je obsahem balíku? Toto jsme nedořešili. Pokud ano, pak by to mělo být pole na objednávkovém formuláři.
* Proces měření a vážení přesuneme mezi kroky "Je balik poskozen?" a "Lze pouzit stitek dopravce". Hlavní důvod je ten, že pokud v některých případech tiskneme přímo štítek dopravce, pak je potřeba vědět jestli balík prošel kontrolou na váhu a rozměry. Pokud ne, pak ho s interním štítkem posílame do chybové fronty.
- Domluvili jsme se, že balík do chybové fronty posíláme hlavně s interním štítkem. ?
- Budeme se dispečera ptát na adresu odesílatele, ale nebudeme ho žádat, aby rozdíly uložil. Týká se to obrazovky S-201.
- Když ukazujeme dispečerovi, aby posoudit zpáteční adresu na balíku ukážeme mu všechny informace o balíku a objednávce. 
- Místo opisování zpáteční adresy, budeme balík fotit tak, aby to pracovník podpory mohl přečíst.
- Na wizardy máme založený ticket na PoC, je třeba prozkoumat:
    - Uděláme je jako SPA?
    - Ve wizardu budou body zlomu (tisk štítku), kde už nepůjde dělat tlačítko back.
    - Jak se to bude chovat, kdyz uživatel zavře prohlížeč a později bude chtít pokračovat v přijímání balíku.
    - Jak ukazovat krok ve kterém se nachází?
- Štítek dopravce tiskneme pouze tehdy, pokud všechny kontroly souhlasí.
- Vystisklý štítek by se měl scanovat - toto tu mám pouze jako poznámku, ale nedomluvili jsem se v jakám kroku. Má to být tak, ze dispečer štítek vytiskne a hned po tom naskenuje? Co se stane, kdyz scan nebude sedět nebo štítek nenajde. To jsou spíš otázky na příště.

## 18.06.2020

Co chceme probrat a otevřené otázky:

* Grooming
* Jak nejlépe označovat věci, které mají jít skrz Bivoje

## 16.06.2020

Na čem jsme se domluvili:

* Planning 4. sprintu
* Budeme přidávat štítky k taskům, které mají vizuální komponent, na který se má Bivoj podívat; případně vytvářet na to specifické tasky
* Budeme do analýzy zapisovat malé nápady a návrhy (do stránky [poznámky](https://jajir.github.io/postman/notes/#otevrene-otazky-napady))

## 09.06.2020
Co chcem probrat a otevřené otázky:

* Planning
* Domluvit definition of done.
* V backlogu nemít tasky assignované na makáče. Pouze pokud s tickety budou před sprintem něco dělat.
* U některých entit není datum události.

Na čem jsme se domluvili:

- Definition of done domluveno.
- Uzavřené tasky neudou na nikoho assignovane.

## 04.06.2020
Co chcem probrat a otevřené otázky:

* Grooming

Na čem jsme se domluvili:

* Grooming

## 02.06.2020
Co chcem probrat a otevřené otázky:

* Naplánujeme sprint.
* Zahájíme sprint.
* Projdeme backlog a domluvíme se, proč jsou úkoly na konkrétních lidech.

Na čem jsme se domluvili:

* Prošli jsme grooming a planning.

## 26.05.2020 - Planning
Co chcem probrat a otevřené otázky:

* Podle toho, co najdeme s labelem "Next", vybereme pár dalších kandidátů do sprintu a odhadneme je.
* Naplánujeme sprint.
* Zahájíme sprint.
* Projdeme backlog a domluvíme se, proč jsou úkoly na konkrétních lidech.

Na čem jsme se domluvili:

* Čtvrteční schůzka tentokrát nebude (jde to za mnou).
* Balsamiq pojedem v 30 denní zkušební lhůtě zadarmo. Pak se dál domluvíme co dál.
* Řízení změn v dokumentaci. Schůzky bude commitovat be pull-requestu ten, kdo dělá zápis. Změny analýzy půjde s pull requestem.
* David navrhoval přidat referenční číslo pro zákazníka. Zákazníkovy by to umožnilo mít pro svoje účely na balíku svůj kód. Přidal jsem to bodu k řešení do fáze II.

## 21.05.2020 - Grooming
Co chcem probrat a otevřené otázky:

* Blíž se podíváme na jiru.
* Projdem otevřené úkoly, co lze další týden stihnout. Projdem si, že tasku rozumíme stejně a shodnem se na jeho složitosti. 

Na čem jsme se domluvili:

* Společně jsme prošli úkoly na domluvili se, jak budeme pracovat s jirou.
* Několik tasků se podařilo naodhadovat.
* Domluvil jsme se, že nebudeme používat pro vykazovaní připravené excely, ale budeme vykazovat přímo na jednotlivé úkoly.
* Pro schůzky a další administrativu máme task [https://internet-handel.atlassian.net/browse/POST-73](https://internet-handel.atlassian.net/browse/POST-73).
* Pro odhadování tasků použijeme Finobacciovu řadu [https://en.wikipedia.org/wiki/Fibonacci_number](https://en.wikipedia.org/wiki/Fibonacci_number).

## 19.05.2020 - Stav & Plánování
Co chcem probrat a otevřené otázky:

* Co kdo udělal, případné problémy.
* Odhadneme složitost tasků na další týden.
* Bitbucket issues přestávají stačit. Chybí mi složitějši dotazy. Například tickety na mě bez closed a bez resolved. Chybi mi dashboardy, mohli bychom lepe videt, co se budem odhadovat, co máme do iterace a podobně.
* Budeme potřebovat ve fázi 1. řešit jiné než české DPH (daňové zákony)?
* Potvrdit si scope fáze 1. Platí, že budeme posílat pouze do Německa? Nebo začneme Polskem?

Na čem jsme se domluvili:

* Kluci připravili jiru. Hodně dobré. Děkuji.
* Fáze 1. je pouze českých daňových zákonů.
* Ve Fázi 1. budeme posílat pouze do Německa.

## 17.05.2020
Co chcem probrat a otevřené otázky:

* Probereme odhadovani tasku. Konkrétně:
    * Jak to lze odhadovat?
    * Jak odhady vyhodnocovat?
    * Jak a kde evidovat?
    * Chceme to vůbec?
* Testovaní na projektu UI testy a jednotkové testy. Jak s tím budeme pokračovat.

Na čem jsme se domluvili:

* Připravím do google doc jednoduchý excel na výkazy pro každého z nás.
* V excelu bude sloupec číslo ticketu z bitbucketu, čas od, do a případná poznámka.
* Junit testy nemá smysl dál zkoušet, přineslo by to víc zpoždění a zátěže pro tým než užitku.
* S UI testy počkáme až bude UC-4 a pak je vyzkoušíme.
* V úterý poprvé zkusíme odhadnou komplexitu tasků.
* Naplánuju schůzku na další čtvrtek - grooming.

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

