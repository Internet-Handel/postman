# Obrazovky

Zde jsou schematicky popsané obrazovky systému.

## <a name="S-000"></a>S-000 - Info box

V některých případech systém potvrzuje, že operace dopadla dobře, nebo že neco není možné udělat a zárověn to nemá povahu validace pole. V těchto a podobných případech budem ukazovat oznámení:

![Info box](./imgs/s-000.png "Info box")

Ve výsledku to může vypadat odlišně.

## <a name="S-00"></a>S-00 - Přihlašovací obrazovka

Přihlašovací obrazovka

![Přihlašovací obrazovka](./imgs/s-00-login.png "Přihlašovací obrazovka")

Chyba ve formuláři se zobarazí následovně:

![Přihlašovací obrazovka - nastala chyba](./imgs/s-00-login-err.png "Přihlašovací obrazovka - nastala chyba")

## <a name="S-01"></a>S-01 - Základní rozcestník

![Uvítací obrazovka](./imgs/s-01.png "Uvítací obrazovka")

Sekci "Pracovník podpory" uvidí pouze pracovník podpory, stejně se chová sekce "Dispečer". Detaily toho, kdo co vidí jsou vidět za analýzy.

## <a name="S-02"></a>S-02 - Odhlášení

![odhlášení](./imgs/s-02-logout.png "Odhlášení")

## <a name="S-03"></a>S-03 - Hledání balíků 📦

![Hledání balíků](./imgs/s-03-search.png "Hledání balíků")

Do pole hledat, pujde zadat část libovolné adresy, kód balíku, telefon zákazníka, čast jména, prostě cokoliv. 

## <a name="S-04"></a>S-04 - Detail objednávky

Stránku může být rozdělená pomocí záložek na více. Pokud odkaz na detail balíku není aktivní znamená to, že balík fyzicky nemáme a ani jsme neměli. Obrazovka obsahuje několik samostatných sekcí:

* Obecné infromace o objednávce
* Platby
* Kontaktní historie
* Události
* Daňové doklady
* Číslo objednávky a variabilní symbol jsou stejné hodnoty.

![Detail objednávky](./imgs/s-04-order-details.png "Detail objednávky")

Detaily záznamů kontaktní historie na této stránce nejsou vidět. Pro ně by měla vzniknout nová stránka s jejich seznamem a zde přibýt odkaz na ní.

Tlačítka zde budou zobrazená podel aktuálních možností. Například tlačítko "Označit za nezaplacenou" nebude vidět ve stavu objednávky `Nezaplacená`.

## <a name="S-041"></a>S-041 - Potvrzení odpárování platby 💵

Pokud pracovník podpory na obrazovce [S-04 detail objednávky](./imgs/s-04-order-details.png "Detail objednávky") stiskne odpárovat, tak se mu zobrazí potvrzovací dialog:

![Potvrzení odpárování platby](./imgs/s-04-order-details-confirm.png "Potvrzení odpárování platby")

## <a name="S-045"></a>S-045 - Vystavit dobropis 💵

![Vystavit dobropis](./imgs/s-045.png "Vystavit dobropis")

## <a name="S-046"></a>S-046 - Vystavit fakturu 💵

![Vystavit fakturu](./imgs/s-046.png "Vystavit fakturu")

## <a name="S-047"></a>S-047 - Vytvořit záznam do komunikační historie

![Vytvořit záznam do komunikační historie](./imgs/s-047.png "Vytvořit záznam do komunikační historie")

## <a name="S-048"></a>S-048 - Rozdělení objednávky mezi dvě platby 💵

![Rozdělení objednávky mezi dvě platby](./imgs/s-048.png "Rozdělení objednávky mezi dvě platby")

Validace:

* Pokud bude převáděná část vetší než celková částka platby, pak se zobrazí: "Nelze převést vyšší částku než je samotná platba."
* Pokud pracovník nevyplní pole s číslem zakázky pak se zobrazí: "Číslo zakázky je povinné".
* Pokud je vyplněná neexistující zakázka, pak se zobrazí: "Zadaná zakázka neexistuje."

## <a name="S-05"></a>S-05 - Detail balíku 📦

Číslo balíku v nadpisu stránky bude kód balíku. Pokud balík kód balíku namá, pak zde bude kód interního štítku.

