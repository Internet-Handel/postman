# Schůzky

Zde budeme zaznamenávat, na čem jsme se domluvili a co bychom rádi probrali.

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
* Honza - ozvu se Jirkovi, aby se mnou prošel applikaci.
* Honza - přepsat UC pro přijetí a zpracování balíků, tak aby se při happy day scénáři tiskl rovnou štítek dopravce. S tím, že ne pro každého dopravce to bude možné. Dopravce musí umožňovat generování štítků dřív, než mu předáme balík.
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