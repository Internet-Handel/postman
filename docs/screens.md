# Obrazovky

Zde jsou schematicky popsané obrazovky systému.

## <a name="S-00"></a>S-00 - Přihlašovací obrazovka

Přihlašovací obrazovka

![Přihlašovací obrazovka](./imgs/s-00-login.png "Přihlašovací obrazovka")

Chyba ve formuláři se zobarazí následovně:

![Přihlašovací obrazovka - nastala chyba](./imgs/s-00-login-err.png "Přihlašovací obrazovka - nastala chyba")

## <a name="S-01"></a>S-01 - Základní rozcestník

![Uvítací obrazovka](./imgs/s-01.png "Uvítací obrazovka")

Sekci "Pracovník podpory" uvidí pouze pracovník podpory, stejně se chová sekce "Dispečer".

## <a name="S-02"></a>S-02 - Odhlášení

![odhlášení](./imgs/s-02-logout.png "Odhlášení")

## <a name="S-03"></a>S-03 - Hledání

![Hledání](./imgs/s-03-search.png "Hledání")

Do pole hledat, pujde zadat část libovolné adresy, kód balíku, telefon zákazníka, čast jména, prostě cokoliv. 

**Budeme ve výsledcích mixovat balíky a objednávky?**


## <a name="S-04"></a>S-04 - Detail objednávky


## <a name="S-05"></a>S-05 - Detail balíku

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

**Doplnit validace na jednotliva pole, chceme ciselnik bank?**