Doručovací odresa balíku nemusí být ta, kterou zadal na objednávce zákazník. Pokud doručujeme do dalšího depa, pak zde bude adresa depa. Doručovací adresu, kterou zadal klient lze dohledat na objednávce.

![Detail balíku](./imgs/s05-package-detail.png "Detail balíku")

Tlačítka pro fyzickou manipulaci s balíkem jsou dostupná pouze dispečerovi. Jedna se o:

* Přidat záznam o poškození
* Přidat záznam o přebalení
* Přidat měření
* Rozdělit balík

Odkaz na detail je z [hledání balíků S-03](./#S-03) a z [detailu objednávky S-04](./#S-04).

Část napárované balíky popisuje stav, kdy přijde balík, který se nepodaří spojit s objednávkou, dispečer balík změří a zváží a opatří interním štítkem. Teprve dodatečně se přijde na to, k jaký to byl balík u jaké objednávky.

## <a name="S-051"></a>S-051 - Změna doručovací adresy

![Změna doručovací adresy](./imgs/s-051.png "Změna doručovací adresy")

Může být součástí stránky [S-04 Detail objednávky](./#S-04)

## <a name="S-052"></a>S-052 - Připojit balík 📦

![Připojit balík](./imgs/s-052.png "Připojit balík")

## <a name="S-053"></a>S-053 - Poškození balíku 📦

Obrázky u osob nejsou nutné. Na nahrávání fotek osob není UC.

![Poškození balíku](./imgs/s-053.png "Poškození balíku")

## <a name="S-054"></a>S-054 - Chyba při zpracování balíku 📦

Alternativou k předchozí obrazovce je obecná obrazovka pro chybu při zoracování balíku.

![Chyba při zpracování balíku](./imgs/s-054.png "Chyba při zpracování balíku")

## <a name="S-06"></a>S-06 - Přehled plateb

![Platby](./imgs/s-06-payments.png "Platby")

V posledním sloupci bude vidět, jestli je platba spárovaná s objednávkou. Pokud ano, pak zde bude odkaz na detail objednávky.

Checkbox "Zobrazit pouze nespárované" platby umožní omezit pohled jen na nespárované.

Pokud je nějaké číslo odchozího účtu zvýrazněné jako odkaz, pak to znamená, ze z toho účtu nám přišlo víc platek a kliknutím na odkaz si lze tyto platby vyfiltrovat - [S-08 seznam plateb vyfiltrovaný podle odchozího účtu](./#S-08).	

## <a name="S-07"></a>S-07 - Přidání platby

![Přidání platby](./imgs/s-07-insert-payments.png "Přidání platby")

## <a name="S-08"></a>S-08 - Seznam plateb vyfiltrovaný podle odchozího účtu 

![Seznam plateb vyfiltrovaný podle příchozího účtu](./imgs/s-08-payments-from.png "Seznam plateb vyfiltrovaný podle příchozího účtu")

## <a name="S-09"></a>S-09 - Spárovat platbu s objednávkou 

![Spárovat platbu s objednávkou](./imgs/s-09-link.png "Spárovat platbu s objednávkou")

Po potvrzení "Spárovat" nebo "Cancel" se uživatel vrací na stránku v výpisem plateb.

## <a name="S-10"></a>S-10 - Hledání objednávek 

![Hledání objednávek](./imgs/s-10-order-search.png "Hledání objednávek")

Objednávky lze filtrovat podle:

* Textu - bude se hledat v polích:
    * adresách
    * emailech
* Minimální a maximální ceny objednávky.
* Stavu objednávky -  zde půjde hledat pouze nezaplacené objednávky. Ve seznamu stavů bude možnost hledat objednávky v libovolném stavu.
* Počtu dní, které uplynuli od založení objednávky, kde nepřišla platba. - Pokud nakonec platba přišla,  pak se taková objednávka nevyhledá.
* Vybrat objednávky, ke kterým dorazil aspoň jeden balík.
* Vybrat objednávky, ke kterým nedorazil žádný balík.

## <a name="S-011"></a>S-011 - Hledání objednávek podle plateb

Obrazovka pro hledání chybových stavů u plateb. Například:

* Objednávek, kde zákazník po zaplacení poslal platbu podruhé.

![Hledání objednávek podle plateb](./imgs/s-011.png "Hledání objednávek podle plateb")

## <a name="S-11"></a>S-11 - Spárovat objednávku s platbou

Po stisknutí "Spárovat" na S-10 se zobrazí obrazovka:

![Napojení platby na objednávky](./imgs/s-11-order-pair-with-payment.png "Napojení platby na objednávky")

## <a name="S-12"></a>S-12 - Seznam uživatelů

Odkaz na tuto stránku povede přímo z hlavního rozcestníku [S-01](./#S-01).

![Seznam uživatelů](./imgs/s-12.png "Seznam uživatelů")

Poslední uživatel Milan Strnad není aktivní a nebude se moc přihlásit do systému.

## <a name="S-13"></a>S-13 - Přidat uživatele 👱

![Přidat uživatele](./imgs/s-13.png "Přidat uživatele")

## <a name="S-14"></a>S-14 - Upravit uživatele 👱

![Upravit uživatele](./imgs/s-14.png "Upravit uživatele")

## <a name="S-15"></a>S-15 - Nastavit heslo uživatele 👱

![Nastavit heslo uživatele](./imgs/s-15.png "Nastavit heslo uživatele")

## <a name="S-200"></a>S-200 - Zadání kódu balíku 📦

![Zadání kódu balíku](./imgs/s-200.png "Zadání kódu balíku")

## <a name="S-201"></a>S-201 - Zadání zpáteční adresy

Stránka slouží pro opsání adresy odesílatele z balíku. Protože adresa můze být poškozená nebo nemusí být uvedená vůbec, jsou jednotlivá pole nepoviná. Pouze by zde měla být validace na maxímální délku. 

![Zadání zpáteční adresy](./imgs/s-201.png "Zadání zpáteční adresy")

## <a name="S-202"></a>S-202 - Kontrola zpáteční adresy

![Kontrola zpáteční adresy](./imgs/s-202.png "Kontrola zpáteční adresy")

## <a name="S-203"></a>S-203 - Je balík poškozen? 📦

![Je balík poškozen?](./imgs/s-203.png "Je balík poškozen?")

## <a name="S-204"></a>S-204 - Poškození balíku 📦

![Poškození balíku](./imgs/s-204.png "Poškození balíku")

## <a name="S-205"></a>S-205 - Tisk interního štítku 🖨 🏷

![Tisk interního štítku 🖨](./imgs/s-205.png "Tisk interního štítku 🖨")

## <a name="S-206"></a>S-206 - Zadání spotřeby obalového materiálu

![Zadání spotřeby obalového materiálu](./imgs/s-206.png "Zadání spotřeby obalového materiálu")

## <a name="S-207"></a>S-207 - Měření a vážení ⚖️

![Měření a vážení](./imgs/s-207.png "Měření a vážení")

Všechna pole jsou povinná a musí obsahovat číselné hodnoty.

## <a name="S-208"></a>S-208 - Fronta kam má být balík vložen 📦

![Fronta kam má být balík vložen](./imgs/s-208.png "Fronta kam má být balík vložen")

## <a name="S-209"></a>S-209 - Načtení interního štítku 🏷

Stránka pro načítání interního štítku se načte tak, ze focus je v poli pro kód interního štítku. To umožní dispečerovi čtečkou načít čárový kód bez dalšího klikání. Stejně tak by stránka měla poznat, že kód byl načten a přejít na další stránku bez potvrzování tlačítkem "pokračovat".

Na stránce by měla být validace, že kód interního štítku existuje a balík je ve správném stavu. To co je správný stav zavisí na použitém UC.

![Načtení interního štítku](./imgs/s-209.png "Načtení interního štítku")

## <a name="S-210"></a>S-210 - Co dál s chybovým balíkem 📦

![Co dál s chybovým balíkem](./imgs/s-210.png "Co dál s chybovým balíkem")

## <a name="S-211"></a>S-211 - Načtení interního štítku 2 🏷

Stejná stránka jako je S-209 s tím, že na obrazovce je možnost zadat, že balík nemá interní štítek.

![Načtení interního štítku](./imgs/s-211.png "Načtení interního štítku")

## <a name="S-212"></a>S-212 - Tisk štítku dopravce 🖨 🏷

Zároveň se zobrazením této obrazovky se vytiskne štítek dopravce.

![Tisk štítku dopravce](./imgs/s-212.png "Tisk štítku dopravce")
