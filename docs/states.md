# Stavy

**Doplnit k UC přechody mezi stavy.**

Objednávky a balíky během vyřizování procházejí několika stavama. V první verzi, kde budeme mít právě jeden balík na objednávky, bude možné následující stavy spojit v jeden.

## Stavy objednávek

Objednávka prochází následujícími stavy:

![Stavy objednávky](./diagrams/out/states-order.png "Stavy objednávky")

Podle všeho u objednávky nebudem potřebovat evidovat stavy.

## Stavy jednotlivých balíků

Balíky během doručování procházejí následujícími stavy:

![Stavy balíků](./diagrams/out/states-package.png "Stavy balíků")

Balík bude ve stavu "Na cestě" aspoň dvakrát jednou od zákazníka do depa a podruhé z depa k adresátovi. Ze stavu "Na cestě" se může balík dostat do stavu "čeká na zaplacení" a pak do stavu "Chyba". To se stane v případě, že zákazník odmítne balík převzít, nebo se ho nějakého jiného důvodu nepodaří doručit.

Stavy bude možné rekonstrovat z jiných záznamů. V některých případech to bude nemožné, například to jestli je zaplaceno nelze udělat jako součet přijatých plateb.

U balíčků je třeba znát historii všech stavů. To je potřeba pro reklamace a evidenci pohybu balíku. Historii stavů lze později využít pro optimalizaci procesů. 