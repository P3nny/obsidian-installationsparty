# Bonus: Command Line

*Du bist hier, weil Claudian im Hintergrund genau dieses Werkzeug benutzt, um in deinem Vault zu lesen und zu schreiben. Damit Du besser verstehst, was da passiert, ist Wissen über die Command Line hilfreich und was sie alles kann. *

Inhaltlich angelehnt an das [Django Girls Tutorial](https://tutorial.djangogirls.org/en/intro_to_command_line/), die ImageMagick-Übung an [Code4Girls](https://github.com/P3nny/Code4Girls_4U/blob/master/Code4Girls%20-%20Command%20Line.ipynb) — plus ein paar zusätzliche Übungen, die zeigen, wie viel Power in diesem unscheinbaren schwarzen Fenster steckt.

## Was ist die Command Line

Die Command Line (auch: [[Terminal]], Konsole, CLI, Prompt) ist der ursprüngliche "Prompt". Bevor es Windows und andere graphische Buntzeroberflächen gab, tippten Programmierer:innen Befehle ein und der Computer erledigte textbasiert, was du heute mit der Maus machst. Allerdings mussten die Befehle als Programmiersprache gegeben werden, damit die Computer sie verstanden. Wenn man "Computersprache" spricht, kann eine Zeile auf der Kommandozeile viele Klicks mit der Maus ersetzen. 

Auswendig lernen musst du davon nichts, dafür hast du inzwischen eine KI. Aber zumindest im Ansatz zu verstehen, was sie da tun will, lohnt sich — spätestens, wenn sie mal etwas anderes tut als erwartet.

## Terminal öffnen

- **macOS:** Launchpad → Andere → Terminal
- **Linux:** meist unter Anwendungen → Zubehör → Terminal (je nach System leicht anders)
- **Windows mit Git Bash** (aus [[00-installation#Schritt 10: Ein besseres Windows-Terminal|Installation, Schritt 10]]): Windows-Taste drücken, „**Git Bash**" eingeben, Enter — öffnet ein eigenes Fenster. Empfohlen für dieses Kapitel: Alle Befehle darin funktionieren exakt wie auf Mac/Linux beschrieben, ganz ohne PowerShell-Alternativen.
- **Windows ohne Git Bash:** Windows-Taste drücken, „Terminal", „PowerShell" oder „cmd" eingeben (je nachdem, was installiert ist — siehe nächster Abschnitt) und Enter drücken

Du siehst danach ein Fenster mit einem blinkenden Cursor, der auf deine Eingabe wartet — das nennt man den **Prompt**. Auf Mac/Linux endet er meist mit `$`, auf Windows mit `>`. Diesen Anfangsteil tippst du nie selbst mit, er ist schon da.

## Windows: Welches Terminal habe ich?

*(Mac/Linux können diesen Abschnitt überspringen — dort gibt's nur ein Terminal.)*

Windows bringt mehrere Terminals mit, die unterschiedlich viel können. Am schnellsten findest du heraus, welches du gerade offen hast, indem du Folgendes eintippst:

```
$PSVersionTable.PSVersion
```

- Kommt eine **Versionsnummer** zurück → du bist in **PowerShell**. Die meisten Befehle in diesem Kapitel funktionieren hier mit der Windows-Spalte aus den Tabellen unten.
- Kommt eine **Fehlermeldung** (etwa „wird nicht als Name eines Cmdlets erkannt") → du bist in **cmd / Eingabeaufforderung**, der einfachsten Variante.

*Schon oben Git Bash geöffnet (siehe „Terminal öffnen")? Dann betrifft dich dieser Abschnitt nicht — für dich gilt überall die Mac/Linux-Spalte.*

## Erste Schritte

**Übung:** Tippe die folgenden Befehle nacheinander ein (Enter nicht vergessen) und schau, was passiert:

| Befehl (Mac/Linux) | Befehl (Windows)                              | Was er tut                                     |
| ------------------ | --------------------------------------------- | ---------------------------------------------- |
| `whoami`           | `whoami`                                      | zeigt deinen Benutzernamen                     |
| `pwd`              | PowerShell: `pwd` · cmd: `cd` (ohne Argument) | zeigt, in welchem Ordner du gerade bist        |
| `ls`               | `dir`                                         | listet Dateien und Ordner an diesem Ort        |
| cd ..              | cd ..                                         | Geht wieder zurück in den nächsthöheren Ordner |


*Tipp: Tippe die Befehle selbst ab, statt sie zu kopieren — so bleiben sie besser hängen.*

## Verzeichnisse wechseln und anlegen

**Übung:**

1. Wechsle in deinen Desktop-Ordner: `cd Desktop`
2. Prüfe, ob es geklappt hat (`pwd`; in der klassischen Eingabeaufforderung: `cd` ohne Argument)
3. Lege einen neuen Ordner namens `uebung` an: `mkdir uebung`
4. Wechsle hinein und lege darin einen weiteren Ordner namens `test` an

*Tipp: Tippst du die ersten Buchstaben eines Ordnernamens und drückst dann Tab, vervollständigt das Terminal den Rest automatisch.*

## Eine Datei erstellen und anzeigen

**Übung:** Du bist noch im `test`-Ordner von eben. Lege dort eine Textdatei an und lass dir ihren Inhalt anzeigen:

```
echo "Hallo Workshop!" > notiz.txt
```
```
cat notiz.txt
```

*Windows: `cat` funktioniert in PowerShell genauso; in der klassischen Eingabeaufforderung heißt der Befehl `type notiz.txt`.*

- `>` = leitet die Ausgabe von `echo` nicht auf den Bildschirm, sondern **in eine neue Datei** um. Gibt es die Datei schon, wird ihr Inhalt überschrieben.
- `cat notiz.txt` = zeigt den Dateiinhalt direkt im Terminal an, ganz ohne Editor zu öffnen

**Auflösung:** Im Terminal erscheint `Hallo Workshop!` — derselbe Text, den du gerade mit `echo` in die Datei geschrieben hast.

## Aufräumen

**Übung:** Geh zurück zum Desktop (`cd ..`) und lösche den `uebung`-Ordner wieder komplett:

⚠️ **Achtung:** Gelöschte Dateien über die Command Line landen nicht im Papierkorb — sie sind sofort und unwiderruflich weg. Immer zweimal hinschauen, bevor du `rm` oder `rmdir` drückst.

- Mac/Linux/Git Bash: `rm -r uebung`
- Windows PowerShell: `rm -r uebung`
- Windows cmd (Eingabeaufforderung): `rmdir /S uebung` — cmd fragt nochmal nach, mit `J` bestätigen

Zum Schluss kannst du das Terminal mit dem Befehl `exit` wieder schließen.

| Befehl (Mac/Linux) | Befehl (Windows) | Was er tut            |
| ------------------ | ---------------- | --------------------- |
| `exit`             | `exit`           | schließt das Terminal |

Alle Befehle von oben — plus ein paar mehr fürs Textverarbeiten (grep (Suche), wc (Wörter zählen), head (erste Zeilen anzeigen), sort (Sortieren)) — zum Nachschlagen im [[2-cheatsheet-command-line|Cheatsheet Command Line]].

---

## Jetzt wird's spielerisch: drei Power-Übungen

Die Command Line kann weit mehr als Ordner verschieben. Hier drei kleine, greifbare Beispiele, was möglich ist, sobald man Befehle kombiniert.

### 1. Eine echte Pipeline: dein Second Brain auf einen Blick

Drei Command Line - Werkzeuge zu einer Pipeline kombiniert: `grep` durchsucht Text nach einem Muster, `sort` bringt Zeilen nebeneinander, `uniq -c` zählt, wie oft jede vorkommt.

**Zum Warmwerden:** Wechsle in deinen Vault-Ordner (entweder mit cd oder im Explorer auf den Ordner klicken und rechte Maustaste "im Terminal öffnen) und durchsuche alle Markdown-Dateien nach dem Wort „OKF":

```
grep -r "OKF" . --include="*.md" | sort
```

- `grep -r "OKF" .` = durchsuche rekursiv (auch Unterordner) ab dem aktuellen Ordner (`.`) nach „OKF"
- `--include="*.md"` = nur in `.md`-Dateien suchen
- `| sort` = die Fundstellen alphabetisch sortiert ausgeben

**Jetzt eine Nummer größer — eine echte Bestandsaufnahme deines Second Brains:**

```
grep -h "^type:" notizen/*.md | sort | uniq -c | sort -rn
```

- `grep -h "^type:" notizen/*.md` = durchsucht jede Notiz im Ordner nach der Frontmatter-Zeile `type:`, `-h` unterdrückt die Dateinamen in der Ausgabe
- `sort` = bringt gleiche Werte nebeneinander — Voraussetzung, damit `uniq` sie erkennt
- `uniq -c` = zählt, wie oft jeder `type`-Wert vorkommt
- `sort -rn` = sortiert nach dieser Zahl, absteigend (`r` = reverse, `n` = numerisch)

**Auflösung:** Die Ausgabe zeigt dir z. B. `3 type: Konzept`, `2 type: Tool` — auf einen Blick, welche Notiz-Arten in deinem Vault am häufigsten sind. Kein Plugin, keine KI, vier eingebaute Werkzeuge kombiniert. Genau so durchsuchen und verdichten erfahrene Nutzerinnen riesige Codebasen oder Logdateien in Sekunden, statt jede Datei einzeln zu öffnen.

*Windows-Hinweis: In PowerShell funktioniert die Bestandsaufnahme ähnlich mit `Select-String -Path notizen\*.md -Pattern "^type:" | Group-Object Line | Sort-Object Count -Descending`. Für die Original-Unix-Befehle empfiehlt sich Git Bash.*

### 2. Aus Einzelbildern ein GIF bauen: dein Pixel-Einhorn wird lebendig

![[code4girls.png|150]]

Mit dem Werkzeug **ImageMagick** lässt sich aus einer Reihe von Bildern in Sekunden eine Animation basteln. Im Vault liegen unter `notizen/bilder/marie/` schon 24 fertige Frames eines Pixel-Einhorns (`marie_0.png` bis `marie_23.png`) — die baust du jetzt zu einem laufenden GIF zusammen.[^1]

**So soll's am Ende aussehen:**

![[unicorn.gif]]

**Installation:** siehe [[00-installation#Schritt 11: Werkzeuge für die Spaß-Übungen|Installation, Teil D, Schritt 11]] — dort auch die Variante ohne Adminrechte ([[Ohne Adminrechte]]).

**Übung:** Wechsle zunächst in `/notizen/bilder/marie` (mit `cd` oder im Explorer/Finder auf den Ordner `notizen/bilder/marie` klicken und „Im Terminal öffnen"), dann baue die Animation:

```
convert -delay 60 -loop 0 marie_{0..23}.png mariechen.gif
```

- `-delay 60` = 0,6 Sekunden zwischen den Bildern
- `-loop 0` = Animation läuft endlos
- `marie_{0..23}.png` = zählt automatisch von `marie_0.png` bis `marie_23.png` hoch — eine Bash-Kurzschreibweise namens **Brace Expansion**

*Warum nicht einfach der Platzhalter `*.png` (dasselbe `*` wie bei `*.md` in der Pipeline-Übung oben)? Weil diese Dateien `marie_0` bis `marie_23` heißen, ohne führende Nullen — `*` sortiert alphabetisch (`marie_1`, `marie_10`, `marie_11`, … `marie_2`, …) statt numerisch, und die Animation würde durcheinanderspringen. Mit `{0..23}` bekommst du garantiert die richtige Reihenfolge.*

*Windows-Hinweis: `{0..23}` ist eine Bash-Funktion und läuft nur in Git Bash, nicht in PowerShell/cmd — noch ein Grund, für dieses Kapitel bei Git Bash zu bleiben (siehe „Terminal öffnen" oben).*

**Auflösung:** Im Ordner `notizen/bilder/marie/` liegt jetzt `mariechen.gif` — einfach in Obsidians Dateiliste anklicken und deinem Einhorn beim Laufen zuschauen.

### 3. Eine sprechende Kuh: `cowsay` (optional — überspring das gerne, wenn's nicht klappt)

Es gibt eine große Entwicklergemeinschaft, die zusätzliche Programme fürs Terminal schreibt. `cowsay` ist eines davon: Es packt eingegebenen Text in eine ASCII-Art-Kuh mit Sprechblase — nutzlos und großartig zugleich, und ein guter erster Kontakt mit **Pipes** (`|`), also dem Weiterreichen von Ausgaben zwischen Programmen.

*Diese Übung ist die launischste im ganzen Kapitel: Auf manchen Windows-Rechnern verweigert `Install-Module` grundsätzlich den Dienst — nicht wegen eines falschen Befehls, sondern weil Firmenrichtlinien den Zugriff auf die PowerShell Gallery sperren oder ein benötigter Paketanbieter fehlt. Klappt's nicht in zwei, drei Versuchen: einfach überspringen, für den Rest des Kapitels brauchst du es nicht.*

**Installation:**

| Werkzeug   | Mac/Linux                                          | Windows                                                |
| ---------- | --------------------------------------------------- | ------------------------------------------------------- |
| **cowsay** | `brew install cowsay` / `sudo apt install cowsay`   | `Install-Module -Name CowsaySharp -Scope CurrentUser`    |

**Keine Adminrechte?** Geht trotzdem — siehe [[Ohne Adminrechte]].

*Windows-Hinweis: Git Bash bringt anders als Mac/Linux keinen Paketmanager mit (kein `apt`), `cowsay` lässt sich darüber also nicht nachinstallieren. Nimm stattdessen das PowerShell-Modul oben.*

**Übung (Mac/Linux):**
```
echo "Hallo Workshop!" | cowsay
```

Das `|` (Pipe) leitet die Ausgabe von `echo` als Eingabe an `cowsay` weiter, statt sie einfach auf dem Bildschirm auszugeben.

**Übung (Windows/PowerShell):**
```
Get-Cowsay -message "Hallo Workshop!"
```

Das PowerShell-Modul bringt sein eigenes Kommando statt der Pipe mit — Ergebnis ist dasselbe.

*Meldet PowerShell dazu einen Parameter-Fehler (nicht den grundsätzlichen Installationsfehler von oben): `Get-Help Get-Cowsay -Examples` zeigt die genaue Syntax deiner installierten Version.*

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

---

## Inspiration: Was man mit ein bisschen Programmierung noch alles automatisieren könnte

Diese Liste orientiert sich am Aufbau des Buches [*Automate the Boring Stuff with Python*](https://automatetheboringstuff.com/) von Al Sweigart (kostenlos online lesbar) — für alle, die nach dem Workshop tiefer einsteigen wollen:

- Web-Inhalte automatisch durchsuchen, herunterladen oder Formulare ausfüllen
- Text in großen Textmengen oder Dateien automatisch finden und ersetzen (Stichwort „Muster erkennen" — reguläre Ausdrücke)
- Dateien automatisch umbenennen, sortieren, verschieben oder komprimieren
- Excel-Tabellen oder Google Sheets automatisch befüllen oder auswerten
- PDFs und Word-Dokumente automatisch zusammenführen, aufteilen oder Text daraus extrahieren
- CSV-, JSON- oder XML-Dateien automatisch verarbeiten
- Zeitgesteuerte Aufgaben einrichten, die täglich oder wöchentlich von selbst laufen (Stichwort Cron aus dem Bonus-Kapitel Power-Usecase!)
- Automatisch E-Mails, SMS oder Push-Benachrichtigungen verschicken
- Diagramme erstellen oder Bilder automatisch bearbeiten (Logo einfügen, Größe ändern, drehen)
- Text aus Screenshots oder Fotos erkennen (OCR)
- Sich wiederholende Maus- und Tastatur-Aktionen automatisieren
- Text vorlesen lassen oder Sprache automatisch in Text umwandeln

Vieles davon ist mit den Grundlagen aus diesem Kapitel schon in Reichweite — den Rest übernimmt die KI aus `04-ki-second-brain`.

[^1]: Idee und Bildmaterial für die GIF-Übung aus P3nny, „Code4Girls – Command Line" ([GitHub](https://github.com/P3nny/Code4Girls_4U/blob/master/Code4Girls%20-%20Command%20Line.ipynb)).
