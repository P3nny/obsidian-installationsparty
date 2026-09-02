# Bonus: Command Line

*Du bist hier, weil Claudian im Hintergrund genau dieses Werkzeug benutzt, um in deinem Vault zu lesen und zu schreiben — und du wissen willst, was da eigentlich passiert. Genau darum geht's jetzt.*

Inhaltlich angelehnt an das [Django Girls Tutorial](https://tutorial.djangogirls.org/en/intro_to_command_line/), plus ein paar zusätzliche Übungen, die zeigen, wie viel Power in diesem unscheinbaren schwarzen Fenster steckt.

## Was ist die Command Line

Die Command Line (auch: Terminal, Konsole, CLI, Prompt) ist ein rein textbasiertes Werkzeug, um Dateien auf deinem Rechner anzuschauen, zu verschieben und zu bearbeiten — im Grunde dasselbe wie der Finder (Mac) oder der Explorer (Windows), nur ohne Fenster, Icons und Mausklicks. Stattdessen tippst du Befehle, die der Computer direkt ausführt.

Das mag am Anfang ungewohnt wirken, ist aber oft schneller als Klicken — und einige Dinge gehen überhaupt nur über die Command Line. Die gute Nachricht vorweg: Auswendig lernen musst du davon nichts, dafür hast du inzwischen eine KI. Aber zu verstehen, was sie da für dich tut, lohnt sich — spätestens, wenn sie mal etwas anderes tut als erwartet.

## Terminal öffnen

- **macOS:** Launchpad → Andere → Terminal
- **Linux:** meist unter Anwendungen → Zubehör → Terminal (je nach System leicht anders)
- **Windows:** Windows-Taste drücken, „Terminal", „PowerShell" oder „cmd" eingeben (je nachdem, was installiert ist — siehe nächster Abschnitt) und Enter drücken

Du siehst danach ein Fenster mit einem blinkenden Cursor, der auf deine Eingabe wartet — das nennt man den **Prompt**. Auf Mac/Linux endet er meist mit `$`, auf Windows mit `>`. Diesen Anfangsteil tippst du nie selbst mit, er ist schon da.

## Windows: Welches Terminal habe ich?

*(Mac/Linux können diesen Abschnitt überspringen — dort gibt's nur ein Terminal.)*

Windows bringt mehrere Terminals mit, die unterschiedlich viel können. Am schnellsten findest du heraus, welches du gerade offen hast, indem du Folgendes eintippst:

```
$PSVersionTable.PSVersion
```

- Kommt eine **Versionsnummer** zurück → du bist in **PowerShell**. Die meisten Befehle in diesem Kapitel funktionieren hier mit der Windows-Spalte aus den Tabellen unten.
- Kommt eine **Fehlermeldung** (etwa „wird nicht als Name eines Cmdlets erkannt") → du bist in **cmd / Eingabeaufforderung**, der einfachsten Variante.

Falls du in Schritt 10 der Installation schon **Git Bash** installiert hast: Öffne stattdessen dieses Terminal — dort funktionieren alle Befehle in diesem Kapitel exakt wie auf Mac/Linux beschrieben, ganz ohne Umweg über PowerShell-Alternativen.

## Erste Schritte

**Übung:** Tippe die folgenden Befehle nacheinander ein (Enter nicht vergessen) und schau, was passiert:

| Befehl (Mac/Linux) | Befehl (Windows) | Was er tut |
|---|---|---|
| `whoami` | `whoami` | zeigt deinen Benutzernamen |
| `pwd` | `cd` (ohne Argument) | zeigt, in welchem Ordner du gerade bist |
| `ls` | `dir` | listet Dateien und Ordner an diesem Ort |

*Tipp: Tippe die Befehle selbst ab, statt sie zu kopieren — so bleiben sie besser hängen.*

## Verzeichnisse wechseln und anlegen

**Übung:**

1. Wechsle in deinen Desktop-Ordner: `cd Desktop`
2. Prüfe, ob es geklappt hat (`pwd` bzw. `cd` ohne Argument)
3. Lege einen neuen Ordner namens `uebung` an: `mkdir uebung`
4. Wechsle hinein und lege darin einen weiteren Ordner namens `test` an

*Tipp: Tippst du die ersten Buchstaben eines Ordnernamens und drückst dann Tab, vervollständigt das Terminal den Rest automatisch.*

## Aufräumen

**Übung:** Geh zurück zum Desktop (`cd ..`) und lösche den `uebung`-Ordner wieder komplett:

- Mac/Linux/PowerShell: `rm -r uebung`
- Windows (klassische Eingabeaufforderung): `rmdir /S uebung`

⚠️ **Achtung:** Gelöschte Dateien über die Command Line landen nicht im Papierkorb — sie sind sofort und unwiderruflich weg. Immer zweimal hinschauen, bevor du `rm` oder `rmdir` drückst.

Zum Schluss kannst du das Terminal mit dem Befehl `exit` wieder schließen.

---

## Spickzettel

| Was | Mac/Linux | Windows |
|---|---|---|
| Fenster schließen | `exit` | `exit` |
| Ordner wechseln | `cd ordner` | `cd ordner` |
| aktueller Ordner | `pwd` | `cd` |
| Inhalt anzeigen | `ls` | `dir` |
| Datei kopieren | `cp quelle ziel` | `copy quelle ziel` |
| Datei verschieben | `mv quelle ziel` | `move quelle ziel` |
| Ordner anlegen | `mkdir name` | `mkdir name` |
| Datei löschen | `rm datei` | `del datei` |
| Ordner löschen | `rm -r ordner` | `rmdir /S ordner` |
| Hilfe zu einem Befehl | `man befehl` | `befehl /?` |

---

## Jetzt wird's spielerisch: drei Power-Übungen

Die Command Line kann weit mehr als Ordner verschieben. Hier drei kleine, greifbare Beispiele, was möglich ist, sobald man Befehle kombiniert.

### 1. Eine sprechende Kuh: `cowsay`

`cowsay` ist ein kleines Programm, das eingegebenen Text in eine ASCII-Art-Kuh mit Sprechblase packt — nutzlos und großartig zugleich, und ein guter erster Kontakt mit **Pipes** (`|`), also dem Weiterreichen von Ausgaben zwischen Programmen.

**Installation:**
- macOS (mit Homebrew): `brew install cowsay`
- Linux: `sudo apt install cowsay`
- Windows mit Git Bash (aus Installation, Schritt 10): wie Linux, oder falls dort nicht vorhanden, per PowerShell-Modul (siehe unten)
- Windows ohne Adminrechte: PowerShell-Modul ohne Zusatzrechte installieren: `Install-Module -Scope CurrentUser PSCowsay`, danach `Get-Cow "Hallo Workshop!"` statt der `echo | cowsay`-Pipe unten

**Übung (Mac/Linux/Git Bash):**
```
echo "Hallo Workshop!" | cowsay
```

Das `|` (Pipe) leitet die Ausgabe von `echo` als Eingabe an `cowsay` weiter, statt sie einfach auf dem Bildschirm auszugeben.

**Auflösung — so sieht das Ergebnis aus:**
```
 ________________
< Hallo Workshop! >
 ----------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

### 2. Aus Einzelbildern ein GIF bauen

Mit dem Werkzeug **ImageMagick** lässt sich aus einer Reihe von Bildern in Sekunden eine Animation basteln — praktisch z. B. für Screenshots, die den Fortschritt eines Vaults über mehrere Wochen zeigen.

**Installation:**
- macOS: `brew install imagemagick`
- Linux: `sudo apt install imagemagick`
- Windows mit Adminrechten: Installer von [imagemagick.org](https://imagemagick.org/script/download.php)
- Windows ohne Adminrechte: [portable ZIP-Version](https://imagemagick.org/script/download.php#windows) herunterladen und entpacken — `convert.exe` läuft direkt aus dem entpackten Ordner heraus, ganz ohne Installation

**Übung:** Lege 3–5 Bilder in einen Ordner (z. B. `bild1.png`, `bild2.png`, `bild3.png`) und führe im selben Ordner aus:

```
convert -delay 50 -loop 0 bild*.png animation.gif
```

- `-delay 50` = 0,5 Sekunden zwischen den Bildern
- `-loop 0` = Animation läuft endlos
- `bild*.png` = alle Dateien, die mit „bild" beginnen und auf „.png" enden — das `*` ist ein **Platzhalter**

**Auflösung:** Im Ordner liegt danach eine `animation.gif`, die durch alle Bilder in alphabetischer Reihenfolge durchblättert.

### 3. Eine echte Pipeline: `grep` + `sort`

Jetzt kombinieren wir zwei Werkzeuge zu einer kleinen Pipeline: `grep` durchsucht Text nach einem Muster, `sort` bringt das Ergebnis in eine Reihenfolge.

**Übung:** Wechsle in deinen Vault-Ordner und durchsuche alle Markdown-Dateien nach dem Wort „OKF":

```
grep -r "OKF" . --include="*.md" | sort
```

- `grep -r "OKF" .` = durchsuche rekursiv (auch Unterordner) ab dem aktuellen Ordner (`.`) nach „OKF"
- `--include="*.md"` = nur in `.md`-Dateien suchen
- `| sort` = die Fundstellen alphabetisch sortiert ausgeben

*Windows-Hinweis: In PowerShell funktioniert das ähnlich mit `Select-String -Path *.md -Pattern "OKF" -Recurse | Sort-Object`. Für die Original-Unix-Befehle empfiehlt sich Git Bash.*

**Auflösung:** Die Ausgabe zeigt dir jede Zeile, in der „OKF" vorkommt, zusammen mit dem Dateinamen — sortiert statt in der zufälligen Reihenfolge, in der `grep` sie gefunden hat. Genau so durchsuchen erfahrene Nutzerinnen riesige Codebasen oder Logdateien in Sekunden, statt jede Datei einzeln zu öffnen.

---

## Inspiration: Was man mit ein bisschen Programmierung noch alles automatisieren könnte

Diese Liste orientiert sich am Aufbau des Buches [*Automate the Boring Stuff with Python*](https://automatetheboringstuff.com/) von Al Sweigart (kostenlos online lesbar) — für alle, die nach dem Workshop tiefer einsteigen wollen:

- Web-Inhalte automatisch durchsuchen, herunterladen oder Formulare ausfüllen
- Text in großen Textmengen oder Dateien automatisch finden und ersetzen (Stichwort „Muster erkennen" — reguläre Ausdrücke)
- Dateien automatisch umbenennen, sortieren, verschieben oder komprimieren
- Excel-Tabellen oder Google Sheets automatisch befüllen oder auswerten
- PDFs und Word-Dokumente automatisch zusammenführen, aufteilen oder Text daraus extrahieren
- CSV-, JSON- oder XML-Dateien automatisch verarbeiten
- Zeitgesteuerte Aufgaben einrichten, die täglich oder wöchentlich von selbst laufen (Stichwort Cron aus Kapitel 5!)
- Automatisch E-Mails, SMS oder Push-Benachrichtigungen verschicken
- Diagramme erstellen oder Bilder automatisch bearbeiten (Logo einfügen, Größe ändern, drehen)
- Text aus Screenshots oder Fotos erkennen (OCR)
- Sich wiederholende Maus- und Tastatur-Aktionen automatisieren
- Text vorlesen lassen oder Sprache automatisch in Text umwandeln

Vieles davon ist mit den Grundlagen aus diesem Kapitel schon in Reichweite — den Rest übernimmt die KI aus `04-ki-second-brain`.
