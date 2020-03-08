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

## <a name="S-03"></a>S-03 - Hledání balíků

![Hledání balíků](./imgs/s-03-search.png "Hledání balíků")

Do pole hledat, pujde zadat část libovolné adresy, kód balíku, telefon zákazníka, čast jména, prostě cokoliv. 

## <a name="S-04"></a>S-04 - Detail objednávky

![Detail objednávky](./imgs/s-04-order-details.png "Detail objednávky")

## <a name="S-05"></a>S-05 - Detail balíku

![Detail balíku](./imgs/s5-package-detail.png "Detail balíku")

Může být součástí stránky [S-04 Detail objednávky](./#S-04)

## <a name="S-06"></a>S-06 - Seznam plateb

![Platby](./imgs/s-06-payments.png "Platby")

V psledním sloupci bude vidět, jestli se platbu podařilo spárovat s objednávkou. Pokud ano, pak zde bude odkaz na detail objednávky.

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

* textu v adresách
* minimální a maximální ceny objednávky
* nezaplacených objednávek

## <a name="S-11"></a>S-11 - Spárovat objednávku s platbou

Po stisknutí "Spárovat" na S-10 se zobrazí obrazovka:

![Napojení platby na objednávky](./imgs/s-11-order-pair-with-payment.png "Napojení platby na objednávky")

## <a name="S-12"></a>S-12 - Seznam uživatelů

Odkaz na tuto stránku povede přímo z hlavního rozcestníku [S-01](./#S-01).

![Seznam uživatelů](./imgs/s-12.png "Seznam uživatelů")

Poslední uživatel Milan Strnad není aktivní a nebude se moc přihlásit do systému.

## <a name="S-13"></a>S-13 - Přidat uživatele

![Přidat uživatele](./imgs/s-13.png "Přidat uživatele")

## <a name="S-14"></a>S-14 - Upravit uživatele

![Upravit uživatele](./imgs/s-14.png "Upravit uživatele")

## <a name="S-15"></a>S-15 - Nastavit heslo uživatele

![Nastavit heslo uživatele](./imgs/s-15.png "Nastavit heslo uživatele")

## <a name="S-200"></a>S-200 - Dispečer
