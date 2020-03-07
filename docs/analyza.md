# Analýza
## Role

Mame tyto role:

![Actors](./diagrams/out/actors.png "Role")

### Zákazník

Zákazník naší doručovací služby. Může to být fyzická osoba nebo společnost.

![Co muze delat Zakaznik](./diagrams/out/ucs-zakaznik.png "UCS for Zakaznik")

Zákaznik můze:

* UC-04 [Registrovat balik](../uc-00/#uc-04).
* UC-05 [Doručit balík do depa](../uc-00/#uc-05).
* UC-06 [Sledovaní balíku](../uc-00/#uc-06). 
* UC-07 [Zaplatit za doručeni](../uc-00/#uc-07).

### Uživatel

Představuje někoho, kdo má přístup do systému. Podle jeho dalši specializace má další možnosti.

![Co muze delat Uzivatel](./diagrams/out/ucs-uzivatel.png "UCS for Uzivatel")

Uživatel můze:

* UC-10 - [Přihlásit se pomocí jména a hesla](../uc-10/#uc-10).
* UC-11 - [Zapomenuté heslo](../uc-10/#uc-11).
* UC-12 - [Zapomenutý login](../uc-10/#uc-12).
* UC-13 - [Odhlášeni ze systému](../uc-10/#uc-13).

UC-11 a UC-12 ted nebudem řešit, stejně tak s tím spojené UC.

### Dispečer

Dispečet je pracovnik doručovací sluzby, odpovědný za činnosti s balíkem od převzetí balíku od dopravce až po předání dalšímu dopravci.

![Co muze delat Despecer](./diagrams/out/ucs-dispecer.png "UCS for Dispecer")

Dispecer musí být v depu. Depo bude umístěné tak, aby bylo v dobrém dosahu přepravců. Co dispečer dělá:

* UC-20 - [Přijetí balíku](../uc-20/#UC-20 "Přijetí balíku").
* UC-21 - [Zpracování přijatých balíků](../uc-20/#UC-21 "Zpracování přijatých balíků").
* UC-22 - [Zpracování balíků v 'čekací frontě'](../uc-20/#UC-22 "Zpracování balíků v 'čekací frontě'").
* UC-23 - [Zpracování balíků 'k doručení'](../uc-20/#UC-23 "Zpracování balíků 'k doručení'").
* UC-24 - [Zpracování balíků v 'chybové' frontě](../uc-20/#UC-24 "Zpracování balíků v 'chybové' frontě").
* UC-25 - [Předání balíků dopravci](../uc-20/#UC-25 "Předání balíků dopravci").

### Pracovník podpory

Pracovník naší doručovací služby. Vyřizuje reklamace, nespárované balíky a pomáhá s procesem doručení balíku.

![Co může delat Support](./diagrams/out/ucs-support.png "UCS for Support")

Support může být fyzicky na centrále. Pracovník podpory je odpovědný za:

* UC-31 - [Změna/obnova hesla](../uc-30/#UC-31 "Změna/obnova hesla")
* UC-32 - [Zapomenuté přihlašovací jméno](../uc-30/#UC-32 "Zapomenuté přihlašovací jméno")
* UC-33 - [Kontrola bankovního účtu](../uc-30/#UC-33 "Kontrola bankovního účtu").
* UC-34 - [Párování plateb](../uc-30/#UC-34 "Párování plateb"). 
* UC-35 - [Řešení chybové fronty](../uc-30/#UC-35 "Řešení chybové fronty"). 
* UC-36 - [Storno objednávky](../uc-30/#UC-36 "Storno objednávky"). 
* UC-37 - [Urgence zaplacení](../uc-30/#UC-37 "Urgence zaplacení"). 
* UC-38 - [Řešení přeplacených objednávek](../uc-30/#UC-38 "Řešení přeplacených objednávek").
* UC-39 - [Zobrazení detailů objednávky a balíku](../uc-30/#UC-34 "Zobrazení detailů objednávky a balíku").
* UC-40 - [Vystaveni dobropisu](../uc-30/#UC-34 "Vystaveni dobropisu").
* UC-41 - [TBD](../uc-30/#UC-41 "Urgovani zaplacení").
* UC-42 - [Reklamace](../uc-30/#UC-34 "v").

**Doplnit k UC přechody mezi stavy.**

### Admin

Pracovnik dorucovaci sluzby, ktery dohlizi na fungovani systemu.

![Co muze delat Admin](./diagrams/out/ucs-admin.png "UCS for Admin")

UC admina nebudem v první fázi řešit.

**TODO aspon si v bodech sepsat,co by tu mělo být**

### eShop

Zákazník, který má možnost zadávát hromadná posílaní balíků.

![Co může dělat eShop](./diagrams/out/ucs-eshop.png "UCS for eShop")
 
Zákazním může:

* UC-60 - Hromadná registrace balíků



