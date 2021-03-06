# Einführung

Dieses zentrale Repository stellt Metainformationen für die Pakete innerhalb des [Contao Managers][3] bereit.

Es erlaubt das Übersetzen und Anreichern von Paketinformationen jedes beliebigen [Composer][1] Pakets. Daher können
auch Pakete die nicht vom Typ `contao-bundle` sind (wie bspw. eine allgemeine PHP Excel Exportbibliothek) übersetzt
werden.

Die Metadaten werden in im [YAML-Format][4] gespeichert und es kann ein Logo im SVG-Format angegeben werden.

## Beispiel einer Paketstruktur

```
meta/[vendor]/[paket-name]
    - de.yml
    - en.yml
    - ru.yml
    - ...
    - logo.svg (optional)
```

Hinweis: Das `logo.svg` kann auch direkt innerhalb von `[vendor]` liegen, es wird dann als Fallback für alle Pakete
dieses `[vendor]` verwendet, sofern kein Logo für das explizite Paket angegeben wurde.

## Beispiel einer YAML Sprachdatei

```
de:
    title: Titel des Bundles oder des Moduls
    description: >
        Lange Beschreibung des Bundles oder des Moduls mit Zeilenumbrüchen.

        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.
        At vero eos et accusam et justo duo dolores et ea rebum.
    keywords:
      - keyword1
      - lorem ipsum
      - keyword2
      ...
```

Bitte verwendet 4 Leerzeichen zum Einrücken oder Verschachteln und sprecht den Nutzer mit "Sie" an.
Für weitere Informationen zum Dateiformat, sieh dir die [Transifex Dokumentation][2] an.

## Unterstützte Sprachen

Siehe https://github.com/contao/contao-manager/blob/master/src/i18n/locales.js

## Wie kannst Du beitragen

1. Klone das Repo
2. Wähle ein vorhandenes Paket oder erstelle einen neuen Ordner für ein nicht existierendes Paket wie "meta/vendor/package"
3. Erstelle einen Pull Request
4. Das Review-Team überprüft deinen Pull-Request innerhalb von ca. 5 Tagen

## Roadmap

* **Automatisiertes Reindexieren**

    Aktuell wird der Index nicht automatisch aktualisiert, sobald sich dieses Repository ändert. Wir planen aber die
    Nutzung von z.B. GitHub Webhooks um die betroffenen Pakete im Index automatisch zu aktualisieren.

* **Merge Berechtigungen für die betroffenen Entwickler**

    Es ist tatsächlich ein "Problem", dass Entwickler von Paketen im Moment keine Möglichkeit haben, die Paketinformationen
    ihrer eigenen Pakete zu aktualisieren, ohne dass jemand mit Merge-Rechten den Pull Request merged. Wir planen die
    Einführung eines Bots der in der Lage ist, zu entscheiden, welcher GitHub-User für welche Pfade innerhalb des meta-Daten
    Verzeichnisses verantwortlich ist und daher einen Pull Request freigeben darf. Sobald freigegeben, würde der Bot das
    Mergen übernehmen. Denkbar wäre eine Implementierung auf Basis der GitHub `OWNERS` Datei bzw. deren Review-Feature.


[1]: https://getcomposer.org
[2]: https://docs.transifex.com/formats/yaml
[3]: https://github.com/contao/contao-manager
[4]: http://yaml.org/
