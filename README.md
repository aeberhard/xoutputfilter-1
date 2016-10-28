# XOutputFilter-Addon für REDAXO 5 #

Mit dem Addon XOutputFilter hat man die Möglichkeit über den Extension-Point OUTPUT_FILTER die Ausgabe der REDAXO-Seite zu beeinflussen sowohl im Frontend als auch im Backend.

Die Hauptaufgabe dieses Addons ist die Ersetzung von Markern/Konstanten in der jeweiligen Sprache und die Kennzeichnung von Abkürzungen und Akronymen.

Über eine Programmschnittstelle kann in Modulen und Addons auf die Sprachersetzungen zugegriffen werden.

Zusätzlich können für das Frontend und das Backend verschiedene "Inserts" mit Code-Fragmenten, sonstigem HTML-Code oder auch PHP-Code angelegt werden. Diese Einträge können dann bestimmten Markern und Kategorien/Unterkategorien zugeordnet werden. Der Code wird - je nach Auswahl - entweder vor, hinter oder statt dem vorhandenen Marker im Quelltext ausgegeben beziehungsweise ausgeführt.

Die gewünschten Funktionen des Addons können über Plugins aktiviert und den Benutzern zugeordnet werden.

---

## Verwendung der Sprachersetzungen in Modulen oder Addons ##

```php
<?php
// Beispiele:
//   $x->get(PLATZHALTER, [Sprache]);
//   xoutputfilter::get(PLATZHALTER, [Sprache]);

$x = new xoutputfilter();
echo $x->get(\'copyright\');
echo $x->get(\'copyright\', 1);
echo $x->get(\'copyright\', rex_clang::getCurrentId());

echo xoutputfilter::get(\'copyright\', rex_clang::getCurrentId());

// Sprachersetzungen auf eigenen HTML-Code anwenden:
$x = new xoutputfilter();
echo $x->replace($my_content, rex_clang::getCurrentId());

echo xoutputfilter::replace($my_content, rex_clang::getCurrentId());
?>
```

---

## Credits ##

* Andreas Eberhard, http://aesoft.de
* Peter Bickel, http://polarpixel.de
* [Friends Of REDAXO](https://github.com/FriendsOfREDAXO) Gemeinsame REDAXO-Entwicklung!

---

Idee und Realisierung der ersten Version: [Andreas Eberhard / aesoft.de](http://aesoft.de) und [Peter Bickel / polarpixel.de](http://polarpixel.de)
