# Analyza


## Role

Mame tyto role:

![Actors](./actors.png "Role")

### Uzivatel

Predstavuje nekoho, kdo ma pristup do systemu. Podle jeho dalsi specializace ma dalsi moznosti.

![Co muze delat Uzivatel](./ucs-uzivatel.png "UCS for Uzivatel")

Uzivatel muze:

* UC-00 - [Přihlásit se pomocí jména a hesla](./uc-00.html#uc-00 "Přihlásit se pomocí jména a hesla").
* UC-01 - Zapomenute heslo.
* UC-02 - Zapomenuty login.
* UC-03 - [Odhlášeni ze systému](./uc-00.html#uc-03 "Odhlášeni ze systému").

UC-01 a UC-02 ted nebudem resit, stejně tak s tím spojené UC.

### Zakaznik

Zakaznik nasi dorucovaci sluzby. Muze to byt fyzicka osoba nebo spolecnost.

![Co muze delat Zakaznik](./ucs-zakaznik.png "UCS for Zakaznik")

Zákaznik muze:

* UC-04 [Registrovat balik](./uc-04.html)
* UC-05 Dorucit balik do depa. Pouze zakaznikovi nabidnem moznost poslat libovolnou postou nebo fyzicky prinest na sberne misto.
* UC-06 [Sledovaní balíku](./uc-06.html "Sledovaní balíku"). Zákazník musí mít možnost sledovat zásilku. Kde je a co se s ni deje.
* UC-07 Zaplatit za doručeni. Posledni krok UC-04.

**TODO negativni scenare**

### Admin

Pracovnik dorucovaci sluzby, ktery dohlizi na fungovani systemu.

![Co muze delat Admin](./ucs-admin.png "UCS for Admin")

UC admina nebudem v první fázi řešit.

**TODO aspon si v bodech sepsat,co by tu mělo být**

### Dispečer

Pracovnik dorucovaci sluzby, odpovedny za prevzeti baliku od zakaznika a predani prepravci.

![Co muze delat Despecer](./ucs-dispecer.png "UCS for Dispecer")

Dispecer musi byt v depu. Depo bude umistene tak, aby bylo v dobrem dosahu prepravcu. Co dispečer dela:

* UC-10 Prijmout baliky. Tento UC nebudem dal rozpracovavat. 
* UC-11 Rozdelit baliky. Projit balizky zkontrolovat stav a podle toho je rozdelit.
* UC-12 Predat baliku. Dispečer vezme hromadku z balíkama pro daného dopravce a předá mu je. Nebudem dal popisovat.

### Support

Pracovnik nasi dorucovaci sluzby. Je odpovdny za hladky provoz sluzby. Vyrizuje reklamace, nesparovan baliky a pomoha s procesem doruceni baliku.

![Co může delat Support](./ucs-support.png "UCS for Support")

Support může být fyzicky na centrále. Je odpovědný za:

* Podpora uzivatelu
    * UC-31 Zmena/obnova hesla 
    * UC-32 Zapomenuté přihlašovací jméno
* UC-33 - Kontrola úctu
* Vyhledaní balíku
* Vystaveni dobropisu
* Urgovani zaplacni
* Reklamace

### eShop

Zakaznik, ktery ma moznost zadavat hromadne posilani.

![Co muze delat eShop](./ucs-eshop.png "UCS for eShop")
 
Zákazním může:

* Hromadné podání



