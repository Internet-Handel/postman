# Jak dál rozšiřovat tuto dokumentaci

Návod jsem zkoušel pouze na Apple.

## Základni informace

Struktura projektu využívá strukturu [MkDocs	](https://www.mkdocs.org) projektu a vypadá takto:
```
├── balsamiq
└── docs
    ├── diagrams
    │   ├── out
    │   └── src
    └── imgs
```
Jednotlive adresáře obsahují dokumenty pro různe technologie. Proces generovaní dokumentace využívá funkci MkDocs. Základní konfigurace projektu je v souboru ``mkdocs.yml``. 

## Předpoklady

Aby jste mohli texty upravovat a publikovat změny, pak budete potřebovat:
 
* Nainstalovaný git
* Nainstalovaný python
* Nainstalovaný MkDocs
* Stáhnutý projekt [github.com/jajir/postman](https://github.com/jajir/postman).

## Jak upravovat texty

Texty jsou v adresari ``docs/src``. Pro úpravu stači znát jednoduchou strukuru markdownu a začít upravovat. Markdown je popsaný například [zde](https://daringfireball.net/projects/markdown/syntax). Až budete s úpravami hotovi, spusťte:

```
mkdocs serve
```
V prohlížeči na adrese ``http://127.0.0.1:8080/`` najdete aktuální verze dokumenatce. Když nějaký dokument upravíte, v prohlížeči se stránka sama aktualizuje.


## Jak přidat novou stránku.

Pokud nechcete, aby se nová stránka objevila v levém menu, pak stačí vytvorit příslušný .md soubor a začít na něj odkazovat. Tím je hotovo. Pokud chcete, aby se odkaz na nový soubor objevil v levém menu, pak musíte odkaz přidat do ``mkdocs.yml``. Jak odkaz přidat by mělo být zjevné.

## Jak upravovat obrázky

### Obrázky s diagramy, UCs, activity disgrams ...

Obrázky jsou generované pomoci PlantUML ze souborů uložených v ``doc/diagrams/src``. Opět stačí přidat nebo upravit soubor a nový nebo upraveny obrázek se sám vygeneruje. Je pohodlné obrázky upravovat a vytvářet v nějakém on-line editoru, například [www.planttext.com](https://www.planttext.com). Popis formátu zápisu obrázku je na [https://plantuml.com](https://plantuml.com "PlantUML home")

### Obrázky s návrhy obrazovek

V adresáři ``balsamiq`` jsou uloženy návrhy obrazovek. Jsou upravitelné v [balsamiq.com](https://balsamiq.com). Obrázky exportujte do adresáře ``docs/imgs/``.
## Jak publikovat upravy na [jajir.github.io/postman/](https://jajir.github.io/postman/)

Pushněte změny na gitgub. Pak na konzoli spusťte:

```
mkdocs gh-deploy
```

