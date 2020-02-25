# Jak dal rozsirovat tuto dokumentaci

Navod jsem zkousel pouze na Apple.

## Zakladni informace

Struktura projektu vyuziva strukturu [maven](https://maven.apache.org) projektu. Stejne tak proces generovani dokumentace vyuziva funkci mavenu.

## Predpoklady

Aby jste mohli texty uptavovat a publikovat zmeny, pak budete potrebovat:
 
* Nainstalovany git
* Nainstalovanou javu, pouzivam verzi OpenJDK 11.
* Nainstalovany maven.
* Stahnuty projekt [github.com/jajir/postman](https://github.com/jajir/postman).

## Jak upravovat texty

Texty jsou v adresari ``src/site/markdown``. Pro upravu staci znat jednoduchou strukuru markdownu a zacit upravovat. Az budete s upravami hotovi, spustte:

```
mvn site-deploy
```
v adresari ``target/site/index.html`` uvidite pregenerovanou a upraven	ou dokumentaci.


## Jak pridat novou stranku.

Pokud nechcete, aby se nova stranka objevila v levem menu, pak staci vytvorit prislusny .md soubor a zacit na nej odkazovat. Tim je hotovo. Pokud chcete, aby se odkaz na novy soubor objevil v levem menu, pak musite odkaz pridat do ``src/site/site.xml``. Jak odkaz pridat by melo byt zjevne. Pro pregenerovani dokumentace nakonec spustit:
```
mvn clean site-deploy
```
A tim by se mel novy odkaz objevit v levem menu.

## Jak upravovat obrazky

### Obrazky UCs nebo sequece diagramu

Obrazky jsou generovat pomoci plant uml ze souboru ulozenych v ``src/site/plantuml``. Opet staci pridat nebo upravit soubor a po spusteni:
```
mvn site-deploy
```
se novy nebo upraveny obrazek vygeneruje. Je pohodlne obrazky upravovat a vytvaret v nejakem on0line editoru, napriklad [www.planttext.com](https://www.planttext.com).


## Jak publikovat upravy na [jajir.github.io/postman/](https://jajir.github.io/postman/)

### Postup
- V souboru ~/m2/settings.xml by melo byt:

```
	...
	<servers>
		<server>
			<id>github</id>
			<username>___jmeno___</username>
			<password>___heslo___</password>
		</server>
	</servers>
	...
```

Stim, ze misto  ``___jmeno___`` bude vase jmeno a misto ``___heslo___`` bude vase heslo.

- Na konzoli spustte:

```
mvn site-deploy
```

nasledne treba i po nekolika	 minutach by se mel upraveny dokument objevit na [jajir.github.io/postman/](https://jajir.github.io/postman/). Pok vse dobre dopadne na konzoli se objevi neco jako:
```
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.034 s
[INFO] Finished at: 2020-02-25T23:17:31+01:00
[INFO] ------------------------------------------------------------------------
```

- Hotovo.