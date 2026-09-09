# Cheatsheet Command Line

Reine Referenz zum Nachschlagen — keine Übung. Deckt die Befehle ab, die im Bonus-Kapitel [[1-command-line|Command Line]] vorkommen, plus ein paar weitere fürs Textverarbeiten.

| Was                       | Mac/Linux/Git Bash    | Windows PowerShell                                           | Windows cmd                                                               |
| ------------------------- | --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Fenster schließen         | `exit`                | `exit`                                                       | `exit`                                                                    |
| Ordner wechseln           | `cd ordner-name`      | `cd ordner-name`                                             | `cd ordner-name`                                                          |
| aktueller Ordner          | `pwd`                 | `pwd`                                                        | `cd` (ohne Argument)                                                      |
| Inhalt anzeigen           | `ls`                  | `dir`                                                        | `dir`                                                                     |
| Inhalt mit Muster         | `ls *.md`             | `dir *.md`                                                   | `dir *.md`                                                                |
| Datei kopieren            | `cp quelle ziel`      | `copy quelle ziel`                                           | `copy quelle ziel`                                                        |
| Datei verschieben         | `mv quelle ziel`      | `move quelle ziel`                                           | `move quelle ziel`                                                        |
| Ordner anlegen            | `mkdir name`          | `mkdir name`                                                 | `mkdir name`                                                              |
| Datei löschen             | `rm datei`            | `del datei`                                                  | `del datei`                                                               |
| Ordner löschen (rekursiv) | `rm -r ordner`        | `rmdir -Recurse ordner`                                      | `rmdir /S ordner`<br>cmd fragt bei `/S` nochmal nach, mit `J` bestätigen. |
| Text ausgeben             | `echo "Text"`         | `echo "Text"`                                                | `echo Text`                                                               |
| Datei-Inhalt anzeigen     | `cat datei`           | `cat datei` (Alias für `Get-Content`)                        | `type datei`                                                              |
| Text in Dateien suchen    | `grep "muster" datei` | `Select-String -Pattern "muster" -Path datei`                | `findstr "muster" datei`                                                  |
| Zeilen zählen             | `wc -l datei`         | `(Get-Content datei \| Measure-Object -Line).Lines`          | kein einfaches Äquivalent**                                               |
| Erste Zeilen anzeigen     | `head -n 5 datei`     | `Get-Content datei -TotalCount 5`                            | kein einfaches Äquivalent**                                               |
| Spalte extrahieren        | `cut -d"," -f2 datei` | `Get-Content datei \| ForEach-Object { ($_ -split ",")[1] }` | kein einfaches Äquivalent**                                               |
| Sortieren                 | `sort datei`          | `Get-Content datei \| Sort-Object`                           | `sort datei`                                                              |
| Duplikate entfernen       | `sort datei \| uniq`  | `Get-Content datei \| Sort-Object -Unique`                   | kein einfaches Äquivalent**                                               |
| Hilfe zu einem Befehl     | `man befehl`          | `Get-Help befehl`                                            | `befehl /?`                                                               |

**Für Textverarbeitung fehlen cmd schlicht die Werkzeuge — nutze hier Git Bash (aus [[00-installation-bonus#Schritt 10: Ein besseres Windows-Terminal|Installation, Schritt 10]]) oder PowerShell.

## Weiterführend

Für alles darüber hinaus (reguläre Ausdrücke, Umleitungen mit `>`/`>>`, Skripte): [ss64.com/bash](https://ss64.com/bash/) für Mac/Linux/Git Bash, [ss64.com/ps](https://ss64.com/ps/) für PowerShell — beide kompakt, kostenlos, ohne Anmeldung.

Zurück zum Kapitel: [[1-command-line|Bonus: Command Line]].
